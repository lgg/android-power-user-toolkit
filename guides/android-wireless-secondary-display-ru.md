# Как использовать другое Android-устройство как настоящий беспроводной второй экран

[English version](android-wireless-secondary-display.md)

Этот гайд показывает, как превратить другой Android-телефон или планшет в **настоящий независимый второй экран** для Android-устройства — не просто зеркалирование.

В результате:

- основной Android-девайс продолжает использовать свой экран;
- второй Android-девайс получает отдельный виртуальный дисплей по Wi-Fi;
- приложения могут независимо работать на этом виртуальном дисплее;
- тач на принимающем устройстве может управлять удалённым экраном;
- фирменные desktop/PC-режимы вроде Lenovo PC Mode могут оставаться включёнными, а отдельные уже запущенные приложения можно переносить на беспроводной экран.

Это рабочая схема, к которой мы пришли после тестирования нескольких вариантов Android multi-display.

## Проверенная конфигурация

Полная схема была проверена **2026-10-01** на:

- **Основное устройство:** Lenovo Xiaoxin Pad Pro 12.7 (2025)
- **Модель:** TB375FC
- **SoC:** MediaTek Dimensity 8300
- **ОС:** Android 15
- **Прошивка:** ZUXOS 1.1.04.287
- **Фирменный desktop mode:** Lenovo PC Mode
- **MagicDesk:** 1.13 (build 214)
- **Рабочая версия Shizuku после troubleshooting:** 13.5.4
- **Приёмник:** Android-телефон с Moonlight

Это не Lenovo-only решение. Основной механизм использует стандартные Android virtual-display/task API через Shizuku и должен быть применим к другим совместимым Android-устройствам. Но OEM-прошивки могут по-разному вмешиваться в multi-display, поэтому на отдельных устройствах возможны дополнительные нюансы.

## За что отвечает каждое приложение

| Приложение | Роль |
| --- | --- |
| [Shizuku](https://github.com/RikkaApps/Shizuku) | Даёт приложениям доступ к привилегированным Android API без полноценного root. |
| [Mirror](https://github.com/jqssun/android-display-mirror) | Создаёт виртуальный дисплей и отдаёт его через встроенный Sunshine-сервер. Создание/стрим дисплея может работать без Shizuku, но **удалённый input требует Shizuku**. |
| [Extend](https://github.com/jqssun/android-display-extend) | Необязательный, но полезный менеджер дисплеев: DPI/разрешение, размещение приложений, ввод и управление дисплеями. |
| [Moonlight](https://github.com/moonlight-stream/moonlight-android) | Работает на втором Android-девайсе и показывает/управляет Sunshine-стримом. |
| [MagicDesk](https://github.com/mekhontsev/magicdesk) | Умеет переносить **уже запущенные Android tasks** между дисплеями. Это ключевой обход для OEM desktop mode, который перехватывает обычный запуск приложений. |

### Почему MagicDesk здесь критичен

Обычный запрос «запусти приложение на display X» может быть перехвачен фирменной desktop-оболочкой.

Именно это произошло у нас с Lenovo PC Mode: когда PC Mode уже был включён, **Extend → Cast Applications** приводил к тому, что Lenovo открывал приложение окном на основном экране PC Mode вместо виртуального Sunshine-дисплея.

MagicDesk решает другую задачу: он может взять **уже существующий живой Android task** и перенести его на другой дисплей. В нашем тесте это обошло перехват нового запуска со стороны Lenovo.

## Требования

Для схемы ниже:

- основной Android-девайс с **Android 14+** для актуальных сборок MagicDesk;
- включённые Developer Options;
- Shizuku, запущенный через Wireless Debugging, USB debugging или root, **если нужен удалённый input и перенос tasks через MagicDesk**;
- основной и принимающий девайс в одной локальной сети для самого простого подключения Moonlight;
- Moonlight на принимающем устройстве;
- Mirror, Extend и MagicDesk на основном устройстве.

Если на одном из устройств включён VPN и Moonlight не находит хост или не подключается, временно отключите VPN на этапе настройки. Позже VPN может работать нормально, если локальная сеть корректно исключена из туннеля.

## Скачивание

### Основной Android-девайс

- Shizuku: https://github.com/RikkaApps/Shizuku/releases
  - Если на Shizuku 13.6.0 возникает описанный ниже UserService timeout, проверенный fallback: https://github.com/RikkaApps/Shizuku/releases/tag/v13.5.4
- Mirror: https://github.com/jqssun/android-display-mirror/releases/latest
- Extend: https://github.com/jqssun/android-display-extend/releases/latest
- MagicDesk: https://github.com/mekhontsev/magicdesk/releases/latest

### Принимающий Android-девайс

- Moonlight: https://play.google.com/store/apps/details?id=com.limelight
- Исходники/релизы: https://github.com/moonlight-stream/moonlight-android

## Шаг 1 — Запускаем Shizuku

На Android 11+ самый удобный вариант без root обычно — Wireless Debugging:

1. Включите **Developer options**.
2. Включите **Wireless debugging**.
3. Откройте Shizuku.
4. Выполните pairing через **Pair device with pairing code**.
5. Запустите Shizuku.
6. Убедитесь, что Shizuku сообщает, что сервис работает.

Когда Mirror, Extend и MagicDesk попросят доступ к Shizuku — разрешите его. Mirror умеет создавать и стримить virtual display без Shizuku, но upstream-документация прямо указывает, что **удалённый input требует Shizuku**; MagicDesk также требует privileged access для глобального списка running tasks и их переноса между дисплеями.

## Шаг 2 — Создаём виртуальный дисплей в Mirror

Откройте **Mirror** на основном устройстве и запустите виртуальный дисплей через встроенный Sunshine.

Стартовые настройки, которые сработали у нас:

- **Send input to external display:** ON
- **Use H.265:** сначала OFF ради максимальной совместимости; потом можно включить
- **Show cursor location:** OFF
- **Auto connect Moonlight beta:** OFF на этапе ручной настройки

Mirror должен создать Android-дисплей с именем примерно:

```text
Sunshine [13]
```

Числовой ID дисплея временный и может меняться при каждом пересоздании виртуального экрана.

## Шаг 3 — Подключаем Moonlight

На принимающем устройстве:

1. Откройте Moonlight.
2. Выполните pairing/подключение к Sunshine-серверу, который поднял Mirror.
3. Запустите стрим.

На этом этапе Moonlight может показать:

> Please select application to cast via the managed display or use mirror only mode.

Это **нормально**. Виртуальный дисплей уже существует и стримится, но Android пока не разместил на нём приложение.

Если нужен прямой тач по координатам, а не режим тачпада, выключите на принимающем устройстве:

**Moonlight → Use touchscreen as a trackpad**

если эта опция включена.

## Шаг 4 — Не включаем Managed Virtual Display Mode в Extend

Extend видит созданный Mirror дисплей и полезен для его настройки/диагностики.

Но в нашей проверенной конфигурации включение:

**Managed Virtual Display Mode**

приводило к отключению Moonlight и ломало рабочий lifecycle Mirror/Sunshine до перезапуска стрима.

Для этой схемы оставляйте **Managed Virtual Display Mode выключенным**.

Виртуальным дисплеем должен владеть Mirror/Sunshine.

## Шаг 5 — Даём MagicDesk нормальный shell-доступ

Откройте MagicDesk.

Нужное состояние:

```text
Access: shell
Service UID: 2000
```

Типовая настройка:

- **Settings → Integrations → Privileged service:** Shizuku
- **Settings → Limits → Maximum access:** Shell

После изменения startup/integration-настроек MagicDesk используйте именно **Exit MagicDesk**, а затем откройте приложение заново. Простого свайпа из Recents может быть недостаточно.

**Не нужно** запускать собственный MagicDesk Desktop ради этого гайда. Нам нужны только его независимые display/task tools.

## Шаг 6 — Проверяем перенос task до включения OEM desktop mode

Сначала проверяем базовую механику без Lenovo PC Mode, DeX и других фирменных оболочек:

1. Убедитесь, что Mirror/Sunshine запущен.
2. Убедитесь, что Moonlight подключён.
3. Откройте на основном устройстве приложение, например Chrome.
4. Откройте MagicDesk.
5. Выберите дисплей **Sunshine [X]**.
6. Откройте **Apps**.
7. Перейдите во вкладку **Running applications**.
8. Выберите Chrome.

MagicDesk должен показать действие примерно такого вида:

```text
Move from display 0 (task 123)
```

Нажмите его.

Chrome должен исчезнуть с основного экрана и появиться на Moonlight-приёмнике без холодного перезапуска.

Если это сработало — базовый Android-to-Android extended display уже работает.

## Шаг 7 — Используем вместе с Lenovo PC Mode или другим OEM desktop mode

Теперь подключаем фирменный desktop mode.

1. Оставьте Mirror/Sunshine и Moonlight запущенными.
2. Включите фирменный desktop mode — в нашей конфигурации это **Lenovo PC Mode**.
3. Откройте нужное приложение внутри PC Mode.
4. Вернитесь в MagicDesk.
5. Выберите виртуальный дисплей **Sunshine [X]**.
6. Откройте **Apps → Running applications**.
7. Найдите уже запущенное приложение.
8. Выберите **Move from display 0 ...**.

На Lenovo TB375FC это успешно перенесло уже существующий Chrome task из Lenovo PC Mode на виртуальный Sunshine-дисплей, при этом сам PC Mode продолжил работать.

В итоге схема выглядит так:

```text
Основной планшет
├── Физический экран → Lenovo PC Mode
└── Виртуальный Sunshine display → отдельное Android-приложение
                                         │
                                         └── Wi-Fi → Moonlight → второй телефон/планшет
```

## Поведение Lenovo PC Mode, которое мы обнаружили

### Что не сработало

При уже включённом Lenovo PC Mode:

**Extend → Cast Applications → приложение**

перехватывался Lenovo, и приложение открывалось окном на основном PC Mode desktop вместо Sunshine.

### Что сработало

Сработали два подхода:

1. **Закастить приложение до включения PC Mode.**  
   Уже размещённое на виртуальном экране приложение продолжало там работать после включения PC Mode.

2. **Лучший вариант: перенести уже запущенный task через MagicDesk.**  
   Это позволяет сначала включить PC Mode, а потом переносить нужные живые приложения на Sunshine.

Второй вариант оказался наиболее удобным.

## Проблема Shizuku 13.6.0 + MediaTek UserService

Это был самый сложный затык в нашем тесте.

### Симптомы

Сам Shizuku выглядел полностью рабочим, Mirror/Extend могли его использовать, но MagicDesk оставался в состоянии:

```text
Access: none
Privileged service is connecting
```

В MagicDesk Diagnostics было:

```text
Privileged runtime: unavailable
WARN [SHELL-001] Privileged command service: Privileged service is connecting
Timed out waiting for privileged service binding
```

Тестовое устройство использовало **MediaTek Dimensity 8300** и **Shizuku 13.6.0.r1086**.

### Что исправило проблему

Откат Shizuku на:

**13.5.4**

сразу исправил binding привилегированного UserService в MagicDesk после перезапуска Shizuku/MagicDesk и повторной выдачи разрешений.

После этого MagicDesk получил shell-доступ, и перенос tasks заработал.

На момент нашего теста (**2026-10-01**) Shizuku 13.6.0 был актуальным релизом, и в upstream уже было несколько открытых issue, совпадающих с нашим сценарием:

- [#1198 — User services don't work on MediaTek devices](https://github.com/RikkaApps/Shizuku/issues/1198)
- [#2443 — Shizuku hangs / stops responding to shell commands after Wi-Fi state changes (regression in 13.6.0)](https://github.com/RikkaApps/Shizuku/issues/2443)
- [#2463 — Had to downgrade from 13.6.0 to 13.5.4 after encountering problems](https://github.com/RikkaApps/Shizuku/issues/2463)

В issue #2463 отдельно описан странный симптом, когда приложение **13.6.0 продолжает показывать “Version 13.5, adb”**. На нашем Lenovo перед откатом мы наблюдали тот же рассинхрон.

### Рекомендация

**Не нужно** навсегда ставить Shizuku 13.5.4 на все устройства.

Начинайте с актуальной версии Shizuku. Но если одновременно выполняется следующее:

- Shizuku пишет, что работает;
- доступ MagicDesk к Shizuku уже выдан;
- MagicDesk висит на `Privileged service is connecting`;
- Diagnostics показывает timeout при privileged service binding;
- особенно если устройство на MediaTek;

то проверка официального релиза [Shizuku 13.5.4](https://github.com/RikkaApps/Shizuku/releases/tag/v13.5.4) — очень логичный troubleshooting step.

Поскольку проблема зависит от версии и прошивки, не стоит откатываться без совпадающих симптомов. В будущих версиях Shizuku регрессия может быть исправлена — сначала проверяйте актуальные upstream issues и release notes.

## Troubleshooting

| Проблема | Что проверить |
| --- | --- |
| Moonlight видит хост, но показывает только сообщение "select application" | Это нормально, пока на виртуальный дисплей не помещён task. Перенесите/закастите приложение на Sunshine. |
| Тач работает как тачпад ноутбука, а не как прямое касание | Выключите **Use touchscreen as a trackpad** в Moonlight. |
| Moonlight не находит хост / не выполняет pairing | Устройства должны быть в одной LAN; временно отключите VPN/firewall; при необходимости используйте ручное подключение. |
| Виртуальный экран пересоздался с другим номером | Нормально. ID вроде 8/13/14 не постоянные. Выберите актуальный Sunshine display в MagicDesk/Extend. |
| Extend снова открывает приложение внутри Lenovo PC Mode | Используйте MagicDesk **Running applications** и переносите уже запущенный task вместо нового запуска. |
| Moonlight отключается после Managed Virtual Display Mode | Выключите этот режим и оставьте владение дисплеем за Mirror. При необходимости перезапустите Mirror/Sunshine. |
| MagicDesk показывает `Access: none`, хотя разрешение Shizuku дано | Проверьте, что Shizuku запущен, в MagicDesk выбран Shizuku, Maximum access = Shell, затем **Exit MagicDesk** и повторный запуск. |
| Diagnostics показывает `Timed out waiting for privileged service binding` на MediaTek | Если стоит Shizuku 13.6.x, попробуйте 13.5.4. На TB375FC это полностью исправило проблему. |
| Отдельное приложение не переносится или падает | Некоторые приложения/OEM-фреймворки плохо работают с secondary display. Проверьте другое приложение, чтобы отделить app-specific проблему от display stack. |

## Extend и MagicDesk — не одно и то же

Функции пересекаются, но роль разная.

**Extend** особенно удобен для:

- выбора дисплеев;
- запуска/каста приложений на выбранный дисплей;
- DPI/разрешения/ориентации;
- touchpad/touchscreen/input tools.

**MagicDesk** особенно важен здесь, потому что умеет:

- получать список живых running tasks;
- **переносить конкретный уже существующий task на другой display**.

Именно это различие позволило обойти Lenovo PC Mode.

## Почему это лучше обычного screen mirroring

Обычное зеркалирование показывает одно и то же содержимое два раза.

Эта схема создаёт отдельный Android `VirtualDisplay`, поэтому на втором устройстве может быть приложение, которого вообще нет на физическом экране основного девайса.

То есть Android-планшет потенциально превращается в:

- display 1: OEM desktop/PC mode;
- display 2: второй Android-планшет;
- display 3: ещё один виртуальный/физический экран — если железо и прошивка это позволяют.

## Связанные проекты

- Mirror: https://github.com/jqssun/android-display-mirror
- Extend: https://github.com/jqssun/android-display-extend
- Shizuku: https://github.com/RikkaApps/Shizuku
- Moonlight Android: https://github.com/moonlight-stream/moonlight-android
- MagicDesk: https://github.com/mekhontsev/magicdesk

## Проверено, но не гарантировано на каждом Android

Android multi-display сильно зависит от:

- OEM-прошивки;
- версии Android;
- реализации desktop mode;
- поддержки secondary display конкретным приложением;
- изменений системных API и Shizuku.

Результат на Lenovo TB375FC подтверждает, что схема может работать даже тогда, когда фирменный desktop mode производителя сам не даёт нужного extended-display поведения. Но другие устройства могут вести себя иначе.

Если вы подтвердили работу на другом устройстве/ROM — PR или issue с моделью, Android-версией, прошивкой, версией Shizuku и результатом теста будет очень полезен.

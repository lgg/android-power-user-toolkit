# Android Power User Toolkit

[English version](README.md)

Кураторская подборка Android-инструментов, приложений, фиксов, обходных решений и практических пошаговых гайдов для продвинутых пользователей.

Цель простая: собрать в одном месте полезный Android-софт, который решает реальные и часто очень специфичные задачи — особенно те, ради которых обычно приходится часами копаться по форумам, GitHub, Reddit и поисковикам.

В репозитории есть два типа материалов:

- **каталог** полезных приложений с коротким понятным описанием задачи и нормальными ссылками на исходники/официальные страницы и установку;
- **подробные гайды** для сценариев, где нужно несколько приложений, специальные разрешения или неочевидные workaround'ы.

> **Принцип:** по возможности ссылка ведёт на оригинальный репозиторий исходников или официальный сайт разработчика, а установка — на Google Play либо официальный канал релизов проекта.

## Гайды

| Гайд | Что решает |
| --- | --- |
| [Использовать другое Android-устройство как настоящий беспроводной второй экран](guides/android-wireless-secondary-display-ru.md) | Создаёт независимый Android virtual display, стримит его на другой телефон/планшет с тач-управлением и может работать одновременно с фирменными desktop/PC mode. Включает найденный workaround для Lenovo PC Mode и проблему Shizuku/MediaTek, с которой мы столкнулись. |

## Дисплеи, remote desktop и multi-screen

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **spacedesk** | Превращает Android-телефон или планшет в дополнительный монитор для Windows по Wi-Fi, LAN или USB, с поддержкой touch/input. Отличный вариант, когда **хост — Windows**. | [Официальный сайт](https://www.spacedesk.net/) | [Google Play](https://play.google.com/store/apps/details?id=ph.spacedesk.beta) |
| **Mirror — Screen Mirroring Manager** | Создаёт Android virtual displays и умеет стримить их через встроенный Sunshine-сервер в Moonlight. Это основа нашей Android-to-Android multi-display схемы. | [GitHub](https://github.com/jqssun/android-display-mirror) | [Google Play](https://play.google.com/store/apps/details?id=io.github.jqssun.displaymirror) · [GitHub Releases](https://github.com/jqssun/android-display-mirror/releases/latest) |
| **Extend — Display Manager for Android** | Управляет физическими и виртуальными Android-дисплеями, запускает приложения на выбранном экране, помогает с display behavior и input. Полезный компаньон к Mirror. | [GitHub](https://github.com/jqssun/android-display-extend) | [Google Play](https://play.google.com/store/apps/details?id=io.github.jqssun.displayextend) · [GitHub Releases](https://github.com/jqssun/android-display-extend/releases/latest) |
| **Moonlight** | Open-source клиент Sunshine/GameStream. В этой подборке используется на **принимающем Android-устройстве**, чтобы видеть и управлять виртуальным дисплеем основного Android-девайса. | [GitHub](https://github.com/moonlight-stream/moonlight-android) | [Google Play](https://play.google.com/store/apps/details?id=com.limelight) · [GitHub Releases](https://github.com/moonlight-stream/moonlight-android/releases) |
| **MagicDesk** | Android workstation и multi-display manager. Ключевая возможность — **перенос уже запущенных Android tasks между дисплеями**, что позволяет обходить ограничения фирменных desktop mode, перехватывающих обычный запуск приложений. | [GitHub](https://github.com/mekhontsev/magicdesk) | [GitHub Releases](https://github.com/mekhontsev/magicdesk/releases/latest) |
| **Shizuku** | Даёт совместимым приложениям доступ к привилегированным Android API через ADB/root без необходимости давать каждому приложению полноценный root. Нужен для полного функционала нескольких инструментов из этой подборки. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Официальная документация](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

Полный гайд: [Android → Android беспроводной второй экран](guides/android-wireless-secondary-display-ru.md).

## Передача файлов и связь между устройствами

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **LocalSend** | Быстрая зашифрованная локальная передача файлов и текста между Android, iOS, Windows, macOS и Linux. Облако и интернет не нужны, если устройства находятся в одной LAN. Отличная AirDrop-подобная утилита для смешанного парка устройств. | [GitHub](https://github.com/localsend/localsend) · [Официальный сайт](https://localsend.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.localsend.localsend_app) |

## Системные настройки и power-user доступ

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Hidden Settings** | Открывает экраны Android-настроек, activities, диагностику и страницы производителя, до которых трудно или невозможно добраться через обычное меню Settings. Есть создание ярлыков и часть действий через Shizuku/root. | [Официальный сайт](https://www.ceyhanapps.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.ceyhan.sets) |
| **Shizuku** | Мост к привилегированным API, который используют многие продвинутые Android-утилиты без полноценного root. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Официальная документация](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

## Сеть, VPN и privacy-диагностика

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **RKNHardering** | Проверяет Android-устройство на признаки, по которым приложения могут обнаружить VPN/proxy: интерфейсы, маршруты, DNS, несовпадения публичного IP, локальные proxy, установленные VPN-приложения и другие сигналы. Полезен, чтобы понять, что другое приложение потенциально может узнать о вашем сетевом окружении. | [GitHub](https://github.com/xtclovver/RKNHardering) | [GitHub Releases](https://github.com/xtclovver/RKNHardering/releases/latest) · [F-Droid](https://f-droid.org/packages/com.notcvnt.rknhardering/) |

> RKNHardering — это **диагностический инструмент**, а не VPN и не гарантия того, что конфигурация «не детектируется». Проект отдельно маркирует подтверждённые проверки и сведения из сообщества/исследований, поэтому не стоит воспринимать каждый сигнал как безусловный факт без чтения upstream-документации.

## Android Auto и автомобильные head units

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Fermata Auto / Fermata Media Player** | Open-source медиаплеер с аудио, видео, IPTV, плейлистами и поддержкой Android Auto. Полезен, если возможностей штатных Android Auto media apps недостаточно. | [GitHub](https://github.com/AndreyPavlenko/Fermata) | [GitHub Releases](https://github.com/AndreyPavlenko/Fermata/releases/latest) |
| **Headunit Reloaded (HUR)** | Превращает Android-планшет или магнитолу в **Android Auto receiver/emulator**. Полезен для DIY head unit и планшета в автомобиле. Актуальное поведение USB/беспроводного подключения зависит от версии Android Auto и конкретного устройства — проверяйте текущие release notes в Google Play. | [Исторические GPL-исходники](https://github.com/borconi/headunit) *(legacy-код; не стоит считать его исходниками текущей Play-сборки)* · [официальная support-тема](https://forum.xda-developers.com/t/android-4-1-headunit-reloaded-for-android-auto-with-wifi.3432348/) | [Google Play](https://play.google.com/store/apps/details?id=gb.xxy.hr) |

### Примечание по Fermata Auto

Современные версии Android Auto жёстко ограничивают sideloaded apps. Проект Fermata отдельно описывает требования и workaround'ы для новых Android-версий, включая root-варианты и совместимые wireless adapters. Перед установкой проверяйте актуальную документацию проекта.

## Медиа, звук и стриминг

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **YouTube ReVanced / ReVanced Manager** | Open-source платформа для патчинга Android-приложений. Чаще всего используется для сборки кастомизированного YouTube-клиента с нужными патчами. Лучше использовать официальный Manager и патчить совместимый APK самостоятельно, а не скачивать случайные pre-patched APK. | [GitHub](https://github.com/ReVanced/revanced-manager) · [Официальный сайт](https://revanced.app/) | [Официальная загрузка](https://revanced.app/download) · [GitHub Releases](https://github.com/ReVanced/revanced-manager/releases/latest) |
| **ReVanced GmsCore** | Форк microG от ReVanced для **non-root пропатченных Google-приложений**. Он рассчитан на работу рядом с обычными Google Play Services и нужен именно тогда, когда ReVanced-патч явно требует “GmsCore support”. | [GitHub](https://github.com/ReVanced/GmsCore) | [GitHub Releases](https://github.com/ReVanced/GmsCore/releases/latest) |
| **microG Services (upstream)** | Свободная open-source замена реализации Google Play Services API — в первую очередь для ROM/устройств, где обычные Google Play Services отсутствуют или намеренно не используются. **Это не то же самое, что ReVanced GmsCore.** | [GitHub](https://github.com/microg/GmsCore) · [Официальный сайт](https://microg.org/) | [Официальная инструкция загрузки](https://github.com/microg/GmsCore/wiki/Downloads) · [GitHub Releases](https://github.com/microg/GmsCore/releases/latest) |
| **AirMusic** | Передаёт звук почти из любого Android-приложения на AirPlay/AirPlay 2, Sonos, Chromecast, DLNA, HEOS, Roku, Fire TV и другие receivers по локальной сети. Особенно полезно, когда Android штатно не умеет выводить звук в нужную экосистему колонок. Само Android-приложение не публикуется как open source; отдельно есть официальный Magisk-модуль для опционального root-захвата аудио. | [Официальный сайт](https://www.airmusic.app/) · [официальный Magisk-модуль](https://github.com/Magisk-Modules-Repo/airmusic) | [Google Play — Pro](https://play.google.com/store/apps/details?id=app.airmusic.pro) |
| **AudioRelay** | Передаёт звук ПК на Android, позволяет использовать Android-телефон как микрофон для ПК или отправлять Android-аудио на другое устройство. Работает по Wi-Fi и USB и удобен для самодельной low-latency аудиомаршрутизации. | [Официальный сайт](https://audiorelay.net/) | [Google Play](https://play.google.com/store/apps/details?id=com.azefsw.audioconnect) · [Desktop downloads](https://audiorelay.net/downloads) |

## NFC и RFID

Используйте инструменты чтения/записи RFID/NFC только с картами, метками и системами, которыми вы владеете либо которые вам явно разрешено тестировать.

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **MIFARE Classic Tool (MCT)** | Низкоуровневая Android NFC-утилита для чтения, записи, анализа, ключей и дампов **MIFARE Classic** меток. Очень полезна для исследования совместимых карт и тегов. | [GitHub](https://github.com/ikarus23/MifareClassicTool) | [Google Play](https://play.google.com/store/apps/details?id=de.syss.MifareClassicTool) · [F-Droid](https://f-droid.org/packages/de.syss.MifareClassicTool/) · [официальный APK](https://www.icaria.de/mct/releases/) |
| **RFID Tools (RRG)** | Android frontend/toolkit для внешнего RFID/NFC-железа, включая Proxmark3 RDV4, ACR122U, Chameleon Mini и устройства класса PN532. | [GitHub](https://github.com/RfidResearchGroup/RFIDtools) | [Google Play](https://play.google.com/store/apps/details?id=com.rfidresearchgroup.rfidtools) · [GitHub Releases](https://github.com/RfidResearchGroup/RFIDtools/releases) |
| **NFC Tools** | Удобный general-purpose NFC reader/writer для NDEF-тегов и автоматизаций через NFC. Лучше подходит для обычных NFC-меток, чем для low-level MIFARE-исследований. | [Официальный сайт](https://www.wakdev.com/en/apps/nfc-tools-android.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc) |
| **NFC TagInfo by NXP** | Диагностическая утилита от NXP для определения типа NFC/RFID-тега и просмотра доступной информации о карте/метке. Отличный первый шаг, когда вы ещё не знаете, с каким типом тега имеете дело. | [NXP](https://www.nxp.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.taginfolite) |

> Возможности зависят от NFC-контроллера и прошивки телефона. Например, не каждый смартфон способен выполнять все операции с MIFARE Classic, даже если приложение само их поддерживает.

## Игры и бесплатные альтернативы

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Lichess** | Полностью бесплатная/libre open-source шахматная платформа: онлайн-игры, puzzles, анализ, studies, турниры и Stockfish. Сильная альтернатива без подписки для тех, кому не нужна платная экосистема Chess.com. | [GitHub](https://github.com/lichess-org/mobile) · [Официальный сайт](https://lichess.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.lichess.mobileV2) |

## Как отбираются приложения

Это не попытка собрать вообще все Android-приложения. Инструмент подходит для репозитория, если он хорошо делает хотя бы одну из вещей:

- решает конкретную проблему, которую Android или OEM нормально не решает;
- заменяет платный или cloud-locked workflow сильной бесплатной/open-source альтернативой;
- открывает полезные системные функции, обычно скрытые от пользователя;
- соединяет Android с ПК, автомобилем, аудиосистемой, дисплеями, NFC/RFID-железом или другими устройствами;
- очень полезен, но его трудно найти, если заранее не знаешь точное название.

## Зависимость от версий

- **Shizuku:** на части устройств/ROM есть репорты о регрессиях UserService в 13.6.0. На нашем MediaTek-девайсе сам Shizuku работал, Mirror/Extend тоже, но MagicDesk ловил timeout при UserService binding; откат на 13.5.4 всё исправил. Точные симптомы и upstream issues есть в [гайде по второму экрану](guides/android-wireless-secondary-display-ru.md#проблема-shizuku-1360--mediatek-userservice).
- **Android Auto:** Google может менять ограничения sideloaded apps и способы подключения стороннего head-unit софта. Поведение Fermata Auto и HUR нужно считать version-dependent и сверять с актуальными upstream notes.
- **Secondary displays:** Android/OEM-прошивка может переопределять стандартное multi-display поведение. Поддержка функции самим приложением не гарантирует, что конкретный OEM ROM разрешит её использовать.

## Безопасность и доверие

- Предпочитайте **официальный репозиторий разработчика, официальный сайт, Google Play, F-Droid или официальные GitHub Releases**.
- Не скачивайте случайные APK mirrors и pre-patched сборки, если проект предоставляет официальный канал распространения.
- Привилегированные инструменты вроде Shizuku, root-утилит, Android Auto workaround'ов и RFID writers могут менять системное поведение или данные. Сначала читайте upstream-документацию.
- Некоторые техники зависят от прошивки и версии Android. В гайдах этого репозитория отдельно указывается железо/ОС, на которых решение реально проверялось.

## Как внести вклад

PR и issues приветствуются. Хороший вклад должен объяснять **какую проблему решает инструмент**, а не просто содержать название приложения.

Рекомендуемый формат:

```text
Инструмент:
Какую проблему решает:
Почему полезен:
Исходники / официальный сайт:
Официальная установка:
Требования / ограничения:
Проверено на (необязательно):
```

---

Если какой-то инструмент однажды сэкономил вам несколько часов, потому что решил странную Android-проблему, которую нигде нормально не документируют — скорее всего, ему место здесь.

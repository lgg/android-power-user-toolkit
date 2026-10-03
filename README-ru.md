# Android Power User Toolkit

[English version](README.md)

Кураторская подборка Android-инструментов, приложений, фиксов, обходных решений и практических пошаговых гайдов для продвинутых пользователей.

> Последний ручной аудит: **2026-10-01**

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
| **SuperDisplay** | Превращает Android-планшет/телефон в производительный второй экран или графический планшет для Windows по USB/Wi-Fi, с поддержкой стилуса и давления на совместимом железе. | [Официальный сайт](https://superdisplay.app/) | [Google Play](https://play.google.com/store/apps/details?id=com.kelocube.mirrorclient) |
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

## Магазины приложений и управление пакетами

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **F-Droid** | Репозиторий и клиент для свободных/open-source Android-приложений. Полезен для FOSS-софта, которого нет в Google Play, и для community/reproducible builds. | [Официальный сайт](https://f-droid.org/) · [исходники клиента](https://gitlab.com/fdroid/fdroidclient) | [Официальная загрузка](https://f-droid.org/) |
| **SAI (Split APKs Installer)** | Устанавливает и экспортирует split APK bundles (`.apks`) из Android App Bundle, есть root и rootless способы установки. Upstream сейчас скорее maintenance-only, поэтому это полезный специализированный/legacy инструмент, а не активно развивающийся проект. | [GitHub](https://github.com/Aefyr/SAI) | [F-Droid](https://f-droid.org/packages/com.aefyr.sai.fdroid/) · [Google Play](https://play.google.com/store/apps/details?id=com.aefyr.sai) |
| **App Manager** | Очень мощный менеджер приложений: components, permissions, trackers, manifest, установка APK/APKS/APKM/XAPK, backup, debloat, logcat и множество ADB/root-assisted операций. | [GitHub](https://github.com/MuntashirAkon/AppManager) · [Документация](https://muntashirakon.github.io/AppManager/) | [F-Droid](https://f-droid.org/packages/io.github.muntashirakon.AppManager/) · [GitHub Releases](https://github.com/MuntashirAkon/AppManager/releases) |

## Системные настройки и power-user доступ

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **CPU X** | Подробная информация и диагностика устройства: SoC/CPU, RAM, камеры, сенсоры, батарея/ток/температура, мониторинг скорости сети и базовые аппаратные тесты. | [Сайт разработчика](https://adalve.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.abs.cpu_z_advance) |
| **Hidden Settings** | Открывает экраны Android-настроек, activities, диагностику и страницы производителя, до которых трудно или невозможно добраться через обычное меню Settings. Есть создание ярлыков и часть действий через Shizuku/root. | [Официальный сайт](https://www.ceyhanapps.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.ceyhan.sets) |
| **SetEdit (Settings Database Editor)** | Прямой редактор таблиц Android Settings database. Полезен для параметров, которые OEM не показывает в обычном UI. **Используйте осторожно:** неправильные значения могут сломать поведение системы; запись в SECURE/GLOBAL на некоторых Android/ROM требует ADB-разрешения или root. | Закрытые исходники / официальная дистрибуция через Google Play | [Google Play](https://play.google.com/store/apps/details?id=by4a.setedit22) |
| **Shizuku** | Мост к привилегированным API, который используют многие продвинутые Android-утилиты без полноценного root. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Официальная документация](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

## Клавиатуры, ввод и remapping

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Key Mapper** | Open-source инструмент для переназначения аппаратных клавиш/кнопок и автоматизации: физические клавиатуры, мышь, геймпады, volume/side buttons, гарнитуры и экранные кнопки. Есть гибкие triggers/actions/macros, constraints, app-specific mappings и Expert Mode для более глубокого системного перехвата ввода. | [GitHub](https://github.com/keymapperorg/KeyMapper) · [Официальный сайт / документация](https://keymapper.app/) | [Google Play](https://play.google.com/store/apps/details?id=io.github.sds100.keymapper) · [F-Droid](https://f-droid.org/packages/io.github.sds100.keymapper/) · [GitHub Releases](https://github.com/keymapperorg/KeyMapper/releases) |
| **Pastiera** | Современный GPLv3 Android IME с упором на физические клавиатуры. Есть настраиваемые layouts, Cyrillic/translit, JSON import/export, hardware-key shortcuts, переключение раскладок и полноценная экранная клавиатура. Подходит, если хочется одним IME закрыть и physical, и soft keyboard. Pastiera 0.86 — последняя feature-версия; активная разработка переезжает в Plektra. | [GitHub](https://github.com/palsoftware/pastiera) · [Официальный сайт](https://pastiera.eu/) | [GitHub Releases](https://github.com/palsoftware/pastiera/releases) |
| **Plektra** | GPLv3-преемник Pastiera, куда переносится активная разработка. Стоит отслеживать как современный physical-keyboard IME, но пока проект заметно более ранний, чем Pastiera. | [GitHub](https://github.com/pkb-rocks/plektra) | Исходники / releases по мере появления |
| **TypeQ25** | GPLv3 IME для Android-устройств с физической QWERTY-клавиатурой, в первую очередь Unihertz/Zinwa. Поддерживает modifier/navigation modes, shortcuts, редактирование layouts и multi-language input. | [GitHub](https://github.com/sriharshaKanukuntla/TypeQ25) | [GitHub Releases](https://github.com/sriharshaKanukuntla/TypeQ25/releases) |
| **KeymapKit** | Провайдер системных раскладок физической клавиатуры: добавляет Android hardware-keyboard layouts через KCM, не становясь IME и не требуя root, Accessibility или фонового сервиса. Полезен, когда в Android просто нет нужной раскладки. | [GitHub](https://github.com/mahmutaunal/KeymapKit) | [Google Play](https://play.google.com/store/apps/details?id=com.alpware.keymapkit) · [GitHub Releases](https://github.com/mahmutaunal/KeymapKit/releases) |
| **ExKeyMo** | Open-source генератор кастомных раскладок внешней клавиатуры без root. Текущая static-web версия прямо в браузере собирает подписанный layout-provider APK из KCM/настроенной раскладки. | [GitHub](https://github.com/ris58h/exkeymo) · [Web builder](https://ris58h.github.io/exkeymo/) | Сгенерировать APK через web builder |
| **External Keyboard Helper Pro (EKH)** | Старый, но всё ещё полезный hardware-keyboard IME для Bluetooth/USB-клавиатур. Поддерживает кастомные layouts и собственное переключение языка внутри IME, что помогает обходить приложения, которые перехватывают стандартный Android shortcut смены physical layout. **Closed-source/старый target SDK:** на новых Android Play может блокировать установку, тогда нужен sideload. | [Официальная документация](https://www.apedroid.com/android-applications/external-keyboard-helper/documentation) | [Google Play](https://play.google.com/store/apps/details?id=com.apedroid.hwkeyboardhelper) |

## Автоматизация, терминалы и файловые утилиты

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **MacroDroid** | No-code/low-code автоматизация Android на базе triggers, actions и constraints. Подходит для системных рутин, сети, уведомлений, расписаний и сложных сценариев без написания полноценного приложения. | [Официальный сайт](https://macrodroid.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid) |
| **Automate (LlamaLab)** | Мощная визуальная автоматизация на flowchart-блоках. Особенно удобна для сценариев по системным состояниям; есть блоки вроде определения hardware keyboard и смены input method, плюс privileged/ADB-assisted возможности для более глубоких действий. Бесплатной версии хватает для небольших flows в пределах лимита блоков. | [Официальный сайт / документация](https://llamalab.com/automate/) | [Google Play](https://play.google.com/store/apps/details?id=com.llamalab.automate) |
| **OpenTasker** | Современная local-first FOSS-альтернатива Tasker: profiles, contexts, tasks, flow control и растущий набор встроенных actions. Без аккаунта и cloud runtime, с явными permission/capability gates. | [GitHub](https://github.com/SysAdminDoc/OpenTasker) | [GitHub Releases](https://github.com/SysAdminDoc/OpenTasker/releases) |
| **Automation (Jens Schröder)** | Давно развивающийся open-source rule-based automation app с triggers/actions для времени, зарядки, USB, Wi-Fi, Bluetooth, приложений, NFC и других состояний устройства. Лёгкая FOSS-альтернатива коммерческим automation-suite. | [Исходники / официальный Gitea](https://git.server47.de/jens/Automation) | [F-Droid](https://f-droid.org/packages/com.jens.automation2/) · [Google Play](https://play.google.com/store/apps/details?id=com.jens.automation2) |
| **Easer** | GPLv3 автоматизация Android на базе events, conditions и operations с расширением через плагины. Архитектура зрелая, но проект развивается медленнее новых альтернатив. | [GitHub](https://github.com/renyuneyun/Easer) · [Сайт проекта](https://renyuneyun.github.io/Easer/) | [F-Droid](https://f-droid.org/packages/ryey.easer/) |
| **ShizukuAutoTask** | Open-source помощник для автоматизации, который умеет выполнять задачи через Shizuku/UiAutomation или AccessibilityService. Есть постоянные и одноразовые tasks, запись жестов и инспекция UI-tree. | [GitHub](https://github.com/ITAnt/ShizukuAutoTask) | [Ссылка на сборку проекта](https://fir.xcxwo.com/tasker) |
| **Termius** | Удобный кроссплатформенный SSH/Mosh/Telnet/SFTP-клиент для удалённых серверов: сохранённые хосты/ключи, port forwarding, встроенный SFTP, несколько терминальных вкладок и мобильный keyboard addon. Хороший SSH-first вариант, когда нужны серверные сессии без локального Linux-окружения на Android. | [Официальный сайт](https://termius.com/) · [Возможности Android](https://www.termius.com/free-ssh-client-for-android) | [Google Play](https://play.google.com/store/apps/details?id=com.server.auditor.ssh.client) · [Страница Android](https://termius.com/download/android) |
| **Termux** | Полноценный terminal + Linux package environment на Android. Полезен для SSH, скриптов, Git, Python, локальных сервисов и CLI-инструментов без отдельной Linux-системы. | [GitHub](https://github.com/termux/termux-app) | [F-Droid](https://f-droid.org/packages/com.termux/) · [GitHub Releases](https://github.com/termux/termux-app/releases) |
| **Termux Launcher (PickleHik3)** | Независимый terminal-first Android launcher/форк на базе Termux: нативные sessions/windows, рекурсивные split panes и floating panes, layouts, восстановление workspace, улучшенная работа touch/mouse с TUI, scrollback copy mode и keyboard-first shortcuts. Особенно интересен для планшета и desktop-like работы в терминале. **Экспериментальный личный проект:** автор прямо пишет, что проект vibe-coded, и просит security review. Edition `com.termux` заменяет официальный Termux; Nix и VAJ editions могут ставиться рядом. | [GitHub](https://github.com/PickleHik3/termux-launcher) · [Документация](https://picklehik3.github.io/termux-launcher-site/) | [GitHub Releases](https://github.com/PickleHik3/termux-launcher/releases) |
| **ZArchiver** | Мощный архиватор/файловая утилита с поддержкой 7z, ZIP, RAR и множества других форматов, включая создание, распаковку и просмотр архивов. | [Официальный сайт](https://zdevs.ru/ru/) | [Google Play](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver) |

> **Termius vs Termux Launcher:** Termius — прежде всего клиент для удалённых серверов; Termux Launcher даёт локальное Termux/Linux-окружение плюс нативные panes/layouts. Для чистого SSH-администрирования проще Termius; для локальных CLI-инструментов и desktop-like multi-pane терминала на Android интереснее Termux Launcher.

## Сеть, VPN, proxy и обход DPI

### Рекомендуемые варианты

- **⭐ v2RayTun** — рекомендуемый универсальный Android-клиент, если у вас уже есть своя proxy/VPN-подписка или конфигурация сервера. Поддерживает распространённые Xray/V2Ray-протоколы и импорт конфигов/подписок.
- **⭐ ByeByeDPI** — рекомендуемый локальный инструмент обхода DPI/фильтрации, когда проблема именно в блокировке со стороны провайдера, а не в необходимости удалённого VPN endpoint. **Это не удалённый VPN-сервис**, и сам по себе он не скрывает публичный IP.

> Android обычно разрешает только один активный туннель на базе `VpnService`. Поэтому многие клиенты ниже конкурируют за один и тот же Android VPN slot, даже если технически это proxy-клиенты, а не коммерческие VPN-сервисы. При комбинации инструментов проверяйте, может ли один из них работать в proxy mode вместо `VpnService`.

### Proxy, VPN и tunneling-клиенты

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **⭐ Рекомендуем — v2RayTun** | Кроссплатформенный proxy-клиент на Xray для импорта своих конфигов/подписок. Поддерживает современные V2Ray/Xray-протоколы; сам **не продаёт и не предоставляет VPN-серверы**. | [Официальный GitHub (roadmap/releases)](https://github.com/LXST-CODE/v2RayTun) · [Сайт разработчика](https://databridges.tech/) | [Google Play](https://play.google.com/store/apps/details?id=com.v2raytun.android) · [GitHub Releases](https://github.com/LXST-CODE/v2RayTun/releases) |
| **sing-box (SFA)** | Официальный Android-клиент универсальной proxy-платформы sing-box. Управляет локальными/удалёнными профилями и TUN через Android `VpnService`; хороший выбор для гибкой низкоуровневой multi-protocol настройки. | [Исходники Android](https://github.com/SagerNet/sing-box-for-android) · [core](https://github.com/SagerNet/sing-box) · [Docs](https://sing-box.sagernet.org/clients/android/) | [Google Play](https://play.google.com/store/apps/details?id=io.nekohasekai.sfa) · [F-Droid](https://f-droid.org/packages/io.nekohasekai.sfa/) · [GitHub Releases](https://github.com/SagerNet/sing-box/releases) |
| **V2rayGG** | V2RayNG-подобный клиент с фокусом на privacy, поддержкой VLESS, VMess, Shadowsocks и продвинутой маршрутизацией/профилями. Google Play называет приложение open source, но заявленная там ссылка на исходники сейчас недоступна (аудит 2026-10-01), поэтому случайный сторонний fork здесь не подставляется. | Заявленная в Google Play ссылка на source сейчас недоступна | [Google Play](https://play.google.com/store/apps/details?id=com.github.v2raygg) |
| **Shadowrocket for Android (Cross Ltd.)** | Android proxy/VPN-клиент со встроенными нодами и поддержкой VMess, VLESS, Trojan, Shadowsocks, Hysteria2, WireGuard, SOCKS/HTTP и subscription import. **Не путать с другим, оригинальным iOS-приложением Shadowrocket.** | Закрытые исходники; подтверждённого публичного source repo не найдено | [Google Play](https://play.google.com/store/apps/details?id=com.v2cross.proxy) |
| **Tailscale** | Open-source Android-клиент для identity-aware mesh/overlay сети на WireGuard. Отлично подходит для безопасного доступа к своим устройствам, homelab и приватным сетям; это не обычный V2Ray subscription-клиент. | [GitHub](https://github.com/tailscale/tailscale-android) · [Официальный сайт](https://tailscale.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.tailscale.ipn) · [официальные APK](https://pkgs.tailscale.com/stable/#android) |
| **V2BOX** | Multi-protocol proxy-клиент с VLESS/VMess, Shadowsocks, Trojan, SSH, Hysteria/Hysteria2, Reality и импортом подписок. Закрытый клиент HexaSoftware. | [Сайт разработчика](https://hexasoftware.dev/) | [Google Play](https://play.google.com/store/apps/details?id=dev.hexasoftware.v2box) |
| **V2Ray Client+ (V2ray VPN Client: Xray Vless)** | Лёгкий V2Ray/Xray-клиент с фокусом на VLESS Reality / XTLS RPRX Vision, импортом `vless://` и QR. Подходит, если нужен простой VLESS-клиент без огромного UI. | Закрытые исходники; подтверждённого публичного source repo не найдено | [Google Play](https://play.google.com/store/apps/details?id=com.v2ray.client) |
| **Happ — Proxy Utility** | Proxy-клиент на Xray-core с routing и поддержкой VLESS Reality, VMess, Trojan, Shadowsocks, SOCKS и Hysteria2. Проект сам серверы не предоставляет — нужен свой конфиг/подписка. | [GitHub](https://github.com/Happ-proxy/happ-android) · [Официальный сайт](https://happ.su/) | [Google Play](https://play.google.com/store/apps/details?id=com.happproxy) · [GitHub APK](https://github.com/Happ-proxy/happ-android/releases/latest) |
| **Hiddify** | Open-source мультиплатформенный клиент на sing-box: TUN mode, auto node selection, remote profiles и поддержка VLESS/VMess/Reality/Hysteria2/TUIC/SSH/WireGuard и популярных форматов подписок. | [GitHub](https://github.com/hiddify/hiddify-app) · [Официальный сайт](https://hiddify.com/) | [Google Play](https://play.google.com/store/apps/details?id=app.hiddify.com) · [GitHub Releases](https://github.com/hiddify/hiddify-app/releases/latest) |
| **Outline Client** | Open-source клиент для Outline Server, при этом **полностью совместим и с обычными Shadowsocks-серверами**. Хороший простой вариант для Shadowsocks-oriented схемы клиент/сервер. | [GitHub](https://github.com/OutlineFoundation/outline-apps) · [Официальный сайт](https://getoutline.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.outline.android.client) · [официальный прямой APK](https://developer.getoutline.org/download-links/) |

### Локальный обход DPI / блокировок

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **⭐ Рекомендуем — ByeByeDPI / ByeDPI for Android** | Локально запускает ByeDPI и перенаправляет трафик через него для обхода части DPI-фильтрации. Использует Android VPN interface для локального перенаправления, но **не является удалённым VPN-сервисом**: сам по себе не шифрует трафик и не скрывает публичный IP. Root не нужен, поддерживается split tunneling. | [Текущий проект](https://github.com/romanvht/ByeByeDPI) · [оригинальная реализация](https://github.com/dovecoteescapee/ByeDPIAndroid) · [Официальный сайт](https://byebyedpi.xyz/) | [GitHub Releases](https://github.com/romanvht/ByeByeDPI/releases/latest) |

### Диагностика VPN / proxy

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **RKNHardering** | Проверяет Android-устройство на признаки, по которым приложения могут обнаружить VPN/proxy: интерфейсы, маршруты, DNS, несовпадения публичного IP, локальные proxy, установленные VPN-приложения и другие сигналы. Полезен, чтобы понять, что другое приложение потенциально может узнать о вашем сетевом окружении. | [GitHub](https://github.com/xtclovver/RKNHardering) | [GitHub Releases](https://github.com/xtclovver/RKNHardering/releases/latest) · [F-Droid](https://f-droid.org/packages/com.notcvnt.rknhardering/) |

> RKNHardering — это **диагностический инструмент**, а не VPN и не гарантия того, что конфигурация «не детектируется». Проект отдельно маркирует подтверждённые проверки и сведения из сообщества/исследований, поэтому не стоит воспринимать каждый сигнал как безусловный факт без чтения upstream-документации.

## Android Auto и автомобильные head units

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Fermata Auto / Fermata Media Player** | Open-source медиаплеер с аудио, видео, IPTV, плейлистами и поддержкой Android Auto. Полезен, если возможностей штатных Android Auto media apps недостаточно. | [GitHub](https://github.com/AndreyPavlenko/Fermata) | [GitHub Releases](https://github.com/AndreyPavlenko/Fermata/releases/latest) |
| **Headunit Reloaded (HUR)** | Превращает Android-планшет или магнитолу в **Android Auto receiver/emulator**. Полезен для DIY head unit и планшета в автомобиле. Актуальное поведение USB/беспроводного подключения зависит от версии Android Auto и конкретного устройства — проверяйте текущие release notes в Google Play. | [Исторические GPL-исходники](https://github.com/borconi/headunit) *(legacy-код; не стоит считать его исходниками текущей Play-сборки)* · [официальная support-тема](https://forum.xda-developers.com/t/android-4-1-headunit-reloaded-for-android-auto-with-wifi.3432348/) | [Google Play](https://play.google.com/store/apps/details?id=gb.xxy.hr) |
| **KingInstaller** | Устанавливает APK с installer metadata так, чтобы Android/Android Auto мог воспринимать их как установленные из Play Store. В актуальных версиях есть classic, Shizuku и root-assisted методы. Совместимость зависит от ROM и версии Android Auto. | [GitHub](https://github.com/fcaronte/KingInstaller) | [GitHub Releases](https://github.com/fcaronte/KingInstaller/releases) |
| **AAStore (Android Auto Store)** | Каталог/установщик сторонних Android Auto-приложений. Оригинальный публичный GitHub-проект прямо помечен как **deprecated**, а совместимость с современными Android Auto постоянно меняется. Считайте его legacy-вариантом и проверяйте актуальную совместимость перед использованием. | [Legacy GitHub](https://github.com/croccio/Android-Auto-Store) | [Legacy GitHub Releases](https://github.com/croccio/Android-Auto-Store/releases) |
| **CarTube** | Community-проект YouTube для Android Auto без root. Публичный проект помечен как alpha и сильно зависит от версии Android Auto. **Видео используйте только когда автомобиль безопасно припаркован.** | [GitHub](https://github.com/Raperowy/CarTube) | [Репозиторий проекта](https://github.com/Raperowy/CarTube) |

### Примечание по Fermata Auto

Поведение sideloaded/нестандартных приложений в Android Auto **зависит от версии**. В релизах и issue-трекере Fermata регулярно фиксируются изменения совместимости по мере обновлений Android Auto, поэтому перед установкой проверяйте актуальные release notes/issues и не рассчитывайте, что Fermata Auto или Fermata Mirror автоматически появятся и заработают на любой версии Android Auto.

## Медиа, звук и стриминг

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **YouTube ReVanced / ReVanced Manager** | Open-source платформа для патчинга Android-приложений. Чаще всего используется для сборки кастомизированного YouTube-клиента с нужными патчами. Лучше использовать официальный Manager и патчить совместимый APK самостоятельно, а не скачивать случайные pre-patched APK. | [GitHub](https://github.com/ReVanced/revanced-manager) · [Официальный сайт](https://revanced.app/) | [Официальная загрузка](https://revanced.app/download) · [GitHub Releases](https://github.com/ReVanced/revanced-manager/releases/latest) |
| **ReVanced GmsCore** | Форк microG от ReVanced для **non-root пропатченных Google-приложений**. Он рассчитан на работу рядом с обычными Google Play Services и нужен именно тогда, когда ReVanced-патч явно требует “GmsCore support”. | [GitHub](https://github.com/ReVanced/GmsCore) | [GitHub Releases](https://github.com/ReVanced/GmsCore/releases/latest) |
| **microG Services (upstream)** | Свободная open-source замена реализации Google Play Services API — в первую очередь для ROM/устройств, где обычные Google Play Services отсутствуют или намеренно не используются. **Это не то же самое, что ReVanced GmsCore.** | [GitHub](https://github.com/microg/GmsCore) · [Официальный сайт](https://microg.org/) | [Официальная инструкция загрузки](https://github.com/microg/GmsCore/wiki/Downloads) · [GitHub Releases](https://github.com/microg/GmsCore/releases/latest) |
| **AirMusic Pro** | Полная платная версия AirMusic. Передаёт звук почти из любого Android-приложения на AirPlay/AirPlay 2, Sonos, Chromecast, DLNA, HEOS, Roku, Fire TV и другие receivers по локальной сети. Это **разовая покупка**, без отдельного аккаунта AirMusic и без подписки. Само Android-приложение не публикуется как open source; отдельно есть официальный Magisk-модуль для опционального root-захвата аудио. | [Официальный сайт](https://www.airmusic.app/) · [официальный Magisk-модуль](https://github.com/Magisk-Modules-Repo/airmusic) | [Google Play — Pro](https://play.google.com/store/apps/details?id=app.airmusic.pro) |
| **AirMusic Trial** | Бесплатная trial-версия, чтобы **до покупки Pro** проверить совместимость AirMusic с конкретным телефоном, приложениями и колонками/ресиверами. По назначению это тот же стриминг, но после 10 минут воспроизведения в звук добавляются тестовые сигналы; после перезапуска AirMusic начинается новый 10-минутный тестовый период. | [Официальный сайт](https://www.airmusic.app/) | [Google Play — Trial](https://play.google.com/store/apps/details?id=app.airmusic.trial) |
| **AudioRelay** | Передаёт звук ПК на Android, позволяет использовать Android-телефон как микрофон для ПК или отправлять Android-аудио на другое устройство. Работает по Wi-Fi и USB и удобен для самодельной low-latency аудиомаршрутизации. | [Официальный сайт](https://audiorelay.net/) | [Google Play](https://play.google.com/store/apps/details?id=com.azefsw.audioconnect) · [Desktop downloads](https://audiorelay.net/downloads) |

## NFC и RFID

Используйте инструменты чтения/записи RFID/NFC только с картами, метками и системами, которыми вы владеете либо которые вам явно разрешено тестировать.

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **MIFARE Classic Tool (MCT)** | Низкоуровневая Android NFC-утилита для чтения, записи, анализа, ключей и дампов **MIFARE Classic** меток. Очень полезна для исследования совместимых карт и тегов. | [GitHub](https://github.com/ikarus23/MifareClassicTool) | [Google Play](https://play.google.com/store/apps/details?id=de.syss.MifareClassicTool) · [F-Droid](https://f-droid.org/packages/de.syss.MifareClassicTool/) · [официальный APK](https://www.icaria.de/mct/releases/) |
| **RFID Tools (RRG)** | Android frontend/toolkit для внешнего RFID/NFC-железа, включая Proxmark3 RDV4, ACR122U, Chameleon Mini и устройства класса PN532. | [GitHub](https://github.com/RfidResearchGroup/RFIDtools) | [Google Play](https://play.google.com/store/apps/details?id=com.rfidresearchgroup.rfidtools) · [GitHub Releases](https://github.com/RfidResearchGroup/RFIDtools/releases) |
| **NFC Tools** | Удобный general-purpose NFC reader/writer для NDEF-тегов и обычных tag workflows. Лучше подходит для повседневных NFC-меток, чем для low-level MIFARE-исследований. | [Официальный сайт](https://www.wakdev.com/en/apps.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc) |
| **NFC Tools Pro** | Платная редакция NFC Tools с тем же простым read/write workflow и расширенным набором возможностей Wakdev. Полезна, если бесплатная версия уже подходит и нужен Pro-набор. | [Официальный сайт](https://www.wakdev.com/en/apps.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.nfctools.pro) |
| **NFC TagWriter by NXP** | Официальное приложение NXP для записи NDEF-данных: контактов, URL/закладок, текста, Wi-Fi/Bluetooth handover и других записей на NFC-теги. | [Официальная страница NXP](https://www.nxp.com/design/design-center/software/rfid-developer-resources/nfc-tagwriter-app-by-nxp%3ANFC-TAGWRITER) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.nfc.tagwriter) |
| **NFC TagInfo by NXP** | Диагностическая утилита NXP для определения технологии NFC/RFID-тега и просмотра поддерживаемой информации. Хороший первый шаг, когда тип тега ещё неизвестен. | [NXP Apps](https://www.nxp.com/pages/nxp-applications%3ANXP-APPS) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.taginfolite) |
| **MIFARE Ultralight Tool** | Специализированный reader/writer/scanner для MIFARE Ultralight и распространённых NTAG-вариантов. | [MTools Tec](https://shop.mtoolstec.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.mtoolstec.mifareultralighttool) |
| **Chameleon Ultra GUI (CU GUI)** | Open-source кроссплатформенный контроллер Chameleon Ultra/Lite по USB-OTG или BLE: firmware update, чтение/запись карт, saved cards/dictionaries и recovery ключей. | [GitHub](https://github.com/GameTec-live/ChameleonUltraGUI) · [Docs](https://gametec-live.com/ChameleonUltraGUI/) | [Google Play](https://play.google.com/store/apps/details?id=io.chameleon.ultra) · [GitHub Releases](https://github.com/GameTec-live/ChameleonUltraGUI/releases) |
| **PCR532** | Инструменты для работы с железом PCR532/PN532. Текущая страница PCR532 у MTools Tec рекомендует MTools, MTools BLE и RFID Tools; отдельно существует более новый независимый open-source Android-клиент/rewrite для PCR532 Pro/совместимого PN532. | [Страница PCR532](https://shop.mtoolstec.com/product/pcr532) · [community Android client](https://github.com/touzi/PCR532) | [Community project](https://github.com/touzi/PCR532) |
| **MTools** | NFC/RFID-утилита для чтения, записи и анализа MIFARE Classic/Ultralight через NFC телефона либо внешние ACR122U/PN532-class readers. | [MTools Tec](https://shop.mtoolstec.com/) | [Google Play](https://play.google.com/store/apps/details?id=tk.toolkeys.mtools) |
| **MTools BLE** | All-in-one BLE/external-reader приложение для PN532 BLE, PCR532, Chameleon Ultra/Lite и похожего железа: MIFARE/DESFire/APDU, dumps/keys и firmware tools. | [MTools docs](https://docs.mtoolstec.com/help-and-info-mtools-lite) | [Google Play](https://play.google.com/store/apps/details?id=com.mtoolstec.mtoolsLite) |

> Возможности зависят от NFC-контроллера и прошивки телефона. Например, не каждый смартфон способен выполнять все операции с MIFARE Classic, даже если приложение само их поддерживает.

## Игры и бесплатные альтернативы

| Инструмент | Для чего нужен | Исходники / официальный сайт | Установка |
| --- | --- | --- | --- |
| **Lichess** | Полностью бесплатная/libre open-source шахматная платформа: онлайн-игры, puzzles, анализ, studies, турниры и Stockfish. Сильная альтернатива без подписки для тех, кому не нужна платная экосистема Chess.com. | [GitHub](https://github.com/lichess-org/mobile) · [Официальный сайт](https://lichess.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.lichess.mobileV2) |

## Полезные сообщества и базы знаний

Для скачивания и security-sensitive настроек в первую очередь лучше использовать официальную документацию проекта, но многие Android edge cases гораздо лучше разобраны сообществом.

- **[4PDA](https://4pda.to/forum/)** — особенно полезен для русскоязычных device-specific тем, нюансов прошивок, Android Auto/магнитол, root/Shizuku, сетевых инструментов и редких Android-утилит.
- **[XDA Forums](https://xdaforums.com/)** — один из сильнейших англоязычных источников по конкретным устройствам/ROM, bootloader/root, Android Auto, ADB, системным твикам и troubleshooting.

Хороший шаблон поиска: **точное название приложения/инструмента + модель устройства + версия Android/прошивки + симптом**.

> Вложения на форумах, модифицированные APK и старые инструкции считайте недоверенными, пока не проверили их. Для установки предпочитайте upstream GitHub/официальные релизы, а 4PDA/XDA используйте в первую очередь для поиска device-specific фиксов, compatibility notes и troubleshooting.

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

## Лицензия

Оригинальные тексты, документация, структура и авторская подборка этого репозитория распространяются по лицензии **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**.

Материалы можно копировать, распространять, переводить, перерабатывать и использовать в производных работах для **некоммерческих** целей при сохранении корректной атрибуции и указании внесённых изменений. Практичный формат атрибуции:

> Android Power User Toolkit by **lgg** — https://github.com/lgg/android-power-user-toolkit — CC BY-NC 4.0

Названия сторонних приложений, товарные знаки, логотипы, скриншоты, исходный код по внешним ссылкам и другие сторонние материалы остаются под лицензиями и правами их владельцев.

Подробнее: [LICENSE](LICENSE).

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

---
title: Жизненный цикл поддержки PowerShell Core
description: Политики, распространяемые на поддержку PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: 8cf8a0ac6140d28e55b065bf711763ba1c681d63
ms.sourcegitcommit: 0a3f9945d52e963e9cba2538ffb33e42156e1395
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "77706263"
---
# <a name="powershell-core-support-lifecycle"></a>Жизненный цикл поддержки PowerShell Core

PowerShell Core — это отдельный набор средств и компонентов, поставляемых, устанавливаемых и настраиваемых отдельно от Windows PowerShell. Поэтому на PowerShell Core не распространяются лицензионные соглашения Windows 7, 8.1, 10 или Windows Server.

Однако PowerShell Core поддерживается в рамках традиционных соглашений о поддержке корпорации Майкрософт, включая [Premier][], [соглашения Microsoft Enterprise][enterprise-agreement] и [Microsoft Software Assurance][assurance].
Вы также можете оплатить [техническую поддержку][] по PowerShell Core, направив в службу поддержки запрос о своей проблеме.

## <a name="community-support"></a>Поддержка сообщества

Мы также предлагаем [поддержку сообщества][] на GitHub, где вы можете зарегистрировать вопрос, ошибку или запрос функции.
Вы также можете получить помощь от других членов [технического сообщества Microsoft PowerShell][] или на любом из форумов, перечисленных в разделе "Ресурсы сообщества" на странице центра документации по [PowerShell][pshub]. Но мы не можем гарантировать, что там вам оперативно помогут решить вашу проблему. Если ваша проблема требует немедленного вмешательства, следует использовать традиционные платные варианты поддержки.

## <a name="lifecycle-of-powershell-core"></a>Жизненный цикл PowerShell Core

В PowerShell Core внедряется [политика современного жизненного цикла Майкрософт][modern]. Этот жизненный цикл поддержки предназначен для предоставления клиентам актуальных версий.

Ветвь PowerShell Core версии 6.x будет обновляться примерно каждые шесть месяцев: 6.0, 6.1, 6.2 и т. д.

> [!IMPORTANT]
> Чтобы продолжить получать поддержку, вам нужно обновить продукт в течение шести месяцев после выпуска версии с новым дополнительным номером.

Например, если версия PowerShell Core 6.1 выпущена 1 июля 2018 г., чтобы продолжать получать поддержку, вам нужно выполнить обновление до версии PowerShell Core 6.1 к 1 января 2019 г.

> [!IMPORTANT]
> Кроме того, вам нужно обновлять продукт в течение 30 дней после выпуска версии с новым исправлением.

Например, если вы используете PowerShell Core 6.1, а версия 6.1.3 выпущена 19 февраля 2019 г., вам нужно выполнить обновление до версии PowerShell Core 6.1.3 в течение 30 дней, т. е. до 21 марта 2019 г. Если требуется какие-либо исправления, они будут включены в наше следующе накопительное обновление.

Согласно политике современного жизненного цикла также требуется, чтобы корпорация Майкрософт предоставляла клиентам уведомление за 12 месяцев до прекращения поддержки продукта (например, PowerShell Core).

Со временем мы планируем реализовать для PowerShell Core возможность долгосрочного обслуживания. Это позволит нам осуществлять обслуживание и выпускать обновления для системы безопасности, чтобы обеспечить поддержку определенной ветви или версии 6.x.

## <a name="supported-platforms"></a>Поддерживаемые платформы

Чтобы проверить, поддерживаются ли официально ваша платформа и версия PowerShell Core, см. таблицу ниже.

Наше сообщество также предоставило пакеты для некоторых платформ, но они не поддерживаются официально. Эти пакеты, отмечены как `Community` в таблице.

Отмеченные как `Experimental` (экспериментальные) платформы официально не поддерживаются, но они доступны для экспериментов с возможностью обратной связи.

| Платформа                                          |      6.2      |    7.0    |
| ------------------------------------------------- | :-----------: | :-------: |
| Windows 8.1 и 10                               |   Поддерживается   | Поддерживается |
| Windows Server 2012 R2 и 2016                      |   Поддерживается   | Поддерживается |
| [Windows Server Semi-Annual Channel][semi-annual] |   Поддерживается   | Поддерживается |
| Ubuntu 16.04 и 18.04.                            |   Поддерживается   | Поддерживается |
| Ubuntu 19.10 (через Snap-пакет)                   |   Сообщество   | Сообщество |
| Ubuntu 20.04 (через Snap-пакет)                   |   Сообщество   | Сообщество |
| Debian 9                                          |   Поддерживается   | Поддерживается |
| Debian 10                                         | Не поддерживается | Поддерживается |
| CentOS 7                                          |   Поддерживается   | Поддерживается |
| CentOS 8                                          | Не поддерживается | Поддерживается |
| Red Hat Enterprise Linux 7                        |   Поддерживается   | Поддерживается |
| Red Hat Enterprise Linux 8                        | Не поддерживается | Поддерживается |
| Fedora 30                                         | Не поддерживается | Поддерживается |
| Alpine 3.8                                        |   См. примечание    | См. примечание  |
| Alpine 3.9 и 3.10                               | Не поддерживается | См. примечание  |
| macOS 10.12+                                      |   Поддерживается   | Поддерживается |
| Arch                                              |   Сообщество   | Сообщество |
| Raspbian                                          |   Сообщество   | Сообщество |
| Kali                                              |   Сообщество   | Сообщество |
| AppImage (работает на нескольких платформах Linux)      |   Сообщество   | Сообщество |
| [Snap-пакет](https://snapcraft.io/powershell)   |   См. примечание    | См. примечание  |

> [!NOTE]
> Snap-пакеты поддерживаются так же, как и соответствующий дистрибутив.

> [!NOTE]
> CIM, удаленное взаимодействие PowerShell и DSC не поддерживаются в Alpine.

## <a name="powershell-releases-end-of-life"></a>Прекращение поддержки выпусков PowerShell

В следующей таблице перечислены даты прекращения поддержки разных выпусков PowerShell Core с учетом [жизненного цикла этого продукта](#lifecycle-of-powershell-core).

| Версия | Дата прекращения поддержки                   |
|---------|-------------------------------|
| 6,0     | 13 февраля 2019 г.             |
| 6.1     | 28 сентября 2019 г.            |
| 6.2     | 6 месяцев после выпуска версии 7     |

## <a name="unsupported-platforms"></a>Неподдерживаемые платформы

По завершении жизненного цикла определенной версии платформы (определяется ее владельцем), прекращается ее поддержка в PowerShell Core. Предыдущие выпуски пакетов останутся доступными для клиентов, которым требуется доступ, но официальная поддержка и обновления больше не будет предоставляться.

Таким образом, поддержка следующих версий прекращается владельцами дистрибутивов.

| Платформа       | Версия | Завершение срока службы                                                                                                                        |
| -------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Debian         | 8       | [Июнь 2018 г.](https://lists.debian.org/debian-security-announce/2018/msg00132.html)                                                  |
| Fedora         | 24      | [Август 2017 г.](https://fedoramagazine.org/fedora-24-eol/)                                                                           |
| Fedora         | 25      | [Декабрь 2017 г.](https://fedoramagazine.org/fedora-25-end-life/)                                                                    |
| Fedora         | 26      | [Май 2018 г.](https://fedoramagazine.org/fedora-26-end-life/)                                                                         |
| Fedora         | 27      | [Ноябрь 2018 г.](https://fedoramagazine.org/fedora-27-end-of-life/)                                                                 |
| Fedora         | 28      | [Май 2019 г.](https://fedoramagazine.org/fedora-28-end-of-life/)                                                                      |
| openSUSE       | 42.1    | [Май 2017 г.](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)                                            |
| openSUSE       | 42.2    | [Январь 2018 г.](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html)                                        |
| openSUSE       | 42.3    | [Июль 2019 г.](https://lists.opensuse.org/opensuse-security-announce/2019-07/msg00000.html)                                           |
| Ubuntu         | 14.04   | [Апрель 2019 г.](https://wiki.ubuntu.com/Releases)                                                                                     |
| Ubuntu         | 16.10   | [Июль 2017 г.](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)                                               |
| Ubuntu         | 17.04   | [Январь 2018 г.](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)                                                 |
| Ubuntu         | 17.10   | [Июль 2018 г.](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)                                               |
| Windows        | 7       | [Январь 2020 г.](https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020)                        |
| Windows Server | 2008 R2 | [Январь 2020 г.](https://support.microsoft.com/en-us/help/4456235/end-of-support-for-windows-server-2008-and-windows-server-2008-r2) |

## <a name="notes-on-licensing"></a>Замечания по лицензированию

PowerShell Core выпускается по [Лицензия MIT][]. По этой лицензии и без соглашения о платной подписке пользователям предоставляется только [поддержку сообщества][]. В рамках поддержки сообщества корпорация Майкрософт не предоставляет никаких гарантий оперативного реагирования или выпуска исправлений.

## <a name="windows-powershell-module"></a>Модуль Windows PowerShell

Поддержка PowerShell Core не распространяется на другие модули продукта, если только они не поддерживают PowerShell Core явным образом. Например, использование модуля `ActiveDirectory`, который поставляется в составе Windows Server, является неподдерживаемым сценарием.

Однако в некоторых случаях модули, которые не поддерживают PowerShell Core явным образом, могут быть совместимы. Установив модуль [WindowsPSModulePath][], можно добавить `PSModulePath` Windows PowerShell в `PSModulePath` PowerShell Core.

Сначала установите модуль **WindowsPSModulePath** из коллекции PowerShell:

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

После установки модуля запустите командлет `Add-WindowsPSModulePath`, чтобы добавить `PSModulePath` Windows PowerShell в PowerShell Core:

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a>Экспериментальные функции

Для [Экспериментальные функции][] предоставляется только [поддержка сообщества](#community-support).

## <a name="release-history"></a>История выпусков

В следующей таблице содержится временная шкала основных выпусков PowerShell. Эта таблица предоставляется для хронологической справки. Не используйте ее для определения жизненного цикла поддержки.

|       Версия        | Дата выпуска |                                                                     Примечание                                                                      |
| -------------------- | :----------: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| PowerShell 7.0 (LTS) |   Март 2020 г.   | На основе .NET Core 3.1 (LTS)                                                                                                                  |
| PowerShell 6.0       |   Январь 2018 г.   | Первый выпуск, на основе .NET Core 2.1. Устанавливается в Windows, Linux и macOS.                                                              |
| PowerShell 5.1       |   Август 2016 г.   | Выпущено в юбилейном обновлении Windows 10 и Windows Server 2016.                                                                             |
| PowerShell 5.0       |   Февраль 2016 г.   | Выпущено в Windows Management Framework (WMF) 5.0                                                                                            |
| PowerShell 4.0       |   Октябрь 2013 г.   | Интегрировано в Windows 8.1 и Windows Server 2012 R2. Устанавливается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows Server 2012. |
| PowerShell 3.0       |   Октябрь 2012 г.   | Интегрировано в Windows 8 и Windows Server 2012. Устанавливается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 SP1 с пакетом обновления 1 (R2) и Windows Server 2008 R2.  |
| PowerShell 2.0       |   Июль 2009 г.   | Интегрировано в Windows 7 и Windows Server 2008 R2. Устанавливается в Windows XP с пакетом обновления 3 (SP3), Windows Server 2003 с пакетом обновления 2 (SP2) и Windows Vista с пакетом обновления 1 (SP1).            |
| PowerShell 1.0       |   Ноябрь 2006 г.   | Устанавливается в Windows XP с пакетом обновления 2 (SP2), Windows Server 2003 с пакетом обновления 1 (SP1) и Windows Vista. Необязательный компонент Windows Server 2008.                          |

<!-- hyperlink references -->
[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[поддержку сообщества]: https://github.com/powershell/powershell/issues
[pshub]: https://docs.microsoft.com/powershell
[технического сообщества Microsoft PowerShell]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[техническую поддержку]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[Лицензия MIT]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[WindowsPSModulePath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Экспериментальные функции]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures

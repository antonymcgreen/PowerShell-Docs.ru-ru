---
description: Windows PowerShell создает журнал событий Windows с именем "Windows PowerShell" для записи событий Windows PowerShell. Этот журнал можно просмотреть в Просмотр событий или с помощью командлетов, получающих события, например `Get-EventLog` командлет. По умолчанию обработчики и события поставщика Windows PowerShell записываются в журнал событий, но можно использовать переменные предпочтений журнала событий для настройки журнала событий. Например, можно добавить события о командах Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232418"
---
# <a name="about-eventlogs"></a>О журналах событий

## <a name="short-description"></a>Краткое описание

Windows PowerShell создает журнал событий Windows с именем "Windows PowerShell" для записи событий Windows PowerShell. Этот журнал можно просмотреть в Просмотр событий или с помощью командлетов, получающих события, например `Get-EventLog` командлет. По умолчанию обработчики и события поставщика Windows PowerShell записываются в журнал событий, но можно использовать переменные предпочтений журнала событий для настройки журнала событий. Например, можно добавить события о командах Windows PowerShell.

## <a name="long-description"></a>Полное описание

В журнале событий Windows PowerShell записываются сведения об операциях Windows PowerShell, таких как запуск и остановка ядра программы, а также запуск и остановка поставщиков Windows PowerShell. Можно также заносить в журнал сведения о командах Windows PowerShell.

Журнал событий Windows PowerShell находится в группе Журналы приложений и служб. Журнал Windows PowerShell — это классический журнал событий, который не использует технологию событий Windows. Чтобы просмотреть журнал, используйте командлеты, предназначенные для классических журналов событий, например `Get-EventLog` .

## <a name="viewing-the-windows-powershell-event-log"></a>Просмотр журнала событий Windows PowerShell

Журнал событий Windows PowerShell можно просмотреть в Просмотр событий или с помощью `Get-EventLog` `Get-WmiObject` командлетов и. Чтобы просмотреть содержимое журнала Windows PowerShell, введите:

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

Чтобы проверить события и их свойства, используйте `Sort-Object` командлет, `Group-Object` командлет и командлеты, которые содержат `Format` команду ( `Format` командлеты).

Например, чтобы просмотреть события в журнале, сгруппированные по ИДЕНТИФИКАТОРу события, введите:

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

Или введите:

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

Чтобы просмотреть все классические журналы событий, введите:

```powershell
Get-EventLog -List
```

Кроме того, с помощью `Get-WmiObject` командлета можно использовать классы инструментарий управления Windows (WMI) (WMI), связанные с событиями, для просмотра журнала событий. Например, чтобы просмотреть все свойства файла журнала событий, введите:

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

Чтобы найти классы WMI, связанные с событиями Win32, введите:

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

Для получения дополнительных сведений введите «Get-Help Get-EventLog» и «Get-Help Get-WmiObject».

## <a name="selecting-events-for-the-windows-powershell-event-log"></a>Выбор событий для журнала событий Windows PowerShell

Можно использовать переменные предпочтений журнала событий, чтобы определить, какие события записываются в журнал событий Windows PowerShell.

Существует шесть переменных предпочтений журнала событий. две переменные для каждого из трех компонентов ведения журнала: ядро (программа Windows PowerShell), поставщики и команды. Переменные Лифецикливент зарегистрируют нормальные события запуска и остановки. Переменные работоспособности регистрируют события ошибок.

В следующей таблице перечислены переменные предпочтений журнала событий.

|Переменная                  |Описание                                    |
|--------------------------|-----------------------------------------------|
|$LogEngineLifeCycleEvent  |Заносит в журнал начало и конец PowerShell          |
|$LogEngineHealthEvent     |Журналы ошибок программы PowerShell                 |
|$LogProviderLifeCycleEvent|Записывает в журнал начало и конец поставщиков PowerShell|
|$LogProviderHealthEvent   |Регистрирует ошибки поставщика PowerShell                |
|$LogCommandLifeCycleEvent |Записывает в журнал запуск и завершение команд   |
|$LogCommandHealthEvent    |Регистрирует ошибки команды                            |

(Дополнительные сведения о поставщиках Windows PowerShell см. в разделе [about_Providers](about_Providers.md).)

По умолчанию включены только следующие типы событий:

* $LogEngineLifeCycleEvent
* $LogEngineHealthEvent
* $LogProviderLifeCycleEvent
* $LogProviderHealthEvent

Чтобы включить тип событий, задайте для него переменную предпочтение $true. Например, чтобы включить события жизненного цикла команды, введите:

```powershell
$LogCommandLifeCycleEvent
```

Или введите:

```powershell
$LogCommandLifeCycleEvent = $true
```

Чтобы отключить тип события, задайте для него переменную предпочтение $false. Например, чтобы отключить события жизненного цикла команды, введите:

```powershell
$LogProviderLifeCycleEvent = $false
```

Можно отключить любое событие, за исключением событий, указывающих на то, что ядро Windows PowerShell и основные поставщики запущены. Эти события создаются до запуска профилей Windows PowerShell и перед тем, как программа размещения готова принять команды.

Параметры переменных применяются только к текущему сеансу Windows PowerShell.
Чтобы применить их ко всем сеансам Windows PowerShell, добавьте их в профиль Windows PowerShell.

## <a name="logging-module-events"></a>События модуля ведения журнала

Начиная с Windows PowerShell 3,0, вы можете записывать события выполнения командлетов и функций в модулях и оснастках Windows PowerShell, установив для свойства LogPipelineExecutionDetails модулей и оснасток значение TRUE. В Windows PowerShell 2,0 эта функция доступна только для оснасток.

Если значение свойства LogPipelineExecutionDetails равно TRUE ( `$true` ), Windows PowerShell записывает события командлета и выполнения функции в сеансе в журнал Windows PowerShell в Просмотр событий. Параметр действует только в текущем сеансе.

Чтобы включить ведение журнала событий выполнения командлетов и функций в модуле, используйте следующую последовательность команд.

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

Чтобы включить ведение журнала событий выполнения командлетов в оснастке, используйте следующую последовательность команд.

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

Чтобы отключить ведение журнала, используйте ту же последовательность команд, чтобы задать для свойства значение FALSE ( `$false` ).

Можно также использовать параметр групповая политика "включить ведение журнала модуля", чтобы включить и отключить ведение журнала модуля и оснастки. Значение политики включает список имен модулей и оснасток. Поддерживаются подстановочные знаки.

Если параметр "включить ведение журнала модуля" установлен для модуля, значение свойства LogPipelineExecutionDetails модуля равно TRUE во всех сеансах, и его нельзя изменить.

Параметр групповой политики включить ведение журнала модуля находится в следующих групповая политика путях:

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

Политика конфигурации пользователя имеет приоритет над политикой конфигурации компьютера, и обе политики имеют предпочтение по отношению к значению свойства LogPipelineExecutionDetails модулей и оснасток.

Дополнительные сведения об этом параметре групповая политика см. в разделе [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="security-and-auditing"></a>Безопасность и аудит

Журнал событий Windows PowerShell предназначен для указания активности и предоставления оперативных сведений для устранения неполадок.

Однако, подобно большинству журналов событий приложений на базе Windows, журнал событий Windows PowerShell не обеспечивает безопасность. Его не следует использовать для аудита безопасности или записи конфиденциальных или собственных сведений.

Журналы событий предназначены для чтения и понимания пользователями. Пользователи могут выполнять чтение и запись в журнал. Пользователь-злоумышленник может прочитать журнал событий на локальном или удаленном компьютере, записать ложные данные, а затем предотвратить ведение журнала действий.

## <a name="notes"></a>Примечания

Авторы модулей могут добавлять функции ведения журнала в свои модули. Дополнительные сведения см. [в разделе Написание модуля Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="see-also"></a>См. также:

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Preference_Variables](about_Preference_Variables.md)

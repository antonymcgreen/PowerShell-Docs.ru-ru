---
description: Описывает, как задать пользовательские значения по умолчанию для параметров командлета и дополнительных функций.
keywords: powershell,командлет
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 0e19241549b53bac9a57de183f2896985f94d116
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231366"
---
# <a name="about-parameters-default-values"></a>О параметрах значения по умолчанию

## <a name="short-description"></a>Краткое описание

Описывает, как задать пользовательские значения по умолчанию для параметров командлета и дополнительных функций.

## <a name="long-description"></a>Подробное описание

`$PSDefaultParameterValues`Переменная предпочтения позволяет указать пользовательские значения по умолчанию для любого командлета или расширенной функции. Командлеты и дополнительные функции используют пользовательское значение по умолчанию, если в команде не указано другое значение.

Авторы командлетов и дополнительных функций устанавливают стандартные значения по умолчанию для их параметров. Как правило, стандартные значения по умолчанию полезны, но они могут быть не подходящими для всех сред.

Эта функция особенно полезна, если необходимо указать одно и то же альтернативное значение параметра практически при каждом использовании команды или если определенное значение параметра трудно запомнить, например имя сервера электронной почты или GUID проекта.

Если требуемое значение по умолчанию зависит от прогнозируемого значения, можно указать блок скрипта, который предоставляет различные значения по умолчанию для параметра в различных условиях.

`$PSDefaultParameterValues` впервые появился в PowerShell 3,0.

## <a name="syntax"></a>Синтаксис

`$PSDefaultParameterValues`Переменная является хэш-таблицей, которая проверяет формат ключей как тип объекта **System. Management. Automation. дефаултпараметердиктионари** . Хэш-таблица содержит пары " **ключ-значение** ". **Ключ** имеет формат `CmdletName:ParameterName` . **Значением является значение** **DefaultValue** или **ScriptBlock** , назначенное ключу.

Синтаксис `$PSDefaultParameterValues` переменной предпочтения выглядит следующим образом:

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

В значениях **CmdletName** и **ParameterName** разрешены подстановочные знаки.

Чтобы задать, изменить, добавить или удалить определенную пару " **ключ-значение** " из `$PSDefaultParameterValues` , используйте методы для изменения стандартной хэш-таблицы. Например, методы **Add** и **Remove** . Эти методы не перезаписывают другие значения в хэш-таблице.

Существует другой синтаксис, который не перезаписывает существующую `$PSDefaultParameterValues` хэш-таблицу. Чтобы добавить или изменить определенную пару " **ключ-значение** ", используйте следующий синтаксис:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

**CmdletName** должен быть именем командлета или именем расширенной функции, использующей атрибут **CmdletBinding** . Нельзя использовать `$PSDefaultParameterValues` для указания значений по умолчанию для скриптов или простых функций.

**DefaultValue** может быть объектом или блоком скрипта. Если значение является блоком сценария, PowerShell вычисляет блок скрипта и использует результат в качестве значения параметра. Если указанный параметр принимает значение блока сценария, заключите значение блока скрипта во второй набор фигурных скобок, например:

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

Дополнительные сведения см. в следующих документах:

- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Preference_Variables](about_Preference_Variables.md)

## <a name="examples"></a>Примеры

### <a name="how-to-set-psdefaultparametervalues"></a>Как задать \$ псдефаултпараметервалуес

`$PSDefaultParameterValues` — это переменная предпочтения, которая существует только в сеансе, в котором она задана. У него нет значения по умолчанию.

Чтобы задать `$PSDefaultParameterValues` , введите имя переменной и одну или несколько пар " **ключ-значение** ". При выполнении другой `$PSDefaultParameterValues` команды она перезаписывает существующую хэш-таблицу.

Примеры изменения пар " **ключ-значение** " без перезаписи значений существующих хэш-таблиц см. в разделе [Добавление значений в \$ псдефаултпараметервалуес](#how-to-add-values-to-psdefaultparametervalues) или [изменение значений в \$ псдефаултпараметервалуес](#how-to-change-values-in-psdefaultparametervalues).

Чтобы сохранить `$PSDefaultParameterValues` данные для будущих сеансов, добавьте `$PSDefaultParameterValues` команду в профиль PowerShell. Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).

#### <a name="set-a-custom-default-value"></a>Задать пользовательское значение по умолчанию

Пара " **ключ-значение** " задает `Send-MailMessage:SmtpServer` для ключа пользовательское значение по умолчанию **Server123** .

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a>Установка значений по умолчанию для нескольких параметров

Чтобы задать значения по умолчанию для нескольких параметров, разделите каждую пару « **ключ-значение** » точкой с запятой ( `;` ). `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` Для ключей и задаются пользовательские значения по умолчанию.

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a>Использование подстановочных знаков и параметров переключателей

Имена командлетов и параметров могут содержать подстановочные знаки. Используйте `$True` и `$False` для задания значений параметров переключателя, например **verbose** . Параметр **verbose** для общего параметра имеет значение `$True` для всех команд.

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a>Использовать массив для значения по умолчанию

Если параметр может принимать несколько значений, массив, в качестве значений по умолчанию можно задать несколько значений. Значение по умолчанию `Invoke-Command:ComputerName` для ключа равно значению массива **Server01** и **Server02** .

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a>Использовать блок сценария

Можно использовать блок скрипта для задания различных значений по умолчанию для параметра в различных условиях. PowerShell вычисляет блок скрипта и использует результат в качестве значения параметра по умолчанию.

`Format-Table:AutoSize`Набор ключей, который переключает параметр на значение по умолчанию **true** . `If`Инструкция содержит условие, которое `$host.Name` должно быть консолью PowerShell **ConsoleHost** .

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

Если параметр принимает значение блока сценария, заключите блок сценария в дополнительный набор фигурных скобок. Когда PowerShell вычисляет внешний блок скрипта, результатом является внутренний блок скрипта, который задается как значение параметра по умолчанию.

`Invoke-Command:ScriptBlock`Ключ задается в качестве значения по умолчанию для **журнала системных событий** , так как блок скрипта заключен во второй набор фигурных скобок. Результат блока скрипта передается в `Invoke-Command` командлет.

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a>Как получить \$ псдефаултпараметервалуес

Значения хэш-таблицы отображаются путем ввода `$PSDefaultParameterValues` в командной строке PowerShell.

Для `$PSDefaultParameterValues` хэш-таблицы заданы три пары " **ключ-значение** ".
Эта хэш-таблица используется в следующих примерах, в которых описывается добавление, изменение и удаление значений из `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

Чтобы получить значение определенного `CmdletName:ParameterName` ключа, используйте следующий синтаксис:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

Например, чтобы получить значение для `Send-MailMessage:SmtpServer` ключа.

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a>Добавление значений в \$ псдефаултпараметервалуес

Чтобы добавить значение в `$PSDefaultParameterValues` , используйте метод **Add** . Добавление значения не влияет на существующие значения хэш-таблицы.

Используйте запятую ( `,` ), чтобы отделить **ключ** от **значения** . В следующем синтаксисе показано, как использовать метод **Add** для `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

Хэш-таблица, созданная в предыдущем примере, обновляется новой парой " **ключ-значение** ". Метод **Add** задает `Get-Process:Name` для ключа значение **PowerShell** .

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

Следующий синтаксис выполняет тот же результат.

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу. `Get-Process:Name`Ключ добавлен.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a>Удаление значений из \$ псдефаултпараметервалуес

Чтобы удалить значение из `$PSDefaultParameterValues` , используйте метод **Remove** хэш-таблиц. Удаление значения не влияет на существующие значения хэш-таблицы.

В следующем синтаксисе показано, как использовать метод **Remove** для `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

В этом примере хэш-таблица, созданная в предыдущем примере, обновляется для удаления пары " **ключ-значение** ". Метод **Remove** удаляет `Get-Process:Name` ключ.

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу. `Get-Process:Name`Ключ был удален.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a>Изменение значений в \$ псдефаултпараметервалуес

Изменения в определенном значении не влияют на существующие значения хэш-таблицы. Чтобы изменить определенную пару " **ключ-значение** " в `$PSDefaultParameterValues` , используйте следующий синтаксис:

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

В этом примере хэш-таблица, созданная в предыдущем примере, обновляется для изменения пары " **ключ-значение** ". Следующая команда изменяет `Send-MailMessage:SmtpServer` ключ на новое значение **ServerXYZ** .

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу. `Send-MailMessage:SmtpServer`Ключ был изменен на новое значение.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a>Отключение и повторное включение \$ псдефаултпараметервалуес

Можно временно отключить и снова включить `$PSDefaultParameterValues` .
Отключение `$PSDefaultParameterValues` полезно, если выполняются сценарии, для которых требуются разные значения параметров по умолчанию.

Чтобы отключить `$PSDefaultParameterValues` , добавьте ключ `Disabled` со значением **true** . Значения в сохраняются `$PSDefaultParameterValues` , но не вступают в силу.

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

Следующий синтаксис выполняет тот же результат.

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу со значением `Disabled` ключа.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

Для повторного включения `$PSDefaultParameterValues` удалите **отключенный** ключ или измените значение **отключенного** ключа на `$False` . Предыдущее значение `$PSDefaultParameterValues` вступает в силу еще раз.

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

Следующий синтаксис выполняет тот же результат.

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу. При использовании метода **Remove** `Disabled` ключ удаляется из выходных данных.
Если для повторного включения использовался альтернативный синтаксис `$PSDefaultParameterValues` , `Disabled` ключ отображается как **false** .

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a>См. также статью

[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Script_Blocks](about_Script_Blocks.md)

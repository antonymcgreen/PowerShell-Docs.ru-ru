---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: a0d0e31e9010c5ee119b4fbe5f6a877ebc4dc1d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226297"
---
# New-Module

## Краткий обзор
Создает новый динамический модуль, который существует только в памяти.

## SYNTAX

### ScriptBlock (по умолчанию)

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### name

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

`New-Module`Командлет создает динамический модуль из блока скрипта. Элементы динамического модуля, например функции и переменные, сразу же становятся доступными в рамках сеанса и остаются таковыми до его завершения.

Для динамических, как и для статических, модулей командлеты и функции по умолчанию экспортируются, а переменные и псевдонимы — нет. Однако можно использовать командлет Export-ModuleMember и параметры, `New-Module` чтобы переопределить значения по умолчанию.

**AsCustomObject** `New-Module` Для возврата динамического модуля в качестве пользовательского объекта можно также использовать параметр AsCustomObject. Элементы модулей, например функции, не импортируются в сеанс, а реализуются в виде методов скриптов пользовательского объекта.

Динамические модули существуют только в памяти, а не на диске. Как и элементы всех остальных модулей, элементы динамических модулей выполняются в закрытой области модуля, являющейся дочерней областью глобальной области. Командлет Get-Module не может получить динамический модуль, но командлет Get-Command может получить экспортированные элементы.

Чтобы сделать динамический модуль доступным, передайте `Get-Module` `New-Module` команду в командлет Import-Module или передайте объект модуля, который `New-Module` возвращает в `Import-Module` . Это действие добавляет в список динамический модуль `Get-Module` , но не сохраняет модуль на диск или делает его постоянным.

## Примеры

### Пример 1. Создание динамического модуля

В этом примере создается новый динамический модуль с именем функции `Hello` . Команда возвращает объект модуля, представляющий новый динамический модуль.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### Пример 2. Работа с динамическими модулями, Get-Module и Get-Command

В этом примере показано, что динамические модули не возвращаются `Get-Module` командлетом. Члены, которые они экспортируют, возвращаются `Get-Command` командлетом.

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### Пример 3. экспорт переменной в текущий сеанс

В этом примере `Export-ModuleMember` командлет используется для экспорта переменной в текущий сеанс.
Без `Export-ModuleMember` команды экспортируется только функция.

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

В выходных данных показано, что в сеанс были экспортированы и переменная, и функция.

### Пример 4. предоставление доступа к динамическому модулю для Get-Module

В этом примере показано, как можно сделать динамический модуль доступным `Get-Module` по конвейеру динамического модуля в `Import-Module` .

`New-Module` Создает объект модуля, который передается в `Import-Module` командлет. Параметр **Name** объекта `New-Module` присваивает понятное имя модулю. Поскольку `Import-Module` по умолчанию не возвращает никаких объектов, выходные данные этой команды отсутствуют. `Get-Module` , что **гритингмодуле** был импортирован в текущий сеанс.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

`Get-Command`Командлет показывает `Hello` функцию, экспортируемую динамическим модулем.

### Пример 5. Создание пользовательского объекта, который содержит экспортированные функции

В этом примере показано, как использовать параметр **AsCustomObject** метода `New-Module` для создания пользовательского объекта, который содержит методы скрипта, представляющие экспортированные функции.

`New-Module`Командлет создает динамический модуль с двумя функциями `Hello` и `Goodbye` . Параметр **AsCustomObject** создает пользовательский объект вместо объекта **PSModuleInfo** , который `New-Module` создается по умолчанию. Этот пользовательский объект сохраняется в `$m` переменной.
`$m`Переменная, по видимому, не имеет присвоенного значения.

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

Передача по конвейеру в `$m` `Get-Member` командлет отображает свойства и методы пользовательского объекта. Выходные данные показывают, что объект содержит методы скрипта, представляющие `Hello` `Goodbye` функции и.
Наконец, мы вызываем эти методы скрипта и отображаем результаты.

### Пример 6. получение результатов блока Script

В этом примере используется параметр **ReturnResult** для запроса результатов выполнения блока сценария вместо запроса объекта модуля. Блок скрипта в новом модуле определяет `SayHello` функцию, а затем вызывает функцию.

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## PARAMETERS

### -ArgumentList

Задает массив аргументов, которые являются значениями параметров, передаваемыми в блок скрипта. Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsCustomObject

Указывает, что этот командлет возвращает пользовательский объект, представляющий динамический модуль. Элементы модуля не импортируются в сеанс, а реализуются в виде методов скриптов пользовательского объекта. Пользовательский объект можно сохранить в переменную и использовать точку для вызова элементов.

Если модуль содержит несколько членов с одинаковым именем, например функцию и переменную с именем A, доступ к одному элементу с каждым именем можно получить из пользовательского объекта.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Командлет

Указывает массив командлетов, которые этот командлет экспортирует из модуля в текущий сеанс.
Введите список командлетов, разделенных запятыми. Можно использовать подстановочные знаки. По умолчанию экспортируются все командлеты в модуле.

В блоке скрипта определять командлеты нельзя, однако, динамический модуль может включать командлеты, если импортирует их из двоичного модуля.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Function

Указывает массив функций, которые этот командлет экспортирует из модуля в текущий сеанс.
Введите список функций, разделенных запятыми. Можно использовать подстановочные знаки. По умолчанию экспортируются все определенные в модуле функции.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Задает имя нового модуля. Имя модуля можно также передать в командлет New-Module по конвейеру.

Значение по умолчанию — это автоматически сформированное имя, которое начинается с `__DynamicModule_` и за которым следует идентификатор GUID, указывающий путь к динамическому модулю.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReturnResult

Указывает, что этот командлет запускает блок скрипта и возвращает результаты блока сценария вместо возврата объекта модуля.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Задает содержимое динамического модуля. Заключите содержимое в фигурные скобки ( `{}` ), чтобы создать блок скрипта. Этот параметр обязателен.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Имя модуля можно передать в этот командлет по конвейеру.

## Выходные данные

### System. Management. Automation. PSModuleInfo, System. Management. Automation. PSCustomObject или None

По умолчанию этот командлет создает объект **PSModuleInfo** . При использовании параметра **AsCustomObject** создается объект **PSCustomObject** . Если вы используете параметр **ReturnResult** , он возвращает результат вычисления блока скрипта в динамическом модуле.

## ПРИМЕЧАНИЯ

Также можно ссылаться `New-Module` по его псевдониму, `nmo` . Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).

## Связанные ссылки

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)

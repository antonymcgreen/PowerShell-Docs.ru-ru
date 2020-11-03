---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: baaff5a02cc583394019d2fe79a1b4d6210473af
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225509"
---
# New-Object

## Краткий обзор
Создает экземпляр объекта Microsoft .NET Framework или COM.

## SYNTAX

### NET (по умолчанию)

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### -

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## DESCRIPTION

`New-Object`Командлет создает экземпляр .NET Framework или COM-объекта.

Можно указать тип класса .NET Framework или идентификатор ProgID объекта COM. По умолчанию вводится полное имя класса .NET Framework, и командлет возвращает ссылку на экземпляр этого класса. Чтобы создать экземпляр COM-объекта, используйте параметр **ComObject** и укажите ProgID объекта в качестве его значения.

## Примеры

### Пример 1. Создание объекта System. Version

В этом примере создается объект **System. Version** с использованием строки "1.2.3.4" в качестве конструктора.

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### Пример 2. Создание COM-объекта Internet Explorer

В этом примере создаются два экземпляра COM-объекта, представляющего приложение Internet Explorer. Первый экземпляр использует хэш-таблицу параметра **Свойства** для вызова метода **Navigate2** и устанавливает свойство **Visible** объекта в значение `$True` , чтобы сделать приложение видимым.
Второй экземпляр получает те же результаты с отдельными командами.

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### Пример 3. Использование параметра with для создания устранимой ошибки

В этом примере показано, что при **добавлении параметра с параметром «** явное» `New-Object` командлет создает неустранимую ошибку, когда COM-объект использует сборку взаимодействия.

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### Пример 4. Создание COM-объекта для управления рабочим столом Windows

В этом примере показано, как создать и использовать COM-объект для управления рабочим столом Windows.

Первая команда использует параметр **ComObject** `New-Object` командлета для создания com-объекта с **оболочкой. ProgID приложения** . Он сохраняет полученный объект в `$ObjShell` переменной. Вторая команда передает `$ObjShell` переменную в `Get-Member` командлет, который отображает свойства и методы COM-объекта. Между методами используется метод **тоггледесктоп** . Третья команда вызывает метод **ToggleDesktop** объекта, чтобы свести к минимуму число открытых окон на рабочем столе.

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### Пример 5. Передача нескольких аргументов в конструктор

В этом примере показано, как создать объект с конструктором, который принимает несколько параметров. Параметры должны быть размещены в массиве при использовании параметра **ArgumentList** .

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

PowerShell привязывает каждый член массива к параметру конструктора.

> [!NOTE]
> В этом примере для удобства чтения используется параметр Сплаттинг. Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

### Пример 6. вызов конструктора, принимающего массив в качестве одного параметра

В этом примере показано, как создать объект с конструктором, принимающим параметр, который является массивом или коллекцией. Параметр массива должен быть помещен в оболочку внутри другого массива.

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

Первая попытка создать объект в этом примере завершается ошибкой. PowerShell попытался привязать три члена `$array` к параметрам конструктора, но конструктор не принимает три параметра. Перенос `$array` в другой массив предотвращает попытку PowerShell выполнить привязку трех членов `$array` к параметрам конструктора.

## PARAMETERS

### -ArgumentList

Задает массив аргументов для передачи конструктору класса .NET Framework. Если конструктор принимает один параметр, который является массивом, этот параметр необходимо заключить в другой массив. Пример:

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).

Псевдоним для **ArgumentList** — **Args**.

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComObject

Указывает программный идентификатор (ProgID) объекта COM.

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Задает значения свойств и вызывает методы нового объекта.

Введите хэш-таблицу, в которой ключи — это имена свойств или методов, а значения — это значения свойств или аргументы методов. `New-Object` Создает объект и задает каждое значение свойства и вызывает каждый метод в том порядке, в котором они отображаются в хэш-таблице.

Если новый объект является производным от класса **PSObject** и вы указали свойство, которое не существует в объекте, `New-Object` добавляет указанное свойство в объект в качестве NoteProperty. Если объект не является **PSObject** , команда создает неустранимую ошибку.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Не ограничивать

Указывает, что командлет создает неустранимую ошибку, когда COM-объект, который вы пытаетесь создать, использует сборку взаимодействия. Эта функция отличает настоящие COM-объекты от объектов .NET Framework с вызываемыми оболочками COM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Указывает полное имя класса .NET Framework. Нельзя указать и параметр **TypeName** , и параметр **ComObject** .

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Объект

`New-Object` Возвращает созданный объект.

## ПРИМЕЧАНИЯ

- `New-Object` предоставляет наиболее часто используемые функциональные возможности функции CreateObject VBScript. Инструкция, подобная `Set objShell = CreateObject("Shell.Application")` в VBScript, может быть переведена в `$objShell = New-Object -COMObject "Shell.Application"` PowerShell.
- `New-Object` расширяет функциональные возможности, доступные в среде сервера сценариев Windows, облегчая работу с .NET Framework объектами из командной строки и в скриптах.

## Связанные ссылки

[about_Object_Creation](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[Compare-Object](Compare-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object;](Measure-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 1a8e278e03d8aea4129c172d786d285d6b55b083
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226586"
---
# Get-Error

## Краткий обзор

Возвращает и отображает последние сообщения об ошибках из текущего сеанса.

## SYNTAX

### Новейшие (по умолчанию)

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### Ошибка

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Error`Командлет возвращает объект **псекстендедеррор** , представляющий текущие сведения об ошибке из последней ошибки, произошедшей в сеансе.

Можно использовать `Get-Error` для вывода указанного числа ошибок, произошедших в текущем сеансе, с помощью **последнего** параметра.

`Get-Error`Командлет также получает объекты Error из коллекции, например `$Error` , чтобы отобразить несколько ошибок из текущего сеанса.

## Примеры

### Пример 1. Получение последних сведений об ошибке

В этом примере `Get-Error` отображаются сведения о последней ошибке, произошедшей в текущем сеансе.

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### Пример 2. Получение указанного числа сообщений об ошибках, произошедших в текущем сеансе

В этом примере показано, как использовать `Get-Error` с **новым** параметром. В этом примере **последними** возвращаются сведения о трех последних ошибках, произошедших в этом сеансе.

```powershell
Get-Error -Newest 3
```

### Пример 3. Отправка коллекции ошибок для получения подробных сообщений

`$Error`Автоматическая переменная содержит массив объектов Error в текущем сеансе. Для `Get-Error` получения подробных сообщений об ошибках можно направить массив объектов в конвейер.

В этом примере `$Error` передается `Get-Error` командлету. Результат представляет собой список подробных сообщений об ошибках, аналогичный результату примера 1.

```powershell
$Error | Get-Error
```

## PARAMETERS

### — Самый новый

Указывает количество ошибок, которые должны отображаться в текущем сеансе.

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Этот параметр используется для входных данных конвейера.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### PSObject

Поддерживает входные данные из любого **PSObject** , но результаты могут различаться, если не задан объект **ерроррекорд** или **Exception** .

## Выходные данные

### System. Management. Automation. Ерроррекорд # Псекстендедеррор

Выходные данные в объекте **псекстендедеррор** .

## ПРИМЕЧАНИЯ

`Get-Error` принимает входные данные конвейера. Например, `$Error | Get-Error`.

## Связанные ссылки

[about_Try_Catch_Finally](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)

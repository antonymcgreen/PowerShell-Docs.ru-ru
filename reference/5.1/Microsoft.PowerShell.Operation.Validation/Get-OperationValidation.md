---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227809"
---
# Get-OperationValidation

## Краткий обзор
Возвращает тесты инфраструктуры проверки операций.

## SYNTAX

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-оператионвалидатион** возвращает платформу проверки операций для установленных модулей.

Модули, содержащие папку Diagnostics, проверяются на наличие Pester тестов в простой или полной вложенной папке или в обоих случаях.

## Примеры

### Пример 1. Проверка операций Get

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

Эта команда получает проверочные тесты из модуля с именем подставлял в папке К:\темп\модулес.

## PARAMETERS

### -ModuleName
Указывает массив имен модулей.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestType
Указывает массив типов тестов.
Допустимые значения: Simple, всесторонний или Both.
Значение по умолчанию — Simple, всеобъемлющее.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передавать входные данные.

## Выходные данные

### PSCustomObject
**PSCustomObject** описывает проверку.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Invoke-OperationValidation](Invoke-OperationValidation.md)

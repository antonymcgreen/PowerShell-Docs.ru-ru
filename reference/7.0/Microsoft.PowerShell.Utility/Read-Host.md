---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: aacc89001373ecc8ef75e630f965a8d807bd4ac3
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "93229625"
---
# Read-Host

## Краткий обзор
Считывает строку ввода из консоли.

## SYNTAX

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## DESCRIPTION

`Read-Host`Командлет считывает строку входных данных из консоли. Его можно использовать для запроса ввода данных пользователем. Так как входные данные можно сохранить в виде защищенной строки, этот командлет можно использовать, чтобы запросить у пользователя защищенные данные, такие как пароли, а также общие данные.

## Примеры

### Пример 1. Сохранение входных данных консоли в переменную

В этом примере отображается строка "введите свой возраст:" в качестве подсказки. Если введено значение и нажата клавиша ВВОД, значение сохраняется в `$Age` переменной.

```powershell
$Age = Read-Host "Please enter your age"
```

### Пример 2. Сохранение входных данных консоли в виде защищенной строки

В этом примере отображается строка "введите пароль:" в качестве подсказки. При вводе значения в `*` консоли вместо входных данных появятся звездочки (). При нажатии клавиши Ввод значение сохраняется как объект **SecureString** в `$pwd_secure_string` переменной.

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## PARAMETERS

### -AsSecureString

Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных. При использовании этого параметра выходные данные `Read-Host` командлета являются объектом **SecureString** ( **System. Security. SecureString** ).

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

### -Prompt

Задает текст запроса.
Введите строку.
Если строка содержит пробелы, заключите ее в кавычки.
PowerShell добавляет двоеточие ( `:` ) в введенный текст.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
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

### System. String или System. Security. SecureString

Если используется параметр **AsSecureString** , `Read-Host` возвращает **SecureString** . В противном случае возвращается строка.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Clear-Host;](../microsoft.powershell.core/clear-host.md)

[Get-Host](Get-Host.md)

[Write-Host](Write-Host.md)

[ConvertFrom-SecureString](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)

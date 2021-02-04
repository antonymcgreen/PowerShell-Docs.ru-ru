---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: c90a2f49c95333e45893e186d6e1f1da4b3fe41a
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771827"
---
# Set-Variable

## Краткий обзор
Задает значение переменной. Создает переменную, если переменной с запрошенным именем не существует.

## SYNTAX

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Variable`Командлет присваивает значение указанной переменной или изменяет текущее значение. Если переменная не существует, командлет создает ее.

## Примеры

### Пример 1. задание переменной и получение ее значения

Эти команды задают значение `$desc` переменной `A description` , а затем получает значение переменной.

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### Пример 2. Задание глобальной переменной, доступной только для чтения

В этом примере создается глобальная переменная, доступная только для чтения, которая содержит все процессы в системе, а затем отображаются все свойства переменной.

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option Constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

Команда использует `Set-Variable` командлет для создания переменной. Он использует параметр **PassThru** для создания объекта, представляющего новую переменную, и использует оператор конвейера ( `|` ) для передачи объекта в `Format-List` командлет.  `Format-List` `*` Для вывода всех свойств только что созданной переменной в нем используется параметр Property со значением All ().

Значение, `(Get-Process)` , заключено в круглые скобки, чтобы убедиться, что оно выполняется перед сохранением в переменной. В противном случае переменная содержит слова «**Get-Process**».

### Пример 3. Знакомство с открытыми и частными переменными

В этом примере показано, как изменить видимость переменной на `Private` . Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

Эта команда показывает, как изменить видимость переменной на Private. Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.

## PARAMETERS

### -Description

Задает описание переменной.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Указывает массив элементов, которые этот командлет исключает из операции. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` .
Разрешено использовать подстановочные знаки.

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

### -Force

Позволяет создать переменную с тем же именем, как у существующей переменной только для чтения, или изменить значение переменной только для чтения.

По умолчанию переменная может быть перезаписана, если только переменная не имеет значение параметра `ReadOnly` или `Constant` . Дополнительные сведения см. в описании параметра **Option** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Задает массив элементов, включаемых этим командлетом в операцию. Значение этого параметра определяет параметр **Name** . Введите имя или шаблон имени, например `c*` . Разрешено использовать подстановочные знаки.

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

Определяет имя переменной.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Параметр-Option

Задает значение свойства **Options** переменной.

Допустимые значения:

- `None`: Задает параметры без параметров. (по умолчанию).
- `ReadOnly`: Можно удалить. Нельзя изменить, за исключением использования параметра Force.
- `Constant`: Невозможно удалить или изменить. `Constant` параметр допустим только при создании переменной. Параметры существующей переменной нельзя изменить на `Constant` .
- `Private`: Переменная доступна только в текущей области.
- `AllScope`: Переменная копируется во все новые создаваемые области.

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий новую переменную. По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope

Задает область действия переменной. Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Скрипт
- Частные
- Число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).

По умолчанию используется значение Local.

Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Задает значение переменной.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### — Видимость

Определяет, видима ли переменная вне сеанса, в котором она была создана. Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.

Допустимые значения:

- Public: переменная является видимой. (Значение Public используется по умолчанию.)
- Private: переменная не видна.

Если переменная является закрытой, она не отображается в списках переменных, например, возвращаемых `Get-Variable` , или в режиме отображения **переменной:** Drive. Команды чтения или изменения значения частной переменной возвращают ошибку. Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Object

Объект, представляющий значение переменной, можно передать по конвейеру `Set-Variable` .

## Выходные данные

### None или System. Management. Automation. PSVariable

При использовании параметра **PassThru** `Set-Variable` создает объект **System. Management. Automation. PSVariable** , представляющий новую или измененную переменную.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

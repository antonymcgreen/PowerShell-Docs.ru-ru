---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 1a405a510c6862e62b4f690c28611af2cf8246c8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227502"
---
# Set-Variable

## Краткий обзор
Задает значение переменной.
Создает переменную, если переменной с запрошенным именем не существует.

## SYNTAX

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Set-Variable** присваивает значение указанной переменной или изменяет текущее значение.
Если переменная не существует, командлет создает ее.

## Примеры

### Пример 1. задание переменной и получение ее значения

```
PS C:\> Set-Variable -Name "desc" -Value "A description"
PS C:\> Get-Variable -Name "desc"
```

Эти команды задают в качестве значения переменной desc описание, а затем получают значение переменной.

### Пример 2. Задание глобальной переменной, доступной только для чтения

```
PS C:\> Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru | Format-List -Property *
```

Эта команда создает глобальную переменную только для чтения, содержащую все процессы в системе, а затем отображает все свойства переменной.

Команда использует командлет **Set-Variable** для создания переменной.
Он использует параметр *PassThru* для создания объекта, представляющего новую переменную, и использует оператор конвейера (|) для передачи объекта в командлет Format-List.
Для вывода всех свойств только что созданной переменной используется параметр *Property* объекта Format-List со значением All (*).

Значение, "(Get-Process)", заключается в круглые скобки, чтобы командлет выполнялся перед сохранением в переменной.
В противном случае переменная содержит слова Get-Process.

### Пример 3. Знакомство с открытыми и частными переменными

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

Эта команда показывает, как изменить видимость переменной на Private.
Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.

В примере выходных данных показана разница в поведении общих и частных переменных.

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

Указывает массив элементов, которые этот командлет исключает из операции.
Значение этого параметра определяет параметр *Path* .
Введите элемент пути или шаблон, например `*.txt` .
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

По умолчанию переменную можно перезаписать, если только переменная не имеет значение параметра ReadOnly или Constant.
Дополнительные сведения см. в описании параметра *Option* .

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

Задает массив элементов, включаемых этим командлетом в операцию.
Значение этого параметра определяет параметр *Name* .
Введите имя или шаблон имени, например `c*` .
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

- Нет: задает параметры без параметров. (по умолчанию).
- ReadOnly: можно удалить. Нельзя изменить, за исключением использования параметра Force.
- Константа: невозможно удалить или изменить. Значение Constant допустимо только при создании переменной. Невозможно изменить параметры существующей переменной на Constant.
- Private: переменная доступна только в текущей области.
- AllScope: переменная копируется во все новые создаваемые области.

Чтобы просмотреть свойство **Options** всех переменных в сеансе, введите `Get-Variable | Format-Table -Property name, options -Autosize` .

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
Возвращает объект, представляющий новую переменную.
По умолчанию этот командлет не создает выходные данные.

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
- Сценарий
- Private
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

Определяет, видима ли переменная вне сеанса, в котором она была создана.
Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.

Допустимые значения:

- Public: переменная является видимой. (Значение Public используется по умолчанию.)
- Private: переменная не видна.

Если переменная частная, она не отображается в списках переменных, например возвращаемых командлетом Get-Variable, или в выходных данных для диска Variable:.
Команды чтения или изменения значения частной переменной возвращают ошибку.
Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.

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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

Объект, представляющий значение переменной, можно передать в командлет **Set-Variable** по конвейеру.

## Выходные данные

### None или System. Management. Automation. PSVariable

При использовании параметра *PassThru* командлет **Set-Variable** создает объект **System. Management. Automation. PSVariable** , представляющий новую или измененную переменную.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

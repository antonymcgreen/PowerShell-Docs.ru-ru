---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 47d69cbe8d8542b5954d3e4a585735f7d0050715
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347726"
---
# Unblock-File

## Краткий обзор
Разблокирует файлы, скачанные из Интернета.

## SYNTAX

### ByPath (по умолчанию)

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Unblock-File`Командлет позволяет открывать файлы, загруженные из Интернета. Он разблокирует файлы скриптов PowerShell, загруженные из Интернета, чтобы их можно было запустить даже в том случае, если политика выполнения PowerShell **RemoteSigned**. По умолчанию эти файлы блокируются для защиты компьютера от ненадежных файлов.

Перед использованием `Unblock-File` командлета проверьте файл и его источник и убедитесь, что он является надежным для открытия.

На внутреннем уровне `Unblock-File` командлет удаляет зону. идентификатор альтернативного потока данных, который имеет значение 3, чтобы указать, что он был загружен из Интернета.

Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Разблокировка файла

Эта команда разблокирует файл PowerShellTips.chm.

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### Пример 2. Разблокировка нескольких файлов

Эта команда разблокирует все файлы в `C:\Downloads` каталоге, имена которых содержат "PowerShell". Не выполняйте подобную команду, пока не убедитесь в безопасности всех файлов.

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### Пример 3. скрипты поиска и разблокировки

Эта команда показывает, как найти и разблокировать скрипты PowerShell.

Первая команда использует параметр **Stream** командлета *Get-Item* для получения файлов с помощью потока зоны. identifier.

Вторая команда показывает, что происходит при запуске заблокированного скрипта в сеансе PowerShell, в котором политика выполнения — **RemoteSigned**. Политика RemoteSigned запрещает выполнение сценариев, загруженных из Интернета, если они не имеют цифровой подписи.

Третья команда использует командлет, `Unblock-File` чтобы разблокировать скрипт, чтобы он мог выполняться в сеансе.

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## PARAMETERS

### -LiteralPath

Указывает файлы для разблокирования. В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает файлы для разблокирования. Поддерживаются подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

### System.String

Путь к файлу можно передать по конвейеру `Unblock-File` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- В PowerShell 7 добавлена поддержка macOS.
- `Unblock-File`Командлет работает только на дисках файловой системы.
- `Unblock-File` выполняет ту же операцию, что и кнопка **разблокировать** в диалоговом окне " **свойства** " в проводнике.
- При использовании `Unblock-File` командлета для незаблокированного файла команда не влияет на неблокируемый файл, и командлет не создает ошибки.

## Связанные ссылки

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[Get-Item](../Microsoft.PowerShell.Management/Get-Item.md)

[Out-File](Out-File.md)

[Поставщик FileSystem](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 7e88e873c5c6aa0733869cdaaf1fba583468261d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226818"
---
# Resolve-Path

## Краткий обзор
Разрешает подстановочные знаки в пути и отображает содержимое пути.

## SYNTAX

### Путь (по умолчанию)

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### LiteralPath

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

`Resolve-Path`Командлет отображает элементы и контейнеры, которые соответствуют шаблону подстановочного знака в указанном расположении. Соответствие может включать файлы, папки, разделы реестра или любой другой объект, доступный поставщику PSDrive.

## Примеры

### Пример 1. разрешение пути к домашней папке

Символ тильды (~) является сокращенной записью для домашней папки текущего пользователя. В этом примере показано `Resolve-Path` возвращение полного значения пути.

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### Пример 2. разрешение пути к папке Windows

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

При запуске из корня диска C: Эта команда возвращает путь к папке Windows на диске C:.

### Пример 3. получение всех путей в папке Windows

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

Эта команда возвращает все папки в папке C:\Windows. Команда использует оператор конвейера (|) для отправки строки пути в `Resolve-Path` .

### Пример 4. разрешение пути UNC

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

Эта команда разрешает UNC-путь и возвращает ресурсы совместного использования этого пути.

### Пример 5. получение относительных путей

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

Эта команда возвращает относительные пути для каталогов в корне диска C:.

### Пример 6. разрешение пути, содержащего скобки

В этом примере используется параметр **LiteralPath** для разрешения пути к \[ \] вложенной папке test XML.
Использование **LiteralPath** приводит к тому, что квадратные скобки интерпретируются как обычные символы, а не как регулярное выражение.

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## PARAMETERS

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например User01 или Domain01\User01, или передайте объект **PSCredential** . Объект **PSCredential** можно создать с помощью `Get-Credential` командлета. При вводе имени пользователя этот командлет запрашивает пароль.

Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Указывает преобразуемый путь, который требуется разрешить. Значение параметра **LiteralPath** используется в точности как типизированное. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь PowerShell для разрешения. Этот параметр обязателен. Можно также передать строку пути в `Resolve-Path` . Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Относительное

Указывает, что этот командлет возвращает относительный путь.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### System. Management. Automation. PathInfo, System. String

Возвращает объект **PathInfo** . Возвращает строковое значение для разрешенного пути, если указан **относительный** параметр.

## ПРИМЕЧАНИЯ

`*-Path`Командлеты работают с файловой системой, реестром и поставщиками сертификатов.

`Resolve-Path` предназначен для работы с любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../microsoft.powershell.core/about/about_providers.md).

`Resolve-Path` разрешает только существующие пути. Его нельзя использовать для разрешения несуществующего расположения.

## Связанные ссылки

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

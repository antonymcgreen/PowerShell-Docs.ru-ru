---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 7752688a04057861fffdbc7b30c293239acb132e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227261"
---
# Join-Path

## Краткий обзор
Объединяет путь и его дочерний путь в один путь.

## SYNTAX

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

`Join-Path`Командлет объединяет путь и дочерний путь в один путь.
Поставщик поддерживает разделители пути.

## Примеры

### Пример 1. Объединение пути с дочерним путем

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

Эта команда использует `Join-Path` для объединения пути с ChildPath.

Так как команда выполняется от `FileSystem` поставщика, она предоставляет `\` Разделитель для объединения путей.

### Пример 2. объединение путей, которые уже содержат разделители каталогов

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

Существующие разделители каталогов `\` и обработаны, поэтому существует только один разделитель между `Path` и `ChildPath`

### Пример 3. Отображение файлов и папок путем присоединения к пути с помощью дочернего пути

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

Эта команда отображает файлы и папки, на которые имеются ссылки, путем объединения \* пути к:\вин и системного \* дочернего пути.
Он отображает те же файлы и папки, что и `Get-ChildItem` , но отображает полный путь к каждому элементу.
В этой команде `Path` `ChildPath` имена и необязательные параметры опущены.

### Пример 4. Использование Join-Path с поставщиком реестра PowerShell

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

Эта команда отображает разделы реестра `HKLM\System` , содержащиеся в подразделе реестра `ControlSet` .

`Resolve`Параметр, пытается разрешить присоединенный путь, включая подстановочные знаки из текущего пути поставщика.`HKLM:\`

### Пример 5. Объединение нескольких корней пути с помощью дочернего пути

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

Эта команда использует `Join-Path` для объединения нескольких корней пути с дочерним путем.

> [!NOTE]
> Диски, указанные параметром, `Path` должны существовать, иначе соединение этой записи завершится ошибкой.

### Пример 6. объединение корней диска файловой системы с дочерним путем

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

Эта команда объединяет корни каждого диска файловой системы PowerShell в консоли с путем к дочернему каталогу SUBDIR.

Команда использует `Get-PSDrive` командлет для получения дисков PowerShell, поддерживаемых поставщиком FileSystem.
`ForEach-Object`Инструкция выбирает только свойство root `PSDriveInfo` объектов и объединяет его с указанным дочерним путем.

Выходные данные показывают, что диски PowerShell на компьютере включали диск, сопоставленный с каталогом C:\Program Files.

### Пример 7. объединение неопределенного числа путей

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

`AdditionalChildPath`Параметр позволяет присоединить неограниченное количество путей.

В этом примере имена параметров не используются, поэтому "a" привязывается к `Path` , "b" к `ChildPath` и "c-g" в `AdditionalChildPath`

## PARAMETERS

### -Аддитионалчилдпас

Задает дополнительные элементы для добавления к значению параметра *path* . `ChildPath`Параметр по-прежнему является обязательным и должен быть указан также.

Этот параметр указывается со `ValueFromRemainingArguments` свойством, которое позволяет присоединить неопределенное число путей.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ChildPath

Указывает элементы, добавляемые к значению `Path` параметра.
Разрешено использовать подстановочные знаки.
`ChildPath`Параметр является обязательным, хотя имя параметра ("ChildPath") является необязательным.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.
> Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

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

### -Path

Указывает основной путь (или пути), к которому добавляется дочерний путь.
Разрешено использовать подстановочные знаки.

Значение `Path` определяет, какой поставщик соединяет пути и добавляет разделители пути.
`Path`Параметр является обязательным, хотя имя параметра (Path) является необязательным.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Разрешить

Указывает, что этот командлет должен попытаться разрешить присоединенный путь от текущего поставщика.

- Если используются подстановочные знаки, командлет возвращает все пути, соответствующие пути к соединению.
- Если **подстановочные знаки не используются** , командлет выдаст ошибку, если путь не существует.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### System.String

Этот командлет возвращает строку, содержащую результирующий путь.

## ПРИМЕЧАНИЯ

Командлеты, содержащие существительное Path (командлеты пути), управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell. Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате. Такие командлеты дейстуют точно так же, как и другие команды для работы с путями, включая Dirname, Normpath, Realpath, Join и т. д.

Командлеты Path можно использовать с несколькими поставщиками, включая `FileSystem` поставщики, `Registry` и `Certificate` .

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.
Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.
Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Convert-Path](Convert-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

[Get-PSProvider](Get-PSProvider.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-PSDrive](Get-PSDrive.md)

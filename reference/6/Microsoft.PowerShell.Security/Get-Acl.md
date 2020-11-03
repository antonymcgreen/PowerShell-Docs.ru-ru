---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: 018a1da2a3fd40a95d378a563cacd68a734d9cd6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229221"
---
# Get-Acl

## Краткий обзор
Возвращает дескриптор безопасности для ресурса, например файла или раздела реестра.

## SYNTAX

### ByPath (по умолчанию)

```
Get-Acl [[-Path] <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [<CommonParameters>]
```

### бинпутобжект

```
Get-Acl -InputObject <PSObject> [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Acl`Командлет получает объекты, представляющие дескриптор безопасности файла или ресурса. Дескриптор безопасности содержит списки управления доступом (ACL) ресурса. В списке ACL указаны разрешения пользователей и групп пользователей на доступ к ресурсу.

Начиная с Windows PowerShell 3,0, параметр **InputObject** можно использовать `Get-Acl` для получения дескриптора безопасности объектов, которые не имеют пути.

## Примеры

### Пример 1. Получение списка ACL для папки

В этом примере возвращается дескриптор безопасности `C:\Windows` каталога.

```powershell
Get-Acl C:\Windows
```

### Пример 2. Получение списка ACL для папки с помощью подстановочных знаков

В этом примере выполняется получение пути PowerShell и SDDL для всех `.log` файлов в `C:\Windows` каталоге, имена которых начинаются с `s` .

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

Команда использует `Get-Acl` командлет для получения объектов, представляющих дескрипторы безопасности каждого файла журнала. Он использует оператор конвейера ( `|` ) для отправки результатов в `Format-List` командлет. Команда использует параметр **Property** параметра, `Format-List` чтобы отобразить только свойства **PSPath** и **SDDL** для каждого объекта дескриптора безопасности.

Списки часто используются в PowerShell, так как длинные значения в таблицах усекаются.

Значения **SDDL** важны для системных администраторов, так как они представляют собой простые текстовые строки, содержащие все данные дескриптора безопасности. Их легко передавать и хранить, а также при необходимости анализировать.

### Пример 3. Получение списка записей аудита для ACL

Этот пример получает дескрипторы безопасности `.log` файлов в `C:\Windows` каталоге, имена которых начинаются с `s` .

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

С помощью параметра **Audit** возвращаются записи аудита из списка SACL в дескрипторе безопасности.
Затем он использует `ForEach-Object` командлет для подсчета количества записей аудита, связанных с каждым файлом. Результат представляет собой список соответствующих чисел.

### Пример 4. Получение списка ACL для раздела реестра

В этом примере `Get-Acl` командлет используется для получения дескриптора безопасности подраздела элемента управления ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) реестра.

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

Параметр **path** задает подраздел Control. Оператор конвейера ( `|` ) передает дескриптор безопасности, который `Get-Acl` получает `Format-List` команду, который форматирует свойства дескриптора безопасности в виде списка, чтобы их было легко читать.

### Пример 5. Получение списка ACL с помощью **InputObject**

В этом примере параметр **InputObject** используется `Get-Acl` для получения дескриптора безопасности объекта подсистемы хранения.

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## PARAMETERS

### -Audit

Возвращает данные аудита для дескриптора безопасности из системного списка управления доступом (SACL).

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

### -Exclude

Исключает указанные элементы. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

### -Filter

Задает фильтр в формате или на языке поставщика. Значение этого параметра определяет параметр **Path**. Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика. Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при получении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Получает только указанные элементы. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

### -Path

Задает путь к ресурсу. `Get-Acl` Возвращает дескриптор безопасности ресурса, указанного в пути. Разрешено использовать подстановочные знаки. Если опустить параметр **path** , `Get-Acl` получает дескриптор безопасности текущего каталога.

Имя параметра (Path) указывать необязательно.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -InputObject

Возвращает дескриптор безопасности для указанного объекта. Введите переменную, содержащую объект, либо команду, которая его возвращают.

Нельзя передать по конвейеру объект, отличный от пути, к `Get-Acl` . Вместо этого настроить параметр **InputObject** прямо в команде.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Задает путь к ресурсу. В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Можно передать строку, содержащую путь, в `Get-Acl` .

## Выходные данные

### System. Security. AccessControl. FileSecurity, System. Security. AccessControl. Директорисекурити, System. Security. AccessControl. Регистрисекурити

`Get-Acl` Возвращает объект, представляющий списки ACL, которые он получает. Тип объекта зависит от типа списка ACL.

## ПРИМЕЧАНИЯ

По умолчанию `Get-Acl` отображает путь PowerShell к ресурсу ( `<provider>::<resource-path>` ), владельцу ресурса и «доступ», список (массив) записей управления доступом в списке управления доступом на уровне пользователей (DACL) для ресурса. Список DACL контролируется владельцем ресурса.

При форматировании результата в виде списка ( `Get-Acl | Format-List` ), помимо пути, владельца и списка доступа, PowerShell отображает следующие свойства и значения свойств:

- **Группа** — группа безопасности владельца.
- **Аудит** : список (массив) записей в системном списке управления доступом (SACL). В списке SACL указываются типы попыток доступа, для которых ОС Windows создает записи аудита.
- **SDDL** : дескриптор безопасности ресурса, отображаемый в одной текстовой строке в формате языка определения дескриптора безопасности. Для получения этих данных PowerShell использует метод **жетсддлформ** дескрипторов безопасности.

Так как `Get-Acl` поддерживается в файловой системе и поставщиках реестра, можно использовать `Get-Acl` для просмотра списка управления доступом к объектам файловой системы, таким как файлы и каталоги, и объекты реестра, такие как разделы и записи реестра.

## Связанные ссылки

[Set-Acl](Set-Acl.md)

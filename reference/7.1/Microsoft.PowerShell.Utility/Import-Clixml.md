---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: d33b74101301ec5806f456ddd9cc73bd8b6bb3e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227153"
---
# Import-Clixml

## Краткий обзор
Импортирует файл CLIXML и создает соответствующие объекты в PowerShell.

## SYNTAX

### ByPath (по умолчанию)

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### ByLiteralPath

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## DESCRIPTION

`Import-Clixml`Командлет импортирует XML-файл Common Language Infrastructure (CLI) с данными, представляющими объекты платформы Microsoft .NET и создает объекты PowerShell. Дополнительные сведения о интерфейсе командной строки см. в разделе [независимость от языка](/dotnet/standard/language-independence).

Важным применением `Import-Clixml` на компьютерах Windows является импорт учетных данных и защищенных строк, экспортированных в виде защищенного XML с помощью `Export-Clixml` . Пример см. в примере 2.

`Import-Clixml` для определения формата кодирования файла использует символ-отметку (BOM). Если файл не имеет BOM, предполагается, что используется кодировка UTF8.

## Примеры

### Пример 1. Импорт сериализованного файла и повторное создание объекта

В этом примере `Export-Clixml` командлет используется для сохранения сериализованной копии сведений о процессе, возвращаемых `Get-Process` . `Import-Clixml` Извлекает содержимое сериализованного файла и повторно создает объект, хранящийся в `$Processes` переменной.

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### Пример 2. Импорт защищенного объекта учетных данных

В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.

> [!IMPORTANT]
> `Export-Clixml` экспортирует только зашифрованные учетные данные в Windows. В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows.
Шифрование гарантирует, что только ваша учетная запись пользователя сможет расшифровать содержимое объекта учетных данных. Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.

В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` . Замените **TestScript** именем скрипта, с которым загружаются учетные данные.

Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.

Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды. Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт. Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.

## PARAMETERS

### -First

Получает только указанное количество объектов. Введите количество объектов, которые необходимо получить.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTotalCount

Сообщает общее число объектов в наборе данных, за которыми следуют выбранные объекты. Если командлет не может определить общее число, отображается **неизвестное общее число**. Целочисленное значение имеет свойство **точности** , которое указывает надежность общего значения Count. Значение **точности** в диапазоне от `0.0` до `1.0` где `0.0` означает, что командлет не может подсчитать объекты, `1.0` означает, что счетчик является точным, а значение между и указывает на более `0.0` `1.0` надежную оценку.

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

### -LiteralPath

Указывает путь к XML-файлам. В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

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

Указывает путь к XML-файлам.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Skip

Игнорирует указанное количество объектов, а затем получает оставшиеся объекты. Введите количество объектов, которые необходимо пропустить.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

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

Можно выполнить конвейерную строку, содержащую путь к `Import-Clixml` .

## Выходные данные

### PSObject

`Import-Clixml` Возвращает объекты, которые были десериализованы из хранимых XML-файлов.

## ПРИМЕЧАНИЯ

При указании нескольких значений параметра разделяйте их запятыми. Например, `<parameter-name> <value1>, <value2>`.

## Связанные ссылки

[Export-Clixml](Export-Clixml.md)

[Введение в сериализацию XML](/dotnet/standard/serialization/introducing-xml-serialization)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk) (Безопасное хранение учетных данных на диске)

[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/) (Передача учетных данных в устаревшие системы с помощью PowerShell)


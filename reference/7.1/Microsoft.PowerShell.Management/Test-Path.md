---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: f31b4242d8febd4fdd0e03596d7394ab2990ddbb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226741"
---
# Test-Path

## Краткий обзор
Определяет, все ли элементы пути существуют.

## SYNTAX

### Путь (по умолчанию)

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### LiteralPath

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## DESCRIPTION

`Test-Path`Командлет определяет, существуют ли все элементы пути. Он возвращает значение `$True` , если все элементы существуют и `$False` отсутствуют. Он также может определить, является ли синтаксис пути допустимым, и указывает, ведет ли путь к контейнеру или элементу терминала или листу. Если `Path` является пустой строкой, `$False` возвращается значение. Если `Path` имеет значение `$null` , массив `$null` или пустой массив, возвращается Неустранимая ошибка.

## Примеры

### Пример 1. Проверка пути

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

Эта команда проверяет, существуют ли все элементы в пути, т. е. каталог C:, каталог Documents и Settings и каталог Давидк. Если таковые отсутствуют, командлет возвращает `$False` .
В противном случае она возвращает `$True`.

### Пример 2. Проверка пути к профилю

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

Эти команды проверяют путь к профилю PowerShell.

Первая команда определяет, существуют ли все элементы пути. Вторая команда определяет, правилен ли синтаксис пути. В этом случае путь имеет значение `$False` , но синтаксис правильный `$True` . Эти команды используют `$profile` , автоматически изменяемую переменную, указывающую на расположение профиля, даже если профиль не существует.

Подробнее об автоматических переменных см. в разделе about_Automatic_Variables.

### Пример 3. Проверка наличия файлов, кроме указанного типа

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

Эта команда проверяет наличие в каталоге коммерческих зданий файлов, отличных от файлов DWG.

Команда использует параметр **path** для указания пути. Так как путь содержит пробел, путь заключается в кавычки. Звездочка в конце пути означает содержимое каталога Commercial Building. При использовании длинных путей, например, введите первые несколько букв пути, а затем используйте клавишу TAB для завершения пути.

Команда задает параметр **Exclude** для указания файлов, которые будут пропущены при вычислении.

В этом случае, поскольку каталог содержит только файлы. DWG, результатом будет `$False` .

### Пример 4. Проверка файла

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

Эта команда проверяет, ведет ли путь, хранящийся в `$profile` переменной, в файл. В этом случае, поскольку профиль PowerShell является `.ps1` файлом, командлет возвращает `$True` .

### Пример 5. Проверка путей в реестре

Эти команды используются `Test-Path` с поставщиком реестра PowerShell.

Первая команда проверяет, правильно ли указан путь реестра в разделе реестра **Microsoft. PowerShell** . Если PowerShell установлен правильно, командлет возвращает `$True` .

> [!IMPORTANT]
> `Test-Path` не работает правильно со всеми поставщиками PowerShell. Например, можно использовать `Test-Path` для проверки пути к разделу реестра, но при его использовании для проверки пути к записи реестра он всегда возвращает значение `$False` , даже если имеется запись реестра.

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### Пример 6. Проверка, является ли файл более новым, чем указанная дата

Эта команда использует динамический параметр **неверсан** , чтобы определить, новее ли файл "PowerShell.exe" на компьютере, чем "13 июля, 2009".

Параметр NewerThan работает только на дисках файловой системы.

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### Пример 7. Проверка пути со значением NULL в качестве значения

Ошибка, возвращенная для `null` , массив `null` или пустой массив, является неустранимой ошибкой. Его можно отключить с помощью `-ErrorAction SilentlyContinue` . В следующем примере показаны все случаи, которые возвращают `NullPathNotPermitted` ошибку.

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### Пример 8. Проверка пути с пробелом в качестве значения

Если для параметра указан пробел или пустая строка `-Path` , возвращается **значение false**.
В следующем примере показаны пробелы и пустая строка.

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## PARAMETERS

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell. Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

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

### -Exclude

Указывает элементы, которые пропускает этот командлет. Значение этого параметра определяет параметр **Path**. Введите путь к элементу или шаблон, например. «*.txt». Можно использовать подстановочные знаки.

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

Задает фильтр в формате или на языке поставщика. Значение этого параметра определяет параметр **Path**. Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика. Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов вместо того, чтобы использовать PowerShell для фильтрации объектов после их извлечения.

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

Указывает пути, которые проверяет этот командлет. Значение этого параметра определяет параметр **Path**. Введите путь к элементу или шаблон, например. «*.txt». Можно использовать подстановочные знаки.

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

### -IsValid

Указывает, что этот командлет проверяет синтаксис пути независимо от того, существуют ли элементы пути. Этот командлет возвращает значение, `$True` Если синтаксис пути допустим, и `$False` Если нет.

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

### -LiteralPath

Указывает проверяемый путь. В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не распознаются как подстановочные знаки. Если путь содержит символы, которые могут интерпретироваться в PowerShell как escape-последовательности, необходимо заключить путь в одинарные кавычки, чтобы они не были интерпретированы.

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

### -Неверсан

Укажите время в качестве объекта **DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Олдерсан

Укажите время в качестве объекта **DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает проверяемый путь. Можно использовать подстановочные знаки. Если путь содержит пробелы, заключите его в одинарные кавычки.

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

### -Пастипе

Задает тип последнего элемента в пути. Этот командлет возвращает, `$True` Если элемент имеет указанный тип и `$False` не имеет значение. Допустимые значения для этого параметра:

- Контейнер.
  элемент, содержащий другие элементы, например каталог или раздел реестра.
- Конечного.
  элемент, который не содержит другие элементы, например файл.
- Всеми.
  или контейнер, или конечный элемент.

Определяет, имеет ли конечный элемент пути определенный тип.

> [!CAUTION]
>
> До PowerShell версии 6.1.2, когда параметры **IsValid** и **пастипе** указаны вместе, `Test-Path` командлет игнорирует параметр **пастипе** и проверяет только синтаксическую путь без проверки типа пути.
>
> В соответствии с [#8607 проблемы](https://github.com/PowerShell/PowerShell/issues/8607)исправление этого поведения может быть критическим изменением в будущей версии, где параметры **IsValid** и **пастипе** относятся к отдельным наборам параметров, и поэтому не могут использоваться совместно, избегая этой путаницы.

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.

## Выходные данные

### System.Boolean

Командлет возвращает **логическое** значение.

## ПРИМЕЧАНИЯ

Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell. Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.
Используйте их, как при использовании **dirname** , **нормпас** , **реалпас** , **Join** или других манипуляторов пути.

Объект `Test-Path` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

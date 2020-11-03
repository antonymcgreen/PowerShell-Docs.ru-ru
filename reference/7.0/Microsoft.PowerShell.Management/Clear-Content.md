---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 5a38fd45ff1f645df7004452b5a3c16c6f5cb74a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226241"
---
# Clear-Content

## Краткий обзор
Удаляет содержимое элемента без удаления самого элемента.

## SYNTAX

### Путь (по умолчанию)

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### LiteralPath

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## DESCRIPTION

`Clear-Content`Командлет удаляет содержимое элемента, например удаление текста из файла, но не удаляет элемент.
В результате элемент существует, но является пустым.
Объект `Clear-Content` аналогичен `Clear-Item` , но он работает с элементами с содержимым, а не с элементами со значениями.

## Примеры

### Пример 1. Удаление всего содержимого из каталога

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

Эта команда удаляет все содержимое файлов с именем "init.txt", содержащихся во всех вложенных каталогах каталога SmpUsers.
Сами файлы не удаляются, но становятся пустыми.

### Пример 2. Удаление содержимого всех файлов с подстановочным знаком

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

Эта команда удаляет содержимое всех файлов из текущего каталога с расширением LOG, включая файлы с атрибутом «только для чтения».
Звездочка ( \* ) в пути представляет все элементы в текущем каталоге.
Параметр **Force** делает команду эффективной для файлов только для чтения.
Использование фильтра для ограничения команды файлами с расширением log, а не указанием \* . log в пути делает операцию быстрее.

### Пример 3. Очистка всех данных из потока

В этом примере показано, как `Clear-Content` командлет очищает содержимое из альтернативного потока данных, оставляя поток нетронутым.

Первая команда использует `Get-Content` командлет для получения содержимого зоны. идентификатор потока в файле Copy-Script.ps1, скачанном из Интернета.

Вторая команда использует `Clear-Content` командлет для очистки содержимого.

Третья команда повторяет первую команду. Он проверяет, что содержимое сброшено, но поток остается. Если поток был удален, команда выдаст ошибку.

Для очистки содержимого альтернативного потока данных можно использовать метод, подобный этому. Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета. Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## PARAMETERS

### -Stream

Указывает альтернативный поток данных для содержимого.
Если поток не существует, этот командлет создаст его.
Подстановочные знаки не поддерживаются.

Stream — это динамический параметр, к которому добавляется поставщик FileSystem `Clear-Content` .
Этот параметр работает только на дисках с файловой системой.

`Clear-Content`С помощью командлета можно изменить содержимое зоны. альтернативный поток данных идентификатора.
Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.
Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.

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

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell. Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте команду Invoke-Command.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

Указывает в виде строкового массива строки, которые этот командлет опускает из пути к содержимому.
Значение этого параметра определяет параметр **Path**.
Введите путь к элементу или шаблон, например. «*.txt».
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

### -Filter

Задает фильтр в формате или на языке поставщика.
Значение этого параметра определяет параметр **Path**.
Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.

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

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

Указывает в виде массива строк содержимое, которое очищает этот командлет.
Значение этого параметра определяет параметр **Path**.
Введите путь к элементу или шаблон, например. «*.txt».
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

### -LiteralPath

Задает путь к элементам, содержимое которых требуется удалить.
В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают, что PowerShell не интерпретирует какие-либо символы как escape-последовательности.

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

Задает путь к элементам, содержимое которых требуется удалить.
Разрешено использовать подстановочные знаки.
Пути должны вести к элементам, а не к контейнерам.
Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.
Разрешено использовать подстановочные знаки.
Этот параметр обязателен, но его имя (Path) можно не указывать.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Вы не можете передать объекты в `Clear-Content` .

## Выходные данные

### Нет

Этот командлет не создает никаких объектов.

## ПРИМЕЧАНИЯ

Можно использовать `Clear-Content` с поставщиком файловой системы PowerShell и с другими поставщиками, которые управляют содержимым.
Чтобы очистить элементы, которые не считаются содержимым, например элементы, управляемые сертификатом PowerShell или поставщиками реестра, используйте `Clear-Item` .

`Clear-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.
Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.
Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Add-Content](Add-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[Set-Content](Set-Content.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

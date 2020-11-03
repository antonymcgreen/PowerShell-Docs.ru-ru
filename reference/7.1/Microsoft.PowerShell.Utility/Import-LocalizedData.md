---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: d19279133a42e3aea17f02348e44aec161ba5a23
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239995"
---
# Import-LocalizedData

## Краткий обзор
Импортирует данные, зависящие от языка, в сценарии и функции в зависимости от языка и региональных параметров пользовательского интерфейса, выбранного для операционной системы.

## SYNTAX

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Import-LocalizedData`Командлет динамически извлекает строки из подкаталога, имя которого соответствует языку пользовательского интерфейса, заданному для текущего пользователя операционной системы. Его задачей является включение сценариев для отображения сообщений для пользователей на языке пользовательского интерфейса, выбранного текущим пользователем.

`Import-LocalizedData` импортирует данные из `.psd1` файлов в подкаталогах, зависящих от языка, в каталоге скрипта и сохраняет их в локальной переменной, указанной в команде. Командлет выбирает подкаталог и файл на основе значения `$PSUICulture` автоматической переменной. При использовании локальной переменной в сценарии для отображения сообщения для пользователя сообщение отображается на языке пользовательского интерфейса пользователя.

Параметры можно использовать `Import-LocalizedData` для указания альтернативного языка и региональных параметров пользовательского интерфейса, пути и имени файла, добавления поддерживаемых команд и подавления сообщения об ошибке, которое появляется, если `.psd1` файлы не найдены.

`Import-LocalizedData`Командлет поддерживает инициативы по многоязыковой поддержке сценариев, которая появилась в Windows PowerShell 2,0. Целью этой инициативы является повышение качества обслуживания пользователей по всему миру благодаря упрощению написания сценариев для отображения сообщений для пользователя на языке интерфейса текущего пользователя. Дополнительные сведения об этом и формате `.psd1` файлов см. в разделе [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

## Примеры

### Пример 1. Импорт текстовых строк

В этом примере текстовые строки импортируются в `$Messages` переменную. Она использует значения по умолчанию для всех остальных параметров командлета.

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

Если команда включена в скрипт Archives.ps1 в `C:\Test` каталоге, а значение `$PsUICulture` автоматической переменной — zh-CN, `Import-LocalizedData` импортирует `Archives.psd1` файл в `C:\test\zh-CN` каталог в `$Messages` переменную.

### Пример 2. Импорт локализованных строк данных

Этот пример выполняется в командной строке, а не в сценарии. Он получает локализованные строки данных из файла Test.psd1 и отображает их в командной строке. Поскольку команда не используется в сценарии, параметр **FileName** является обязательным. В команде используется параметр **UICulture** для указания языка и региональных параметров en-US.

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

`Import-LocalizedData` Возвращает хэш-таблицу, содержащую локализованные строки данных.

### Пример 3. Импорт строк языка и региональных параметров пользовательского интерфейса

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

Эта команда импортирует текстовые строки в `$MsgTbl` переменную скрипта.

Он использует параметр **UICulture** , чтобы направить командлет для импорта данных из `Simple.psd1` файла в `ar-SA` подкаталог `C:\Data\Localized` .

### Пример 4. Импорт локализованных данных в скрипт

В этом примере показано, как использовать локализованные данные в простом сценарии.

```powershell
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

В первой части примера показано содержимое `Test.psd1` файла. Он содержит `ConvertFrom-StringData` команду, преобразующую ряд именованных текстовых строк в хэш-таблицу. `Test.psd1`Файл находится в подкаталоге en-US `C:\Test` каталога, который содержит скрипт.

Во второй части примера показано содержимое `Test.ps1` скрипта. Он содержит `Import-LocalizedData` команду, которая импортирует данные из соответствующего `.psd1` файла в `$Messages` переменную и `Write-Host` команду, записывающую одно из сообщений `$Messages` переменной в программу размещения.

В последней части примера выполняется сценарий. Выходные данные показывают, что отображается правильное сообщение для пользователя на языке пользовательского интерфейса, заданном для текущего пользователя операционной системы.

### Пример 5. Замена текстовых строк по умолчанию в скрипте

В этом примере показано, как использовать `Import-LocalizedData` для замены текстовых строк по умолчанию, определенных в разделе данных скрипта.

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

В этом примере раздел данных скрипта TestScript.ps1 содержит `ConvertFrom-StringData` команду, преобразующую содержимое раздела данных в хэш-таблицу и сохраняющую в значении `$UserMessages` переменной.

Скрипт также включает `Import-LocalizedData` команду, которая импортирует хэш-таблицу переведенных текстовых строк из файла TestScript.psd1 в подкаталоге, заданном значением `$PsUICulture` переменной. Если команда находит `.psd1` файл, то она сохраняет переведенные строки из файла в значении той же `$UserMessages` переменной, перезаписывая хэш-таблицу, сохраненную логикой раздела данных.

Третья команда отображает первое сообщение в `$UserMessages` переменной.

Если `Import-LocalizedData` команда находит `.psd1` файл для `$PsUICulture` языка, значение `$UserMessages` переменной содержит переведенные текстовые строки. В случае сбоя команды по какой-либо причине команда отображает текстовые строки по умолчанию, определенные в разделе DATA сценария.

### Пример 6. Отключение сообщений об ошибках, если культура пользовательского интерфейса не найдена

В этом примере показано, как подавлять сообщения об ошибках, отображаемые, когда `Import-LocalizedData` не удается найти каталоги, соответствующие культуре пользовательского интерфейса пользователя, или не удается найти `.psd1` файл для скрипта в этих каталогах.

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

Для отключения сообщений об ошибке можно использовать общий параметр **ErrorAction** со значением SilentlyContinue. Это особенно удобно, если вы предоставили пользовательские сообщения на языке по умолчанию или на резервной, и сообщение об ошибке не требуется.

В этом примере сравниваются два скрипта `Day1.ps1` и Day2.ps1, которые включают `Import-LocalizedData` команду. Скрипты идентичны, за исключением того, что Day2 использует общий параметр **ErrorAction** со значением `SilentlyContinue` .

В примере выходных данных показаны результаты выполнения обоих скриптов, если для языка и региональных параметров пользовательского интерфейса задано значение, `fr-BE` а для этого языка и региональных параметров пользовательского интерфейса нет соответствующих файлов или каталогов. `Day1.ps1` Отображает сообщение об ошибке и вывод на английском языке. `Day2.ps1` просто отображает вывод на английском языке.

## PARAMETERS

### -Баседиректори

Указывает базовый каталог, в котором `.psd1` находятся файлы. По умолчанию используется каталог, в котором расположен сценарий. `Import-LocalizedData` выполняет поиск `.psd1` файла скрипта в подкаталоге конкретного языка базового каталога.

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

### -Биндингвариабле

Задает переменную, в которую импортируются текстовые строки. Введите имя переменной без знака доллара ( `$` ).

В Windows PowerShell 2.0 этот параметр является обязательным. В Windows PowerShell 3.0 этот параметр является необязательным. Если опустить этот параметр, `Import-LocalizedData` возвращает хэш-таблицу текстовых строк. Хэш-таблица передается по конвейеру или отображается в командной строке.

При использовании `Import-LocalizedData` для замены текстовых строк по умолчанию, указанных в разделе данных скрипта, назначьте раздел данных переменной и введите имя переменной раздела данных в значении параметра **биндингвариабле** . Затем при `Import-LocalizedData` сохранении импортированного содержимого в **биндингвариабле** импортированные данные заменят текстовые строки по умолчанию. Если вы не указываете текстовые строки по умолчанию, можно выбрать любое имя переменной.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName

Указывает имя файла данных ( `.psd1)` для импорта). Введите имя файла. Можно указать имя файла, который не включает `.psd1` расширение имени файла, или можно указать имя файла, включая `.psd1` расширение имени файла. Файлы данных должны сохраняться в Юникоде или UTF-8.

Параметр **filename** является обязательным, если `Import-LocalizedData` не используется в скрипте.
В противном случае параметр является необязательным, и значение по умолчанию — базовое имя сценария. С помощью этого параметра можно направить `Import-LocalizedData` Поиск другого `.psd1` файла.

Например, если имя **файла** не указано и сценарий имеет значение FindFiles.ps1, `Import-LocalizedData` выполняется поиск файла данных FindFiles.psd1.

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

### -Суппортедкомманд

Задает командлеты и функции, которые создают только данные.

Используйте этот параметр для включения командлетов и функций, которые вы написали или протестировали. Дополнительные сведения см. в разделе [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Указывает дополнительный язык и региональные параметры пользовательского интерфейса.
Значением по умолчанию является значение `$PsUICulture` автоматической переменной.
Введите язык и региональные параметры пользовательского интерфейса в `<language>-<region>` формате, например `en-US` , `de-DE` или `ar-SA` .

Значение параметра **UICulture** определяет подкаталог, зависящий от языка (в базовом каталоге), из которого `Import-LocalizedData` получает `.psd1` файл для скрипта.

Командлет ищет подкаталог с тем же именем, что и значение параметра **UICulture** `$PsUICulture` , или автоматически изменяемую переменную, например `de-DE` или `ar-SA` . Если не удается найти каталог или каталог не содержит `.psd1` файл для скрипта, он ищет подкаталог с именем кода языка, например de или AR. Если не удается найти подкаталог или `.psd1` файл, команда завершается ошибкой и данные отображаются на языке по умолчанию, указанном в скрипте.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### System.Collections.Hashtable

`Import-LocalizedData` сохраняет хэш-таблицу в переменной, заданной значением параметра **биндингвариабле** .

## ПРИМЕЧАНИЯ

- Прежде чем использовать `Import-LocalizedData` , локализовать пользовательские сообщения. Отформатируйте сообщения для каждого языкового стандарта (язык и региональные параметры пользовательского интерфейса) в хэш-таблице пар "ключ-значение" и сохраните хэш-таблицу в файле с тем же именем, что и у скрипта, и `.psd1` расширения имени файла. Создайте каталог в каталоге script для каждой поддерживаемой культуры пользовательского интерфейса, а затем сохраните `.psd1` файл для каждого языка и региональных параметров пользовательского интерфейса в каталоге с именем языка и региональных параметров пользовательского интерфейса.

  Например, выполните локализацию сообщений для пользователя для языкового стандарта de-DE и форматируйте их в хэш-таблицу.
  Сохраните хэш-таблицу в `<ScriptName>.psd1` файле. Затем создайте `de-DE` подкаталог в каталоге script и сохраните немецкий `<ScriptName\>.psd1` файл в `de-DE` подкаталоге.
  Повторите эту процедуру для каждого поддерживаемого решением языкового стандарта.

- `Import-LocalizedData` выполняет структурированный поиск локализованных сообщений пользователя для скрипта.

  `Import-LocalizedData` начинает поиск в каталоге, где расположен файл скрипта (или значение параметра **баседиректори** ). Затем он ищет в базовом каталоге подкаталог с тем же именем, что и значение `$PsUICulture` переменной (или значение параметра **UICulture** ), например `de-DE` или `ar-SA` . Затем он ищет в этом подкаталоге `.psd1` файл с тем же именем, что и у скрипта (или значение параметра **filename** ).

  Если `Import-LocalizedData` не удается найти подкаталог с именем языка и региональных параметров пользовательского интерфейса, или подкаталог не содержит `.psd1` файл для скрипта, он ищет `.psd1` файл скрипта в подкаталоге с именем кода языка, например de или AR. Если не удается найти подкаталог или `.psd1` файл, команда завершается ошибкой, данные отображаются на языке по умолчанию в скрипте, и отображается сообщение об ошибке, объясняющее, что данные не удалось импортировать. Чтобы отключить сообщение и корректно завершить его работу, используйте общий параметр **ErrorAction** со значением SilentlyContinue.

  Если `Import-LocalizedData` находит подкаталог и `.psd1` файл, он импортирует хэш-таблицу пользовательских сообщений в значение параметра **биндингвариабле** в команде. Затем при отображении сообщения из хэш-таблицы в переменной отображается локализованное сообщение.

  Дополнительные сведения см. в разделе [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).

## Связанные ссылки

[Write-Host](Write-Host.md)

[Import-PowerShellDataFile](Import-PowerShellDataFile.md)


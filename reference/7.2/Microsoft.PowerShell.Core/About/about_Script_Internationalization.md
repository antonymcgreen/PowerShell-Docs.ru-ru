---
description: Описание возможностей интернационализации сценариев, упрощающих выполнение сценариев для вывода сообщений и инструкций пользователям на языке пользовательского интерфейса.
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 283ea6788e76b481c912fc5672350efd2e8bafaa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603974"
---
# <a name="about-script-internationalization"></a>О международной локализации сценариев

## <a name="short-description"></a>Краткое описание
Описание возможностей интернационализации сценариев, упрощающих выполнение сценариев для вывода сообщений и инструкций пользователям на языке пользовательского интерфейса.

## <a name="long-description"></a>Полное описание

Возможности интернационализации сценариев PowerShell позволяют лучше обслуживать пользователей по всему миру за счет отображения справки и сообщений пользователя на языке пользователя.

Функции интернационализации сценариев запрашивают язык и региональные параметры пользовательского интерфейса операционной системы во время выполнения, импортируют соответствующие переведенные текстовые строки и отображают их пользователю. Раздел данных позволяет хранить текстовые строки отдельно от кода, чтобы они были легко идентифицированы и извлечены. Новый командлет, `ConvertFrom-StringData` преобразует текстовые строки в хэш-таблицы, подобные словарям, чтобы упростить перевод.

Для поддержки текста международных справочных сведений PowerShell предоставляет следующие возможности.

- Раздел данных, разделяющий текстовые строки из инструкций кода. Дополнительные сведения о разделе данных см. в статье [about_Data_Sections](about_Data_Sections.md).

- Новые автоматические переменные `$PSCulture` и `$PSUICulture` . `$PSCulture` хранит имя языка пользовательского интерфейса, используемого в системе для таких элементов, как дата, время и валюта. `$PSUICulture`Переменная хранит имя языка пользовательского интерфейса, используемого в системе для элементов пользовательского интерфейса, таких как меню и текстовые строки.

- Командлет, `ConvertFrom-StringData` , который преобразует текстовые строки в хэш-таблицы, подобные словарям, для упрощения перевода. Дополнительные сведения см. в разделе [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).

- Новый тип файла, `.psd1` , который хранит переведенные текстовые строки. `.psd1`Файлы хранятся в подкаталогах, зависящих от языка каталога сценариев.

- Командлет, `Import-LocalizedData` , который импортирует переведенные текстовые строки для указанного языка в скрипт во время выполнения. Этот командлет распознает и импортирует строки на любом языке, поддерживаемом Windows. Дополнительные сведения см. в разделе [Import-локализеддата](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).

### <a name="the-data-section-storing-default-strings"></a>Раздел Data: хранение строк по умолчанию

Используйте раздел данных в скрипте для хранения текстовых строк на языке по умолчанию. Расположите строки в парах "ключ-значение" в строке ниже. Каждая пара "ключ-значение" должна находиться в отдельной строке. При включении комментариев комментарии должны находиться в разных строках.

`ConvertFrom-StringData`Командлет преобразует пары "ключ-значение" в строке ниже в хэш-таблицу, которая хранится в значении переменной раздела данных.

В следующем примере раздел данных `World.ps1` скрипта содержит набор сообщений о состоянии English-United (EN-US) для сценария. `ConvertFrom-StringData`Командлет преобразует строки в хэш-таблицу и сохраняет их в `$msgtable` переменной.

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).

### <a name="psd1-files-storing-translated-strings"></a>Файлы PSD1: хранение переведенных строк

Сохраните сообщения сценария для каждого языка пользовательского интерфейса в отдельных текстовых файлах с тем же именем, что и у скрипта, и `.psd1` расширения имени файла. Храните файлы в подкаталогах каталога script с именами языков и региональных параметров в следующем формате:

`<language>-<region>`

Примеры: de-DE, AR-SA и zh-Ханс

Например, если `World.ps1` Сценарий хранится в `C:\Scripts` каталоге, необходимо создать структуру каталогов файлов, похожую на следующую:

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

Файл в подкаталоге `World.psd1` de-de каталога скрипта может содержать следующую инструкцию:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

Аналогичным образом `World.psd1` файл в подкаталоге AR-SA каталога скрипта может содержать следующую инструкцию:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a>Import-Локализеддата: динамическое извлечение переведенных строк

Чтобы получить строки в языке пользовательского интерфейса текущего пользователя, используйте `Import-LocalizedData` командлет.

`Import-LocalizedData` находит значение `$PSUICulture` автоматической переменной и импортирует содержимое `<script-name>.psd1` файлов в подкаталоге, который соответствует `$PSUICulture` значению. Затем он сохраняет импортированное содержимое в переменной, заданной значением параметра **биндингвариабле** .

```powershell
Import-LocalizedData -BindingVariable msgTable
```

Например, если `Import-LocalizedData` команда отображается в `C:\Scripts\World.ps1` скрипте, а значение `$PSUICulture` равно "AR-SA", `Import-LocalizedData` находит следующий файл:

`C:\Scripts\ar-SA\World.psd1`

Затем он импортирует арабские текстовые строки из файла в `$msgTable` переменную, заменяя все строки по умолчанию, которые могут быть определены в разделе данных `World.ps1` скрипта.

В результате, когда скрипт использует `$msgTable` переменную для отображения пользовательских сообщений, сообщения отображаются на арабском языке.

Например, следующий сценарий отображает сообщение "введите имя пользователя" на арабском языке:

```powershell
if (!($username)) { $msgTable.promptMsg }
```

Если `Import-LocalizedData` не удается найти `.psd1` файл, соответствующий значению `$PSUIculture` , значение `$msgTable` не заменяется, а вызов `$msgTable.promptMsg` отображает резервные строки en-US.

## <a name="examples"></a>Примеры

В этом примере показано, как в скрипте используются возможности интернационализации скриптов для отображения дня недели пользователям на языке, установленном на компьютере.

Ниже приведен полный список Sample1.ps1 файла скрипта.

Сценарий начинается с раздела данных с именем Day ($Day), который содержит `ConvertFrom-StringData` команду. Выражение, отправленное в, `ConvertFrom-StringData` — это строка, содержащая названия дней в языке и региональных параметрах пользовательского интерфейса по умолчанию en-US в парах "ключ-значение". `ConvertFrom-StringData`Командлет преобразует пары "ключ-значение" в строке ниже в хэш-таблицу и сохраняет ее в значении `$Day` переменной.

`Import-LocalizedData`Команда импортирует содержимое `.psd1` файла в каталоге, который соответствует значению `$PSUICulture` автоматической переменной, и сохраняет его в `$Day` переменной, заменяя значения `$Day` , определенные в разделе данных.

Остальные команды загружают строки в массив и отображают их.

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

`.psd1`Файлы, поддерживающие скрипт, сохраняются в подкаталогах каталога script с именами, соответствующими `$PSUICulture` значениям.

Ниже приведен полный список `.\de-DE\sample1.psd1` .

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

В результате при запуске Sample.ps1 в системе, для которой значение `$PSUICulture` равно de-de, выходные данные скрипта будут:

```Output
Heute ist Freitag
```

## <a name="see-also"></a>См. также

- [about_Data_Sections](about_Data_Sections.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)


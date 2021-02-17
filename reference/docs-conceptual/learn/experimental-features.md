---
ms.date: 12/14/2020
title: Использование экспериментальных функций в PowerShell
description: Список доступных в настоящее время экспериментальных функций и их использование.
ms.openlocfilehash: 556ae8d877b670b119b7b5b958a52488aad16241
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500129"
---
# <a name="using-experimental-features-in-powershell"></a>Использование экспериментальных функций в PowerShell

Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.

Экспериментальной функцией называется та, которая находится на этапе проектирования. Эта функция доступна пользователям для тестирования и предоставления отзывов о ней. Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими.

> [!CAUTION]
> Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы. Экспериментальные функции официально не поддерживаются. Тем не менее мы будем признательны вам за любые отзывы и отчеты об ошибках. Сообщить о проблеме можно в [исходном репозитории GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).

Дополнительные сведения о включении или отключении этих функций см. в статье [Экспериментальные функции](/powershell/module/microsoft.powershell.core/about/about_experimental_features).

## <a name="available-features"></a>Доступные функции

В этой статье описываются доступные экспериментальные функции и сведения об их использовании.

|                            Имя                            |   6.2   |   7.0   |   7.1   |   7.2   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| PSTempDrive (основная фаза в PS 7.0 и выше)                        | &check; |         |         |         |
| PSUseAbbreviationExpansion (основная фаза в PS 7.0 и выше)         | &check; |         |         |         |
| PSNullConditionalOperators (основная функция в версии PS 7.1 и более поздней)         |         | &check; |         |         |
| PSUnixFileStat (только не на базе Windows, общедоступная функция в PS 7.1 и выше)  |         | &check; |         |         |
| PSCommandNotFoundSuggestion                                | &check; | &check; | &check; | &check; |
| PSImplicitRemotingBatching                                 | &check; | &check; | &check; | &check; |
| Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace |         | &check; | &check; | &check; |
| PSDesiredStateConfiguration.InvokeDscResource              |         | &check; | &check; | &check; |
| PSNativePSPathResolution                                   |         |         | &check; | &check; |
| PSCultureInvariantReplaceOperator                          |         |         | &check; | &check; |
| PSNotApplyErrorActionToStderr                              |         |         | &check; | &check; |
| PSSubsystemPluginModel                                     |         |         | &check; | &check; |
| PSAnsiProgress                                             |         |         |         | &check; |
| PSAnsiRendering                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a>Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace

В PowerShell 7.0 эксперимент включает параметр **BreakAll** в командлетах `Debug-Runspace` и `Debug-Job`, чтобы пользователи могли решить, будет ли работа PowerShell в текущем расположении немедленно прервана при подключении отладчика.

В PowerShell 7.1 этот эксперимент также добавляет параметр **Runspace** к командлетам `*-PSBreakpoint`.

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

Параметр **Runspace** указывает объекту **Runspace** взаимодействовать с точками останова в указанном пространстве выполнения.

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

В этом примере задание запускается с точкой останова, для которой настроена прерывание при выполнении `Set-PSBreakPoint`. Пространство выполнения хранится в переменной и передается команде `Get-PSBreakPoint` с параметром **Runspace**. Затем вы можете просмотреть точку останова в переменной `$breakpoint`.

## <a name="psansirendering"></a>PSAnsiRendering

Эта экспериментальная функция добавлена в PowerShell 7.2. Она позволяет изменять способ вывода текста обработчиком PowerShell и добавлять автоматическую переменную `$PSStyle` для управления отрисовкой строковых выходных данных в ANSI.

```powershell
PS> $PSStyle

Name            MemberType Definition
----            ---------- ----------
Reset           Property   string AttributesOff {get;set;}
Background      Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;set;}
Blink           Property   string Blink {get;set;}
BlinkOff        Property   string BlinkOff {get;set;}
Bold            Property   string Bold {get;set;}
BoldOff         Property   string BoldOff {get;set;}
Foreground      Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;set;}
Formatting      Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;set;}
Hidden          Property   string Hidden {get;set;}
HiddenOff       Property   string HiddenOff {get;set;}
OutputRendering Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Reverse         Property   string Reverse {get;set;}
ReverseOff      Property   string ReverseOff {get;set;}
Italic          Property   string Standout {get;set;}
ItalicOff       Property   string StandoutOff {get;set;}
Underline       Property   string Underlined {get;set;}
Underline Off   Property   string UnderlinedOff {get;set;}
```

Базовые элементы возвращают строки escape-последовательностей ANSI, сопоставленные с их именами. Значения можно настраивать.

Дополнительные сведения см. в статье [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

> [!NOTE]
> Разработчики C# могут получать доступ к `PSStyle` как к одиночному элементу. Использование будет выглядеть так:
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> `PSStyle` существует в пространстве имен System.Management.Automation.

Наряду с доступом к `$PSStyle`, появляются изменения в обработчике PowerShell. Система форматирования PowerShell обновляется в соответствии с `$PSStyle.OutputRendering`.

- Добавляется тип `StringDecorated` для обработки экранированных строк ANSI.
- В возвращаемые данные добавляется логическое свойство `string IsDecorated`, если строка содержит escape-последовательности ANSI при наличии в ней ESC или C1 CSI.
- Свойство `Length` возвращает _только_ длину текста без escape-последовательностей ANSI.
- Метод `StringDecorated Substring(int contentLength)` возвращает подстроку, начинающуюся с индекса 0 вплоть до длины содержимого, которое не является частью escape-последовательностей ANSI. Это необходимо для усечения строк и сохранения escape-последовательностей ANSI, которые не занимают место печатаемых символов, при форматировании таблицы.
- Метод `string ToString()` остается без изменений и возвращает версию строки в виде открытого текста.
- Метод `string ToString(bool Ansi)` возвращает необработанную встроенную строку ANSI, если параметр `Ansi` имеет значение true. В противном случае возвращается версия с открытым текстом с удаленными escape-последовательностями ANSI.

## <a name="psansiprogress"></a>PSAnsiProgress

Эта экспериментальная функция добавлена в PowerShell 7.2. Эта функция добавляет элемент `$PSStyle.Progress` и позволяет управлять рендерингом панели просмотра хода выполнения.

- `$PSStyle.Progress.Style` — строка ANSI, задающая стиль рендеринга.
- `$PSStyle.Progress.MaxWidth` — задает максимальную ширину представления. Задайте для ширины консоли значение `0`.
  Значение по умолчанию — `120`
- `$PSStyle.Progress.View` — перечисление со значениями `Minimal` и `Classic`. `Classic` — существующий рендеринг без изменений. `Minimal` — минимальный рендеринг одной строки. Значение по умолчанию — `Minimal`.

В следующем примере стиль рендеринга обновляется для отображения минимального индикатора хода выполнения.

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> Для использования этой функции необходимо включить экспериментальную функцию **PSAnsiRendering**.

## <a name="pscommandnotfoundsuggestion"></a>PSCommandNotFoundSuggestion

Рекомендует потенциальные команды на основе поиска нечетких соответствий после **CommandNotFoundException**.

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a>PSCultureInvariantReplaceOperator

Когда левый операнд в инструкции оператора `-replace` не является строкой, он преобразуется в строку.

Когда эта функция отключена, оператор `-replace` выполняет преобразование строк с учетом языка и региональных параметров.
Например, если для языка и региональных параметров настроен французский язык (fr), значение `1.2` преобразуется в строку `1,2`.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

С включенной функцией:

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a>PSDesiredStateConfiguration.InvokeDscResource

Эта функция включает компиляцию в MOF в системах, отличных от Windows, и позволяет использовать `Invoke-DSCResource` без LCM.

## <a name="psimplicitremotingbatching"></a>PSImplicitRemotingBatching

Эта функция проверяет команду, введенную в оболочке. Если все команды являются командами прокси-сервера неявного удаленного взаимодействия, которые образуют простой конвейер, то эти команды объединяются и вызываются как один удаленный конвейер.

Пример

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

Как показано выше, при включенной функции пакетирования все три команды прокси-сервера неявного удаленного доступа (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) выполняются в удаленном сеансе, а результат из конвейера — это единственные данные, которые возвращаются клиенту. Это приводит к уменьшению объема данных, передаваемых между клиентом и удаленным сеансом. Это также уменьшает количество процессов сериализации и десериализации объекта.

## <a name="psnativepspathresolution"></a>PSNativePSPathResolution

Если путь PSDrive, использующий поставщик FileSystem, передается собственной команде, то и разрешенный путь к файлу передается собственной команде. Это означает, что такая команда, как `code temp:/test.txt`, сейчас работает должным образом.

Кроме того, если в Windows путь начинается с `~`, он преобразуется в полный путь и передается собственной команде. В обоих случаях путь нормализуется к разделителям каталогов для соответствующей операционной системы.

- Если путь не является PSDrive или `~` (в Windows), то нормализация пути не происходит.
- Если путь указан в одинарных кавычках, он не разрешается и рассматривается в качестве литерала.

## <a name="psnotapplyerroractiontostderr"></a>PSNotApplyErrorActionToStderr

Если эта экспериментальная функция включена, записи ошибок, перенаправленные из собственных команд (например, при использовании операторов перенаправления, таких как `2>&1`), не записываются в переменную `$Error`, а привилегированная переменная `$ErrorActionPreference` не влияет на перенаправленные выходные данные.

Многие собственные команды выполняют запись в `stderr` в качестве альтернативного потока для сохранения дополнительных сведений. Такое поведение может запутать пользователя при просмотре ошибок или же дополнительная выходная информация может быть утрачена для пользователя, если для `$ErrorActionPreference` настроено состояние, блокирующее вывод данных.

Если собственная команда имеет ненулевой код завершения, для `$?` задается значение `$false`. Если код завершения равен нулю, для `$?` задается значение `$true`.

## <a name="psnullconditionaloperators"></a>PSNullConditionalOperators

Эта функция вводит новые операторы для операторов доступа к членам, определяемого условием NULL: `?.` и `?[]`. Операторы доступа к элементам со значением NULL могут использоваться для скалярных типов и типов массивов. Возвращает значение члена, к которому был получен доступ, если переменная не равна значению NULL. Если значение переменной равно значению NULL, тогда возвращается NULL.

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

Доступ к свойству `propname` и его значение возвращаются, только если `$x` не равно NULL. Аналогичным образом индексатор используется, только если `$x` не равно NULL. Если `$x` равно NULL, то возвращается значение NULL.

Операторы `?.` и `?[]` являются операторами доступа к членам и не допускают пробела между именем переменной и оператором.

Так как PowerShell допускает `?` в качестве части имени переменной, когда операторы используются без пробела между именем переменной и оператором, требуется устранение неоднозначности. Чтобы устранить неоднозначность, переменные должны заключить имя переменной в скобки `{}`, например: `${x?}?.propertyName` или `${y}?[0]`.

> [!NOTE]
> Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7.1 и более поздних версиях.

## <a name="pstempdrive"></a>PSTempDrive

Создает `TEMP:` PSDrive, сопоставленный с временным каталогом пользователя.

> [!NOTE]
> Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.

## <a name="psunixfilestat"></a>PSUnixFileStat

Эта функция обеспечивает новые возможности для включения данных из API функции **stat** Unix в выходные данные поставщика файловой системы, чтобы упростить более похожий на Unix список файлов. Она добавляет новое свойство примечания в поставщик файловой системы с именем **UnixStat**, которое включает в себя общее выражение API `stat(2)` из базовой системы типов Unix.

Результат `Get-ChildItem` должен выглядеть следующим образом.

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7.1 и более поздних версиях.

## <a name="psuseabbreviationexpansion"></a>PSUseAbbreviationExpansion

Эта функция позволяет выполнять заполнение сокращенных командлетов и функций нажатием клавиши TAB:

Пример:

- `i-psdf<tab>` возвращает `Import-PowerShellDataFile`.
- `u-akvmssdr<tab>` возвращает `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`

Эта функция работает только для заполнения нажатием клавиши TAB (интерактивное использование), поэтому `i-psdf` — недопустимое имя командлета в скрипте.

> [!NOTE]
> Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.

## <a name="pssubsystempluginmodel"></a>PSSubsystemPluginModel

Эта функция включает модель подключаемого модуля подсистемы в PowerShell. Эта функция позволяет разделять компоненты `System.Management.Automation.dll` в отдельные подсистемы, находящиеся в их собственной сборке. Такое разделение сокращает объем дискового пространства ядра PowerShell и позволяет этим компонентам стать необязательными для минимальной установки PowerShell.

В настоящее время поддерживается только подсистема **CommandPredictor**. Эта подсистема используется вместе с модулем PSReadLine для предоставления настраиваемых подключаемых модулей прогнозирования. В будущем **задание**, **CommandCompleter**, **удаленное взаимодействие** и другие компоненты можно будет разделить на сборки подсистемы за пределами `System.Management.Automation.dll`.

Экспериментальная функция содержит новый командлет [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem). Этот командлет доступен, только если функция включена. Этот командлет возвращает сведения о подсистемах, доступных в системе.

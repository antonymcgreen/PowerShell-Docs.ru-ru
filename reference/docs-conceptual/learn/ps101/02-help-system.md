---
title: Справочная система
description: Овладение справочной системой — важное условие для успешной работы с PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 8325a32ad8ec137781300e9d46cab52705f0805a
ms.sourcegitcommit: eaac7af89171379df2e20464ebee9fc7e7d7674a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89493663"
---
# <a name="chapter-2---the-help-system"></a>Глава 2. Справочная система

Двум группам ИТ-специалистов предложили выполнить письменный тест без доступа к компьютеру на определение уровня их квалификации с помощью PowerShell. Начинающие пользователи PowerShell были определены в одну группу, опытные пользователи — в другую.
На основе полученных результатов теста уровень квалификации между двумя группами почти не отличался. Обе группы получили второй тест, подобный первому. На этот раз пользователям был предоставлен доступ к компьютеру с помощью PowerShell без доступа к Интернету. Результаты второго теста показали большое различие в уровне квалификации между двумя группами. Опытные пользователи не всегда знают ответы, но они знают, как их найти.

Чем отличались результаты первого и второго тестов между двумя группами?

Результаты тестов были разными потому, что опытные пользователи не запоминают, как использовать тысячи команд в PowerShell, а эффективно умеют пользоваться справочной системой PowerShell.
Это позволяет им при необходимости находить нужные команды и использовать их.

Я слышал, как автор PowerShell Джеффри Сновер рассказывал подобную историю несколько раз.

Овладение справочной системой — важное условие для успешной работы с PowerShell.

## <a name="discoverability"></a>Возможность обнаружения

Скомпилированные команды в PowerShell называются командлетами. В оригинале слово cmdlet произносится полностью: "командлет". Имена командлетов соответствуют форме отдельных команд "глагол — существительное", что позволяет легко их находить. Например, командлет `Get-Process` определяет выполняемые процессы, а командлет `Get-Service` получает список служб и их состояний. В PowerShell существуют другие типы команд, например псевдонимы и функции, которые будут рассмотрены далее в этом пособии. Команда PowerShell — это универсальное понятие, которое часто используется для ссылки на любой тип команды в PowerShell, независимо от того, является ли он командлетом, функцией или псевдонимом.

## <a name="the-three-core-cmdlets-in-powershell"></a>Три основных командлета в PowerShell

- `Get-Command`
- `Get-Help`
- `Get-Member` (рассматривается в главе 3)

Вопрос, который мне часто задают: как вы различаете команды в PowerShell? Для определения команд можно использовать командлеты `Get-Command` и `Get-Help`.

## <a name="get-help"></a>Get-Help

`Get-Help` — это многоцелевая команда. `Get-Help` помогает научиться использовать найденные команды. `Get-Help` также можно использовать для поиска команд, но, по сравнению с `Get-Command`, другим, менее прямым способом.

Если для поиска команд используется `Get-Help`, сначала выполняется поиск совпадений с подстановочными знаками имен команд на основе предоставленных входных данных. Если командлет не находит совпадение, выполняется поиск по самим разделам справки, и, если совпадений не найдено, ошибка возвращается. Вопреки распространенному мнению, `Get-Help` можно использовать для поиска команд, не содержащих разделов справки.

Первое, что нужно знать о справочной системе PowerShell, — как использовать командлет `Get-Help`. Следующая команда позволяет вывести раздел справки для `Get-Help`.

```powershell
Get-Help -Name Get-Help
```

```Output
Do you want to run Update-Help?
The Update-Help cmdlet downloads the most current Help files for Windows PowerShell
modules, and installs them on your computer. For more information about the Update-Help
cmdlet, see http://go.microsoft.com/fwlink/?LinkId=210614.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

Начиная с PowerShell версии 3, справка PowerShell не поставляется вместе с операционной системой. При первом запуске `Get-Help` для команды выводится предыдущее сообщение. Если вместо командлета `Get-Help` используется функция `help` или псевдоним `man`, этот запрос не появится.

При согласии нажатием клавиши <kbd>Y</kbd> запускается командлет `Update-Help`, который по умолчанию требует доступа к Интернету. `Y` можно указать в верхнем или нижнем регистре.

После загрузки справки и завершения обновления для указанной команды будет возвращен раздел справки.

```powershell
Get-Help -Name Get-Help
```

Попробуйте выполнить этот пример на компьютере, просмотрите выходные данные и запишите, как группируются сведения.

- NAME
- Краткий обзор
- SYNTAX
- DESCRIPTION
- Связанные ссылки
- ПРИМЕЧАНИЯ

Как вы видите, разделы справки могут содержать большой объем информации, причем это даже не весь раздел справки.

Хотя это и не относится к PowerShell, параметр — это способ предоставления команде входных данных. `Get-Help` имеет много параметров, которые можно указать для возврата всего раздела справки или его подмножества.

В разделе синтаксиса раздела справки, который отображается в предыдущем наборе результатов, приводится список всех параметров `Get-Help`. На первый взгляд кажется, что одинаковые параметры приведены шесть раз по-разному. Каждый из этих блоков раздела синтаксиса представляет собой набор параметров. Это означает, что командлет `Get-Help` имеет шесть разных наборов параметров. Если посмотреть более внимательно, можно заметить, что в каждом наборе по крайней мере один параметр отличается.

Эти наборы параметров являются взаимоисключающими. После использования уникального параметра, который существует только в одном из наборов, можно использовать только те параметры, которые содержатся в этом наборе. Например, не удалось одновременно указать параметры **Full** и **Detailed**, так как они находятся в разных наборах.

Каждый из следующих параметров находится в разных наборах.

- Полное
- Подробно
- Примеры
- Справка в Интернете
- Параметр
- ShowWindow

Любые непонятные синтаксические конструкции в разделе синтаксиса, например квадратные и угловые скобки, имеют определенное значение и будут рассматриваться в приложении А к этому пособию. При всей важности непонятных синтаксических конструкций их обычно трудно запоминать тем, кто не работал с PowerShell и не использует их ежедневно.

Дополнительные сведения о том, как распознать непонятные синтаксические конструкции, см. в [Приложение А][].

Для начинающих пользователей существует простой способ вычислять аналогичную информацию, кроме обычного языка.

При указании параметра **Full** в значении `Get-Help` возвращается весь раздел справки.

```powershell
Get-Help -Name Get-Help -Full
```

Попробуйте выполнить этот пример на компьютере, просмотрите выходные данные и запишите, как группируются сведения.

- NAME
- Краткий обзор
- SYNTAX
- DESCRIPTION
- PARAMETERS
- Входные данные
- Выходные данные
- ПРИМЕЧАНИЯ
- Примеры
- Связанные ссылки

Заметьте, что использование параметра **Full** привело к возврату нескольких дополнительных разделов, один из которых представляет собой раздел ПАРАМЕТРОВ, содержащий больше данных, чем раздел СИНТАКСИСА с непонятными конструкциями.

Параметр **Full** является параметром-переключателем, то есть тем, который не требует указывать значение. Если параметр-переключатель указывается, его значение будет верным, а если не указывается, значение будет неверным.

Работая над этой главой в консоли PowerShell, вы заметили, что предыдущая команда для вывода полного раздела справки для `Get-Help` показалась на экране очень быстро и ее нельзя было прочитать. Для этого существует более эффективный способ.

`Help` — это функция, передающая `Get-Help` функции с именем `more`, которая является оболочкой для исполняемого файла `more.com` в Windows. В консоли PowerShell командлет `help` открывает одну страницу справки за один раз. В интегрированной среде сценариев этот командлет работает так же, как `Get-Help`. Я рекомендую использовать функцию `help` вместо командлета `Get-Help`, так как она удобнее и меньше по длине.

При этом вводить меньше символов не всегда оказывается полезным. Сохраняя команды в виде сценария или отправляя их другим пользователям, обязательно используйте полные имена командлетов и параметров. Полные имена являются самодокументируемыми, поэтому их легче распознавать. Всегда помните о том, кому придется читать и распознавать ваши команды. Этим человеком можете оказаться вы. Ваши сотрудники и вы сами будете за это благодарны.

Попробуйте выполнить следующие команды в консоли PowerShell на компьютере с Windows 10 в лабораторной среде.

```powershell
Get-Help -Name Get-Help -Full
help -Name Get-Help -Full
help Get-Help -Full
```

Появились ли различия в выходных данных приведенных выше команд после их запуска на компьютере с Windows 10 в лабораторной среде?

Кроме последних двух параметров, которые возвращают результаты по одной странице за один раз, эти выходные данные ничем не отличаются.
<kbd>ПРОБЕЛ</kbd> используется для вывода следующей страницы содержимого с помощью функции `Help`, а <kbd>Ctrl</kbd>+<kbd>C</kbd> отменяет команды, выполняемые в консоли PowerShell.

В первом примере используется командлет `Get-Help`, во втором — функция `Help`, в третьем параметр **Name** исключается с помощью функции `Help`. **Name** является позиционным параметром и используется в этом примере позиционно. То есть это значение можно указать без имени параметра, если само это значение указано в правильном положении. Как узнать, в каком положении указывать значение? Свериться со справкой, как показано в следующем примере.

```powershell
help Get-Help -Parameter Name
```

```Output
-Name <String>
    Gets help about the specified command or concept. Enter the name of a cmdlet, function,
    provider, script, or workflow, such as Get-Member, a conceptual article name, such as
    about_Objects, or an alias, such as ls. Wildcard characters are permitted in cmdlet and
    provider names, but you can't use wildcard characters to find the names of function help and
    script help articles.

    To get help for a script that isn't located in a path that's listed in the $env:Path
    environment variable, type the script's path and file name.

    If you enter the exact name of a help article, Get-Help displays the article contents.

    If you enter a word or word pattern that appears in several help article titles, Get-Help
    displays a list of the matching titles.

    If you enter a word that doesn't match any help article titles, Get-Help displays a list of
    articles that include that word in their contents.

    The names of conceptual articles, such as about_Objects, must be entered in English, even in
    non-English versions of PowerShell.

    Required?                    false
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  true
```

Заметьте, что в предыдущем примере параметр **Parameter** использовался вместе с функцией справки только для того, чтобы вернуть данные из раздела справки для параметра **Name**. Так намного точнее, чем пытаться вручную проверять то, что напоминает раздел справки в сто страниц.

На основе полученных результатов вы увидите, что параметр **Name** является позиционным и его нужно указать в нулевом положении (первое положение), если он используется позиционно. Если указывается имя параметра, порядок указания параметров не имеет значения.

Еще одна важная деталь: в параметре **Name** значение типа данных должно быть указано одной строкой, которая обозначается `<String>`. Если допускается несколько строк, тип данных будет приведен как `<String[]>`.

Может быть так, что вам не нужно выводить для команды весь раздел справки. Помимо параметра **Full**, существуют другие параметры, которые можно указать с помощью `Get-Help` или `Help`. Попробуйте выполнить следующие команды на компьютере с Windows 10 в лабораторной среде.

```powershell
Get-Help -Name Get-Command -Full
Get-Help -Name Get-Command -Detailed
Get-Help -Name Get-Command -Examples
Get-Help -Name Get-Command -Online
Get-Help -Name Get-Command -Parameter Noun
Get-Help -Name Get-Command -ShowWindow
```

Как правило, вместе с `help <command name>` я использую параметр **Full** или **Online**. Если мне нужно посмотреть только примеры, я использую параметр **Examples**, а если мне нужно получить только конкретный параметр, я использую параметр **Parameter**. Параметр **ShowWindow** открывает раздел справки в отдельном окне с возможностью поиска, которое можно открыть на другом мониторе, если их у вас несколько. Я стараюсь не использовать параметр **ShowWindow**, потому что он содержит всем известную ошибку, при которой не выводится весь раздел справки.

Если нужно открыть справку в отдельном окне, рекомендую использовать параметры **Online** или **Full** и передать результаты в `Out-GridView`, как показано в следующем примере.

```powershell
help Get-Command -Full | Out-GridView
```

Для использования командлета `Out-GridView` и параметра **ShowWindow** командлета `Get-Help` требуется операционная система с графическим интерфейсом пользователя (GUI). Они выводят сообщение об ошибке при попытке использовать любой из них в Windows Server, который установлен с помощью варианта установки Server Core (без GUI).

Чтобы использовать `Get-Help` для поиска команд, используйте подстановочный знак звездочки (`*`) вместе с параметром **Name**. Укажите термин, в котором выполняется поиск команд, в качестве значения параметра **Name**, как показано в следующем примере.

```powershell
help *process*
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an intera...
Get-PSHostProcessInfo             Cmdlet    Microsoft.PowerShell.Core
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-AppvVirtualProcess            Function  AppvClient                ...
Start-AppvVirtualProcess          Function  AppvClient                ...
```

В предыдущем примере подстановочные знаки `*` добавлять необязательно, без них результат будет одинаковым. `Get-Help` автоматически добавляет подстановочные знаки в фоновом режиме.

```powershell
help process
```

Предыдущая команда выдает те же результаты, что и при указании подстановочного знака `*` при каждом завершении процесса.

Я предпочитаю добавлять подстановочные знаки, так как этот вариант всегда работает стабильно. В остальных случаях именно эти знаки, а не какие-либо другие необходимо использовать в определенных сценариях. Если добавить подстановочный знак в середину значения, он больше не будет к нему автоматически добавляться в фоновом режиме.

```powershell
help pr*cess
```

Эта команда не возвращает результаты, если подстановочный знак `*` добавляется в начало, конец или в начало и конец командлета `pr*cess`.

Если указанное значение начинается с тире, создается ошибка, так как PowerShell интерпретирует его как имя параметра, а имени параметра для командлета `Get-Help` не существует.

```powershell
help -process
```

При попытке найти команды, которые заканчиваются на `-process`, нужно в начало значения добавить только подстановочный знак `*`.

```powershell
help *-process
```

При поиске команд PowerShell с помощью `Get-Help` нужно указывать менее точные параметры поиска.

При предыдущем поиске командлета `process` были найдены только те команды, которые содержали в имени `process` и возвращали только эти результаты. Если командлет `Get-Help` будет использоваться для поиска `processes`, он не найдет совпадений для имен команд, поэтому будет выполнять поиск каждого раздела справки в PowerShell в системе и возвращать все найденные совпадения. Это приведет к возврату большого количества результатов.

```powershell
Get-Help processes
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Disconnect-PSSession              Cmdlet    Microsoft.PowerShell.Core Disconnects from...
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an oper...
Get-PSSessionConfiguration        Cmdlet    Microsoft.PowerShell.Core Gets the registe...
New-PSTransportOption             Cmdlet    Microsoft.PowerShell.Core Creates an objec...
Out-Host                          Cmdlet    Microsoft.PowerShell.Core Sends output to ...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects ...
Clear-Variable                    Cmdlet    Microsoft.PowerShell.U... Deletes the valu...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two set...
Convert-String                    Cmdlet    Microsoft.PowerShell.U... Formats a string...
ConvertFrom-Csv                   Cmdlet    Microsoft.PowerShell.U... Converts object ...
ConvertTo-Html                    Cmdlet    Microsoft.PowerShell.U... Converts Microso...
ConvertTo-Xml                     Cmdlet    Microsoft.PowerShell.U... Creates an XML-b...
Debug-Runspace                    Cmdlet    Microsoft.PowerShell.U... Starts an intera...
Export-Csv                        Cmdlet    Microsoft.PowerShell.U... Converts objects...
Export-FormatData                 Cmdlet    Microsoft.PowerShell.U... Saves formatting...
Format-List                       Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Format-Table                      Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Get-Random                        Cmdlet    Microsoft.PowerShell.U... Gets a random nu...
Get-Unique                        Cmdlet    Microsoft.PowerShell.U... Returns unique i...
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects t...
Import-Clixml                     Cmdlet    Microsoft.PowerShell.U... Imports a CLIXML...
Import-Csv                        Cmdlet    Microsoft.PowerShell.U... Creates table-li...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the n...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Out-GridView                      Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects ...
Set-Variable                      Cmdlet    Microsoft.PowerShell.U... Sets the value o...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by...
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command ou...
Trace-Command                     Cmdlet    Microsoft.PowerShell.U... Configures and s...
Write-Output                      Cmdlet    Microsoft.PowerShell.U... Sends the specif...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances o...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-Counter                       Cmdlet    Microsoft.PowerShell.D... Gets performance...
Invoke-WSManAction                Cmdlet    Microsoft.WSMan.Manage... Invokes an actio...
Remove-WSManInstance              Cmdlet    Microsoft.WSMan.Manage... Deletes a manage...
Get-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Displays managem...
New-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Creates a new in...
Set-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Modifies the man...
about_Arithmetic_Operators        HelpFile                            Describes the op...
about_Arrays                      HelpFile                            Describes arrays...
about_Debuggers                   HelpFile                            Describes the Wi...
about_Execution_Policies          HelpFile                            Describes the Wi...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Foreach                     HelpFile                            Describes a lang...
about_Functions                   HelpFile                            Describes how to...
about_Language_Keywords           HelpFile                            Describes the ke...
about_Methods                     HelpFile                            Describes how to...
about_Objects                     HelpFile                            Provides essenti...
about_Parallel                    HelpFile                            Describes the Pa...
about_Pipelines                   HelpFile                            Combining comman...
about_Preference_Variables        HelpFile                            Variables that c...
about_Remote                      HelpFile                            Describes how to...
about_Remote_Output               HelpFile                            Describes how to...
about_Sequence                    HelpFile                            Describes the Se...
about_Session_Configuration_Files HelpFile                            Describes sessio...
about_Variables                   HelpFile                            Describes how va...
about_Windows_PowerShell_5.0      HelpFile                            Describes new fe...
about_WQL                         HelpFile                            Describes WMI Qu...
about_WS-Management_Cmdlets       HelpFile                            Provides an over...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Parallel                    HelpFile                            Describes the Pa...
about_Sequence                    HelpFile                            Describes the Se...
```

С помощью `Help` для поиска `process` вернулось 10 результатов, а для поиска `processes` — 68. Если найден только один результат, вместо списка команд будет отображаться раздел справки.

```powershell
get-help *hotfix*
```

```Output
NAME
    Get-HotFix

SYNOPSIS
    Gets the hotfixes that have been applied to the local and remote computers.


SYNTAX
    Get-HotFix [-ComputerName <String[]>] [-Credential <PSCredential>] [-Description
    <String[]>] [<CommonParameters>]

    Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential
    <PSCredential>] [<CommonParameters>]


DESCRIPTION
    The Get-Hotfix cmdlet gets hotfixes (also called updates) that have been installed
    on either the local computer (or on specified remote computers) by Windows Update,
    Microsoft Update, or Windows Server Update Services; the cmdlet also gets hotfixes
    or updates that have been installed manually by users.


RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821586
    Win32_QuickFixEngineering http://go.microsoft.com/fwlink/?LinkID=145071
    Get-ComputerRestorePoint
    Add-Content

REMARKS
    To see the examples, type: "get-help Get-HotFix -examples".
    For more information, type: "get-help Get-HotFix -detailed".
    For technical information, type: "get-help Get-HotFix -full".
    For online help, type: "get-help Get-HotFix -online"
```

Теперь давайте развеем миф о том, что `Help` в PowerShell может находить только команды, содержащие разделы справки.

```powershell
help *more*
```

```Output
NAME
    more

SYNTAX
    more [[-paths] <string[]>]


ALIASES
    None


REMARKS
    None
```

Заметьте, в предыдущем примере `more` не содержит раздела справки, но системе `Help` в PowerShell удалось ее найти. Система нашла только одно совпадение и вернула основные сведения о синтаксисе, которые будут отображаться, если команда не содержит раздела справки.

PowerShell содержит множество концептуальных разделов справки ("О программе"). Следующая команда используется для возврата списка всех разделов **О программе** в системе.

```powershell
help About_*
```

При ограничении результатов одним из разделов справки "О программе" вместо возврата списка отображается действительный раздел.

```powershell
help about_Updatable_Help
```

Для отображения разделов справки **О программе** справочную систему в PowerShell необходимо обновлять. Если по какой-либо причине не удалось выполнить первоначальное обновление системы справки на компьютере, эти файлы будут недоступны, пока командлет `Update-Help` не будет успешно выполнен.

## <a name="get-command"></a>Get-Command

`Get-Command` облегчает поиск команд. Выполнение `Get-Command` без указания параметров возвращает список всех команд в системе. В приведенном ниже примере показано использование командлета `Get-Command`, который определяет команды, работающие с процессами.

```powershell
Get-Command -Noun Process
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsof...
Cmdlet          Get-Process                                        3.1.0.0    Microsof...
Cmdlet          Start-Process                                      3.1.0.0    Microsof...
Cmdlet          Stop-Process                                       3.1.0.0    Microsof...
Cmdlet          Wait-Process                                       3.1.0.0    Microsof...
```

Заметьте: в предыдущем примере, где выполнялся командлет `Get-Command`, используется параметр **Noun**, а командлет `Process` указан в качестве значения для параметра **Noun**. Что делать, если вы не знаете, как использовать командлет `Get-Command`? `Get-Help` можно использовать для вывода раздела справки для `Get-Command`.

Параметры **Name**, **Noun** и **Verb** поддерживают добавление подстановочных знаков. В приведенном ниже примере показаны подстановочные знаки, используемые с параметром **Name**.

```Output
Get-Command -Name *service*
```

```powershell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Function        Set-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          New-Service                                        3.1.0.0    Microsof...
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
Application     AgentService.exe                                   10.0.14... C:\Windo...
Application     SensorDataService.exe                              10.0.14... C:\Windo...
Application     services.exe                                       10.0.14... C:\Windo...
Application     services.msc                                       0.0.0.0    C:\Windo...
Application     TieringEngineService.exe                           10.0.14... C:\Windo...
```

Я стараюсь не использовать подстановочные знаки с параметром **Name** для `Get-Command`, так как он возвращает и исполняемые файлы, которые не являются собственными командами PowerShell.

При использовании подстановочных знаков с параметром **Name** рекомендую ограничить результаты с помощью параметра **CommandType**.

```powershell
Get-Command -Name *service* -CommandType Cmdlet, Function, Alias
```

Оптимально использовать параметр **Verb** или **Noun** либо оба этих параметра, так как только команды PowerShell состоят из глаголов и существительных.

Что делать, есть в разделе справки найдены ошибки? Можете не волноваться: материалы разделов справки в PowerShell открыты и доступны в репозитории [PowerShell-Docs][] на сайте GitHub. Исправив неверную информацию, вы поможете не только себе, но и другим пользователям. Для этого разместите репозиторий документации PowerShell на сайте GitHub, обновите раздел справки и отправьте запрос на включение внесенных изменений.
После того как этот запрос будет принят, исправленный документ появится в общем доступе.

## <a name="updating-help"></a>Обновление справки

Локальная копия разделов справки PowerShell была ранее впервые обновлена с помощью запрошенной команды. Рекомендуется периодически обновлять справочную систему, так как содержимое справки может обновляться. Для обновления разделов справки используется командлет `Update-Help`.
Для этого требуется доступ к Интернету по умолчанию, а вам необходимо запустить PowerShell с повышенными правами администратора.

```powershell
Update-Help
```

```Output
Update-Help : Failed to update Help for the module(s) 'BitsTransfer' with UI culture(s)
{en-US} : The value of the HelpInfoUri key in the module manifest must resolve to a
container or root URL on a website where the help files are stored. The HelpInfoUri
'https://technet.microsoft.com/en-us/library/dd819413.aspx' does not resolve to a
container.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : InvalidOperation: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : InvalidHelpInfoUri,Microsoft.PowerShell.Commands.UpdateHel
   pCommand

Update-Help : Failed to update Help for the module(s) 'NetworkControllerDiagnostics,
StorageReplica' with UI culture(s) {en-US} : Unable to retrieve the HelpInfo XML file
for UI culture en-US. Make sure the HelpInfoUri property in the module manifest is valid
or check your network connection and then try the command again.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : ResourceUnavailable: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : UnableToRetrieveHelpInfoXml,Microsoft.PowerShell.Commands.
   UpdateHelpCommand
```

Два модуля вернули распространенные ошибки. Если на компьютере отсутствует доступ к Интернету, можно использовать командлет `Save-Help` на другом компьютере с доступом к Интернету, чтобы сначала сохранить обновленную справочную информацию в общей папке, а затем использовать параметр **SourcePath** для `Update-Help`, чтобы указать это сетевое расположение для разделов справки.

Для периодического обновления содержимого справки на компьютере настройте запланированную задачу или добавление логики в скрипт профилирования в PowerShell. Сценарии профилирования будут рассматриваться в следующей главе.

## <a name="summary"></a>Сводка

В этой главе вы узнали, как найти команды с помощью командлетов `Get-Help` и `Get-Command`. Кроме того, вы научились пользоваться справочной системой, которая позволяет использовать найденные команды. Мы также рассмотрели, как обновлять содержимое разделов справки при доступных обновлениях.

Мне нужно, чтобы вы изучали по одной команде PowerShell в день.

```powershell
Get-Command | Get-Random | Get-Help -Full
```

## <a name="review"></a>Просмотр

1. Является ли параметр **DisplayName** `Get-Service` позиционным?
1. Сколько наборов параметров содержится в командлете `Get-Process`?
1. Какие команды PowerShell используются для работы с журналами событий?
1. Какая команда PowerShell возвращает список процессов PowerShell, запущенных на компьютере?
1. Как обновить содержимое справки PowerShell, сохраненное на компьютере?

## <a name="recommended-reading"></a>Рекомендуем прочесть

Если вы хотите более подробно изучить темы, описанные в этой главе, рекомендую ознакомиться со следующими разделами справки по PowerShell.

- [Get-Help][]
- [Get-Command][]
- [Update-Help][]
- [Save-Help][]
- [about_Updatable_Help][]
- [about_Command_Syntax][]

В следующей главе вы узнаете о командлете `Get-Member`, а также об объектах, свойствах и методах.

<!-- link references -->
[Get-Help]: /powershell/module/microsoft.powershell.core/get-help
[Get-Command]: /powershell/module/microsoft.powershell.core/get-command
[Update-Help]: /powershell/module/microsoft.powershell.core/update-help
[Save-Help]: /powershell/module/microsoft.powershell.core/save-help
[about_Updatable_Help]: /powershell/module/microsoft.powershell.core/about/about_updatable_help
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[PowerShell-Docs]: https://github.com/powershell/powershell
[Приложение А]: appendix-a.md

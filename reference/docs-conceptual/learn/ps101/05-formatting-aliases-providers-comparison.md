---
title: Форматирование, псевдонимы, поставщики, сравнение
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
description: В этой главе представлены понятия форматирования выходных данных, псевдонимов команд, поставщиков и операций сравнения.
ms.openlocfilehash: efe70d2d220f8451e781603b6000c3553dda910c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501615"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a>Глава 5. Форматирование, псевдонимы, поставщики, сравнение

## <a name="requirements"></a>Требования

В некоторых примерах, приведенных в этой главе, требуется модуль SQL Server PowerShell. Модуль устанавливается в составе [SQL Server Management Studio (SSMS)][SMSS]. Он также используется в последующих главах. Скачайте и установите его на компьютер Windows 10 с лабораторной средой.

## <a name="format-right"></a>Форматирование как можно ближе к правому краю

В главе 4 вы узнали, как выполнять фильтрацию как можно ближе к левому краю. Правило для форматирования выходных данных команды вручную аналогично этому правилу, за исключением того, что форматирование должно осуществляться как можно ближе к правому краю.

Самыми распространенными командами форматирования являются `Format-Table` и `Format-List`. Кроме того, можно использовать команды `Format-Wide` и `Format-Custom`, но они менее популярны.

Как упоминалось в главе 3, команда, возвращающая более четырех свойств, по умолчанию выводит их в виде списка, если не используется пользовательское форматирование.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```Output
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

Воспользуемся командлетом `Format-Table`, чтобы вручную переопределить форматирование и отображать выходные данные в виде таблицы, а не списка.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

Выходными данными по умолчанию для `Get-Service` являются три свойства в таблице.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Воспользуемся командлетом `Format-List`, чтобы переопределить форматирование по умолчанию и возвращать результаты в виде списка.

```powershell
Get-Service -Name w32time | Format-List
```

```Output
Name                : w32time
DisplayName         : Windows Time
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
ServiceType         : Win32ShareProcess
```

Обратите внимание, что, если просто передать `Get-Service` в командлет `Format-List`, он будет возвращать дополнительные свойства. Эта возможность поддерживается не для каждой команды, так как форматирование определенной команды настраивается в фоновом режиме.

Главное, что нужно знать при использовании команд форматирования, это то, что они создают объекты форматирования, которые отличаются от обычных объектов в PowerShell.

```powershell
Get-Service -Name w32time | Format-List | Get-Member
```

```Output
   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
autosizeInfo                            Property   Microsoft.PowerShell.Commands.Inter...
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
pageFooterEntry                         Property   Microsoft.PowerShell.Commands.Inter...
pageHeaderEntry                         Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEntryData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
formatEntryInfo                         Property   Microsoft.PowerShell.Commands.Inter...
outOfBand                               Property   bool outOfBand {get;set;}
writeStream                             Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
```

Это означает, что команды форматирования невозможно передать в большинство других команд. Их можно передать в некоторые команды `Out-*`. Но только в эти. Именно поэтому необходимо выполнять форматирование в самом конце строки (форматирование как можно ближе к правому краю).

## <a name="aliases"></a>Aliases

Псевдоним в PowerShell — это более короткое имя команды. PowerShell содержит набор встроенных псевдонимов, а также позволяет определять собственные псевдонимы.

Для поиска псевдонимов используется командлет `Get-Alias`. Если псевдоним для команды уже известен, параметр **Name** поможет определить команду, с которой он связан.

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

В качестве значения параметра **Name** можно указать несколько псевдонимов.

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

Вы заметите, что параметр **Name** опускается, так как он является позиционным параметром.

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

Чтобы найти псевдонимы для команды, необходимо использовать параметр **Definition** .

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

Параметр **Definition** не может использоваться позиционно, поэтому он должен быть задан.

Псевдонимы ускоряют ввод значений и эффективны при вводе команд в консоль.
Их не следует использовать в сценариях или коде, который вы сохраняете или используете совместно с другими пользователями. Как говорилось ранее в этой книге, полные имена командлетов и параметров являются самодокументируемыми, что упрощает их понимание.

Будьте внимательны при создании собственных псевдонимов, так как они будут существовать только в текущем сеансе PowerShell на вашем компьютере.

## <a name="providers"></a>Поставщики

Поставщик в PowerShell — это интерфейс, который позволяет файловой системе, например, получить доступ к хранилищу данных. В PowerShell имеется ряд встроенных поставщиков.

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
Certificate          ShouldProcess                      {Cert}
WSMan                Credentials                        {WSMan}
```

Как видно в предыдущих результатах, существуют встроенные поставщики для реестра, псевдонимов, переменных среды, файловой системы, функций, переменных, сертификатов и WSMan.

Фактические диски, используемые этими поставщиками для предоставления хранилища данных, можно определить с помощью командлета `Get-PSDrive`. Командлет `Get-PSDrive` не только отображает диски, предоставляемые поставщиками, но и выводит логические диски Windows, включая диски, сопоставленные с сетевыми папками.

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
Alias                                  Alias
C                  14.41        112.10 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
WSMan                                  WSMan
```

Сторонние модули, такие как модуль PowerShell для Active Directory и модуль PowerShell для SQL Server, имеют собственные поставщики PowerShell и PSDrive.

Импортируем модули PowerShell для Active Directory и SQL Server.

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

Проверим, были ли добавлены дополнительные поставщики PowerShell.

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
ActiveDirectory      Include, Exclude, Filter, Shoul... {AD}
SqlServer            Credentials                        {SQLSERVER}
```

Обратите внимание, что в предыдущем наборе результатов теперь существует два новых поставщика PowerShell: один для Active Directory и другой для SQL Server.

Для каждого из этих модулей также был добавлен диск PSDrive.

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
AD                                     ActiveDire... //RootDSE/
Alias                                  Alias
C                  19.38        107.13 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
SQLSERVER                              SqlServer     SQLSERVER:\
Variable                               Variable
WSMan                                  WSMan
```

Доступ к дискам PSDrive осуществляется так же, как к традиционной файловой системе.

```powershell
Get-ChildItem -Path Cert:\LocalMachine\CA
```

```Output
   PSParentPath: Microsoft.PowerShell.Security\Certificate::LocalMachine\CA

Thumbprint                                Subject
----------                                -------
FEE449EE0E3965A5246F000E87FDE2A065FD89D4  CN=Root Agency
D559A586669B08F46A30A133F8A9ED3D038E2EA8  OU=www.verisign.com/CPS Incorporated LIABI...
109F1CAED645BB78B3EA2B94C0697C740733031C  CN=Microsoft Windows Hardware Compatibility,...
```

## <a name="comparison-operators"></a>Операторы сравнения

PowerShell содержит несколько операторов сравнения, которые используются для сравнения значений или поиска значений, соответствующих определенным шаблонам. В таблице 5-1 содержится список операторов сравнения в PowerShell.

|    Оператор    |                          Определение                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | Равно                                                     |
| `-ne`          | Не равно                                                 |
| `-gt`          | Больше                                                 |
| `-ge`          | Больше или равно                                     |
| `-lt`          | Меньше чем                                                    |
| `-le`          | Меньше или равно                                        |
| `-Like`        | Соответствие с использованием подстановочного знака `*`.                       |
| `-NotLike`     | Несоответствие с использованием подстановочного знака `*`.              |
| `-Match`       | Соответствует указному регулярному выражению.                     |
| `-NotMatch`    | Не соответствует указанному регулярному выражению.              |
| `-Contains`    | Определяет, что коллекция содержит указанное значение.        |
| `-NotContains` | Определяет, что коллекция не содержит указанное значение. |
| `-In`          | Определяет, что указанное значение находится в коллекции.           |
| `-NotIn`       | Определяет, что указанное значение не находится в коллекции.       |
| `-Replace`     | Заменяет указанное значение.                                 |

Все операторы, перечисленные в таблице 5-1, не учитывают регистр. Поместите `c` перед оператором, приведенным в таблице 5-1, чтобы сделать его чувствительным к регистру. Например, `-ceq` — это зависящая от регистра версия оператора сравнения `-eq`.

Если используется оператор сравнения "равно", PowerShell в формате, где первая буква каждого слова прописная, а остальные строчные, соответствует powershell в нижнем регистре.

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

Если используется зависящая от регистра версия оператора сравнения "равно", эти два значения не равны.

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

Оператор сравнения "не равно" изменяет условие на противоположное.

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

Операторы "больше", "больше или равно", "меньше", "меньше или равно" работают со строковыми или числовыми значениями.

```powershell
5 -gt 5
```

```Output
False
```

Если в предыдущем примере вместо оператора "больше" будет использоваться оператор "больше или равно", будет возвращено **логическое** значение True, так как пять равно пяти.

```powershell
5 -ge 5
```

```Output
True
```

На основе результатов из предыдущих двух примеров можно догадаться, как работают операторы "меньше" и "меньше или равно".

```powershell
5 -lt 10
```

```Output
True
```

Операторы `-Like` и `-Match` могут приводить в замешательство даже опытных пользователей PowerShell. `-Like` используется с подстановочными знаками `*` и `?` для выполнения совпадений с указанным шаблоном.

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

`-Match` использует регулярное выражение для выполнения сопоставления.

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

Для сохранения чисел с 1 по 10 в переменной воспользуемся оператором диапазона.

```powershell
$Numbers = 1..10
```

```Output
```

Определим, содержит ли переменная `$Numbers` число 15.

```powershell
$Numbers -contains 15
```

```Output
False
```

Определим, содержит ли она число 10.

```powershell
$Numbers -contains 10
```

```Output
True
```

`-NotContains` изменяет логику на противоположную, чтобы проверить, что переменная `$Numbers` не содержит значение.

```powershell
$Numbers -notcontains 15
```

```Output
True
```

В предыдущем примере возвращается **логическое** значение True, поскольку переменная `$Numbers` не содержит число 15. Однако она содержит число 10, поэтому при тестировании получим False.

```powershell
$Numbers -notcontains 10
```

```Output
False
```

Оператор сравнения in впервые появился в PowerShell версии 3.0. Он используется, чтобы определить, находится ли значение в массиве. `$Numbers` переменная находится в массиве, так как он содержит несколько значений.

```powershell
15 -in $Numbers
```

```Output
False
```

Другими словами, `-in` выполняет ту же проверку, что и оператор сравнения contains, за исключением того, что действие происходит в обратном направлении.

```powershell
10 -in $Numbers
```

```Output
True
```

15 не находится в массиве `$Numbers`, поэтому в следующем примере возвращается значение False.

```powershell
15 -in $Numbers
```

```Output
False
```

Точно так же, как оператор `-contains`, `not` меняет логику оператора `-in` на обратную.

```powershell
10 -notin $Numbers
```

```Output
False
```

В предыдущем примере возвращается значение False, поскольку массив `$Numbers` содержит число 10, а условием было проверить, что он не содержит число 10.

15 не находится в массиве `$Numbers`, поэтому возвращается **логическое** значение True.

```powershell
15 -notin $Numbers
```

```Output
True
```

Оператор `-replace` делает то, что вы думаете. Он используется для замены чего-либо. При указании одного значения это значение заменяется пустым (т. е. ничем). В следующем примере Shell заменяется пустым значением.

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

Если вы хотите заменить значение другим значением, укажите новое значение после шаблона, который требуется заменить. SQL Saturday in Baton Rouge — это мероприятие, в котором я стараюсь принимать участие каждый год. В следующем примере я заменяю слово Saturday на сокращение Sat.

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

Существуют также такие методы, как **Replace()** , которые можно использовать для замены точно так же, как оператор замены. Однако оператор `-Replace` не учитывает регистр по умолчанию, а метод **Replace()** зависит от регистра.

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

Обратите внимание, что слово Saturday не было заменено в предыдущем примере. Это обусловлено тем, что оно было указано в другом регистре, чем исходное слово. Если слово Saturday задается в том же регистре, что и исходное, метод **Replace()** заменяет его ожидаемым образом.

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

При использовании методов для преобразования данных следует соблюдать осторожность, так как могут возникнуть непредвиденные проблемы, такие как непрохождение _турецкого теста_ . Пример см. в статье блога [Using Pester to Test PowerShell Code with Other Cultures][]. Чтобы избежать проблем такого типа, рекомендуется по возможности использовать оператор вместо метода.

Несмотря на то что операторы сравнения можно использовать, как показано в предыдущих примерах, обычно я применяю их с командлетом `Where-Object` для выполнения фильтрации.

## <a name="summary"></a>Сводка

В этой главе вы узнали, как выполнять форматирование как можно ближе к правому краю, как использовать псевдонимы, поставщики и операторы сравнения.

## <a name="review"></a>Просмотр

1. Для чего нужно выполнять форматирование как можно ближе к правому краю?
1. Как определить фактический командлет для псевдонима `%`?
1. Почему не следует использовать псевдонимы в сценариях, которые вы сохраняете, или коде, используемом совместно с другими пользователями?
1. Выведите список каталогов на дисках, связанных с одним из поставщиков реестра.
1. В чем заключается одно из основных преимуществ использования оператора замены вместо метода замены?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [Format-Table][]
- [Format-List][]
- [Format-Wide][]
- [about_Aliases][]
- [about_Providers][]
- [about_Comparison_Operators][]
- [about_Arrays][]

<!-- link references -->
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
[Format-Table]: /powershell/module/microsoft.powershell.utility/format-table
[Format-List]: /powershell/module/microsoft.powershell.utility/format-list
[Format-Wide]: /powershell/module/microsoft.powershell.utility/format-wide
[about_Aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[about_Providers]: /powershell/module/microsoft.powershell.core/about/about_providers
[about_Comparison_Operators]: /powershell/module/microsoft.powershell.core/about/about_comparison_operators
[about_Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Using Pester to Test PowerShell Code with Other Cultures]: https://mikefrobbins.com/2015/10/22/using-pester-to-test-powershell-code-with-other-cultures/ (Использование Pester для тестирования кода PowerShell для других языков и региональных параметров)

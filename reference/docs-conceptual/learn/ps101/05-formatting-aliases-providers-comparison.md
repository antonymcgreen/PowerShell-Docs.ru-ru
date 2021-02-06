---
title: Форматирование, псевдонимы, поставщики, сравнение
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
description: В этой главе представлены понятия форматирования выходных данных, псевдонимов команд, поставщиков и операций сравнения.
ms.openlocfilehash: 5573ca58601af0c6af15736b772a9792d8d77a79
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99602077"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a><span data-ttu-id="03bcb-103">Глава 5. Форматирование, псевдонимы, поставщики, сравнение</span><span class="sxs-lookup"><span data-stu-id="03bcb-103">Chapter 5 - Formatting, aliases, providers, comparison</span></span>

## <a name="requirements"></a><span data-ttu-id="03bcb-104">Требования</span><span class="sxs-lookup"><span data-stu-id="03bcb-104">Requirements</span></span>

<span data-ttu-id="03bcb-105">В некоторых примерах, приведенных в этой главе, требуется модуль SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03bcb-105">The SQL Server PowerShell module is required by some of the examples shown in this chapter.</span></span> <span data-ttu-id="03bcb-106">Модуль устанавливается в составе [SQL Server Management Studio (SSMS)][SMSS].</span><span class="sxs-lookup"><span data-stu-id="03bcb-106">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="03bcb-107">Он также используется в последующих главах.</span><span class="sxs-lookup"><span data-stu-id="03bcb-107">It's also used in subsequent chapters.</span></span> <span data-ttu-id="03bcb-108">Скачайте и установите его на компьютер Windows 10 с лабораторной средой.</span><span class="sxs-lookup"><span data-stu-id="03bcb-108">Download and install it on your Windows 10 lab environment computer.</span></span>

## <a name="format-right"></a><span data-ttu-id="03bcb-109">Форматирование как можно ближе к правому краю</span><span class="sxs-lookup"><span data-stu-id="03bcb-109">Format Right</span></span>

<span data-ttu-id="03bcb-110">В главе 4 вы узнали, как выполнять фильтрацию как можно ближе к левому краю.</span><span class="sxs-lookup"><span data-stu-id="03bcb-110">In Chapter 4, you learned to filter as far to the left as possible.</span></span> <span data-ttu-id="03bcb-111">Правило для форматирования выходных данных команды вручную аналогично этому правилу, за исключением того, что форматирование должно осуществляться как можно ближе к правому краю.</span><span class="sxs-lookup"><span data-stu-id="03bcb-111">The rule for manually formatting a command's output is similar to that rule except it needs to occur as far to the right as possible.</span></span>

<span data-ttu-id="03bcb-112">Самыми распространенными командами форматирования являются `Format-Table` и `Format-List`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-112">The most common format commands are `Format-Table` and `Format-List`.</span></span> <span data-ttu-id="03bcb-113">Кроме того, можно использовать команды `Format-Wide` и `Format-Custom`, но они менее популярны.</span><span class="sxs-lookup"><span data-stu-id="03bcb-113">`Format-Wide` and `Format-Custom` can also be used, but are less common.</span></span>

<span data-ttu-id="03bcb-114">Как упоминалось в главе 3, команда, возвращающая более четырех свойств, по умолчанию выводит их в виде списка, если не используется пользовательское форматирование.</span><span class="sxs-lookup"><span data-stu-id="03bcb-114">As mentioned in Chapter 3, a command that returns more than four properties defaults to a list unless custom formatting is used.</span></span>

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

<span data-ttu-id="03bcb-115">Воспользуемся командлетом `Format-Table`, чтобы вручную переопределить форматирование и отображать выходные данные в виде таблицы, а не списка.</span><span class="sxs-lookup"><span data-stu-id="03bcb-115">Use the `Format-Table` cmdlet to manually override the formatting and show the output in a table instead of a list.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

<span data-ttu-id="03bcb-116">Выходными данными по умолчанию для `Get-Service` являются три свойства в таблице.</span><span class="sxs-lookup"><span data-stu-id="03bcb-116">The default output for `Get-Service` is three properties in a table.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="03bcb-117">Воспользуемся командлетом `Format-List`, чтобы переопределить форматирование по умолчанию и возвращать результаты в виде списка.</span><span class="sxs-lookup"><span data-stu-id="03bcb-117">Use the `Format-List` cmdlet to override the default formatting and return the results in a list.</span></span>

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

<span data-ttu-id="03bcb-118">Обратите внимание, что, если просто передать `Get-Service` в командлет `Format-List`, он будет возвращать дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="03bcb-118">Notice that simply piping `Get-Service` to `Format-List` made it return additional properties.</span></span> <span data-ttu-id="03bcb-119">Эта возможность поддерживается не для каждой команды, так как форматирование определенной команды настраивается в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="03bcb-119">This doesn't occur with every command because of the way the formatting for that particular command is set up behind the scenes.</span></span>

<span data-ttu-id="03bcb-120">Главное, что нужно знать при использовании команд форматирования, это то, что они создают объекты форматирования, которые отличаются от обычных объектов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03bcb-120">The number one thing to be aware of with the format cmdlets is they produce format objects that are different than normal objects in PowerShell.</span></span>

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

<span data-ttu-id="03bcb-121">Это означает, что команды форматирования невозможно передать в большинство других команд.</span><span class="sxs-lookup"><span data-stu-id="03bcb-121">What this means is format commands can't be piped to most other commands.</span></span> <span data-ttu-id="03bcb-122">Их можно передать в некоторые команды `Out-*`. Но только в эти.</span><span class="sxs-lookup"><span data-stu-id="03bcb-122">They can be piped to some of the `Out-*` commands, but that's about it.</span></span> <span data-ttu-id="03bcb-123">Именно поэтому необходимо выполнять форматирование в самом конце строки (форматирование как можно ближе к правому краю).</span><span class="sxs-lookup"><span data-stu-id="03bcb-123">This is why you want to perform any formatting at the very end of the line (format right).</span></span>

## <a name="aliases"></a><span data-ttu-id="03bcb-124">Aliases</span><span class="sxs-lookup"><span data-stu-id="03bcb-124">Aliases</span></span>

<span data-ttu-id="03bcb-125">Псевдоним в PowerShell — это более короткое имя команды.</span><span class="sxs-lookup"><span data-stu-id="03bcb-125">An alias in PowerShell is a shorter name for a command.</span></span> <span data-ttu-id="03bcb-126">PowerShell содержит набор встроенных псевдонимов, а также позволяет определять собственные псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="03bcb-126">PowerShell includes a set of built-in aliases and you can also define your own aliases.</span></span>

<span data-ttu-id="03bcb-127">Для поиска псевдонимов используется командлет `Get-Alias`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-127">The `Get-Alias` cmdlet is used to find aliases.</span></span> <span data-ttu-id="03bcb-128">Если псевдоним для команды уже известен, параметр **Name** поможет определить команду, с которой он связан.</span><span class="sxs-lookup"><span data-stu-id="03bcb-128">If you already know the alias for a command, the **Name** parameter is used to determine what command the alias is associated with.</span></span>

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

<span data-ttu-id="03bcb-129">В качестве значения параметра **Name** можно указать несколько псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="03bcb-129">Multiple aliases can be specified for the value of the **Name** parameter.</span></span>

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="03bcb-130">Вы заметите, что параметр **Name** опускается, так как он является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="03bcb-130">You'll often see the **Name** parameter omitted since it's a positional parameter.</span></span>

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

<span data-ttu-id="03bcb-131">Чтобы найти псевдонимы для команды, необходимо использовать параметр **Definition**.</span><span class="sxs-lookup"><span data-stu-id="03bcb-131">If you want to find aliases for a command, you'll need to use the **Definition** parameter.</span></span>

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="03bcb-132">Параметр **Definition** не может использоваться позиционно, поэтому он должен быть задан.</span><span class="sxs-lookup"><span data-stu-id="03bcb-132">The **Definition** parameter can't be used positionally so it must be specified.</span></span>

<span data-ttu-id="03bcb-133">Псевдонимы ускоряют ввод значений и эффективны при вводе команд в консоль.</span><span class="sxs-lookup"><span data-stu-id="03bcb-133">Aliases can save you a few keystrokes and they're fine when you're typing commands into the console.</span></span>
<span data-ttu-id="03bcb-134">Их не следует использовать в сценариях или коде, который вы сохраняете или используете совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="03bcb-134">They shouldn't be used in scripts or any code that you're saving or sharing with others.</span></span> <span data-ttu-id="03bcb-135">Как говорилось ранее в этой книге, полные имена командлетов и параметров являются самодокументируемыми, что упрощает их понимание.</span><span class="sxs-lookup"><span data-stu-id="03bcb-135">As mentioned earlier in this book, using full cmdlet and parameter names is self-documenting and easier to understand.</span></span>

<span data-ttu-id="03bcb-136">Будьте внимательны при создании собственных псевдонимов, так как они будут существовать только в текущем сеансе PowerShell на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="03bcb-136">Use caution when creating your own aliases because they'll only exist in your current PowerShell session on your computer.</span></span>

## <a name="providers"></a><span data-ttu-id="03bcb-137">Поставщики</span><span class="sxs-lookup"><span data-stu-id="03bcb-137">Providers</span></span>

<span data-ttu-id="03bcb-138">Поставщик в PowerShell — это интерфейс, который позволяет файловой системе, например, получить доступ к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="03bcb-138">A provider in PowerShell is an interface that allows file system like access to a datastore.</span></span> <span data-ttu-id="03bcb-139">В PowerShell имеется ряд встроенных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="03bcb-139">There are a number of built-in providers in PowerShell.</span></span>

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

<span data-ttu-id="03bcb-140">Как видно в предыдущих результатах, существуют встроенные поставщики для реестра, псевдонимов, переменных среды, файловой системы, функций, переменных, сертификатов и WSMan.</span><span class="sxs-lookup"><span data-stu-id="03bcb-140">As you can see in the previous results, there are built-in providers for the registry, aliases, environment variables, the file system, functions, variables, certificates, and WSMan.</span></span>

<span data-ttu-id="03bcb-141">Фактические диски, используемые этими поставщиками для предоставления хранилища данных, можно определить с помощью командлета `Get-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-141">The actual drives that these providers use to expose their datastore can be determined with the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="03bcb-142">Командлет `Get-PSDrive` не только отображает диски, предоставляемые поставщиками, но и выводит логические диски Windows, включая диски, сопоставленные с сетевыми папками.</span><span class="sxs-lookup"><span data-stu-id="03bcb-142">The `Get-PSDrive` cmdlet not only displays drives exposed by providers, but it also displays Windows logical drives including drives mapped to network shares.</span></span>

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

<span data-ttu-id="03bcb-143">Сторонние модули, такие как модуль PowerShell для Active Directory и модуль PowerShell для SQL Server, имеют собственные поставщики PowerShell и PSDrive.</span><span class="sxs-lookup"><span data-stu-id="03bcb-143">Third-party modules such as the Active Directory PowerShell module and the SQLServer PowerShell module both add their own PowerShell provider and PSDrive.</span></span>

<span data-ttu-id="03bcb-144">Импортируем модули PowerShell для Active Directory и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03bcb-144">Import the Active Directory and SQL Server PowerShell modules.</span></span>

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

<span data-ttu-id="03bcb-145">Проверим, были ли добавлены дополнительные поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03bcb-145">Check to see if any additional PowerShell providers were added.</span></span>

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

<span data-ttu-id="03bcb-146">Обратите внимание, что в предыдущем наборе результатов теперь существует два новых поставщика PowerShell: один для Active Directory и другой для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03bcb-146">Notice that in the previous set of results, two new PowerShell providers now exist, one for Active Directory and another one for SQL Server.</span></span>

<span data-ttu-id="03bcb-147">Для каждого из этих модулей также был добавлен диск PSDrive.</span><span class="sxs-lookup"><span data-stu-id="03bcb-147">A PSDrive for each of those modules was also added.</span></span>

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

<span data-ttu-id="03bcb-148">Доступ к дискам PSDrive осуществляется так же, как к традиционной файловой системе.</span><span class="sxs-lookup"><span data-stu-id="03bcb-148">PSDrives can be accessed just like a traditional file system.</span></span>

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

## <a name="comparison-operators"></a><span data-ttu-id="03bcb-149">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="03bcb-149">Comparison Operators</span></span>

<span data-ttu-id="03bcb-150">PowerShell содержит несколько операторов сравнения, которые используются для сравнения значений или поиска значений, соответствующих определенным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="03bcb-150">PowerShell contains a number of comparison operators that are used to compare values or find values that match certain patterns.</span></span> <span data-ttu-id="03bcb-151">В таблице 5-1 содержится список операторов сравнения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03bcb-151">Table 5-1 contains a list of comparison operators in PowerShell.</span></span>

|    <span data-ttu-id="03bcb-152">Оператор</span><span class="sxs-lookup"><span data-stu-id="03bcb-152">Operator</span></span>    |                          <span data-ttu-id="03bcb-153">Определение</span><span class="sxs-lookup"><span data-stu-id="03bcb-153">Definition</span></span>                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | <span data-ttu-id="03bcb-154">Равно</span><span class="sxs-lookup"><span data-stu-id="03bcb-154">Equal to</span></span>                                                     |
| `-ne`          | <span data-ttu-id="03bcb-155">Не равно</span><span class="sxs-lookup"><span data-stu-id="03bcb-155">Not equal to</span></span>                                                 |
| `-gt`          | <span data-ttu-id="03bcb-156">Больше</span><span class="sxs-lookup"><span data-stu-id="03bcb-156">Greater than</span></span>                                                 |
| `-ge`          | <span data-ttu-id="03bcb-157">Больше или равно</span><span class="sxs-lookup"><span data-stu-id="03bcb-157">Greater than or equal to</span></span>                                     |
| `-lt`          | <span data-ttu-id="03bcb-158">Меньше чем</span><span class="sxs-lookup"><span data-stu-id="03bcb-158">Less than</span></span>                                                    |
| `-le`          | <span data-ttu-id="03bcb-159">Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="03bcb-159">Less than or equal to</span></span>                                        |
| `-Like`        | <span data-ttu-id="03bcb-160">Соответствие с использованием подстановочного знака `*`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-160">Match using the `*` wildcard character</span></span>                       |
| `-NotLike`     | <span data-ttu-id="03bcb-161">Несоответствие с использованием подстановочного знака `*`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-161">Does not match using the `*` wildcard character</span></span>              |
| `-Match`       | <span data-ttu-id="03bcb-162">Соответствует указному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="03bcb-162">Matches the specified regular expression</span></span>                     |
| `-NotMatch`    | <span data-ttu-id="03bcb-163">Не соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="03bcb-163">Does not match the specified regular expression</span></span>              |
| `-Contains`    | <span data-ttu-id="03bcb-164">Определяет, что коллекция содержит указанное значение.</span><span class="sxs-lookup"><span data-stu-id="03bcb-164">Determines if a collection contains a specified value</span></span>        |
| `-NotContains` | <span data-ttu-id="03bcb-165">Определяет, что коллекция не содержит указанное значение.</span><span class="sxs-lookup"><span data-stu-id="03bcb-165">Determines if a collection does not contain a specific value</span></span> |
| `-In`          | <span data-ttu-id="03bcb-166">Определяет, что указанное значение находится в коллекции.</span><span class="sxs-lookup"><span data-stu-id="03bcb-166">Determines if a specified value is in a collection</span></span>           |
| `-NotIn`       | <span data-ttu-id="03bcb-167">Определяет, что указанное значение не находится в коллекции.</span><span class="sxs-lookup"><span data-stu-id="03bcb-167">Determines if a specified value is not in a collection</span></span>       |
| `-Replace`     | <span data-ttu-id="03bcb-168">Заменяет указанное значение.</span><span class="sxs-lookup"><span data-stu-id="03bcb-168">Replaces the specified value</span></span>                                 |

<span data-ttu-id="03bcb-169">Все операторы, перечисленные в таблице 5-1, не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="03bcb-169">All of the operators listed in Table 5-1 are case-insensitive.</span></span> <span data-ttu-id="03bcb-170">Поместите `c` перед оператором, приведенным в таблице 5-1, чтобы сделать его чувствительным к регистру.</span><span class="sxs-lookup"><span data-stu-id="03bcb-170">Place a `c` in front of the operator listed in Table 5-1 to make it case-sensitive.</span></span> <span data-ttu-id="03bcb-171">Например, `-ceq` — это зависящая от регистра версия оператора сравнения `-eq`.</span><span class="sxs-lookup"><span data-stu-id="03bcb-171">For example, `-ceq` is the case-sensitive version of the `-eq` comparison operator.</span></span>

<span data-ttu-id="03bcb-172">Если используется оператор сравнения "равно", PowerShell в формате, где первая буква каждого слова прописная, а остальные строчные, соответствует powershell в нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="03bcb-172">Proper case "PowerShell" is equal to lower case "powershell" using the equals comparison operator.</span></span>

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

<span data-ttu-id="03bcb-173">Если используется зависящая от регистра версия оператора сравнения "равно", эти два значения не равны.</span><span class="sxs-lookup"><span data-stu-id="03bcb-173">It's not equal using the case-sensitive version of the equals comparison operator.</span></span>

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

<span data-ttu-id="03bcb-174">Оператор сравнения "не равно" изменяет условие на противоположное.</span><span class="sxs-lookup"><span data-stu-id="03bcb-174">The not equal comparison operator reverses the condition.</span></span>

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

<span data-ttu-id="03bcb-175">Операторы "больше", "больше или равно", "меньше", "меньше или равно" работают со строковыми или числовыми значениями.</span><span class="sxs-lookup"><span data-stu-id="03bcb-175">Greater than, greater than or equal to, less than, and less than or equal all work with string or numeric values.</span></span>

```powershell
5 -gt 5
```

```Output
False
```

<span data-ttu-id="03bcb-176">Если в предыдущем примере вместо оператора "больше" будет использоваться оператор "больше или равно", будет возвращено **логическое** значение True, так как пять равно пяти.</span><span class="sxs-lookup"><span data-stu-id="03bcb-176">Using greater than or equal to instead of greater than with the previous example returns the **Boolean** true since five is equal to five.</span></span>

```powershell
5 -ge 5
```

```Output
True
```

<span data-ttu-id="03bcb-177">На основе результатов из предыдущих двух примеров можно догадаться, как работают операторы "меньше" и "меньше или равно".</span><span class="sxs-lookup"><span data-stu-id="03bcb-177">Based on the results from the previous two examples, you can probably guess how both less than and less than or equal to work.</span></span>

```powershell
5 -lt 10
```

```Output
True
```

<span data-ttu-id="03bcb-178">Операторы `-Like` и `-Match` могут приводить в замешательство даже опытных пользователей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03bcb-178">The `-Like` and `-Match` operators can be confusing, even for experienced PowerShell users.</span></span> <span data-ttu-id="03bcb-179">`-Like` используется с подстановочными знаками `*` и `?` для выполнения совпадений с указанным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="03bcb-179">`-Like` is used with wildcard the characters `*` and `?` to perform "like" matches.</span></span>

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

<span data-ttu-id="03bcb-180">`-Match` использует регулярное выражение для выполнения сопоставления.</span><span class="sxs-lookup"><span data-stu-id="03bcb-180">`-Match` uses a regular expression to perform the matching.</span></span>

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

<span data-ttu-id="03bcb-181">Для сохранения чисел с 1 по 10 в переменной воспользуемся оператором диапазона.</span><span class="sxs-lookup"><span data-stu-id="03bcb-181">Use the range operator to store the numbers 1 through 10 in a variable.</span></span>

```powershell
$Numbers = 1..10
```

```Output
```

<span data-ttu-id="03bcb-182">Определим, содержит ли переменная `$Numbers` число 15.</span><span class="sxs-lookup"><span data-stu-id="03bcb-182">Determine if the `$Numbers` variable includes 15.</span></span>

```powershell
$Numbers -contains 15
```

```Output
False
```

<span data-ttu-id="03bcb-183">Определим, содержит ли она число 10.</span><span class="sxs-lookup"><span data-stu-id="03bcb-183">Determine if it includes the number 10.</span></span>

```powershell
$Numbers -contains 10
```

```Output
True
```

<span data-ttu-id="03bcb-184">`-NotContains` изменяет логику на противоположную, чтобы проверить, что переменная `$Numbers` не содержит значение.</span><span class="sxs-lookup"><span data-stu-id="03bcb-184">`-NotContains` reverses the logic to see if the `$Numbers` variable doesn't contain a value.</span></span>

```powershell
$Numbers -notcontains 15
```

```Output
True
```

<span data-ttu-id="03bcb-185">В предыдущем примере возвращается **логическое** значение True, поскольку переменная `$Numbers` не содержит число 15.</span><span class="sxs-lookup"><span data-stu-id="03bcb-185">The previous example returns the **Boolean** true because it's true that the `$Numbers` variable doesn't contain 15.</span></span> <span data-ttu-id="03bcb-186">Однако она содержит число 10, поэтому при тестировании получим False.</span><span class="sxs-lookup"><span data-stu-id="03bcb-186">It does however contain the number 10 so it's false when it's tested.</span></span>

```powershell
$Numbers -notcontains 10
```

```Output
False
```

<span data-ttu-id="03bcb-187">Оператор сравнения in впервые появился в PowerShell версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="03bcb-187">The "in" comparison operator was first introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="03bcb-188">Он используется, чтобы определить, находится ли значение в массиве.</span><span class="sxs-lookup"><span data-stu-id="03bcb-188">It's used to determine if a value is "in" an array.</span></span> <span data-ttu-id="03bcb-189">`$Numbers` переменная находится в массиве, так как он содержит несколько значений.</span><span class="sxs-lookup"><span data-stu-id="03bcb-189">The `$Numbers` variable is an array since it contains multiple values.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="03bcb-190">Другими словами, `-in` выполняет ту же проверку, что и оператор сравнения contains, за исключением того, что действие происходит в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="03bcb-190">In other words, `-in` performs the same test as the contains comparison operator except from the opposite direction.</span></span>

```powershell
10 -in $Numbers
```

```Output
True
```

<span data-ttu-id="03bcb-191">15 не находится в массиве `$Numbers`, поэтому в следующем примере возвращается значение False.</span><span class="sxs-lookup"><span data-stu-id="03bcb-191">15 isn't in the `$Numbers` array so false is returned in the following example.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="03bcb-192">Точно так же, как оператор `-contains`, `not` меняет логику оператора `-in` на обратную.</span><span class="sxs-lookup"><span data-stu-id="03bcb-192">Just like the `-contains` operator, `not` reverses the logic for the `-in` operator.</span></span>

```powershell
10 -notin $Numbers
```

```Output
False
```

<span data-ttu-id="03bcb-193">В предыдущем примере возвращается значение False, поскольку массив `$Numbers` содержит число 10, а условием было проверить, что он не содержит число 10.</span><span class="sxs-lookup"><span data-stu-id="03bcb-193">The previous example returns false because the `$Numbers` array does include 10 and the condition was testing to determine if it didn't contain 10.</span></span>

<span data-ttu-id="03bcb-194">15 не находится в массиве `$Numbers`, поэтому возвращается **логическое** значение True.</span><span class="sxs-lookup"><span data-stu-id="03bcb-194">15 is "not in" the `$Numbers` array so it returns the **Boolean** true.</span></span>

```powershell
15 -notin $Numbers
```

```Output
True
```

<span data-ttu-id="03bcb-195">Оператор `-replace` делает то, что вы думаете.</span><span class="sxs-lookup"><span data-stu-id="03bcb-195">The `-replace` operator does just want you would think.</span></span> <span data-ttu-id="03bcb-196">Он используется для замены чего-либо.</span><span class="sxs-lookup"><span data-stu-id="03bcb-196">It's used to replace something.</span></span> <span data-ttu-id="03bcb-197">При указании одного значения это значение заменяется пустым (т. е. ничем).</span><span class="sxs-lookup"><span data-stu-id="03bcb-197">Specifying one value replaces that value with nothing.</span></span> <span data-ttu-id="03bcb-198">В следующем примере Shell заменяется пустым значением.</span><span class="sxs-lookup"><span data-stu-id="03bcb-198">In the following example, I replace "Shell" with nothing.</span></span>

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

<span data-ttu-id="03bcb-199">Если вы хотите заменить значение другим значением, укажите новое значение после шаблона, который требуется заменить.</span><span class="sxs-lookup"><span data-stu-id="03bcb-199">If you want to replace a value with a different value, specify the new value after the pattern you want to replace.</span></span> <span data-ttu-id="03bcb-200">SQL Saturday in Baton Rouge — это мероприятие, в котором я стараюсь принимать участие каждый год.</span><span class="sxs-lookup"><span data-stu-id="03bcb-200">SQL Saturday in Baton Rouge is an event that I try to speak at every year.</span></span> <span data-ttu-id="03bcb-201">В следующем примере я заменяю слово Saturday на сокращение Sat.</span><span class="sxs-lookup"><span data-stu-id="03bcb-201">In the following example, I replace the word "Saturday" with the abbreviation "Sat".</span></span>

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="03bcb-202">Существуют также такие методы, как **Replace()** , которые можно использовать для замены точно так же, как оператор замены.</span><span class="sxs-lookup"><span data-stu-id="03bcb-202">There are also methods like **Replace()** that can be used to replace things similar to the way the replace operator works.</span></span> <span data-ttu-id="03bcb-203">Однако оператор `-Replace` не учитывает регистр по умолчанию, а метод **Replace()** зависит от регистра.</span><span class="sxs-lookup"><span data-stu-id="03bcb-203">However, the `-Replace` operator is case-insensitive by default, and the **Replace()** method is case-sensitive.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

<span data-ttu-id="03bcb-204">Обратите внимание, что слово Saturday не было заменено в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="03bcb-204">Notice that the word "Saturday" wasn't replaced in the previous example.</span></span> <span data-ttu-id="03bcb-205">Это обусловлено тем, что оно было указано в другом регистре, чем исходное слово.</span><span class="sxs-lookup"><span data-stu-id="03bcb-205">This is because it was specified in a different case than the original.</span></span> <span data-ttu-id="03bcb-206">Если слово Saturday задается в том же регистре, что и исходное, метод **Replace()** заменяет его ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="03bcb-206">When the word "Saturday" is specified in the same case as the original, the **Replace()** method does replace it as expected.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="03bcb-207">При использовании методов для преобразования данных следует соблюдать осторожность, так как могут возникнуть непредвиденные проблемы, такие как непрохождение _турецкого теста_.</span><span class="sxs-lookup"><span data-stu-id="03bcb-207">Be careful when using methods to transform data because you can run into unforeseen problems, such as failing the _Turkey Test_.</span></span> <span data-ttu-id="03bcb-208">Пример см. в статье блога [Using Pester to Test PowerShell Code with Other Cultures][].</span><span class="sxs-lookup"><span data-stu-id="03bcb-208">For an example, see the blog article titled [Using Pester to Test PowerShell Code with Other Cultures][].</span></span> <span data-ttu-id="03bcb-209">Чтобы избежать проблем такого типа, рекомендуется по возможности использовать оператор вместо метода.</span><span class="sxs-lookup"><span data-stu-id="03bcb-209">My recommendation is to use an operator instead of a method whenever possible to avoid these types of problems.</span></span>

<span data-ttu-id="03bcb-210">Несмотря на то что операторы сравнения можно использовать, как показано в предыдущих примерах, обычно я применяю их с командлетом `Where-Object` для выполнения фильтрации.</span><span class="sxs-lookup"><span data-stu-id="03bcb-210">While the comparison operators can be used as shown in the previous examples, I normally find myself using them with the `Where-Object` cmdlet to perform some type of filtering.</span></span>

## <a name="summary"></a><span data-ttu-id="03bcb-211">Сводка</span><span class="sxs-lookup"><span data-stu-id="03bcb-211">Summary</span></span>

<span data-ttu-id="03bcb-212">В этой главе вы узнали, как выполнять форматирование как можно ближе к правому краю, как использовать псевдонимы, поставщики и операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="03bcb-212">In this chapter, you've learned a number of different topics to include Formatting Right, Aliases, Providers, and Comparison Operators.</span></span>

## <a name="review"></a><span data-ttu-id="03bcb-213">Просмотр</span><span class="sxs-lookup"><span data-stu-id="03bcb-213">Review</span></span>

1. <span data-ttu-id="03bcb-214">Для чего нужно выполнять форматирование как можно ближе к правому краю?</span><span class="sxs-lookup"><span data-stu-id="03bcb-214">Why is it necessary to perform Formatting as far to the right as possible?</span></span>
1. <span data-ttu-id="03bcb-215">Как определить фактический командлет для псевдонима `%`?</span><span class="sxs-lookup"><span data-stu-id="03bcb-215">How do you determine what the actual cmdlet is for the `%` alias?</span></span>
1. <span data-ttu-id="03bcb-216">Почему не следует использовать псевдонимы в сценариях, которые вы сохраняете, или коде, используемом совместно с другими пользователями?</span><span class="sxs-lookup"><span data-stu-id="03bcb-216">Why shouldn't you use aliases in scripts you save or code you share with others?</span></span>
1. <span data-ttu-id="03bcb-217">Выведите список каталогов на дисках, связанных с одним из поставщиков реестра.</span><span class="sxs-lookup"><span data-stu-id="03bcb-217">Perform a directory listing on the drives that are associated with one of the registry providers.</span></span>
1. <span data-ttu-id="03bcb-218">В чем заключается одно из основных преимуществ использования оператора замены вместо метода замены?</span><span class="sxs-lookup"><span data-stu-id="03bcb-218">What's one of the main benefits of using the replace operator instead of the replace method?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="03bcb-219">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="03bcb-219">Recommended Reading</span></span>

- <span data-ttu-id="03bcb-220">[Format-Table][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-220">[Format-Table][]</span></span>
- <span data-ttu-id="03bcb-221">[Format-List][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-221">[Format-List][]</span></span>
- <span data-ttu-id="03bcb-222">[Format-Wide][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-222">[Format-Wide][]</span></span>
- <span data-ttu-id="03bcb-223">[about_Aliases][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-223">[about_Aliases][]</span></span>
- <span data-ttu-id="03bcb-224">[about_Providers][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-224">[about_Providers][]</span></span>
- <span data-ttu-id="03bcb-225">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-225">[about_Comparison_Operators][]</span></span>
- <span data-ttu-id="03bcb-226">[about_Arrays][]</span><span class="sxs-lookup"><span data-stu-id="03bcb-226">[about_Arrays][]</span></span>

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

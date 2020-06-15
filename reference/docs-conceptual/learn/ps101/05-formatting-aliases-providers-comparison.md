---
title: Форматирование, псевдонимы, поставщики, сравнение
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: eb23b048a50f10ea83d156c0499772b1be439336
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438005"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a><span data-ttu-id="63f9e-102">Глава 5. Форматирование, псевдонимы, поставщики, сравнение</span><span class="sxs-lookup"><span data-stu-id="63f9e-102">Chapter 5 - Formatting, aliases, providers, comparison</span></span>

## <a name="requirements"></a><span data-ttu-id="63f9e-103">Требования</span><span class="sxs-lookup"><span data-stu-id="63f9e-103">Requirements</span></span>

<span data-ttu-id="63f9e-104">В некоторых примерах, приведенных в этой главе, требуется модуль SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f9e-104">The SQL Server PowerShell module is required by some of the examples shown in this chapter.</span></span> <span data-ttu-id="63f9e-105">Модуль устанавливается в составе [SQL Server Management Studio (SSMS)][SMSS].</span><span class="sxs-lookup"><span data-stu-id="63f9e-105">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="63f9e-106">Он также используется в последующих главах.</span><span class="sxs-lookup"><span data-stu-id="63f9e-106">It's also used in subsequent chapters.</span></span> <span data-ttu-id="63f9e-107">Скачайте и установите его на компьютер Windows 10 с лабораторной средой.</span><span class="sxs-lookup"><span data-stu-id="63f9e-107">Download and install it on your Windows 10 lab environment computer.</span></span>

## <a name="format-right"></a><span data-ttu-id="63f9e-108">Форматирование как можно ближе к правому краю</span><span class="sxs-lookup"><span data-stu-id="63f9e-108">Format Right</span></span>

<span data-ttu-id="63f9e-109">В главе 4 вы узнали, как выполнять фильтрацию как можно ближе к левому краю.</span><span class="sxs-lookup"><span data-stu-id="63f9e-109">In Chapter 4, you learned to filter as far to the left as possible.</span></span> <span data-ttu-id="63f9e-110">Правило для форматирования выходных данных команды вручную аналогично этому правилу, за исключением того, что форматирование должно осуществляться как можно ближе к правому краю.</span><span class="sxs-lookup"><span data-stu-id="63f9e-110">The rule for manually formatting a command's output is similar to that rule except it needs to occur as far to the right as possible.</span></span>

<span data-ttu-id="63f9e-111">Самыми распространенными командами форматирования являются `Format-Table` и `Format-List`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-111">The most common format commands are `Format-Table` and `Format-List`.</span></span> <span data-ttu-id="63f9e-112">Кроме того, можно использовать команды `Format-Wide` и `Format-Custom`, но они менее популярны.</span><span class="sxs-lookup"><span data-stu-id="63f9e-112">`Format-Wide` and `Format-Custom` can also be used, but are less common.</span></span>

<span data-ttu-id="63f9e-113">Как упоминалось в главе 3, команда, возвращающая более четырех свойств, по умолчанию выводит их в виде списка, если не используется пользовательское форматирование.</span><span class="sxs-lookup"><span data-stu-id="63f9e-113">As mentioned in Chapter 3, a command that returns more than four properties defaults to a list unless custom formatting is used.</span></span>

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

<span data-ttu-id="63f9e-114">Воспользуемся командлетом `Format-Table`, чтобы вручную переопределить форматирование и отображать выходные данные в виде таблицы, а не списка.</span><span class="sxs-lookup"><span data-stu-id="63f9e-114">Use the `Format-Table` cmdlet to manually override the formatting and show the output in a table instead of a list.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

<span data-ttu-id="63f9e-115">Выходными данными по умолчанию для `Get-Service` являются три свойства в таблице.</span><span class="sxs-lookup"><span data-stu-id="63f9e-115">The default output for `Get-Service` is three properties in a table.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="63f9e-116">Воспользуемся командлетом `Format-List`, чтобы переопределить форматирование по умолчанию и возвращать результаты в виде списка.</span><span class="sxs-lookup"><span data-stu-id="63f9e-116">Use the `Format-List` cmdlet to override the default formatting and return the results in a list.</span></span>

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

<span data-ttu-id="63f9e-117">Обратите внимание, что, если просто передать `Get-Service` в командлет `Format-List`, он будет возвращать дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="63f9e-117">Notice that simply piping `Get-Service` to `Format-List` made it return additional properties.</span></span> <span data-ttu-id="63f9e-118">Эта возможность поддерживается не для каждой команды, так как форматирование определенной команды настраивается в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="63f9e-118">This doesn't occur with every command because of the way the formatting for that particular command is set up behind the scenes.</span></span>

<span data-ttu-id="63f9e-119">Главное, что нужно знать при использовании команд форматирования, это то, что они создают объекты форматирования, которые отличаются от обычных объектов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f9e-119">The number one thing to be aware of with the format cmdlets is they produce format objects that are different than normal objects in PowerShell.</span></span>

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

<span data-ttu-id="63f9e-120">Это означает, что команды форматирования невозможно передать в большинство других команд.</span><span class="sxs-lookup"><span data-stu-id="63f9e-120">What this means is format commands can't be piped to most other commands.</span></span> <span data-ttu-id="63f9e-121">Их можно передать в некоторые команды `Out-*`. Но только в эти.</span><span class="sxs-lookup"><span data-stu-id="63f9e-121">They can be piped to some of the `Out-*` commands, but that's about it.</span></span> <span data-ttu-id="63f9e-122">Именно поэтому необходимо выполнять форматирование в самом конце строки (форматирование как можно ближе к правому краю).</span><span class="sxs-lookup"><span data-stu-id="63f9e-122">This is why you want to perform any formatting at the very end of the line (format right).</span></span>

## <a name="aliases"></a><span data-ttu-id="63f9e-123">Aliases</span><span class="sxs-lookup"><span data-stu-id="63f9e-123">Aliases</span></span>

<span data-ttu-id="63f9e-124">Псевдоним в PowerShell — это более короткое имя команды.</span><span class="sxs-lookup"><span data-stu-id="63f9e-124">An alias in PowerShell is a shorter name for a command.</span></span> <span data-ttu-id="63f9e-125">PowerShell содержит набор встроенных псевдонимов, а также позволяет определять собственные псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="63f9e-125">PowerShell includes a set of built-in aliases and you can also define your own aliases.</span></span>

<span data-ttu-id="63f9e-126">Для поиска псевдонимов используется командлет `Get-Alias`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-126">The `Get-Alias` cmdlet is used to find aliases.</span></span> <span data-ttu-id="63f9e-127">Если псевдоним для команды уже известен, параметр **Name** поможет определить команду, с которой он связан.</span><span class="sxs-lookup"><span data-stu-id="63f9e-127">If you already know the alias for a command, the **Name** parameter is used to determine what command the alias is associated with.</span></span>

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

<span data-ttu-id="63f9e-128">В качестве значения параметра **Name** можно указать несколько псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="63f9e-128">Multiple aliases can be specified for the value of the **Name** parameter.</span></span>

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="63f9e-129">Вы заметите, что параметр **Name** опускается, так как он является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="63f9e-129">You'll often see the **Name** parameter omitted since it's a positional parameter.</span></span>

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

<span data-ttu-id="63f9e-130">Чтобы найти псевдонимы для команды, необходимо использовать параметр **Definition**.</span><span class="sxs-lookup"><span data-stu-id="63f9e-130">If you want to find aliases for a command, you'll need to use the **Definition** parameter.</span></span>

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="63f9e-131">Параметр **Definition** не может использоваться позиционно, поэтому он должен быть задан.</span><span class="sxs-lookup"><span data-stu-id="63f9e-131">The **Definition** parameter can't be used positionally so it must be specified.</span></span>

<span data-ttu-id="63f9e-132">Псевдонимы ускоряют ввод значений и эффективны при вводе команд в консоль.</span><span class="sxs-lookup"><span data-stu-id="63f9e-132">Aliases can save you a few keystrokes and they're fine when you're typing commands into the console.</span></span>
<span data-ttu-id="63f9e-133">Их не следует использовать в сценариях или коде, который вы сохраняете или используете совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="63f9e-133">They shouldn't be used in scripts or any code that you're saving or sharing with others.</span></span> <span data-ttu-id="63f9e-134">Как говорилось ранее в этой книге, полные имена командлетов и параметров являются самодокументируемыми, что упрощает их понимание.</span><span class="sxs-lookup"><span data-stu-id="63f9e-134">As mentioned earlier in this book, using full cmdlet and parameter names is self-documenting and easier to understand.</span></span>

<span data-ttu-id="63f9e-135">Будьте внимательны при создании собственных псевдонимов, так как они будут существовать только в текущем сеансе PowerShell на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="63f9e-135">Use caution when creating your own aliases because they'll only exist in your current PowerShell session on your computer.</span></span>

## <a name="providers"></a><span data-ttu-id="63f9e-136">Поставщики</span><span class="sxs-lookup"><span data-stu-id="63f9e-136">Providers</span></span>

<span data-ttu-id="63f9e-137">Поставщик в PowerShell — это интерфейс, который позволяет файловой системе, например, получить доступ к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="63f9e-137">A provider in PowerShell is an interface that allows file system like access to a datastore.</span></span> <span data-ttu-id="63f9e-138">В PowerShell имеется ряд встроенных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="63f9e-138">There are a number of built-in providers in PowerShell.</span></span>

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

<span data-ttu-id="63f9e-139">Как видно в предыдущих результатах, существуют встроенные поставщики для реестра, псевдонимов, переменных среды, файловой системы, функций, переменных, сертификатов и WSMan.</span><span class="sxs-lookup"><span data-stu-id="63f9e-139">As you can see in the previous results, there are built-in providers for the registry, aliases, environment variables, the file system, functions, variables, certificates, and WSMan.</span></span>

<span data-ttu-id="63f9e-140">Фактические диски, используемые этими поставщиками для предоставления хранилища данных, можно определить с помощью командлета `Get-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-140">The actual drives that these providers use to expose their datastore can be determined with the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="63f9e-141">Командлет `Get-PSDrive` не только отображает диски, предоставляемые поставщиками, но и выводит логические диски Windows, включая диски, сопоставленные с сетевыми папками.</span><span class="sxs-lookup"><span data-stu-id="63f9e-141">The `Get-PSDrive` cmdlet not only displays drives exposed by providers, but it also displays Windows logical drives including drives mapped to network shares.</span></span>

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

<span data-ttu-id="63f9e-142">Сторонние модули, такие как модуль PowerShell для Active Directory и модуль PowerShell для SQL Server, имеют собственные поставщики PowerShell и PSDrive.</span><span class="sxs-lookup"><span data-stu-id="63f9e-142">Third-party modules such as the Active Directory PowerShell module and the SQLServer PowerShell module both add their own PowerShell provider and PSDrive.</span></span>

<span data-ttu-id="63f9e-143">Импортируем модули PowerShell для Active Directory и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63f9e-143">Import the Active Directory and SQL Server PowerShell modules.</span></span>

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

<span data-ttu-id="63f9e-144">Проверим, были ли добавлены дополнительные поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f9e-144">Check to see if any additional PowerShell providers were added.</span></span>

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

<span data-ttu-id="63f9e-145">Обратите внимание, что в предыдущем наборе результатов теперь существует два новых поставщика PowerShell: один для Active Directory и другой для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63f9e-145">Notice that in the previous set of results, two new PowerShell providers now exist, one for Active Directory and another one for SQL Server.</span></span>

<span data-ttu-id="63f9e-146">Для каждого из этих модулей также был добавлен диск PSDrive.</span><span class="sxs-lookup"><span data-stu-id="63f9e-146">A PSDrive for each of those modules was also added.</span></span>

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

<span data-ttu-id="63f9e-147">Доступ к дискам PSDrive осуществляется так же, как к традиционной файловой системе.</span><span class="sxs-lookup"><span data-stu-id="63f9e-147">PSDrives can be accessed just like a traditional file system.</span></span>

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

## <a name="comparison-operators"></a><span data-ttu-id="63f9e-148">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="63f9e-148">Comparison Operators</span></span>

<span data-ttu-id="63f9e-149">PowerShell содержит несколько операторов сравнения, которые используются для сравнения значений или поиска значений, соответствующих определенным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="63f9e-149">PowerShell contains a number of comparison operators that are used to compare values or find values that match certain patterns.</span></span> <span data-ttu-id="63f9e-150">В таблице 5-1 содержится список операторов сравнения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f9e-150">Table 5-1 contains a list of comparison operators in PowerShell.</span></span>

|    <span data-ttu-id="63f9e-151">Оператор</span><span class="sxs-lookup"><span data-stu-id="63f9e-151">Operator</span></span>    |                          <span data-ttu-id="63f9e-152">Определение</span><span class="sxs-lookup"><span data-stu-id="63f9e-152">Definition</span></span>                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | <span data-ttu-id="63f9e-153">Равно</span><span class="sxs-lookup"><span data-stu-id="63f9e-153">Equal to</span></span>                                                     |
| `-ne`          | <span data-ttu-id="63f9e-154">Не равно</span><span class="sxs-lookup"><span data-stu-id="63f9e-154">Not equal to</span></span>                                                 |
| `-gt`          | <span data-ttu-id="63f9e-155">Больше</span><span class="sxs-lookup"><span data-stu-id="63f9e-155">Greater than</span></span>                                                 |
| `-ge`          | <span data-ttu-id="63f9e-156">Больше или равно</span><span class="sxs-lookup"><span data-stu-id="63f9e-156">Greater than or equal to</span></span>                                     |
| `-lt`          | <span data-ttu-id="63f9e-157">Меньше чем</span><span class="sxs-lookup"><span data-stu-id="63f9e-157">Less than</span></span>                                                    |
| `-le`          | <span data-ttu-id="63f9e-158">Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="63f9e-158">Less than or equal to</span></span>                                        |
| `-Like`        | <span data-ttu-id="63f9e-159">Соответствие с использованием подстановочного знака `*`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-159">Match using the `*` wildcard character</span></span>                       |
| `-NotLike`     | <span data-ttu-id="63f9e-160">Несоответствие с использованием подстановочного знака `*`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-160">Does not match using the `*` wildcard character</span></span>              |
| `-Match`       | <span data-ttu-id="63f9e-161">Соответствует указному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="63f9e-161">Matches the specified regular expression</span></span>                     |
| `-NotMatch`    | <span data-ttu-id="63f9e-162">Не соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="63f9e-162">Does not match the specified regular expression</span></span>              |
| `-Contains`    | <span data-ttu-id="63f9e-163">Определяет, что коллекция содержит указанное значение.</span><span class="sxs-lookup"><span data-stu-id="63f9e-163">Determines if a collection contains a specified value</span></span>        |
| `-NotContains` | <span data-ttu-id="63f9e-164">Определяет, что коллекция не содержит указанное значение.</span><span class="sxs-lookup"><span data-stu-id="63f9e-164">Determines if a collection does not contain a specific value</span></span> |
| `-In`          | <span data-ttu-id="63f9e-165">Определяет, что указанное значение находится в коллекции.</span><span class="sxs-lookup"><span data-stu-id="63f9e-165">Determines if a specified value is in a collection</span></span>           |
| `-NotIn`       | <span data-ttu-id="63f9e-166">Определяет, что указанное значение не находится в коллекции.</span><span class="sxs-lookup"><span data-stu-id="63f9e-166">Determines if a specified value is not in a collection</span></span>       |
| `-Replace`     | <span data-ttu-id="63f9e-167">Заменяет указанное значение.</span><span class="sxs-lookup"><span data-stu-id="63f9e-167">Replaces the specified value</span></span>                                 |

<span data-ttu-id="63f9e-168">Все операторы, перечисленные в таблице 5-1, не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="63f9e-168">All of the operators listed in Table 5-1 are case-insensitive.</span></span> <span data-ttu-id="63f9e-169">Поместите `c` перед оператором, приведенным в таблице 5-1, чтобы сделать его чувствительным к регистру.</span><span class="sxs-lookup"><span data-stu-id="63f9e-169">Place a `c` in front of the operator listed in Table 5-1 to make it case-sensitive.</span></span> <span data-ttu-id="63f9e-170">Например, `-ceq` — это зависящая от регистра версия оператора сравнения `-eq`.</span><span class="sxs-lookup"><span data-stu-id="63f9e-170">For example, `-ceq` is the case-sensitive version of the `-eq` comparison operator.</span></span>

<span data-ttu-id="63f9e-171">Если используется оператор сравнения "равно", PowerShell в формате, где первая буква каждого слова прописная, а остальные строчные, соответствует powershell в нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="63f9e-171">Proper case "PowerShell" is equal to lower case "powershell" using the equals comparison operator.</span></span>

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

<span data-ttu-id="63f9e-172">Если используется зависящая от регистра версия оператора сравнения "равно", эти два значения не равны.</span><span class="sxs-lookup"><span data-stu-id="63f9e-172">It's not equal using the case-sensitive version of the equals comparison operator.</span></span>

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

<span data-ttu-id="63f9e-173">Оператор сравнения "не равно" изменяет условие на противоположное.</span><span class="sxs-lookup"><span data-stu-id="63f9e-173">The not equal comparison operator reverses the condition.</span></span>

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

<span data-ttu-id="63f9e-174">Операторы "больше", "больше или равно", "меньше", "меньше или равно" работают со строковыми или числовыми значениями.</span><span class="sxs-lookup"><span data-stu-id="63f9e-174">Greater than, greater than or equal to, less than, and less than or equal all work with string or numeric values.</span></span>

```powershell
5 -gt 5
```

```Output
False
```

<span data-ttu-id="63f9e-175">Если в предыдущем примере вместо оператора "больше" будет использоваться оператор "больше или равно", будет возвращено **логическое** значение True, так как пять равно пяти.</span><span class="sxs-lookup"><span data-stu-id="63f9e-175">Using greater than or equal to instead of greater than with the previous example returns the **Boolean** true since five is equal to five.</span></span>

```powershell
5 -ge 5
```

```Output
True
```

<span data-ttu-id="63f9e-176">На основе результатов из предыдущих двух примеров можно догадаться, как работают операторы "меньше" и "меньше или равно".</span><span class="sxs-lookup"><span data-stu-id="63f9e-176">Based on the results from the previous two examples, you can probably guess how both less than and less than or equal to work.</span></span>

```powershell
5 -lt 10
```

```Output
True
```

<span data-ttu-id="63f9e-177">Операторы `-Like` и `-Match` могут приводить в замешательство даже опытных пользователей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63f9e-177">The `-Like` and `-Match` operators can be confusing, even for experienced PowerShell users.</span></span> <span data-ttu-id="63f9e-178">`-Like` используется с подстановочными знаками `*` и `?` для выполнения совпадений с указанным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="63f9e-178">`-Like` is used with wildcard the characters `*` and `?` to perform "like" matches.</span></span>

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

<span data-ttu-id="63f9e-179">`-Match` использует регулярное выражение для выполнения сопоставления.</span><span class="sxs-lookup"><span data-stu-id="63f9e-179">`-Match` uses a regular expression to perform the matching.</span></span>

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

<span data-ttu-id="63f9e-180">Для сохранения чисел с 1 по 10 в переменной воспользуемся оператором диапазона.</span><span class="sxs-lookup"><span data-stu-id="63f9e-180">Use the range operator to store the numbers 1 through 10 in a variable.</span></span>

```powershell
$Numbers = 1..10
```

```Output
```

<span data-ttu-id="63f9e-181">Определим, содержит ли переменная `$Numbers` число 15.</span><span class="sxs-lookup"><span data-stu-id="63f9e-181">Determine if the `$Numbers` variable includes 15.</span></span>

```powershell
$Numbers -contains 15
```

```Output
False
```

<span data-ttu-id="63f9e-182">Определим, содержит ли она число 10.</span><span class="sxs-lookup"><span data-stu-id="63f9e-182">Determine if it includes the number 10.</span></span>

```powershell
$Numbers -contains 10
```

```Output
True
```

<span data-ttu-id="63f9e-183">`-NotContains` изменяет логику на противоположную, чтобы проверить, что переменная `$Numbers` не содержит значение.</span><span class="sxs-lookup"><span data-stu-id="63f9e-183">`-NotContains` reverses the logic to see if the `$Numbers` variable doesn't contain a value.</span></span>

```powershell
$Numbers -notcontains 15
```

```Output
True
```

<span data-ttu-id="63f9e-184">В предыдущем примере возвращается **логическое** значение True, поскольку переменная `$Numbers` не содержит число 15.</span><span class="sxs-lookup"><span data-stu-id="63f9e-184">The previous example returns the **Boolean** true because it's true that the `$Numbers` variable doesn't contain 15.</span></span> <span data-ttu-id="63f9e-185">Однако она содержит число 10, поэтому при тестировании получим False.</span><span class="sxs-lookup"><span data-stu-id="63f9e-185">It does however contain the number 10 so it's false when it's tested.</span></span>

```powershell
$Numbers -notcontains 10
```

```Output
False
```

<span data-ttu-id="63f9e-186">Оператор сравнения in впервые появился в PowerShell версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="63f9e-186">The "in" comparison operator was first introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="63f9e-187">Он используется, чтобы определить, находится ли значение в массиве.</span><span class="sxs-lookup"><span data-stu-id="63f9e-187">It's used to determine if a value is "in" an array.</span></span> <span data-ttu-id="63f9e-188">`$Numbers` переменная находится в массиве, так как он содержит несколько значений.</span><span class="sxs-lookup"><span data-stu-id="63f9e-188">The `$Numbers` variable is an array since it contains multiple values.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="63f9e-189">Другими словами, `-in` выполняет ту же проверку, что и оператор сравнения contains, за исключением того, что действие происходит в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="63f9e-189">In other words, `-in` performs the same test as the contains comparison operator except from the opposite direction.</span></span>

```powershell
10 -in $Numbers
```

```Output
True
```

<span data-ttu-id="63f9e-190">15 не находится в массиве `$Numbers`, поэтому в следующем примере возвращается значение False.</span><span class="sxs-lookup"><span data-stu-id="63f9e-190">15 isn't in the `$Numbers` array so false is returned in the following example.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="63f9e-191">Точно так же, как оператор `-contains`, `not` меняет логику оператора `-in` на обратную.</span><span class="sxs-lookup"><span data-stu-id="63f9e-191">Just like the `-contains` operator, `not` reverses the logic for the `-in` operator.</span></span>

```powershell
10 -notin $Numbers
```

```Output
False
```

<span data-ttu-id="63f9e-192">В предыдущем примере возвращается значение False, поскольку массив `$Numbers` содержит число 10, а условием было проверить, что он не содержит число 10.</span><span class="sxs-lookup"><span data-stu-id="63f9e-192">The previous example returns false because the `$Numbers` array does include 10 and the condition was testing to determine if it didn't contain 10.</span></span>

<span data-ttu-id="63f9e-193">15 не находится в массиве `$Numbers`, поэтому возвращается **логическое** значение True.</span><span class="sxs-lookup"><span data-stu-id="63f9e-193">15 is "not in" the `$Numbers` array so it returns the **Boolean** true.</span></span>

```powershell
15 -notin $Numbers
```

```Output
True
```

<span data-ttu-id="63f9e-194">Оператор `-replace` делает то, что вы думаете.</span><span class="sxs-lookup"><span data-stu-id="63f9e-194">The `-replace` operator does just want you would think.</span></span> <span data-ttu-id="63f9e-195">Он используется для замены чего-либо.</span><span class="sxs-lookup"><span data-stu-id="63f9e-195">It's used to replace something.</span></span> <span data-ttu-id="63f9e-196">При указании одного значения это значение заменяется пустым (т. е. ничем).</span><span class="sxs-lookup"><span data-stu-id="63f9e-196">Specifying one value replaces that value with nothing.</span></span> <span data-ttu-id="63f9e-197">В следующем примере Shell заменяется пустым значением.</span><span class="sxs-lookup"><span data-stu-id="63f9e-197">In the following example, I replace "Shell" with nothing.</span></span>

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

<span data-ttu-id="63f9e-198">Если вы хотите заменить значение другим значением, укажите новое значение после шаблона, который требуется заменить.</span><span class="sxs-lookup"><span data-stu-id="63f9e-198">If you want to replace a value with a different value, specify the new value after the pattern you want to replace.</span></span> <span data-ttu-id="63f9e-199">SQL Saturday in Baton Rouge — это мероприятие, в котором я стараюсь принимать участие каждый год.</span><span class="sxs-lookup"><span data-stu-id="63f9e-199">SQL Saturday in Baton Rouge is an event that I try to speak at every year.</span></span> <span data-ttu-id="63f9e-200">В следующем примере я заменяю слово Saturday на сокращение Sat.</span><span class="sxs-lookup"><span data-stu-id="63f9e-200">In the following example, I replace the word "Saturday" with the abbreviation "Sat".</span></span>

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="63f9e-201">Существуют также такие методы, как **Replace()** , которые можно использовать для замены точно так же, как оператор замены.</span><span class="sxs-lookup"><span data-stu-id="63f9e-201">There are also methods like **Replace()** that can be used to replace things similar to the way the replace operator works.</span></span> <span data-ttu-id="63f9e-202">Однако оператор `-Replace` не учитывает регистр по умолчанию, а метод **Replace()** зависит от регистра.</span><span class="sxs-lookup"><span data-stu-id="63f9e-202">However, the `-Replace` operator is case-insensitive by default, and the **Replace()** method is case-sensitive.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

<span data-ttu-id="63f9e-203">Обратите внимание, что слово Saturday не было заменено в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="63f9e-203">Notice that the word "Saturday" wasn't replaced in the previous example.</span></span> <span data-ttu-id="63f9e-204">Это обусловлено тем, что оно было указано в другом регистре, чем исходное слово.</span><span class="sxs-lookup"><span data-stu-id="63f9e-204">This is because it was specified in a different case than the original.</span></span> <span data-ttu-id="63f9e-205">Если слово Saturday задается в том же регистре, что и исходное, метод **Replace()** заменяет его ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="63f9e-205">When the word "Saturday" is specified in the same case as the original, the **Replace()** method does replace it as expected.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="63f9e-206">При использовании методов для преобразования данных следует соблюдать осторожность, так как могут возникнуть непредвиденные проблемы, такие как непрохождение _турецкого теста_.</span><span class="sxs-lookup"><span data-stu-id="63f9e-206">Be careful when using methods to transform data because you can run into unforeseen problems, such as failing the _Turkey Test_.</span></span> <span data-ttu-id="63f9e-207">Пример см. в статье блога [Using Pester to Test PowerShell Code with Other Cultures][].</span><span class="sxs-lookup"><span data-stu-id="63f9e-207">For an example, see the blog article titled [Using Pester to Test PowerShell Code with Other Cultures][].</span></span> <span data-ttu-id="63f9e-208">Чтобы избежать проблем такого типа, рекомендуется по возможности использовать оператор вместо метода.</span><span class="sxs-lookup"><span data-stu-id="63f9e-208">My recommendation is to use an operator instead of a method whenever possible to avoid these types of problems.</span></span>

<span data-ttu-id="63f9e-209">Несмотря на то что операторы сравнения можно использовать, как показано в предыдущих примерах, обычно я применяю их с командлетом `Where-Object` для выполнения фильтрации.</span><span class="sxs-lookup"><span data-stu-id="63f9e-209">While the comparison operators can be used as shown in the previous examples, I normally find myself using them with the `Where-Object` cmdlet to perform some type of filtering.</span></span>

## <a name="summary"></a><span data-ttu-id="63f9e-210">Сводка</span><span class="sxs-lookup"><span data-stu-id="63f9e-210">Summary</span></span>

<span data-ttu-id="63f9e-211">В этой главе вы узнали, как выполнять форматирование как можно ближе к правому краю, как использовать псевдонимы, поставщики и операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="63f9e-211">In this chapter, you've learned a number of different topics to include Formatting Right, Aliases, Providers, and Comparison Operators.</span></span>

## <a name="review"></a><span data-ttu-id="63f9e-212">Просмотр</span><span class="sxs-lookup"><span data-stu-id="63f9e-212">Review</span></span>

1. <span data-ttu-id="63f9e-213">Для чего нужно выполнять форматирование как можно ближе к правому краю?</span><span class="sxs-lookup"><span data-stu-id="63f9e-213">Why is it necessary to perform Formatting as far to the right as possible?</span></span>
1. <span data-ttu-id="63f9e-214">Как определить фактический командлет для псевдонима `%`?</span><span class="sxs-lookup"><span data-stu-id="63f9e-214">How do you determine what the actual cmdlet is for the `%` alias?</span></span>
1. <span data-ttu-id="63f9e-215">Почему не следует использовать псевдонимы в сценариях, которые вы сохраняете, или коде, используемом совместно с другими пользователями?</span><span class="sxs-lookup"><span data-stu-id="63f9e-215">Why shouldn't you use aliases in scripts you save or code you share with others?</span></span>
1. <span data-ttu-id="63f9e-216">Выведите список каталогов на дисках, связанных с одним из поставщиков реестра.</span><span class="sxs-lookup"><span data-stu-id="63f9e-216">Perform a directory listing on the drives that are associated with one of the registry providers.</span></span>
1. <span data-ttu-id="63f9e-217">В чем заключается одно из основных преимуществ использования оператора замены вместо метода замены?</span><span class="sxs-lookup"><span data-stu-id="63f9e-217">What's one of the main benefits of using the replace operator instead of the replace method?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="63f9e-218">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="63f9e-218">Recommended Reading</span></span>

- <span data-ttu-id="63f9e-219">[Format-Table][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-219">[Format-Table][]</span></span>
- <span data-ttu-id="63f9e-220">[Format-List][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-220">[Format-List][]</span></span>
- <span data-ttu-id="63f9e-221">[Format-Wide][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-221">[Format-Wide][]</span></span>
- <span data-ttu-id="63f9e-222">[about_Aliases][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-222">[about_Aliases][]</span></span>
- <span data-ttu-id="63f9e-223">[about_Providers][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-223">[about_Providers][]</span></span>
- <span data-ttu-id="63f9e-224">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-224">[about_Comparison_Operators][]</span></span>
- <span data-ttu-id="63f9e-225">[about_Arrays][]</span><span class="sxs-lookup"><span data-stu-id="63f9e-225">[about_Arrays][]</span></span>

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

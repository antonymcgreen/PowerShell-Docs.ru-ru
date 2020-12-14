---
description: Позволяет указать, какие пространства имен используются в сеансе.
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: b48cd85e200f44cdf9fdf278de78e07a918386c8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891352"
---
# <a name="about-using"></a><span data-ttu-id="18b5b-103">Об использовании</span><span class="sxs-lookup"><span data-stu-id="18b5b-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="18b5b-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="18b5b-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="18b5b-105">Позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="18b5b-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="18b5b-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="18b5b-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="18b5b-107">`using`Инструкция позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="18b5b-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="18b5b-108">Добавление пространств имен упрощает использование классов и членов .NET и позволяет импортировать классы из модулей скриптов и сборок.</span><span class="sxs-lookup"><span data-stu-id="18b5b-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="18b5b-109">`using`Операторы должны располагаться перед любыми другими инструкциями в скрипте.</span><span class="sxs-lookup"><span data-stu-id="18b5b-109">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="18b5b-110">`using`Оператор не следует путать с `using:` модификатором области для переменных.</span><span class="sxs-lookup"><span data-stu-id="18b5b-110">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="18b5b-111">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="18b5b-111">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="18b5b-112">Синтаксис пространства имен</span><span class="sxs-lookup"><span data-stu-id="18b5b-112">Namespace syntax</span></span>

<span data-ttu-id="18b5b-113">Чтобы указать пространства имен .NET, из которых следует разрешить типы:</span><span class="sxs-lookup"><span data-stu-id="18b5b-113">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="18b5b-114">Указание пространства имен упрощает ссылки на типы по их коротким именам.</span><span class="sxs-lookup"><span data-stu-id="18b5b-114">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="18b5b-115">Синтаксис модуля</span><span class="sxs-lookup"><span data-stu-id="18b5b-115">Module syntax</span></span>

<span data-ttu-id="18b5b-116">Чтобы загрузить классы из модуля PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="18b5b-116">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="18b5b-117">Значением `<module-name>` может быть имя модуля, полная спецификация модуля или путь к файлу модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-117">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="18b5b-118">Если `<module-name>` является путем, путь может быть полным или относительным.</span><span class="sxs-lookup"><span data-stu-id="18b5b-118">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="18b5b-119">Относительный путь разрешается относительно скрипта, содержащего инструкцию using.</span><span class="sxs-lookup"><span data-stu-id="18b5b-119">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="18b5b-120">Если `<module-name>` является спецификацией имени или модуля, PowerShell выполняет поиск в **PSModulePath** для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-120">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="18b5b-121">Спецификация модуля — это хэш-таблица, которая содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="18b5b-121">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="18b5b-122">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-122">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="18b5b-123">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-123">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="18b5b-124">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="18b5b-124">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="18b5b-125">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="18b5b-125">These keys can't be used together.</span></span>
  - <span data-ttu-id="18b5b-126">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-126">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="18b5b-127">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-127">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="18b5b-128">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="18b5b-128">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="18b5b-129">Синтаксис сборки</span><span class="sxs-lookup"><span data-stu-id="18b5b-129">Assembly syntax</span></span>

<span data-ttu-id="18b5b-130">Предварительная загрузка типов из сборки .NET:</span><span class="sxs-lookup"><span data-stu-id="18b5b-130">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
using assembly <.NET-namespace>
```

<span data-ttu-id="18b5b-131">При загрузке сборки выгружаются типы .NET из этой сборки в скрипт во время синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="18b5b-131">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="18b5b-132">Это позволяет создавать новые классы PowerShell, использующие типы из предварительно загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="18b5b-132">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="18b5b-133">В Windows PowerShell 5,1 можно загрузить сборку по имени пути или по имени.</span><span class="sxs-lookup"><span data-stu-id="18b5b-133">In Windows PowerShell 5.1 you can load the assembly by path name or by name.</span></span> <span data-ttu-id="18b5b-134">При использовании имени PowerShell выполняет поиск соответствующей сборки в глобальном кэше сборок (GAC) .NET.</span><span class="sxs-lookup"><span data-stu-id="18b5b-134">When you use the name, PowerShell searches the .NET Global Assembly Cache (GAC) for the associated assembly.</span></span>

<span data-ttu-id="18b5b-135">Если вы не создаете новые классы PowerShell, используйте `Add-Type` вместо этого командлет.</span><span class="sxs-lookup"><span data-stu-id="18b5b-135">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="18b5b-136">Дополнительные сведения см. в разделе [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="18b5b-136">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="18b5b-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="18b5b-137">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="18b5b-138">Пример 1. Добавление пространств имен для разрешения имени TypeName</span><span class="sxs-lookup"><span data-stu-id="18b5b-138">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="18b5b-139">Следующий скрипт получает криптографический хэш для строки "Hello World".</span><span class="sxs-lookup"><span data-stu-id="18b5b-139">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="18b5b-140">Обратите внимание, что `using namespace System.Text` и `using namespace System.IO` упрощает ссылки на `[UnicodeEncoding]` в и и в `System.Text` `[Stream]` `[MemoryStream]` `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="18b5b-140">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="18b5b-141">Пример 2. Загрузка классов из модуля скрипта</span><span class="sxs-lookup"><span data-stu-id="18b5b-141">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="18b5b-142">В этом примере у нас есть модуль скрипта PowerShell с именем **кардгамес** , который определяет следующие классы:</span><span class="sxs-lookup"><span data-stu-id="18b5b-142">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="18b5b-143">**Кардгамес. колода**</span><span class="sxs-lookup"><span data-stu-id="18b5b-143">**CardGames.Deck**</span></span>
- <span data-ttu-id="18b5b-144">**Кардгамес. Card**</span><span class="sxs-lookup"><span data-stu-id="18b5b-144">**CardGames.Card**</span></span>

<span data-ttu-id="18b5b-145">`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем.</span><span class="sxs-lookup"><span data-stu-id="18b5b-145">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="18b5b-146">Классы не импортируются.</span><span class="sxs-lookup"><span data-stu-id="18b5b-146">Classes are not imported.</span></span> <span data-ttu-id="18b5b-147">`using module`Команда импортирует модуль, а также загружает определения классов.</span><span class="sxs-lookup"><span data-stu-id="18b5b-147">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="18b5b-148">Пример 3. Загрузка классов из сборки</span><span class="sxs-lookup"><span data-stu-id="18b5b-148">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="18b5b-149">В этом примере загружается сборка, чтобы ее классы можно было использовать для создания новых классов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18b5b-149">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="18b5b-150">Следующий скрипт создает новый класс PowerShell, производный от класса **директориконтекст** .</span><span class="sxs-lookup"><span data-stu-id="18b5b-150">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```

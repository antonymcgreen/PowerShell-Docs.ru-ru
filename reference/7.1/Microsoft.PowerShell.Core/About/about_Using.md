---
description: Позволяет указать, какие пространства имен используются в сеансе.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: eaf983ad03676b4ac57a3b35bc44f72036da55b4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231829"
---
# <a name="about-using"></a><span data-ttu-id="1c60b-104">Об использовании</span><span class="sxs-lookup"><span data-stu-id="1c60b-104">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="1c60b-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1c60b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1c60b-106">Позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1c60b-106">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="1c60b-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1c60b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1c60b-108">`using`Инструкция позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1c60b-108">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="1c60b-109">Добавление пространств имен упрощает использование классов и членов .NET и позволяет импортировать классы из модулей скриптов и сборок.</span><span class="sxs-lookup"><span data-stu-id="1c60b-109">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="1c60b-110">`using`Операторы должны располагаться перед любыми другими инструкциями в скрипте.</span><span class="sxs-lookup"><span data-stu-id="1c60b-110">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="1c60b-111">`using`Оператор не следует путать с `using:` модификатором области для переменных.</span><span class="sxs-lookup"><span data-stu-id="1c60b-111">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="1c60b-112">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="1c60b-112">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1c60b-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c60b-113">Syntax</span></span>

<span data-ttu-id="1c60b-114">Чтобы указать пространства имен .NET, из которых следует разрешить типы:</span><span class="sxs-lookup"><span data-stu-id="1c60b-114">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="1c60b-115">Чтобы загрузить классы из модуля PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1c60b-115">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="1c60b-116">Предварительная загрузка типов из сборки .NET:</span><span class="sxs-lookup"><span data-stu-id="1c60b-116">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="1c60b-117">Указание пространства имен упрощает ссылки на типы по их коротким именам.</span><span class="sxs-lookup"><span data-stu-id="1c60b-117">Specifying a namespace makes it easier to reference types by their short names.</span></span>

<span data-ttu-id="1c60b-118">При загрузке сборки выгружаются типы .NET из этой сборки в скрипт во время синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="1c60b-118">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="1c60b-119">Это позволяет создавать новые классы PowerShell, использующие типы из предварительно загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="1c60b-119">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="1c60b-120">Если вы не создаете новые классы PowerShell, используйте `Add-Type` вместо этого командлет.</span><span class="sxs-lookup"><span data-stu-id="1c60b-120">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="1c60b-121">Дополнительные сведения см. в разделе [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="1c60b-121">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="1c60b-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="1c60b-122">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="1c60b-123">Пример 1. Добавление пространств имен для разрешения имени TypeName</span><span class="sxs-lookup"><span data-stu-id="1c60b-123">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="1c60b-124">Следующий скрипт получает криптографический хэш для строки "Hello World".</span><span class="sxs-lookup"><span data-stu-id="1c60b-124">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="1c60b-125">Обратите внимание, что `using namespace System.Text` и `using namespace System.IO` упрощает ссылки на `[UnicodeEncoding]` в и и в `System.Text` `[Stream]` `[MemoryStream]` `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="1c60b-125">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="1c60b-126">Пример 2. Загрузка классов из модуля скрипта</span><span class="sxs-lookup"><span data-stu-id="1c60b-126">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="1c60b-127">В этом примере у нас есть модуль скрипта PowerShell с именем **кардгамес** , который определяет следующие классы:</span><span class="sxs-lookup"><span data-stu-id="1c60b-127">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="1c60b-128">**Кардгамес. колода**</span><span class="sxs-lookup"><span data-stu-id="1c60b-128">**CardGames.Deck**</span></span>
- <span data-ttu-id="1c60b-129">**Кардгамес. Card**</span><span class="sxs-lookup"><span data-stu-id="1c60b-129">**CardGames.Card**</span></span>

<span data-ttu-id="1c60b-130">`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем.</span><span class="sxs-lookup"><span data-stu-id="1c60b-130">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="1c60b-131">Классы не импортируются.</span><span class="sxs-lookup"><span data-stu-id="1c60b-131">Classes are not imported.</span></span> <span data-ttu-id="1c60b-132">`using module`Команда импортирует модуль, а также загружает определения классов.</span><span class="sxs-lookup"><span data-stu-id="1c60b-132">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="1c60b-133">Пример 3. Загрузка классов из сборки</span><span class="sxs-lookup"><span data-stu-id="1c60b-133">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="1c60b-134">В этом примере загружается сборка, чтобы ее классы можно было использовать для создания новых классов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c60b-134">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="1c60b-135">Следующий скрипт создает новый класс PowerShell, производный от класса **директориконтекст** .</span><span class="sxs-lookup"><span data-stu-id="1c60b-135">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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


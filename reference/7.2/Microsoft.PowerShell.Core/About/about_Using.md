---
description: Позволяет указать, какие пространства имен используются в сеансе.
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: ba3833f522265ad240d376b07c5add393c4b2721
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "99603115"
---
# <a name="about-using"></a><span data-ttu-id="c2f03-103">Об использовании</span><span class="sxs-lookup"><span data-stu-id="c2f03-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="c2f03-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c2f03-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c2f03-105">Позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c2f03-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="c2f03-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c2f03-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="c2f03-107">`using`Инструкция позволяет указать, какие пространства имен используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c2f03-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="c2f03-108">Добавление пространств имен упрощает использование классов и членов .NET и позволяет импортировать классы из модулей скриптов и сборок.</span><span class="sxs-lookup"><span data-stu-id="c2f03-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="c2f03-109">`using`Операторы должны располагаться перед любыми другими инструкциями в скрипте или модуле.</span><span class="sxs-lookup"><span data-stu-id="c2f03-109">The `using` statements must come before any other statements in a script or module.</span></span> <span data-ttu-id="c2f03-110">Ни один оператор без комментариев не может предшествовать ему, включая параметры.</span><span class="sxs-lookup"><span data-stu-id="c2f03-110">No uncommented statement can precede it, including parameters.</span></span>

<span data-ttu-id="c2f03-111">`using`Инструкция не должна содержать переменных.</span><span class="sxs-lookup"><span data-stu-id="c2f03-111">The `using` statement must not contain any variables.</span></span>

<span data-ttu-id="c2f03-112">`using`Оператор не следует путать с `using:` модификатором области для переменных.</span><span class="sxs-lookup"><span data-stu-id="c2f03-112">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="c2f03-113">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2f03-113">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="c2f03-114">Синтаксис пространства имен</span><span class="sxs-lookup"><span data-stu-id="c2f03-114">Namespace syntax</span></span>

<span data-ttu-id="c2f03-115">Чтобы указать пространства имен .NET, из которых следует разрешить типы:</span><span class="sxs-lookup"><span data-stu-id="c2f03-115">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="c2f03-116">Указание пространства имен упрощает ссылки на типы по их коротким именам.</span><span class="sxs-lookup"><span data-stu-id="c2f03-116">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="c2f03-117">Синтаксис модуля</span><span class="sxs-lookup"><span data-stu-id="c2f03-117">Module syntax</span></span>

<span data-ttu-id="c2f03-118">Чтобы загрузить классы из модуля PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c2f03-118">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="c2f03-119">Значением `<module-name>` может быть имя модуля, полная спецификация модуля или путь к файлу модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-119">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="c2f03-120">Если `<module-name>` является путем, путь может быть полным или относительным.</span><span class="sxs-lookup"><span data-stu-id="c2f03-120">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="c2f03-121">Относительный путь разрешается относительно скрипта, содержащего инструкцию using.</span><span class="sxs-lookup"><span data-stu-id="c2f03-121">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="c2f03-122">Если `<module-name>` является спецификацией имени или модуля, PowerShell выполняет поиск в **PSModulePath** для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-122">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="c2f03-123">Спецификация модуля — это хэш-таблица, которая содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="c2f03-123">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="c2f03-124">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-124">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="c2f03-125">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-125">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="c2f03-126">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="c2f03-126">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="c2f03-127">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="c2f03-127">These keys can't be used together.</span></span>
  - <span data-ttu-id="c2f03-128">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-128">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="c2f03-129">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-129">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="c2f03-130">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-130">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

<span data-ttu-id="c2f03-131">`using module`Оператор импортирует классы из корневого модуля ( `ModuleToProcess` ) модуля скрипта или двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="c2f03-131">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="c2f03-132">Он не выполняет согласованный импорт классов, определенных во вложенных модулях или классах, определенных в скриптах, которые являются точками, источником которых является модуль.</span><span class="sxs-lookup"><span data-stu-id="c2f03-132">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="c2f03-133">Классы, которые должны быть доступны пользователям за пределами модуля, должны быть определены в корневом модуле.</span><span class="sxs-lookup"><span data-stu-id="c2f03-133">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

<span data-ttu-id="c2f03-134">Во время разработки модуля скрипта часто вносятся изменения в код, а затем загружается новая версия модуля `Import-Module` с параметром **Force** .</span><span class="sxs-lookup"><span data-stu-id="c2f03-134">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="c2f03-135">Это применимо только к изменениям функций в корневом модуле.</span><span class="sxs-lookup"><span data-stu-id="c2f03-135">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="c2f03-136">`Import-Module` не перезагружает вложенные модули.</span><span class="sxs-lookup"><span data-stu-id="c2f03-136">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="c2f03-137">Кроме того, не существует способа загрузить обновленные классы.</span><span class="sxs-lookup"><span data-stu-id="c2f03-137">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="c2f03-138">Чтобы убедиться, что вы используете последнюю версию, необходимо выгрузить модуль с помощью `Remove-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="c2f03-138">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="c2f03-139">`Remove-Module` Удаляет корневой модуль, все вложенные модули и все классы, определенные в модулях.</span><span class="sxs-lookup"><span data-stu-id="c2f03-139">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="c2f03-140">Затем можно перезагрузить модуль и классы с помощью `Import-Module` и `using module` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c2f03-140">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="c2f03-141">Синтаксис сборки</span><span class="sxs-lookup"><span data-stu-id="c2f03-141">Assembly syntax</span></span>

<span data-ttu-id="c2f03-142">Предварительная загрузка типов из сборки .NET:</span><span class="sxs-lookup"><span data-stu-id="c2f03-142">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="c2f03-143">При загрузке сборки выгружаются типы .NET из этой сборки в скрипт во время синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="c2f03-143">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="c2f03-144">Это позволяет создавать новые классы PowerShell, использующие типы из предварительно загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="c2f03-144">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="c2f03-145">Если вы не создаете новые классы PowerShell, используйте `Add-Type` вместо этого командлет.</span><span class="sxs-lookup"><span data-stu-id="c2f03-145">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="c2f03-146">Дополнительные сведения см. в разделе [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="c2f03-146">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="c2f03-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="c2f03-147">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="c2f03-148">Пример 1. Добавление пространств имен для разрешения имени TypeName</span><span class="sxs-lookup"><span data-stu-id="c2f03-148">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="c2f03-149">Следующий скрипт получает криптографический хэш для строки "Hello World".</span><span class="sxs-lookup"><span data-stu-id="c2f03-149">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="c2f03-150">Обратите внимание, что `using namespace System.Text` и `using namespace System.IO` упрощает ссылки на `[UnicodeEncoding]` в и и в `System.Text` `[Stream]` `[MemoryStream]` `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="c2f03-150">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="c2f03-151">Пример 2. Загрузка классов из модуля скрипта</span><span class="sxs-lookup"><span data-stu-id="c2f03-151">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="c2f03-152">В этом примере у нас есть модуль скрипта PowerShell с именем **кардгамес** , который определяет следующие классы:</span><span class="sxs-lookup"><span data-stu-id="c2f03-152">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="c2f03-153">**Кардгамес. колода**</span><span class="sxs-lookup"><span data-stu-id="c2f03-153">**CardGames.Deck**</span></span>
- <span data-ttu-id="c2f03-154">**Кардгамес. Card**</span><span class="sxs-lookup"><span data-stu-id="c2f03-154">**CardGames.Card**</span></span>

<span data-ttu-id="c2f03-155">`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем.</span><span class="sxs-lookup"><span data-stu-id="c2f03-155">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="c2f03-156">Классы не импортируются.</span><span class="sxs-lookup"><span data-stu-id="c2f03-156">Classes are not imported.</span></span> <span data-ttu-id="c2f03-157">`using module`Команда импортирует модуль, а также загружает определения классов.</span><span class="sxs-lookup"><span data-stu-id="c2f03-157">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="c2f03-158">Пример 3. Загрузка классов из сборки</span><span class="sxs-lookup"><span data-stu-id="c2f03-158">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="c2f03-159">В этом примере загружается сборка, чтобы ее классы можно было использовать для создания новых классов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2f03-159">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="c2f03-160">Следующий скрипт создает новый класс PowerShell, производный от класса **директориконтекст** .</span><span class="sxs-lookup"><span data-stu-id="c2f03-160">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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

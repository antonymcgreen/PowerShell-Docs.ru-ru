---
ms.date: 07/29/2020
title: Новые возможности языка в PowerShell 5.0
ms.openlocfilehash: dada39c4121a810c7ce87a642f232934152104e5
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410178"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="5be94-102">Новые возможности языка в PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5be94-102">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="5be94-103">В PowerShell 5.0 появилась возможность определения классов и других определяемых пользователем типов с использованием формального синтаксиса и семантики, как и в других объектно-ориентированных языках программирования.</span><span class="sxs-lookup"><span data-stu-id="5be94-103">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="5be94-104">Целью этого шага является расширение вариантов использования PowerShell, доступных разработчикам и ИТ-специалистам, упрощение разработки артефактов PowerShell (например, ресурсов DSC) и ускорение освоения поверхностей управления.</span><span class="sxs-lookup"><span data-stu-id="5be94-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

<span data-ttu-id="5be94-105">В PowerShell 5.0 появились следующие новые элементы языка для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5be94-105">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="5be94-106">Ключевое слово Class</span><span class="sxs-lookup"><span data-stu-id="5be94-106">Class keyword</span></span>

<span data-ttu-id="5be94-107">Ключевое слово `class` определяет новый класс.</span><span class="sxs-lookup"><span data-stu-id="5be94-107">The `class` keyword defines a new class.</span></span> <span data-ttu-id="5be94-108">Это подлинный тип .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5be94-108">This is a true .NET Framework type.</span></span> <span data-ttu-id="5be94-109">Члены класса являются открытыми, но только в рамках области модуля.</span><span class="sxs-lookup"><span data-stu-id="5be94-109">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="5be94-110">Вы не можете ссылаться на имя типа в виде строки (например, `New-Object` не работает), а также использовать литерал типа (например, `[MyClass]`) за пределами файла скрипта или модуля, где определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="5be94-110">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="5be94-111">Ключевое слово Enum и перечисления</span><span class="sxs-lookup"><span data-stu-id="5be94-111">Enum keyword and enumerations</span></span>

<span data-ttu-id="5be94-112">Добавлена поддержка ключевого слова `enum`, где символ новой строки используется в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="5be94-112">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="5be94-113">Сейчас нельзя определить перечислитель относительно самого себя.</span><span class="sxs-lookup"><span data-stu-id="5be94-113">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="5be94-114">Тем не менее перечисление можно инициализировать относительно другого перечисления, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5be94-114">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="5be94-115">Кроме того, нельзя задать базовый тип (всегда `[int]`).</span><span class="sxs-lookup"><span data-stu-id="5be94-115">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="5be94-116">Значение перечислителя должно быть константой времени анализа.</span><span class="sxs-lookup"><span data-stu-id="5be94-116">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="5be94-117">Его нельзя задать как результат вызванной команды.</span><span class="sxs-lookup"><span data-stu-id="5be94-117">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="5be94-118">Перечисления поддерживают арифметические операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5be94-118">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="5be94-119">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="5be94-119">Import-DscResource</span></span>

<span data-ttu-id="5be94-120">Теперь `Import-DscResource` — это динамическое ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="5be94-120">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="5be94-121">PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут **DscResource**.</span><span class="sxs-lookup"><span data-stu-id="5be94-121">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="5be94-122">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="5be94-122">ImplementingAssembly</span></span>

<span data-ttu-id="5be94-123">В **ModuleInfo** добавлено новое поле **ImplementingAssembly**.</span><span class="sxs-lookup"><span data-stu-id="5be94-123">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="5be94-124">Ему присваивается динамическая сборка, созданная для модуля сценариев, если скрипт определяет классы, или загруженная сборка для двоичных модулей.</span><span class="sxs-lookup"><span data-stu-id="5be94-124">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="5be94-125">Оно не задано, когда **ModuleType** имеет значение **Manifest**.</span><span class="sxs-lookup"><span data-stu-id="5be94-125">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="5be94-126">Отражение поля **ImplementingAssembly** обнаруживает ресурсы в модуле.</span><span class="sxs-lookup"><span data-stu-id="5be94-126">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="5be94-127">Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.</span><span class="sxs-lookup"><span data-stu-id="5be94-127">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

## <a name="further-reading"></a><span data-ttu-id="5be94-128">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5be94-128">Further reading</span></span>

- [<span data-ttu-id="5be94-129">about_Classes</span><span class="sxs-lookup"><span data-stu-id="5be94-129">about_Classes</span></span>](/powershell/module/microsoft.powershell.core/about/about_classes)
- [<span data-ttu-id="5be94-130">about_Enum</span><span class="sxs-lookup"><span data-stu-id="5be94-130">about_Enum</span></span>](/powershell/module/microsoft.powershell.core/about/about_enum)
- [<span data-ttu-id="5be94-131">about_Classes_and_DSC</span><span class="sxs-lookup"><span data-stu-id="5be94-131">about_Classes_and_DSC</span></span>](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)

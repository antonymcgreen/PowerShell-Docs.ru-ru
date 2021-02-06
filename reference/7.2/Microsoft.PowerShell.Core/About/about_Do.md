---
description: Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: 412a13669e86df5804dd74d75fcb5b4389192c79
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604733"
---
# <a name="about-do"></a><span data-ttu-id="987b9-103">О Do</span><span class="sxs-lookup"><span data-stu-id="987b9-103">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="987b9-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="987b9-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="987b9-105">Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.</span><span class="sxs-lookup"><span data-stu-id="987b9-105">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="987b9-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="987b9-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="987b9-107">Ключевое слово do работает с ключевым словом While или ключевым словом Until для выполнения инструкций в блоке скрипта в соответствии с условием.</span><span class="sxs-lookup"><span data-stu-id="987b9-107">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="987b9-108">В отличие от связанного цикла while, блок сценария в цикле Do всегда выполняется по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="987b9-108">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="987b9-109">Цикл **do-while** — это множество циклов while.</span><span class="sxs-lookup"><span data-stu-id="987b9-109">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="987b9-110">В цикле **do-while** условие вычисляется после выполнения блока script.</span><span class="sxs-lookup"><span data-stu-id="987b9-110">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="987b9-111">Как и в цикле while, блок скрипта повторяется, пока условие принимает значение true.</span><span class="sxs-lookup"><span data-stu-id="987b9-111">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="987b9-112">Как и цикл **do-while** , цикл **Do-Until** всегда запускается по крайней мере один раз перед вычислением условия.</span><span class="sxs-lookup"><span data-stu-id="987b9-112">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="987b9-113">Однако блок скрипта выполняется только тогда, когда условие имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="987b9-113">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="987b9-114">Ключевые слова *Continue* и *break* управления потоком можно использовать в цикле **do-while** или в цикле **Do-Until** .</span><span class="sxs-lookup"><span data-stu-id="987b9-114">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="987b9-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="987b9-115">Syntax</span></span>

<span data-ttu-id="987b9-116">Ниже приведен синтаксис инструкции **do-while** :</span><span class="sxs-lookup"><span data-stu-id="987b9-116">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="987b9-117">Ниже приведен синтаксис инструкции **Do-Until** :</span><span class="sxs-lookup"><span data-stu-id="987b9-117">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="987b9-118">Список инструкций содержит одну или несколько инструкций, выполняемых при каждом входе или повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="987b9-118">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="987b9-119">Часть условия инструкции разрешается в true или false.</span><span class="sxs-lookup"><span data-stu-id="987b9-119">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="987b9-120">Пример</span><span class="sxs-lookup"><span data-stu-id="987b9-120">Example</span></span>

<span data-ttu-id="987b9-121">Следующий пример инструкции Do подсчитывает количество элементов в массиве до тех пор, пока не достигнет элемента со значением 0.</span><span class="sxs-lookup"><span data-stu-id="987b9-121">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="987b9-122">В следующем примере используется ключевое слово Until.</span><span class="sxs-lookup"><span data-stu-id="987b9-122">The following example uses the Until keyword.</span></span> <span data-ttu-id="987b9-123">Обратите внимание, что оператор «не равно» ( `-ne` ) заменяется оператором «равно» ( `-eq` ).</span><span class="sxs-lookup"><span data-stu-id="987b9-123">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="987b9-124">В следующем примере записываются все значения массива, пропуская все значения меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="987b9-124">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="987b9-125">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="987b9-125">SEE ALSO</span></span>

[<span data-ttu-id="987b9-126">about_While</span><span class="sxs-lookup"><span data-stu-id="987b9-126">about_While</span></span>](about_While.md)

[<span data-ttu-id="987b9-127">about_Operators</span><span class="sxs-lookup"><span data-stu-id="987b9-127">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="987b9-128">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="987b9-128">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="987b9-129">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="987b9-129">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="987b9-130">about_Break</span><span class="sxs-lookup"><span data-stu-id="987b9-130">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="987b9-131">about_Continue</span><span class="sxs-lookup"><span data-stu-id="987b9-131">about_Continue</span></span>](about_Continue.md)


---
description: Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231513"
---
# <a name="about-do"></a><span data-ttu-id="cfd9f-104">О Do</span><span class="sxs-lookup"><span data-stu-id="cfd9f-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="cfd9f-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cfd9f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="cfd9f-106">Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="cfd9f-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cfd9f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="cfd9f-108">Ключевое слово do работает с ключевым словом While или ключевым словом Until для выполнения инструкций в блоке скрипта в соответствии с условием.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="cfd9f-109">В отличие от связанного цикла while, блок сценария в цикле Do всегда выполняется по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="cfd9f-110">Цикл **do-while** — это множество циклов while.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="cfd9f-111">В цикле **do-while** условие вычисляется после выполнения блока script.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="cfd9f-112">Как и в цикле while, блок скрипта повторяется, пока условие принимает значение true.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="cfd9f-113">Как и цикл **do-while** , цикл **Do-Until** всегда запускается по крайней мере один раз перед вычислением условия.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="cfd9f-114">Однако блок скрипта выполняется только тогда, когда условие имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="cfd9f-115">Ключевые слова *Continue* и *break* управления потоком можно использовать в цикле **do-while** или в цикле **Do-Until** .</span><span class="sxs-lookup"><span data-stu-id="cfd9f-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="cfd9f-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfd9f-116">Syntax</span></span>

<span data-ttu-id="cfd9f-117">Ниже приведен синтаксис инструкции **do-while** :</span><span class="sxs-lookup"><span data-stu-id="cfd9f-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="cfd9f-118">Ниже приведен синтаксис инструкции **Do-Until** :</span><span class="sxs-lookup"><span data-stu-id="cfd9f-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="cfd9f-119">Список инструкций содержит одну или несколько инструкций, выполняемых при каждом входе или повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="cfd9f-120">Часть условия инструкции разрешается в true или false.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="cfd9f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="cfd9f-121">Example</span></span>

<span data-ttu-id="cfd9f-122">Следующий пример инструкции Do подсчитывает количество элементов в массиве до тех пор, пока не достигнет элемента со значением 0.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="cfd9f-123">В следующем примере используется ключевое слово Until.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="cfd9f-124">Обратите внимание, что оператор «не равно» ( `-ne` ) заменяется оператором «равно» ( `-eq` ).</span><span class="sxs-lookup"><span data-stu-id="cfd9f-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="cfd9f-125">В следующем примере записываются все значения массива, пропуская все значения меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="cfd9f-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="cfd9f-126">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="cfd9f-126">SEE ALSO</span></span>

[<span data-ttu-id="cfd9f-127">about_While</span><span class="sxs-lookup"><span data-stu-id="cfd9f-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="cfd9f-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="cfd9f-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="cfd9f-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="cfd9f-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="cfd9f-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="cfd9f-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="cfd9f-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="cfd9f-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="cfd9f-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="cfd9f-132">about_Continue</span></span>](about_Continue.md)

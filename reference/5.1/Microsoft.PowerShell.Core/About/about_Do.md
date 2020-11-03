---
description: Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: 9c5a7c561fde4d96401771870cf4e85d78591593
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232430"
---
# <a name="about-do"></a><span data-ttu-id="b7572-104">О Do</span><span class="sxs-lookup"><span data-stu-id="b7572-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="b7572-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b7572-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b7572-106">Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.</span><span class="sxs-lookup"><span data-stu-id="b7572-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="b7572-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b7572-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b7572-108">Ключевое слово do работает с ключевым словом While или ключевым словом Until для выполнения инструкций в блоке скрипта в соответствии с условием.</span><span class="sxs-lookup"><span data-stu-id="b7572-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="b7572-109">В отличие от связанного цикла while, блок сценария в цикле Do всегда выполняется по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="b7572-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="b7572-110">Цикл **do-while** — это множество циклов while.</span><span class="sxs-lookup"><span data-stu-id="b7572-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="b7572-111">В цикле **do-while** условие вычисляется после выполнения блока script.</span><span class="sxs-lookup"><span data-stu-id="b7572-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="b7572-112">Как и в цикле while, блок скрипта повторяется, пока условие принимает значение true.</span><span class="sxs-lookup"><span data-stu-id="b7572-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="b7572-113">Как и цикл **do-while** , цикл **Do-Until** всегда запускается по крайней мере один раз перед вычислением условия.</span><span class="sxs-lookup"><span data-stu-id="b7572-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="b7572-114">Однако блок скрипта выполняется только тогда, когда условие имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="b7572-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="b7572-115">Ключевые слова *Continue* и *break* управления потоком можно использовать в цикле **do-while** или в цикле **Do-Until** .</span><span class="sxs-lookup"><span data-stu-id="b7572-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="b7572-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7572-116">Syntax</span></span>

<span data-ttu-id="b7572-117">Ниже приведен синтаксис инструкции **do-while** :</span><span class="sxs-lookup"><span data-stu-id="b7572-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="b7572-118">Ниже приведен синтаксис инструкции **Do-Until** :</span><span class="sxs-lookup"><span data-stu-id="b7572-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="b7572-119">Список инструкций содержит одну или несколько инструкций, выполняемых при каждом входе или повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="b7572-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="b7572-120">Часть условия инструкции разрешается в true или false.</span><span class="sxs-lookup"><span data-stu-id="b7572-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="b7572-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b7572-121">Example</span></span>

<span data-ttu-id="b7572-122">Следующий пример инструкции Do подсчитывает количество элементов в массиве до тех пор, пока не достигнет элемента со значением 0.</span><span class="sxs-lookup"><span data-stu-id="b7572-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="b7572-123">В следующем примере используется ключевое слово Until.</span><span class="sxs-lookup"><span data-stu-id="b7572-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="b7572-124">Обратите внимание, что оператор «не равно» ( `-ne` ) заменяется оператором «равно» ( `-eq` ).</span><span class="sxs-lookup"><span data-stu-id="b7572-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="b7572-125">В следующем примере записываются все значения массива, пропуская все значения меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="b7572-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="b7572-126">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="b7572-126">SEE ALSO</span></span>

[<span data-ttu-id="b7572-127">about_While</span><span class="sxs-lookup"><span data-stu-id="b7572-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="b7572-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="b7572-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="b7572-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="b7572-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="b7572-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="b7572-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="b7572-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="b7572-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="b7572-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="b7572-132">about_Continue</span></span>](about_Continue.md)

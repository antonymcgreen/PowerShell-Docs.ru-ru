---
description: Описывает языковую инструкцию, которую можно использовать для выполнения блока команд на основе результатов условного теста.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 37c277a5919ba5fc39f953e05edaf58d159f3e7c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604578"
---
# <a name="about-while"></a><span data-ttu-id="43ab8-103">О программе while</span><span class="sxs-lookup"><span data-stu-id="43ab8-103">About While</span></span>

## <a name="short-description"></a><span data-ttu-id="43ab8-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="43ab8-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="43ab8-105">Описывает языковую инструкцию, которую можно использовать для выполнения блока команд на основе результатов условного теста.</span><span class="sxs-lookup"><span data-stu-id="43ab8-105">Describes a language statement that you can use to run a command block based on the results of a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="43ab8-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="43ab8-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="43ab8-107">Оператор while (также называемый циклом while) — это языковая конструкция для создания цикла, запускающего команды в блоке команд, если условный тест имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="43ab8-107">The While statement (also known as a While loop) is a language construct for creating a loop that runs commands in a command block as long as a conditional test evaluates to true.</span></span> <span data-ttu-id="43ab8-108">Оператор while проще создавать, чем оператор for, поскольку его синтаксис менее сложен.</span><span class="sxs-lookup"><span data-stu-id="43ab8-108">The While statement is easier to construct than a For statement because its syntax is less complicated.</span></span> <span data-ttu-id="43ab8-109">Кроме того, он является более гибким, чем оператор foreach, так как в инструкции While указывается условный тест, определяющий, сколько раз выполняется цикл.</span><span class="sxs-lookup"><span data-stu-id="43ab8-109">In addition, it is more flexible than the Foreach statement because you specify a conditional test in the While statement to control how many times the loop runs.</span></span>

<span data-ttu-id="43ab8-110">Ниже показан синтаксис инструкции While:</span><span class="sxs-lookup"><span data-stu-id="43ab8-110">The following shows the While statement syntax:</span></span>

```powershell
while (<condition>){<statement list>}
```

<span data-ttu-id="43ab8-111">При выполнении инструкции While PowerShell вычисляет `<condition>` раздел инструкции перед входом в `<statement list>` раздел.</span><span class="sxs-lookup"><span data-stu-id="43ab8-111">When you run a While statement, PowerShell evaluates the `<condition>` section of the statement before entering the `<statement list>` section.</span></span> <span data-ttu-id="43ab8-112">Часть условия инструкции разрешается как true или false.</span><span class="sxs-lookup"><span data-stu-id="43ab8-112">The condition portion of the statement resolves to either true or false.</span></span> <span data-ttu-id="43ab8-113">Пока условие остается истинным, PowerShell повторно выполнят этот `<statement list>` раздел.</span><span class="sxs-lookup"><span data-stu-id="43ab8-113">As long as the condition remains true, PowerShell reruns the `<statement list>` section.</span></span>

<span data-ttu-id="43ab8-114">`<statement list>`Раздел инструкции содержит одну или несколько команд, которые выполняются каждый раз при входе или повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="43ab8-114">The `<statement list>` section of the statement contains one or more commands that are run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="43ab8-115">Например, следующая инструкция while отображает числа от 1 до 3, если переменная $val не была создана или если $val переменная была создана и инициализирована значением 0.</span><span class="sxs-lookup"><span data-stu-id="43ab8-115">For example, the following While statement displays the numbers 1 through 3 if the $val variable has not been created or if the $val variable has been created and initialized to 0.</span></span>

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

<span data-ttu-id="43ab8-116">В этом примере условие ($val не равно 3) имеет значение true, когда $val \= 0, 1, 2.</span><span class="sxs-lookup"><span data-stu-id="43ab8-116">In this example, the condition ($val is not equal to 3) is true while $val \= 0, 1, 2.</span></span> <span data-ttu-id="43ab8-117">Каждый раз с помощью цикла $val увеличивается на 1 с помощью \+ \+ оператора унарного инкремента ($Val \+ \+ ).</span><span class="sxs-lookup"><span data-stu-id="43ab8-117">Each time through the loop, $val is incremented by 1 using the \+\+ unary increment operator ($val\+\+).</span></span> <span data-ttu-id="43ab8-118">Последний раз в цикле, $val \= 3.</span><span class="sxs-lookup"><span data-stu-id="43ab8-118">The last time through the loop, $val \= 3.</span></span> <span data-ttu-id="43ab8-119">Если $val равно 3, то оператор Condition принимает значение false, а цикл завершается.</span><span class="sxs-lookup"><span data-stu-id="43ab8-119">When $val equals 3, the condition statement evaluates to false, and the loop exits.</span></span>

<span data-ttu-id="43ab8-120">Чтобы удобно написать эту команду в командной строке PowerShell, введите ее следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43ab8-120">To conveniently write this command at the PowerShell command prompt, you can enter it in the following way:</span></span>

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

<span data-ttu-id="43ab8-121">Обратите внимание, что точка с запятой отделяет первую команду, которая добавляет 1 к $val из второй команды, которая записывает значение $val в консоль.</span><span class="sxs-lookup"><span data-stu-id="43ab8-121">Notice that the semicolon separates the first command that adds 1 to $val from the second command that writes the value of $val to the console.</span></span>

## <a name="see-also"></a><span data-ttu-id="43ab8-122">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="43ab8-122">SEE ALSO</span></span>

[<span data-ttu-id="43ab8-123">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="43ab8-123">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="43ab8-124">about_Do</span><span class="sxs-lookup"><span data-stu-id="43ab8-124">about_Do</span></span>](about_Do.md)

[<span data-ttu-id="43ab8-125">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="43ab8-125">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="43ab8-126">about_For</span><span class="sxs-lookup"><span data-stu-id="43ab8-126">about_For</span></span>](about_For.md)

[<span data-ttu-id="43ab8-127">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="43ab8-127">about_Language_Keywords</span></span>](about_Language_Keywords.md)


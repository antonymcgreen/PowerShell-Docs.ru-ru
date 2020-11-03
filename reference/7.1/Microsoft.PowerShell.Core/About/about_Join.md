---
description: Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: 578d12461a1e915e699970ca17c6f8220eb7fef1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232473"
---
# <a name="about-join"></a><span data-ttu-id="6a935-104">О соединении</span><span class="sxs-lookup"><span data-stu-id="6a935-104">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="6a935-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6a935-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6a935-106">Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="6a935-106">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="6a935-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6a935-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6a935-108">Оператор Join объединяет набор строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="6a935-108">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="6a935-109">Строки добавляются к результирующей строке в том порядке, в котором они отображаются в команде.</span><span class="sxs-lookup"><span data-stu-id="6a935-109">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="6a935-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a935-110">Syntax</span></span>

<span data-ttu-id="6a935-111">На следующей схеме показан синтаксис оператора Join.</span><span class="sxs-lookup"><span data-stu-id="6a935-111">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="6a935-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a935-112">Parameters</span></span>

<span data-ttu-id="6a935-113">String [] — указывает одну или несколько строк для объединения.</span><span class="sxs-lookup"><span data-stu-id="6a935-113">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="6a935-114">Разделитель — указывает один или несколько символов между объединенными строками.</span><span class="sxs-lookup"><span data-stu-id="6a935-114">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="6a935-115">Значение по умолчанию — без разделителя ("").</span><span class="sxs-lookup"><span data-stu-id="6a935-115">The default is no delimiter ("").</span></span>

<span data-ttu-id="6a935-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a935-116">Remarks</span></span>

<span data-ttu-id="6a935-117">Оператор унарного объединения (-Join <строка [] >) имеет более высокий приоритет, чем запятая.</span><span class="sxs-lookup"><span data-stu-id="6a935-117">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="6a935-118">В результате при отправке разделенного запятыми списка строк в оператор унарного объединения в оператор Join передается только первая строка (перед первой запятой).</span><span class="sxs-lookup"><span data-stu-id="6a935-118">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="6a935-119">Чтобы использовать оператор унарного объединения, заключите строки в круглые скобки или сохраните строки в переменной, а затем отправьте переменную в соединение.</span><span class="sxs-lookup"><span data-stu-id="6a935-119">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="6a935-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="6a935-120">For example:</span></span>

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a><span data-ttu-id="6a935-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="6a935-121">Examples</span></span>

<span data-ttu-id="6a935-122">Следующая инструкция соединяет три строки:</span><span class="sxs-lookup"><span data-stu-id="6a935-122">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="6a935-123">Следующая инструкция соединяет три строки, разделенные пробелом:</span><span class="sxs-lookup"><span data-stu-id="6a935-123">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="6a935-124">Следующие инструкции используют разделитель из нескольких символов для объединения трех строк:</span><span class="sxs-lookup"><span data-stu-id="6a935-124">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="6a935-125">Следующая инструкция соединяет строки в строке ниже в одной строке.</span><span class="sxs-lookup"><span data-stu-id="6a935-125">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="6a935-126">Так как строка Here является одной строкой, строки в этой строке должны быть разделены, прежде чем их можно будет соединить.</span><span class="sxs-lookup"><span data-stu-id="6a935-126">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="6a935-127">Этот метод можно использовать для повторного объединения строк в XML-файл, сохраненный в строке ниже:</span><span class="sxs-lookup"><span data-stu-id="6a935-127">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="6a935-128">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="6a935-128">SEE ALSO</span></span>

[<span data-ttu-id="6a935-129">about_Operators</span><span class="sxs-lookup"><span data-stu-id="6a935-129">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="6a935-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="6a935-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="6a935-131">about_Split</span><span class="sxs-lookup"><span data-stu-id="6a935-131">about_Split</span></span>](about_Split.md)


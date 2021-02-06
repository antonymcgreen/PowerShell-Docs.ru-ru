---
description: Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d76e95aaeca1b5b94bb1a2216576a985ffb209c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600169"
---
# <a name="about-join"></a><span data-ttu-id="7d5dd-103">О соединении</span><span class="sxs-lookup"><span data-stu-id="7d5dd-103">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="7d5dd-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="7d5dd-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="7d5dd-105">Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-105">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="7d5dd-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="7d5dd-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="7d5dd-107">Оператор Join объединяет набор строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-107">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="7d5dd-108">Строки добавляются к результирующей строке в том порядке, в котором они отображаются в команде.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-108">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="7d5dd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d5dd-109">Syntax</span></span>

<span data-ttu-id="7d5dd-110">На следующей схеме показан синтаксис оператора Join.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-110">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="7d5dd-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d5dd-111">Parameters</span></span>

<span data-ttu-id="7d5dd-112">String [] — указывает одну или несколько строк для объединения.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-112">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="7d5dd-113">Разделитель — указывает один или несколько символов между объединенными строками.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-113">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="7d5dd-114">Значение по умолчанию — без разделителя ("").</span><span class="sxs-lookup"><span data-stu-id="7d5dd-114">The default is no delimiter ("").</span></span>

<span data-ttu-id="7d5dd-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d5dd-115">Remarks</span></span>

<span data-ttu-id="7d5dd-116">Оператор унарного объединения (-Join <строка [] >) имеет более высокий приоритет, чем запятая.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-116">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="7d5dd-117">В результате при отправке разделенного запятыми списка строк в оператор унарного объединения в оператор Join передается только первая строка (перед первой запятой).</span><span class="sxs-lookup"><span data-stu-id="7d5dd-117">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="7d5dd-118">Чтобы использовать оператор унарного объединения, заключите строки в круглые скобки или сохраните строки в переменной, а затем отправьте переменную в соединение.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-118">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="7d5dd-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="7d5dd-119">For example:</span></span>

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

### <a name="examples"></a><span data-ttu-id="7d5dd-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="7d5dd-120">Examples</span></span>

<span data-ttu-id="7d5dd-121">Следующая инструкция соединяет три строки:</span><span class="sxs-lookup"><span data-stu-id="7d5dd-121">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="7d5dd-122">Следующая инструкция соединяет три строки, разделенные пробелом:</span><span class="sxs-lookup"><span data-stu-id="7d5dd-122">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="7d5dd-123">Следующие инструкции используют разделитель из нескольких символов для объединения трех строк:</span><span class="sxs-lookup"><span data-stu-id="7d5dd-123">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="7d5dd-124">Следующая инструкция соединяет строки в строке ниже в одной строке.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-124">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="7d5dd-125">Так как строка Here является одной строкой, строки в этой строке должны быть разделены, прежде чем их можно будет соединить.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-125">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="7d5dd-126">Этот метод можно использовать для повторного объединения строк в XML-файл, сохраненный в строке ниже:</span><span class="sxs-lookup"><span data-stu-id="7d5dd-126">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="7d5dd-127">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="7d5dd-127">SEE ALSO</span></span>

[<span data-ttu-id="7d5dd-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="7d5dd-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="7d5dd-129">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="7d5dd-129">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="7d5dd-130">about_Split</span><span class="sxs-lookup"><span data-stu-id="7d5dd-130">about_Split</span></span>](about_Split.md)


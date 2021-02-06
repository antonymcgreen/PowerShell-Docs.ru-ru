---
description: Описывает использование подстановочных знаков в PowerShell.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: b5f13fdbfbc24e19e5ad0b1cd6ecc1b99f68914f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600893"
---
# <a name="about-wildcards"></a><span data-ttu-id="305b1-103">О подстановочных знаках</span><span class="sxs-lookup"><span data-stu-id="305b1-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="305b1-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="305b1-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="305b1-105">Описывает использование подстановочных знаков в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="305b1-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="305b1-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="305b1-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="305b1-107">Символы-шаблоны представляют один или несколько символов.</span><span class="sxs-lookup"><span data-stu-id="305b1-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="305b1-108">Их можно использовать для создания шаблонов Word в командах.</span><span class="sxs-lookup"><span data-stu-id="305b1-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="305b1-109">Например, чтобы получить все файлы в `C:\Techdocs` каталоге с `.ppt` расширением имени файла, введите:</span><span class="sxs-lookup"><span data-stu-id="305b1-109">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="305b1-110">В этом случае `*` подстановочный знак звездочки () представляет все символы, которые отображаются перед `.ppt` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="305b1-110">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="305b1-111">PowerShell поддерживает следующие подстановочные знаки:</span><span class="sxs-lookup"><span data-stu-id="305b1-111">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="305b1-112">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="305b1-112">Wildcard</span></span>|<span data-ttu-id="305b1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="305b1-113">Description</span></span>               |<span data-ttu-id="305b1-114">Пример</span><span class="sxs-lookup"><span data-stu-id="305b1-114">Example</span></span> |<span data-ttu-id="305b1-115">Соответствие</span><span class="sxs-lookup"><span data-stu-id="305b1-115">Match</span></span>        |<span data-ttu-id="305b1-116">Нет совпадений</span><span class="sxs-lookup"><span data-stu-id="305b1-116">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="305b1-117">Совпадение с нулем или несколькими символами</span><span class="sxs-lookup"><span data-stu-id="305b1-117">Match zero or more characters</span></span> | <span data-ttu-id="305b1-118">конкретного\*</span><span class="sxs-lookup"><span data-stu-id="305b1-118">a\*</span></span>  | <span data-ttu-id="305b1-119">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="305b1-119">aA, ag, Apple</span></span> | <span data-ttu-id="305b1-120">банан</span><span class="sxs-lookup"><span data-stu-id="305b1-120">banana</span></span> |
|<span data-ttu-id="305b1-121">?</span><span class="sxs-lookup"><span data-stu-id="305b1-121">?</span></span>       |<span data-ttu-id="305b1-122">Совпадение с одним символом в этой позиции</span><span class="sxs-lookup"><span data-stu-id="305b1-122">Match one character in that position</span></span> | <span data-ttu-id="305b1-123">? n</span><span class="sxs-lookup"><span data-stu-id="305b1-123">?n</span></span> | <span data-ttu-id="305b1-124">Объект, в, на</span><span class="sxs-lookup"><span data-stu-id="305b1-124">an, in, on</span></span> | <span data-ttu-id="305b1-125">обнаружил</span><span class="sxs-lookup"><span data-stu-id="305b1-125">ran</span></span> |
|<span data-ttu-id="305b1-126">\[ \]</span><span class="sxs-lookup"><span data-stu-id="305b1-126">\[ \]</span></span>   |<span data-ttu-id="305b1-127">Совпадение с диапазоном символов</span><span class="sxs-lookup"><span data-stu-id="305b1-127">Match a range of characters</span></span> | <span data-ttu-id="305b1-128">\[a-l \] УК</span><span class="sxs-lookup"><span data-stu-id="305b1-128">\[a-l\]ook</span></span> | <span data-ttu-id="305b1-129">книга, Кука, взгляд</span><span class="sxs-lookup"><span data-stu-id="305b1-129">book, cook, look</span></span> | <span data-ttu-id="305b1-130">была</span><span class="sxs-lookup"><span data-stu-id="305b1-130">took</span></span> |
|<span data-ttu-id="305b1-131">\[ \]</span><span class="sxs-lookup"><span data-stu-id="305b1-131">\[ \]</span></span>   |<span data-ttu-id="305b1-132">Совпадение с конкретными символами</span><span class="sxs-lookup"><span data-stu-id="305b1-132">Match specific characters</span></span> | <span data-ttu-id="305b1-133">\[BC \] УК</span><span class="sxs-lookup"><span data-stu-id="305b1-133">\[bc\]ook</span></span> | <span data-ttu-id="305b1-134">книга, Кука</span><span class="sxs-lookup"><span data-stu-id="305b1-134">book, cook</span></span> | <span data-ttu-id="305b1-135">ключ</span><span class="sxs-lookup"><span data-stu-id="305b1-135">hook</span></span> |

<span data-ttu-id="305b1-136">В один шаблон Word можно включить несколько подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="305b1-136">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="305b1-137">Например, чтобы найти текстовые файлы с именами, начинающимися с букв **a** до **l**, введите:</span><span class="sxs-lookup"><span data-stu-id="305b1-137">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="305b1-138">Многие командлеты принимают подстановочные знаки в значениях параметров.</span><span class="sxs-lookup"><span data-stu-id="305b1-138">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="305b1-139">Раздел справки для каждого командлета описывает, какие параметры принимают подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="305b1-139">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="305b1-140">Для параметров, которые принимают подстановочные знаки, их использование не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="305b1-140">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="305b1-141">Подстановочные знаки можно использовать в командах и блоках скриптов, например для создания шаблона Word, представляющего значения свойств.</span><span class="sxs-lookup"><span data-stu-id="305b1-141">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="305b1-142">Например, следующая команда получает службы, в которых значение свойства **serviceType** включает **Interactive**.</span><span class="sxs-lookup"><span data-stu-id="305b1-142">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="305b1-143">В следующем примере `If` инструкция включает условие, которое использует подстановочные знаки для поиска значений свойств.</span><span class="sxs-lookup"><span data-stu-id="305b1-143">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="305b1-144">Если **Описание** точки восстановления включает **PowerShell**, команда добавляет значение свойства **CreationTime** для точки восстановления в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="305b1-144">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="305b1-145">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="305b1-145">SEE ALSO</span></span>

[<span data-ttu-id="305b1-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="305b1-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="305b1-147">about_If</span><span class="sxs-lookup"><span data-stu-id="305b1-147">about_If</span></span>](about_If.md)

[<span data-ttu-id="305b1-148">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="305b1-148">about_Script_Blocks</span></span>](about_Script_Blocks.md)


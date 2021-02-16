---
description: Описывает использование подстановочных знаков в PowerShell.
Locale: en-US
ms.date: 02/13/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 54108eaafa645452f58b1962c3f103bcdd5c9e4a
ms.sourcegitcommit: 9777152e026c47ba8d319593051416054cb62246
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "100529997"
---
# <a name="about-wildcards"></a><span data-ttu-id="37c4f-103">О подстановочных знаках</span><span class="sxs-lookup"><span data-stu-id="37c4f-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="37c4f-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="37c4f-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="37c4f-105">Описывает использование подстановочных знаков в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37c4f-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="37c4f-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="37c4f-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="37c4f-107">Символы-шаблоны представляют один или несколько символов.</span><span class="sxs-lookup"><span data-stu-id="37c4f-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="37c4f-108">Их можно использовать для создания шаблонов Word в командах.</span><span class="sxs-lookup"><span data-stu-id="37c4f-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="37c4f-109">Выражения с подстановочными знаками используются с `-like` оператором или с любым параметром, который принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="37c4f-109">Wildcard expressions are used with the `-like` operator or with any parameter that accepts wildcards.</span></span>

<span data-ttu-id="37c4f-110">Например, чтобы сопоставить все файлы в `C:\Techdocs` каталоге с `.ppt` расширением имени файла, введите:</span><span class="sxs-lookup"><span data-stu-id="37c4f-110">For example, to match all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="37c4f-111">В этом случае `*` подстановочный знак звездочки () представляет все символы, которые отображаются перед `.ppt` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="37c4f-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="37c4f-112">Выражения с подстановочными знаками проще регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="37c4f-112">Wildcard expressions are simpler than regular expressions.</span></span> <span data-ttu-id="37c4f-113">Дополнительные сведения см. в разделе [about_Regular_Expressions](./about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="37c4f-113">For more information, see [about_Regular_Expressions](./about_Regular_Expressions.md).</span></span>

<span data-ttu-id="37c4f-114">PowerShell поддерживает следующие подстановочные знаки:</span><span class="sxs-lookup"><span data-stu-id="37c4f-114">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="37c4f-115">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="37c4f-115">Wildcard</span></span>|<span data-ttu-id="37c4f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="37c4f-116">Description</span></span>               |<span data-ttu-id="37c4f-117">Пример</span><span class="sxs-lookup"><span data-stu-id="37c4f-117">Example</span></span> |<span data-ttu-id="37c4f-118">Соответствие</span><span class="sxs-lookup"><span data-stu-id="37c4f-118">Match</span></span>        |<span data-ttu-id="37c4f-119">Нет совпадений</span><span class="sxs-lookup"><span data-stu-id="37c4f-119">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="37c4f-120">Совпадение с нулем или несколькими символами</span><span class="sxs-lookup"><span data-stu-id="37c4f-120">Match zero or more characters</span></span> | <span data-ttu-id="37c4f-121">конкретного\*</span><span class="sxs-lookup"><span data-stu-id="37c4f-121">a\*</span></span>  | <span data-ttu-id="37c4f-122">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="37c4f-122">aA, ag, Apple</span></span> | <span data-ttu-id="37c4f-123">банан</span><span class="sxs-lookup"><span data-stu-id="37c4f-123">banana</span></span> |
|<span data-ttu-id="37c4f-124">?</span><span class="sxs-lookup"><span data-stu-id="37c4f-124">?</span></span>       |<span data-ttu-id="37c4f-125">Совпадение с одним символом в этой позиции</span><span class="sxs-lookup"><span data-stu-id="37c4f-125">Match one character in that position</span></span> | <span data-ttu-id="37c4f-126">? n</span><span class="sxs-lookup"><span data-stu-id="37c4f-126">?n</span></span> | <span data-ttu-id="37c4f-127">Объект, в, на</span><span class="sxs-lookup"><span data-stu-id="37c4f-127">an, in, on</span></span> | <span data-ttu-id="37c4f-128">обнаружил</span><span class="sxs-lookup"><span data-stu-id="37c4f-128">ran</span></span> |
|<span data-ttu-id="37c4f-129">\[ \]</span><span class="sxs-lookup"><span data-stu-id="37c4f-129">\[ \]</span></span>   |<span data-ttu-id="37c4f-130">Совпадение с диапазоном символов</span><span class="sxs-lookup"><span data-stu-id="37c4f-130">Match a range of characters</span></span> | <span data-ttu-id="37c4f-131">\[a-l \] УК</span><span class="sxs-lookup"><span data-stu-id="37c4f-131">\[a-l\]ook</span></span> | <span data-ttu-id="37c4f-132">книга, Кука, взгляд</span><span class="sxs-lookup"><span data-stu-id="37c4f-132">book, cook, look</span></span> | <span data-ttu-id="37c4f-133">была</span><span class="sxs-lookup"><span data-stu-id="37c4f-133">took</span></span> |
|<span data-ttu-id="37c4f-134">\[ \]</span><span class="sxs-lookup"><span data-stu-id="37c4f-134">\[ \]</span></span>   |<span data-ttu-id="37c4f-135">Совпадение с конкретными символами</span><span class="sxs-lookup"><span data-stu-id="37c4f-135">Match specific characters</span></span> | <span data-ttu-id="37c4f-136">\[BC \] УК</span><span class="sxs-lookup"><span data-stu-id="37c4f-136">\[bc\]ook</span></span> | <span data-ttu-id="37c4f-137">книга, Кука</span><span class="sxs-lookup"><span data-stu-id="37c4f-137">book, cook</span></span> | <span data-ttu-id="37c4f-138">ключ</span><span class="sxs-lookup"><span data-stu-id="37c4f-138">hook</span></span> |

<span data-ttu-id="37c4f-139">В один шаблон Word можно включить несколько подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="37c4f-139">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="37c4f-140">Например, чтобы найти текстовые файлы с именами, начинающимися с букв **a** до **l**, введите:</span><span class="sxs-lookup"><span data-stu-id="37c4f-140">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="37c4f-141">Многие командлеты принимают подстановочные знаки в значениях параметров.</span><span class="sxs-lookup"><span data-stu-id="37c4f-141">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="37c4f-142">Раздел справки для каждого командлета описывает, какие параметры принимают подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="37c4f-142">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="37c4f-143">Для параметров, которые принимают подстановочные знаки, их использование не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="37c4f-143">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="37c4f-144">Подстановочные знаки можно использовать в командах и блоках скриптов, например для создания шаблона Word, представляющего значения свойств.</span><span class="sxs-lookup"><span data-stu-id="37c4f-144">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="37c4f-145">Например, следующая команда получает службы, в которых значение свойства **serviceType** включает **Interactive**.</span><span class="sxs-lookup"><span data-stu-id="37c4f-145">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="37c4f-146">В следующем примере `If` инструкция включает условие, которое использует подстановочные знаки для поиска значений свойств.</span><span class="sxs-lookup"><span data-stu-id="37c4f-146">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="37c4f-147">Если **Описание** точки восстановления включает **PowerShell**, команда добавляет значение свойства **CreationTime** для точки восстановления в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="37c4f-147">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="37c4f-148">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="37c4f-148">SEE ALSO</span></span>

[<span data-ttu-id="37c4f-149">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="37c4f-149">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="37c4f-150">about_If</span><span class="sxs-lookup"><span data-stu-id="37c4f-150">about_If</span></span>](about_If.md)

[<span data-ttu-id="37c4f-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="37c4f-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)

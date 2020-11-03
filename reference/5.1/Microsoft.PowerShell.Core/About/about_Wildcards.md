---
description: Описывает использование подстановочных знаков в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 4656266107a29e4f57c5e273788d382a477a2428
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232253"
---
# <a name="about-wildcards"></a><span data-ttu-id="43697-104">О подстановочных знаках</span><span class="sxs-lookup"><span data-stu-id="43697-104">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="43697-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="43697-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="43697-106">Описывает использование подстановочных знаков в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43697-106">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="43697-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="43697-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="43697-108">Символы-шаблоны представляют один или несколько символов.</span><span class="sxs-lookup"><span data-stu-id="43697-108">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="43697-109">Их можно использовать для создания шаблонов Word в командах.</span><span class="sxs-lookup"><span data-stu-id="43697-109">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="43697-110">Например, чтобы получить все файлы в `C:\Techdocs` каталоге с `.ppt` расширением имени файла, введите:</span><span class="sxs-lookup"><span data-stu-id="43697-110">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="43697-111">В этом случае `*` подстановочный знак звездочки () представляет все символы, которые отображаются перед `.ppt` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="43697-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="43697-112">PowerShell поддерживает следующие подстановочные знаки:</span><span class="sxs-lookup"><span data-stu-id="43697-112">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="43697-113">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="43697-113">Wildcard</span></span>|<span data-ttu-id="43697-114">Описание</span><span class="sxs-lookup"><span data-stu-id="43697-114">Description</span></span>               |<span data-ttu-id="43697-115">Пример</span><span class="sxs-lookup"><span data-stu-id="43697-115">Example</span></span> |<span data-ttu-id="43697-116">Соответствует</span><span class="sxs-lookup"><span data-stu-id="43697-116">Match</span></span>        |<span data-ttu-id="43697-117">Нет совпадений</span><span class="sxs-lookup"><span data-stu-id="43697-117">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="43697-118">Совпадение с нулем или несколькими символами</span><span class="sxs-lookup"><span data-stu-id="43697-118">Match zero or more characters</span></span> | <span data-ttu-id="43697-119">конкретного\*</span><span class="sxs-lookup"><span data-stu-id="43697-119">a\*</span></span>  | <span data-ttu-id="43697-120">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="43697-120">aA, ag, Apple</span></span> | <span data-ttu-id="43697-121">банан</span><span class="sxs-lookup"><span data-stu-id="43697-121">banana</span></span> |
|<span data-ttu-id="43697-122">?</span><span class="sxs-lookup"><span data-stu-id="43697-122">?</span></span>       |<span data-ttu-id="43697-123">Совпадение с одним символом в этой позиции</span><span class="sxs-lookup"><span data-stu-id="43697-123">Match one character in that position</span></span> | <span data-ttu-id="43697-124">? n</span><span class="sxs-lookup"><span data-stu-id="43697-124">?n</span></span> | <span data-ttu-id="43697-125">Объект, в, на</span><span class="sxs-lookup"><span data-stu-id="43697-125">an, in, on</span></span> | <span data-ttu-id="43697-126">обнаружил</span><span class="sxs-lookup"><span data-stu-id="43697-126">ran</span></span> |
|<span data-ttu-id="43697-127">\[ \]</span><span class="sxs-lookup"><span data-stu-id="43697-127">\[ \]</span></span>   |<span data-ttu-id="43697-128">Совпадение с диапазоном символов</span><span class="sxs-lookup"><span data-stu-id="43697-128">Match a range of characters</span></span> | <span data-ttu-id="43697-129">\[a-l \] УК</span><span class="sxs-lookup"><span data-stu-id="43697-129">\[a-l\]ook</span></span> | <span data-ttu-id="43697-130">книга, Кука, взгляд</span><span class="sxs-lookup"><span data-stu-id="43697-130">book, cook, look</span></span> | <span data-ttu-id="43697-131">была</span><span class="sxs-lookup"><span data-stu-id="43697-131">took</span></span> |
|<span data-ttu-id="43697-132">\[ \]</span><span class="sxs-lookup"><span data-stu-id="43697-132">\[ \]</span></span>   |<span data-ttu-id="43697-133">Совпадение с конкретными символами</span><span class="sxs-lookup"><span data-stu-id="43697-133">Match specific characters</span></span> | <span data-ttu-id="43697-134">\[BC \] УК</span><span class="sxs-lookup"><span data-stu-id="43697-134">\[bc\]ook</span></span> | <span data-ttu-id="43697-135">книга, Кука</span><span class="sxs-lookup"><span data-stu-id="43697-135">book, cook</span></span> | <span data-ttu-id="43697-136">ключ</span><span class="sxs-lookup"><span data-stu-id="43697-136">hook</span></span> |

<span data-ttu-id="43697-137">В один шаблон Word можно включить несколько подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="43697-137">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="43697-138">Например, чтобы найти текстовые файлы с именами, начинающимися с букв **a** до **l** , введите:</span><span class="sxs-lookup"><span data-stu-id="43697-138">For example, to find text files with names that begin with the letters **a** through **l** , type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="43697-139">Многие командлеты принимают подстановочные знаки в значениях параметров.</span><span class="sxs-lookup"><span data-stu-id="43697-139">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="43697-140">Раздел справки для каждого командлета описывает, какие параметры принимают подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="43697-140">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="43697-141">Для параметров, которые принимают подстановочные знаки, их использование не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="43697-141">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="43697-142">Подстановочные знаки можно использовать в командах и блоках скриптов, например для создания шаблона Word, представляющего значения свойств.</span><span class="sxs-lookup"><span data-stu-id="43697-142">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="43697-143">Например, следующая команда получает службы, в которых значение свойства **serviceType** включает **Interactive**.</span><span class="sxs-lookup"><span data-stu-id="43697-143">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="43697-144">В следующем примере `If` инструкция включает условие, которое использует подстановочные знаки для поиска значений свойств.</span><span class="sxs-lookup"><span data-stu-id="43697-144">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="43697-145">Если **Описание** точки восстановления включает **PowerShell** , команда добавляет значение свойства **CreationTime** для точки восстановления в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="43697-145">If the restore point's **Description** includes **PowerShell** , the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="43697-146">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="43697-146">SEE ALSO</span></span>

[<span data-ttu-id="43697-147">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="43697-147">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="43697-148">about_If</span><span class="sxs-lookup"><span data-stu-id="43697-148">about_If</span></span>](about_If.md)

[<span data-ttu-id="43697-149">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="43697-149">about_Script_Blocks</span></span>](about_Script_Blocks.md)

---
title: Входные параметры фильтра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 553878c34e74129f9876cca25a5393cb0d53445a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067694"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="2bbb8-102">Параметры фильтра ввода</span><span class="sxs-lookup"><span data-stu-id="2bbb8-102">Input Filter Parameters</span></span>

<span data-ttu-id="2bbb8-103">Командлет можно определить `Filter`, `Include`, и `Exclude` параметры фильтрации набора входных значений объектов, на которые влияет на командлет.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-103">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="2bbb8-104">Как правило, определяется набор входных объектов `InputObject`, `Path`, или `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-104">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="2bbb8-105">Например, у командлета может быть `Path` параметр, который принимает несколько путей, используя символы-шаблоны и каждый путь Указывает входной объект.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-105">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="2bbb8-106">Используются вместе, `Filter`, `Include`, и `Exclude` параметры дальнейшего уточнения пути, командлет работает на каждый раз, он вызывается.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-106">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="2bbb8-107">Включать и исключать параметры</span><span class="sxs-lookup"><span data-stu-id="2bbb8-107">Include and Exclude Parameters</span></span>

<span data-ttu-id="2bbb8-108">`Include` И `Exclude` параметры определяют объекты, которые включаются или исключаются из набора входных объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-108">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="2bbb8-109">Используйте эти параметры, если фильтр можно выразить на языке стандартные подстановочные.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-109">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="2bbb8-110">(Дополнительные сведения о подстановочных знаках см. в разделе [Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).) `Include` Параметр включает все объекты, имена которых соответствуют заданному фильтру включения.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-110">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="2bbb8-111">`Exclude` Исключает все объекты, имена которых соответствуют заданному фильтру.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-111">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="2bbb8-112">Параметр фильтра</span><span class="sxs-lookup"><span data-stu-id="2bbb8-112">Filter Parameter</span></span>

<span data-ttu-id="2bbb8-113">`Filter` Параметр задает фильтр, не выражается на языке стандартные подстановочные.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-113">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="2bbb8-114">Например, фильтры интерфейсы служб Active Directory (ADSI) или SQL, можно передать в командлет по его `Filter` параметра.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-114">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="2bbb8-115">В командлетах Windows PowerShell, предоставляемые поставщиками Windows PowerShell, командлет, чтобы получить доступ к хранилищу данных указаны эти фильтры.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-115">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="2bbb8-116">Как правило, каждый поставщик определяет свой собственный фильтр.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-116">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="2bbb8-117">Если указан без набора объектов ввода</span><span class="sxs-lookup"><span data-stu-id="2bbb8-117">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="2bbb8-118">Если нет набор входных объектов, это обычно означает, для фильтрации для всех объектов.</span><span class="sxs-lookup"><span data-stu-id="2bbb8-118">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="2bbb8-119">Дополнительные сведения см. в разделе[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span><span class="sxs-lookup"><span data-stu-id="2bbb8-119">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="2bbb8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2bbb8-120">See Also</span></span>

[<span data-ttu-id="2bbb8-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bbb8-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
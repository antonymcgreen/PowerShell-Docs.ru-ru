---
title: Параметры входного фильтра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 553878c34e74129f9876cca25a5393cb0d53445a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364393"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="0f06e-102">Параметры фильтра ввода</span><span class="sxs-lookup"><span data-stu-id="0f06e-102">Input Filter Parameters</span></span>

<span data-ttu-id="0f06e-103">Командлет может определять параметры `Filter`, `Include`и `Exclude`, которые фильтруют набор входных объектов, на которые влияет командлет.</span><span class="sxs-lookup"><span data-stu-id="0f06e-103">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="0f06e-104">Как правило, набор входных объектов задается параметром `InputObject`, `Path`или `Name`.</span><span class="sxs-lookup"><span data-stu-id="0f06e-104">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="0f06e-105">Например, командлет может иметь параметр `Path`, который принимает несколько путей с помощью подстановочных знаков, и каждый путь указывает на входной объект.</span><span class="sxs-lookup"><span data-stu-id="0f06e-105">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="0f06e-106">Параметры `Filter`, `Include`и `Exclude` дополнительно указывают пути, выполняемые командлетом при каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="0f06e-106">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="0f06e-107">Параметры включения и исключения</span><span class="sxs-lookup"><span data-stu-id="0f06e-107">Include and Exclude Parameters</span></span>

<span data-ttu-id="0f06e-108">Параметры `Include` и `Exclude` определяют объекты, которые включаются или исключаются из набора входных объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="0f06e-108">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="0f06e-109">Используйте эти параметры, если фильтр можно выразить на стандартном языке с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="0f06e-109">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="0f06e-110">(Дополнительные сведения о символах-шаблонах см. [в разделе Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).) Параметр `Include` включает все объекты, имена которых соответствуют фильтру включения.</span><span class="sxs-lookup"><span data-stu-id="0f06e-110">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="0f06e-111">Параметр `Exclude` исключает все объекты, имена которых соответствуют фильтру.</span><span class="sxs-lookup"><span data-stu-id="0f06e-111">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="0f06e-112">Параметр фильтра</span><span class="sxs-lookup"><span data-stu-id="0f06e-112">Filter Parameter</span></span>

<span data-ttu-id="0f06e-113">Параметр `Filter` задает фильтр, который не выражается в стандартном языке с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="0f06e-113">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="0f06e-114">Например, Active Directory интерфейсы ADSI или фильтры SQL могут передаваться в командлет через его параметр `Filter`.</span><span class="sxs-lookup"><span data-stu-id="0f06e-114">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="0f06e-115">В командлетах, предоставляемых Windows PowerShell, эти фильтры указываются поставщиками Windows PowerShell, которые используют командлет для доступа к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="0f06e-115">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="0f06e-116">Каждый поставщик обычно определяет собственный фильтр.</span><span class="sxs-lookup"><span data-stu-id="0f06e-116">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="0f06e-117">Фильтрация, если не указано ни одного набора входных объектов</span><span class="sxs-lookup"><span data-stu-id="0f06e-117">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="0f06e-118">Если не указано ни одного набора входных объектов, обычно это означает фильтрацию по всем объектам.</span><span class="sxs-lookup"><span data-stu-id="0f06e-118">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="0f06e-119">Дополнительные сведения см. в разделе[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span><span class="sxs-lookup"><span data-stu-id="0f06e-119">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f06e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f06e-120">See Also</span></span>

[<span data-ttu-id="0f06e-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f06e-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
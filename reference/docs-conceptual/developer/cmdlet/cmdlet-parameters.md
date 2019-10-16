---
title: Параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.assetid: 3f1cca5f-5b95-4bce-94a6-a22db1aefd47
caps.latest.revision: 23
ms.openlocfilehash: 914a10907bcf980eed8d7e2f819c382fe6b341ad
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365933"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="2edb8-102">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="2edb8-102">Cmdlet Parameters</span></span>

<span data-ttu-id="2edb8-103">Параметры командлета предоставляют механизм, позволяющий командлету принимать входные данные.</span><span class="sxs-lookup"><span data-stu-id="2edb8-103">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="2edb8-104">Параметры могут принимать входные данные непосредственно из командной строки или из объектов, передаваемых в командлет через конвейер, аргументы (также называемые *значениями*) этих параметров могут указывать входные данные, принимаемые командлетом, способ выполнения командлетом действия и данные, возвращаемые командлетом в конвейер.</span><span class="sxs-lookup"><span data-stu-id="2edb8-104">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2edb8-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="2edb8-105">In This Section</span></span>

<span data-ttu-id="2edb8-106">[Объявление свойств как параметров](./declaring-properties-as-parameters.md) Предоставляет основные сведения, которые необходимо понимать перед объявлением параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="2edb8-106">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="2edb8-107">[Типы параметров командлета](./types-of-cmdlet-parameters.md) Описывает различные типы параметров, которые можно объявить в командлетах.</span><span class="sxs-lookup"><span data-stu-id="2edb8-107">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="2edb8-108">[Имя параметра командлета и рекомендации по функциональности](./standard-cmdlet-parameter-names-and-types.md) Дискусес имена, рекомендуемый тип данных и функциональность стандартных параметров.</span><span class="sxs-lookup"><span data-stu-id="2edb8-108">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discuses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="2edb8-109">[Псевдонимы параметров](./parameter-aliases.md) Описывает псевдонимы, которые можно определить для параметров.</span><span class="sxs-lookup"><span data-stu-id="2edb8-109">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="2edb8-110">[Общие имена параметров](./common-parameter-names.md) В этом разделе описаны параметры, которые Windows PowerShell добавляет в командлеты.</span><span class="sxs-lookup"><span data-stu-id="2edb8-110">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="2edb8-111">[Наборы параметров командлета](./cmdlet-parameter-sets.md) Описывает, как наборы параметров позволяют создавать один командлет, который может выполнять различные действия в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="2edb8-111">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="2edb8-112">[Динамические параметры командлета](./cmdlet-dynamic-parameters.md) Обсуждаются параметры, доступные пользователю при особых условиях.</span><span class="sxs-lookup"><span data-stu-id="2edb8-112">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="2edb8-113">[Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md) Описывает, как обеспечить поддержку подстановочных знаков при проектировании командлета, который будет выполняться для группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2edb8-113">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="2edb8-114">[Проверка входных параметров](./validating-parameter-input.md) Описывает, как Windows PowerShell проверяет аргументы, передаваемые в параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="2edb8-114">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="2edb8-115">[Параметры входного фильтра](./input-filter-parameters.md) Описывает параметры `Filter`, `Include` и `Exclude`, которые фильтруют набор входных объектов, на которые влияет командлет.</span><span class="sxs-lookup"><span data-stu-id="2edb8-115">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="2edb8-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2edb8-116">Related Sections</span></span>

[<span data-ttu-id="2edb8-117">Проверка входных параметров</span><span class="sxs-lookup"><span data-stu-id="2edb8-117">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="2edb8-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2edb8-118">See Also</span></span>

[<span data-ttu-id="2edb8-119">Объявление атрибута Parameter</span><span class="sxs-lookup"><span data-stu-id="2edb8-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="2edb8-120">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2edb8-120">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

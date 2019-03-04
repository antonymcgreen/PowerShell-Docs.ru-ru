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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853850"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="b9cea-102">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="b9cea-102">Cmdlet Parameters</span></span>

<span data-ttu-id="b9cea-103">Параметры командлета предоставляют механизм, позволяющий командлету, чтобы принимать входные данные.</span><span class="sxs-lookup"><span data-stu-id="b9cea-103">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="b9cea-104">Параметры могут принимать входные данные, непосредственно из командной строки или из объектов передается командлету по конвейеру, аргументы (также называется *значения*) из этих параметров можно указать ввода, который принимает командлет, как командлет необходимо выполнить действия и данных, который возвращает командлет в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b9cea-104">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9cea-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="b9cea-105">In This Section</span></span>

<span data-ttu-id="b9cea-106">[Объявление свойств как параметры](./declaring-properties-as-parameters.md) содержит основные сведения, необходимо понимать, прежде чем объявить параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="b9cea-106">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="b9cea-107">[Типы параметров командлета](./types-of-cmdlet-parameters.md) описываются различные типы параметров, которые можно объявить в командлетах.</span><span class="sxs-lookup"><span data-stu-id="b9cea-107">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="b9cea-108">[Имя параметра командлета и функциональные возможности инструкции](./standard-cmdlet-parameter-names-and-types.md) обсуждение имена, рекомендуется использовать тип данных и функциональных возможностей стандартные параметры.</span><span class="sxs-lookup"><span data-stu-id="b9cea-108">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discuses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="b9cea-109">[Псевдонимы параметра](./parameter-aliases.md) рассматриваются псевдонимы, которые можно определить для параметров.</span><span class="sxs-lookup"><span data-stu-id="b9cea-109">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="b9cea-110">[Имена общих параметров](./common-parameter-names.md) в этом разделе описываются параметры, которые добавляет командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9cea-110">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="b9cea-111">[Задает параметр командлета](./cmdlet-parameter-sets.md) рассматриваются как наборы параметров, которые позволяют создавать один командлет, который может выполнять различные действия для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="b9cea-111">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="b9cea-112">[Динамические параметры командлета](./cmdlet-dynamic-parameters.md) рассматриваются параметры, доступные для пользователя в специальных условиях.</span><span class="sxs-lookup"><span data-stu-id="b9cea-112">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="b9cea-113">[Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md) описывает способ обеспечения поддержки подстановочные знаки, при проектировании командлет, который будет выполняться для группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b9cea-113">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="b9cea-114">[Проверка входных данных параметра](./validating-parameter-input.md) показано, как Windows PowerShell проверяет аргументы, передаваемые параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="b9cea-114">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="b9cea-115">[Входные параметры фильтра](./input-filter-parameters.md) описание `Filter`, `Include`, и `Exclude` параметры фильтрации набора входных значений объектов, на которые влияет на командлет.</span><span class="sxs-lookup"><span data-stu-id="b9cea-115">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b9cea-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b9cea-116">Related Sections</span></span>

[<span data-ttu-id="b9cea-117">Как проверки входных параметров</span><span class="sxs-lookup"><span data-stu-id="b9cea-117">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="b9cea-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b9cea-118">See Also</span></span>

[<span data-ttu-id="b9cea-119">Объявление параметра-атрибут</span><span class="sxs-lookup"><span data-stu-id="b9cea-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="b9cea-120">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9cea-120">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

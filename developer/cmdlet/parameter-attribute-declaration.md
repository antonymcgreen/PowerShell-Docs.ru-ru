---
title: Объявление атрибута параметра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, Parameter
- Parameter attribute, described
- Parameter attribute
ms.assetid: 08433d0b-169b-42c8-9335-2881d9034698
caps.latest.revision: 13
ms.openlocfilehash: a3488d5fb3f7eb3df28d0242d6c39d07145a3c8d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067558"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="87899-102">Объявление атрибута параметра</span><span class="sxs-lookup"><span data-stu-id="87899-102">Parameter Attribute Declaration</span></span>

<span data-ttu-id="87899-103">Атрибут параметра определяет открытым свойством класса cmdlet как параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="87899-103">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="87899-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87899-104">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="87899-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87899-105">Parameters</span></span>

<span data-ttu-id="87899-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="87899-107">`True` Указывает, что командлет параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="87899-107">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="87899-108">Если при вызове командлета не указан обязательный параметр, Windows PowerShell запрашивает у пользователя значение параметра.</span><span class="sxs-lookup"><span data-stu-id="87899-108">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="87899-109">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="87899-109">The default is `false`.</span></span>

<span data-ttu-id="87899-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="87899-111">Указывает, что для параметра установлено, что этот командлет параметр принадлежит.</span><span class="sxs-lookup"><span data-stu-id="87899-111">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="87899-112">Если не задан параметр указан, для всех наборов параметров относится параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-112">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="87899-113">`Position` ([System.Integer](/dotnet/api/System.Integer)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-113">`Position` ([System.Integer](/dotnet/api/System.Integer)) Optional named parameter.</span></span> <span data-ttu-id="87899-114">Указывает позицию параметра в команде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87899-114">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="87899-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="87899-116">`True` Указывает, что параметр командлета получает значение из объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="87899-116">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="87899-117">Укажите это ключевое слово, если командлет осуществляет доступ к полный объект, не только свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="87899-117">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="87899-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="87899-118">The default is `false`.</span></span>

<span data-ttu-id="87899-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="87899-120">`True` Указывает, что параметр командлета получает значение из свойства объекта конвейера, с тем же именем, или тот же псевдоним в качестве этого параметра.</span><span class="sxs-lookup"><span data-stu-id="87899-120">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="87899-121">Например, если этот командлет не выполняет `Name` также имеет параметр и объект конвейера `Name` свойство, значение `Name` назначается свойство `Name` параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="87899-121">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="87899-122">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="87899-122">The default is `false`.</span></span>

<span data-ttu-id="87899-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="87899-124">`True` Указывает, что параметр командлета принимает все остальные аргументы, которые передаются в командлет.</span><span class="sxs-lookup"><span data-stu-id="87899-124">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="87899-125">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="87899-125">The default is `false`.</span></span>

<span data-ttu-id="87899-126">`HelpMessage` Необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-126">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="87899-127">Указывает краткое описание параметра.</span><span class="sxs-lookup"><span data-stu-id="87899-127">Specifies a short description of the parameter.</span></span> <span data-ttu-id="87899-128">Windows PowerShell отображается следующее сообщение при выполнении командлета и не указан обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-128">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="87899-129">`HelpMessageBaseName` Необязательный именованный параметр. Указывает расположение, в которой находятся идентификаторы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="87899-129">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="87899-130">Например этот параметр может указать сборки ресурсов, которая содержит справочные сообщения, которые необходимо локализовать.</span><span class="sxs-lookup"><span data-stu-id="87899-130">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="87899-131">`HelpMessageResourceId` Необязательный именованный параметр. Указывает идентификатор ресурса для сообщения системы помощи.</span><span class="sxs-lookup"><span data-stu-id="87899-131">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="87899-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="87899-132">Remarks</span></span>

- <span data-ttu-id="87899-133">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="87899-133">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="87899-134">У командлета может быть любое число параметров.</span><span class="sxs-lookup"><span data-stu-id="87899-134">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="87899-135">Однако для удобства пользователя, Ограничьте число параметров.</span><span class="sxs-lookup"><span data-stu-id="87899-135">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="87899-136">Параметры должны объявляться на открытые нестатические поля или свойства.</span><span class="sxs-lookup"><span data-stu-id="87899-136">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="87899-137">Параметры должны объявляться на свойства.</span><span class="sxs-lookup"><span data-stu-id="87899-137">Parameters should be declared on properties.</span></span> <span data-ttu-id="87899-138">Свойство должно иметь открытый метод доступа set и если `ValueFromPipeline` или `ValueFromPipelineByPropertyName` указывается ключевое слово, свойство должно иметь метод доступа get открытый.</span><span class="sxs-lookup"><span data-stu-id="87899-138">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="87899-139">При указании позиционные параметры, Ограничьте число позиционные параметры в качестве параметра значение меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="87899-139">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="87899-140">И позиционные параметры могут не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="87899-140">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="87899-141">Позиций, 5, 100 и 250 работать так же, как позиций 0, 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="87899-141">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="87899-142">Когда `Position` ключевое слово не задан, параметр командлета нужно ссылаться по его имени.</span><span class="sxs-lookup"><span data-stu-id="87899-142">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="87899-143">При использовании наборов параметров, обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="87899-143">When you use parameter sets, note the following:</span></span>

    - <span data-ttu-id="87899-144">Каждый набор параметров должен иметь по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="87899-144">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="87899-145">Хороший командлет проектирования указывает, что этот уникальный также должен быть обязательным, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="87899-145">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="87899-146">Если командлет должен выполняться без параметров, уникальный параметр не может быть обязательным.</span><span class="sxs-lookup"><span data-stu-id="87899-146">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

    - <span data-ttu-id="87899-147">Не задан параметр должен содержать более одного позиционного параметра с той же позиции.</span><span class="sxs-lookup"><span data-stu-id="87899-147">No parameter set should contain more than one positional parameter with the same position.</span></span>

    - <span data-ttu-id="87899-148">Следует объявлять только один параметр в набор параметров `ValueFromPipeline = true`.</span><span class="sxs-lookup"><span data-stu-id="87899-148">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="87899-149">Можно определить несколько параметров `ValueFromPipelineByPropertyName = true`.</span><span class="sxs-lookup"><span data-stu-id="87899-149">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

    - <span data-ttu-id="87899-150">Можно определить несколько параметров `ValueFromPipelineByPropertyName = true`.</span><span class="sxs-lookup"><span data-stu-id="87899-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="87899-151">Дополнительные сведения о правилах для имен параметров см. в разделе [имена параметров командлета](standard-cmdlet-parameter-names-and-types.md).</span><span class="sxs-lookup"><span data-stu-id="87899-151">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="87899-152">Атрибут параметра определяется [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="87899-152">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="87899-153">См. также</span><span class="sxs-lookup"><span data-stu-id="87899-153">See Also</span></span>

[<span data-ttu-id="87899-154">System.Management.Automation.Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="87899-154">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="87899-155">Имена параметров командлета</span><span class="sxs-lookup"><span data-stu-id="87899-155">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="87899-156">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87899-156">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

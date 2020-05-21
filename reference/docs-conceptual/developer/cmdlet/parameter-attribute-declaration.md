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
ms.openlocfilehash: 7482690c44cdaabf23b886107ac5d112c0fa5c9d
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692386"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="bb824-102">Объявление атрибута параметра</span><span class="sxs-lookup"><span data-stu-id="bb824-102">Parameter Attribute Declaration</span></span>

<span data-ttu-id="bb824-103">Атрибут Parameter определяет открытое свойство класса командлета в качестве параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="bb824-103">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb824-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb824-104">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="bb824-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb824-105">Parameters</span></span>

<span data-ttu-id="bb824-106">`Mandatory`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="bb824-107">`True`Указывает, что параметр командлета является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bb824-107">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="bb824-108">Если требуемый параметр не указан при вызове командлета, Windows PowerShell предлагает пользователю указать значение параметра.</span><span class="sxs-lookup"><span data-stu-id="bb824-108">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="bb824-109">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bb824-109">The default is `false`.</span></span>

<span data-ttu-id="bb824-110">`ParameterSetName`([System. String](/dotnet/api/System.String)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="bb824-111">Задает набор параметров, к которому относится этот параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="bb824-111">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="bb824-112">Если набор параметров не задан, параметр относится ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="bb824-112">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="bb824-113">`Position`([System. Int32](/dotnet/api/System.Int32)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-113">`Position` ([System.Int32](/dotnet/api/System.Int32)) Optional named parameter.</span></span> <span data-ttu-id="bb824-114">Задает расположение параметра в команде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb824-114">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="bb824-115">`ValueFromPipeline`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="bb824-116">`True`Указывает, что параметр командлета принимает значение из объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="bb824-116">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="bb824-117">Укажите это ключевое слово, если командлет обращается к полному объекту, а не только к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="bb824-117">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="bb824-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bb824-118">The default is `false`.</span></span>

<span data-ttu-id="bb824-119">`ValueFromPipelineByPropertyName`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="bb824-120">`True`Указывает, что параметр командлета принимает свое значение из свойства объекта конвейера с тем же именем или псевдонимом, что и у этого параметра.</span><span class="sxs-lookup"><span data-stu-id="bb824-120">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="bb824-121">Например, если у командлета есть `Name` параметр, а у объекта конвейера также есть `Name` свойство, значение `Name` свойства присваивается `Name` параметру командлета.</span><span class="sxs-lookup"><span data-stu-id="bb824-121">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="bb824-122">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bb824-122">The default is `false`.</span></span>

<span data-ttu-id="bb824-123">`ValueFromRemainingArguments`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="bb824-124">`True`Указывает, что параметр командлета принимает все оставшиеся аргументы, переданные в командлет.</span><span class="sxs-lookup"><span data-stu-id="bb824-124">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="bb824-125">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bb824-125">The default is `false`.</span></span>

<span data-ttu-id="bb824-126">`HelpMessage`Необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-126">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="bb824-127">Задает краткое описание параметра.</span><span class="sxs-lookup"><span data-stu-id="bb824-127">Specifies a short description of the parameter.</span></span> <span data-ttu-id="bb824-128">Windows PowerShell отображает это сообщение при выполнении командлета, а обязательный параметр не указан.</span><span class="sxs-lookup"><span data-stu-id="bb824-128">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="bb824-129">`HelpMessageBaseName`Необязательный именованный параметр. Указывает расположение, в котором находятся идентификаторы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bb824-129">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="bb824-130">Например, этот параметр может указывать сборку ресурсов, содержащую справочные сообщения, которые требуется локализовать.</span><span class="sxs-lookup"><span data-stu-id="bb824-130">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="bb824-131">`HelpMessageResourceId`Необязательный именованный параметр. Указывает идентификатор ресурса для сообщения справки.</span><span class="sxs-lookup"><span data-stu-id="bb824-131">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb824-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bb824-132">Remarks</span></span>

- <span data-ttu-id="bb824-133">Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bb824-133">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="bb824-134">Командлет может иметь любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="bb824-134">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="bb824-135">Однако для повышения удобства работы пользователей Ограничьте количество параметров.</span><span class="sxs-lookup"><span data-stu-id="bb824-135">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="bb824-136">Параметры должны быть объявлены для открытых нестатических полей или свойств.</span><span class="sxs-lookup"><span data-stu-id="bb824-136">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="bb824-137">Параметры должны быть объявлены в свойствах.</span><span class="sxs-lookup"><span data-stu-id="bb824-137">Parameters should be declared on properties.</span></span> <span data-ttu-id="bb824-138">Свойство должно иметь открытый метод доступа set, и если `ValueFromPipeline` `ValueFromPipelineByPropertyName` указано ключевое слово или, свойство должно иметь открытый метод доступа get.</span><span class="sxs-lookup"><span data-stu-id="bb824-138">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="bb824-139">При указании позиционированных параметров Ограничьте число параметров, заданных в параметре, равным меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="bb824-139">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="bb824-140">И параметры позиционирования не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="bb824-140">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="bb824-141">Позиции 5, 100 и 250 работают так же, как позиции 0, 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="bb824-141">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="bb824-142">Если `Position` ключевое слово не указано, на параметр командлета должно ссылаться имя.</span><span class="sxs-lookup"><span data-stu-id="bb824-142">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="bb824-143">При использовании наборов параметров Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="bb824-143">When you use parameter sets, note the following:</span></span>

  - <span data-ttu-id="bb824-144">Каждый набор параметров должен иметь по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb824-144">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="bb824-145">Хорошая структура командлетов указывает, что этот уникальный параметр также должен быть обязательным, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="bb824-145">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="bb824-146">Если командлет предназначен для выполнения без параметров, то уникальный параметр не может быть обязательным.</span><span class="sxs-lookup"><span data-stu-id="bb824-146">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

  - <span data-ttu-id="bb824-147">Ни один из наборов параметров не должен содержать более одного позиционированного параметра с одинаковой позицией.</span><span class="sxs-lookup"><span data-stu-id="bb824-147">No parameter set should contain more than one positional parameter with the same position.</span></span>

  - <span data-ttu-id="bb824-148">Только один параметр в наборе параметров должен объявлять `ValueFromPipeline = true` .</span><span class="sxs-lookup"><span data-stu-id="bb824-148">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="bb824-149">Может быть определено несколько параметров `ValueFromPipelineByPropertyName = true` .</span><span class="sxs-lookup"><span data-stu-id="bb824-149">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

  - <span data-ttu-id="bb824-150">Может быть определено несколько параметров `ValueFromPipelineByPropertyName = true` .</span><span class="sxs-lookup"><span data-stu-id="bb824-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="bb824-151">Дополнительные сведения о рекомендациях по именам параметров см. в разделе [имена параметров командлета](standard-cmdlet-parameter-names-and-types.md).</span><span class="sxs-lookup"><span data-stu-id="bb824-151">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="bb824-152">Атрибут параметра определяется классом [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="bb824-152">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb824-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb824-153">See Also</span></span>

[<span data-ttu-id="bb824-154">System. Management. Automation. Параметераттрибуте</span><span class="sxs-lookup"><span data-stu-id="bb824-154">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="bb824-155">Имена параметров командлета</span><span class="sxs-lookup"><span data-stu-id="bb824-155">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="bb824-156">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb824-156">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

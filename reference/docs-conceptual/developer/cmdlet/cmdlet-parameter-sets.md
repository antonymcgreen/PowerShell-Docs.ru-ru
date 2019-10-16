---
title: Наборы параметров командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: d8c00c7ffd369a32af151836785a2c5f47b05a68
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365903"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="57b01-102">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="57b01-102">Cmdlet parameter sets</span></span>

<span data-ttu-id="57b01-103">В PowerShell используются наборы параметров, позволяющие создавать один командлет, который может выполнять различные действия в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="57b01-103">PowerShell uses parameter sets to enable you to write a single cmdlet that can do different actions for different scenarios.</span></span> <span data-ttu-id="57b01-104">Наборы параметров позволяют предоставлять пользователю различные параметры.</span><span class="sxs-lookup"><span data-stu-id="57b01-104">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="57b01-105">И, чтобы получить различные сведения на основе параметров, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="57b01-105">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="57b01-106">Примеры наборов параметров</span><span class="sxs-lookup"><span data-stu-id="57b01-106">Examples of parameter sets</span></span>

<span data-ttu-id="57b01-107">Например, командлет PowerShell `Get-EventLog` возвращает различную информацию в зависимости от того, указывает ли пользователь параметр **List** или **/l** .</span><span class="sxs-lookup"><span data-stu-id="57b01-107">For example, the PowerShell `Get-EventLog` cmdlet returns different information depending on whether the user specifies the **List** or **LogName** parameter.</span></span> <span data-ttu-id="57b01-108">Если указан параметр **List** , командлет возвращает сведения о самих файлах журнала, но не сведения о событиях, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="57b01-108">If the **List** parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="57b01-109">Если указан параметр " **/l** ", командлет возвращает сведения о событиях в определенном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="57b01-109">If the **LogName** parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="57b01-110">Параметры **List** и параметров задания указывают два отдельных набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-110">The **List** and **LogName** parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="57b01-111">Уникальный параметр</span><span class="sxs-lookup"><span data-stu-id="57b01-111">Unique parameter</span></span>

<span data-ttu-id="57b01-112">Каждый набор параметров должен иметь уникальный параметр, используемый средой выполнения PowerShell для предоставления соответствующего набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-112">Each parameter set must have a unique parameter that the PowerShell runtime uses to expose the appropriate parameter set.</span></span> <span data-ttu-id="57b01-113">Если это возможно, уникальный параметр должен быть обязательным.</span><span class="sxs-lookup"><span data-stu-id="57b01-113">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="57b01-114">Если параметр является обязательным, пользователь должен указать параметр, а среда выполнения PowerShell использует этот параметр для определения набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-114">When a parameter is mandatory, the user must specify the parameter, and the PowerShell runtime uses that parameter to identify the parameter set.</span></span> <span data-ttu-id="57b01-115">Уникальный параметр не может быть обязательным, если командлет предназначен для запуска без указания каких-либо параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-115">The unique parameter can't be mandatory if your cmdlet is designed to run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="57b01-116">Несколько наборов параметров</span><span class="sxs-lookup"><span data-stu-id="57b01-116">Multiple parameter sets</span></span>

<span data-ttu-id="57b01-117">На следующем рисунке в левом столбце показаны три допустимых набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-117">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="57b01-118">**Параметр A** уникален для первого набора параметров, **параметр B** уникален для второго набора параметров, а **параметр C** является уникальным для третьего набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-118">**Parameter A** is unique to the first parameter set, **parameter B** is unique to the second parameter set, and **parameter C** is unique to the third parameter set.</span></span> <span data-ttu-id="57b01-119">В правом столбце наборы параметров не имеют уникального параметра.</span><span class="sxs-lookup"><span data-stu-id="57b01-119">In the right column, the parameter sets don't have a unique parameter.</span></span>

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="57b01-121">Требования к наборам параметров</span><span class="sxs-lookup"><span data-stu-id="57b01-121">Parameter set requirements</span></span>

<span data-ttu-id="57b01-122">Следующие требования применяются ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-122">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="57b01-123">Каждый набор параметров должен иметь по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="57b01-123">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="57b01-124">Если это возможно, присвоить этому параметру обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="57b01-124">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="57b01-125">Набор параметров, содержащий несколько позиционированных параметров, должен определять уникальные позиции для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="57b01-125">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="57b01-126">Ни один из двух параметров позиционирования не может указывать одну и ту же точку.</span><span class="sxs-lookup"><span data-stu-id="57b01-126">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="57b01-127">Только один параметр в наборе может объявить ключевое слово `ValueFromPipeline` со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="57b01-127">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span>
  <span data-ttu-id="57b01-128">Несколько параметров могут определять ключевое слово `ValueFromPipelineByPropertyName` со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="57b01-128">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="57b01-129">Если для параметра не задан набор параметров, параметр относится ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-129">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="57b01-130">Для командлета или функции существует ограничение в 32 наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-130">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="57b01-131">Наборы параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="57b01-131">Default parameter sets</span></span>

<span data-ttu-id="57b01-132">Если определено несколько наборов параметров, можно использовать ключевое слово `DefaultParameterSetName` атрибута **командлета** , чтобы указать набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57b01-132">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the **Cmdlet** attribute to specify the default parameter set.</span></span> <span data-ttu-id="57b01-133">PowerShell использует набор параметров по умолчанию, если не может определить набор параметров для использования на основе сведений, предоставленных командой.</span><span class="sxs-lookup"><span data-stu-id="57b01-133">PowerShell uses the default parameter set if it can't determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="57b01-134">Дополнительные сведения об атрибуте **командлета** см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="57b01-134">For more information about the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="57b01-135">Объявление наборов параметров</span><span class="sxs-lookup"><span data-stu-id="57b01-135">Declaring parameter sets</span></span>

<span data-ttu-id="57b01-136">Чтобы создать набор параметров, необходимо указать ключевое слово `ParameterSetName` при объявлении атрибута **параметра** для каждого параметра в наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-136">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="57b01-137">Для параметров, принадлежащих к нескольким наборам параметров, добавьте атрибут **параметра** для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-137">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span> <span data-ttu-id="57b01-138">Этот атрибут позволяет определить параметр по-разному для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="57b01-138">This attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="57b01-139">Например, можно определить параметр как обязательный в одном наборе и необязательный в другом.</span><span class="sxs-lookup"><span data-stu-id="57b01-139">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="57b01-140">Однако каждый набор параметров должен содержать один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="57b01-140">However, each parameter set must contain one unique parameter.</span></span> <span data-ttu-id="57b01-141">Дополнительные сведения см. в разделе [объявление атрибута Parameter](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="57b01-141">For more information, see [Parameter Attribute Declaration](parameter-attribute-declaration.md).</span></span>

<span data-ttu-id="57b01-142">В следующем примере параметр **username** является уникальным параметром набора параметров `Test01`, а параметр **ComputerName** является уникальным параметром набора параметров `Test02`.</span><span class="sxs-lookup"><span data-stu-id="57b01-142">In the following example, the **UserName** parameter is the unique parameter of the `Test01` parameter set, and the **ComputerName** parameter is the unique parameter of the `Test02` parameter set.</span></span> <span data-ttu-id="57b01-143">Параметр **шаредпарам** принадлежит обоим наборам и является обязательным для набора параметров `Test01`, но необязателен для набора параметров `Test02`.</span><span class="sxs-lookup"><span data-stu-id="57b01-143">The **SharedParam** parameter belongs to both sets and is mandatory for the `Test01` parameter set but optional for the `Test02` parameter set.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test02")]
public string ComputerName
{
  get { return computerName; }
  set { computerName = value; }
}
private string computerName;

[Parameter(Mandatory= true, ParameterSetName = "Test01")]
[Parameter(ParameterSetName = "Test02")]
public string SharedParam
{
    get { return sharedParam; }
    set { sharedParam = value; }
}
private string sharedParam;
```

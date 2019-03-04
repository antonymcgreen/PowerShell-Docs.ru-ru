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
ms.openlocfilehash: a5822ef1ed3c9efb5957c20255783d515de8957a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857270"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="3b4c7-102">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="3b4c7-102">Cmdlet Parameter Sets</span></span>

<span data-ttu-id="3b4c7-103">Windows PowerShell использует наборы параметров для позволяют использовать один командлет, который может выполнять различные действия для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-103">Windows PowerShell uses parameter sets to enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span> <span data-ttu-id="3b4c7-104">Наборы параметров позволяют предоставлять различные параметры для пользователя и возвращают различные сведения, в зависимости от параметров, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-104">Parameter sets enable you to expose different parameters to the user and to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="3b4c7-105">Примеры наборов параметров</span><span class="sxs-lookup"><span data-stu-id="3b4c7-105">Examples of Parameter Sets</span></span>

<span data-ttu-id="3b4c7-106">Например `Get-EventLog` командлет (предоставляемое Windows PowerShell) возвращает разную информацию в зависимости от того, является ли пользователь указывает `List` или `LogName` параметра.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-106">For example, the `Get-EventLog` cmdlet (provided by Windows PowerShell) returns different information depending on whether the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="3b4c7-107">Если `List` параметр указан, командлет возвращает сведения о файлах журналов, сами, но не о событиях, они содержат.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-107">If the `List` parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="3b4c7-108">Если `LogName` параметр указан, командлет возвращает информацию о событиях в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="3b4c7-109">`List` И `LogName` параметры определяют две различные наборы параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-109">The `List` and `LogName` parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="3b4c7-110">Параметр UNIQUE командлета</span><span class="sxs-lookup"><span data-stu-id="3b4c7-110">Unique Parameter</span></span>

<span data-ttu-id="3b4c7-111">Каждый набор параметров должен иметь уникальный параметр, среда выполнения Windows PowerShell можно использовать для предоставления набор соответствующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-111">Each parameter set must have a unique parameter that the Windows PowerShell runtime can use to expose the appropriate parameter set.</span></span> <span data-ttu-id="3b4c7-112">Если это возможно уникальный параметр должен быть обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-112">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="3b4c7-113">Когда параметр является обязательным, пользователь вынужден укажите параметр и среды выполнения Windows PowerShell с помощью этого параметра для определения параметров, настроенный для использования.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-113">When a parameter is mandatory, the user is forced to specify the parameter, and the Windows PowerShell runtime can use that parameter to identify the parameter set to use.</span></span> <span data-ttu-id="3b4c7-114">Уникальный параметр не может быть обязательным в том случае, если командлет должен выполняться без параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-114">The unique parameter cannot be mandatory if your cmdlet is designed to be run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="3b4c7-115">Несколько наборов параметров</span><span class="sxs-lookup"><span data-stu-id="3b4c7-115">Multiple Parameter Sets</span></span>

<span data-ttu-id="3b4c7-116">На следующем рисунке в левом столбце отображаются три набора допустимых параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-116">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="3b4c7-117">Параметр типа является уникальным для первого набора параметров, параметр B является уникальным для второй набор параметров, и параметр C является уникальным для третий набор параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-117">Parameter A is unique to the first parameter set, parameter B is unique to the second parameter set, and parameter C is unique to the third parameter set.</span></span> <span data-ttu-id="3b4c7-118">Тем не менее в столбце справа от наборов параметров нет уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-118">However, in the right column, the parameter sets do not have a unique parameter.</span></span>

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="3b4c7-120">Требования к параметру Set.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-120">Parameter Set Requirements</span></span>

<span data-ttu-id="3b4c7-121">Следующие требования применяются для всех наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-121">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="3b4c7-122">Каждый набор параметров должен иметь по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-122">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="3b4c7-123">По возможности сделайте этот параметр обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-123">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="3b4c7-124">Набор параметров, содержащий несколько позиционные параметры необходимо определить уникальное позиции для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-124">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="3b4c7-125">Без два позиционных параметров можно указать ту же позицию.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-125">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="3b4c7-126">Можно объявить только один параметр в наборе `ValueFromPipeline` ключевое слово со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-126">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="3b4c7-127">Можно определить несколько параметров `ValueFromPipelineByPropertyName` ключевое слово со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-127">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="3b4c7-128">Если не задан параметр не указан для параметра, для всех наборов параметров относится параметр.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-128">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="3b4c7-129">Наборы параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3b4c7-129">Default Parameter Sets</span></span>

<span data-ttu-id="3b4c7-130">Если определены несколько наборов параметров, можно использовать `DefaultParameterSetName` ключевое слово атрибута командлет, чтобы указать набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-130">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the Cmdlet attribute to specify the default parameter set.</span></span> <span data-ttu-id="3b4c7-131">Windows PowerShell использует параметр по умолчанию, если он не может определить параметр, настроенный для использования на основе данных командой.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-131">Windows PowerShell uses the default parameter set if it cannot determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="3b4c7-132">Дополнительные сведения об атрибуте командлета см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3b4c7-132">For more information about the Cmdlet attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="3b4c7-133">Объявление наборов параметров</span><span class="sxs-lookup"><span data-stu-id="3b4c7-133">Declaring Parameter Sets</span></span>

<span data-ttu-id="3b4c7-134">Чтобы создать набор параметров, необходимо указать `ParameterSetName` ключевое слово при объявлении атрибут параметра для каждого параметра в наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-134">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the Parameter attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="3b4c7-135">Для параметров, которые принадлежат несколько наборов параметров добавьте атрибут параметра для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-135">For parameters that belong to multiple parameter sets, add a Parameter attribute for each parameter set.</span></span> <span data-ttu-id="3b4c7-136">Это позволяет определить параметр по-разному для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-136">This enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="3b4c7-137">Например можно определить параметр как обязательные в одном наборе и необязательные в другом.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-137">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="3b4c7-138">Тем не менее каждый набор параметров должен содержать один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-138">However, each parameter set must contain one unique parameter.</span></span>

<span data-ttu-id="3b4c7-139">В следующем примере `UserName` параметр — это уникальный параметр Test01 набор параметров и `ComputerName` параметр — это уникальный параметр Test02 набор параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-139">In the following example, the `UserName` parameter is the unique parameter of the Test01 parameter set, and the `ComputerName` parameter is the unique parameter of the Test02 parameter set.</span></span> <span data-ttu-id="3b4c7-140">`SharedParam` Параметр принадлежит к обоим наборам и является обязательным для параметра Test01 установить, но необязательно для Test02 набор параметров.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-140">The `SharedParam` parameter belongs to both sets and is mandatory for the Test01 parameter set but optional for the Test02 parameter set.</span></span>

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
private string sharedParam;    [Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```
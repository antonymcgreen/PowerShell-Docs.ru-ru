---
ms.date: 09/13/2016
ms.topic: reference
title: Наборы параметров командлета
description: Наборы параметров командлета
ms.openlocfilehash: e84af7faf5b7459d8dbe06847526efe804e2c5e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668292"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="34c0a-103">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="34c0a-103">Cmdlet parameter sets</span></span>

<span data-ttu-id="34c0a-104">В PowerShell используются наборы параметров, позволяющие создавать один командлет, который может выполнять различные действия в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="34c0a-104">PowerShell uses parameter sets to enable you to write a single cmdlet that can do different actions for different scenarios.</span></span> <span data-ttu-id="34c0a-105">Наборы параметров позволяют предоставлять пользователю различные параметры.</span><span class="sxs-lookup"><span data-stu-id="34c0a-105">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="34c0a-106">И, чтобы получить различные сведения на основе параметров, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="34c0a-106">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="34c0a-107">Примеры наборов параметров</span><span class="sxs-lookup"><span data-stu-id="34c0a-107">Examples of parameter sets</span></span>

<span data-ttu-id="34c0a-108">Например, `Get-EventLog` командлет PowerShell возвращает различные сведения в зависимости от того, указывает ли пользователь параметр **List** или i  .</span><span class="sxs-lookup"><span data-stu-id="34c0a-108">For example, the PowerShell `Get-EventLog` cmdlet returns different information depending on whether the user specifies the **List** or **LogName** parameter.</span></span> <span data-ttu-id="34c0a-109">Если указан параметр **List** , командлет возвращает сведения о самих файлах журнала, но не сведения о событиях, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="34c0a-109">If the **List** parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="34c0a-110">Если указан параметр " **/l** ", командлет возвращает сведения о событиях в определенном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="34c0a-110">If the **LogName** parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="34c0a-111">Параметры **List** и  параметров задания указывают два отдельных набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-111">The **List** and **LogName** parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="34c0a-112">Уникальный параметр</span><span class="sxs-lookup"><span data-stu-id="34c0a-112">Unique parameter</span></span>

<span data-ttu-id="34c0a-113">Каждый набор параметров должен иметь уникальный параметр, используемый средой выполнения PowerShell для предоставления соответствующего набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-113">Each parameter set must have a unique parameter that the PowerShell runtime uses to expose the appropriate parameter set.</span></span> <span data-ttu-id="34c0a-114">Если это возможно, уникальный параметр должен быть обязательным.</span><span class="sxs-lookup"><span data-stu-id="34c0a-114">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="34c0a-115">Если параметр является обязательным, пользователь должен указать параметр, а среда выполнения PowerShell использует этот параметр для определения набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-115">When a parameter is mandatory, the user must specify the parameter, and the PowerShell runtime uses that parameter to identify the parameter set.</span></span> <span data-ttu-id="34c0a-116">Уникальный параметр не может быть обязательным, если командлет предназначен для запуска без указания каких-либо параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-116">The unique parameter can't be mandatory if your cmdlet is designed to run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="34c0a-117">Несколько наборов параметров</span><span class="sxs-lookup"><span data-stu-id="34c0a-117">Multiple parameter sets</span></span>

<span data-ttu-id="34c0a-118">На следующем рисунке в левом столбце показаны три допустимых набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-118">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="34c0a-119">**Параметр A** уникален для первого набора параметров, **параметр B** уникален для второго набора параметров, а **параметр C** является уникальным для третьего набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-119">**Parameter A** is unique to the first parameter set, **parameter B** is unique to the second parameter set, and **parameter C** is unique to the third parameter set.</span></span> <span data-ttu-id="34c0a-120">В правом столбце наборы параметров не имеют уникального параметра.</span><span class="sxs-lookup"><span data-stu-id="34c0a-120">In the right column, the parameter sets don't have a unique parameter.</span></span>

![Иллюстрация наборов параметров](media/cmdlet-parameter-sets/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="34c0a-122">Требования к наборам параметров</span><span class="sxs-lookup"><span data-stu-id="34c0a-122">Parameter set requirements</span></span>

<span data-ttu-id="34c0a-123">Следующие требования применяются ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-123">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="34c0a-124">Каждый набор параметров должен иметь по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="34c0a-124">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="34c0a-125">Если это возможно, присвоить этому параметру обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="34c0a-125">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="34c0a-126">Набор параметров, содержащий несколько позиционированных параметров, должен определять уникальные позиции для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="34c0a-126">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="34c0a-127">Ни один из двух параметров позиционирования не может указывать одну и ту же точку.</span><span class="sxs-lookup"><span data-stu-id="34c0a-127">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="34c0a-128">Только один параметр в наборе может объявить `ValueFromPipeline` ключевое слово со значением `true` .</span><span class="sxs-lookup"><span data-stu-id="34c0a-128">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span>
  <span data-ttu-id="34c0a-129">Несколько параметров могут определять `ValueFromPipelineByPropertyName` ключевое слово со значением `true` .</span><span class="sxs-lookup"><span data-stu-id="34c0a-129">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="34c0a-130">Если для параметра не задан набор параметров, параметр относится ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-130">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="34c0a-131">Для командлета или функции существует ограничение в 32 наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-131">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="34c0a-132">Наборы параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="34c0a-132">Default parameter sets</span></span>

<span data-ttu-id="34c0a-133">Если определено несколько наборов параметров, можно использовать `DefaultParameterSetName` ключевое слово атрибута **командлета** для указания набора параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34c0a-133">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the **Cmdlet** attribute to specify the default parameter set.</span></span> <span data-ttu-id="34c0a-134">PowerShell использует набор параметров по умолчанию, если не может определить набор параметров для использования на основе сведений, предоставленных командой.</span><span class="sxs-lookup"><span data-stu-id="34c0a-134">PowerShell uses the default parameter set if it can't determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="34c0a-135">Дополнительные сведения об атрибуте **командлета** см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="34c0a-135">For more information about the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="34c0a-136">Объявление наборов параметров</span><span class="sxs-lookup"><span data-stu-id="34c0a-136">Declaring parameter sets</span></span>

<span data-ttu-id="34c0a-137">Чтобы создать набор параметров, необходимо указать `ParameterSetName` ключевое слово при объявлении атрибута **Parameter** для каждого параметра в наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-137">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="34c0a-138">Для параметров, принадлежащих к нескольким наборам параметров, добавьте атрибут **параметра** для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-138">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span> <span data-ttu-id="34c0a-139">Этот атрибут позволяет определить параметр по-разному для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-139">This attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="34c0a-140">Например, можно определить параметр как обязательный в одном наборе и необязательный в другом.</span><span class="sxs-lookup"><span data-stu-id="34c0a-140">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="34c0a-141">Однако каждый набор параметров должен содержать один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="34c0a-141">However, each parameter set must contain one unique parameter.</span></span> <span data-ttu-id="34c0a-142">Дополнительные сведения см. в разделе [объявление атрибута Parameter](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="34c0a-142">For more information, see [Parameter Attribute Declaration](parameter-attribute-declaration.md).</span></span>

<span data-ttu-id="34c0a-143">В следующем примере параметр **username** является уникальным параметром `Test01` набора параметров, а параметр **ComputerName** — уникальным параметром `Test02` набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-143">In the following example, the **UserName** parameter is the unique parameter of the `Test01` parameter set, and the **ComputerName** parameter is the unique parameter of the `Test02` parameter set.</span></span> <span data-ttu-id="34c0a-144">Параметр **шаредпарам** относится к обоим наборам и является обязательным для `Test01` набора параметров, но необязателен для `Test02` набора параметров.</span><span class="sxs-lookup"><span data-stu-id="34c0a-144">The **SharedParam** parameter belongs to both sets and is mandatory for the `Test01` parameter set but optional for the `Test02` parameter set.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test02")]
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

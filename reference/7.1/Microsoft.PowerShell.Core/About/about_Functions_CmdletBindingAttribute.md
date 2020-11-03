---
description: Описывает атрибут, который делает функцию функционировать как скомпилированный командлет.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: eb6e161fd03898fe420103c04b26c0f6249be590
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232137"
---
# <a name="about-functions-cmdletbindingattribute"></a><span data-ttu-id="11be9-104">О функциях Кмдлетбиндингаттрибуте</span><span class="sxs-lookup"><span data-stu-id="11be9-104">About Functions CmdletBindingAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="11be9-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="11be9-105">Short description</span></span>
<span data-ttu-id="11be9-106">Описывает атрибут, который делает функцию функционировать как скомпилированный командлет.</span><span class="sxs-lookup"><span data-stu-id="11be9-106">Describes the attribute that makes a function work like a compiled cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="11be9-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="11be9-107">Long description</span></span>

<span data-ttu-id="11be9-108">`CmdletBinding`Атрибут является атрибутом функций, которые делают их работать как скомпилированные командлеты, написанные на языке C#.</span><span class="sxs-lookup"><span data-stu-id="11be9-108">The `CmdletBinding` attribute is an attribute of functions that makes them operate like compiled cmdlets written in C#.</span></span> <span data-ttu-id="11be9-109">Он предоставляет доступ к функциям командлетов.</span><span class="sxs-lookup"><span data-stu-id="11be9-109">It provides access to the features of cmdlets.</span></span>

<span data-ttu-id="11be9-110">PowerShell привязывает параметры функций, имеющих атрибут, так `CmdletBinding` же, как он привязывает параметры скомпилированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="11be9-110">PowerShell binds the parameters of functions that have the `CmdletBinding` attribute in the same way that it binds the parameters of compiled cmdlets.</span></span> <span data-ttu-id="11be9-111">`$PSCmdlet`Автоматическая переменная доступна для функций с `CmdletBinding` атрибутом, но `$Args` переменная недоступна.</span><span class="sxs-lookup"><span data-stu-id="11be9-111">The `$PSCmdlet` automatic variable is available to functions with the `CmdletBinding` attribute, but the `$Args` variable is not available.</span></span>

<span data-ttu-id="11be9-112">В функциях, имеющих `CmdletBinding` атрибут, неизвестные параметры и аргументы, которые не имеют соответствующих параметров позиционирования, приводят к сбою привязки параметра.</span><span class="sxs-lookup"><span data-stu-id="11be9-112">In functions that have the `CmdletBinding` attribute, unknown parameters and positional arguments that have no matching positional parameters cause parameter binding to fail.</span></span>

> [!NOTE]
> <span data-ttu-id="11be9-113">Скомпилированные командлеты используют `Cmdlet` атрибут Required, который аналогичен `CmdletBinding` атрибуту, описанному в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="11be9-113">Compiled cmdlets use the required `Cmdlet` attribute, which is similar to the `CmdletBinding` attribute that is described in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="11be9-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11be9-114">Syntax</span></span>

<span data-ttu-id="11be9-115">В следующем примере показан формат функции, указывающей все необязательные аргументы `CmdletBinding` атрибута.</span><span class="sxs-lookup"><span data-stu-id="11be9-115">The following example shows the format of a function that specifies all the optional arguments of the `CmdletBinding` attribute.</span></span> <span data-ttu-id="11be9-116">Ниже приведено краткое описание каждого аргумента.</span><span class="sxs-lookup"><span data-stu-id="11be9-116">A brief description of each argument follows this example.</span></span>

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a><span data-ttu-id="11be9-117">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="11be9-117">ConfirmImpact</span></span>

<span data-ttu-id="11be9-118">Аргумент **ConfirmImpact** указывает, когда действие функции должно быть подтверждено вызовом метода **ShouldProcess** .</span><span class="sxs-lookup"><span data-stu-id="11be9-118">The **ConfirmImpact** argument specifies when the action of the function should be confirmed by a call to the **ShouldProcess** method.</span></span> <span data-ttu-id="11be9-119">Вызов метода **ShouldProcess** отображает запрос подтверждения, только если аргумент **ConfirmImpact** равен значению `$ConfirmPreference` привилегированной переменной или больше него.</span><span class="sxs-lookup"><span data-stu-id="11be9-119">The call to the **ShouldProcess** method displays a confirmation prompt only when the **ConfirmImpact** argument is equal to or greater than the value of the `$ConfirmPreference` preference variable.</span></span> <span data-ttu-id="11be9-120">(Значение аргумента по умолчанию — **Medium**.) Указывайте этот аргумент только в том случае, если также указан аргумент **SupportsShouldProcess** .</span><span class="sxs-lookup"><span data-stu-id="11be9-120">(The default value of the argument is **Medium**.) Specify this argument only when the **SupportsShouldProcess** argument is also specified.</span></span>

<span data-ttu-id="11be9-121">Дополнительные сведения о запросах на подтверждение см. в разделе [запрос подтверждения](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="11be9-121">For more information about confirmation requests, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

## <a name="defaultparametersetname"></a><span data-ttu-id="11be9-122">DefaultParameterSetName</span><span class="sxs-lookup"><span data-stu-id="11be9-122">DefaultParameterSetName</span></span>

<span data-ttu-id="11be9-123">Аргумент **дефаултпараметерсетнаме** указывает имя набора параметров, который PowerShell будет пытаться использовать, если не сможет определить, какой набор параметров использовать.</span><span class="sxs-lookup"><span data-stu-id="11be9-123">The **DefaultParameterSetName** argument specifies the name of the parameter set that PowerShell will attempt to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="11be9-124">Эту ошибку можно избежать, сделав уникальный параметр для каждого параметра, устанавливая обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="11be9-124">You can avoid this issue by making the unique parameter of each parameter set a mandatory parameter.</span></span>

## <a name="helpuri"></a><span data-ttu-id="11be9-125">HelpURI</span><span class="sxs-lookup"><span data-stu-id="11be9-125">HelpURI</span></span>

<span data-ttu-id="11be9-126">Аргумент **HelpURI** указывает Интернет-адрес интерактивной версии раздела справки, описывающего функцию.</span><span class="sxs-lookup"><span data-stu-id="11be9-126">The **HelpURI** argument specifies the internet address of the online version of the help topic that describes the function.</span></span> <span data-ttu-id="11be9-127">Значение аргумента **HelpURI** должно начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="11be9-127">The value of the **HelpURI** argument must begin with "http" or "https".</span></span>

<span data-ttu-id="11be9-128">Значение аргумента **HelpURI** используется для значения свойства **HelpURI** объекта **CommandInfo** , который `Get-Command` возвращает значение для функции.</span><span class="sxs-lookup"><span data-stu-id="11be9-128">The **HelpURI** argument value is used for the value of the **HelpURI** property of the **CommandInfo** object that `Get-Command` returns for the function.</span></span>

<span data-ttu-id="11be9-129">Однако если файлы справки установлены на компьютере, а значение первой ссылки в разделе **релатедлинкс** файла справки является URI, а значение первой `.Link` директивы в справке на основе комментариев — URI, URI в файле справки используется в качестве значения свойства **HelpUri** для функции.</span><span class="sxs-lookup"><span data-stu-id="11be9-129">However, when help files are installed on the computer and the value of the first link in the **RelatedLinks** section of the help file is a URI, or the value of the first `.Link` directive in comment-based help is a URI, the URI in the help file is used as the value of the **HelpUri** property of the function.</span></span>

<span data-ttu-id="11be9-130">`Get-Help`Командлет использует значение свойства **HelpURI** , чтобы определить Интернет-версию раздела справки по функции, если в команде указан параметр **Online** `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="11be9-130">The `Get-Help` cmdlet uses the value of the **HelpURI** property to locate the online version of the function help topic when the **Online** parameter of `Get-Help` is specified in a command.</span></span>

## <a name="supportspaging"></a><span data-ttu-id="11be9-131">суппортспагинг</span><span class="sxs-lookup"><span data-stu-id="11be9-131">SupportsPaging</span></span>

<span data-ttu-id="11be9-132">Аргумент **суппортспагинг** добавляет в функцию **первые** параметры, **Skip** и **IncludeTotalCount** .</span><span class="sxs-lookup"><span data-stu-id="11be9-132">The **SupportsPaging** argument adds the **First** , **Skip** , and **IncludeTotalCount** parameters to the function.</span></span> <span data-ttu-id="11be9-133">Эти параметры позволяют пользователям выбирать выходные данные из очень большого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="11be9-133">These parameters allow users to select output from a very large result set.</span></span> <span data-ttu-id="11be9-134">Этот аргумент предназначен для командлетов и функций, возвращающих данные из больших хранилищ данных, которые поддерживают выбор данных, например базу данных SQL.</span><span class="sxs-lookup"><span data-stu-id="11be9-134">This argument is designed for cmdlets and functions that return data from large data stores that support data selection, such as an SQL database.</span></span>

<span data-ttu-id="11be9-135">Этот аргумент появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="11be9-135">This argument was introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="11be9-136">**First** : возвращает только первые "n" объектов.</span><span class="sxs-lookup"><span data-stu-id="11be9-136">**First** : Gets only the first 'n' objects.</span></span>
- <span data-ttu-id="11be9-137">**Пропустить** : пропускает первые объекты "n", а затем получает оставшиеся объекты.</span><span class="sxs-lookup"><span data-stu-id="11be9-137">**Skip** :  Ignores the first 'n' objects and then gets the remaining objects.</span></span>
- <span data-ttu-id="11be9-138">**IncludeTotalCount** : сообщает количество объектов в наборе данных (целое число), за которыми следуют объекты.</span><span class="sxs-lookup"><span data-stu-id="11be9-138">**IncludeTotalCount** : Reports the number of objects in the data set (an integer) followed by the objects.</span></span> <span data-ttu-id="11be9-139">Если командлет не может определить общее число, возвращается значение "Неизвестный общий счетчик".</span><span class="sxs-lookup"><span data-stu-id="11be9-139">If the cmdlet cannot determine the total count, it returns "Unknown total count".</span></span>

<span data-ttu-id="11be9-140">PowerShell включает **невтоталкаунт** — вспомогательный метод, который получает значение общего числа для возврата и включает оценку точности значения общего числа.</span><span class="sxs-lookup"><span data-stu-id="11be9-140">PowerShell includes **NewTotalCount** , a helper method that gets the total count value to return and includes an estimate of the accuracy of the total count value.</span></span>

<span data-ttu-id="11be9-141">В следующем примере функции показано, как добавить поддержку параметров разбиения по страницам в расширенную функцию.</span><span class="sxs-lookup"><span data-stu-id="11be9-141">The following sample function shows how to add support for the paging parameters to an advanced function.</span></span>

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="11be9-142">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="11be9-142">SupportsShouldProcess</span></span>

<span data-ttu-id="11be9-143">Аргумент **SupportsShouldProcess** добавляет в функцию параметры **Confirm** и **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="11be9-143">The **SupportsShouldProcess** argument adds **Confirm** and **WhatIf** parameters to the function.</span></span> <span data-ttu-id="11be9-144">Параметр **Confirm** запрашивает у пользователя перед выполнением команды для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="11be9-144">The **Confirm** parameter prompts the user before it runs the command on each object in the pipeline.</span></span> <span data-ttu-id="11be9-145">Параметр **WhatIf** перечисляет изменения, которые могут быть внесены командой, вместо выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="11be9-145">The **WhatIf** parameter lists the changes that the command would make, instead of running the command.</span></span>

## <a name="positionalbinding"></a><span data-ttu-id="11be9-146">PositionalBinding</span><span class="sxs-lookup"><span data-stu-id="11be9-146">PositionalBinding</span></span>

<span data-ttu-id="11be9-147">Аргумент **поситионалбиндинг** определяет, являются ли параметры в функции позиционированными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11be9-147">The **PositionalBinding** argument determines whether parameters in the function are positional by default.</span></span> <span data-ttu-id="11be9-148">Значение по умолчанию — `$True`.</span><span class="sxs-lookup"><span data-stu-id="11be9-148">The default value is `$True`.</span></span> <span data-ttu-id="11be9-149">**PositionalBinding** `$False` Для отключения позиционированной привязки можно использовать аргумент поситионалбиндинг со значением.</span><span class="sxs-lookup"><span data-stu-id="11be9-149">You can use the **PositionalBinding** argument with a value of `$False` to disable positional binding.</span></span>

<span data-ttu-id="11be9-150">Аргумент **поситионалбиндинг** появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="11be9-150">The **PositionalBinding** argument is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="11be9-151">Если параметры являются позиционированными, имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="11be9-151">When parameters are positional, the parameter name is optional.</span></span>
<span data-ttu-id="11be9-152">PowerShell связывает безымянные значения параметров с параметрами функции в соответствии с порядком или позицией неименованных значений параметров в команде Function.</span><span class="sxs-lookup"><span data-stu-id="11be9-152">PowerShell associates unnamed parameter values with the function parameters according to the order or position of the unnamed parameter values in the function command.</span></span>

<span data-ttu-id="11be9-153">Если параметры не являются позиционированными (они называются "именованными"), в команде требуется имя параметра (или аббревиатура или псевдоним имени).</span><span class="sxs-lookup"><span data-stu-id="11be9-153">When parameters are not positional (they are "named"), the parameter name (or an abbreviation or alias of the name) is required in the command.</span></span>

<span data-ttu-id="11be9-154">Если **поситионалбиндинг** имеет значение `$True` , параметры функции по умолчанию являются позиционированными.</span><span class="sxs-lookup"><span data-stu-id="11be9-154">When **PositionalBinding** is `$True`, function parameters are positional by default.</span></span> <span data-ttu-id="11be9-155">PowerShell присваивает номера позиций параметрам в том порядке, в котором они объявляются в функции.</span><span class="sxs-lookup"><span data-stu-id="11be9-155">PowerShell assigns position number to the parameters in the order in which they are declared in the function.</span></span>

<span data-ttu-id="11be9-156">Если **поситионалбиндинг** имеет значение `$False` , параметры функции по умолчанию не являются позиционированными.</span><span class="sxs-lookup"><span data-stu-id="11be9-156">When **PositionalBinding** is `$False`, function parameters are not positional by default.</span></span> <span data-ttu-id="11be9-157">Если в параметре не **объявлен аргумент-** **параметр** , то имя параметра (или псевдоним или аббревиатура) должно быть включено при использовании параметра в функции.</span><span class="sxs-lookup"><span data-stu-id="11be9-157">Unless the **Position** argument of the **Parameter** attribute is declared on the parameter, the parameter name (or an alias or abbreviation) must be included when the parameter is used in a function.</span></span>

<span data-ttu-id="11be9-158">Аргумент **расположения** атрибута **Parameter** имеет приоритет над значением по умолчанию **поситионалбиндинг** .</span><span class="sxs-lookup"><span data-stu-id="11be9-158">The **Position** argument of the **Parameter** attribute takes precedence over the **PositionalBinding** default value.</span></span> <span data-ttu-id="11be9-159">Аргумент « **позиционирование** » можно использовать для указания значения параметра «значение».</span><span class="sxs-lookup"><span data-stu-id="11be9-159">You can use the **Position** argument to specify a position value for a parameter.</span></span> <span data-ttu-id="11be9-160">Дополнительные сведения о аргументе " **Расположение** " см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="11be9-160">For more information about the **Position** argument, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="notes"></a><span data-ttu-id="11be9-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="11be9-161">Notes</span></span>

<span data-ttu-id="11be9-162">Аргумент **SupportsTransactions** не поддерживается в расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="11be9-162">The **SupportsTransactions** argument is not supported in advanced functions.</span></span>

## <a name="keywords"></a><span data-ttu-id="11be9-163">Keywords</span><span class="sxs-lookup"><span data-stu-id="11be9-163">Keywords</span></span>

<span data-ttu-id="11be9-164">about_Functions_CmdletBinding_Attribute</span><span class="sxs-lookup"><span data-stu-id="11be9-164">about_Functions_CmdletBinding_Attribute</span></span>

## <a name="see-also"></a><span data-ttu-id="11be9-165">См. также статью</span><span class="sxs-lookup"><span data-stu-id="11be9-165">See also</span></span>

[<span data-ttu-id="11be9-166">about_Functions</span><span class="sxs-lookup"><span data-stu-id="11be9-166">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="11be9-167">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="11be9-167">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="11be9-168">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="11be9-168">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="11be9-169">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="11be9-169">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="11be9-170">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="11be9-170">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

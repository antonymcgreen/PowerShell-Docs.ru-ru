---
description: Описывает, как функции, указывающие `CmdletBinding` атрибут, могут использовать методы и свойства, доступные для скомпилированных командлетов.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 260dab1937715da34b9191ff2765dee7d2ac3ec5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232414"
---
# <a name="about-functions-advanced-methods"></a><span data-ttu-id="e84ec-104">О функциях дополнительные методы</span><span class="sxs-lookup"><span data-stu-id="e84ec-104">About Functions Advanced Methods</span></span>

## <a name="short-description"></a><span data-ttu-id="e84ec-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="e84ec-105">Short description</span></span>

<span data-ttu-id="e84ec-106">Описывает, как функции, указывающие `CmdletBinding` атрибут, могут использовать методы и свойства, доступные для скомпилированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="e84ec-106">Describes how functions that specify the `CmdletBinding` attribute can use the methods and properties that are available to compiled cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="e84ec-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e84ec-107">Long description</span></span>

<span data-ttu-id="e84ec-108">Функции, которые задают `CmdletBinding` атрибут, могут обращаться к ряду методов и свойств через `$PSCmdlet` переменную.</span><span class="sxs-lookup"><span data-stu-id="e84ec-108">Functions that specify the `CmdletBinding` attribute can access a number of methods and properties through the `$PSCmdlet` variable.</span></span> <span data-ttu-id="e84ec-109">К этим методам относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="e84ec-109">These methods include the following methods:</span></span>

- <span data-ttu-id="e84ec-110">Методы обработки ввода, которые скомпилированные командлеты используют для выполнения своей работы.</span><span class="sxs-lookup"><span data-stu-id="e84ec-110">Input-processing methods that compiled cmdlets use to do their work.</span></span>
- <span data-ttu-id="e84ec-111">`ShouldProcess`Методы и `ShouldContinue` , используемые для получения отзывов пользователей перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="e84ec-111">The `ShouldProcess` and `ShouldContinue` methods that are used to get user feedback before an action is performed.</span></span>
- <span data-ttu-id="e84ec-112">`ThrowTerminatingError`Метод создания записей об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e84ec-112">The `ThrowTerminatingError` method for generating error records.</span></span>
- <span data-ttu-id="e84ec-113">Несколько `Write` методов, возвращающих различные типы выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e84ec-113">Several `Write` methods that return different types of output.</span></span>

<span data-ttu-id="e84ec-114">Все методы и свойства класса **PSCmdlet** доступны для расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="e84ec-114">All the methods and properties of the **PSCmdlet** class are available to advanced functions.</span></span> <span data-ttu-id="e84ec-115">Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="e84ec-115">For more information, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="e84ec-116">Дополнительные сведения об `CmdletBinding` атрибуте см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="e84ec-116">For more information about the `CmdletBinding` attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>
<span data-ttu-id="e84ec-117">Сведения о классе **кмдлетбиндингаттрибуте** см. в разделе [System. Management. Automation. командлет. кмдлетбиндингаттрибуте](/dotnet/api/system.management.automation.cmdletbindingattribute).</span><span class="sxs-lookup"><span data-stu-id="e84ec-117">For the **CmdletBindingAttribute** class, see [System.Management.Automation.Cmdlet.CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span></span>

### <a name="input-processing-methods"></a><span data-ttu-id="e84ec-118">Методы обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="e84ec-118">Input processing methods</span></span>

<span data-ttu-id="e84ec-119">Методы, описанные в этом разделе, называются методами обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="e84ec-119">The methods described in this section are referred to as the input processing methods.</span></span> <span data-ttu-id="e84ec-120">Для функций эти три метода представлены `Begin` `Process` `End` блоками, и функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-120">For functions, these three methods are represented by the `Begin`, `Process`, and `End` blocks of the function.</span></span> <span data-ttu-id="e84ec-121">В функциях не обязательно использовать ни один из этих блоков.</span><span class="sxs-lookup"><span data-stu-id="e84ec-121">You aren't required to use any of these blocks in your functions.</span></span>

> [!NOTE]
> <span data-ttu-id="e84ec-122">Эти блоки также доступны для функций, которые не используют `CmdletBinding` атрибут.</span><span class="sxs-lookup"><span data-stu-id="e84ec-122">These blocks are also available to functions that don't use the `CmdletBinding` attribute.</span></span>

#### <a name="begin"></a><span data-ttu-id="e84ec-123">Начать</span><span class="sxs-lookup"><span data-stu-id="e84ec-123">Begin</span></span>

<span data-ttu-id="e84ec-124">Этот блок используется для предоставления необязательной одноразовой предварительной обработки для функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-124">This block is used to provide optional one-time preprocessing for the function.</span></span>
<span data-ttu-id="e84ec-125">Среда выполнения PowerShell использует код в этом блоке один раз для каждого экземпляра функции в конвейере.</span><span class="sxs-lookup"><span data-stu-id="e84ec-125">The PowerShell runtime uses the code in this block once for each instance of the function in the pipeline.</span></span>

#### <a name="process"></a><span data-ttu-id="e84ec-126">Процесс</span><span class="sxs-lookup"><span data-stu-id="e84ec-126">Process</span></span>

<span data-ttu-id="e84ec-127">Этот блок используется для обеспечения обработки записей по записям для функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-127">This block is used to provide record-by-record processing for the function.</span></span> <span data-ttu-id="e84ec-128">Блок можно использовать `Process` без определения других блоков.</span><span class="sxs-lookup"><span data-stu-id="e84ec-128">You can use a `Process` block without defining the other blocks.</span></span> <span data-ttu-id="e84ec-129">Количество `Process` выполнений блоков зависит от того, как используется функция и какие входные данные получает функция.</span><span class="sxs-lookup"><span data-stu-id="e84ec-129">The number of `Process` block executions depends on how you use the function and what input the function receives.</span></span>

<span data-ttu-id="e84ec-130">Автоматическая переменная `$_` или `$PSItem` содержит текущий объект в конвейере для использования в `Process` блоке.</span><span class="sxs-lookup"><span data-stu-id="e84ec-130">The automatic variable `$_` or `$PSItem` contains the current object in the pipeline for use in the `Process` block.</span></span> <span data-ttu-id="e84ec-131">`$input`Автоматическая переменная содержит перечислитель, доступный только для функций и блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="e84ec-131">The `$input` automatic variable contains an enumerator that's only available to functions and script blocks.</span></span>
<span data-ttu-id="e84ec-132">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e84ec-132">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="e84ec-133">Вызов функции в начале или за пределами конвейера выполняет `Process` блок один раз.</span><span class="sxs-lookup"><span data-stu-id="e84ec-133">Calling the function at the beginning, or outside of a pipeline, executes the `Process` block once.</span></span>
- <span data-ttu-id="e84ec-134">В конвейере `Process` блок выполняется один раз для каждого входного объекта, который достигает функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-134">Within a pipeline, the `Process` block executes once for each input object that reaches the function.</span></span>
- <span data-ttu-id="e84ec-135">Если входные данные конвейера, которые достигают функции, пусты, `Process` блок **не** выполняется.</span><span class="sxs-lookup"><span data-stu-id="e84ec-135">If the pipeline input that reaches the function is empty, the `Process` block **does not** execute.</span></span>
  - <span data-ttu-id="e84ec-136">`Begin`Блоки и `End` по-прежнему выполняются.</span><span class="sxs-lookup"><span data-stu-id="e84ec-136">The `Begin` and `End` blocks still execute.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e84ec-137">Если параметр функции принимает входные данные конвейера, а `Process` блок не определен, обработка записи по записям завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e84ec-137">If a function parameter is set to accept pipeline input, and a `Process` block isn't defined, record-by-record processing will fail.</span></span> <span data-ttu-id="e84ec-138">В этом случае функция будет выполняться только один раз, независимо от входных данных.</span><span class="sxs-lookup"><span data-stu-id="e84ec-138">In this case, your function will only execute once, regardless of the input.</span></span>

#### <a name="end"></a><span data-ttu-id="e84ec-139">Конец</span><span class="sxs-lookup"><span data-stu-id="e84ec-139">End</span></span>

<span data-ttu-id="e84ec-140">Этот блок используется для предоставления функции необязательной однократной последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="e84ec-140">This block is used to provide optional one-time post-processing for the function.</span></span>

<span data-ttu-id="e84ec-141">В следующем примере показана структура функции, которая содержит `Begin` блок для одноразовой предварительной обработки, `Process` блок для обработки нескольких записей и `End` блок для однократной последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="e84ec-141">The following example shows the outline of a function that contains a `Begin` block for one-time preprocessing, a `Process` block for multiple record processing, and an `End` block for one-time post-processing.</span></span>

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> <span data-ttu-id="e84ec-142">Для использования `Begin` блока или необходимо `End` определить все три блока.</span><span class="sxs-lookup"><span data-stu-id="e84ec-142">Using either a `Begin` or `End` block requires that you define all three blocks.</span></span> <span data-ttu-id="e84ec-143">При использовании всех трех блоков весь код PowerShell должен находиться внутри одного из блоков.</span><span class="sxs-lookup"><span data-stu-id="e84ec-143">When using all three blocks, all PowerShell code must be inside one of the blocks.</span></span>

### <a name="confirmation-methods"></a><span data-ttu-id="e84ec-144">Методы подтверждения</span><span class="sxs-lookup"><span data-stu-id="e84ec-144">Confirmation methods</span></span>

#### <a name="shouldprocess"></a><span data-ttu-id="e84ec-145">ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="e84ec-145">ShouldProcess</span></span>

<span data-ttu-id="e84ec-146">Этот метод вызывается для запроса подтверждения от пользователя до того, как функция выполняет действие, которое привело бы к изменению системы.</span><span class="sxs-lookup"><span data-stu-id="e84ec-146">This method is called to request confirmation from the user before the function performs an action that would change the system.</span></span> <span data-ttu-id="e84ec-147">Функция может продолжаться на основе логического значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="e84ec-147">The function can continue based on the Boolean value returned by the method.</span></span> <span data-ttu-id="e84ec-148">Этот метод может быть вызван только внутри `Process{}` блока функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-148">This method can only be called only from within the `Process{}` block of the function.</span></span> <span data-ttu-id="e84ec-149">`CmdletBinding`Атрибут также должен объявлять, что функция поддерживает `ShouldProcess` (как показано в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="e84ec-149">The `CmdletBinding` attribute must also declare that the function supports `ShouldProcess` (as shown in the previous example).</span></span>

<span data-ttu-id="e84ec-150">Дополнительные сведения об этом методе см. в разделе [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span><span class="sxs-lookup"><span data-stu-id="e84ec-150">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span></span>

<span data-ttu-id="e84ec-151">Дополнительные сведения о запросе подтверждения см. в разделе [запрос подтверждения](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="e84ec-151">For more information about how to request confirmation, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

#### <a name="shouldcontinue"></a><span data-ttu-id="e84ec-152">ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="e84ec-152">ShouldContinue</span></span>

<span data-ttu-id="e84ec-153">Этот метод вызывается для запроса второго сообщения с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="e84ec-153">This method is called to request a second confirmation message.</span></span> <span data-ttu-id="e84ec-154">Он должен вызываться, когда `ShouldProcess` метод возвращает значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="e84ec-154">It should be called when the `ShouldProcess` method returns `$true`.</span></span> <span data-ttu-id="e84ec-155">Дополнительные сведения об этом методе см. в разделе [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span><span class="sxs-lookup"><span data-stu-id="e84ec-155">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span></span>

### <a name="error-methods"></a><span data-ttu-id="e84ec-156">Методы ошибок</span><span class="sxs-lookup"><span data-stu-id="e84ec-156">Error methods</span></span>

<span data-ttu-id="e84ec-157">Функции могут вызывать два разных метода при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="e84ec-157">Functions can call two different methods when errors occur.</span></span> <span data-ttu-id="e84ec-158">При возникновении неустранимой ошибки функция должна вызвать `WriteError` метод, который описан в `Write` разделе методы.</span><span class="sxs-lookup"><span data-stu-id="e84ec-158">When a non-terminating error occurs, the function should call the `WriteError` method, which is described in the `Write` methods section.</span></span> <span data-ttu-id="e84ec-159">Когда возникает завершающая ошибка и функция не может продолжить работу, она должна вызвать `ThrowTerminatingError` метод.</span><span class="sxs-lookup"><span data-stu-id="e84ec-159">When a terminating error occurs and the function can't continue, it should call the `ThrowTerminatingError` method.</span></span> <span data-ttu-id="e84ec-160">Можно также использовать `Throw` инструкцию для завершения ошибок и командлет [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) для устранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="e84ec-160">You can also use the `Throw` statement for terminating errors and the [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) cmdlet for non-terminating errors.</span></span>

<span data-ttu-id="e84ec-161">Дополнительные сведения см. в разделе [System. Management. Automation. командлет. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span><span class="sxs-lookup"><span data-stu-id="e84ec-161">For more information, see [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span></span>

### <a name="write-methods"></a><span data-ttu-id="e84ec-162">Методы записи</span><span class="sxs-lookup"><span data-stu-id="e84ec-162">Write methods</span></span>

<span data-ttu-id="e84ec-163">Функция может вызывать следующие методы для возврата различных типов выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e84ec-163">A function can call the following methods to return different types of output.</span></span>
<span data-ttu-id="e84ec-164">Обратите внимание, что не все выходные данные переходят к следующей команде в конвейере.</span><span class="sxs-lookup"><span data-stu-id="e84ec-164">Notice that not all the output goes to the next command in the pipeline.</span></span> <span data-ttu-id="e84ec-165">Можно также использовать различные `Write` командлеты, например `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="e84ec-165">You can also use the various `Write` cmdlets, such as `Write-Error`.</span></span>

#### <a name="writecommanddetail"></a><span data-ttu-id="e84ec-166">вритекомманддетаил</span><span class="sxs-lookup"><span data-stu-id="e84ec-166">WriteCommandDetail</span></span>

<span data-ttu-id="e84ec-167">Дополнительные сведения о `WriteCommandDetails` методе см. в разделе [System. Management. Automation. командлет. вритекомманддетаил](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span><span class="sxs-lookup"><span data-stu-id="e84ec-167">For information about the `WriteCommandDetails` method, see [System.Management.Automation.Cmdlet.WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span></span>

#### <a name="writedebug"></a><span data-ttu-id="e84ec-168">вритедебуг</span><span class="sxs-lookup"><span data-stu-id="e84ec-168">WriteDebug</span></span>

<span data-ttu-id="e84ec-169">Чтобы предоставить сведения, которые можно использовать для устранения неполадок функции, сделайте ее вызовом `WriteDebug` метода.</span><span class="sxs-lookup"><span data-stu-id="e84ec-169">To provide information that can be used to troubleshoot a function, make the function call the `WriteDebug` method.</span></span> <span data-ttu-id="e84ec-170">`WriteDebug`Метод отображает сообщения отладки для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e84ec-170">The `WriteDebug` method displays debug messages to the user.</span></span> <span data-ttu-id="e84ec-171">Дополнительные сведения см. в разделе [System. Management. Automation. командлет. вритедебуг](/dotnet/api/system.management.automation.cmdlet.writedebug).</span><span class="sxs-lookup"><span data-stu-id="e84ec-171">For more information, see [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span></span>

#### <a name="writeerror"></a><span data-ttu-id="e84ec-172">WriteError</span><span class="sxs-lookup"><span data-stu-id="e84ec-172">WriteError</span></span>

<span data-ttu-id="e84ec-173">Функции должны вызывать этот метод при возникновении устранимых ошибок, а функция предназначена для продолжения обработки записей.</span><span class="sxs-lookup"><span data-stu-id="e84ec-173">Functions should call this method when non-terminating errors occur and the function is designed to continue processing records.</span></span> <span data-ttu-id="e84ec-174">Дополнительные сведения см. в разделе [System. Management. Automation. командлет. WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span><span class="sxs-lookup"><span data-stu-id="e84ec-174">For more information, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span></span>

> [!NOTE]
> <span data-ttu-id="e84ec-175">При возникновении завершающей ошибки функция должна вызвать метод [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) .</span><span class="sxs-lookup"><span data-stu-id="e84ec-175">If a terminating error occurs, the function should call the [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) method.</span></span>

#### <a name="writeobject"></a><span data-ttu-id="e84ec-176">WriteObject</span><span class="sxs-lookup"><span data-stu-id="e84ec-176">WriteObject</span></span>

<span data-ttu-id="e84ec-177">`WriteObject`Метод позволяет функции отправить объект в следующую команду в конвейере.</span><span class="sxs-lookup"><span data-stu-id="e84ec-177">The `WriteObject` method allows the function to send an object to the next command in the pipeline.</span></span> <span data-ttu-id="e84ec-178">В большинстве случаев `WriteObject` метод используется, когда функция возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="e84ec-178">In most cases, `WriteObject` is the method to use when the function returns data.</span></span> <span data-ttu-id="e84ec-179">Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span><span class="sxs-lookup"><span data-stu-id="e84ec-179">For more information, see [System.Management.Automation.PSCmdlet.WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span></span>

#### <a name="writeprogress"></a><span data-ttu-id="e84ec-180">вритепрогресс</span><span class="sxs-lookup"><span data-stu-id="e84ec-180">WriteProgress</span></span>

<span data-ttu-id="e84ec-181">Для функций с действиями, выполнение которых занимает много времени, этот метод позволяет функции вызвать `WriteProgress` метод, чтобы отображались сведения о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e84ec-181">For functions with actions that take a long time to complete, this method allows the function to call the `WriteProgress` method so that progress information is displayed.</span></span> <span data-ttu-id="e84ec-182">Например, можно отобразить процент завершенных.</span><span class="sxs-lookup"><span data-stu-id="e84ec-182">For example, you can display the percent completed.</span></span>
<span data-ttu-id="e84ec-183">Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритепрогресс](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span><span class="sxs-lookup"><span data-stu-id="e84ec-183">For more information, see [System.Management.Automation.PSCmdlet.WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span></span>

#### <a name="writeverbose"></a><span data-ttu-id="e84ec-184">вритевербосе</span><span class="sxs-lookup"><span data-stu-id="e84ec-184">WriteVerbose</span></span>

<span data-ttu-id="e84ec-185">Чтобы получить подробные сведения о том, что делает функция, вызовите `WriteVerbose` метод, чтобы отобразить подробные сообщения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e84ec-185">To provide detailed information about what the function is doing, make the function call the `WriteVerbose` method to display verbose messages to the user.</span></span> <span data-ttu-id="e84ec-186">По умолчанию подробные сообщения не отображаются.</span><span class="sxs-lookup"><span data-stu-id="e84ec-186">By default, verbose messages aren't displayed.</span></span> <span data-ttu-id="e84ec-187">Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритевербосе](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span><span class="sxs-lookup"><span data-stu-id="e84ec-187">For more information, see [System.Management.Automation.PSCmdlet.WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span></span>

#### <a name="writewarning"></a><span data-ttu-id="e84ec-188">вритеварнинг</span><span class="sxs-lookup"><span data-stu-id="e84ec-188">WriteWarning</span></span>

<span data-ttu-id="e84ec-189">Чтобы предоставить сведения об условиях, которые могут привести к непредвиденным результатам, сделайте функцию вызовом метода Вритеварнинг, чтобы отобразить предупреждающие сообщения пользователю.</span><span class="sxs-lookup"><span data-stu-id="e84ec-189">To provide information about conditions that may cause unexpected results, make the function call the WriteWarning method to display warning messages to the user.</span></span> <span data-ttu-id="e84ec-190">По умолчанию отображаются предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="e84ec-190">By default, warning messages are displayed.</span></span> <span data-ttu-id="e84ec-191">Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритеварнинг](/dotnet/api/system.management.automation.cmdlet.writewarning).</span><span class="sxs-lookup"><span data-stu-id="e84ec-191">For more information, see [System.Management.Automation.PSCmdlet.WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span></span>

> [!NOTE]
> <span data-ttu-id="e84ec-192">Можно также отобразить предупреждающие сообщения, настроив `$WarningPreference` переменную или используя `Verbose` `Debug` Параметры командной строки и.</span><span class="sxs-lookup"><span data-stu-id="e84ec-192">You can also display warning messages by configuring the `$WarningPreference` variable or by using the `Verbose` and `Debug` command-line options.</span></span> <span data-ttu-id="e84ec-193">Дополнительные сведения о `$WarningPreference` переменной см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e84ec-193">for more information about the `$WarningPreference` variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="other-methods-and-properties"></a><span data-ttu-id="e84ec-194">Другие методы и свойства</span><span class="sxs-lookup"><span data-stu-id="e84ec-194">Other methods and properties</span></span>

<span data-ttu-id="e84ec-195">Дополнительные сведения о других методах и свойствах, к которым можно получить доступ через `$PSCmdlet` переменную, см. в разделе [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="e84ec-195">For information about the other methods and properties that can be accessed through the `$PSCmdlet` variable, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="e84ec-196">Например, свойство [параметерсетнаме](/dotnet/api/system.management.automation.pscmdlet.parametersetname) позволяет увидеть используемый набор параметров.</span><span class="sxs-lookup"><span data-stu-id="e84ec-196">For example, the [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) property allows you to see the parameter set that is being used.</span></span> <span data-ttu-id="e84ec-197">Наборы параметров позволяют создавать функции, выполняющие различные задачи на основе параметров, указанных при выполнении функции.</span><span class="sxs-lookup"><span data-stu-id="e84ec-197">Parameter sets allow you to create a function that performs different tasks based on the parameters that are specified when the function is run.</span></span>

## <a name="see-also"></a><span data-ttu-id="e84ec-198">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e84ec-198">See also</span></span>

[<span data-ttu-id="e84ec-199">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e84ec-199">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="e84ec-200">about_Functions</span><span class="sxs-lookup"><span data-stu-id="e84ec-200">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="e84ec-201">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="e84ec-201">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="e84ec-202">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="e84ec-202">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="e84ec-203">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="e84ec-203">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="e84ec-204">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="e84ec-204">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="e84ec-205">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="e84ec-205">about_Preference_Variables</span></span>](about_Preference_Variables.md)

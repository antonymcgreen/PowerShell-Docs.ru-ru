---
description: Описание работы с параметрами команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: 7cc5c071116df8d3326a4ea13802227d350bfac3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232354"
---
# <a name="about-parameters"></a><span data-ttu-id="e67eb-104">О параметрах</span><span class="sxs-lookup"><span data-stu-id="e67eb-104">About Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="e67eb-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="e67eb-105">Short description</span></span>
<span data-ttu-id="e67eb-106">Описание работы с параметрами команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e67eb-106">Describes how to work with command parameters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e67eb-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e67eb-107">Long description</span></span>

<span data-ttu-id="e67eb-108">Большинство команд PowerShell, таких как командлеты, функции и скрипты, зависят от параметров, позволяющих пользователям выбирать параметры или предоставлять входные данные.</span><span class="sxs-lookup"><span data-stu-id="e67eb-108">Most PowerShell commands, such as cmdlets, functions, and scripts, rely on parameters to allow users to select options or provide input.</span></span> <span data-ttu-id="e67eb-109">Параметры соответствуют имени команды и имеют следующую форму:</span><span class="sxs-lookup"><span data-stu-id="e67eb-109">The parameters follow the command name and have the following form:</span></span>

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

<span data-ttu-id="e67eb-110">Имени параметра предшествует дефис (-), который сообщает PowerShell, что слово, следующее за дефисом, является именем параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-110">The name of the parameter is preceded by a hyphen (-), which signals to PowerShell that the word following the hyphen is a parameter name.</span></span> <span data-ttu-id="e67eb-111">Имя и значение параметра могут разделяться пробелами или символами двоеточия.</span><span class="sxs-lookup"><span data-stu-id="e67eb-111">The parameter name and value can be separated by a space or a colon character.</span></span> <span data-ttu-id="e67eb-112">Некоторые параметры не занимают и не принимают значение параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-112">Some parameters do not require or accept a parameter value.</span></span> <span data-ttu-id="e67eb-113">Другим параметрам требуется значение, но не требуется имя параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="e67eb-113">Other parameters require a value, but do not require the parameter name in the command.</span></span>

<span data-ttu-id="e67eb-114">Тип параметров и требования к этим параметрам различаются.</span><span class="sxs-lookup"><span data-stu-id="e67eb-114">The type of parameters and the requirements for those parameters vary.</span></span> <span data-ttu-id="e67eb-115">Чтобы найти сведения о параметрах команды, используйте `Get-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="e67eb-115">To find information about the parameters of a command, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="e67eb-116">Например, чтобы найти сведения о параметрах `Get-ChildItem` командлета, введите:</span><span class="sxs-lookup"><span data-stu-id="e67eb-116">For example, to find information about the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="e67eb-117">Чтобы найти сведения о параметрах скрипта, используйте полный путь к файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="e67eb-117">To find information about the parameters of a script, use the full path to the script file.</span></span> <span data-ttu-id="e67eb-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="e67eb-118">For example:</span></span>

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

<span data-ttu-id="e67eb-119">`Get-Help`Командлет возвращает различные сведения о команде, включая описание, синтаксис команды, сведения о параметрах и примеры, демонстрирующие использование параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="e67eb-119">The `Get-Help` cmdlet returns various details about the command, including a description, the command syntax, information about the parameters, and examples showing how to use the parameters in a command.</span></span>

<span data-ttu-id="e67eb-120">Можно также использовать параметр параметра `Get-Help` командлета для поиска сведений о конкретном параметре.</span><span class="sxs-lookup"><span data-stu-id="e67eb-120">You can also use the Parameter parameter of the `Get-Help` cmdlet to find information about a particular parameter.</span></span> <span data-ttu-id="e67eb-121">Также можно использовать параметр **Parameter** с подстановочным знаком ( `*` ), чтобы найти сведения обо всех параметрах команды.</span><span class="sxs-lookup"><span data-stu-id="e67eb-121">Or, you can use the **Parameter** parameter with the wildcard character ( `*` ) value to find information about all parameters of the command.</span></span> <span data-ttu-id="e67eb-122">Например, следующая команда получает сведения обо всех параметрах `Get-Member` командлета:</span><span class="sxs-lookup"><span data-stu-id="e67eb-122">For example, the following command gets information about all parameters of the `Get-Member` cmdlet:</span></span>

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a><span data-ttu-id="e67eb-123">Значения параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e67eb-123">Default parameter values</span></span>

<span data-ttu-id="e67eb-124">Необязательные параметры имеют значение по умолчанию, которое является значением, которое используется или предполагается, если параметр не указан в команде.</span><span class="sxs-lookup"><span data-stu-id="e67eb-124">Optional parameters have a default value, which is the value that is used or assumed when the parameter is not specified in the command.</span></span>

<span data-ttu-id="e67eb-125">Например, значение по умолчанию параметра **ComputerName** во многих командлетах — это имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="e67eb-125">For example, the default value of the **ComputerName** parameter of many cmdlets is the name of the local computer.</span></span> <span data-ttu-id="e67eb-126">В результате в команде используется имя локального компьютера, если не указан параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="e67eb-126">As a result, the local computer name is used in the command unless the **ComputerName** parameter is specified.</span></span>

<span data-ttu-id="e67eb-127">Чтобы найти значение параметра по умолчанию, см. раздел справки для командлета.</span><span class="sxs-lookup"><span data-stu-id="e67eb-127">To find the default parameter value, see help topic for the cmdlet.</span></span> <span data-ttu-id="e67eb-128">Описание параметра должно включать значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e67eb-128">The parameter description should include the default value.</span></span>

<span data-ttu-id="e67eb-129">Можно также задать пользовательское значение по умолчанию для любого параметра командлета или расширенной функции.</span><span class="sxs-lookup"><span data-stu-id="e67eb-129">You can also set a custom default value for any parameter of a cmdlet or advanced function.</span></span> <span data-ttu-id="e67eb-130">Дополнительные сведения о настройке пользовательских значений по умолчанию см. в разделе [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="e67eb-130">For information about setting custom default values, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="e67eb-131">Таблица атрибутов параметра</span><span class="sxs-lookup"><span data-stu-id="e67eb-131">Parameter attribute table</span></span>

<span data-ttu-id="e67eb-132">При использовании **полных** параметров, **параметров** или **сетевого** параметра `Get-Help` командлета `Get-Help` отображает таблицу атрибутов параметров с подробными сведениями о параметре.</span><span class="sxs-lookup"><span data-stu-id="e67eb-132">When you use the **Full** , **Parameter** , or **Online** parameters of the `Get-Help` cmdlet, `Get-Help` displays a parameter attribute table with detailed information about the parameter.</span></span>

<span data-ttu-id="e67eb-133">Эти сведения включают сведения, необходимые для использования параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-133">This information includes the details you need to know to use the parameter.</span></span>
<span data-ttu-id="e67eb-134">Например, раздел справки для `Get-ChildItem` командлета содержит следующие сведения о параметре пути:</span><span class="sxs-lookup"><span data-stu-id="e67eb-134">For example, the help topic for the `Get-ChildItem` cmdlet includes the following details about its Path parameter:</span></span>

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

<span data-ttu-id="e67eb-135">Сведения о параметрах включают в себя синтаксис параметров, описание параметра и атрибуты параметров.</span><span class="sxs-lookup"><span data-stu-id="e67eb-135">The parameter information includes the parameter syntax, a description of the parameter, and the parameter attributes.</span></span> <span data-ttu-id="e67eb-136">В следующих разделах описываются атрибуты параметров.</span><span class="sxs-lookup"><span data-stu-id="e67eb-136">The following sections describe the parameter attributes.</span></span>

#### <a name="parameter-required"></a><span data-ttu-id="e67eb-137">Требуется параметр</span><span class="sxs-lookup"><span data-stu-id="e67eb-137">Parameter Required</span></span>

<span data-ttu-id="e67eb-138">Этот параметр указывает, является ли параметр обязательным, то есть должны ли все команды, использующие этот командлет, включать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="e67eb-138">This setting indicates whether the parameter is mandatory, that is, whether all commands that use this cmdlet must include this parameter.</span></span> <span data-ttu-id="e67eb-139">Если значение равно **true** и в команде отсутствует параметр, PowerShell запрашивает значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-139">When the value is **True** and the parameter is missing from the command, PowerShell prompts you for a value for the parameter.</span></span>

#### <a name="parameter-position"></a><span data-ttu-id="e67eb-140">Расположение параметра</span><span class="sxs-lookup"><span data-stu-id="e67eb-140">Parameter Position</span></span>

<span data-ttu-id="e67eb-141">Если `Position` для параметра задано положительное целое число, имя параметра не требуется.</span><span class="sxs-lookup"><span data-stu-id="e67eb-141">If the `Position` setting is set to a positive integer, the parameter name is not required.</span></span> <span data-ttu-id="e67eb-142">Этот тип параметра называется параметром позиционирования, а число указывает на расположение, в котором параметр должен располагаться относительно других параметров позиционирования.</span><span class="sxs-lookup"><span data-stu-id="e67eb-142">This type of parameter is referred to as a positional parameter, and the number indicates the position in which the parameter must appear in relation to other positional parameters.</span></span> <span data-ttu-id="e67eb-143">Именованный параметр может быть указан в любом месте после имени командлета.</span><span class="sxs-lookup"><span data-stu-id="e67eb-143">A named parameter can be listed in any position after the cmdlet name.</span></span> <span data-ttu-id="e67eb-144">Если вы включили имя параметра для позиционированного параметра, то параметр может быть указан в любом месте после имени командлета.</span><span class="sxs-lookup"><span data-stu-id="e67eb-144">If you include the parameter name for a positional parameter, the parameter can be listed in any position after the cmdlet name.</span></span>

<span data-ttu-id="e67eb-145">Например, `Get-ChildItem` командлет содержит параметры Path и Exclude.</span><span class="sxs-lookup"><span data-stu-id="e67eb-145">For example, the `Get-ChildItem` cmdlet has Path and Exclude parameters.</span></span> <span data-ttu-id="e67eb-146">`Position`Параметр **path** имеет значение **0** , что означает, что он является позиционированным параметром.</span><span class="sxs-lookup"><span data-stu-id="e67eb-146">The `Position` setting for **Path** is **0** , which means that it is a positional parameter.</span></span> <span data-ttu-id="e67eb-147">`Position`Параметр **Exclude** имеет **имя**.</span><span class="sxs-lookup"><span data-stu-id="e67eb-147">The `Position` setting for **Exclude** is **named**.</span></span>

<span data-ttu-id="e67eb-148">Это означает, что **путь** не требует имени параметра, но его значение должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="e67eb-148">This means that **Path** does not require the parameter name, but its parameter value must be the first or only unnamed parameter value in the command.</span></span>
<span data-ttu-id="e67eb-149">Однако, поскольку параметр Exclude является именованным параметром, его можно поместить в любую позицию в команде.</span><span class="sxs-lookup"><span data-stu-id="e67eb-149">However, because the Exclude parameter is a named parameter, you can place it in any position in the command.</span></span>

<span data-ttu-id="e67eb-150">В результате `Position` настройки этих двух параметров можно использовать любую из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="e67eb-150">As a result of the `Position` settings for these two parameters, you can use any of the following commands:</span></span>

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

<span data-ttu-id="e67eb-151">Если бы вы включали другой параметр с указанием параметра, не указывая имя параметра, этот параметр должен быть помещен в порядок, заданный `Position` параметром.</span><span class="sxs-lookup"><span data-stu-id="e67eb-151">If you were to include another positional parameter without including the parameter name, that parameter must be placed in the order specified by the `Position` setting.</span></span>

#### <a name="parameter-type"></a><span data-ttu-id="e67eb-152">Тип параметра</span><span class="sxs-lookup"><span data-stu-id="e67eb-152">Parameter Type</span></span>

<span data-ttu-id="e67eb-153">Этот параметр указывает Microsoft .NET тип платформы для значения параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-153">This setting specifies the Microsoft .NET Framework type of the parameter value.</span></span> <span data-ttu-id="e67eb-154">Например, если тип — **Int32** , значение параметра должно быть целым числом.</span><span class="sxs-lookup"><span data-stu-id="e67eb-154">For example, if the type is **Int32** , the parameter value must be an integer.</span></span> <span data-ttu-id="e67eb-155">Если тип является строковым, значение параметра должно быть символьной строкой.</span><span class="sxs-lookup"><span data-stu-id="e67eb-155">If the type is string, the parameter value must be a character string.</span></span> <span data-ttu-id="e67eb-156">Если строка содержит пробелы, значение должно быть заключено в кавычки, либо перед пробелами должно стоять escape-символ (').</span><span class="sxs-lookup"><span data-stu-id="e67eb-156">If the string contains spaces, the value must be enclosed in quotation marks, or the spaces must be preceded by the escape character ( \` ).</span></span>

#### <a name="default-value"></a><span data-ttu-id="e67eb-157">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e67eb-157">Default Value</span></span>

<span data-ttu-id="e67eb-158">Этот параметр определяет значение, которое будет считаться параметром, если другое значение не указано.</span><span class="sxs-lookup"><span data-stu-id="e67eb-158">This setting specifies the value that the parameter will assume if no other value is provided.</span></span> <span data-ttu-id="e67eb-159">Например, значение параметра Path по умолчанию часто является текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="e67eb-159">For example, the default value of the Path parameter is often the current directory.</span></span> <span data-ttu-id="e67eb-160">Обязательные параметры никогда не имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e67eb-160">Required parameters never have a default value.</span></span>
<span data-ttu-id="e67eb-161">Для многих необязательных параметров значение по умолчанию отсутствует, так как параметр не действует, если он не используется.</span><span class="sxs-lookup"><span data-stu-id="e67eb-161">For many optional parameters, there is no default because the parameter has no effect if it is not used.</span></span>

#### <a name="accepts-multiple-values"></a><span data-ttu-id="e67eb-162">Принимает несколько значений</span><span class="sxs-lookup"><span data-stu-id="e67eb-162">Accepts Multiple Values</span></span>

<span data-ttu-id="e67eb-163">Этот параметр указывает, принимает ли параметр несколько значений параметров.</span><span class="sxs-lookup"><span data-stu-id="e67eb-163">This setting indicates whether a parameter accepts multiple parameter values.</span></span>
<span data-ttu-id="e67eb-164">Если параметр принимает несколько значений, можно ввести разделенный запятыми список в качестве значения параметра в команде или сохранить список с разделителями-запятыми (массив) в переменной, а затем указать переменную в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-164">When a parameter accepts multiple values, you can type a comma-separated list as the value of the parameter in the command, or save a comma-separated list (an array) in a variable, and then specify the variable as the parameter value.</span></span>

<span data-ttu-id="e67eb-165">Например, параметр ServiceName `Get-Service` командлета принимает несколько значений.</span><span class="sxs-lookup"><span data-stu-id="e67eb-165">For example, the ServiceName parameter of the `Get-Service` cmdlet accepts multiple values.</span></span> <span data-ttu-id="e67eb-166">Допустимы следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e67eb-166">The following commands are both valid:</span></span>

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a><span data-ttu-id="e67eb-167">Принимает входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="e67eb-167">Accepts Pipeline Input</span></span>

<span data-ttu-id="e67eb-168">Этот параметр указывает, можно ли использовать оператор конвейера ( `|` ) для отправки значения в параметр.</span><span class="sxs-lookup"><span data-stu-id="e67eb-168">This setting indicates whether you can use the pipeline operator ( `|` ) to send a value to the parameter.</span></span>

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

<span data-ttu-id="e67eb-169">Если параметр имеет значение true (по значению)), PowerShell пытается связать все переданные значения с этим параметром перед тем, как попытается обработать команду другими методами.</span><span class="sxs-lookup"><span data-stu-id="e67eb-169">When a parameter is "True (by Value)", PowerShell tries to associate any piped values with that parameter before it tries other methods to interpret the command.</span></span>

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

<span data-ttu-id="e67eb-170">Например, можно передать значение в параметр **Name** только в том случае, если у значения есть свойство с именем **Name**.</span><span class="sxs-lookup"><span data-stu-id="e67eb-170">For example, you can pipe a value to a **Name** parameter only when the value has a property called **Name**.</span></span>

> [!NOTE]
> <span data-ttu-id="e67eb-171">Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с **отложенной привязкой** для параметра.</span><span class="sxs-lookup"><span data-stu-id="e67eb-171">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
>
> <span data-ttu-id="e67eb-172">Блок скрипта **с отложенной привязкой** запускается автоматически во время **ParameterBinding оболочки**.</span><span class="sxs-lookup"><span data-stu-id="e67eb-172">The **delay-bind** script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="e67eb-173">Результат привязан к параметру.</span><span class="sxs-lookup"><span data-stu-id="e67eb-173">The result is bound to the parameter.</span></span> <span data-ttu-id="e67eb-174">Отложенная привязка **не** работает для параметров, определенных как `ScriptBlock` тип `System.Object` , или блок скрипта передается **без** вызова.</span><span class="sxs-lookup"><span data-stu-id="e67eb-174">Delay binding does **not** work for parameters defined as type `ScriptBlock` or `System.Object`, the script block is passed through **without** being invoked.</span></span>
>
> <span data-ttu-id="e67eb-175">Сведения о блоках скриптов **с отложенной привязкой** можно узнать здесь [about_Script_Blocks. md](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="e67eb-175">You can read about **delay-bind** script blocks here [about_Script_Blocks.md](about_Script_Blocks.md)</span></span>

#### <a name="accepts-wildcard-characters"></a><span data-ttu-id="e67eb-176">Принимает подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="e67eb-176">Accepts Wildcard Characters</span></span>

<span data-ttu-id="e67eb-177">Этот параметр указывает, может ли значение параметра содержать подстановочные знаки, чтобы значение параметра можно было сопоставить более чем с одним существующим элементом в целевом контейнере.</span><span class="sxs-lookup"><span data-stu-id="e67eb-177">This setting indicates whether the parameter's value can contain wildcard characters so that the parameter value can be matched to more than one existing item in the target container.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="e67eb-178">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e67eb-178">Common Parameters</span></span>

<span data-ttu-id="e67eb-179">Общие параметры — это параметры, которые можно использовать с любым командлетом.</span><span class="sxs-lookup"><span data-stu-id="e67eb-179">Common parameters are parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="e67eb-180">Дополнительные сведения об общих параметрах см. в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e67eb-180">For more information about common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e67eb-181">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e67eb-181">See also</span></span>

[<span data-ttu-id="e67eb-182">about_Command_syntax</span><span class="sxs-lookup"><span data-stu-id="e67eb-182">about_Command_syntax</span></span>](about_Command_syntax.md)

[<span data-ttu-id="e67eb-183">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="e67eb-183">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="e67eb-184">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="e67eb-184">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="e67eb-185">about_Parameters_Default_Values</span><span class="sxs-lookup"><span data-stu-id="e67eb-185">about_Parameters_Default_Values</span></span>](about_Parameters_Default_Values.md)

[<span data-ttu-id="e67eb-186">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="e67eb-186">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="e67eb-187">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="e67eb-187">about_Wildcards</span></span>](about_Wildcards.md)

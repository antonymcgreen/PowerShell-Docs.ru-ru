---
description: Объясняется, как добавлять параметры в расширенные функции.
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: da21f6fb7d19fa2ffcd9cd6c5eea217792937ae4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601477"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="9a5a4-103">О функциях дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="9a5a4-103">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="9a5a4-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="9a5a4-104">Short description</span></span>

<span data-ttu-id="9a5a4-105">Объясняется, как добавлять параметры в расширенные функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-105">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="9a5a4-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9a5a4-106">Long description</span></span>

<span data-ttu-id="9a5a4-107">Вы можете добавить параметры в расширенные функции, которые вы пишете, и использовать атрибуты и аргументы параметров для ограничения значений параметров, которые пользователи будут передавать с параметром.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-107">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="9a5a4-108">Параметры, добавляемые в функцию, доступны пользователям в дополнение к общим параметрам, которые PowerShell автоматически добавляет ко всем командлетам и расширенным функциям.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-108">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="9a5a4-109">Дополнительные сведения об общих параметрах PowerShell см. в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-109">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="9a5a4-110">Начиная с PowerShell 3,0 можно использовать Сплаттинг с `@Args` для представления параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-110">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="9a5a4-111">Сплаттинг является допустимым для простых и расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-111">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="9a5a4-112">Дополнительные сведения см. в разделе [about_Functions](about_Functions.md) и [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-112">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="9a5a4-113">Преобразование типов значений параметров</span><span class="sxs-lookup"><span data-stu-id="9a5a4-113">Type conversion of parameter values</span></span>

<span data-ttu-id="9a5a4-114">При предоставлении строк в качестве аргументов для параметров, которые предполагают другой тип, PowerShell неявно преобразует строки в целевой тип параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-114">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="9a5a4-115">Расширенные функции выполняют синтаксический анализ инвариантных значений параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-115">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="9a5a4-116">В отличие от этого, преобразование с учетом языка и региональных параметров выполняется во время привязки параметра для скомпилированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-116">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="9a5a4-117">В этом примере мы создадим командлет и функцию скрипта, которая принимает `[datetime]` параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-117">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="9a5a4-118">Текущий язык и региональные параметры изменены для использования параметров немецкого языка.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-118">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="9a5a4-119">Дата в немецком формате передается в параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-119">A German-formatted date is passed to the parameter.</span></span>

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

<span data-ttu-id="9a5a4-120">Как показано выше, командлеты используют синтаксический анализ с учетом языка и региональных параметров для преобразования строки.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-120">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

<span data-ttu-id="9a5a4-121">Дополнительные функции используют синтаксический анализ инвариантного языка и региональных параметров, что приводит к следующей ошибке.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-121">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func: Cannot process argument transformation on parameter 'Date'.
Cannot convert value "19-06-2018" to type "System.DateTime". Error: "String
'19-06-2018' was not recognized as a valid DateTime."
```

## <a name="static-parameters"></a><span data-ttu-id="9a5a4-122">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="9a5a4-122">Static parameters</span></span>

<span data-ttu-id="9a5a4-123">Статические параметры — это параметры, которые всегда доступны в функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-123">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="9a5a4-124">Большинство параметров в командлетах и скриптах PowerShell являются статическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-124">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="9a5a4-125">В следующем примере показано объявление параметра **ComputerName** , имеющего следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-125">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="9a5a4-126">Это обязательный параметр (обязательно).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-126">It's mandatory (required).</span></span>
- <span data-ttu-id="9a5a4-127">Он принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-127">It takes input from the pipeline.</span></span>
- <span data-ttu-id="9a5a4-128">Он принимает массив строк в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-128">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="9a5a4-129">Атрибуты параметров</span><span class="sxs-lookup"><span data-stu-id="9a5a4-129">Attributes of parameters</span></span>

<span data-ttu-id="9a5a4-130">В этом разделе описываются атрибуты, которые можно добавить в параметры функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-130">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="9a5a4-131">Все атрибуты являются необязательными</span><span class="sxs-lookup"><span data-stu-id="9a5a4-131">All attributes are optional.</span></span> <span data-ttu-id="9a5a4-132">Однако если опустить атрибут **CmdletBinding** , то для распознавания в качестве расширенной функции функция должна включать атрибут **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-132">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="9a5a4-133">В каждое объявление параметра можно добавить один или несколько атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-133">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="9a5a4-134">Количество атрибутов, которые можно добавить в объявление параметра, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-134">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="9a5a4-135">Атрибут параметра</span><span class="sxs-lookup"><span data-stu-id="9a5a4-135">Parameter attribute</span></span>

<span data-ttu-id="9a5a4-136">Атрибут **Parameter** используется для объявления атрибутов параметров функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-136">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="9a5a4-137">Атрибут **параметра** является необязательным, и его можно опустить, если ни один из параметров функций не требует атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-137">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="9a5a4-138">Но для распознавания в качестве расширенной функции, а не для простой функции, функция должна иметь либо атрибут **CmdletBinding** , либо атрибут **Parameter** , либо и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-138">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="9a5a4-139">Атрибут **Parameter** имеет аргументы, определяющие характеристики параметра, например, является ли параметр обязательным или необязательным.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-139">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="9a5a4-140">Используйте следующий синтаксис для объявления атрибута **параметра** , аргумента и значения аргумента.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-140">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="9a5a4-141">Круглые скобки, которые заключают аргумент и его значение, должны следовать за **параметром** без промежуточного пробела.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-141">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="9a5a4-142">Используйте запятые для разделения аргументов в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-142">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="9a5a4-143">Используйте следующий синтаксис, чтобы объявить два аргумента атрибута **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-143">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="9a5a4-144">Типы логических аргументов атрибута **Parameter** по умолчанию имеют **значение false** , если не указано в атрибуте **параметра** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-144">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="9a5a4-145">Присвойте аргументу значение `$true` или просто перечислите аргумент по имени.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-145">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="9a5a4-146">Например, следующие атрибуты **параметров** эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-146">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="9a5a4-147">Если вы используете атрибут **Parameter** без аргументов, в качестве альтернативы использованию атрибута **CmdletBinding** , по-прежнему требуются круглые скобки, следующие за именем атрибута.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-147">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="9a5a4-148">Обязательный аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-148">Mandatory argument</span></span>

<span data-ttu-id="9a5a4-149">`Mandatory`Аргумент указывает, что параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-149">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="9a5a4-150">Если этот аргумент не указан, параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-150">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="9a5a4-151">В следующем примере объявляется параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-151">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="9a5a4-152">Он использует `Mandatory` аргумент, чтобы сделать параметр обязательным.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-152">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="9a5a4-153">Аргумент расположения</span><span class="sxs-lookup"><span data-stu-id="9a5a4-153">Position argument</span></span>

<span data-ttu-id="9a5a4-154">`Position`Аргумент определяет, является ли имя параметра обязательным, если параметр используется в команде.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-154">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="9a5a4-155">Если объявление параметра включает `Position` аргумент, то имя параметра может быть опущено, а PowerShell определяет неименованное значение параметра по его положению или порядку в списке неименованных значений параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-155">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="9a5a4-156">Если `Position` аргумент не указан, имя параметра или псевдоним или аббревиатура имени параметра должно предшествовать значению параметра при использовании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-156">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="9a5a4-157">По умолчанию все параметры функции являются позиционированными.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-157">By default, all function parameters are positional.</span></span> <span data-ttu-id="9a5a4-158">PowerShell присваивает номера позиций параметрам в порядке, в котором параметры объявляются в функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-158">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="9a5a4-159">Чтобы отключить эту функцию, задайте `PositionalBinding` для аргумента атрибута **CmdletBinding** значение `$False` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-159">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="9a5a4-160">`Position`Аргумент имеет приоритет над значением `PositionalBinding` аргумента атрибута **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-160">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="9a5a4-161">Дополнительные сведения см `PositionalBinding` . в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-161">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="9a5a4-162">Значение `Position` аргумента указывается как целое число.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-162">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="9a5a4-163">Значение " **0** " представляет первую точку в команде, значение " **1** " — вторую точку в команде и т. д.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-163">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="9a5a4-164">Если у функции нет позиционированных параметров, PowerShell назначает позиции каждому параметру в соответствии с порядком, в котором объявляются параметры.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-164">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="9a5a4-165">Тем не менее, рекомендуется не полагаться на это назначение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-165">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="9a5a4-166">Если требуется, чтобы параметры были позиционированы, используйте `Position` аргумент.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-166">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="9a5a4-167">В следующем примере объявляется параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-167">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="9a5a4-168">Он использует `Position` аргумент со значением **0**.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-168">It uses the `Position` argument with a value of **0**.</span></span> <span data-ttu-id="9a5a4-169">В результате, если параметр `-ComputerName` не указан в команде, его значение должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-169">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="9a5a4-170">Параметерсетнаме, аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-170">ParameterSetName argument</span></span>

<span data-ttu-id="9a5a4-171">`ParameterSetName`Аргумент задает набор параметров, к которому принадлежит параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-171">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="9a5a4-172">Если набор параметров не задан, параметр относится ко всем наборам параметров, определенным функцией.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-172">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="9a5a4-173">Поэтому для каждого набора параметров должен быть хотя бы один параметр, который не является членом какого-либо другого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-173">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5a4-174">Для командлета или функции существует ограничение в 32 наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-174">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="9a5a4-175">В следующем примере объявляется параметр **ComputerName** в `Computer` наборе параметров, параметр **username** в `User` наборе параметров и параметр **сводки** в обоих наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-175">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

<span data-ttu-id="9a5a4-176">`ParameterSetName`В каждом аргументе можно указать только одно значение и только один `ParameterSetName` аргумент в каждом атрибуте **параметра** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-176">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="9a5a4-177">Чтобы указать, что параметр отображается более чем в одном наборе параметров, добавьте дополнительные атрибуты **параметров** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-177">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="9a5a4-178">В следующем примере параметр **сводки** явно добавляется к `Computer` `User` наборам параметров и.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-178">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="9a5a4-179">Параметр **сводки** является необязательным в `Computer` наборе параметров и обязателен в `User` наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-179">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

<span data-ttu-id="9a5a4-180">Дополнительные сведения о наборах параметров см. в разделе [о наборах параметров](about_parameter_sets.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-180">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="9a5a4-181">Валуефромпипелине, аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-181">ValueFromPipeline argument</span></span>

<span data-ttu-id="9a5a4-182">`ValueFromPipeline`Аргумент указывает, что параметр принимает входные данные из объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-182">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="9a5a4-183">Укажите этот аргумент, если функция принимает весь объект, а не только свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-183">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="9a5a4-184">В следующем примере объявляется параметр **ComputerName** , который является обязательным и принимает объект, который передается в функцию из конвейера.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-184">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="9a5a4-185">Валуефромпипелинебипропертинаме, аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-185">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="9a5a4-186">`ValueFromPipelineByPropertyName`Аргумент указывает, что параметр принимает входные данные из свойства объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-186">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="9a5a4-187">Свойство объекта должно иметь то же имя или псевдоним, что и параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-187">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="9a5a4-188">Например, если функция имеет параметр **ComputerName** , а переданный объект имеет свойство **ComputerName** , значение свойства **ComputerName** присваивается параметру **ComputerName** функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-188">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="9a5a4-189">В следующем примере объявляется обязательный параметр **ComputerName** , который принимает входные данные из свойства **ComputerName** объекта, которое передается в функцию через конвейер.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-189">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="9a5a4-190">Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с _отложенной привязкой_ для параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-190">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="9a5a4-191">Блок скрипта _с отложенной привязкой_ запускается автоматически во время **ParameterBinding оболочки**.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-191">The _delay-bind_ script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="9a5a4-192">Результат привязан к параметру.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-192">The result is bound to the parameter.</span></span> <span data-ttu-id="9a5a4-193">Отложенная привязка не работает для параметров, определенных как тип `ScriptBlock` или `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-193">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="9a5a4-194">Блок скрипта передается _без_ вызова.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-194">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="9a5a4-195">Сведения о блоках скриптов _с отложенной привязкой_ можно узнать здесь [about_Script_Blocks. md](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-195">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="9a5a4-196">Валуефромремаинингаргументс, аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-196">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="9a5a4-197">`ValueFromRemainingArguments`Аргумент указывает, что параметр принимает все значения параметра в команде, которые не назначены другим параметрам функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-197">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="9a5a4-198">В следующем примере объявляется обязательный параметр **значения** и **оставшийся** параметр, принимающий все остальные значения параметров, которые передаются в функцию.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-198">The following example declares a **Value** parameter that's mandatory and a **Remaining** parameter that accepts all the remaining parameter values that are submitted to the function.</span></span>

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 2 elements
0: one
1: two
```

> [!NOTE]
> <span data-ttu-id="9a5a4-199">До выхода версии PowerShell 6,2 коллекция **валуефромремаинингаргументс** была соединена как единая сущность с индексом **0**.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-199">Prior to PowerShell 6.2, the **ValueFromRemainingArguments** collection was joined as single entity under index **0**.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="9a5a4-200">Хелпмессаже, аргумент</span><span class="sxs-lookup"><span data-stu-id="9a5a4-200">HelpMessage argument</span></span>

<span data-ttu-id="9a5a4-201">`HelpMessage`Аргумент задает строку, содержащую краткое описание параметра или его значение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-201">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="9a5a4-202">PowerShell отображает это сообщение в командной строке, которая появляется, когда в команде отсутствует обязательное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-202">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="9a5a4-203">Этот аргумент не влияет на необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-203">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="9a5a4-204">В следующем примере объявляется обязательный параметр **ComputerName** и сообщение справки, поясняющее ожидаемое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-204">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="9a5a4-205">Если для функции не существует другого синтаксиса [справки на основе комментариев](./about_comment_based_help.md) (например,), `.SYNOPSIS` это сообщение также отображается в `Get-Help` выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-205">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="9a5a4-206">Alias - атрибут</span><span class="sxs-lookup"><span data-stu-id="9a5a4-206">Alias attribute</span></span>

<span data-ttu-id="9a5a4-207">Атрибут **Alias** устанавливает альтернативное имя для параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-207">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="9a5a4-208">Количество псевдонимов, которые можно назначить параметру, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-208">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="9a5a4-209">В следующем примере показано объявление параметра, добавляющее псевдонимы **CN** и **MachineName** в обязательный параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-209">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="9a5a4-210">Атрибут Суппортсвилдкардс</span><span class="sxs-lookup"><span data-stu-id="9a5a4-210">SupportsWildcards attribute</span></span>

<span data-ttu-id="9a5a4-211">Атрибут **суппортсвилдкардс** используется для указания того, что параметр принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-211">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="9a5a4-212">В следующем примере показано объявление параметра для обязательного параметра **пути** , который поддерживает подстановочные значения.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-212">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="9a5a4-213">Использование этого атрибута не включает автоматическую поддержку подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-213">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="9a5a4-214">Разработчик командлета должен реализовать код, обрабатывающий входные данные с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-214">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="9a5a4-215">Поддерживаемые подстановочные знаки могут различаться в зависимости от базового API или поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-215">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="9a5a4-216">Дополнительные сведения см. в разделе [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-216">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="9a5a4-217">Атрибуты проверки параметров и переменных</span><span class="sxs-lookup"><span data-stu-id="9a5a4-217">Parameter and variable validation attributes</span></span>

<span data-ttu-id="9a5a4-218">Атрибуты проверки Direct PowerShell для проверки значений параметров, отправляемых пользователями при вызове расширенной функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-218">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="9a5a4-219">Если значения параметров не прошли проверку, создается ошибка и функция не вызывается.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-219">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="9a5a4-220">Проверка параметров применяется только к предоставленным входным данным, а любые другие значения, такие как значения по умолчанию, не проверяются.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-220">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="9a5a4-221">Можно также использовать атрибуты проверки, чтобы ограничить значения, которые пользователи могут указывать для переменных.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-221">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="9a5a4-222">При использовании преобразователя типов вместе с атрибутом проверки преобразователь типов должен быть определен перед атрибутом.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-222">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="9a5a4-223">Атрибут проверки AllowNull</span><span class="sxs-lookup"><span data-stu-id="9a5a4-223">AllowNull validation attribute</span></span>

<span data-ttu-id="9a5a4-224">Атрибут **AllowNull** допускает значение обязательного параметра `$null` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-224">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="9a5a4-225">В следующем примере объявляется параметр **компутеринфо** Hashtable, который может иметь значение **null** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-225">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="9a5a4-226">Атрибут **AllowNull** не работает, если преобразователь типов имеет значение String, так как тип строки не принимает значение null.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-226">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="9a5a4-227">Для этого сценария можно использовать атрибут **алловемптистринг** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-227">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="9a5a4-228">Атрибут проверки Алловемптистринг</span><span class="sxs-lookup"><span data-stu-id="9a5a4-228">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="9a5a4-229">Атрибут **алловемптистринг** позволяет значению обязательного параметра быть пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-229">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="9a5a4-230">В следующем примере объявляется параметр **ComputerName** , который может иметь пустое строковое значение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-230">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="9a5a4-231">Атрибут проверки Алловемптиколлектион</span><span class="sxs-lookup"><span data-stu-id="9a5a4-231">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="9a5a4-232">Атрибут **алловемптиколлектион** позволяет значению обязательного параметра быть пустой коллекцией `@()` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-232">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="9a5a4-233">В следующем примере объявляется параметр **ComputerName** , который может иметь пустое значение коллекции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-233">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="9a5a4-234">Атрибут проверки Валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="9a5a4-234">ValidateCount validation attribute</span></span>

<span data-ttu-id="9a5a4-235">Атрибут **валидатекаунт** указывает минимальное и максимальное число значений параметров, принимаемых параметром.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-235">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="9a5a4-236">PowerShell выдает ошибку, если число значений параметров в команде, вызывающей функцию, находится за пределами этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-236">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="9a5a4-237">Приведенное ниже объявление параметра создает параметр **ComputerName** , который принимает от одного до пяти значений параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-237">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="9a5a4-238">Атрибут проверки Валидателенгс</span><span class="sxs-lookup"><span data-stu-id="9a5a4-238">ValidateLength validation attribute</span></span>

<span data-ttu-id="9a5a4-239">Атрибут **валидателенгс** указывает минимальное и максимальное число символов в значении параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-239">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="9a5a4-240">PowerShell выдает ошибку, если длина значения, указанного для параметра или переменной, находится за пределами диапазона.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-240">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="9a5a4-241">В следующем примере имя каждого компьютера должно содержать от 1 до десяти символов.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-241">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="9a5a4-242">В следующем примере значение переменной `$number` должно быть как минимум одним символом в длину и не более десяти символов.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-242">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="9a5a4-243">В этом примере значение `01` заключено в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-243">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="9a5a4-244">Атрибут **валидателенгс** не принимает число без заключения в кавычки.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-244">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="9a5a4-245">Атрибут проверки ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="9a5a4-245">ValidatePattern validation attribute</span></span>

<span data-ttu-id="9a5a4-246">Атрибут **ValidatePattern** указывает регулярное выражение, которое сравнивается с параметром или значением переменной.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-246">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="9a5a4-247">PowerShell выдает ошибку, если значение не соответствует шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-247">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="9a5a4-248">В следующем примере значение параметра должно содержать четырехзначное число, а каждая цифра должна быть числом от 0 до девяти.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-248">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="9a5a4-249">В следующем примере значение переменной `$number` должно быть ровно четырехзначным числом, а каждая цифра должна быть числом от 0 до девяти.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-249">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="9a5a4-250">Атрибут проверки Валидатеранже</span><span class="sxs-lookup"><span data-stu-id="9a5a4-250">ValidateRange validation attribute</span></span>

<span data-ttu-id="9a5a4-251">Атрибут **валидатеранже** задает числовой диапазон или **валидатеранжекинд** значение перечисления для каждого значения параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-251">The **ValidateRange** attribute specifies a numeric range or a **ValidateRangeKind** enum value for each parameter or variable value.</span></span>
<span data-ttu-id="9a5a4-252">PowerShell выдает ошибку, если какое-либо значение выходит за пределы этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-252">PowerShell generates an error if any value is outside that range.</span></span>

<span data-ttu-id="9a5a4-253">Перечисление **валидатеранжекинд** допускает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-253">The **ValidateRangeKind** enum allows for the following values:</span></span>

- <span data-ttu-id="9a5a4-254">**Положительное** число больше нуля.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-254">**Positive** - A number greater than zero.</span></span>
- <span data-ttu-id="9a5a4-255">**Отрицательное** — число меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-255">**Negative** - A number less than zero.</span></span>
- <span data-ttu-id="9a5a4-256">**Неположительное** число, меньшее или равное нулю.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-256">**NonPositive** - A number less than or equal to zero.</span></span>
- <span data-ttu-id="9a5a4-257">**Неотрицательное** — число больше или равно нулю.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-257">**NonNegative** - A number greater than or equal to zero.</span></span>

<span data-ttu-id="9a5a4-258">В следующем примере значение параметра **попыток** должно находиться в диапазоне от 0 до десяти.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-258">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="9a5a4-259">В следующем примере значение переменной `$number` должно находиться в диапазоне от 0 до десяти.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-259">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

<span data-ttu-id="9a5a4-260">В следующем примере значение переменной `$number` должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-260">In the following example, the value of the variable `$number` must be greater than zero.</span></span>

```powershell
[Int32][ValidateRange("Positive")]$number = 1
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="9a5a4-261">Атрибут проверки Валидатескрипт</span><span class="sxs-lookup"><span data-stu-id="9a5a4-261">ValidateScript validation attribute</span></span>

<span data-ttu-id="9a5a4-262">Атрибут **валидатескрипт** указывает скрипт, используемый для проверки значения параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-262">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="9a5a4-263">PowerShell передает значение в скрипт и выдает ошибку, если скрипт возвращает `$false` или вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-263">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="9a5a4-264">При использовании атрибута **валидатескрипт** проверяемое значение сопоставляется с `$_` переменной.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-264">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="9a5a4-265">Переменную можно использовать `$_` для ссылки на значение в скрипте.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-265">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="9a5a4-266">В следующем примере значение параметра **евентдате** должно быть больше или равно текущей дате.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-266">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="9a5a4-267">В следующем примере значение переменной `$date` должно быть больше текущей даты и времени или равно ей.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-267">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="9a5a4-268">При использовании **валидатескрипт** нельзя передавать `$null` значение в параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-268">If you use **ValidateScript**, you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="9a5a4-269">При передаче значения NULL **валидатескрипт** не может проверить аргумент.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-269">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="9a5a4-270">Атрибут "Validate"</span><span class="sxs-lookup"><span data-stu-id="9a5a4-270">ValidateSet attribute</span></span>

<span data-ttu-id="9a5a4-271">Атрибут **Validate** задает набор допустимых значений для параметра или переменной и включает Заполнение клавишей TAB.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-271">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="9a5a4-272">PowerShell выдает ошибку, если значение параметра или переменной не соответствует значению в наборе.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-272">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="9a5a4-273">В следующем примере значение параметра **detail** может быть только низким, средним или высоким.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-273">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="9a5a4-274">В следующем примере значение переменной `$flavor` должно быть шоколадным, Strawberry или обычный.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-274">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="9a5a4-275">Проверка выполняется каждый раз, когда переменная присваивается даже внутри скрипта.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-275">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="9a5a4-276">Например, следующее приводит к ошибке во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-276">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

#### <a name="dynamic-validateset-values"></a><span data-ttu-id="9a5a4-277">Динамические значения Validate</span><span class="sxs-lookup"><span data-stu-id="9a5a4-277">Dynamic validateSet values</span></span>

<span data-ttu-id="9a5a4-278">**Класс** можно использовать для динамического создания значений для **Validate** во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-278">You can use a **Class** to dynamically generate the values for **ValidateSet** at runtime.</span></span> <span data-ttu-id="9a5a4-279">В следующем примере допустимые значения для переменной `$Sound` создаются с помощью **класса** с именем **саунднамес** , который проверяет три пути файловой системы для доступных звуковых файлов:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-279">In the following example, the valid values for the variable `$Sound` are generated via a **Class** named **SoundNames** that checks three filesystem paths for available sound files:</span></span>

```powershell
Class SoundNames : System.Management.Automation.IValidateSetValuesGenerator {
    [String[]] GetValidValues() {
        $SoundPaths = '/System/Library/Sounds/',
            '/Library/Sounds','~/Library/Sounds'
        $SoundNames = ForEach ($SoundPath in $SoundPaths) {
            If (Test-Path $SoundPath) {
                (Get-ChildItem $SoundPath).BaseName
            }
        }
        return [String[]] $SoundNames
    }
}
```

<span data-ttu-id="9a5a4-280">`[SoundNames]`Затем класс реализуется как динамическое значение **Validate** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-280">The `[SoundNames]` class is then implemented as a dynamic **ValidateSet** value as follows:</span></span>

```powershell
Param(
    [ValidateSet([SoundNames])]
    [String]$Sound
)
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="9a5a4-281">Атрибут проверки Валидатенотнулл</span><span class="sxs-lookup"><span data-stu-id="9a5a4-281">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="9a5a4-282">Атрибут **валидатенотнулл** указывает, что значение параметра не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-282">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="9a5a4-283">PowerShell выдает ошибку, если параметр имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-283">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="9a5a4-284">Атрибут **валидатенотнулл** предназначен для использования, если параметр является необязательным и тип не определен или имеет преобразователь типов, который не может неявно преобразовать значение null, например **Object**.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-284">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object**.</span></span> <span data-ttu-id="9a5a4-285">Если указать тип, который будет неявно преобразовывать значение null, например **строку**, значение NULL преобразуется в пустую строку даже при использовании атрибута **валидатенотнулл** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-285">If you specify a type that that will implicitly convert a null value such as a **string**, the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="9a5a4-286">Для этого сценария используйте **валидатенотнуллоремпти**</span><span class="sxs-lookup"><span data-stu-id="9a5a4-286">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="9a5a4-287">В следующем примере значение параметра **ID** не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-287">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="9a5a4-288">Атрибут проверки Валидатенотнуллоремпти</span><span class="sxs-lookup"><span data-stu-id="9a5a4-288">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="9a5a4-289">Атрибут **валидатенотнуллоремпти** указывает, что значение параметра не может быть `$null` пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-289">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="9a5a4-290">PowerShell выдает ошибку, если параметр используется в вызове функции, но имеет значение `$null` , пустую строку ( `""` ) или пустой массив `@()` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-290">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="9a5a4-291">Атрибут проверки Валидатедриве</span><span class="sxs-lookup"><span data-stu-id="9a5a4-291">ValidateDrive validation attribute</span></span>

<span data-ttu-id="9a5a4-292">Атрибут **валидатедриве** указывает, что значение параметра должно представлять путь, который ссылается только на разрешенные диски.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-292">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="9a5a4-293">PowerShell выдает ошибку, если значение параметра относится к дискам, отличным от разрешенного.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-293">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="9a5a4-294">Наличие пути, за исключением самого диска, не проверяется.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-294">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="9a5a4-295">Если используется относительный путь, текущий диск должен находиться в списке разрешенных дисков.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-295">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="9a5a4-296">Атрибут проверки Валидатеусердриве</span><span class="sxs-lookup"><span data-stu-id="9a5a4-296">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="9a5a4-297">Атрибут **валидатеусердриве** указывает, что значение параметра должно представлять путь, который ссылается на `User` диск.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-297">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="9a5a4-298">PowerShell выдает ошибку, если путь ссылается на другой диск.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-298">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="9a5a4-299">Атрибут проверки проверяет только наличие части пути, которая является диском.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-299">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="9a5a4-300">Если используется относительный путь, то текущий диск должен быть `User` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-300">If you use relative path, the current drive must be `User`.</span></span>

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

<span data-ttu-id="9a5a4-301">Вы можете определить `User` диск в достаточном объеме конфигураций сеансов администрирования (JEA).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-301">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="9a5a4-302">В этом примере мы создадим диск User:.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-302">For this example, we create the User: drive.</span></span>

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="9a5a4-303">Атрибут проверки Валидатетрустеддата</span><span class="sxs-lookup"><span data-stu-id="9a5a4-303">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="9a5a4-304">Этот атрибут был добавлен в 6.1.1 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-304">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="9a5a4-305">В настоящее время атрибут используется внутри самой PowerShell и не предназначен для внешнего использования.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-305">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="9a5a4-306">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="9a5a4-306">Dynamic parameters</span></span>

<span data-ttu-id="9a5a4-307">Динамические параметры — это параметры командлета, функции или скрипта, доступные только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-307">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="9a5a4-308">Например, несколько командлетов поставщика имеют параметры, доступные только при использовании командлета на диске поставщика или в определенном пути к диску поставщика.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-308">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="9a5a4-309">Например, параметр **Encoding** доступен для `Add-Content` `Get-Content` командлетов, и, `Set-Content` только если он используется на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-309">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="9a5a4-310">Можно также создать параметр, который появляется только в том случае, если другой параметр используется в команде функции или если другой параметр имеет определенное значение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-310">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="9a5a4-311">Динамические параметры могут быть полезными, но их следует использовать только при необходимости, так как пользователям может быть трудно обнаружить.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-311">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="9a5a4-312">Чтобы найти динамический параметр, пользователь должен быть в пути поставщика, использовать параметр **ArgumentList** `Get-Command` командлета или использовать параметр **path** в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-312">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="9a5a4-313">Чтобы создать динамический параметр для функции или скрипта, используйте `DynamicParam` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-313">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="9a5a4-314">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-314">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="9a5a4-315">В списке инструкций используйте `If` оператор, чтобы указать условия, при которых параметр доступен в функции.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-315">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="9a5a4-316">Используйте `New-Object` командлет, чтобы создать объект **System. Management. Automation. рунтимедефинедпараметер** для представления параметра и указать его имя.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-316">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="9a5a4-317">Вы можете использовать `New-Object` команду, чтобы создать объект **System. Management. Automation. параметераттрибуте** для представления атрибутов параметра, например **обязательный**, параметр " **Расположение**" или " **валуефромпипелине** " или набор параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-317">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory**, **Position**, or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="9a5a4-318">В следующем примере показан пример функции со стандартными параметрами **Name** и **path** и необязательным динамическим параметром с именем **DP1**.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-318">The following example shows a sample function with standard parameters named **Name** and **Path**, and an optional dynamic parameter named **DP1**.</span></span> <span data-ttu-id="9a5a4-319">Параметр **DP1** находится в `PSet1` наборе параметров и имеет тип `Int32` .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-319">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="9a5a4-320">Параметр **DP1** доступен в `Get-Sample` функции только в том случае, если значение параметра **path** начинается с `HKLM:` , что указывает на то, что он используется на `HKEY_LOCAL_MACHINE` диске реестра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-320">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

<span data-ttu-id="9a5a4-321">Дополнительные сведения см. в разделе [рунтимедефинедпараметер](/dotnet/api/system.management.automation.runtimedefinedparameter).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-321">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="9a5a4-322">Параметры-переключатели</span><span class="sxs-lookup"><span data-stu-id="9a5a4-322">Switch parameters</span></span>

<span data-ttu-id="9a5a4-323">Параметры переключателей — это параметры без значения параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-323">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="9a5a4-324">Они вступают в силу только в том случае, если они используются и имеют только один результат.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-324">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="9a5a4-325">Например, параметром **Parameter параметра** **powershell.exe** является параметр Switch.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-325">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="9a5a4-326">Чтобы создать параметр переключателя в функции, укажите `Switch` тип в определении параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-326">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="9a5a4-327">Пример:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-327">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="9a5a4-328">Кроме того, можно использовать другой метод:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-328">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="9a5a4-329">Параметры переключателей просты в использовании и являются предпочтительными по сравнению с логическими параметрами, которые имеют более сложный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-329">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="9a5a4-330">Например, чтобы использовать параметр Switch, пользователь вводит параметр в команду.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-330">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="9a5a4-331">Чтобы использовать логический параметр, пользователь вводит параметр и логическое значение.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-331">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="9a5a4-332">При создании параметров переключателя следует тщательно выбирать имя параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-332">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="9a5a4-333">Убедитесь, что имя параметра передает пользователю результат параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-333">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="9a5a4-334">Избегайте неоднозначных терминов, таких как **Фильтр** или **Максимальное** значение, которое может требовать значения.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-334">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="9a5a4-335">Атрибут Аргументкомплетер</span><span class="sxs-lookup"><span data-stu-id="9a5a4-335">ArgumentCompleter attribute</span></span>

<span data-ttu-id="9a5a4-336">Атрибут **аргументкомплетер** позволяет добавлять значения заполнения клавишей TAB в конкретный параметр.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-336">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="9a5a4-337">Атрибут **аргументкомплетер** должен быть определен для каждого параметра, для которого требуется заполнение по клавише TAB.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-337">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="9a5a4-338">Как и в случае с **DynamicParameters**, доступные значения рассчитываются во время выполнения, когда пользователь нажимает клавишу <kbd>Tab</kbd> после имени параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-338">Similar to **DynamicParameters**, the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="9a5a4-339">Чтобы добавить атрибут **аргументкомплетер** , необходимо определить блок скрипта, который определяет значения.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-339">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="9a5a4-340">Блок скрипта должен принимать следующие параметры в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-340">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="9a5a4-341">Имена параметров не важны, так как значения указаны по положению.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-341">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="9a5a4-342">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-342">The syntax is as follows:</span></span>

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="9a5a4-343">Блок сценария Аргументкомплетер</span><span class="sxs-lookup"><span data-stu-id="9a5a4-343">ArgumentCompleter script block</span></span>

<span data-ttu-id="9a5a4-344">Для параметров блока сценария задаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9a5a4-344">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="9a5a4-345">`$commandName` (Расположение 0) — Этот параметр задает имя команды, для которой блок скрипта обеспечивает заполнение нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-345">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="9a5a4-346">`$parameterName` (Расположение 1) — Этот параметр задан для параметра, значение которого требует заполнения нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-346">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="9a5a4-347">`$wordToComplete` (Расположение 2) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-347">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="9a5a4-348">`$commandAst` (Расположение 3) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-348">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="9a5a4-349">Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-349">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="9a5a4-350">`$fakeBoundParameters` (Расположение 4) — для этого параметра задается хэш-таблица `$PSBoundParameters` , содержащая для командлета перед нажатием пользователем <kbd>вкладки</kbd>. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a4-350">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="9a5a4-351">Блок скрипта **аргументкомплетер** должен выполнить девращение значений с помощью конвейера, например `ForEach-Object` , `Where-Object` или другого подходящего метода.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-351">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="9a5a4-352">Возврат массива значений приводит к тому, что PowerShell обрабатывает весь массив как **одно** значение заполнения Tab.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-352">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="9a5a4-353">В следующем примере заполнение клавиши TAB добавляется в параметр **value** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-353">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="9a5a4-354">Если указан только параметр **value** , отображаются все возможные значения или аргументы для **параметра значение** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-354">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="9a5a4-355">Если указан параметр **типа** , параметр **value** отображает только возможные значения для этого типа.</span><span class="sxs-lookup"><span data-stu-id="9a5a4-355">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="9a5a4-356">Кроме того, `-like` оператор гарантирует, что если пользователь вводит следующую команду и использует заполнение по <kbd>клавише TAB</kbd> , возвращается только **Apple** .</span><span class="sxs-lookup"><span data-stu-id="9a5a4-356">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a><span data-ttu-id="9a5a4-357">См. также</span><span class="sxs-lookup"><span data-stu-id="9a5a4-357">See also</span></span>

[<span data-ttu-id="9a5a4-358">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9a5a4-358">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="9a5a4-359">about_Functions</span><span class="sxs-lookup"><span data-stu-id="9a5a4-359">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="9a5a4-360">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="9a5a4-360">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="9a5a4-361">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="9a5a4-361">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="9a5a4-362">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="9a5a4-362">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="9a5a4-363">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="9a5a4-363">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

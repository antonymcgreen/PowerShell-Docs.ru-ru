---
description: Объясняется, как добавлять параметры в расширенные функции.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 4123d71392f8b32df8d04033d85476cb18b39736
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "93233290"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="320a3-104">О функциях дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="320a3-104">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="320a3-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="320a3-105">Short description</span></span>

<span data-ttu-id="320a3-106">Объясняется, как добавлять параметры в расширенные функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-106">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="320a3-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="320a3-107">Long description</span></span>

<span data-ttu-id="320a3-108">Вы можете добавить параметры в расширенные функции, которые вы пишете, и использовать атрибуты и аргументы параметров для ограничения значений параметров, которые пользователи будут передавать с параметром.</span><span class="sxs-lookup"><span data-stu-id="320a3-108">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="320a3-109">Параметры, добавляемые в функцию, доступны пользователям в дополнение к общим параметрам, которые PowerShell автоматически добавляет ко всем командлетам и расширенным функциям.</span><span class="sxs-lookup"><span data-stu-id="320a3-109">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="320a3-110">Дополнительные сведения об общих параметрах PowerShell см. в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-110">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="320a3-111">Начиная с PowerShell 3,0 можно использовать Сплаттинг с `@Args` для представления параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="320a3-111">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="320a3-112">Сплаттинг является допустимым для простых и расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="320a3-112">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="320a3-113">Дополнительные сведения см. в разделе [about_Functions](about_Functions.md) и [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-113">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="320a3-114">Преобразование типов значений параметров</span><span class="sxs-lookup"><span data-stu-id="320a3-114">Type conversion of parameter values</span></span>

<span data-ttu-id="320a3-115">При предоставлении строк в качестве аргументов для параметров, которые предполагают другой тип, PowerShell неявно преобразует строки в целевой тип параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-115">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="320a3-116">Расширенные функции выполняют синтаксический анализ инвариантных значений параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-116">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="320a3-117">В отличие от этого, преобразование с учетом языка и региональных параметров выполняется во время привязки параметра для скомпилированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="320a3-117">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="320a3-118">В этом примере мы создадим командлет и функцию скрипта, которая принимает `[datetime]` параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-118">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="320a3-119">Текущий язык и региональные параметры изменены для использования параметров немецкого языка.</span><span class="sxs-lookup"><span data-stu-id="320a3-119">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="320a3-120">Дата в немецком формате передается в параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-120">A German-formatted date is passed to the parameter.</span></span>

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

<span data-ttu-id="320a3-121">Как показано выше, командлеты используют синтаксический анализ с учетом языка и региональных параметров для преобразования строки.</span><span class="sxs-lookup"><span data-stu-id="320a3-121">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

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

<span data-ttu-id="320a3-122">Дополнительные функции используют синтаксический анализ инвариантного языка и региональных параметров, что приводит к следующей ошибке.</span><span class="sxs-lookup"><span data-stu-id="320a3-122">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a><span data-ttu-id="320a3-123">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="320a3-123">Static parameters</span></span>

<span data-ttu-id="320a3-124">Статические параметры — это параметры, которые всегда доступны в функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-124">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="320a3-125">Большинство параметров в командлетах и скриптах PowerShell являются статическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="320a3-125">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="320a3-126">В следующем примере показано объявление параметра **ComputerName** , имеющего следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="320a3-126">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="320a3-127">Это обязательный параметр (обязательно).</span><span class="sxs-lookup"><span data-stu-id="320a3-127">It's mandatory (required).</span></span>
- <span data-ttu-id="320a3-128">Он принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="320a3-128">It takes input from the pipeline.</span></span>
- <span data-ttu-id="320a3-129">Он принимает массив строк в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="320a3-129">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="320a3-130">Атрибуты параметров</span><span class="sxs-lookup"><span data-stu-id="320a3-130">Attributes of parameters</span></span>

<span data-ttu-id="320a3-131">В этом разделе описываются атрибуты, которые можно добавить в параметры функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-131">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="320a3-132">Все атрибуты являются необязательными</span><span class="sxs-lookup"><span data-stu-id="320a3-132">All attributes are optional.</span></span> <span data-ttu-id="320a3-133">Однако если опустить атрибут **CmdletBinding** , то для распознавания в качестве расширенной функции функция должна включать атрибут **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="320a3-133">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="320a3-134">В каждое объявление параметра можно добавить один или несколько атрибутов.</span><span class="sxs-lookup"><span data-stu-id="320a3-134">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="320a3-135">Количество атрибутов, которые можно добавить в объявление параметра, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="320a3-135">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="320a3-136">Атрибут параметра</span><span class="sxs-lookup"><span data-stu-id="320a3-136">Parameter attribute</span></span>

<span data-ttu-id="320a3-137">Атрибут **Parameter** используется для объявления атрибутов параметров функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-137">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="320a3-138">Атрибут **параметра** является необязательным, и его можно опустить, если ни один из параметров функций не требует атрибутов.</span><span class="sxs-lookup"><span data-stu-id="320a3-138">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="320a3-139">Но для распознавания в качестве расширенной функции, а не для простой функции, функция должна иметь либо атрибут **CmdletBinding** , либо атрибут **Parameter** , либо и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="320a3-139">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="320a3-140">Атрибут **Parameter** имеет аргументы, определяющие характеристики параметра, например, является ли параметр обязательным или необязательным.</span><span class="sxs-lookup"><span data-stu-id="320a3-140">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="320a3-141">Используйте следующий синтаксис для объявления атрибута **параметра** , аргумента и значения аргумента.</span><span class="sxs-lookup"><span data-stu-id="320a3-141">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="320a3-142">Круглые скобки, которые заключают аргумент и его значение, должны следовать за **параметром** без промежуточного пробела.</span><span class="sxs-lookup"><span data-stu-id="320a3-142">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="320a3-143">Используйте запятые для разделения аргументов в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="320a3-143">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="320a3-144">Используйте следующий синтаксис, чтобы объявить два аргумента атрибута **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="320a3-144">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="320a3-145">Типы логических аргументов атрибута **Parameter** по умолчанию имеют **значение false** , если не указано в атрибуте **параметра** .</span><span class="sxs-lookup"><span data-stu-id="320a3-145">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="320a3-146">Присвойте аргументу значение `$true` или просто перечислите аргумент по имени.</span><span class="sxs-lookup"><span data-stu-id="320a3-146">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="320a3-147">Например, следующие атрибуты **параметров** эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="320a3-147">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="320a3-148">Если вы используете атрибут **Parameter** без аргументов, в качестве альтернативы использованию атрибута **CmdletBinding** , по-прежнему требуются круглые скобки, следующие за именем атрибута.</span><span class="sxs-lookup"><span data-stu-id="320a3-148">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="320a3-149">Обязательный аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-149">Mandatory argument</span></span>

<span data-ttu-id="320a3-150">`Mandatory`Аргумент указывает, что параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="320a3-150">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="320a3-151">Если этот аргумент не указан, параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="320a3-151">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="320a3-152">В следующем примере объявляется параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="320a3-152">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="320a3-153">Он использует `Mandatory` аргумент, чтобы сделать параметр обязательным.</span><span class="sxs-lookup"><span data-stu-id="320a3-153">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="320a3-154">Аргумент расположения</span><span class="sxs-lookup"><span data-stu-id="320a3-154">Position argument</span></span>

<span data-ttu-id="320a3-155">`Position`Аргумент определяет, является ли имя параметра обязательным, если параметр используется в команде.</span><span class="sxs-lookup"><span data-stu-id="320a3-155">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="320a3-156">Если объявление параметра включает `Position` аргумент, то имя параметра может быть опущено, а PowerShell определяет неименованное значение параметра по его положению или порядку в списке неименованных значений параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="320a3-156">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="320a3-157">Если `Position` аргумент не указан, имя параметра или псевдоним или аббревиатура имени параметра должно предшествовать значению параметра при использовании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="320a3-157">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="320a3-158">По умолчанию все параметры функции являются позиционированными.</span><span class="sxs-lookup"><span data-stu-id="320a3-158">By default, all function parameters are positional.</span></span> <span data-ttu-id="320a3-159">PowerShell присваивает номера позиций параметрам в порядке, в котором параметры объявляются в функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-159">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="320a3-160">Чтобы отключить эту функцию, задайте `PositionalBinding` для аргумента атрибута **CmdletBinding** значение `$False` .</span><span class="sxs-lookup"><span data-stu-id="320a3-160">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="320a3-161">`Position`Аргумент имеет приоритет над значением `PositionalBinding` аргумента атрибута **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="320a3-161">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="320a3-162">Дополнительные сведения см `PositionalBinding` . в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-162">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="320a3-163">Значение `Position` аргумента указывается как целое число.</span><span class="sxs-lookup"><span data-stu-id="320a3-163">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="320a3-164">Значение " **0** " представляет первую точку в команде, значение " **1** " — вторую точку в команде и т. д.</span><span class="sxs-lookup"><span data-stu-id="320a3-164">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="320a3-165">Если у функции нет позиционированных параметров, PowerShell назначает позиции каждому параметру в соответствии с порядком, в котором объявляются параметры.</span><span class="sxs-lookup"><span data-stu-id="320a3-165">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="320a3-166">Тем не менее, рекомендуется не полагаться на это назначение.</span><span class="sxs-lookup"><span data-stu-id="320a3-166">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="320a3-167">Если требуется, чтобы параметры были позиционированы, используйте `Position` аргумент.</span><span class="sxs-lookup"><span data-stu-id="320a3-167">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="320a3-168">В следующем примере объявляется параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="320a3-168">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="320a3-169">Он использует `Position` аргумент со значением **0**.</span><span class="sxs-lookup"><span data-stu-id="320a3-169">It uses the `Position` argument with a value of **0**.</span></span> <span data-ttu-id="320a3-170">В результате, если параметр `-ComputerName` не указан в команде, его значение должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="320a3-170">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="320a3-171">Параметерсетнаме, аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-171">ParameterSetName argument</span></span>

<span data-ttu-id="320a3-172">`ParameterSetName`Аргумент задает набор параметров, к которому принадлежит параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-172">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="320a3-173">Если набор параметров не задан, параметр относится ко всем наборам параметров, определенным функцией.</span><span class="sxs-lookup"><span data-stu-id="320a3-173">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="320a3-174">Поэтому для каждого набора параметров должен быть хотя бы один параметр, который не является членом какого-либо другого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-174">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="320a3-175">Для командлета или функции существует ограничение в 32 наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-175">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="320a3-176">В следующем примере объявляется параметр **ComputerName** в `Computer` наборе параметров, параметр **username** в `User` наборе параметров и параметр **сводки** в обоих наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-176">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

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

<span data-ttu-id="320a3-177">`ParameterSetName`В каждом аргументе можно указать только одно значение и только один `ParameterSetName` аргумент в каждом атрибуте **параметра** .</span><span class="sxs-lookup"><span data-stu-id="320a3-177">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="320a3-178">Чтобы указать, что параметр отображается более чем в одном наборе параметров, добавьте дополнительные атрибуты **параметров** .</span><span class="sxs-lookup"><span data-stu-id="320a3-178">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="320a3-179">В следующем примере параметр **сводки** явно добавляется к `Computer` `User` наборам параметров и.</span><span class="sxs-lookup"><span data-stu-id="320a3-179">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="320a3-180">Параметр **сводки** является необязательным в `Computer` наборе параметров и обязателен в `User` наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-180">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

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

<span data-ttu-id="320a3-181">Дополнительные сведения о наборах параметров см. в разделе [о наборах параметров](about_parameter_sets.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-181">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="320a3-182">Валуефромпипелине, аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-182">ValueFromPipeline argument</span></span>

<span data-ttu-id="320a3-183">`ValueFromPipeline`Аргумент указывает, что параметр принимает входные данные из объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="320a3-183">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="320a3-184">Укажите этот аргумент, если функция принимает весь объект, а не только свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="320a3-184">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="320a3-185">В следующем примере объявляется параметр **ComputerName** , который является обязательным и принимает объект, который передается в функцию из конвейера.</span><span class="sxs-lookup"><span data-stu-id="320a3-185">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="320a3-186">Валуефромпипелинебипропертинаме, аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-186">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="320a3-187">`ValueFromPipelineByPropertyName`Аргумент указывает, что параметр принимает входные данные из свойства объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="320a3-187">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="320a3-188">Свойство объекта должно иметь то же имя или псевдоним, что и параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-188">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="320a3-189">Например, если функция имеет параметр **ComputerName** , а переданный объект имеет свойство **ComputerName** , значение свойства **ComputerName** присваивается параметру **ComputerName** функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-189">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="320a3-190">В следующем примере объявляется обязательный параметр **ComputerName** , который принимает входные данные из свойства **ComputerName** объекта, которое передается в функцию через конвейер.</span><span class="sxs-lookup"><span data-stu-id="320a3-190">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="320a3-191">Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с _отложенной привязкой_ для параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-191">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="320a3-192">Блок скрипта _с отложенной привязкой_ запускается автоматически во время **ParameterBinding оболочки**.</span><span class="sxs-lookup"><span data-stu-id="320a3-192">The _delay-bind_ script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="320a3-193">Результат привязан к параметру.</span><span class="sxs-lookup"><span data-stu-id="320a3-193">The result is bound to the parameter.</span></span> <span data-ttu-id="320a3-194">Отложенная привязка не работает для параметров, определенных как тип `ScriptBlock` или `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="320a3-194">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="320a3-195">Блок скрипта передается _без_ вызова.</span><span class="sxs-lookup"><span data-stu-id="320a3-195">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="320a3-196">Сведения о блоках скриптов _с отложенной привязкой_ можно узнать здесь [about_Script_Blocks. md](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-196">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="320a3-197">Валуефромремаинингаргументс, аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-197">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="320a3-198">`ValueFromRemainingArguments`Аргумент указывает, что параметр принимает все значения параметра в команде, которые не назначены другим параметрам функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-198">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="320a3-199">Существует известная ошибка при использовании коллекций с **валуефромремаинингаргументс** , где переданная коллекция рассматривается как один элемент.</span><span class="sxs-lookup"><span data-stu-id="320a3-199">There's a known issue for using collections with **ValueFromRemainingArguments** where the passed-in collection is treated as a single element.</span></span>

<span data-ttu-id="320a3-200">В следующем примере показана эта известная проблема.</span><span class="sxs-lookup"><span data-stu-id="320a3-200">The following example demonstrates this known issue.</span></span> <span data-ttu-id="320a3-201">**Оставшийся** параметр должен содержать **один** с **индексом 0** и **двумя** с **индексом 1**.</span><span class="sxs-lookup"><span data-stu-id="320a3-201">The **Remaining** parameter should contain **one** at **index 0** and **two** at **index 1**.</span></span>
<span data-ttu-id="320a3-202">Вместо этого оба элемента объединяются в одну сущность.</span><span class="sxs-lookup"><span data-stu-id="320a3-202">Instead, both elements are combined into a single entity.</span></span>

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
Found 1 elements
0: one two
```

> [!NOTE]
> <span data-ttu-id="320a3-203">Эта проблема решена в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="320a3-203">This issue is resolved in PowerShell 6.2.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="320a3-204">Хелпмессаже, аргумент</span><span class="sxs-lookup"><span data-stu-id="320a3-204">HelpMessage argument</span></span>

<span data-ttu-id="320a3-205">`HelpMessage`Аргумент задает строку, содержащую краткое описание параметра или его значение.</span><span class="sxs-lookup"><span data-stu-id="320a3-205">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="320a3-206">PowerShell отображает это сообщение в командной строке, которая появляется, когда в команде отсутствует обязательное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-206">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="320a3-207">Этот аргумент не влияет на необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="320a3-207">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="320a3-208">В следующем примере объявляется обязательный параметр **ComputerName** и сообщение справки, поясняющее ожидаемое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-208">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="320a3-209">Если для функции не существует другого синтаксиса [справки на основе комментариев](./about_comment_based_help.md) (например,), `.SYNOPSIS` это сообщение также отображается в `Get-Help` выходных данных.</span><span class="sxs-lookup"><span data-stu-id="320a3-209">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="320a3-210">Alias - атрибут</span><span class="sxs-lookup"><span data-stu-id="320a3-210">Alias attribute</span></span>

<span data-ttu-id="320a3-211">Атрибут **Alias** устанавливает альтернативное имя для параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-211">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="320a3-212">Количество псевдонимов, которые можно назначить параметру, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="320a3-212">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="320a3-213">В следующем примере показано объявление параметра, добавляющее псевдонимы **CN** и **MachineName** в обязательный параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="320a3-213">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="320a3-214">Атрибут Суппортсвилдкардс</span><span class="sxs-lookup"><span data-stu-id="320a3-214">SupportsWildcards attribute</span></span>

<span data-ttu-id="320a3-215">Атрибут **суппортсвилдкардс** используется для указания того, что параметр принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="320a3-215">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="320a3-216">В следующем примере показано объявление параметра для обязательного параметра **пути** , который поддерживает подстановочные значения.</span><span class="sxs-lookup"><span data-stu-id="320a3-216">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="320a3-217">Использование этого атрибута не включает автоматическую поддержку подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="320a3-217">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="320a3-218">Разработчик командлета должен реализовать код, обрабатывающий входные данные с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="320a3-218">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="320a3-219">Поддерживаемые подстановочные знаки могут различаться в зависимости от базового API или поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="320a3-219">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="320a3-220">Дополнительные сведения см. в разделе [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-220">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="320a3-221">Атрибуты проверки параметров и переменных</span><span class="sxs-lookup"><span data-stu-id="320a3-221">Parameter and variable validation attributes</span></span>

<span data-ttu-id="320a3-222">Атрибуты проверки Direct PowerShell для проверки значений параметров, отправляемых пользователями при вызове расширенной функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-222">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="320a3-223">Если значения параметров не прошли проверку, создается ошибка и функция не вызывается.</span><span class="sxs-lookup"><span data-stu-id="320a3-223">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="320a3-224">Проверка параметров применяется только к предоставленным входным данным, а любые другие значения, такие как значения по умолчанию, не проверяются.</span><span class="sxs-lookup"><span data-stu-id="320a3-224">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="320a3-225">Можно также использовать атрибуты проверки, чтобы ограничить значения, которые пользователи могут указывать для переменных.</span><span class="sxs-lookup"><span data-stu-id="320a3-225">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="320a3-226">При использовании преобразователя типов вместе с атрибутом проверки преобразователь типов должен быть определен перед атрибутом.</span><span class="sxs-lookup"><span data-stu-id="320a3-226">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="320a3-227">Атрибут проверки AllowNull</span><span class="sxs-lookup"><span data-stu-id="320a3-227">AllowNull validation attribute</span></span>

<span data-ttu-id="320a3-228">Атрибут **AllowNull** допускает значение обязательного параметра `$null` .</span><span class="sxs-lookup"><span data-stu-id="320a3-228">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="320a3-229">В следующем примере объявляется параметр **компутеринфо** Hashtable, который может иметь значение **null** .</span><span class="sxs-lookup"><span data-stu-id="320a3-229">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="320a3-230">Атрибут **AllowNull** не работает, если преобразователь типов имеет значение String, так как тип строки не принимает значение null.</span><span class="sxs-lookup"><span data-stu-id="320a3-230">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="320a3-231">Для этого сценария можно использовать атрибут **алловемптистринг** .</span><span class="sxs-lookup"><span data-stu-id="320a3-231">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="320a3-232">Атрибут проверки Алловемптистринг</span><span class="sxs-lookup"><span data-stu-id="320a3-232">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="320a3-233">Атрибут **алловемптистринг** позволяет значению обязательного параметра быть пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="320a3-233">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="320a3-234">В следующем примере объявляется параметр **ComputerName** , который может иметь пустое строковое значение.</span><span class="sxs-lookup"><span data-stu-id="320a3-234">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="320a3-235">Атрибут проверки Алловемптиколлектион</span><span class="sxs-lookup"><span data-stu-id="320a3-235">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="320a3-236">Атрибут **алловемптиколлектион** позволяет значению обязательного параметра быть пустой коллекцией `@()` .</span><span class="sxs-lookup"><span data-stu-id="320a3-236">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="320a3-237">В следующем примере объявляется параметр **ComputerName** , который может иметь пустое значение коллекции.</span><span class="sxs-lookup"><span data-stu-id="320a3-237">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="320a3-238">Атрибут проверки Валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="320a3-238">ValidateCount validation attribute</span></span>

<span data-ttu-id="320a3-239">Атрибут **валидатекаунт** указывает минимальное и максимальное число значений параметров, принимаемых параметром.</span><span class="sxs-lookup"><span data-stu-id="320a3-239">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="320a3-240">PowerShell выдает ошибку, если число значений параметров в команде, вызывающей функцию, находится за пределами этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="320a3-240">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="320a3-241">Приведенное ниже объявление параметра создает параметр **ComputerName** , который принимает от одного до пяти значений параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-241">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="320a3-242">Атрибут проверки Валидателенгс</span><span class="sxs-lookup"><span data-stu-id="320a3-242">ValidateLength validation attribute</span></span>

<span data-ttu-id="320a3-243">Атрибут **валидателенгс** указывает минимальное и максимальное число символов в значении параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="320a3-243">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="320a3-244">PowerShell выдает ошибку, если длина значения, указанного для параметра или переменной, находится за пределами диапазона.</span><span class="sxs-lookup"><span data-stu-id="320a3-244">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="320a3-245">В следующем примере имя каждого компьютера должно содержать от 1 до десяти символов.</span><span class="sxs-lookup"><span data-stu-id="320a3-245">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="320a3-246">В следующем примере значение переменной `$number` должно быть как минимум одним символом в длину и не более десяти символов.</span><span class="sxs-lookup"><span data-stu-id="320a3-246">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="320a3-247">В этом примере значение `01` заключено в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="320a3-247">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="320a3-248">Атрибут **валидателенгс** не принимает число без заключения в кавычки.</span><span class="sxs-lookup"><span data-stu-id="320a3-248">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="320a3-249">Атрибут проверки ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="320a3-249">ValidatePattern validation attribute</span></span>

<span data-ttu-id="320a3-250">Атрибут **ValidatePattern** указывает регулярное выражение, которое сравнивается с параметром или значением переменной.</span><span class="sxs-lookup"><span data-stu-id="320a3-250">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="320a3-251">PowerShell выдает ошибку, если значение не соответствует шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="320a3-251">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="320a3-252">В следующем примере значение параметра должно содержать четырехзначное число, а каждая цифра должна быть числом от 0 до девяти.</span><span class="sxs-lookup"><span data-stu-id="320a3-252">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="320a3-253">В следующем примере значение переменной `$number` должно быть ровно четырехзначным числом, а каждая цифра должна быть числом от 0 до девяти.</span><span class="sxs-lookup"><span data-stu-id="320a3-253">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="320a3-254">Атрибут проверки Валидатеранже</span><span class="sxs-lookup"><span data-stu-id="320a3-254">ValidateRange validation attribute</span></span>

<span data-ttu-id="320a3-255">Атрибут **валидатеранже** задает числовой диапазон для каждого значения параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="320a3-255">The **ValidateRange** attribute specifies a numeric range for each parameter or variable value.</span></span> <span data-ttu-id="320a3-256">PowerShell выдает ошибку, если какое-либо значение выходит за пределы этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="320a3-256">PowerShell generates an error if any value is outside that range.</span></span> <span data-ttu-id="320a3-257">В следующем примере значение параметра **попыток** должно находиться в диапазоне от 0 до десяти.</span><span class="sxs-lookup"><span data-stu-id="320a3-257">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="320a3-258">В следующем примере значение переменной `$number` должно находиться в диапазоне от 0 до десяти.</span><span class="sxs-lookup"><span data-stu-id="320a3-258">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="320a3-259">Атрибут проверки Валидатескрипт</span><span class="sxs-lookup"><span data-stu-id="320a3-259">ValidateScript validation attribute</span></span>

<span data-ttu-id="320a3-260">Атрибут **валидатескрипт** указывает скрипт, используемый для проверки значения параметра или переменной.</span><span class="sxs-lookup"><span data-stu-id="320a3-260">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="320a3-261">PowerShell передает значение в скрипт и выдает ошибку, если скрипт возвращает `$false` или вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="320a3-261">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="320a3-262">При использовании атрибута **валидатескрипт** проверяемое значение сопоставляется с `$_` переменной.</span><span class="sxs-lookup"><span data-stu-id="320a3-262">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="320a3-263">Переменную можно использовать `$_` для ссылки на значение в скрипте.</span><span class="sxs-lookup"><span data-stu-id="320a3-263">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="320a3-264">В следующем примере значение параметра **евентдате** должно быть больше или равно текущей дате.</span><span class="sxs-lookup"><span data-stu-id="320a3-264">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="320a3-265">В следующем примере значение переменной `$date` должно быть больше текущей даты и времени или равно ей.</span><span class="sxs-lookup"><span data-stu-id="320a3-265">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="320a3-266">При использовании **валидатескрипт** нельзя передавать `$null` значение в параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-266">If you use **ValidateScript** , you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="320a3-267">При передаче значения NULL **валидатескрипт** не может проверить аргумент.</span><span class="sxs-lookup"><span data-stu-id="320a3-267">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="320a3-268">Атрибут "Validate"</span><span class="sxs-lookup"><span data-stu-id="320a3-268">ValidateSet attribute</span></span>

<span data-ttu-id="320a3-269">Атрибут **Validate** задает набор допустимых значений для параметра или переменной и включает Заполнение клавишей TAB.</span><span class="sxs-lookup"><span data-stu-id="320a3-269">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="320a3-270">PowerShell выдает ошибку, если значение параметра или переменной не соответствует значению в наборе.</span><span class="sxs-lookup"><span data-stu-id="320a3-270">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="320a3-271">В следующем примере значение параметра **detail** может быть только низким, средним или высоким.</span><span class="sxs-lookup"><span data-stu-id="320a3-271">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="320a3-272">В следующем примере значение переменной `$flavor` должно быть шоколадным, Strawberry или обычный.</span><span class="sxs-lookup"><span data-stu-id="320a3-272">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="320a3-273">Проверка выполняется каждый раз, когда переменная присваивается даже внутри скрипта.</span><span class="sxs-lookup"><span data-stu-id="320a3-273">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="320a3-274">Например, следующее приводит к ошибке во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="320a3-274">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="320a3-275">Атрибут проверки Валидатенотнулл</span><span class="sxs-lookup"><span data-stu-id="320a3-275">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="320a3-276">Атрибут **валидатенотнулл** указывает, что значение параметра не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="320a3-276">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="320a3-277">PowerShell выдает ошибку, если параметр имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="320a3-277">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="320a3-278">Атрибут **валидатенотнулл** предназначен для использования, если параметр является необязательным и тип не определен или имеет преобразователь типов, который не может неявно преобразовать значение null, например **Object**.</span><span class="sxs-lookup"><span data-stu-id="320a3-278">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object**.</span></span> <span data-ttu-id="320a3-279">Если указать тип, который будет неявно преобразовывать значение null, например **строку** , значение NULL преобразуется в пустую строку даже при использовании атрибута **валидатенотнулл** .</span><span class="sxs-lookup"><span data-stu-id="320a3-279">If you specify a type that that will implicitly convert a null value such as a **string** , the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="320a3-280">Для этого сценария используйте **валидатенотнуллоремпти**</span><span class="sxs-lookup"><span data-stu-id="320a3-280">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="320a3-281">В следующем примере значение параметра **ID** не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="320a3-281">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="320a3-282">Атрибут проверки Валидатенотнуллоремпти</span><span class="sxs-lookup"><span data-stu-id="320a3-282">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="320a3-283">Атрибут **валидатенотнуллоремпти** указывает, что значение параметра не может быть `$null` пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="320a3-283">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="320a3-284">PowerShell выдает ошибку, если параметр используется в вызове функции, но имеет значение `$null` , пустую строку ( `""` ) или пустой массив `@()` .</span><span class="sxs-lookup"><span data-stu-id="320a3-284">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="320a3-285">Атрибут проверки Валидатедриве</span><span class="sxs-lookup"><span data-stu-id="320a3-285">ValidateDrive validation attribute</span></span>

<span data-ttu-id="320a3-286">Атрибут **валидатедриве** указывает, что значение параметра должно представлять путь, который ссылается только на разрешенные диски.</span><span class="sxs-lookup"><span data-stu-id="320a3-286">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="320a3-287">PowerShell выдает ошибку, если значение параметра относится к дискам, отличным от разрешенного.</span><span class="sxs-lookup"><span data-stu-id="320a3-287">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="320a3-288">Наличие пути, за исключением самого диска, не проверяется.</span><span class="sxs-lookup"><span data-stu-id="320a3-288">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="320a3-289">Если используется относительный путь, текущий диск должен находиться в списке разрешенных дисков.</span><span class="sxs-lookup"><span data-stu-id="320a3-289">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="320a3-290">Атрибут проверки Валидатеусердриве</span><span class="sxs-lookup"><span data-stu-id="320a3-290">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="320a3-291">Атрибут **валидатеусердриве** указывает, что значение параметра должно представлять путь, который ссылается на `User` диск.</span><span class="sxs-lookup"><span data-stu-id="320a3-291">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="320a3-292">PowerShell выдает ошибку, если путь ссылается на другой диск.</span><span class="sxs-lookup"><span data-stu-id="320a3-292">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="320a3-293">Атрибут проверки проверяет только наличие части пути, которая является диском.</span><span class="sxs-lookup"><span data-stu-id="320a3-293">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="320a3-294">Если используется относительный путь, то текущий диск должен быть `User` .</span><span class="sxs-lookup"><span data-stu-id="320a3-294">If you use relative path, the current drive must be `User`.</span></span>

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

<span data-ttu-id="320a3-295">Вы можете определить `User` диск в достаточном объеме конфигураций сеансов администрирования (JEA).</span><span class="sxs-lookup"><span data-stu-id="320a3-295">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="320a3-296">В этом примере мы создадим диск User:.</span><span class="sxs-lookup"><span data-stu-id="320a3-296">For this example, we create the User: drive.</span></span>

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

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="320a3-297">Атрибут проверки Валидатетрустеддата</span><span class="sxs-lookup"><span data-stu-id="320a3-297">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="320a3-298">Этот атрибут был добавлен в 6.1.1 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="320a3-298">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="320a3-299">В настоящее время атрибут используется внутри самой PowerShell и не предназначен для внешнего использования.</span><span class="sxs-lookup"><span data-stu-id="320a3-299">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="320a3-300">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="320a3-300">Dynamic parameters</span></span>

<span data-ttu-id="320a3-301">Динамические параметры — это параметры командлета, функции или скрипта, доступные только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="320a3-301">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="320a3-302">Например, несколько командлетов поставщика имеют параметры, доступные только при использовании командлета на диске поставщика или в определенном пути к диску поставщика.</span><span class="sxs-lookup"><span data-stu-id="320a3-302">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="320a3-303">Например, параметр **Encoding** доступен для `Add-Content` `Get-Content` командлетов, и, `Set-Content` только если он используется на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="320a3-303">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="320a3-304">Можно также создать параметр, который появляется только в том случае, если другой параметр используется в команде функции или если другой параметр имеет определенное значение.</span><span class="sxs-lookup"><span data-stu-id="320a3-304">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="320a3-305">Динамические параметры могут быть полезными, но их следует использовать только при необходимости, так как пользователям может быть трудно обнаружить.</span><span class="sxs-lookup"><span data-stu-id="320a3-305">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="320a3-306">Чтобы найти динамический параметр, пользователь должен быть в пути поставщика, использовать параметр **ArgumentList** `Get-Command` командлета или использовать параметр **path** в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="320a3-306">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="320a3-307">Чтобы создать динамический параметр для функции или скрипта, используйте `DynamicParam` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="320a3-307">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="320a3-308">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="320a3-308">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="320a3-309">В списке инструкций используйте `If` оператор, чтобы указать условия, при которых параметр доступен в функции.</span><span class="sxs-lookup"><span data-stu-id="320a3-309">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="320a3-310">Используйте `New-Object` командлет, чтобы создать объект **System. Management. Automation. рунтимедефинедпараметер** для представления параметра и указать его имя.</span><span class="sxs-lookup"><span data-stu-id="320a3-310">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="320a3-311">Вы можете использовать `New-Object` команду, чтобы создать объект **System. Management. Automation. параметераттрибуте** для представления атрибутов параметра, например **обязательный** , параметр " **Расположение** " или " **валуефромпипелине** " или набор параметров.</span><span class="sxs-lookup"><span data-stu-id="320a3-311">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory** , **Position** , or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="320a3-312">В следующем примере показан пример функции со стандартными параметрами **Name** и **path** и необязательным динамическим параметром с именем **DP1**.</span><span class="sxs-lookup"><span data-stu-id="320a3-312">The following example shows a sample function with standard parameters named **Name** and **Path** , and an optional dynamic parameter named **DP1**.</span></span> <span data-ttu-id="320a3-313">Параметр **DP1** находится в `PSet1` наборе параметров и имеет тип `Int32` .</span><span class="sxs-lookup"><span data-stu-id="320a3-313">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="320a3-314">Параметр **DP1** доступен в `Get-Sample` функции только в том случае, если значение параметра **path** начинается с `HKLM:` , что указывает на то, что он используется на `HKEY_LOCAL_MACHINE` диске реестра.</span><span class="sxs-lookup"><span data-stu-id="320a3-314">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

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

<span data-ttu-id="320a3-315">Дополнительные сведения см. в разделе [рунтимедефинедпараметер](/dotnet/api/system.management.automation.runtimedefinedparameter).</span><span class="sxs-lookup"><span data-stu-id="320a3-315">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="320a3-316">Параметры-переключатели</span><span class="sxs-lookup"><span data-stu-id="320a3-316">Switch parameters</span></span>

<span data-ttu-id="320a3-317">Параметры переключателей — это параметры без значения параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-317">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="320a3-318">Они вступают в силу только в том случае, если они используются и имеют только один результат.</span><span class="sxs-lookup"><span data-stu-id="320a3-318">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="320a3-319">Например, параметром **Parameter параметра** **powershell.exe** является параметр Switch.</span><span class="sxs-lookup"><span data-stu-id="320a3-319">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="320a3-320">Чтобы создать параметр переключателя в функции, укажите `Switch` тип в определении параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-320">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="320a3-321">Пример:</span><span class="sxs-lookup"><span data-stu-id="320a3-321">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="320a3-322">Кроме того, можно использовать другой метод:</span><span class="sxs-lookup"><span data-stu-id="320a3-322">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="320a3-323">Параметры переключателей просты в использовании и являются предпочтительными по сравнению с логическими параметрами, которые имеют более сложный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="320a3-323">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="320a3-324">Например, чтобы использовать параметр Switch, пользователь вводит параметр в команду.</span><span class="sxs-lookup"><span data-stu-id="320a3-324">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="320a3-325">Чтобы использовать логический параметр, пользователь вводит параметр и логическое значение.</span><span class="sxs-lookup"><span data-stu-id="320a3-325">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="320a3-326">При создании параметров переключателя следует тщательно выбирать имя параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-326">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="320a3-327">Убедитесь, что имя параметра передает пользователю результат параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-327">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="320a3-328">Избегайте неоднозначных терминов, таких как **Фильтр** или **Максимальное** значение, которое может требовать значения.</span><span class="sxs-lookup"><span data-stu-id="320a3-328">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="320a3-329">Атрибут Аргументкомплетер</span><span class="sxs-lookup"><span data-stu-id="320a3-329">ArgumentCompleter attribute</span></span>

<span data-ttu-id="320a3-330">Атрибут **аргументкомплетер** позволяет добавлять значения заполнения клавишей TAB в конкретный параметр.</span><span class="sxs-lookup"><span data-stu-id="320a3-330">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="320a3-331">Атрибут **аргументкомплетер** должен быть определен для каждого параметра, для которого требуется заполнение по клавише TAB.</span><span class="sxs-lookup"><span data-stu-id="320a3-331">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="320a3-332">Как и в случае с **DynamicParameters** , доступные значения рассчитываются во время выполнения, когда пользователь нажимает клавишу <kbd>Tab</kbd> после имени параметра.</span><span class="sxs-lookup"><span data-stu-id="320a3-332">Similar to **DynamicParameters** , the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="320a3-333">Чтобы добавить атрибут **аргументкомплетер** , необходимо определить блок скрипта, который определяет значения.</span><span class="sxs-lookup"><span data-stu-id="320a3-333">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="320a3-334">Блок скрипта должен принимать следующие параметры в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="320a3-334">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="320a3-335">Имена параметров не важны, так как значения указаны по положению.</span><span class="sxs-lookup"><span data-stu-id="320a3-335">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="320a3-336">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="320a3-336">The syntax is as follows:</span></span>

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

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="320a3-337">Блок сценария Аргументкомплетер</span><span class="sxs-lookup"><span data-stu-id="320a3-337">ArgumentCompleter script block</span></span>

<span data-ttu-id="320a3-338">Для параметров блока сценария задаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="320a3-338">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="320a3-339">`$commandName` (Расположение 0) — Этот параметр задает имя команды, для которой блок скрипта обеспечивает заполнение нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="320a3-339">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="320a3-340">`$parameterName` (Расположение 1) — Этот параметр задан для параметра, значение которого требует заполнения нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="320a3-340">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="320a3-341">`$wordToComplete` (Расположение 2) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="320a3-341">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="320a3-342">`$commandAst` (Расположение 3) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки.</span><span class="sxs-lookup"><span data-stu-id="320a3-342">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="320a3-343">Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="320a3-343">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="320a3-344">`$fakeBoundParameters` (Расположение 4) — для этого параметра задается хэш-таблица `$PSBoundParameters` , содержащая для командлета перед нажатием пользователем <kbd>вкладки</kbd>. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="320a3-344">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="320a3-345">Блок скрипта **аргументкомплетер** должен выполнить девращение значений с помощью конвейера, например `ForEach-Object` , `Where-Object` или другого подходящего метода.</span><span class="sxs-lookup"><span data-stu-id="320a3-345">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="320a3-346">Возврат массива значений приводит к тому, что PowerShell обрабатывает весь массив как **одно** значение заполнения Tab.</span><span class="sxs-lookup"><span data-stu-id="320a3-346">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="320a3-347">В следующем примере заполнение клавиши TAB добавляется в параметр **value** .</span><span class="sxs-lookup"><span data-stu-id="320a3-347">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="320a3-348">Если указан только параметр **value** , отображаются все возможные значения или аргументы для **параметра значение** .</span><span class="sxs-lookup"><span data-stu-id="320a3-348">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="320a3-349">Если указан параметр **типа** , параметр **value** отображает только возможные значения для этого типа.</span><span class="sxs-lookup"><span data-stu-id="320a3-349">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="320a3-350">Кроме того, `-like` оператор гарантирует, что если пользователь вводит следующую команду и использует заполнение по <kbd>клавише TAB</kbd> , возвращается только **Apple** .</span><span class="sxs-lookup"><span data-stu-id="320a3-350">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="320a3-351">См. также статью</span><span class="sxs-lookup"><span data-stu-id="320a3-351">See also</span></span>

[<span data-ttu-id="320a3-352">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="320a3-352">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="320a3-353">about_Functions</span><span class="sxs-lookup"><span data-stu-id="320a3-353">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="320a3-354">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="320a3-354">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="320a3-355">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="320a3-355">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="320a3-356">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="320a3-356">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="320a3-357">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="320a3-357">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

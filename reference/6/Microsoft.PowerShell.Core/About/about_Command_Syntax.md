---
description: Описывает схемы синтаксиса, используемые в PowerShell.
keywords: powershell,командлет
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 33692eebab41e20bd85eb447cc66f1ff592977ef
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231546"
---
# <a name="about-command-syntax"></a><span data-ttu-id="dff71-104">О синтаксисе команд</span><span class="sxs-lookup"><span data-stu-id="dff71-104">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="dff71-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="dff71-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="dff71-106">Описывает схемы синтаксиса, используемые в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dff71-106">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="dff71-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="dff71-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="dff71-108">Командлеты [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) и [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) отображают схемы синтаксиса, помогающие правильно создавать команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-108">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="dff71-109">В этом разделе объясняется, как интерпретировать схемы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dff71-109">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="dff71-110">СХЕМЫ СИНТАКСИСА</span><span class="sxs-lookup"><span data-stu-id="dff71-110">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="dff71-111">Каждый абзац на схеме синтаксиса команд представляет допустимую форму команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-111">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="dff71-112">Чтобы создать команду, следуйте схеме синтаксиса слева направо.</span><span class="sxs-lookup"><span data-stu-id="dff71-112">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="dff71-113">Выберите из необязательных параметров и укажите значения для заполнителей.</span><span class="sxs-lookup"><span data-stu-id="dff71-113">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="dff71-114">PowerShell использует следующую нотацию для схем синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dff71-114">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="dff71-115">Ниже приведен синтаксис командлета [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .</span><span class="sxs-lookup"><span data-stu-id="dff71-115">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="dff71-116">Синтаксис задается прописными буквами для удобства чтения, но в PowerShell регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="dff71-116">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="dff71-117">Схема синтаксиса содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="dff71-117">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="dff71-118">Имя команды</span><span class="sxs-lookup"><span data-stu-id="dff71-118">Command name</span></span>

<span data-ttu-id="dff71-119">Команды всегда начинаются с имени команды, например `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="dff71-119">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="dff71-120">Введите имя команды или ее псевдоним, например "gcm" для `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="dff71-120">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="dff71-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="dff71-121">Parameters</span></span>

<span data-ttu-id="dff71-122">Параметры команды — это параметры, определяющие действие команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-122">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="dff71-123">Некоторые параметры принимают значение "value", которое является входным пользователем для команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-123">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="dff71-124">Например, `Get-Help` команда имеет параметр **Name** , который позволяет указать имя раздела, для которого отображается справка.</span><span class="sxs-lookup"><span data-stu-id="dff71-124">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="dff71-125">Имя раздела — это значение параметра **Name** .</span><span class="sxs-lookup"><span data-stu-id="dff71-125">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="dff71-126">В команде PowerShell имена параметров всегда начинаются с дефиса.</span><span class="sxs-lookup"><span data-stu-id="dff71-126">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="dff71-127">Дефис сообщает PowerShell, что элемент в команде является именем параметра.</span><span class="sxs-lookup"><span data-stu-id="dff71-127">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="dff71-128">Например, чтобы использовать параметр Name параметра `New-Alias` , введите следующее:</span><span class="sxs-lookup"><span data-stu-id="dff71-128">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="dff71-129">Параметры могут быть обязательными или необязательными.</span><span class="sxs-lookup"><span data-stu-id="dff71-129">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="dff71-130">В схеме синтаксиса необязательные элементы заключаются в квадратные скобки `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="dff71-130">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="dff71-131">Дополнительные сведения о параметрах см. в разделе [about_Parameters](about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="dff71-131">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="dff71-132">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="dff71-132">Parameter Values</span></span>

<span data-ttu-id="dff71-133">Значение параметра — это входные данные, которые принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="dff71-133">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="dff71-134">Поскольку оболочка Windows PowerShell основана на Microsoft .NET Framework, значения параметров представлены на схеме синтаксиса по типу .NET.</span><span class="sxs-lookup"><span data-stu-id="dff71-134">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="dff71-135">Например, параметр name `Get-Help` принимает значение «String», представляющее собой текстовую строку, например одно слово или несколько слов, заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="dff71-135">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="dff71-136">Тип .NET значения параметра заключен в угловые скобки `< >` , чтобы указать, что он является заполнителем для значения, а не литералом, введенным в команде.</span><span class="sxs-lookup"><span data-stu-id="dff71-136">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="dff71-137">Чтобы использовать параметр, замените заполнитель типа .NET объектом с указанным типом .NET.</span><span class="sxs-lookup"><span data-stu-id="dff71-137">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="dff71-138">Например, чтобы использовать параметр **Name** , введите "-Name", а затем строку, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dff71-138">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="dff71-139">Параметры без значений</span><span class="sxs-lookup"><span data-stu-id="dff71-139">Parameters with no values</span></span>

<span data-ttu-id="dff71-140">Некоторые параметры не принимают входные данные, поэтому они не имеют значения параметра.</span><span class="sxs-lookup"><span data-stu-id="dff71-140">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="dff71-141">Параметры без значений называются параметрами-переключателями, так как они работают как параметры on/off.</span><span class="sxs-lookup"><span data-stu-id="dff71-141">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="dff71-142">Вы включаете их (on) или не пропускаете их (OFF) из команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-142">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="dff71-143">Чтобы использовать параметр Switch, просто введите имя параметра, перед которым следует дефис.</span><span class="sxs-lookup"><span data-stu-id="dff71-143">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="dff71-144">Например, чтобы использовать параметр **WhatIf** `New-Alias` командлета, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="dff71-144">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="dff71-145">Наборы параметров</span><span class="sxs-lookup"><span data-stu-id="dff71-145">Parameter Sets</span></span>

<span data-ttu-id="dff71-146">Параметры команды перечислены в наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-146">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="dff71-147">Наборы параметров выглядят как абзацы схемы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dff71-147">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="dff71-148">`New-Alias`Командлет имеет один набор параметров, но многие командлеты имеют несколько наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-148">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="dff71-149">Некоторые параметры командлета уникальны для набора параметров, а другие — в нескольких наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-149">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="dff71-150">Каждый набор параметров представляет формат допустимой команды.</span><span class="sxs-lookup"><span data-stu-id="dff71-150">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="dff71-151">Набор параметров включает в себя только параметры, которые можно использовать вместе в команде.</span><span class="sxs-lookup"><span data-stu-id="dff71-151">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="dff71-152">Если параметры не могут использоваться в одной команде, они отображаются в отдельных наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-152">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="dff71-153">Например, командлет [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) имеет следующие наборы параметров:</span><span class="sxs-lookup"><span data-stu-id="dff71-153">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="dff71-154">Первый набор параметров, который возвращает случайное число, имеет **минимальные** и **максимальные** параметры.</span><span class="sxs-lookup"><span data-stu-id="dff71-154">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="dff71-155">Второй набор параметров, который возвращает случайно выбранный объект из набора объектов, включает параметры **InputObject** и **Count** .</span><span class="sxs-lookup"><span data-stu-id="dff71-155">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="dff71-156">Оба набора параметров имеют параметр **SetSeed** и общие параметры.</span><span class="sxs-lookup"><span data-stu-id="dff71-156">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="dff71-157">Эти наборы параметров указывают, что можно использовать параметры **InputObject** и **Count** в одной команде, но нельзя использовать параметры **Maximum** и **Count** в одной и той же команде.</span><span class="sxs-lookup"><span data-stu-id="dff71-157">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="dff71-158">Вы указываете, какой набор параметров следует использовать, с помощью параметров в этом наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-158">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="dff71-159">Однако у каждого командлета также есть набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dff71-159">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="dff71-160">Набор параметров по умолчанию используется, если не указаны параметры, уникальные для набора параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-160">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="dff71-161">Например, если вы используете `Get-Random` без параметров, Windows PowerShell предполагает, что вы используете набор **числовых** параметров и возвращает случайное число.</span><span class="sxs-lookup"><span data-stu-id="dff71-161">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="dff71-162">В каждом наборе параметров параметры отображаются в порядке расположения.</span><span class="sxs-lookup"><span data-stu-id="dff71-162">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="dff71-163">Порядок параметров в команде имеет значение только в том случае, если не заданы имена необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-163">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="dff71-164">Если имена параметров опущены, PowerShell присваивает значения параметрам по положению и типу.</span><span class="sxs-lookup"><span data-stu-id="dff71-164">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="dff71-165">Дополнительные сведения о положении параметра см. в разделе `about_Parameters` .</span><span class="sxs-lookup"><span data-stu-id="dff71-165">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="dff71-166">Символы в схемах синтаксиса</span><span class="sxs-lookup"><span data-stu-id="dff71-166">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="dff71-167">На схеме синтаксиса перечислены имя команды, параметры команды и значения параметров.</span><span class="sxs-lookup"><span data-stu-id="dff71-167">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="dff71-168">В нем также используются символы, чтобы продемонстрировать, как создать допустимую команду.</span><span class="sxs-lookup"><span data-stu-id="dff71-168">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="dff71-169">Схемы синтаксиса используют следующие символы:</span><span class="sxs-lookup"><span data-stu-id="dff71-169">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="dff71-170">Дефис `-` обозначает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="dff71-170">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="dff71-171">В команде введите дефис непосредственно перед именем параметра без промежуточных пробелов, как показано на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dff71-171">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="dff71-172">Например, чтобы использовать параметр **Name** типа `New-Alias` , введите:</span><span class="sxs-lookup"><span data-stu-id="dff71-172">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="dff71-173">Угловые скобки `<>` обозначают текст заполнителя.</span><span class="sxs-lookup"><span data-stu-id="dff71-173">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="dff71-174">В команде не вводите угловые скобки или текст заполнителя.</span><span class="sxs-lookup"><span data-stu-id="dff71-174">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="dff71-175">Вместо этого замените его элементом, который он описывает.</span><span class="sxs-lookup"><span data-stu-id="dff71-175">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="dff71-176">Угловые скобки используются для задания типа .NET значения, принимаемого параметром.</span><span class="sxs-lookup"><span data-stu-id="dff71-176">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="dff71-177">Например, чтобы использовать параметр **Name** `New-Alias` командлета, замените на `<string>` строку, представляющую собой одно слово или группу слов, заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="dff71-177">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="dff71-178">Квадратные скобки `[ ]` обозначают необязательные элементы.</span><span class="sxs-lookup"><span data-stu-id="dff71-178">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="dff71-179">Параметр и его значение могут быть необязательными, или имя обязательного параметра может быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="dff71-179">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="dff71-180">Например, параметр **Description** аргумента `New-Alias` и его значение заключаются в квадратные скобки, так как они являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="dff71-180">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="dff71-181">Квадратные скобки также указывают, что значение параметра name `<string>` является обязательным, но имя параметра "имя" является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dff71-181">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="dff71-182">Правая и левая скобки, `[]` добавленные к типу .NET, указывают на то, что параметр может принимать одно или несколько значений этого типа.</span><span class="sxs-lookup"><span data-stu-id="dff71-182">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="dff71-183">Введите значения в список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="dff71-183">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="dff71-184">Например, параметр **Name** `New-Alias` командлета принимает только одну строку, но параметр **Name** для [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) может принимать одну или несколько строк.</span><span class="sxs-lookup"><span data-stu-id="dff71-184">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="dff71-185">Фигурные скобки `{}` обозначают "перечисление", которое представляет собой набор допустимых значений для параметра.</span><span class="sxs-lookup"><span data-stu-id="dff71-185">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="dff71-186">Значения в фигурных скобках разделяются вертикальными линиями `|` .</span><span class="sxs-lookup"><span data-stu-id="dff71-186">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="dff71-187">Эти строки указывают на «эксклюзивный» выбор, что означает, что можно выбрать только одно значение из набора значений, перечисленных внутри фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="dff71-187">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="dff71-188">Например, синтаксис для `New-Alias` командлета включает следующее перечисление значений для параметра **Option** :</span><span class="sxs-lookup"><span data-stu-id="dff71-188">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="dff71-189">Фигурные скобки и вертикальные линии указывают, что можно выбрать одно из перечисленных значений **для параметра параметра** , например "ReadOnly" или "AllScope".</span><span class="sxs-lookup"><span data-stu-id="dff71-189">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="dff71-190">Необязательные элементы</span><span class="sxs-lookup"><span data-stu-id="dff71-190">Optional Items</span></span>

<span data-ttu-id="dff71-191">Необязательные элементы заключены в квадратные скобки `[]` .</span><span class="sxs-lookup"><span data-stu-id="dff71-191">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="dff71-192">Например, в `New-Alias` описании синтаксиса командлета параметр **Scope** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dff71-192">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="dff71-193">Это указывается в синтаксисе квадратными скобками вокруг имени параметра и типа:</span><span class="sxs-lookup"><span data-stu-id="dff71-193">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="dff71-194">Ниже приведены правильные примеры использования `New-Alias` командлета.</span><span class="sxs-lookup"><span data-stu-id="dff71-194">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="dff71-195">Имя параметра может быть необязательным, даже если значение для этого параметра является обязательным.</span><span class="sxs-lookup"><span data-stu-id="dff71-195">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="dff71-196">Это указывается в синтаксисе квадратными скобками вокруг имени параметра, но не типа параметра, как в этом примере из `New-Alias` командлета:</span><span class="sxs-lookup"><span data-stu-id="dff71-196">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="dff71-197">Следующие команды правильно используют `New-Alias` командлет.</span><span class="sxs-lookup"><span data-stu-id="dff71-197">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="dff71-198">Эти команды дают тот же результат.</span><span class="sxs-lookup"><span data-stu-id="dff71-198">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="dff71-199">Если имя параметра не включено в инструкцию как типизированное, Windows PowerShell пытается использовать расположение аргументов для присвоения значений параметрам.</span><span class="sxs-lookup"><span data-stu-id="dff71-199">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="dff71-200">Следующий пример не завершен:</span><span class="sxs-lookup"><span data-stu-id="dff71-200">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="dff71-201">Для этого командлета требуются значения как для параметров **имени** , так и для **значения** .</span><span class="sxs-lookup"><span data-stu-id="dff71-201">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="dff71-202">В примерах синтаксиса скобки также используются при именовании и приведении к типам .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dff71-202">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="dff71-203">В этом контексте квадратные скобки не указывают, что элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dff71-203">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="dff71-204">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="dff71-204">SEE ALSO</span></span>

- [<span data-ttu-id="dff71-205">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="dff71-205">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="dff71-206">Get-Command</span><span class="sxs-lookup"><span data-stu-id="dff71-206">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="dff71-207">Get-Help</span><span class="sxs-lookup"><span data-stu-id="dff71-207">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Получение подробной справки
ms.assetid: 6fb4daf7-8607-4a3e-b692-f77631adc1b9
ms.openlocfilehash: 88f0357b935a7c75df07d667e3f2f2d0e493f89d
ms.sourcegitcommit: 59727f71dc204785a1bcdedc02716d8340a77aeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "43134040"
---
# <a name="getting-detailed-help-information"></a><span data-ttu-id="fd90e-103">Получение подробной справки</span><span class="sxs-lookup"><span data-stu-id="fd90e-103">Getting detailed help information</span></span>

<span data-ttu-id="fd90e-104">PowerShell содержит подробные статьи справки, объясняющие концепции и язык PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd90e-104">PowerShell includes detailed Help articles that explain PowerShell concepts and the PowerShell language.</span></span> <span data-ttu-id="fd90e-105">Статьи предоставляют сведения о каждом командлете и поставщике, а также многих функциях и скриптах.</span><span class="sxs-lookup"><span data-stu-id="fd90e-105">There are also Help articles for each cmdlet and provider and for many functions and scripts.</span></span>

<span data-ttu-id="fd90e-106">Эти статьи можно отобразить в интерфейсе командной строки или просмотреть их последние обновленные версии в онлайн-документации по [PowerShell](/powershell/scripting/powershell-scripting).</span><span class="sxs-lookup"><span data-stu-id="fd90e-106">You can display these Help articles at the command prompt or view the most recently updated versions of these articles in the [PowerShell](/powershell/scripting/powershell-scripting) documentation online.</span></span>

## <a name="getting-help-for-cmdlets"></a><span data-ttu-id="fd90e-107">Получение справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="fd90e-107">Getting help for cmdlets</span></span>

<span data-ttu-id="fd90e-108">Для получения справки по командлетам PowerShell используйте командлет [Get-Help](/powershell/module/microsoft.powershell.core/Get-Help).</span><span class="sxs-lookup"><span data-stu-id="fd90e-108">To get Help about PowerShell cmdlets, use the [Get-Help](/powershell/module/microsoft.powershell.core/Get-Help) cmdlet.</span></span> <span data-ttu-id="fd90e-109">Например, для получения справки по командлету `Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-109">For example, to get Help for the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="fd90e-110">или</span><span class="sxs-lookup"><span data-stu-id="fd90e-110">or</span></span>

```powershell
Get-ChildItem -?
```

<span data-ttu-id="fd90e-111">Справку можно получить и по самому командлету Get-Help.</span><span class="sxs-lookup"><span data-stu-id="fd90e-111">You can even get Help about the Get-Help cmdlet.</span></span> <span data-ttu-id="fd90e-112">Например:</span><span class="sxs-lookup"><span data-stu-id="fd90e-112">For example:</span></span>

```powershell
Get-Help Get-Help
```

<span data-ttu-id="fd90e-113">Чтобы отобразить список всех статей справки о командлетах в рамках текущего сеанса, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-113">To get a list of all the cmdlet Help articles in your session, type:</span></span>

```powershell
Get-Help -Category Cmdlet
```

<span data-ttu-id="fd90e-114">Чтобы отобразить каждую статью справки постранично, используйте функцию `help` или ее псевдоним `man`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-114">To display one page of each Help article at a time, use the `help` function or its alias `man`.</span></span>
<span data-ttu-id="fd90e-115">Например, чтобы отобразить справку по командлету `Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-115">For example, to display Help for the `Get-ChildItem` cmdlet, type</span></span>

```powershell
man Get-ChildItem
```

<span data-ttu-id="fd90e-116">или</span><span class="sxs-lookup"><span data-stu-id="fd90e-116">or</span></span>

```powershell
help Get-ChildItem
```

<span data-ttu-id="fd90e-117">Чтобы отобразить подробную информацию, используйте параметр **Detailed** командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-117">To display detailed information, use the **Detailed** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="fd90e-118">Например, чтобы получить подробные сведения о командлете `Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-118">For example, to get detailed information about the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Detailed
```

<span data-ttu-id="fd90e-119">Чтобы отобразить все содержимое статьи справки, используйте параметр **Full** командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-119">To display all content in the Help article, use the **Full** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="fd90e-120">Например, чтобы отобразить все содержимое статьи справки о командлете `Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-120">For example, to display all content in the Help article for the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Full
```

<span data-ttu-id="fd90e-121">Чтобы получить подробную справку по параметрам командлета, используйте параметр **Parameter** командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-121">To get detailed Help about the parameters of a cmdlet, use the **Parameter** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="fd90e-122">Например, чтобы получить подробную справку по всем параметрам командлета`Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-122">For example, to get detailed Help for all of the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Parameter *
```

<span data-ttu-id="fd90e-123">Чтобы отобразить только примеры из статьи справки, используйте параметр **Examples** командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-123">To display only the examples in a Help article, use the **Examples** parameter of the `Get-Help`.</span></span>
<span data-ttu-id="fd90e-124">Например, чтобы вывести только примеры из статьи справки о командлете`Get-ChildItem `, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-124">For example, to display only the examples in the Help article for the `Get-ChildItem `cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Examples
```

<span data-ttu-id="fd90e-125">Сведения о написании статей справки о командлетах см. в руководстве по [написанию справки по командлетам](/powershell/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="fd90e-125">For information about how to write Help articles for the cmdlets that you write, see [How to Write Cmdlet Help](/powershell/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="getting-conceptual-help"></a><span data-ttu-id="fd90e-126">Получение справки по концепциям</span><span class="sxs-lookup"><span data-stu-id="fd90e-126">Getting conceptual help</span></span>

<span data-ttu-id="fd90e-127">Командлет `Get-Help` также можно использовать для отображения статей справки по концепциям PowerShell, в том числе статей о языке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd90e-127">The `Get-Help` cmdlet also displays information about conceptual articles in PowerShell, including articles about the PowerShell language.</span></span> <span data-ttu-id="fd90e-128">Посвященные концепциям статьи справки начинаются с префикса about_, например about_line_editing.</span><span class="sxs-lookup"><span data-stu-id="fd90e-128">Conceptual Help articles begin with the "about_" prefix, such as about_line_editing.</span></span> <span data-ttu-id="fd90e-129">(Название статьи о концепциях нужно вводить на английском языке, даже если используется локализованная версия PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="fd90e-129">(The name of the conceptual article must be entered in English even on non-English versions of PowerShell.)</span></span>

<span data-ttu-id="fd90e-130">Для отображения списка статей о концепциях введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-130">To display a list of conceptual articles, type:</span></span>

```powershell
Get-Help about_*
```

<span data-ttu-id="fd90e-131">Для отображения определенной статьи справки введите название этой статьи, например:</span><span class="sxs-lookup"><span data-stu-id="fd90e-131">To display a particular Help article, type the article name, for example:</span></span>

```powershell
Get-Help about_command_syntax
```

<span data-ttu-id="fd90e-132">Параметры командлета `Get-Help`, например **Detailed**, **Parameter** и **Examples**, не влияют на отображение статей справки о концепциях.</span><span class="sxs-lookup"><span data-stu-id="fd90e-132">The parameters of `Get-Help`, such as **Detailed**, **Parameter**, and **Examples**, have no effect on the display of conceptual Help articles.</span></span>

## <a name="getting-help-about-providers"></a><span data-ttu-id="fd90e-133">Получение справки по поставщикам</span><span class="sxs-lookup"><span data-stu-id="fd90e-133">Getting help about providers</span></span>

<span data-ttu-id="fd90e-134">Командлет `Get-Help` позволяет получить информацию о поставщиках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd90e-134">The `Get-Help` cmdlet displays information about PowerShell providers.</span></span> <span data-ttu-id="fd90e-135">Чтобы получить справку по поставщику, введите команду `Get-Help` и имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="fd90e-135">To get Help for a provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="fd90e-136">Например, чтобы получить справку для поставщика Registry, введите:</span><span class="sxs-lookup"><span data-stu-id="fd90e-136">For example, to get Help for the Registry provider, type:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="fd90e-137">Чтобы отобразить список всех статей справки о поставщиках для текущего сеанса, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-137">To get a list of all the provider Help articles in your session, type</span></span>

```powershell
Get-Help -Category provider
```

<span data-ttu-id="fd90e-138">Параметры командлета `Get-Help`, например **Detailed**, **Parameter** и **Examples**, не влияют на отображение статей справки о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="fd90e-138">The parameters of `Get-Help`, such as **Detailed**, **Parameter**, and **Examples**, have no effect on the display of provider Help articles.</span></span>

## <a name="getting-help-about-scripts-and-functions"></a><span data-ttu-id="fd90e-139">Получение справки по скриптам и функциям</span><span class="sxs-lookup"><span data-stu-id="fd90e-139">Getting help about scripts and functions</span></span>

<span data-ttu-id="fd90e-140">Многим скриптам и функциям PowerShell посвящены отдельные статьи справки.</span><span class="sxs-lookup"><span data-stu-id="fd90e-140">Many scripts and functions in PowerShell have Help articles.</span></span> <span data-ttu-id="fd90e-141">Используйте командлет `Get-Help`, чтобы отобразить статьи справки о скриптах и функциях.</span><span class="sxs-lookup"><span data-stu-id="fd90e-141">Use the `Get-Help` cmdlet to display the Help articles for scripts and functions.</span></span>

<span data-ttu-id="fd90e-142">Чтобы получить справку по определенной функции, введите команду `Get-Help` и имя этой функции.</span><span class="sxs-lookup"><span data-stu-id="fd90e-142">To display the Help for a function, type `Get-Help` followed by the function name.</span></span> <span data-ttu-id="fd90e-143">Например, чтобы получить справку по функции `Disable-PSRemoting`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-143">For example, to get Help for the `Disable-PSRemoting` function, type:</span></span>

```powershell
Get-Help Disable-PSRemoting
```

<span data-ttu-id="fd90e-144">Чтобы получить справку по определенному скрипту, введите путь к файлу этого скрипта.</span><span class="sxs-lookup"><span data-stu-id="fd90e-144">To display the Help for a script, type the path to the script file.</span></span> <span data-ttu-id="fd90e-145">Если путь к скрипту не указан в переменной среды Path, необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="fd90e-145">If the script is not in a path listed in the Path environment variable, you must use the fully qualified path.</span></span>

<span data-ttu-id="fd90e-146">Например, если скрипт TestScript.ps1 находится в каталоге C:\\PS-Test, чтобы отобразить статью справки об этом скрипте, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-146">For example, if you have a script called "TestScript.ps1" in your C:\\PS-Test directory, to display the Help article for the script, type:</span></span>

```powershell
Get-Help c:\ps-test\TestScript.ps1
```

<span data-ttu-id="fd90e-147">Параметры отображения справки по командлетам также позволяют отображать справку по скриптам и функциям.</span><span class="sxs-lookup"><span data-stu-id="fd90e-147">The parameters that are designed for displaying cmdlet Help work for script and function Help, too.</span></span> <span data-ttu-id="fd90e-148">Справка по функциям и скриптам не выводится, если задана команда `Get-Help *`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-148">However, help for functions and scripts is not shown when you run `Get-Help *`.</span></span>

<span data-ttu-id="fd90e-149">См. дополнительные сведения о написании статей справки о функциях и скриптах:</span><span class="sxs-lookup"><span data-stu-id="fd90e-149">For information about writing Help articles for your functions and scripts, see the following articles:</span></span>

- [<span data-ttu-id="fd90e-150">about_Functions</span><span class="sxs-lookup"><span data-stu-id="fd90e-150">about_Functions</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions)
- [<span data-ttu-id="fd90e-151">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="fd90e-151">about_Scripts</span></span>](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [<span data-ttu-id="fd90e-152">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="fd90e-152">about_Comment_Based_Help</span></span>](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)

## <a name="getting-help-online"></a><span data-ttu-id="fd90e-153">Получение справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="fd90e-153">Getting help online</span></span>

<span data-ttu-id="fd90e-154">Лучше всего использовать интернет-версии статей справки.</span><span class="sxs-lookup"><span data-stu-id="fd90e-154">Viewing the Help articles online is one of the best ways to get help.</span></span> <span data-ttu-id="fd90e-155">Статьи в Интернете легко обновлять, поэтому в них содержится самая актуальная информация.</span><span class="sxs-lookup"><span data-stu-id="fd90e-155">Online articles are easier to update and provide the most current content.</span></span>

<span data-ttu-id="fd90e-156">Чтобы отобразить интернет-версию статьи справки используйте параметр **Online** командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fd90e-156">To get Help online, use the **Online** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="fd90e-157">Все статьи справки, содержащиеся в PowerShell, в том числе статьи справки о поставщиках и концепциях (About), можно найти в онлайн-документации по [PowerShell](/powershell/scripting/powershell-scripting).</span><span class="sxs-lookup"><span data-stu-id="fd90e-157">All the Help articles that come with PowerShell, including provider Help and conceptual (About) Help articles, are available online in the [PowerShell](/powershell/scripting/powershell-scripting) documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="fd90e-158">Параметр **Online** нельзя использовать для отображения статей справки о концепциях (about_\*) и поставщиках.</span><span class="sxs-lookup"><span data-stu-id="fd90e-158">You can't use the **Online** parameter with conceptual (about_\*) or provider Help articles.</span></span>
> <span data-ttu-id="fd90e-159">Статьи справки об отдельных командлетах, функциях и скриптах могут не иметь интернет-версий.</span><span class="sxs-lookup"><span data-stu-id="fd90e-159">Online help is optional, so it does not work for every cmdlet, function, or script.</span></span>

<span data-ttu-id="fd90e-160">Например, чтобы открыть интернет-версию статьи справки о командлете `Get-ChildItem`, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-160">For example, to get the online version of the Help article about the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Online
```

<span data-ttu-id="fd90e-161">PowerShell откроет статью в вашем браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd90e-161">PowerShell opens the article in your default browser.</span></span> <span data-ttu-id="fd90e-162">Если статья справки имеет интернет-версию, можно также узнать ее URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="fd90e-162">If online Help is supported for a Help article, you can also view the URL of the Help article.</span></span> <span data-ttu-id="fd90e-163">URL-адрес отображается в разделе со связанными ссылками в статье справки.</span><span class="sxs-lookup"><span data-stu-id="fd90e-163">The URL appears in the Related Links section of a Help article.</span></span>

<span data-ttu-id="fd90e-164">Например, чтобы посмотреть адрес интернет-версии командлета Add-Computer, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fd90e-164">For example, to see the URL for the online version of the Add-Computer cmdlet, type:</span></span>

```powershell
Get-Help Add-Computer
```

<span data-ttu-id="fd90e-165">Первая строка в разделе со связанными ссылками в статье показана ниже.</span><span class="sxs-lookup"><span data-stu-id="fd90e-165">The first line in the Related Links section of the article is shown below.</span></span>

```Output
Online version: http://go.microsoft.com/fwlink/?LinkId=821564
```

<span data-ttu-id="fd90e-166">Сведения об обеспечении интернет-поддержки собственных статей справки см. в разделе [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).</span><span class="sxs-lookup"><span data-stu-id="fd90e-166">For information about how to provide online support for your Help articles, see [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd90e-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd90e-167">See also</span></span>

- [<span data-ttu-id="fd90e-168">about_Functions</span><span class="sxs-lookup"><span data-stu-id="fd90e-168">about_Functions</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions)
- [<span data-ttu-id="fd90e-169">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="fd90e-169">about_Scripts</span></span>](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [<span data-ttu-id="fd90e-170">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="fd90e-170">about_Comment_Based_Help</span></span>](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)
- [<span data-ttu-id="fd90e-171">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fd90e-171">Get-Help</span></span>](/powershell/module/microsoft.powershell.core/get-help)

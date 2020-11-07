---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: b5758fdb9fc3e8f604b24fb9c64cad3f95047ec3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347777"
---
# <span data-ttu-id="58c32-103">Show-Command</span><span class="sxs-lookup"><span data-stu-id="58c32-103">Show-Command</span></span>

## <span data-ttu-id="58c32-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="58c32-104">SYNOPSIS</span></span>
<span data-ttu-id="58c32-105">Отображает сведения о команде PowerShell в графическом окне.</span><span class="sxs-lookup"><span data-stu-id="58c32-105">Displays PowerShell command information in a graphical window.</span></span>

## <span data-ttu-id="58c32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="58c32-106">SYNTAX</span></span>

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="58c32-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="58c32-107">DESCRIPTION</span></span>

<span data-ttu-id="58c32-108">`Show-Command`Командлет позволяет создать команду PowerShell в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="58c32-108">The `Show-Command` cmdlet lets you create a PowerShell command in a command window.</span></span> <span data-ttu-id="58c32-109">Эту функцию командного окна можно использовать для запуска или возврата команды.</span><span class="sxs-lookup"><span data-stu-id="58c32-109">You can use the features of the command window to run the command or have it return the command to you.</span></span>

<span data-ttu-id="58c32-110">`Show-Command` — Это очень полезное средство обучения и обучения.</span><span class="sxs-lookup"><span data-stu-id="58c32-110">`Show-Command` is a very useful teaching and learning tool.</span></span> <span data-ttu-id="58c32-111">`Show-Command` работает со всеми типами команд, включая командлеты, функции, рабочие процессы и команды CIM.</span><span class="sxs-lookup"><span data-stu-id="58c32-111">`Show-Command` works on all command types, including cmdlets, functions, workflows and CIM commands.</span></span>

<span data-ttu-id="58c32-112">Без параметров `Show-Command` отображает командное окно, в котором перечислены все доступные команды во всех установленных модулях.</span><span class="sxs-lookup"><span data-stu-id="58c32-112">Without parameters, `Show-Command` displays a command window that lists all available commands in all installed modules.</span></span> <span data-ttu-id="58c32-113">Чтобы найти команды в модуле, выберите модуль в соответствующем раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="58c32-113">To find the commands in a module, select the module from the Modules drop-down list.</span></span> <span data-ttu-id="58c32-114">Чтобы выбрать команду, щелкните имя команды.</span><span class="sxs-lookup"><span data-stu-id="58c32-114">To select a command, click the command name.</span></span>

<span data-ttu-id="58c32-115">Чтобы использовать командное окно, выберите команду либо с помощью имени, либо щелкнув имя команды в списке **команды** .</span><span class="sxs-lookup"><span data-stu-id="58c32-115">To use the command window, select a command, either by using the Name or by clicking the command name in the **Commands** list.</span></span> <span data-ttu-id="58c32-116">Каждый набор параметров отображается на отдельной вкладке. Звездочки указывают обязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="58c32-116">Each parameter set is displayed on a separate tab. Asterisks indicate the mandatory parameters.</span></span> <span data-ttu-id="58c32-117">Чтобы ввести значение для параметра, введите значение в текстовое поле или выберите его из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="58c32-117">To enter values for a parameter, type the value in the text box or select the value from the drop-down box.</span></span> <span data-ttu-id="58c32-118">Чтобы добавить параметр переключателя, установите флажок параметра.</span><span class="sxs-lookup"><span data-stu-id="58c32-118">To add a switch parameter, click to select the parameter check box.</span></span>

<span data-ttu-id="58c32-119">Когда все будет готово, щелкните **Copy** , чтобы скопировать созданную команду в буфер обмена, или **Run** , чтобы выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="58c32-119">When you're ready, you can click **Copy** to copy the command that you've created to the clipboard or click **Run** to run the command.</span></span> <span data-ttu-id="58c32-120">Можно также использовать параметр **PassThru** для возврата команды в главное приложение, например консоль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58c32-120">You can also use the **PassThru** parameter to return the command to the host program, such as the PowerShell console.</span></span> <span data-ttu-id="58c32-121">Чтобы отменить выбор команды и вернуться к представлению, в котором отображаются все команды, нажмите клавишу CTRL и выберите выбранную команду.</span><span class="sxs-lookup"><span data-stu-id="58c32-121">To cancel the command selection and return to the view that displays all commands, press Ctrl and click the selected command.</span></span>

<span data-ttu-id="58c32-122">В интегрированной среде сценариев (ISE) PowerShell `Show-Command` по умолчанию отображается вариант окна.</span><span class="sxs-lookup"><span data-stu-id="58c32-122">In the PowerShell Integrated Scripting Environment (ISE), a variation of the `Show-Command` window is displayed by default.</span></span> <span data-ttu-id="58c32-123">Сведения об использовании этого командного окна см. в разделах справки PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="58c32-123">For information about using this command window, see the PowerShell ISE Help topics.</span></span>

<span data-ttu-id="58c32-124">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="58c32-124">This cmdlet was reintroduced in PowerShell 7.</span></span>

<span data-ttu-id="58c32-125">Поскольку для этого командлета требуется пользовательский интерфейс, он не работает на Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="58c32-125">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="58c32-126">Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="58c32-126">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="58c32-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="58c32-127">EXAMPLES</span></span>

### <span data-ttu-id="58c32-128">Пример 1. Открытие окна команд</span><span class="sxs-lookup"><span data-stu-id="58c32-128">Example 1: Open the Commands window</span></span>

<span data-ttu-id="58c32-129">В этом примере отображается представление окна по умолчанию `Show-Command` .</span><span class="sxs-lookup"><span data-stu-id="58c32-129">This example displays the default view of the `Show-Command` window.</span></span> <span data-ttu-id="58c32-130">В окне **команды** отображается список всех команд во всех модулях, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="58c32-130">The **Commands** window displays a list of all commands in all modules that are installed on the computer.</span></span>

```powershell
Show-Command
```

### <span data-ttu-id="58c32-131">Пример 2. Открытие командлета в окне "команды"</span><span class="sxs-lookup"><span data-stu-id="58c32-131">Example 2: Open a cmdlet in the Commands window</span></span>

<span data-ttu-id="58c32-132">В этом примере командлет выводится `Invoke-Command` в **командном** окне.</span><span class="sxs-lookup"><span data-stu-id="58c32-132">This example display the `Invoke-Command` cmdlet in the **Command** window.</span></span> <span data-ttu-id="58c32-133">Это отображение можно использовать для выполнения `Invoke-Command` команд.</span><span class="sxs-lookup"><span data-stu-id="58c32-133">You can use this display to run `Invoke-Command` commands.</span></span>

```powershell
Show-Command -Name "Invoke-Command"
```

### <span data-ttu-id="58c32-134">Пример 3. Открытие командлета с указанными параметрами</span><span class="sxs-lookup"><span data-stu-id="58c32-134">Example 3: Open a cmdlet with specified parameters</span></span>

<span data-ttu-id="58c32-135">Эта команда открывает `Show-Command` окно для `Connect-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="58c32-135">This command opens a `Show-Command` window for the`Connect-PSSession`cmdlet.</span></span>

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

<span data-ttu-id="58c32-136">Параметры **Height** и **Width** определяют размер командного окна.</span><span class="sxs-lookup"><span data-stu-id="58c32-136">The **Height** and **Width** parameters specify the dimension of the command window.</span></span> <span data-ttu-id="58c32-137">Параметр **еррорпопуп** отображает окно команды ошибки.</span><span class="sxs-lookup"><span data-stu-id="58c32-137">The **ErrorPopup** parameter displays the error command window.</span></span>

<span data-ttu-id="58c32-138">При нажатии кнопки **выполнить** `Connect-PSSession` команда выполняется так же, как и при вводе `Connect-PSSession` команды в командной строке.</span><span class="sxs-lookup"><span data-stu-id="58c32-138">When you click **Run** , the `Connect-PSSession` command runs, just as would if you typed the `Connect-PSSession` command at the command line.</span></span>

### <span data-ttu-id="58c32-139">Пример 4. Указание новых значений параметров по умолчанию для командлета</span><span class="sxs-lookup"><span data-stu-id="58c32-139">Example 4: Specify new default parameter values for a cmdlet</span></span>

<span data-ttu-id="58c32-140">В этом примере `$PSDefaultParameterValues` Автоматическая переменная используется для задания новых значений по умолчанию для параметров **Height** , **Width** и **еррорпопуп** `Show-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="58c32-140">This example uses the `$PSDefaultParameterValues` automatic variable to set new default values for the **Height** , **Width** , and **ErrorPopup** parameters of the `Show-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

<span data-ttu-id="58c32-141">Теперь при выполнении `Show-Command` команды новые значения по умолчанию применяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="58c32-141">Now when you run a `Show-Command` command, the new defaults are applied automatically.</span></span> <span data-ttu-id="58c32-142">Чтобы использовать эти значения по умолчанию в каждом сеансе PowerShell, добавьте `$PSDefaultParameterValues` переменную в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58c32-142">To use these default values in every PowerShell session, add the `$PSDefaultParameterValues` variable to your PowerShell profile.</span></span> <span data-ttu-id="58c32-143">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) и [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="58c32-143">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) and [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span></span>

### <span data-ttu-id="58c32-144">Пример 5. Отправка выходных данных в представление сетки</span><span class="sxs-lookup"><span data-stu-id="58c32-144">Example 5: Send output to a grid view</span></span>

<span data-ttu-id="58c32-145">Эта команда показывает, как использовать `Show-Command` `Out-GridView` командлеты и вместе.</span><span class="sxs-lookup"><span data-stu-id="58c32-145">This command shows how to use the `Show-Command` and `Out-GridView` cmdlets together.</span></span>

```powershell
Show-Command Get-ChildItem | Out-GridView
```

<span data-ttu-id="58c32-146">Команда использует командлет, `Show-Command` чтобы открыть командное окно для `Get-ChildItem` командлета.</span><span class="sxs-lookup"><span data-stu-id="58c32-146">The command uses the `Show-Command` cmdlet to open a command window for the`Get-ChildItem`cmdlet.</span></span>
<span data-ttu-id="58c32-147">При нажатии кнопки **выполнить** `Get-ChildItem` команда выполняет команду и создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="58c32-147">When you click the **Run** button, the `Get-ChildItem` command runs and generates output.</span></span> <span data-ttu-id="58c32-148">Оператор конвейера (|) отправляет выходные данные команды в `Get-ChildItem` `Out-GridView` командлет, который отображает `Get-ChildItem` выходные данные в интерактивном окне.</span><span class="sxs-lookup"><span data-stu-id="58c32-148">The pipeline operator ( | ) sends the output of the `Get-ChildItem` command to the `Out-GridView` cmdlet, which displays the `Get-ChildItem` output in an interactive window.</span></span>

### <span data-ttu-id="58c32-149">Пример 6. Отображение команды, созданной в окне "команды"</span><span class="sxs-lookup"><span data-stu-id="58c32-149">Example 6: Display a command that you create in the Commands window</span></span>

<span data-ttu-id="58c32-150">В этом примере показана команда, созданная в `Show-Command` окне.</span><span class="sxs-lookup"><span data-stu-id="58c32-150">This example shows the command that you created in the `Show-Command` window.</span></span> <span data-ttu-id="58c32-151">Команда использует параметр **PassThru** , который возвращает `Show-Command` результаты в виде строки.</span><span class="sxs-lookup"><span data-stu-id="58c32-151">The command uses the **PassThru** parameter, which returns the `Show-Command` results in a string.</span></span>

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

<span data-ttu-id="58c32-152">Например, если вы используете `Show-Command` окно для создания `Get-EventLog` команды, которая получает пять самых новых событий в журнале событий Windows PowerShell, а затем нажмите кнопку **ОК** , команда возвращает выходные данные, показанные выше.</span><span class="sxs-lookup"><span data-stu-id="58c32-152">For example, if you use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log, and then click **OK** , the command returns the output shown above.</span></span> <span data-ttu-id="58c32-153">Просмотр строки команды поможет вам изучить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58c32-153">Viewing the command string helps you learn PowerShell.</span></span>

### <span data-ttu-id="58c32-154">Пример 7. Сохранение команды в переменной</span><span class="sxs-lookup"><span data-stu-id="58c32-154">Example 7: Save a command to a variable</span></span>

<span data-ttu-id="58c32-155">В этом примере показано, как выполнить командную строку, полученную при использовании параметра **PassThru** `Show-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="58c32-155">This example shows how to run the command string that you get when you use the **PassThru** parameter of the `Show-Command` cmdlet.</span></span> <span data-ttu-id="58c32-156">Эта стратегия позволяет видеть команду и использовать ее.</span><span class="sxs-lookup"><span data-stu-id="58c32-156">This strategy lets you see the command and use it.</span></span>

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

<span data-ttu-id="58c32-157">Первая команда использует параметр **PassThru** `Show-Command` командлета и сохраняет результаты команды в `$C` переменной.</span><span class="sxs-lookup"><span data-stu-id="58c32-157">The first command uses the **PassThru** parameter of the `Show-Command` cmdlet and saves the results of the command in the `$C` variable.</span></span> <span data-ttu-id="58c32-158">В этом случае мы используем окно, `Show-Command` чтобы создать `Get-EventLog` команду, которая получает пять самых новых событий в журнале событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58c32-158">In this case, we use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log.</span></span> <span data-ttu-id="58c32-159">При нажатии **OK** кнопки ОК `Show-Command` возвращает командную строку, которая сохраняется в `$C` переменной.</span><span class="sxs-lookup"><span data-stu-id="58c32-159">When you click **OK** , `Show-Command` returns the command string, which is saved in the `$C` variable.</span></span>

### <span data-ttu-id="58c32-160">Пример 8. сохранение выходных данных команды в переменную</span><span class="sxs-lookup"><span data-stu-id="58c32-160">Example 8: Save the output of a command to a variable</span></span>

<span data-ttu-id="58c32-161">В этом примере используется параметр **еррорпопуп** для сохранения выходных данных команды в переменной.</span><span class="sxs-lookup"><span data-stu-id="58c32-161">This example uses the **ErrorPopup** parameter to save the output of a command in a variable.</span></span>

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

<span data-ttu-id="58c32-162">Помимо отображения ошибок в окне, параметр **ErrorPopup** возвращает выходные данные команды в текущую команду вместо создания новой команды.</span><span class="sxs-lookup"><span data-stu-id="58c32-162">In addition to displaying errors in a window, **ErrorPopup** returns command output to the current command, instead of creating a new command.</span></span> <span data-ttu-id="58c32-163">При выполнении этой команды `Show-Command` открывается окно.</span><span class="sxs-lookup"><span data-stu-id="58c32-163">When you run this command, the `Show-Command` window opens.</span></span> <span data-ttu-id="58c32-164">Функции окна можно использовать для установки значений параметров.</span><span class="sxs-lookup"><span data-stu-id="58c32-164">You can use the window features to set parameter values.</span></span> <span data-ttu-id="58c32-165">Чтобы выполнить команду, нажмите кнопку **выполнить** в `Show-Command` окне.</span><span class="sxs-lookup"><span data-stu-id="58c32-165">To run the command, click the **Run** button in the `Show-Command` window.</span></span>

## <span data-ttu-id="58c32-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="58c32-166">PARAMETERS</span></span>

### <span data-ttu-id="58c32-167">-Еррорпопуп</span><span class="sxs-lookup"><span data-stu-id="58c32-167">-ErrorPopup</span></span>

<span data-ttu-id="58c32-168">Указывает, что командлет выводит ошибки во всплывающем окне, а также отображает их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="58c32-168">Indicates that the cmdlet displays errors in a pop-up window, in addition to displaying them at the command line.</span></span> <span data-ttu-id="58c32-169">По умолчанию, когда команда, выполняемая в `Show-Command` окне, вызывает ошибку, эта ошибка отображается только в командной строке.</span><span class="sxs-lookup"><span data-stu-id="58c32-169">By default, when a command that is run in a `Show-Command` window generates an error, the error is displayed only at the command line.</span></span>

<span data-ttu-id="58c32-170">Кроме того, при выполнении команды (с помощью кнопки **выполнить** в `Show-Command` окне) параметр **еррорпопуп** возвращает результаты команды текущей команде вместо выполнения команды и возврата ее выходных данных в новую команду.</span><span class="sxs-lookup"><span data-stu-id="58c32-170">Also, when you run the command (by using the **Run** button in the `Show-Command` window), the **ErrorPopup** parameter returns the command results to the current command, instead of running the command and returning its output to a new command.</span></span> <span data-ttu-id="58c32-171">Эту функцию можно использовать для сохранения результатов команды в переменной.</span><span class="sxs-lookup"><span data-stu-id="58c32-171">You can use this feature to save the command results in a variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-172">-Height</span><span class="sxs-lookup"><span data-stu-id="58c32-172">-Height</span></span>

<span data-ttu-id="58c32-173">Задает высоту `Show-Command` окна в пикселях.</span><span class="sxs-lookup"><span data-stu-id="58c32-173">Specifies the height of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="58c32-174">Введите значение в диапазоне от 300 пикселей до числа пикселей разрешения экрана.</span><span class="sxs-lookup"><span data-stu-id="58c32-174">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="58c32-175">Если значение слишком велико для отображения командного окна на экране, `Show-Command` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="58c32-175">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="58c32-176">Высота по умолчанию: 600 пикселей.</span><span class="sxs-lookup"><span data-stu-id="58c32-176">The default height is 600 pixels.</span></span> <span data-ttu-id="58c32-177">Для `Show-Command` команды, включающей параметр **Name** , высота по умолчанию составляет 300 пикселей.</span><span class="sxs-lookup"><span data-stu-id="58c32-177">For a `Show-Command` command that includes the **Name** parameter, the default height is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-178">-Name</span><span class="sxs-lookup"><span data-stu-id="58c32-178">-Name</span></span>

<span data-ttu-id="58c32-179">Отображает командное окно для заданной команды.</span><span class="sxs-lookup"><span data-stu-id="58c32-179">Displays a command window for the specified command.</span></span> <span data-ttu-id="58c32-180">Введите имя одной команды, например имя командлета, функции или команды CIM.</span><span class="sxs-lookup"><span data-stu-id="58c32-180">Enter the name of one command, such as the name of a cmdlet, function, or CIM command.</span></span> <span data-ttu-id="58c32-181">Если этот параметр не указан, `Show-Command` отображает командное окно, в котором перечислены все команды PowerShell во всех модулях, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="58c32-181">If you omit this parameter, `Show-Command` displays a command window that lists all of the PowerShell commands in all modules installed on the computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-182">-Нокоммонпараметер</span><span class="sxs-lookup"><span data-stu-id="58c32-182">-NoCommonParameter</span></span>

<span data-ttu-id="58c32-183">Указывает, что этот командлет опускает раздел общих параметров на экране команды.</span><span class="sxs-lookup"><span data-stu-id="58c32-183">Indicates that this cmdlet omits the Common Parameters section of the command display.</span></span> <span data-ttu-id="58c32-184">По умолчанию общие параметры отображаются в развертываемом разделе в нижней части командного окна.</span><span class="sxs-lookup"><span data-stu-id="58c32-184">By default, the Common Parameters appear in an expandable section at the bottom of the command window.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-185">-PassThru</span><span class="sxs-lookup"><span data-stu-id="58c32-185">-PassThru</span></span>

<span data-ttu-id="58c32-186">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="58c32-186">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="58c32-187">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="58c32-187">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="58c32-188">Чтобы выполнить командную строку, скопируйте и вставьте ее в командной строке или сохраните в переменной и используйте `Invoke-Expression` командлет для выполнения строки в переменной.</span><span class="sxs-lookup"><span data-stu-id="58c32-188">To run the command string, copy and paste it at the command prompt or save it in a variable and use the `Invoke-Expression` cmdlet to run the string in the variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-189">-Width</span><span class="sxs-lookup"><span data-stu-id="58c32-189">-Width</span></span>

<span data-ttu-id="58c32-190">Задает ширину `Show-Command` окна в пикселях.</span><span class="sxs-lookup"><span data-stu-id="58c32-190">Specifies the width of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="58c32-191">Введите значение в диапазоне от 300 пикселей до числа пикселей разрешения экрана.</span><span class="sxs-lookup"><span data-stu-id="58c32-191">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="58c32-192">Если значение слишком велико для отображения командного окна на экране, `Show-Command` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="58c32-192">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="58c32-193">Ширина по умолчанию: 300 пикселей.</span><span class="sxs-lookup"><span data-stu-id="58c32-193">The default width is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58c32-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="58c32-194">CommonParameters</span></span>

<span data-ttu-id="58c32-195">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="58c32-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58c32-196">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="58c32-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58c32-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="58c32-197">INPUTS</span></span>

### <span data-ttu-id="58c32-198">Нет</span><span class="sxs-lookup"><span data-stu-id="58c32-198">None</span></span>

<span data-ttu-id="58c32-199">Вы не можете передать входные данные в `Show-Command` .</span><span class="sxs-lookup"><span data-stu-id="58c32-199">You cannot pipe input to `Show-Command`.</span></span>

## <span data-ttu-id="58c32-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="58c32-200">OUTPUTS</span></span>

### <span data-ttu-id="58c32-201">Нет, System. String, System. Object</span><span class="sxs-lookup"><span data-stu-id="58c32-201">None, System.String, System.Object</span></span>

<span data-ttu-id="58c32-202">При использовании параметра **PassThru** `Show-Command` возвращает командную строку.</span><span class="sxs-lookup"><span data-stu-id="58c32-202">When you use the **PassThru** parameter, `Show-Command` returns a command string.</span></span> <span data-ttu-id="58c32-203">При использовании параметра **еррорпопуп** `Show-Command` возвращает выходные данные команды (любой объект).</span><span class="sxs-lookup"><span data-stu-id="58c32-203">When you use the **ErrorPopup** parameter, `Show-Command` returns the command output (any object).</span></span> <span data-ttu-id="58c32-204">В противном случае не `Show-Command` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="58c32-204">Otherwise, `Show-Command` does not generate any output.</span></span>

## <span data-ttu-id="58c32-205">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="58c32-205">NOTES</span></span>

<span data-ttu-id="58c32-206">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="58c32-206">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="58c32-207">`Show-Command` не работает в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="58c32-207">`Show-Command` does not work in remote sessions.</span></span>

## <span data-ttu-id="58c32-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="58c32-208">RELATED LINKS</span></span>

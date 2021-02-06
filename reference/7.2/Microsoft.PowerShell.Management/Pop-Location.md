---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 8a44849f27de80ece486b573f1adccafab51972a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605060"
---
# <span data-ttu-id="ac3bd-102">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="ac3bd-102">Pop-Location</span></span>

## <span data-ttu-id="ac3bd-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ac3bd-103">SYNOPSIS</span></span>
<span data-ttu-id="ac3bd-104">Меняет текущее расположение на расположение, указанное в последней записи стека.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-104">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="ac3bd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac3bd-105">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="ac3bd-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ac3bd-106">DESCRIPTION</span></span>

<span data-ttu-id="ac3bd-107">`Pop-Location`Командлет изменяет текущее расположение на расположение, которое недавно было отправлено в стек с помощью `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-107">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="ac3bd-108">Можно открыть расположение из стека по умолчанию или из стека, созданного с помощью `Push-Location` команды.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-108">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="ac3bd-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="ac3bd-109">EXAMPLES</span></span>

### <span data-ttu-id="ac3bd-110">Пример 1. Переход к последнему расположению</span><span class="sxs-lookup"><span data-stu-id="ac3bd-110">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="ac3bd-111">Эта команда меняет текущее расположение на расположение, указанное в последней записи текущего стека.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-111">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="ac3bd-112">Пример 2. Переход к последнему расположению в именованном стеке</span><span class="sxs-lookup"><span data-stu-id="ac3bd-112">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="ac3bd-113">Эта команда меняет текущее расположение на расположение, указанное в последней записи стека Stack2.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-113">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="ac3bd-114">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-114">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="ac3bd-115">Пример 3. Перемещение между расположениями для разных поставщиков</span><span class="sxs-lookup"><span data-stu-id="ac3bd-115">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="ac3bd-116">Эти команды используют `Push-Location` `Pop-Location` командлеты и для перемещения между расположениями, поддерживаемыми различными поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-116">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="ac3bd-117">Команды используют `pushd` псевдоним для `Push-Location` и `popd` псевдоним для `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="ac3bd-117">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="ac3bd-118">Первая команда помещает текущее расположение файловой системы в стек и переходит на диск HKLM, поддерживаемый поставщиком реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-118">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="ac3bd-119">Вторая команда помещает расположение реестра в стек и переходит в расположение, поддерживаемое поставщиком сертификатов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-119">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="ac3bd-120">Две последние команды извлекают эти расположения из стека.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-120">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="ac3bd-121">Первая `popd` команда возвращается к диску реестра, а вторая команда возвращается к диску файловой системы.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-121">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="ac3bd-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac3bd-122">PARAMETERS</span></span>

### <span data-ttu-id="ac3bd-123">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ac3bd-123">-PassThru</span></span>

<span data-ttu-id="ac3bd-124">Передает объект, представляющий расположение в конвейер.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-124">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="ac3bd-125">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-125">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ac3bd-126">-StackName</span><span class="sxs-lookup"><span data-stu-id="ac3bd-126">-StackName</span></span>

<span data-ttu-id="ac3bd-127">Указывает стек папок, из которого будет взято расположение.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-127">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="ac3bd-128">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-128">Enter a location stack name.</span></span>

<span data-ttu-id="ac3bd-129">Без этого параметра `Pop-Location` извлекает расположение из текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-129">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="ac3bd-130">По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-130">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="ac3bd-131">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-131">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="ac3bd-132">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-132">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="ac3bd-133">`Pop-Location` невозможно открыть расположение из неименованного стека по умолчанию, если он не является текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-133">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ac3bd-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ac3bd-134">CommonParameters</span></span>

<span data-ttu-id="ac3bd-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ac3bd-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ac3bd-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ac3bd-137">INPUTS</span></span>

### <span data-ttu-id="ac3bd-138">None</span><span class="sxs-lookup"><span data-stu-id="ac3bd-138">None</span></span>

<span data-ttu-id="ac3bd-139">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ac3bd-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ac3bd-140">OUTPUTS</span></span>

### <span data-ttu-id="ac3bd-141">Нет, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="ac3bd-141">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="ac3bd-142">Этот командлет создает объект **System. Management. Automation. PathInfo** , представляющий расположение, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="ac3bd-142">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="ac3bd-143">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-143">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ac3bd-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ac3bd-144">NOTES</span></span>

<span data-ttu-id="ac3bd-145">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-145">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="ac3bd-146">Каждое пространство выполнения имеет свой собственный _текущий каталог_.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-146">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="ac3bd-147">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="ac3bd-147">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="ac3bd-148">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-148">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="ac3bd-149">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-149">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="ac3bd-150">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-150">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="ac3bd-151">Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-151">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="ac3bd-152">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-152">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="ac3bd-153">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-153">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="ac3bd-154">PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-154">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="ac3bd-155">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-155">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="ac3bd-156">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-156">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="ac3bd-157">Для управления стеками расположений используйте `*-Location` командлеты PowerShell следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac3bd-157">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="ac3bd-158">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-158">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="ac3bd-159">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-159">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="ac3bd-160">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-160">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="ac3bd-161">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-161">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="ac3bd-162">Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-162">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="ac3bd-163">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-163">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="ac3bd-164">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-164">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="ac3bd-165">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-165">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="ac3bd-166">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-166">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="ac3bd-167">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$Null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-167">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="ac3bd-168">Также можно ссылаться `Pop-Location` по встроенному псевдониму `popd` .</span><span class="sxs-lookup"><span data-stu-id="ac3bd-168">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="ac3bd-169">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-169">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="ac3bd-170">`Pop-Location` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-170">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ac3bd-171">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="ac3bd-171">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="ac3bd-172">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ac3bd-172">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ac3bd-173">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ac3bd-173">RELATED LINKS</span></span>

[<span data-ttu-id="ac3bd-174">Get-Location</span><span class="sxs-lookup"><span data-stu-id="ac3bd-174">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="ac3bd-175">Push-Location</span><span class="sxs-lookup"><span data-stu-id="ac3bd-175">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="ac3bd-176">Set-Location</span><span class="sxs-lookup"><span data-stu-id="ac3bd-176">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="ac3bd-177">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="ac3bd-177">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="ac3bd-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ac3bd-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

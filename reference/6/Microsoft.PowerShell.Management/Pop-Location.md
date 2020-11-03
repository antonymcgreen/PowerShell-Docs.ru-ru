---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 42a5c9c75c11a40b5bb842d86894688a354bed15
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "93230254"
---
# <span data-ttu-id="289e6-103">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="289e6-103">Pop-Location</span></span>

## <span data-ttu-id="289e6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="289e6-104">SYNOPSIS</span></span>
<span data-ttu-id="289e6-105">Меняет текущее расположение на расположение, указанное в последней записи стека.</span><span class="sxs-lookup"><span data-stu-id="289e6-105">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="289e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="289e6-106">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="289e6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="289e6-107">DESCRIPTION</span></span>

<span data-ttu-id="289e6-108">`Pop-Location`Командлет изменяет текущее расположение на расположение, которое недавно было отправлено в стек с помощью `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-108">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="289e6-109">Можно открыть расположение из стека по умолчанию или из стека, созданного с помощью `Push-Location` команды.</span><span class="sxs-lookup"><span data-stu-id="289e6-109">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="289e6-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="289e6-110">EXAMPLES</span></span>

### <span data-ttu-id="289e6-111">Пример 1. Переход к последнему расположению</span><span class="sxs-lookup"><span data-stu-id="289e6-111">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="289e6-112">Эта команда меняет текущее расположение на расположение, указанное в последней записи текущего стека.</span><span class="sxs-lookup"><span data-stu-id="289e6-112">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="289e6-113">Пример 2. Переход к последнему расположению в именованном стеке</span><span class="sxs-lookup"><span data-stu-id="289e6-113">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="289e6-114">Эта команда меняет текущее расположение на расположение, указанное в последней записи стека Stack2.</span><span class="sxs-lookup"><span data-stu-id="289e6-114">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="289e6-115">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="289e6-115">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="289e6-116">Пример 3. Перемещение между расположениями для разных поставщиков</span><span class="sxs-lookup"><span data-stu-id="289e6-116">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="289e6-117">Эти команды используют `Push-Location` `Pop-Location` командлеты и для перемещения между расположениями, поддерживаемыми различными поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289e6-117">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="289e6-118">Команды используют `pushd` псевдоним для `Push-Location` и `popd` псевдоним для `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="289e6-118">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="289e6-119">Первая команда помещает текущее расположение файловой системы в стек и переходит на диск HKLM, поддерживаемый поставщиком реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289e6-119">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="289e6-120">Вторая команда помещает расположение реестра в стек и переходит в расположение, поддерживаемое поставщиком сертификатов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289e6-120">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="289e6-121">Две последние команды извлекают эти расположения из стека.</span><span class="sxs-lookup"><span data-stu-id="289e6-121">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="289e6-122">Первая `popd` команда возвращается к диску реестра, а вторая команда возвращается к диску файловой системы.</span><span class="sxs-lookup"><span data-stu-id="289e6-122">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="289e6-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="289e6-123">PARAMETERS</span></span>

### <span data-ttu-id="289e6-124">-PassThru</span><span class="sxs-lookup"><span data-stu-id="289e6-124">-PassThru</span></span>

<span data-ttu-id="289e6-125">Передает объект, представляющий расположение в конвейер.</span><span class="sxs-lookup"><span data-stu-id="289e6-125">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="289e6-126">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="289e6-126">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="289e6-127">-StackName</span><span class="sxs-lookup"><span data-stu-id="289e6-127">-StackName</span></span>

<span data-ttu-id="289e6-128">Указывает стек папок, из которого будет взято расположение.</span><span class="sxs-lookup"><span data-stu-id="289e6-128">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="289e6-129">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="289e6-129">Enter a location stack name.</span></span>

<span data-ttu-id="289e6-130">Без этого параметра `Pop-Location` извлекает расположение из текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="289e6-130">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="289e6-131">По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289e6-131">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="289e6-132">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-132">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="289e6-133">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="289e6-133">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="289e6-134">`Pop-Location` невозможно открыть расположение из неименованного стека по умолчанию, если он не является текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="289e6-134">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

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

### <span data-ttu-id="289e6-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="289e6-135">CommonParameters</span></span>

<span data-ttu-id="289e6-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="289e6-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="289e6-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="289e6-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="289e6-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="289e6-138">INPUTS</span></span>

### <span data-ttu-id="289e6-139">Нет</span><span class="sxs-lookup"><span data-stu-id="289e6-139">None</span></span>

<span data-ttu-id="289e6-140">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="289e6-140">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="289e6-141">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="289e6-141">OUTPUTS</span></span>

### <span data-ttu-id="289e6-142">Нет, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="289e6-142">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="289e6-143">Этот командлет создает объект **System. Management. Automation. PathInfo** , представляющий расположение, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="289e6-143">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="289e6-144">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="289e6-144">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="289e6-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="289e6-145">NOTES</span></span>

<span data-ttu-id="289e6-146">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="289e6-146">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="289e6-147">Каждое пространство выполнения имеет свой собственный _текущий каталог_ .</span><span class="sxs-lookup"><span data-stu-id="289e6-147">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="289e6-148">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="289e6-148">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="289e6-149">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="289e6-149">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="289e6-150">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="289e6-150">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="289e6-151">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="289e6-151">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="289e6-152">Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам.</span><span class="sxs-lookup"><span data-stu-id="289e6-152">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="289e6-153">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="289e6-153">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="289e6-154">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="289e6-154">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="289e6-155">PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="289e6-155">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="289e6-156">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="289e6-156">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="289e6-157">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="289e6-157">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="289e6-158">Для управления стеками расположений используйте `*-Location` командлеты PowerShell следующим образом:</span><span class="sxs-lookup"><span data-stu-id="289e6-158">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="289e6-159">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="289e6-159">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="289e6-160">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="289e6-160">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="289e6-161">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-161">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="289e6-162">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-162">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="289e6-163">Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-163">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="289e6-164">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="289e6-164">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="289e6-165">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="289e6-165">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="289e6-166">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="289e6-166">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="289e6-167">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="289e6-167">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="289e6-168">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$Null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="289e6-168">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="289e6-169">Также можно ссылаться `Pop-Location` по встроенному псевдониму `popd` .</span><span class="sxs-lookup"><span data-stu-id="289e6-169">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="289e6-170">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="289e6-170">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="289e6-171">`Pop-Location` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="289e6-171">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="289e6-172">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="289e6-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="289e6-173">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="289e6-173">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="289e6-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="289e6-174">RELATED LINKS</span></span>

[<span data-ttu-id="289e6-175">Get-Location</span><span class="sxs-lookup"><span data-stu-id="289e6-175">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="289e6-176">Push-Location</span><span class="sxs-lookup"><span data-stu-id="289e6-176">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="289e6-177">Set-Location</span><span class="sxs-lookup"><span data-stu-id="289e6-177">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="289e6-178">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="289e6-178">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="289e6-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="289e6-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

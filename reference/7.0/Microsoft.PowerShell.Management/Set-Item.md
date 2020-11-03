---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: 4485b1a140b1496ee80d81d1526b3d76e446fd34
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226121"
---
# <span data-ttu-id="8afce-103">Set-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-103">Set-Item</span></span>

## <span data-ttu-id="8afce-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8afce-104">SYNOPSIS</span></span>
<span data-ttu-id="8afce-105">Изменяет значение элемента на значение, указанное в команде.</span><span class="sxs-lookup"><span data-stu-id="8afce-105">Changes the value of an item to the value specified in the command.</span></span>

## <span data-ttu-id="8afce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8afce-106">SYNTAX</span></span>

### <span data-ttu-id="8afce-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8afce-107">Path (Default)</span></span>

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8afce-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8afce-108">LiteralPath</span></span>

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8afce-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8afce-109">DESCRIPTION</span></span>

<span data-ttu-id="8afce-110">`Set-Item`Командлет изменяет значение элемента, например переменную или раздел реестра, на значение, указанное в команде.</span><span class="sxs-lookup"><span data-stu-id="8afce-110">The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.</span></span>

## <span data-ttu-id="8afce-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8afce-111">EXAMPLES</span></span>

### <span data-ttu-id="8afce-112">Пример 1. Создание псевдонима</span><span class="sxs-lookup"><span data-stu-id="8afce-112">Example 1: Create an alias</span></span>

<span data-ttu-id="8afce-113">Эта команда создает псевдоним NP для блокнота.</span><span class="sxs-lookup"><span data-stu-id="8afce-113">This command creates an alias of np for Notepad.</span></span>

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### <span data-ttu-id="8afce-114">Пример 2. изменение значения переменной среды</span><span class="sxs-lookup"><span data-stu-id="8afce-114">Example 2: Change the value of an environment variable</span></span>

<span data-ttu-id="8afce-115">Эта команда изменяет значение переменной среды UserRole на "Администратор".</span><span class="sxs-lookup"><span data-stu-id="8afce-115">This command changes the value of the UserRole environment variable to Administrator.</span></span>

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### <span data-ttu-id="8afce-116">Пример 3. изменение функции Prompt</span><span class="sxs-lookup"><span data-stu-id="8afce-116">Example 3: Modify your prompt function</span></span>

<span data-ttu-id="8afce-117">Эта команда изменяет функцию Prompt таким образом, чтобы она отображала время перед путем.</span><span class="sxs-lookup"><span data-stu-id="8afce-117">This command changes the prompt function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### <span data-ttu-id="8afce-118">Пример 4. Задание параметров для функции Prompt</span><span class="sxs-lookup"><span data-stu-id="8afce-118">Example 4: Set options for your prompt function</span></span>

<span data-ttu-id="8afce-119">Эта команда задает параметры **AllScope** и **ReadOnly** для функции Prompt.</span><span class="sxs-lookup"><span data-stu-id="8afce-119">This command sets the **AllScope** and **ReadOnly** options for the prompt function.</span></span>
<span data-ttu-id="8afce-120">Эта команда использует динамический параметр **Options функции** `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="8afce-120">This command uses the **Options** dynamic parameter of `Set-Item`.</span></span>
<span data-ttu-id="8afce-121">Параметр **Options** доступен `Set-Item` только в том случае, если он используется с **псевдонимом** или поставщиком **функций** .</span><span class="sxs-lookup"><span data-stu-id="8afce-121">The **Options** parameter is available in `Set-Item` only when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## <span data-ttu-id="8afce-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8afce-122">PARAMETERS</span></span>

### <span data-ttu-id="8afce-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="8afce-123">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8afce-124">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8afce-124">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8afce-125">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-125">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8afce-126">-Exclude</span><span class="sxs-lookup"><span data-stu-id="8afce-126">-Exclude</span></span>

<span data-ttu-id="8afce-127">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="8afce-127">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="8afce-128">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="8afce-128">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8afce-129">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="8afce-129">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="8afce-130">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8afce-130">Wildcard characters are permitted.</span></span> <span data-ttu-id="8afce-131">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="8afce-131">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8afce-132">-Filter</span><span class="sxs-lookup"><span data-stu-id="8afce-132">-Filter</span></span>

<span data-ttu-id="8afce-133">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="8afce-133">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="8afce-134">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="8afce-134">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="8afce-135">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-135">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="8afce-136">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="8afce-136">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8afce-137">-Force</span><span class="sxs-lookup"><span data-stu-id="8afce-137">-Force</span></span>

<span data-ttu-id="8afce-138">Заставляет командлет задавать элементы, которые в противном случае не могут быть изменены, например псевдоним или переменные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8afce-138">Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables.</span></span> <span data-ttu-id="8afce-139">С помощью этого командлета нельзя изменять постоянные псевдонимы или переменные.</span><span class="sxs-lookup"><span data-stu-id="8afce-139">The cmdlet cannot change constant aliases or variables.</span></span>
<span data-ttu-id="8afce-140">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="8afce-140">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="8afce-141">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="8afce-142">Даже при использовании параметра *Force* командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8afce-142">Even using the *Force* parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="8afce-143">-Include</span><span class="sxs-lookup"><span data-stu-id="8afce-143">-Include</span></span>

<span data-ttu-id="8afce-144">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="8afce-144">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="8afce-145">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="8afce-145">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8afce-146">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="8afce-146">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="8afce-147">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8afce-147">Wildcard characters are permitted.</span></span> <span data-ttu-id="8afce-148">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="8afce-148">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8afce-149">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8afce-149">-LiteralPath</span></span>

<span data-ttu-id="8afce-150">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="8afce-150">Specifies a path to one or more locations.</span></span> <span data-ttu-id="8afce-151">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="8afce-151">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="8afce-152">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="8afce-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8afce-153">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8afce-153">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8afce-154">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="8afce-154">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="8afce-155">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-155">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8afce-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8afce-156">-PassThru</span></span>

<span data-ttu-id="8afce-157">Передает объект, представляющий элемент, в конвейер.</span><span class="sxs-lookup"><span data-stu-id="8afce-157">Passes an object that represents the item to the pipeline.</span></span>
<span data-ttu-id="8afce-158">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8afce-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8afce-159">-Path</span><span class="sxs-lookup"><span data-stu-id="8afce-159">-Path</span></span>

<span data-ttu-id="8afce-160">Задает путь к расположению элементов.</span><span class="sxs-lookup"><span data-stu-id="8afce-160">Specifies a path of the location of the items.</span></span>
<span data-ttu-id="8afce-161">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8afce-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8afce-162">-Value</span><span class="sxs-lookup"><span data-stu-id="8afce-162">-Value</span></span>

<span data-ttu-id="8afce-163">Задает новое имя для элемента.</span><span class="sxs-lookup"><span data-stu-id="8afce-163">Specifies a new value for the item.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8afce-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8afce-164">-Confirm</span></span>

<span data-ttu-id="8afce-165">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8afce-165">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8afce-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8afce-166">-WhatIf</span></span>

<span data-ttu-id="8afce-167">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8afce-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8afce-168">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8afce-168">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8afce-169">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8afce-169">CommonParameters</span></span>

<span data-ttu-id="8afce-170">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="8afce-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="8afce-171">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8afce-172">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8afce-172">INPUTS</span></span>

### <span data-ttu-id="8afce-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="8afce-173">System.Object</span></span>

<span data-ttu-id="8afce-174">Объект, который представляет новое значение элемента, можно передать этому командлету по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8afce-174">You can pipe an object that represents the new value of the item to this cmdlet.</span></span>

## <span data-ttu-id="8afce-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8afce-175">OUTPUTS</span></span>

### <span data-ttu-id="8afce-176">Отсутствует или объект, представляющий новый или измененный элемент.</span><span class="sxs-lookup"><span data-stu-id="8afce-176">None or an object representing the new or changed item.</span></span>

<span data-ttu-id="8afce-177">Этот командлет создает объект, который представляет элемент, если указан параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="8afce-177">This cmdlet generates an object that represent the item, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="8afce-178">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8afce-178">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8afce-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8afce-179">NOTES</span></span>

- <span data-ttu-id="8afce-180">`Set-Item` не поддерживается поставщиком файловой системы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8afce-180">`Set-Item` is not supported by the PowerShell FileSystem provider.</span></span> <span data-ttu-id="8afce-181">Чтобы изменить значения элементов в файловой системе, используйте `Set-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="8afce-181">To change the values of items in the file system, use the `Set-Content` cmdlet.</span></span>
- <span data-ttu-id="8afce-182">На дисках реестра `HKLM:` и `HKCU:` `Set-Item` изменяет данные в значении (по умолчанию) раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="8afce-182">In the Registry drives, `HKLM:` and `HKCU:`, `Set-Item` changes the data in the (Default) value of a registry key.</span></span>
  - <span data-ttu-id="8afce-183">Чтобы создать и изменить имена разделов реестра, используйте `New-Item` `Rename-Item` командлет и.</span><span class="sxs-lookup"><span data-stu-id="8afce-183">To create and change the names of registry keys, use the `New-Item` and `Rename-Item` cmdlet.</span></span>
  - <span data-ttu-id="8afce-184">Чтобы изменить имена и данные в значениях реестра, используйте `New-ItemProperty` `Set-ItemProperty` командлеты, и `Rename-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="8afce-184">To change the names and data in registry values, use the `New-ItemProperty`, `Set-ItemProperty`, and `Rename-ItemProperty` cmdlets.</span></span>
- <span data-ttu-id="8afce-185">`Set-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8afce-185">`Set-Item` is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="8afce-186">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="8afce-186">To list the providers available in your session, type `Get-PsProvider`.</span></span>
  <span data-ttu-id="8afce-187">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8afce-187">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8afce-188">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8afce-188">RELATED LINKS</span></span>

[<span data-ttu-id="8afce-189">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-189">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="8afce-190">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-190">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="8afce-191">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-191">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="8afce-192">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-192">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="8afce-193">Move-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-193">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="8afce-194">New-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-194">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="8afce-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="8afce-196">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="8afce-196">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="8afce-197">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8afce-197">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

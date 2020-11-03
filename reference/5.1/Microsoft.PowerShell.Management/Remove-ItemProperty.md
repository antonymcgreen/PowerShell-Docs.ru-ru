---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227938"
---
# <span data-ttu-id="a263b-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="a263b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a263b-104">SYNOPSIS</span></span>
<span data-ttu-id="a263b-105">Удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="a263b-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="a263b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a263b-106">SYNTAX</span></span>

### <span data-ttu-id="a263b-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a263b-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a263b-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a263b-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="a263b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a263b-109">DESCRIPTION</span></span>

<span data-ttu-id="a263b-110">`Remove-ItemProperty`Командлет удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="a263b-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="a263b-111">Его можно использовать для удаления параметров реестра и их значений.</span><span class="sxs-lookup"><span data-stu-id="a263b-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="a263b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a263b-112">EXAMPLES</span></span>

### <span data-ttu-id="a263b-113">Пример 1. Удаление значения реестра</span><span class="sxs-lookup"><span data-stu-id="a263b-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="a263b-114">Эта команда удаляет значение реестра "Смппроперти" и его данные из подраздела "Смпаппликатион" раздела реестра "HKEY_LOCAL_MACHINE\Software".</span><span class="sxs-lookup"><span data-stu-id="a263b-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the "HKEY_LOCAL_MACHINE\Software" registry key.</span></span>

<span data-ttu-id="a263b-115">Поскольку команда выполняется с диска файловой системы ( `PS C:\>` ), она включает полный путь к подразделу "смпаппликатион", включая диск, `HKLM:` и ключ "Software".</span><span class="sxs-lookup"><span data-stu-id="a263b-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

<span data-ttu-id="a263b-116">Он использует параметр **Name** для задания удаляемого значения реестра.</span><span class="sxs-lookup"><span data-stu-id="a263b-116">It uses the **Name** parameter to identify the registry value that is being deleted.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### <span data-ttu-id="a263b-117">Пример 2. Удаление значения реестра из расположения HKCU</span><span class="sxs-lookup"><span data-stu-id="a263b-117">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="a263b-118">Эти команды удаляют значение реестра Options и его данные из подраздела "MyApp" в "HKEY_CURRENT_USER\Software\MyCompany".</span><span class="sxs-lookup"><span data-stu-id="a263b-118">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

<span data-ttu-id="a263b-119">Первая команда использует командлет, `Set-Location` чтобы изменить текущее расположение на **HKEY_CURRENT_USER** диск ( `HKCU:` ) и подраздел "софтваре\микомпани\мяпп".</span><span class="sxs-lookup"><span data-stu-id="a263b-119">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the "Software\MyCompany\MyApp" subkey.</span></span>

<span data-ttu-id="a263b-120">Вторая команда использует `Remove-ItemProperty` для удаления значения реестра Options и его данных из подраздела MyApp.</span><span class="sxs-lookup"><span data-stu-id="a263b-120">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span>
<span data-ttu-id="a263b-121">Поскольку требуется **путь** , команда использует точку (".") для указания текущего расположения.</span><span class="sxs-lookup"><span data-stu-id="a263b-121">Because **Path** is required, the command uses a dot ('.') to indicate the current location.</span></span>
<span data-ttu-id="a263b-122">Для указания удаляемого значения реестра используется **имя** .</span><span class="sxs-lookup"><span data-stu-id="a263b-122">It uses **Name** to specify which registry value to delete.</span></span>
<span data-ttu-id="a263b-123">Он использует параметр **Confirm** , чтобы запросить запрос пользователя перед удалением значения.</span><span class="sxs-lookup"><span data-stu-id="a263b-123">It uses the **Confirm** parameter to request a user prompt before deleting the value.</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### <span data-ttu-id="a263b-124">Пример 3. Удаление значения реестра с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="a263b-124">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="a263b-125">Эта команда удаляет значение реестра "NoOfEmployees" и его данные из раздела реестра "Hklm\software\mycompany.".</span><span class="sxs-lookup"><span data-stu-id="a263b-125">This command deletes the "NoOfEmployees" registry value, and its data, from the "HKLM\Software\MyCompany" registry key.</span></span>

<span data-ttu-id="a263b-126">Команда использует `Get-Item` командлет для получения элемента, представляющего раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="a263b-126">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="a263b-127">Для отправки объекта в используется оператор конвейера ( `|` ) `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="a263b-127">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="a263b-128">Затем **Name** `Remove-ItemProperty` для указания имени значения реестра используется параметр name аргумента.</span><span class="sxs-lookup"><span data-stu-id="a263b-128">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

## <span data-ttu-id="a263b-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a263b-129">PARAMETERS</span></span>

### <span data-ttu-id="a263b-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="a263b-130">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a263b-131">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a263b-131">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a263b-132">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="a263b-132">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a263b-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="a263b-133">-Exclude</span></span>

<span data-ttu-id="a263b-134">Указывает элементы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="a263b-134">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="a263b-135">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a263b-135">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a263b-136">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="a263b-136">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a263b-137">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a263b-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a263b-138">-Filter</span><span class="sxs-lookup"><span data-stu-id="a263b-138">-Filter</span></span>

<span data-ttu-id="a263b-139">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="a263b-139">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="a263b-140">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a263b-140">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="a263b-141">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="a263b-141">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="a263b-142">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="a263b-142">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a263b-143">-Force</span><span class="sxs-lookup"><span data-stu-id="a263b-143">-Force</span></span>

<span data-ttu-id="a263b-144">Заставляет командлет удалить свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a263b-144">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="a263b-145">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="a263b-145">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="a263b-146">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a263b-146">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="a263b-147">-Include</span><span class="sxs-lookup"><span data-stu-id="a263b-147">-Include</span></span>

<span data-ttu-id="a263b-148">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="a263b-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="a263b-149">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a263b-149">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a263b-150">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="a263b-150">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a263b-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a263b-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a263b-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a263b-152">-LiteralPath</span></span>

<span data-ttu-id="a263b-153">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="a263b-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="a263b-154">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="a263b-154">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="a263b-155">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="a263b-155">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="a263b-156">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a263b-156">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="a263b-157">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="a263b-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a263b-158">-Name</span><span class="sxs-lookup"><span data-stu-id="a263b-158">-Name</span></span>

<span data-ttu-id="a263b-159">Задает имена удаляемых свойств.</span><span class="sxs-lookup"><span data-stu-id="a263b-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="a263b-160">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a263b-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a263b-161">-Path</span><span class="sxs-lookup"><span data-stu-id="a263b-161">-Path</span></span>

<span data-ttu-id="a263b-162">Указывает путь к элементу, свойства которого удаляются.</span><span class="sxs-lookup"><span data-stu-id="a263b-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="a263b-163">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a263b-163">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a263b-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="a263b-164">-UseTransaction</span></span>

<span data-ttu-id="a263b-165">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a263b-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="a263b-166">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="a263b-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="a263b-167">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="a263b-167">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a263b-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a263b-168">-Confirm</span></span>

<span data-ttu-id="a263b-169">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a263b-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a263b-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a263b-170">-WhatIf</span></span>

<span data-ttu-id="a263b-171">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a263b-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a263b-172">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a263b-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a263b-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a263b-173">CommonParameters</span></span>

<span data-ttu-id="a263b-174">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a263b-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a263b-175">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a263b-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a263b-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a263b-176">INPUTS</span></span>

### <span data-ttu-id="a263b-177">System.String</span><span class="sxs-lookup"><span data-stu-id="a263b-177">System.String</span></span>

<span data-ttu-id="a263b-178">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="a263b-178">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="a263b-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a263b-179">OUTPUTS</span></span>

### <span data-ttu-id="a263b-180">Нет</span><span class="sxs-lookup"><span data-stu-id="a263b-180">None</span></span>

<span data-ttu-id="a263b-181">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a263b-181">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="a263b-182">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a263b-182">NOTES</span></span>

<span data-ttu-id="a263b-183">В поставщике реестра PowerShell значения реестра считаются свойствами раздела или подраздела реестра.</span><span class="sxs-lookup"><span data-stu-id="a263b-183">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="a263b-184">Для управления этими значениями можно использовать командлеты **ItemProperty** .</span><span class="sxs-lookup"><span data-stu-id="a263b-184">You can use the **ItemProperty** cmdlets to manage these values.</span></span>

<span data-ttu-id="a263b-185">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a263b-185">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a263b-186">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="a263b-186">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a263b-187">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="a263b-187">For more information, see about_Providers.</span></span>

## <span data-ttu-id="a263b-188">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a263b-188">RELATED LINKS</span></span>

[<span data-ttu-id="a263b-189">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a263b-189">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a263b-190">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-190">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="a263b-191">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-191">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="a263b-192">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-192">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="a263b-193">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-193">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="a263b-194">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-194">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="a263b-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a263b-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="a263b-196">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-196">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="a263b-197">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a263b-197">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="a263b-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a263b-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

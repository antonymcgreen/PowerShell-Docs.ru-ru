---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 870d8e9797ff2cfce14034706f704c0e1c954fc2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600484"
---
# <span data-ttu-id="3c8ff-102">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-102">Remove-ItemProperty</span></span>

## <span data-ttu-id="3c8ff-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3c8ff-103">SYNOPSIS</span></span>
<span data-ttu-id="3c8ff-104">Удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-104">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="3c8ff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c8ff-105">SYNTAX</span></span>

### <span data-ttu-id="3c8ff-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3c8ff-106">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3c8ff-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3c8ff-107">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3c8ff-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c8ff-108">DESCRIPTION</span></span>

<span data-ttu-id="3c8ff-109">`Remove-ItemProperty`Командлет удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-109">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="3c8ff-110">Его можно использовать для удаления параметров реестра и их значений.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-110">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="3c8ff-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c8ff-111">EXAMPLES</span></span>

### <span data-ttu-id="3c8ff-112">Пример 1. Удаление значения реестра</span><span class="sxs-lookup"><span data-stu-id="3c8ff-112">Example 1: Delete a registry value</span></span>

<span data-ttu-id="3c8ff-113">Эта команда удаляет значение реестра "Смппроперти" и его данные из подраздела "Смпаппликатион" `HKEY_LOCAL_MACHINE\Software` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-113">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="3c8ff-114">Поскольку команда выполняется с диска файловой системы ( `PS C:\>` ), она включает полный путь к подразделу "смпаппликатион", включая диск, `HKLM:` и ключ "Software".</span><span class="sxs-lookup"><span data-stu-id="3c8ff-114">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="3c8ff-115">Пример 2. Удаление значения реестра из расположения HKCU</span><span class="sxs-lookup"><span data-stu-id="3c8ff-115">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="3c8ff-116">Эти команды удаляют значение реестра Options и его данные из подраздела "MyApp" в "HKEY_CURRENT_USER\Software\MyCompany".</span><span class="sxs-lookup"><span data-stu-id="3c8ff-116">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="3c8ff-117">Первая команда использует командлет, `Set-Location` чтобы изменить текущее расположение на **HKEY_CURRENT_USER** диск ( `HKCU:` ) и `Software\MyCompany\MyApp` подраздел.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-117">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="3c8ff-118">Вторая команда использует `Remove-ItemProperty` для удаления значения реестра Options и его данных из подраздела MyApp.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-118">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="3c8ff-119">Поскольку требуется **путь** , команда использует точку ( `.` ) для указания текущего расположения.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-119">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="3c8ff-120">Параметр **Confirm** запрашивает у пользователя запрос перед удалением значения.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-120">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="3c8ff-121">Пример 3. Удаление значения реестра с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="3c8ff-121">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="3c8ff-122">Эта команда удаляет значение реестра "NoOfEmployees" и его данные из `HKLM\Software\MyCompany` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-122">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="3c8ff-123">Команда использует `Get-Item` командлет для получения элемента, представляющего раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-123">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="3c8ff-124">Для отправки объекта в используется оператор конвейера ( `|` ) `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-124">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="3c8ff-125">Затем  `Remove-ItemProperty` для указания имени значения реестра используется параметр name аргумента.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-125">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="3c8ff-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c8ff-126">PARAMETERS</span></span>

### <span data-ttu-id="3c8ff-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="3c8ff-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3c8ff-128">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3c8ff-129">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="3c8ff-130">-Exclude</span><span class="sxs-lookup"><span data-stu-id="3c8ff-130">-Exclude</span></span>

<span data-ttu-id="3c8ff-131">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="3c8ff-132">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3c8ff-133">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="3c8ff-134">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="3c8ff-135">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3c8ff-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="3c8ff-136">-Filter</span></span>

<span data-ttu-id="3c8ff-137">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3c8ff-138">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="3c8ff-139">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="3c8ff-140">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="3c8ff-141">-Force</span><span class="sxs-lookup"><span data-stu-id="3c8ff-141">-Force</span></span>

<span data-ttu-id="3c8ff-142">Заставляет командлет удалить свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-142">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="3c8ff-143">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="3c8ff-144">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="3c8ff-145">-Include</span><span class="sxs-lookup"><span data-stu-id="3c8ff-145">-Include</span></span>

<span data-ttu-id="3c8ff-146">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3c8ff-147">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3c8ff-148">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3c8ff-149">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="3c8ff-150">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3c8ff-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3c8ff-151">-LiteralPath</span></span>

<span data-ttu-id="3c8ff-152">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3c8ff-153">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="3c8ff-154">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3c8ff-155">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3c8ff-156">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3c8ff-157">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3c8ff-158">-Name</span><span class="sxs-lookup"><span data-stu-id="3c8ff-158">-Name</span></span>

<span data-ttu-id="3c8ff-159">Задает имена удаляемых свойств.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="3c8ff-160">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3c8ff-161">-Path</span><span class="sxs-lookup"><span data-stu-id="3c8ff-161">-Path</span></span>

<span data-ttu-id="3c8ff-162">Указывает путь к элементу, свойства которого удаляются.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="3c8ff-163">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3c8ff-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3c8ff-164">-Confirm</span></span>

<span data-ttu-id="3c8ff-165">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3c8ff-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3c8ff-166">-WhatIf</span></span>

<span data-ttu-id="3c8ff-167">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3c8ff-168">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3c8ff-169">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3c8ff-169">CommonParameters</span></span>

<span data-ttu-id="3c8ff-170">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3c8ff-171">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3c8ff-172">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3c8ff-172">INPUTS</span></span>

### <span data-ttu-id="3c8ff-173">System.String</span><span class="sxs-lookup"><span data-stu-id="3c8ff-173">System.String</span></span>

<span data-ttu-id="3c8ff-174">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-174">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="3c8ff-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3c8ff-175">OUTPUTS</span></span>

### <span data-ttu-id="3c8ff-176">None</span><span class="sxs-lookup"><span data-stu-id="3c8ff-176">None</span></span>

<span data-ttu-id="3c8ff-177">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-177">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="3c8ff-178">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3c8ff-178">NOTES</span></span>

- <span data-ttu-id="3c8ff-179">В поставщике реестра PowerShell значения реестра считаются свойствами раздела или подраздела реестра.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-179">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="3c8ff-180">Для управления этими значениями можно использовать командлеты **ItemProperty** .</span><span class="sxs-lookup"><span data-stu-id="3c8ff-180">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="3c8ff-181">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-181">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3c8ff-182">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="3c8ff-182">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3c8ff-183">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ff-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3c8ff-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3c8ff-184">RELATED LINKS</span></span>

[<span data-ttu-id="3c8ff-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3c8ff-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="3c8ff-186">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-186">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="3c8ff-187">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-187">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="3c8ff-188">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-188">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="3c8ff-189">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-189">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="3c8ff-190">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-190">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="3c8ff-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="3c8ff-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="3c8ff-192">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-192">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="3c8ff-193">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3c8ff-193">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="3c8ff-194">Set-Location</span><span class="sxs-lookup"><span data-stu-id="3c8ff-194">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="3c8ff-195">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3c8ff-195">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


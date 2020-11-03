---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 2daf4d9dacc0f15ab5347fff4bec831be25d97a6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225553"
---
# <span data-ttu-id="d88ed-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="d88ed-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d88ed-104">SYNOPSIS</span></span>
<span data-ttu-id="d88ed-105">Удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="d88ed-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="d88ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d88ed-106">SYNTAX</span></span>

### <span data-ttu-id="d88ed-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d88ed-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d88ed-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d88ed-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d88ed-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d88ed-109">DESCRIPTION</span></span>

<span data-ttu-id="d88ed-110">`Remove-ItemProperty`Командлет удаляет свойство и его значение из элемента.</span><span class="sxs-lookup"><span data-stu-id="d88ed-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="d88ed-111">Его можно использовать для удаления параметров реестра и их значений.</span><span class="sxs-lookup"><span data-stu-id="d88ed-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="d88ed-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="d88ed-112">EXAMPLES</span></span>

### <span data-ttu-id="d88ed-113">Пример 1. Удаление значения реестра</span><span class="sxs-lookup"><span data-stu-id="d88ed-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="d88ed-114">Эта команда удаляет значение реестра "Смппроперти" и его данные из подраздела "Смпаппликатион" `HKEY_LOCAL_MACHINE\Software` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="d88ed-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="d88ed-115">Поскольку команда выполняется с диска файловой системы ( `PS C:\>` ), она включает полный путь к подразделу "смпаппликатион", включая диск, `HKLM:` и ключ "Software".</span><span class="sxs-lookup"><span data-stu-id="d88ed-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="d88ed-116">Пример 2. Удаление значения реестра из расположения HKCU</span><span class="sxs-lookup"><span data-stu-id="d88ed-116">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="d88ed-117">Эти команды удаляют значение реестра Options и его данные из подраздела "MyApp" в "HKEY_CURRENT_USER\Software\MyCompany".</span><span class="sxs-lookup"><span data-stu-id="d88ed-117">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="d88ed-118">Первая команда использует командлет, `Set-Location` чтобы изменить текущее расположение на **HKEY_CURRENT_USER** диск ( `HKCU:` ) и `Software\MyCompany\MyApp` подраздел.</span><span class="sxs-lookup"><span data-stu-id="d88ed-118">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="d88ed-119">Вторая команда использует `Remove-ItemProperty` для удаления значения реестра Options и его данных из подраздела MyApp.</span><span class="sxs-lookup"><span data-stu-id="d88ed-119">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="d88ed-120">Поскольку требуется **путь** , команда использует точку ( `.` ) для указания текущего расположения.</span><span class="sxs-lookup"><span data-stu-id="d88ed-120">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="d88ed-121">Параметр **Confirm** запрашивает у пользователя запрос перед удалением значения.</span><span class="sxs-lookup"><span data-stu-id="d88ed-121">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="d88ed-122">Пример 3. Удаление значения реестра с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="d88ed-122">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="d88ed-123">Эта команда удаляет значение реестра "NoOfEmployees" и его данные из `HKLM\Software\MyCompany` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="d88ed-123">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="d88ed-124">Команда использует `Get-Item` командлет для получения элемента, представляющего раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="d88ed-124">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="d88ed-125">Для отправки объекта в используется оператор конвейера ( `|` ) `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="d88ed-125">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="d88ed-126">Затем **Name** `Remove-ItemProperty` для указания имени значения реестра используется параметр name аргумента.</span><span class="sxs-lookup"><span data-stu-id="d88ed-126">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="d88ed-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d88ed-127">PARAMETERS</span></span>

### <span data-ttu-id="d88ed-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="d88ed-128">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d88ed-129">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d88ed-129">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d88ed-130">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-130">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d88ed-131">-Exclude</span><span class="sxs-lookup"><span data-stu-id="d88ed-131">-Exclude</span></span>

<span data-ttu-id="d88ed-132">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="d88ed-132">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d88ed-133">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="d88ed-133">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d88ed-134">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d88ed-134">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d88ed-135">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="d88ed-136">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="d88ed-136">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d88ed-137">-Filter</span><span class="sxs-lookup"><span data-stu-id="d88ed-137">-Filter</span></span>

<span data-ttu-id="d88ed-138">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="d88ed-138">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d88ed-139">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="d88ed-139">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d88ed-140">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-140">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d88ed-141">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="d88ed-141">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d88ed-142">-Force</span><span class="sxs-lookup"><span data-stu-id="d88ed-142">-Force</span></span>

<span data-ttu-id="d88ed-143">Заставляет командлет удалить свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="d88ed-143">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="d88ed-144">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="d88ed-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="d88ed-145">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="d88ed-146">-Include</span><span class="sxs-lookup"><span data-stu-id="d88ed-146">-Include</span></span>

<span data-ttu-id="d88ed-147">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="d88ed-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d88ed-148">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="d88ed-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d88ed-149">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="d88ed-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d88ed-150">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="d88ed-151">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="d88ed-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d88ed-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d88ed-152">-LiteralPath</span></span>

<span data-ttu-id="d88ed-153">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="d88ed-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d88ed-154">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="d88ed-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d88ed-155">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d88ed-156">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d88ed-157">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="d88ed-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d88ed-158">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="d88ed-159">-Name</span><span class="sxs-lookup"><span data-stu-id="d88ed-159">-Name</span></span>

<span data-ttu-id="d88ed-160">Задает имена удаляемых свойств.</span><span class="sxs-lookup"><span data-stu-id="d88ed-160">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="d88ed-161">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-161">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d88ed-162">-Path</span><span class="sxs-lookup"><span data-stu-id="d88ed-162">-Path</span></span>

<span data-ttu-id="d88ed-163">Указывает путь к элементу, свойства которого удаляются.</span><span class="sxs-lookup"><span data-stu-id="d88ed-163">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="d88ed-164">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d88ed-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d88ed-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d88ed-165">-Confirm</span></span>

<span data-ttu-id="d88ed-166">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d88ed-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d88ed-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d88ed-167">-WhatIf</span></span>

<span data-ttu-id="d88ed-168">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d88ed-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d88ed-169">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d88ed-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d88ed-170">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d88ed-170">CommonParameters</span></span>

<span data-ttu-id="d88ed-171">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d88ed-171">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d88ed-172">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-172">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d88ed-173">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d88ed-173">INPUTS</span></span>

### <span data-ttu-id="d88ed-174">System.String</span><span class="sxs-lookup"><span data-stu-id="d88ed-174">System.String</span></span>

<span data-ttu-id="d88ed-175">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="d88ed-175">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="d88ed-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d88ed-176">OUTPUTS</span></span>

### <span data-ttu-id="d88ed-177">Нет</span><span class="sxs-lookup"><span data-stu-id="d88ed-177">None</span></span>

<span data-ttu-id="d88ed-178">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d88ed-178">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="d88ed-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d88ed-179">NOTES</span></span>

- <span data-ttu-id="d88ed-180">В поставщике реестра PowerShell значения реестра считаются свойствами раздела или подраздела реестра.</span><span class="sxs-lookup"><span data-stu-id="d88ed-180">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="d88ed-181">Для управления этими значениями можно использовать командлеты **ItemProperty** .</span><span class="sxs-lookup"><span data-stu-id="d88ed-181">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="d88ed-182">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="d88ed-182">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d88ed-183">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="d88ed-183">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d88ed-184">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d88ed-184">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d88ed-185">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d88ed-185">RELATED LINKS</span></span>

[<span data-ttu-id="d88ed-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d88ed-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="d88ed-187">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-187">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d88ed-188">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-188">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d88ed-189">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-189">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d88ed-190">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-190">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d88ed-191">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-191">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d88ed-192">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d88ed-192">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d88ed-193">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-193">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="d88ed-194">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d88ed-194">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d88ed-195">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d88ed-195">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="d88ed-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d88ed-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 4cf883964e1ff86487bf5abca8789af62b274c8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227977"
---
# <span data-ttu-id="b64ef-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-103">Move-ItemProperty</span></span>

## <span data-ttu-id="b64ef-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b64ef-104">Synopsis</span></span>
<span data-ttu-id="b64ef-105">Перемещает свойство из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="b64ef-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="b64ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b64ef-106">SYNTAX</span></span>

### <span data-ttu-id="b64ef-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b64ef-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b64ef-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b64ef-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b64ef-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b64ef-109">Description</span></span>

<span data-ttu-id="b64ef-110">`Move-ItemProperty`Командлет перемещает свойство элемента из одного элемента в другой элемент.</span><span class="sxs-lookup"><span data-stu-id="b64ef-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="b64ef-111">Например, с его помощью можно переместить запись реестра из одного раздела реестра в другой.</span><span class="sxs-lookup"><span data-stu-id="b64ef-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="b64ef-112">При перемещении свойства элемента оно добавляется в новом месте и удаляется из прежнего.</span><span class="sxs-lookup"><span data-stu-id="b64ef-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="b64ef-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b64ef-113">EXAMPLES</span></span>

### <span data-ttu-id="b64ef-114">Пример 1. Перенос значения реестра и его данных в другой раздел</span><span class="sxs-lookup"><span data-stu-id="b64ef-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="b64ef-115">Эта команда перемещает значение реестра версии и его данные из подраздела MyApp в подраздел NewApp `HKLM\Software\MyCompany` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="b64ef-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="b64ef-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b64ef-116">PARAMETERS</span></span>

### <span data-ttu-id="b64ef-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="b64ef-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b64ef-118">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b64ef-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b64ef-119">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="b64ef-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b64ef-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="b64ef-120">-Destination</span></span>

<span data-ttu-id="b64ef-121">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="b64ef-121">Specifies the path to the destination location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b64ef-122">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b64ef-122">-Exclude</span></span>

<span data-ttu-id="b64ef-123">Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="b64ef-123">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="b64ef-124">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="b64ef-124">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b64ef-125">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="b64ef-125">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b64ef-126">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b64ef-126">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b64ef-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="b64ef-127">-Filter</span></span>

<span data-ttu-id="b64ef-128">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="b64ef-128">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="b64ef-129">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="b64ef-129">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="b64ef-130">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="b64ef-130">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="b64ef-131">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="b64ef-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b64ef-132">-Force</span><span class="sxs-lookup"><span data-stu-id="b64ef-132">-Force</span></span>

<span data-ttu-id="b64ef-133">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="b64ef-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="b64ef-134">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="b64ef-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="b64ef-135">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b64ef-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="b64ef-136">-Include</span><span class="sxs-lookup"><span data-stu-id="b64ef-136">-Include</span></span>

<span data-ttu-id="b64ef-137">Указывает в виде массива строк свойство или свойство, которое этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="b64ef-137">Specifies, as a string array, a property or property that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="b64ef-138">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="b64ef-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b64ef-139">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="b64ef-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b64ef-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b64ef-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b64ef-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b64ef-141">-LiteralPath</span></span>

<span data-ttu-id="b64ef-142">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="b64ef-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="b64ef-143">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b64ef-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="b64ef-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b64ef-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b64ef-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b64ef-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b64ef-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b64ef-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="b64ef-147">-Name</span><span class="sxs-lookup"><span data-stu-id="b64ef-147">-Name</span></span>

<span data-ttu-id="b64ef-148">Указывает имя свойства, которое нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="b64ef-148">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b64ef-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b64ef-149">-PassThru</span></span>

<span data-ttu-id="b64ef-150">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="b64ef-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b64ef-151">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b64ef-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b64ef-152">-Path</span><span class="sxs-lookup"><span data-stu-id="b64ef-152">-Path</span></span>

<span data-ttu-id="b64ef-153">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="b64ef-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="b64ef-154">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b64ef-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b64ef-155">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b64ef-155">-UseTransaction</span></span>

<span data-ttu-id="b64ef-156">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b64ef-156">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b64ef-157">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="b64ef-157">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b64ef-158">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="b64ef-158">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="b64ef-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b64ef-159">-Confirm</span></span>

<span data-ttu-id="b64ef-160">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b64ef-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b64ef-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b64ef-161">-WhatIf</span></span>

<span data-ttu-id="b64ef-162">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b64ef-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b64ef-163">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b64ef-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b64ef-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b64ef-164">CommonParameters</span></span>

<span data-ttu-id="b64ef-165">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b64ef-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b64ef-166">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b64ef-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b64ef-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b64ef-167">INPUTS</span></span>

### <span data-ttu-id="b64ef-168">System.String</span><span class="sxs-lookup"><span data-stu-id="b64ef-168">System.String</span></span>

<span data-ttu-id="b64ef-169">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="b64ef-169">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b64ef-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b64ef-170">OUTPUTS</span></span>

### <span data-ttu-id="b64ef-171">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b64ef-171">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="b64ef-172">При использовании параметра **PassThru** этот командлет создает объект **PSCustomObject** , представляющий перемещенное свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="b64ef-172">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span>
<span data-ttu-id="b64ef-173">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b64ef-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b64ef-174">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b64ef-174">NOTES</span></span>

<span data-ttu-id="b64ef-175">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="b64ef-175">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b64ef-176">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="b64ef-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b64ef-177">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b64ef-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b64ef-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b64ef-178">RELATED LINKS</span></span>

[<span data-ttu-id="b64ef-179">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-179">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b64ef-180">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-180">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="b64ef-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b64ef-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b64ef-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="b64ef-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b64ef-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b64ef-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b64ef-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b64ef-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

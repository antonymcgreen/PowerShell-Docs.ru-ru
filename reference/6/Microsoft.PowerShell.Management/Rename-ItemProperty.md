---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 3768a24438b0cc33711ebe61dc63c57c27bac976
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226821"
---
# <span data-ttu-id="cd936-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="cd936-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cd936-104">SYNOPSIS</span></span>
<span data-ttu-id="cd936-105">Переименовывает свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="cd936-105">Renames a property of an item.</span></span>

## <span data-ttu-id="cd936-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd936-106">SYNTAX</span></span>

### <span data-ttu-id="cd936-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cd936-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cd936-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cd936-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cd936-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd936-109">DESCRIPTION</span></span>

<span data-ttu-id="cd936-110">`Rename-ItemProperty`Командлет изменяет имя указанного свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="cd936-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="cd936-111">Значение свойства не меняется.</span><span class="sxs-lookup"><span data-stu-id="cd936-111">The value of the property is not changed.</span></span>
<span data-ttu-id="cd936-112">Например, можно использовать `Rename-ItemProperty` для изменения имени записи реестра.</span><span class="sxs-lookup"><span data-stu-id="cd936-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="cd936-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="cd936-113">EXAMPLES</span></span>

### <span data-ttu-id="cd936-114">Пример 1. Переименование записи реестра</span><span class="sxs-lookup"><span data-stu-id="cd936-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="cd936-115">Эта команда переименовывает запись реестра конфигурации, содержащуюся в разделе, в значение `HKEY_LOCAL_MACHINE\Software\SmpApplication` «олдконфиг».</span><span class="sxs-lookup"><span data-stu-id="cd936-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="cd936-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd936-116">PARAMETERS</span></span>

### <span data-ttu-id="cd936-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="cd936-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="cd936-118">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd936-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="cd936-119">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="cd936-120">-Exclude</span><span class="sxs-lookup"><span data-stu-id="cd936-120">-Exclude</span></span>

<span data-ttu-id="cd936-121">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="cd936-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="cd936-122">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="cd936-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="cd936-123">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="cd936-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="cd936-124">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cd936-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="cd936-125">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="cd936-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="cd936-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="cd936-126">-Filter</span></span>

<span data-ttu-id="cd936-127">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="cd936-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="cd936-128">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="cd936-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="cd936-129">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="cd936-130">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="cd936-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="cd936-131">-Force</span><span class="sxs-lookup"><span data-stu-id="cd936-131">-Force</span></span>

<span data-ttu-id="cd936-132">Заставляет командлет переименовать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd936-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="cd936-133">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="cd936-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="cd936-134">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="cd936-135">-Include</span><span class="sxs-lookup"><span data-stu-id="cd936-135">-Include</span></span>

<span data-ttu-id="cd936-136">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="cd936-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="cd936-137">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="cd936-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="cd936-138">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="cd936-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="cd936-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cd936-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="cd936-140">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="cd936-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="cd936-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cd936-141">-LiteralPath</span></span>

<span data-ttu-id="cd936-142">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="cd936-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="cd936-143">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="cd936-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="cd936-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="cd936-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="cd936-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="cd936-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="cd936-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="cd936-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="cd936-147">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd936-148">-Name</span><span class="sxs-lookup"><span data-stu-id="cd936-148">-Name</span></span>

<span data-ttu-id="cd936-149">Задает текущее имя свойства для переименования.</span><span class="sxs-lookup"><span data-stu-id="cd936-149">Specifies the current name of the property to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd936-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="cd936-150">-NewName</span></span>

<span data-ttu-id="cd936-151">Задает новое имя свойства.</span><span class="sxs-lookup"><span data-stu-id="cd936-151">Specifies the new name for the property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd936-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cd936-152">-PassThru</span></span>

<span data-ttu-id="cd936-153">Возвращает объект, представляющий свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="cd936-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="cd936-154">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cd936-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cd936-155">-Path</span><span class="sxs-lookup"><span data-stu-id="cd936-155">-Path</span></span>

<span data-ttu-id="cd936-156">Указывает путь к элементу для переименования.</span><span class="sxs-lookup"><span data-stu-id="cd936-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="cd936-157">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cd936-157">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="cd936-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cd936-158">-Confirm</span></span>

<span data-ttu-id="cd936-159">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cd936-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cd936-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cd936-160">-WhatIf</span></span>

<span data-ttu-id="cd936-161">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cd936-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cd936-162">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cd936-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cd936-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cd936-163">CommonParameters</span></span>

<span data-ttu-id="cd936-164">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="cd936-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="cd936-165">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cd936-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cd936-166">INPUTS</span></span>

### <span data-ttu-id="cd936-167">System.String</span><span class="sxs-lookup"><span data-stu-id="cd936-167">System.String</span></span>

<span data-ttu-id="cd936-168">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="cd936-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="cd936-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cd936-169">OUTPUTS</span></span>

### <span data-ttu-id="cd936-170">Нет, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="cd936-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="cd936-171">Этот командлет создает объект **PSCustomObject** , представляющий переименованное свойство Item, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="cd936-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="cd936-172">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cd936-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cd936-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cd936-173">NOTES</span></span>

<span data-ttu-id="cd936-174">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="cd936-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="cd936-175">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="cd936-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="cd936-176">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="cd936-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="cd936-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cd936-177">RELATED LINKS</span></span>

[<span data-ttu-id="cd936-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="cd936-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="cd936-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="cd936-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="cd936-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="cd936-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="cd936-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="cd936-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="cd936-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cd936-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="cd936-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cd936-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

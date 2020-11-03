---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: d9403a2572926101a7ccab8992013b60e4fb77f4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226097"
---
# <span data-ttu-id="95faa-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="95faa-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="95faa-104">SYNOPSIS</span></span>
<span data-ttu-id="95faa-105">Переименовывает свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="95faa-105">Renames a property of an item.</span></span>

## <span data-ttu-id="95faa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95faa-106">SYNTAX</span></span>

### <span data-ttu-id="95faa-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="95faa-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="95faa-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="95faa-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="95faa-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95faa-109">DESCRIPTION</span></span>

<span data-ttu-id="95faa-110">`Rename-ItemProperty`Командлет изменяет имя указанного свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="95faa-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="95faa-111">Значение свойства не меняется.</span><span class="sxs-lookup"><span data-stu-id="95faa-111">The value of the property is not changed.</span></span>
<span data-ttu-id="95faa-112">Например, можно использовать `Rename-ItemProperty` для изменения имени записи реестра.</span><span class="sxs-lookup"><span data-stu-id="95faa-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="95faa-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="95faa-113">EXAMPLES</span></span>

### <span data-ttu-id="95faa-114">Пример 1. Переименование записи реестра</span><span class="sxs-lookup"><span data-stu-id="95faa-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="95faa-115">Эта команда переименовывает запись реестра конфигурации, содержащуюся в разделе, в значение `HKEY_LOCAL_MACHINE\Software\SmpApplication` «олдконфиг».</span><span class="sxs-lookup"><span data-stu-id="95faa-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="95faa-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95faa-116">PARAMETERS</span></span>

### <span data-ttu-id="95faa-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="95faa-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="95faa-118">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95faa-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="95faa-119">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="95faa-120">-Exclude</span><span class="sxs-lookup"><span data-stu-id="95faa-120">-Exclude</span></span>

<span data-ttu-id="95faa-121">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="95faa-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="95faa-122">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="95faa-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="95faa-123">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="95faa-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="95faa-124">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="95faa-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="95faa-125">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="95faa-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="95faa-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="95faa-126">-Filter</span></span>

<span data-ttu-id="95faa-127">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="95faa-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="95faa-128">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="95faa-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="95faa-129">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="95faa-130">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="95faa-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="95faa-131">-Force</span><span class="sxs-lookup"><span data-stu-id="95faa-131">-Force</span></span>

<span data-ttu-id="95faa-132">Заставляет командлет переименовать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="95faa-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="95faa-133">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="95faa-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="95faa-134">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="95faa-135">-Include</span><span class="sxs-lookup"><span data-stu-id="95faa-135">-Include</span></span>

<span data-ttu-id="95faa-136">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="95faa-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="95faa-137">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="95faa-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="95faa-138">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="95faa-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="95faa-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="95faa-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="95faa-140">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="95faa-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="95faa-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="95faa-141">-LiteralPath</span></span>

<span data-ttu-id="95faa-142">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="95faa-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="95faa-143">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="95faa-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="95faa-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="95faa-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="95faa-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="95faa-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="95faa-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="95faa-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="95faa-147">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="95faa-148">-Name</span><span class="sxs-lookup"><span data-stu-id="95faa-148">-Name</span></span>

<span data-ttu-id="95faa-149">Задает текущее имя свойства для переименования.</span><span class="sxs-lookup"><span data-stu-id="95faa-149">Specifies the current name of the property to rename.</span></span>

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

### <span data-ttu-id="95faa-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="95faa-150">-NewName</span></span>

<span data-ttu-id="95faa-151">Задает новое имя свойства.</span><span class="sxs-lookup"><span data-stu-id="95faa-151">Specifies the new name for the property.</span></span>

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

### <span data-ttu-id="95faa-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="95faa-152">-PassThru</span></span>

<span data-ttu-id="95faa-153">Возвращает объект, представляющий свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="95faa-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="95faa-154">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="95faa-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="95faa-155">-Path</span><span class="sxs-lookup"><span data-stu-id="95faa-155">-Path</span></span>

<span data-ttu-id="95faa-156">Указывает путь к элементу для переименования.</span><span class="sxs-lookup"><span data-stu-id="95faa-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="95faa-157">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="95faa-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="95faa-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="95faa-158">-Confirm</span></span>

<span data-ttu-id="95faa-159">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="95faa-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="95faa-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="95faa-160">-WhatIf</span></span>

<span data-ttu-id="95faa-161">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="95faa-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="95faa-162">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="95faa-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="95faa-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="95faa-163">CommonParameters</span></span>

<span data-ttu-id="95faa-164">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="95faa-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="95faa-165">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="95faa-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="95faa-166">INPUTS</span></span>

### <span data-ttu-id="95faa-167">System.String</span><span class="sxs-lookup"><span data-stu-id="95faa-167">System.String</span></span>

<span data-ttu-id="95faa-168">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="95faa-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="95faa-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="95faa-169">OUTPUTS</span></span>

### <span data-ttu-id="95faa-170">Нет, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="95faa-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="95faa-171">Этот командлет создает объект **PSCustomObject** , представляющий переименованное свойство Item, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="95faa-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="95faa-172">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="95faa-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="95faa-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="95faa-173">NOTES</span></span>

<span data-ttu-id="95faa-174">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="95faa-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="95faa-175">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="95faa-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="95faa-176">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="95faa-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="95faa-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="95faa-177">RELATED LINKS</span></span>

[<span data-ttu-id="95faa-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="95faa-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="95faa-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="95faa-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="95faa-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="95faa-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="95faa-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="95faa-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="95faa-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="95faa-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="95faa-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="95faa-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

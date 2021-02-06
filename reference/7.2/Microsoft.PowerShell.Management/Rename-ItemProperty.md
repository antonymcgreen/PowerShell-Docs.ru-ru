---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 4fbd2677d6a978d4d144effe9607bceb376ad43f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604099"
---
# <span data-ttu-id="c0886-102">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-102">Rename-ItemProperty</span></span>

## <span data-ttu-id="c0886-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c0886-103">SYNOPSIS</span></span>
<span data-ttu-id="c0886-104">Переименовывает свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="c0886-104">Renames a property of an item.</span></span>

## <span data-ttu-id="c0886-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0886-105">SYNTAX</span></span>

### <span data-ttu-id="c0886-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c0886-106">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c0886-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c0886-107">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c0886-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c0886-108">DESCRIPTION</span></span>

<span data-ttu-id="c0886-109">`Rename-ItemProperty`Командлет изменяет имя указанного свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="c0886-109">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="c0886-110">Значение свойства не меняется.</span><span class="sxs-lookup"><span data-stu-id="c0886-110">The value of the property is not changed.</span></span>
<span data-ttu-id="c0886-111">Например, можно использовать `Rename-ItemProperty` для изменения имени записи реестра.</span><span class="sxs-lookup"><span data-stu-id="c0886-111">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="c0886-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="c0886-112">EXAMPLES</span></span>

### <span data-ttu-id="c0886-113">Пример 1. Переименование записи реестра</span><span class="sxs-lookup"><span data-stu-id="c0886-113">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="c0886-114">Эта команда переименовывает запись реестра конфигурации, содержащуюся в разделе, в значение `HKEY_LOCAL_MACHINE\Software\SmpApplication` «олдконфиг».</span><span class="sxs-lookup"><span data-stu-id="c0886-114">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="c0886-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c0886-115">PARAMETERS</span></span>

### <span data-ttu-id="c0886-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="c0886-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c0886-117">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0886-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c0886-118">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="c0886-119">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c0886-119">-Exclude</span></span>

<span data-ttu-id="c0886-120">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="c0886-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c0886-121">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="c0886-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c0886-122">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c0886-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c0886-123">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c0886-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="c0886-124">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c0886-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c0886-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="c0886-125">-Filter</span></span>

<span data-ttu-id="c0886-126">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="c0886-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c0886-127">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="c0886-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c0886-128">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c0886-129">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="c0886-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c0886-130">-Force</span><span class="sxs-lookup"><span data-stu-id="c0886-130">-Force</span></span>

<span data-ttu-id="c0886-131">Заставляет командлет переименовать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c0886-131">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="c0886-132">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="c0886-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c0886-133">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c0886-134">-Include</span><span class="sxs-lookup"><span data-stu-id="c0886-134">-Include</span></span>

<span data-ttu-id="c0886-135">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="c0886-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c0886-136">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="c0886-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c0886-137">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="c0886-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c0886-138">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c0886-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="c0886-139">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c0886-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c0886-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c0886-140">-LiteralPath</span></span>

<span data-ttu-id="c0886-141">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="c0886-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c0886-142">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="c0886-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c0886-143">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="c0886-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c0886-144">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c0886-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c0886-145">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0886-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c0886-146">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c0886-147">-Name</span><span class="sxs-lookup"><span data-stu-id="c0886-147">-Name</span></span>

<span data-ttu-id="c0886-148">Задает текущее имя свойства для переименования.</span><span class="sxs-lookup"><span data-stu-id="c0886-148">Specifies the current name of the property to rename.</span></span>

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

### <span data-ttu-id="c0886-149">-NewName</span><span class="sxs-lookup"><span data-stu-id="c0886-149">-NewName</span></span>

<span data-ttu-id="c0886-150">Задает новое имя свойства.</span><span class="sxs-lookup"><span data-stu-id="c0886-150">Specifies the new name for the property.</span></span>

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

### <span data-ttu-id="c0886-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c0886-151">-PassThru</span></span>

<span data-ttu-id="c0886-152">Возвращает объект, представляющий свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="c0886-152">Returns an object that represents the item property.</span></span>
<span data-ttu-id="c0886-153">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c0886-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c0886-154">-Path</span><span class="sxs-lookup"><span data-stu-id="c0886-154">-Path</span></span>

<span data-ttu-id="c0886-155">Указывает путь к элементу для переименования.</span><span class="sxs-lookup"><span data-stu-id="c0886-155">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="c0886-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c0886-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c0886-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c0886-157">-Confirm</span></span>

<span data-ttu-id="c0886-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c0886-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c0886-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c0886-159">-WhatIf</span></span>

<span data-ttu-id="c0886-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c0886-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c0886-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c0886-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c0886-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c0886-162">CommonParameters</span></span>

<span data-ttu-id="c0886-163">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="c0886-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c0886-164">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c0886-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c0886-165">INPUTS</span></span>

### <span data-ttu-id="c0886-166">System.String</span><span class="sxs-lookup"><span data-stu-id="c0886-166">System.String</span></span>

<span data-ttu-id="c0886-167">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="c0886-167">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="c0886-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c0886-168">OUTPUTS</span></span>

### <span data-ttu-id="c0886-169">Нет, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c0886-169">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="c0886-170">Этот командлет создает объект **PSCustomObject** , представляющий переименованное свойство Item, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="c0886-170">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="c0886-171">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c0886-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c0886-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c0886-172">NOTES</span></span>

<span data-ttu-id="c0886-173">`Remove-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="c0886-173">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c0886-174">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="c0886-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="c0886-175">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c0886-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c0886-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c0886-176">RELATED LINKS</span></span>

[<span data-ttu-id="c0886-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="c0886-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="c0886-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="c0886-180">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-180">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="c0886-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="c0886-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="c0886-183">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c0886-183">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c0886-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c0886-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="c0886-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c0886-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


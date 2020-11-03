---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: 22c55ab07b5524e9552808ebaf385b18e22106ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229618"
---
# <span data-ttu-id="9be52-103">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-103">Copy-ItemProperty</span></span>

## <span data-ttu-id="9be52-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9be52-104">SYNOPSIS</span></span>
<span data-ttu-id="9be52-105">Копирует свойство и его значение из одного указанного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="9be52-105">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="9be52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9be52-106">SYNTAX</span></span>

### <span data-ttu-id="9be52-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9be52-107">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9be52-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9be52-108">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9be52-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9be52-109">DESCRIPTION</span></span>

<span data-ttu-id="9be52-110">`Copy-ItemProperty`Командлет копирует свойство и значение из указанного расположения в другое расположение.</span><span class="sxs-lookup"><span data-stu-id="9be52-110">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="9be52-111">Например, с помощью этого командлета можно скопировать одну или несколько записей реестра из одного раздела реестра в другой раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="9be52-111">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="9be52-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="9be52-112">EXAMPLES</span></span>

### <span data-ttu-id="9be52-113">Пример 1. копирование свойства из раздела реестра в другой раздел реестра</span><span class="sxs-lookup"><span data-stu-id="9be52-113">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="9be52-114">Эта команда копирует свойство с именем MyProperty из раздела реестра "MyApplication" в раздел реестра "MyApplicationRev2".</span><span class="sxs-lookup"><span data-stu-id="9be52-114">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="9be52-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9be52-115">PARAMETERS</span></span>

### <span data-ttu-id="9be52-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="9be52-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9be52-117">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be52-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9be52-118">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9be52-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="9be52-119">-Destination</span></span>

<span data-ttu-id="9be52-120">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="9be52-120">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="9be52-121">-Exclude</span><span class="sxs-lookup"><span data-stu-id="9be52-121">-Exclude</span></span>

<span data-ttu-id="9be52-122">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="9be52-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9be52-123">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="9be52-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9be52-124">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="9be52-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9be52-125">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9be52-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="9be52-126">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="9be52-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9be52-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="9be52-127">-Filter</span></span>

<span data-ttu-id="9be52-128">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="9be52-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9be52-129">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="9be52-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="9be52-130">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="9be52-131">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="9be52-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="9be52-132">-Force</span><span class="sxs-lookup"><span data-stu-id="9be52-132">-Force</span></span>

<span data-ttu-id="9be52-133">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="9be52-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="9be52-134">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="9be52-134">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="9be52-135">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="9be52-136">-Include</span><span class="sxs-lookup"><span data-stu-id="9be52-136">-Include</span></span>

<span data-ttu-id="9be52-137">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="9be52-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9be52-138">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="9be52-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9be52-139">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="9be52-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="9be52-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9be52-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="9be52-141">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="9be52-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9be52-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9be52-142">-LiteralPath</span></span>

<span data-ttu-id="9be52-143">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="9be52-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9be52-144">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="9be52-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9be52-145">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="9be52-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9be52-146">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9be52-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9be52-147">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="9be52-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9be52-148">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="9be52-149">-Name</span><span class="sxs-lookup"><span data-stu-id="9be52-149">-Name</span></span>

<span data-ttu-id="9be52-150">Указывает имя свойства, которое нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="9be52-150">Specifies the name of the property to be copied.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9be52-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9be52-151">-PassThru</span></span>

<span data-ttu-id="9be52-152">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="9be52-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="9be52-153">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9be52-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9be52-154">-Path</span><span class="sxs-lookup"><span data-stu-id="9be52-154">-Path</span></span>

<span data-ttu-id="9be52-155">Указывает в виде массива строк путь к свойству, которое необходимо скопировать.</span><span class="sxs-lookup"><span data-stu-id="9be52-155">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="9be52-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9be52-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9be52-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9be52-157">-Confirm</span></span>

<span data-ttu-id="9be52-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9be52-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9be52-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9be52-159">-WhatIf</span></span>

<span data-ttu-id="9be52-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9be52-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9be52-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9be52-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9be52-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9be52-162">CommonParameters</span></span>

<span data-ttu-id="9be52-163">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="9be52-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9be52-164">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9be52-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9be52-165">INPUTS</span></span>

### <span data-ttu-id="9be52-166">System.String</span><span class="sxs-lookup"><span data-stu-id="9be52-166">System.String</span></span>

<span data-ttu-id="9be52-167">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="9be52-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9be52-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9be52-168">OUTPUTS</span></span>

### <span data-ttu-id="9be52-169">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9be52-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="9be52-170">При использовании параметра **PassThru** этот командлет создает объект **PsCustomObject** , представляющий скопированное свойство Item.</span><span class="sxs-lookup"><span data-stu-id="9be52-170">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="9be52-171">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9be52-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9be52-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9be52-172">NOTES</span></span>

<span data-ttu-id="9be52-173">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="9be52-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9be52-174">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="9be52-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9be52-175">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9be52-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9be52-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9be52-176">RELATED LINKS</span></span>

[<span data-ttu-id="9be52-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="9be52-178">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-178">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="9be52-179">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-179">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="9be52-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="9be52-181">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-181">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="9be52-182">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9be52-182">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="9be52-183">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="9be52-183">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="9be52-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9be52-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


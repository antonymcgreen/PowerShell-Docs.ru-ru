---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: d6dd6d21d7c0022e8ca1ea7dbd8e1cab8a680de6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599391"
---
# <span data-ttu-id="36802-102">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-102">Copy-ItemProperty</span></span>

## <span data-ttu-id="36802-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="36802-103">SYNOPSIS</span></span>
<span data-ttu-id="36802-104">Копирует свойство и его значение из одного указанного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="36802-104">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="36802-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36802-105">SYNTAX</span></span>

### <span data-ttu-id="36802-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="36802-106">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="36802-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="36802-107">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="36802-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36802-108">DESCRIPTION</span></span>

<span data-ttu-id="36802-109">`Copy-ItemProperty`Командлет копирует свойство и значение из указанного расположения в другое расположение.</span><span class="sxs-lookup"><span data-stu-id="36802-109">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="36802-110">Например, с помощью этого командлета можно скопировать одну или несколько записей реестра из одного раздела реестра в другой раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="36802-110">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="36802-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="36802-111">EXAMPLES</span></span>

### <span data-ttu-id="36802-112">Пример 1. копирование свойства из раздела реестра в другой раздел реестра</span><span class="sxs-lookup"><span data-stu-id="36802-112">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="36802-113">Эта команда копирует свойство с именем MyProperty из раздела реестра "MyApplication" в раздел реестра "MyApplicationRev2".</span><span class="sxs-lookup"><span data-stu-id="36802-113">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="36802-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36802-114">PARAMETERS</span></span>

### <span data-ttu-id="36802-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="36802-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="36802-116">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36802-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="36802-117">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="36802-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="36802-118">-Destination</span><span class="sxs-lookup"><span data-stu-id="36802-118">-Destination</span></span>

<span data-ttu-id="36802-119">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="36802-119">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="36802-120">-Exclude</span><span class="sxs-lookup"><span data-stu-id="36802-120">-Exclude</span></span>

<span data-ttu-id="36802-121">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="36802-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="36802-122">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="36802-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="36802-123">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="36802-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="36802-124">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="36802-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="36802-125">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="36802-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="36802-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="36802-126">-Filter</span></span>

<span data-ttu-id="36802-127">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="36802-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="36802-128">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="36802-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="36802-129">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="36802-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="36802-130">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="36802-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="36802-131">-Force</span><span class="sxs-lookup"><span data-stu-id="36802-131">-Force</span></span>

<span data-ttu-id="36802-132">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="36802-132">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="36802-133">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="36802-133">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="36802-134">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="36802-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="36802-135">-Include</span><span class="sxs-lookup"><span data-stu-id="36802-135">-Include</span></span>

<span data-ttu-id="36802-136">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="36802-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="36802-137">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="36802-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="36802-138">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="36802-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="36802-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="36802-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="36802-140">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="36802-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="36802-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="36802-141">-LiteralPath</span></span>

<span data-ttu-id="36802-142">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="36802-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="36802-143">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="36802-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="36802-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="36802-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="36802-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="36802-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="36802-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="36802-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="36802-147">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="36802-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="36802-148">-Name</span><span class="sxs-lookup"><span data-stu-id="36802-148">-Name</span></span>

<span data-ttu-id="36802-149">Указывает имя свойства, которое нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="36802-149">Specifies the name of the property to be copied.</span></span>

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

### <span data-ttu-id="36802-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="36802-150">-PassThru</span></span>

<span data-ttu-id="36802-151">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="36802-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="36802-152">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="36802-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="36802-153">-Path</span><span class="sxs-lookup"><span data-stu-id="36802-153">-Path</span></span>

<span data-ttu-id="36802-154">Указывает в виде массива строк путь к свойству, которое необходимо скопировать.</span><span class="sxs-lookup"><span data-stu-id="36802-154">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="36802-155">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="36802-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="36802-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="36802-156">-Confirm</span></span>

<span data-ttu-id="36802-157">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="36802-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="36802-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="36802-158">-WhatIf</span></span>

<span data-ttu-id="36802-159">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="36802-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="36802-160">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="36802-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="36802-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="36802-161">CommonParameters</span></span>

<span data-ttu-id="36802-162">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="36802-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="36802-163">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="36802-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="36802-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="36802-164">INPUTS</span></span>

### <span data-ttu-id="36802-165">System.String</span><span class="sxs-lookup"><span data-stu-id="36802-165">System.String</span></span>

<span data-ttu-id="36802-166">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="36802-166">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="36802-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="36802-167">OUTPUTS</span></span>

### <span data-ttu-id="36802-168">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="36802-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="36802-169">При использовании параметра **PassThru** этот командлет создает объект **PsCustomObject** , представляющий скопированное свойство Item.</span><span class="sxs-lookup"><span data-stu-id="36802-169">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="36802-170">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="36802-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="36802-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="36802-171">NOTES</span></span>

<span data-ttu-id="36802-172">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="36802-172">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="36802-173">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="36802-173">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="36802-174">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="36802-174">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="36802-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="36802-175">RELATED LINKS</span></span>

[<span data-ttu-id="36802-176">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-176">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="36802-177">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-177">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="36802-178">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-178">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="36802-179">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-179">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="36802-180">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-180">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="36802-181">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="36802-181">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="36802-182">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="36802-182">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="36802-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="36802-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


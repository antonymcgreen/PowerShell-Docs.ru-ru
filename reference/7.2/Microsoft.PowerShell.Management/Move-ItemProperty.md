---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 92a14e4bd165efd4721e3802cade827744c9c056
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603958"
---
# <span data-ttu-id="80e00-102">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-102">Move-ItemProperty</span></span>

## <span data-ttu-id="80e00-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="80e00-103">Synopsis</span></span>
<span data-ttu-id="80e00-104">Перемещает свойство из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="80e00-104">Moves a property from one location to another.</span></span>

## <span data-ttu-id="80e00-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80e00-105">SYNTAX</span></span>

### <span data-ttu-id="80e00-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="80e00-106">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80e00-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="80e00-107">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="80e00-108">Описание</span><span class="sxs-lookup"><span data-stu-id="80e00-108">Description</span></span>

<span data-ttu-id="80e00-109">`Move-ItemProperty`Командлет перемещает свойство элемента из одного элемента в другой элемент.</span><span class="sxs-lookup"><span data-stu-id="80e00-109">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="80e00-110">Например, с его помощью можно переместить запись реестра из одного раздела реестра в другой.</span><span class="sxs-lookup"><span data-stu-id="80e00-110">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="80e00-111">При перемещении свойства элемента оно добавляется в новом месте и удаляется из прежнего.</span><span class="sxs-lookup"><span data-stu-id="80e00-111">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="80e00-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="80e00-112">EXAMPLES</span></span>

### <span data-ttu-id="80e00-113">Пример 1. Перенос значения реестра и его данных в другой раздел</span><span class="sxs-lookup"><span data-stu-id="80e00-113">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="80e00-114">Эта команда перемещает значение реестра версии и его данные из подраздела MyApp в подраздел NewApp `HKLM\Software\MyCompany` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="80e00-114">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="80e00-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80e00-115">PARAMETERS</span></span>

### <span data-ttu-id="80e00-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="80e00-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="80e00-117">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80e00-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="80e00-118">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="80e00-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="80e00-119">-Destination</span></span>

<span data-ttu-id="80e00-120">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="80e00-120">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="80e00-121">-Exclude</span><span class="sxs-lookup"><span data-stu-id="80e00-121">-Exclude</span></span>

<span data-ttu-id="80e00-122">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="80e00-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="80e00-123">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="80e00-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80e00-124">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="80e00-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="80e00-125">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80e00-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="80e00-126">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="80e00-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="80e00-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="80e00-127">-Filter</span></span>

<span data-ttu-id="80e00-128">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="80e00-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="80e00-129">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="80e00-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="80e00-130">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="80e00-131">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="80e00-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="80e00-132">-Force</span><span class="sxs-lookup"><span data-stu-id="80e00-132">-Force</span></span>

<span data-ttu-id="80e00-133">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="80e00-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="80e00-134">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="80e00-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="80e00-135">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="80e00-136">-Include</span><span class="sxs-lookup"><span data-stu-id="80e00-136">-Include</span></span>

<span data-ttu-id="80e00-137">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="80e00-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="80e00-138">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="80e00-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80e00-139">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="80e00-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="80e00-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80e00-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="80e00-141">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="80e00-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="80e00-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="80e00-142">-LiteralPath</span></span>

<span data-ttu-id="80e00-143">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="80e00-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="80e00-144">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="80e00-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="80e00-145">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="80e00-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="80e00-146">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="80e00-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="80e00-147">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="80e00-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="80e00-148">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="80e00-149">-Name</span><span class="sxs-lookup"><span data-stu-id="80e00-149">-Name</span></span>

<span data-ttu-id="80e00-150">Указывает имя свойства, которое нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="80e00-150">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="80e00-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="80e00-151">-PassThru</span></span>

<span data-ttu-id="80e00-152">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="80e00-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="80e00-153">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="80e00-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="80e00-154">-Path</span><span class="sxs-lookup"><span data-stu-id="80e00-154">-Path</span></span>

<span data-ttu-id="80e00-155">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="80e00-155">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="80e00-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80e00-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="80e00-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="80e00-157">-Confirm</span></span>

<span data-ttu-id="80e00-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="80e00-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="80e00-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="80e00-159">-WhatIf</span></span>

<span data-ttu-id="80e00-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="80e00-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="80e00-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="80e00-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="80e00-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="80e00-162">CommonParameters</span></span>

<span data-ttu-id="80e00-163">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="80e00-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="80e00-164">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="80e00-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="80e00-165">INPUTS</span></span>

### <span data-ttu-id="80e00-166">System.String</span><span class="sxs-lookup"><span data-stu-id="80e00-166">System.String</span></span>

<span data-ttu-id="80e00-167">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="80e00-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="80e00-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="80e00-168">OUTPUTS</span></span>

### <span data-ttu-id="80e00-169">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="80e00-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="80e00-170">При использовании параметра **PassThru** этот командлет создает объект **PSCustomObject**, представляющий перемещенное свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="80e00-170">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="80e00-171">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80e00-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="80e00-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="80e00-172">NOTES</span></span>

<span data-ttu-id="80e00-173">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="80e00-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="80e00-174">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="80e00-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="80e00-175">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80e00-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="80e00-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="80e00-176">RELATED LINKS</span></span>

[<span data-ttu-id="80e00-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="80e00-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="80e00-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="80e00-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="80e00-181">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-181">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="80e00-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="80e00-183">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80e00-183">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="80e00-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="80e00-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


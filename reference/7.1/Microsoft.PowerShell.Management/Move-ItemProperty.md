---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: e3c1d1641c6f4b30b17c9f0f6703cd063663f25b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226465"
---
# <span data-ttu-id="40ca7-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-103">Move-ItemProperty</span></span>

## <span data-ttu-id="40ca7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="40ca7-104">Synopsis</span></span>
<span data-ttu-id="40ca7-105">Перемещает свойство из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="40ca7-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="40ca7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40ca7-106">SYNTAX</span></span>

### <span data-ttu-id="40ca7-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="40ca7-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="40ca7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="40ca7-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="40ca7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="40ca7-109">Description</span></span>

<span data-ttu-id="40ca7-110">`Move-ItemProperty`Командлет перемещает свойство элемента из одного элемента в другой элемент.</span><span class="sxs-lookup"><span data-stu-id="40ca7-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="40ca7-111">Например, с его помощью можно переместить запись реестра из одного раздела реестра в другой.</span><span class="sxs-lookup"><span data-stu-id="40ca7-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="40ca7-112">При перемещении свойства элемента оно добавляется в новом месте и удаляется из прежнего.</span><span class="sxs-lookup"><span data-stu-id="40ca7-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="40ca7-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="40ca7-113">EXAMPLES</span></span>

### <span data-ttu-id="40ca7-114">Пример 1. Перенос значения реестра и его данных в другой раздел</span><span class="sxs-lookup"><span data-stu-id="40ca7-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="40ca7-115">Эта команда перемещает значение реестра версии и его данные из подраздела MyApp в подраздел NewApp `HKLM\Software\MyCompany` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="40ca7-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="40ca7-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40ca7-116">PARAMETERS</span></span>

### <span data-ttu-id="40ca7-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="40ca7-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="40ca7-118">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40ca7-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="40ca7-119">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="40ca7-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="40ca7-120">-Destination</span></span>

<span data-ttu-id="40ca7-121">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="40ca7-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="40ca7-122">-Exclude</span><span class="sxs-lookup"><span data-stu-id="40ca7-122">-Exclude</span></span>

<span data-ttu-id="40ca7-123">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="40ca7-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="40ca7-124">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="40ca7-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="40ca7-125">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="40ca7-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="40ca7-126">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="40ca7-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="40ca7-127">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="40ca7-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="40ca7-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="40ca7-128">-Filter</span></span>

<span data-ttu-id="40ca7-129">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="40ca7-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="40ca7-130">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="40ca7-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="40ca7-131">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="40ca7-132">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="40ca7-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="40ca7-133">-Force</span><span class="sxs-lookup"><span data-stu-id="40ca7-133">-Force</span></span>

<span data-ttu-id="40ca7-134">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="40ca7-134">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="40ca7-135">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="40ca7-135">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="40ca7-136">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-136">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="40ca7-137">-Include</span><span class="sxs-lookup"><span data-stu-id="40ca7-137">-Include</span></span>

<span data-ttu-id="40ca7-138">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="40ca7-138">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="40ca7-139">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="40ca7-139">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="40ca7-140">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="40ca7-140">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="40ca7-141">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="40ca7-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="40ca7-142">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="40ca7-142">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="40ca7-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="40ca7-143">-LiteralPath</span></span>

<span data-ttu-id="40ca7-144">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="40ca7-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="40ca7-145">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="40ca7-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="40ca7-146">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="40ca7-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="40ca7-147">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="40ca7-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="40ca7-148">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="40ca7-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="40ca7-149">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="40ca7-150">-Name</span><span class="sxs-lookup"><span data-stu-id="40ca7-150">-Name</span></span>

<span data-ttu-id="40ca7-151">Указывает имя свойства, которое нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="40ca7-151">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="40ca7-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="40ca7-152">-PassThru</span></span>

<span data-ttu-id="40ca7-153">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="40ca7-153">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="40ca7-154">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="40ca7-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="40ca7-155">-Path</span><span class="sxs-lookup"><span data-stu-id="40ca7-155">-Path</span></span>

<span data-ttu-id="40ca7-156">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="40ca7-156">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="40ca7-157">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="40ca7-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="40ca7-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="40ca7-158">-Confirm</span></span>

<span data-ttu-id="40ca7-159">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="40ca7-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="40ca7-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="40ca7-160">-WhatIf</span></span>

<span data-ttu-id="40ca7-161">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="40ca7-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="40ca7-162">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="40ca7-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="40ca7-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="40ca7-163">CommonParameters</span></span>

<span data-ttu-id="40ca7-164">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="40ca7-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="40ca7-165">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="40ca7-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="40ca7-166">INPUTS</span></span>

### <span data-ttu-id="40ca7-167">System.String</span><span class="sxs-lookup"><span data-stu-id="40ca7-167">System.String</span></span>

<span data-ttu-id="40ca7-168">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="40ca7-168">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="40ca7-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="40ca7-169">OUTPUTS</span></span>

### <span data-ttu-id="40ca7-170">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="40ca7-170">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="40ca7-171">При использовании параметра **PassThru** этот командлет создает объект **PSCustomObject** , представляющий перемещенное свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="40ca7-171">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="40ca7-172">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="40ca7-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="40ca7-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="40ca7-173">NOTES</span></span>

<span data-ttu-id="40ca7-174">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="40ca7-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="40ca7-175">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="40ca7-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="40ca7-176">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="40ca7-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="40ca7-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="40ca7-177">RELATED LINKS</span></span>

[<span data-ttu-id="40ca7-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="40ca7-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="40ca7-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="40ca7-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="40ca7-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="40ca7-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="40ca7-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="40ca7-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="40ca7-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="40ca7-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


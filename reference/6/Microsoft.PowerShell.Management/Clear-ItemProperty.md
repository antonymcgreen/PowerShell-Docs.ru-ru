---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: 35d323b2cffe17619f6d741c296884c8f60e128b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226941"
---
# <span data-ttu-id="11449-103">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-103">Clear-ItemProperty</span></span>

## <span data-ttu-id="11449-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="11449-104">SYNOPSIS</span></span>
<span data-ttu-id="11449-105">Удаляет значение свойства без удаления самого свойства.</span><span class="sxs-lookup"><span data-stu-id="11449-105">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="11449-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11449-106">SYNTAX</span></span>

### <span data-ttu-id="11449-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="11449-107">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="11449-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="11449-108">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="11449-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="11449-109">DESCRIPTION</span></span>

<span data-ttu-id="11449-110">`Clear-ItemProperty`Командлет очищает значение свойства, но не удаляет свойство.</span><span class="sxs-lookup"><span data-stu-id="11449-110">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="11449-111">Данный командлет можно использовать для удаления данных параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="11449-111">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="11449-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="11449-112">EXAMPLES</span></span>

### <span data-ttu-id="11449-113">Пример 1. Удаление значения раздела реестра</span><span class="sxs-lookup"><span data-stu-id="11449-113">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="11449-114">Эта команда очищает данные в параметре реестра "Options" в подразделе "MyApp" раздела `HKEY_LOCAL_MACHINE\Software\MyCompany` .</span><span class="sxs-lookup"><span data-stu-id="11449-114">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="11449-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11449-115">PARAMETERS</span></span>

### <span data-ttu-id="11449-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="11449-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="11449-117">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11449-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="11449-118">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="11449-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="11449-119">-Exclude</span><span class="sxs-lookup"><span data-stu-id="11449-119">-Exclude</span></span>

<span data-ttu-id="11449-120">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="11449-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="11449-121">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="11449-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="11449-122">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="11449-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="11449-123">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11449-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="11449-124">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="11449-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="11449-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="11449-125">-Filter</span></span>

<span data-ttu-id="11449-126">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="11449-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="11449-127">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="11449-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="11449-128">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="11449-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="11449-129">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="11449-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="11449-130">-Force</span><span class="sxs-lookup"><span data-stu-id="11449-130">-Force</span></span>

<span data-ttu-id="11449-131">Указывает, что этот командлет удаляет из элементов свойства, недоступные пользователю другими способами.</span><span class="sxs-lookup"><span data-stu-id="11449-131">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="11449-132">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="11449-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="11449-133">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="11449-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="11449-134">-Include</span><span class="sxs-lookup"><span data-stu-id="11449-134">-Include</span></span>

<span data-ttu-id="11449-135">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="11449-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="11449-136">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="11449-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="11449-137">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="11449-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="11449-138">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11449-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="11449-139">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="11449-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="11449-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="11449-140">-LiteralPath</span></span>

<span data-ttu-id="11449-141">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="11449-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="11449-142">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="11449-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="11449-143">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="11449-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="11449-144">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="11449-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="11449-145">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="11449-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="11449-146">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="11449-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="11449-147">-Name</span><span class="sxs-lookup"><span data-stu-id="11449-147">-Name</span></span>

<span data-ttu-id="11449-148">Задает имя очищаемого свойства, например имя раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="11449-148">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="11449-149">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11449-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="11449-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="11449-150">-PassThru</span></span>

<span data-ttu-id="11449-151">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="11449-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="11449-152">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="11449-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="11449-153">-Path</span><span class="sxs-lookup"><span data-stu-id="11449-153">-Path</span></span>

<span data-ttu-id="11449-154">Указывает путь к очищаемому свойству.</span><span class="sxs-lookup"><span data-stu-id="11449-154">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="11449-155">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11449-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="11449-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="11449-156">-Confirm</span></span>

<span data-ttu-id="11449-157">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="11449-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="11449-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="11449-158">-WhatIf</span></span>

<span data-ttu-id="11449-159">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="11449-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="11449-160">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="11449-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="11449-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="11449-161">CommonParameters</span></span>

<span data-ttu-id="11449-162">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="11449-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="11449-163">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="11449-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="11449-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="11449-164">INPUTS</span></span>

### <span data-ttu-id="11449-165">System.String</span><span class="sxs-lookup"><span data-stu-id="11449-165">System.String</span></span>

<span data-ttu-id="11449-166">Строку пути можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="11449-166">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="11449-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="11449-167">OUTPUTS</span></span>

### <span data-ttu-id="11449-168">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="11449-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="11449-169">При использовании параметра **PassThru** `Clear-ItemProperty` создает объект **PSCustomObject** , представляющий свойство очистки элемента.</span><span class="sxs-lookup"><span data-stu-id="11449-169">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="11449-170">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="11449-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="11449-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="11449-171">NOTES</span></span>

- <span data-ttu-id="11449-172">Можно использовать `Clear-ItemProperty` для удаления данных из значений реестра без удаления значения.</span><span class="sxs-lookup"><span data-stu-id="11449-172">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="11449-173">Если значение имеет тип данных Binary или DWORD, то при его очистке ему присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="11449-173">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="11449-174">В противном случае присваивается пустое значение.</span><span class="sxs-lookup"><span data-stu-id="11449-174">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="11449-175">`Clear-ItemProperty`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="11449-175">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="11449-176">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="11449-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="11449-177">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="11449-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="11449-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="11449-178">RELATED LINKS</span></span>

[<span data-ttu-id="11449-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="11449-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="11449-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="11449-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="11449-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11449-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="11449-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="11449-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
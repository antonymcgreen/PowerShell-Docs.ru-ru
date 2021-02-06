---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: fc454095f9610e8712af18bfe1558e275324cefe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601301"
---
# <span data-ttu-id="14024-102">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-102">Clear-ItemProperty</span></span>

## <span data-ttu-id="14024-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="14024-103">SYNOPSIS</span></span>
<span data-ttu-id="14024-104">Удаляет значение свойства без удаления самого свойства.</span><span class="sxs-lookup"><span data-stu-id="14024-104">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="14024-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14024-105">SYNTAX</span></span>

### <span data-ttu-id="14024-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="14024-106">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="14024-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="14024-107">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="14024-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14024-108">DESCRIPTION</span></span>

<span data-ttu-id="14024-109">`Clear-ItemProperty`Командлет очищает значение свойства, но не удаляет свойство.</span><span class="sxs-lookup"><span data-stu-id="14024-109">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="14024-110">Данный командлет можно использовать для удаления данных параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="14024-110">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="14024-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="14024-111">EXAMPLES</span></span>

### <span data-ttu-id="14024-112">Пример 1. Удаление значения раздела реестра</span><span class="sxs-lookup"><span data-stu-id="14024-112">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="14024-113">Эта команда очищает данные в параметре реестра "Options" в подразделе "MyApp" раздела `HKEY_LOCAL_MACHINE\Software\MyCompany` .</span><span class="sxs-lookup"><span data-stu-id="14024-113">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="14024-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14024-114">PARAMETERS</span></span>

### <span data-ttu-id="14024-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="14024-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="14024-116">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14024-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="14024-117">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="14024-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="14024-118">-Exclude</span><span class="sxs-lookup"><span data-stu-id="14024-118">-Exclude</span></span>

<span data-ttu-id="14024-119">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="14024-119">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="14024-120">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="14024-120">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="14024-121">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="14024-121">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="14024-122">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="14024-122">Wildcard characters are permitted.</span></span> <span data-ttu-id="14024-123">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="14024-123">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="14024-124">-Filter</span><span class="sxs-lookup"><span data-stu-id="14024-124">-Filter</span></span>

<span data-ttu-id="14024-125">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="14024-125">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="14024-126">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="14024-126">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="14024-127">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="14024-127">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="14024-128">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="14024-128">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="14024-129">-Force</span><span class="sxs-lookup"><span data-stu-id="14024-129">-Force</span></span>

<span data-ttu-id="14024-130">Указывает, что этот командлет удаляет из элементов свойства, недоступные пользователю другими способами.</span><span class="sxs-lookup"><span data-stu-id="14024-130">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="14024-131">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="14024-131">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="14024-132">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="14024-132">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="14024-133">-Include</span><span class="sxs-lookup"><span data-stu-id="14024-133">-Include</span></span>

<span data-ttu-id="14024-134">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="14024-134">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="14024-135">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="14024-135">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="14024-136">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="14024-136">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="14024-137">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="14024-137">Wildcard characters are permitted.</span></span> <span data-ttu-id="14024-138">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="14024-138">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="14024-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="14024-139">-LiteralPath</span></span>

<span data-ttu-id="14024-140">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="14024-140">Specifies a path to one or more locations.</span></span> <span data-ttu-id="14024-141">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="14024-141">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="14024-142">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="14024-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="14024-143">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="14024-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="14024-144">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="14024-144">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="14024-145">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="14024-145">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="14024-146">-Name</span><span class="sxs-lookup"><span data-stu-id="14024-146">-Name</span></span>

<span data-ttu-id="14024-147">Задает имя очищаемого свойства, например имя раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="14024-147">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="14024-148">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="14024-148">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="14024-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="14024-149">-PassThru</span></span>

<span data-ttu-id="14024-150">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="14024-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="14024-151">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="14024-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="14024-152">-Path</span><span class="sxs-lookup"><span data-stu-id="14024-152">-Path</span></span>

<span data-ttu-id="14024-153">Указывает путь к очищаемому свойству.</span><span class="sxs-lookup"><span data-stu-id="14024-153">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="14024-154">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="14024-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="14024-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="14024-155">-Confirm</span></span>

<span data-ttu-id="14024-156">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="14024-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="14024-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="14024-157">-WhatIf</span></span>

<span data-ttu-id="14024-158">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="14024-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="14024-159">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="14024-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="14024-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="14024-160">CommonParameters</span></span>

<span data-ttu-id="14024-161">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="14024-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="14024-162">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="14024-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="14024-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="14024-163">INPUTS</span></span>

### <span data-ttu-id="14024-164">System.String</span><span class="sxs-lookup"><span data-stu-id="14024-164">System.String</span></span>

<span data-ttu-id="14024-165">Строку пути можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="14024-165">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="14024-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="14024-166">OUTPUTS</span></span>

### <span data-ttu-id="14024-167">Нет или System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="14024-167">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="14024-168">При использовании параметра **PassThru** `Clear-ItemProperty` создает объект **PSCustomObject** , представляющий свойство очистки элемента.</span><span class="sxs-lookup"><span data-stu-id="14024-168">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="14024-169">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="14024-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="14024-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="14024-170">NOTES</span></span>

- <span data-ttu-id="14024-171">Можно использовать `Clear-ItemProperty` для удаления данных из значений реестра без удаления значения.</span><span class="sxs-lookup"><span data-stu-id="14024-171">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="14024-172">Если значение имеет тип данных Binary или DWORD, то при его очистке ему присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="14024-172">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="14024-173">В противном случае присваивается пустое значение.</span><span class="sxs-lookup"><span data-stu-id="14024-173">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="14024-174">`Clear-ItemProperty`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="14024-174">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="14024-175">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="14024-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="14024-176">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="14024-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="14024-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="14024-177">RELATED LINKS</span></span>

[<span data-ttu-id="14024-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="14024-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="14024-180">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-180">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="14024-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="14024-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14024-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="14024-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="14024-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


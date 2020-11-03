---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: abf6a5ef365a606b6ca501e9cb924528763a8754
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228830"
---
# <span data-ttu-id="c817d-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-103">Get-ItemProperty</span></span>

## <span data-ttu-id="c817d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c817d-104">SYNOPSIS</span></span>
<span data-ttu-id="c817d-105">Получает свойства указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="c817d-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="c817d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c817d-106">SYNTAX</span></span>

### <span data-ttu-id="c817d-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c817d-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="c817d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c817d-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="c817d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c817d-109">DESCRIPTION</span></span>

<span data-ttu-id="c817d-110">`Get-ItemProperty`Командлет возвращает свойства указанных элементов.</span><span class="sxs-lookup"><span data-stu-id="c817d-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="c817d-111">Например, с помощью этого командлета можно получить значение свойства LastAccessTime объекта File.</span><span class="sxs-lookup"><span data-stu-id="c817d-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="c817d-112">Этот командлет также можно использовать для просмотра записей реестра и их значений.</span><span class="sxs-lookup"><span data-stu-id="c817d-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="c817d-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c817d-113">EXAMPLES</span></span>

### <span data-ttu-id="c817d-114">Пример 1. Получение сведений о конкретном каталоге</span><span class="sxs-lookup"><span data-stu-id="c817d-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="c817d-115">Эта команда возвращает сведения о `C:\Windows` каталоге.</span><span class="sxs-lookup"><span data-stu-id="c817d-115">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="c817d-116">Пример 2. получение свойств указанного файла</span><span class="sxs-lookup"><span data-stu-id="c817d-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="c817d-117">Эта команда возвращает свойства `C:\Test\Weather.xls` файла.</span><span class="sxs-lookup"><span data-stu-id="c817d-117">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="c817d-118">Результат передается `Format-List` командлету для вывода выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="c817d-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="c817d-119">Пример 3. Отображение имени значения и данных записей реестра в подразделе реестра</span><span class="sxs-lookup"><span data-stu-id="c817d-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="c817d-120">Эта команда отображает имя значения и данные каждой из записей реестра, содержащихся в подразделе реестра CurrentVersion.</span><span class="sxs-lookup"><span data-stu-id="c817d-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="c817d-121">Эта команда требует наличия диска PowerShell с именем `HKLM:` , сопоставленного с кустом реестра "HKEY_LOCAL_MACHINE".</span><span class="sxs-lookup"><span data-stu-id="c817d-121">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="c817d-122">Диск с таким именем и сопоставлением доступен в PowerShell по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c817d-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="c817d-123">Путь к указанному подразделу реестра может быть задан и другим способом. Необходимо ввести путь, начиная с имени поставщика и двоеточия, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c817d-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="c817d-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="c817d-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="c817d-125">Пример 4. Получение имени значения и данных записи реестра в подразделе реестра</span><span class="sxs-lookup"><span data-stu-id="c817d-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="c817d-126">Эта команда возвращает имя значения и данные записи реестра "ProgramFilesDir" в подразделе реестра "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="c817d-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="c817d-127">**Путь** задает подраздел, а параметр **Name** указывает имя значения записи.</span><span class="sxs-lookup"><span data-stu-id="c817d-127">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="c817d-128">Пример 5. Получение имен значений и данных записей реестра в разделе реестра</span><span class="sxs-lookup"><span data-stu-id="c817d-128">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="c817d-129">Эта команда возвращает имена значений и данные записей реестра в разделе реестра "PowerShellEngine".</span><span class="sxs-lookup"><span data-stu-id="c817d-129">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="c817d-130">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="c817d-130">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## <span data-ttu-id="c817d-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c817d-131">PARAMETERS</span></span>

### <span data-ttu-id="c817d-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="c817d-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c817d-133">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c817d-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c817d-134">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="c817d-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="c817d-135">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c817d-135">-Exclude</span></span>

<span data-ttu-id="c817d-136">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="c817d-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c817d-137">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="c817d-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c817d-138">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c817d-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c817d-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c817d-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="c817d-140">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c817d-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c817d-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="c817d-141">-Filter</span></span>

<span data-ttu-id="c817d-142">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="c817d-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c817d-143">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="c817d-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c817d-144">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="c817d-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c817d-145">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="c817d-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c817d-146">-Include</span><span class="sxs-lookup"><span data-stu-id="c817d-146">-Include</span></span>

<span data-ttu-id="c817d-147">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="c817d-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c817d-148">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="c817d-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c817d-149">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="c817d-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c817d-150">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c817d-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="c817d-151">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c817d-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c817d-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c817d-152">-LiteralPath</span></span>

<span data-ttu-id="c817d-153">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="c817d-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c817d-154">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="c817d-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c817d-155">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="c817d-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c817d-156">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c817d-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c817d-157">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="c817d-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c817d-158">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c817d-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c817d-159">-Name</span><span class="sxs-lookup"><span data-stu-id="c817d-159">-Name</span></span>

<span data-ttu-id="c817d-160">Указывает имена свойств, которые нужно извлечь.</span><span class="sxs-lookup"><span data-stu-id="c817d-160">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="c817d-161">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c817d-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c817d-162">-Path</span><span class="sxs-lookup"><span data-stu-id="c817d-162">-Path</span></span>

<span data-ttu-id="c817d-163">Указывает путь к элементам.</span><span class="sxs-lookup"><span data-stu-id="c817d-163">Specifies the path to the item or items.</span></span>
<span data-ttu-id="c817d-164">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c817d-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c817d-165">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c817d-165">CommonParameters</span></span>

<span data-ttu-id="c817d-166">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="c817d-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c817d-167">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c817d-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c817d-168">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c817d-168">INPUTS</span></span>

### <span data-ttu-id="c817d-169">System.String</span><span class="sxs-lookup"><span data-stu-id="c817d-169">System.String</span></span>

<span data-ttu-id="c817d-170">Можно передать строку, содержащую путь, в `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="c817d-170">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="c817d-171">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c817d-171">OUTPUTS</span></span>

### <span data-ttu-id="c817d-172">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="c817d-172">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="c817d-173">`Get-ItemProperty` Возвращает объект для каждого свойства элемента, которое он получает.</span><span class="sxs-lookup"><span data-stu-id="c817d-173">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="c817d-174">Тип объекта зависит от извлекаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c817d-174">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="c817d-175">Например в случае диска файловой системы командлет возвращает файл или папку.</span><span class="sxs-lookup"><span data-stu-id="c817d-175">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="c817d-176">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c817d-176">NOTES</span></span>

<span data-ttu-id="c817d-177">`Get-ItemProperty`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="c817d-177">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c817d-178">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="c817d-178">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="c817d-179">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c817d-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c817d-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c817d-180">RELATED LINKS</span></span>

[<span data-ttu-id="c817d-181">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-181">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="c817d-182">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-182">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="c817d-183">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-183">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="c817d-184">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-184">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="c817d-185">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-185">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="c817d-186">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-186">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="c817d-187">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c817d-187">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="c817d-188">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c817d-188">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

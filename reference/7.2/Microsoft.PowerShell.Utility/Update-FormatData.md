---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 91d0274e485573de96d9960fa49f6d327156a79a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602289"
---
# <span data-ttu-id="2fdf0-102">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="2fdf0-102">Update-FormatData</span></span>

## <span data-ttu-id="2fdf0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2fdf0-103">SYNOPSIS</span></span>
<span data-ttu-id="2fdf0-104">Обновляет данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-104">Updates the formatting data in the current session.</span></span>

## <span data-ttu-id="2fdf0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2fdf0-105">SYNTAX</span></span>

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2fdf0-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fdf0-106">DESCRIPTION</span></span>

<span data-ttu-id="2fdf0-107">`Update-FormatData`Командлет перезагружает данные форматирования из файлов форматирования в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-107">The `Update-FormatData` cmdlet reloads the formatting data from formatting files into the current session.</span></span> <span data-ttu-id="2fdf0-108">Этот командлет позволяет обновлять данные форматирования без перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-108">This cmdlet lets you update the formatting data without restarting PowerShell.</span></span>

<span data-ttu-id="2fdf0-109">Без параметров `Update-FormatData` перегружает загруженные ранее файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-109">Without parameters, `Update-FormatData` reloads the formatting files that it loaded previously.</span></span>
<span data-ttu-id="2fdf0-110">`Update-FormatData`Для добавления новых файлов форматирования в сеанс можно использовать параметры.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-110">You can use the parameters of `Update-FormatData` to add new formatting files to the session.</span></span>

<span data-ttu-id="2fdf0-111">Файлы форматирования — это текстовые файлы в формате XML с `format.ps1xml` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-111">Formatting files are text files in XML format with the `format.ps1xml` file name extension.</span></span> <span data-ttu-id="2fdf0-112">Данные форматирования в этих файлах определяют способ отображения объектов Microsoft .NET Framework в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-112">The formatting data in the files defines the display of Microsoft .NET Framework objects in the session.</span></span>

<span data-ttu-id="2fdf0-113">При запуске PowerShell загружает данные формата из исходного кода PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-113">When PowerShell starts, it loads the format data from the PowerShell source code.</span></span> <span data-ttu-id="2fdf0-114">Однако можно создать пользовательские format.ps1XML-файлы для обновления форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-114">However, you can create custom format.ps1xml files to update formatting in the current session.</span></span> <span data-ttu-id="2fdf0-115">Можно использовать `Update-FormatData` для повторной загрузки данных форматирования в текущий сеанс без перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-115">You can use `Update-FormatData` to reload the formatting data into the current session without restarting PowerShell.</span></span> <span data-ttu-id="2fdf0-116">Это полезно в том случае, если вы добавили или изменили файл форматирования, но не хотите прерывать сеанс.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-116">This is useful when you have added or changed a formatting file, but do not want to interrupt the session.</span></span>

<span data-ttu-id="2fdf0-117">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="2fdf0-117">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="2fdf0-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="2fdf0-118">EXAMPLES</span></span>

### <span data-ttu-id="2fdf0-119">Пример 1. Перезагрузка ранее загруженных файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="2fdf0-119">Example 1: Reload previously loaded formatting files</span></span>

```powershell
Update-FormatData
```

<span data-ttu-id="2fdf0-120">Эта команда перезагружает файлы форматирования, которые она ранее загрузила.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-120">This command reloads the formatting files that it loaded previously.</span></span>

### <span data-ttu-id="2fdf0-121">Пример 2. Перезагрузка файлов форматирования и файлов форматирования трассировки и журнала</span><span class="sxs-lookup"><span data-stu-id="2fdf0-121">Example 2: Reload formatting files and trace and log formatting files</span></span>

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

<span data-ttu-id="2fdf0-122">Эта команда перезагружает в сеанс файлы форматирования, включая два новых файла: Trace.format.ps1xml и Log.format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-122">This command reloads the formatting files into the session, including two new files, Trace.format.ps1xml and Log.format.ps1xml.</span></span>

<span data-ttu-id="2fdf0-123">Поскольку в команде используется параметр **AppendPath** , данные форматирования в новых файлах загружаются после форматирования данных из встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-123">Because the command uses the **AppendPath** parameter, the formatting data in the new files is loaded after the formatting data from the built-in files.</span></span>

<span data-ttu-id="2fdf0-124">Используется параметр **AppendPath** , так как новые файлы содержат данные форматирования для объектов, на которые нет ссылок во встроенных файлах.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-124">The **AppendPath** parameter is used because the new files contain formatting data for objects that are not referenced in the built-in files.</span></span>

### <span data-ttu-id="2fdf0-125">Пример 3. изменение файла форматирования и его повторная загрузка</span><span class="sxs-lookup"><span data-stu-id="2fdf0-125">Example 3: Edit a formatting file and reload it</span></span>

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

<span data-ttu-id="2fdf0-126">В этом примере показано, как перезагрузить файл форматирования после его изменения.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-126">This example shows how to reload a formatting file after you have edited it.</span></span>

<span data-ttu-id="2fdf0-127">Первая команда добавляет в сеанс файл NewFiles.format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-127">The first command adds the NewFiles.format.ps1xml file to the session.</span></span> <span data-ttu-id="2fdf0-128">Он использует параметр **препендпас** , поскольку файл содержит данные форматирования для объектов, на которые имеются ссылки во встроенных файлах.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-128">It uses the **PrependPath** parameter because the file contains formatting data for objects that are referenced in the built-in files.</span></span>

<span data-ttu-id="2fdf0-129">После добавления XML-файла NewFiles.format.ps1и его тестирования в этих сеансах автор редактирует файл.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-129">After adding the NewFiles.format.ps1xml file and testing it in these sessions, the author edits the file.</span></span>

<span data-ttu-id="2fdf0-130">Вторая команда использует `Update-FormatData` командлет для повторной загрузки файлов форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-130">The second command uses the `Update-FormatData` cmdlet to reload the formatting files.</span></span> <span data-ttu-id="2fdf0-131">Так как XML-файл NewFiles.format.ps1был ранее загружен, `Update-FormatData` автоматически перезагружает его без использования параметров.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-131">Because the NewFiles.format.ps1xml file was previously loaded, `Update-FormatData` automatically reloads it without using parameters.</span></span>

## <span data-ttu-id="2fdf0-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2fdf0-132">PARAMETERS</span></span>

### <span data-ttu-id="2fdf0-133">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="2fdf0-133">-AppendPath</span></span>

<span data-ttu-id="2fdf0-134">Указывает файлы форматирования, которые этот командлет добавляет к сеансу.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-134">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="2fdf0-135">Файлы загружаются после того, как PowerShell загружает встроенные файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-135">The files are loaded after PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="2fdf0-136">При форматировании объектов .NET PowerShell использует первое определение форматирования, найденное для каждого типа .NET.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-136">When formatting .NET objects, PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="2fdf0-137">При использовании параметра **AppendPath** PowerShell выполняет поиск данных из встроенных файлов до того, как он встречает добавляемые данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-137">If you use the **AppendPath** parameter, PowerShell searches the data from the built-in files before it encounters the formatting data that you are adding.</span></span>

<span data-ttu-id="2fdf0-138">Используйте этот параметр для добавления файла, форматирующего объект .NET, на который нет ссылок во встроенных файлах форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-138">Use this parameter to add a file that formats a .NET object that is not referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2fdf0-139">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="2fdf0-139">-PrependPath</span></span>

<span data-ttu-id="2fdf0-140">Указывает файлы форматирования, которые этот командлет добавляет к сеансу.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-140">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="2fdf0-141">Файлы загружаются перед тем, как PowerShell загружает встроенные файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-141">The files are loaded before PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="2fdf0-142">При форматировании объектов .NET PowerShell использует первое определение форматирования, найденное для каждого типа .NET.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-142">When formatting .NET objects, PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="2fdf0-143">При использовании параметра **Препендпас** PowerShell ищет данные из добавляемых файлов перед тем, как обнаруживает данные форматирования из встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-143">If you use the **PrependPath** parameter, PowerShell searches the data from the files that you are adding before it encounters the formatting data from the built-in files.</span></span>

<span data-ttu-id="2fdf0-144">Используйте этот параметр для добавления файла, форматирующего объект .NET, на который также есть ссылки во встроенных файлах форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-144">Use this parameter to add a file that formats a .NET object that is also referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2fdf0-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2fdf0-145">-Confirm</span></span>

<span data-ttu-id="2fdf0-146">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-146">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2fdf0-147">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2fdf0-147">-WhatIf</span></span>

<span data-ttu-id="2fdf0-148">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-148">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2fdf0-149">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-149">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2fdf0-150">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2fdf0-150">CommonParameters</span></span>

<span data-ttu-id="2fdf0-151">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2fdf0-152">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2fdf0-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2fdf0-153">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2fdf0-153">INPUTS</span></span>

### <span data-ttu-id="2fdf0-154">System.String</span><span class="sxs-lookup"><span data-stu-id="2fdf0-154">System.String</span></span>

<span data-ttu-id="2fdf0-155">Строку, содержащую путь к добавлению, можно передать в `Update-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="2fdf0-155">You can pipe a string that contains the append path to `Update-FormatData`.</span></span>

## <span data-ttu-id="2fdf0-156">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2fdf0-156">OUTPUTS</span></span>

### <span data-ttu-id="2fdf0-157">None</span><span class="sxs-lookup"><span data-stu-id="2fdf0-157">None</span></span>

<span data-ttu-id="2fdf0-158">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-158">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="2fdf0-159">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2fdf0-159">NOTES</span></span>

- <span data-ttu-id="2fdf0-160">`Update-FormatData` также обновляет данные форматирования для команд в сеансе, импортированных из модулей.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-160">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="2fdf0-161">При изменении файла форматирования для модуля можно выполнить `Update-FormatData` команду, чтобы обновить данные форматирования для импортированных команд.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-161">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="2fdf0-162">Импортировать модуль снова не требуется.</span><span class="sxs-lookup"><span data-stu-id="2fdf0-162">You do not need to import the module again.</span></span>

## <span data-ttu-id="2fdf0-163">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2fdf0-163">RELATED LINKS</span></span>

[<span data-ttu-id="2fdf0-164">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="2fdf0-164">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="2fdf0-165">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="2fdf0-165">Export-FormatData</span></span>](Export-FormatData.md)

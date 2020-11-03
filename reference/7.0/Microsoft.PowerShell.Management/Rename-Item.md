---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: f05101f06e4911a797d3342b2b535780badeaefd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226194"
---
# <span data-ttu-id="b3d6a-103">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-103">Rename-Item</span></span>

## <span data-ttu-id="b3d6a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b3d6a-104">SYNOPSIS</span></span>
<span data-ttu-id="b3d6a-105">Переименовывает элемент в пространстве имен поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-105">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="b3d6a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3d6a-106">SYNTAX</span></span>

### <span data-ttu-id="b3d6a-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b3d6a-107">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="b3d6a-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b3d6a-108">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="b3d6a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3d6a-109">DESCRIPTION</span></span>

<span data-ttu-id="b3d6a-110">`Rename-Item`Командлет изменяет имя указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-110">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="b3d6a-111">Он не влияет на содержимое переименовываемого элемента.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-111">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="b3d6a-112">Нельзя использовать `Rename-Item` для перемещения элемента, например путем указания пути вместе с новым именем.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-112">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="b3d6a-113">Чтобы переместить и переименовать элемент, используйте `Move-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-113">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="b3d6a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="b3d6a-114">EXAMPLES</span></span>

### <span data-ttu-id="b3d6a-115">Пример 1. Переименование файла</span><span class="sxs-lookup"><span data-stu-id="b3d6a-115">Example 1: Rename a file</span></span>

<span data-ttu-id="b3d6a-116">Эта команда переименовывает файл `daily_file.txt` в `monday_file.txt` .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-116">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="b3d6a-117">Пример 2. Переименование и перемещение элемента</span><span class="sxs-lookup"><span data-stu-id="b3d6a-117">Example 2: Rename and move an item</span></span>

<span data-ttu-id="b3d6a-118">Нельзя использовать `Rename-Item` для переименования и перемещения элемента.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-118">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="b3d6a-119">В частности, нельзя указывать путь для значения параметра **newname** , если путь не идентичен пути, указанному в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-119">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="b3d6a-120">В противном случае допускается только новое имя.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-120">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="b3d6a-121">В этом примере предпринимается попытка переименовать `project.txt` файл в текущем каталоге в `old-project.txt` в `D:\Archive` каталоге.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-121">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="b3d6a-122">Результатом является сообщение об ошибке в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-122">The result is the error shown in the output.</span></span>

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### <span data-ttu-id="b3d6a-123">Пример 3. Переименование раздела реестра</span><span class="sxs-lookup"><span data-stu-id="b3d6a-123">Example 3: Rename a registry key</span></span>

<span data-ttu-id="b3d6a-124">В этом примере раздел реестра переименовывается из **рекламы** в **маркетинг**.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-124">This example renames a registry key from **Advertising** to **Marketing**.</span></span> <span data-ttu-id="b3d6a-125">После выполнения команды раздел переименовывается, но записи реестра в нем остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-125">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="b3d6a-126">Пример 4. Переименование нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="b3d6a-126">Example 4: Rename multiple files</span></span>

<span data-ttu-id="b3d6a-127">В этом примере все `*.txt` файлы в текущем каталоге переименованы в `*.log` .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-127">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

<span data-ttu-id="b3d6a-128">`Get-ChildItem`Командлет получает все файлы в текущей папке, `.txt` для которых расширение файла затем передает их `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-128">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="b3d6a-129">Значение **newname** — это блок скрипта, запускаемый перед отправкой значения в параметр **newname** .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-129">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="b3d6a-130">В блоке скрипта `$_` Автоматическая переменная представляет каждый объект файла по мере того, как он доходит до команды через конвейер.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-130">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="b3d6a-131">Блок скрипта использует `-replace` оператор для замены расширения файла каждого файла на `.log` .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-131">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="b3d6a-132">Обратите внимание, что сопоставление с помощью `-replace` оператора не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-132">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="b3d6a-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3d6a-133">PARAMETERS</span></span>

### <span data-ttu-id="b3d6a-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="b3d6a-134">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b3d6a-135">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-135">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="b3d6a-136">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-136">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b3d6a-137">-Force</span><span class="sxs-lookup"><span data-stu-id="b3d6a-137">-Force</span></span>

<span data-ttu-id="b3d6a-138">Заставляет командлет переименовывать элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-138">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="b3d6a-139">Командлет не может изменить постоянные псевдонимы или переменные.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-139">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="b3d6a-140">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-140">Implementation varies from provider to provider.</span></span> <span data-ttu-id="b3d6a-141">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="b3d6a-142">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-142">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="b3d6a-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b3d6a-143">-LiteralPath</span></span>

<span data-ttu-id="b3d6a-144">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b3d6a-145">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b3d6a-146">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b3d6a-147">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b3d6a-148">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b3d6a-149">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3d6a-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="b3d6a-150">-NewName</span></span>

<span data-ttu-id="b3d6a-151">Задает новое имя элемента.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-151">Specifies the new name of the item.</span></span> <span data-ttu-id="b3d6a-152">Введите только имя без пути.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-152">Enter only a name, not a path and name.</span></span> <span data-ttu-id="b3d6a-153">Если ввести путь, отличающийся от пути, указанного в параметре **path** , `Rename-Item` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-153">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="b3d6a-154">Чтобы переименовать и переместить элемент, используйте `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-154">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="b3d6a-155">В значении параметра **newname** нельзя использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-155">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="b3d6a-156">Чтобы указать имя для нескольких файлов, используйте оператор **Replace** в регулярном выражении.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-156">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="b3d6a-157">Дополнительные сведения об операторе Replace см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-157">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

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

### <span data-ttu-id="b3d6a-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b3d6a-158">-PassThru</span></span>

<span data-ttu-id="b3d6a-159">Возвращает объект, представляющий элемент для конвейера.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-159">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="b3d6a-160">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b3d6a-161">-Path</span><span class="sxs-lookup"><span data-stu-id="b3d6a-161">-Path</span></span>

<span data-ttu-id="b3d6a-162">Указывает путь к элементу для переименования.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-162">Specifies the path of the item to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b3d6a-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b3d6a-163">-Confirm</span></span>

<span data-ttu-id="b3d6a-164">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b3d6a-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b3d6a-165">-WhatIf</span></span>

<span data-ttu-id="b3d6a-166">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b3d6a-167">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b3d6a-168">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b3d6a-168">CommonParameters</span></span>

<span data-ttu-id="b3d6a-169">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3d6a-170">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b3d6a-171">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b3d6a-171">INPUTS</span></span>

### <span data-ttu-id="b3d6a-172">System.String</span><span class="sxs-lookup"><span data-stu-id="b3d6a-172">System.String</span></span>

<span data-ttu-id="b3d6a-173">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-173">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b3d6a-174">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b3d6a-174">OUTPUTS</span></span>

### <span data-ttu-id="b3d6a-175">Отсутствует или объект, представляющий переименованный элемент.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-175">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="b3d6a-176">Этот командлет создает объект, представляющий переименованный элемент, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="b3d6a-176">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b3d6a-177">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b3d6a-178">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b3d6a-178">NOTES</span></span>

<span data-ttu-id="b3d6a-179">`Rename-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-179">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b3d6a-180">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="b3d6a-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="b3d6a-181">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b3d6a-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b3d6a-182">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b3d6a-182">RELATED LINKS</span></span>

[<span data-ttu-id="b3d6a-183">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-183">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="b3d6a-184">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-184">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="b3d6a-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b3d6a-185">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="b3d6a-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="b3d6a-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="b3d6a-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="b3d6a-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="b3d6a-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="b3d6a-191">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b3d6a-191">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b3d6a-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="b3d6a-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="b3d6a-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b3d6a-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

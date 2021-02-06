---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: dec5c2c905486110e4885f29d236ab41d945fb96
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601610"
---
# <span data-ttu-id="14f4a-102">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-102">Rename-Item</span></span>

## <span data-ttu-id="14f4a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="14f4a-103">SYNOPSIS</span></span>
<span data-ttu-id="14f4a-104">Переименовывает элемент в пространстве имен поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14f4a-104">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="14f4a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14f4a-105">SYNTAX</span></span>

### <span data-ttu-id="14f4a-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="14f4a-106">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="14f4a-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="14f4a-107">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="14f4a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14f4a-108">DESCRIPTION</span></span>

<span data-ttu-id="14f4a-109">`Rename-Item`Командлет изменяет имя указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="14f4a-109">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="14f4a-110">Он не влияет на содержимое переименовываемого элемента.</span><span class="sxs-lookup"><span data-stu-id="14f4a-110">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="14f4a-111">Нельзя использовать `Rename-Item` для перемещения элемента, например путем указания пути вместе с новым именем.</span><span class="sxs-lookup"><span data-stu-id="14f4a-111">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="14f4a-112">Чтобы переместить и переименовать элемент, используйте `Move-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="14f4a-112">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="14f4a-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="14f4a-113">EXAMPLES</span></span>

### <span data-ttu-id="14f4a-114">Пример 1. Переименование файла</span><span class="sxs-lookup"><span data-stu-id="14f4a-114">Example 1: Rename a file</span></span>

<span data-ttu-id="14f4a-115">Эта команда переименовывает файл `daily_file.txt` в `monday_file.txt` .</span><span class="sxs-lookup"><span data-stu-id="14f4a-115">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="14f4a-116">Пример 2. Переименование и перемещение элемента</span><span class="sxs-lookup"><span data-stu-id="14f4a-116">Example 2: Rename and move an item</span></span>

<span data-ttu-id="14f4a-117">Нельзя использовать `Rename-Item` для переименования и перемещения элемента.</span><span class="sxs-lookup"><span data-stu-id="14f4a-117">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="14f4a-118">В частности, нельзя указывать путь для значения параметра **newname** , если путь не идентичен пути, указанному в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="14f4a-118">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="14f4a-119">В противном случае допускается только новое имя.</span><span class="sxs-lookup"><span data-stu-id="14f4a-119">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="14f4a-120">В этом примере предпринимается попытка переименовать `project.txt` файл в текущем каталоге в `old-project.txt` в `D:\Archive` каталоге.</span><span class="sxs-lookup"><span data-stu-id="14f4a-120">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="14f4a-121">Результатом является сообщение об ошибке в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="14f4a-121">The result is the error shown in the output.</span></span>

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

### <span data-ttu-id="14f4a-122">Пример 3. Переименование раздела реестра</span><span class="sxs-lookup"><span data-stu-id="14f4a-122">Example 3: Rename a registry key</span></span>

<span data-ttu-id="14f4a-123">В этом примере раздел реестра переименовывается из **рекламы** в **маркетинг**.</span><span class="sxs-lookup"><span data-stu-id="14f4a-123">This example renames a registry key from **Advertising** to **Marketing**.</span></span> <span data-ttu-id="14f4a-124">После выполнения команды раздел переименовывается, но записи реестра в нем остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="14f4a-124">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="14f4a-125">Пример 4. Переименование нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="14f4a-125">Example 4: Rename multiple files</span></span>

<span data-ttu-id="14f4a-126">В этом примере все `*.txt` файлы в текущем каталоге переименованы в `*.log` .</span><span class="sxs-lookup"><span data-stu-id="14f4a-126">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

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

<span data-ttu-id="14f4a-127">`Get-ChildItem`Командлет получает все файлы в текущей папке, `.txt` для которых расширение файла затем передает их `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="14f4a-127">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="14f4a-128">Значение **newname** — это блок скрипта, запускаемый перед отправкой значения в параметр **newname** .</span><span class="sxs-lookup"><span data-stu-id="14f4a-128">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="14f4a-129">В блоке скрипта `$_` Автоматическая переменная представляет каждый объект файла по мере того, как он доходит до команды через конвейер.</span><span class="sxs-lookup"><span data-stu-id="14f4a-129">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="14f4a-130">Блок скрипта использует `-replace` оператор для замены расширения файла каждого файла на `.log` .</span><span class="sxs-lookup"><span data-stu-id="14f4a-130">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="14f4a-131">Обратите внимание, что сопоставление с помощью `-replace` оператора не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="14f4a-131">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="14f4a-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14f4a-132">PARAMETERS</span></span>

### <span data-ttu-id="14f4a-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="14f4a-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="14f4a-134">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14f4a-134">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="14f4a-135">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="14f4a-136">-Force</span><span class="sxs-lookup"><span data-stu-id="14f4a-136">-Force</span></span>

<span data-ttu-id="14f4a-137">Заставляет командлет переименовывать элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="14f4a-137">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="14f4a-138">Командлет не может изменить постоянные псевдонимы или переменные.</span><span class="sxs-lookup"><span data-stu-id="14f4a-138">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="14f4a-139">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="14f4a-139">Implementation varies from provider to provider.</span></span> <span data-ttu-id="14f4a-140">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-140">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="14f4a-141">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="14f4a-141">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="14f4a-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="14f4a-142">-LiteralPath</span></span>

<span data-ttu-id="14f4a-143">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="14f4a-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="14f4a-144">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="14f4a-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="14f4a-145">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="14f4a-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="14f4a-146">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="14f4a-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="14f4a-147">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="14f4a-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="14f4a-148">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="14f4a-149">-NewName</span><span class="sxs-lookup"><span data-stu-id="14f4a-149">-NewName</span></span>

<span data-ttu-id="14f4a-150">Задает новое имя элемента.</span><span class="sxs-lookup"><span data-stu-id="14f4a-150">Specifies the new name of the item.</span></span> <span data-ttu-id="14f4a-151">Введите только имя без пути.</span><span class="sxs-lookup"><span data-stu-id="14f4a-151">Enter only a name, not a path and name.</span></span> <span data-ttu-id="14f4a-152">Если ввести путь, отличающийся от пути, указанного в параметре **path** , `Rename-Item` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="14f4a-152">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="14f4a-153">Чтобы переименовать и переместить элемент, используйте `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="14f4a-153">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="14f4a-154">В значении параметра **newname** нельзя использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="14f4a-154">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="14f4a-155">Чтобы указать имя для нескольких файлов, используйте оператор **Replace** в регулярном выражении.</span><span class="sxs-lookup"><span data-stu-id="14f4a-155">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="14f4a-156">Дополнительные сведения об операторе Replace см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-156">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

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

### <span data-ttu-id="14f4a-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="14f4a-157">-PassThru</span></span>

<span data-ttu-id="14f4a-158">Возвращает объект, представляющий элемент для конвейера.</span><span class="sxs-lookup"><span data-stu-id="14f4a-158">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="14f4a-159">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="14f4a-159">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="14f4a-160">-Path</span><span class="sxs-lookup"><span data-stu-id="14f4a-160">-Path</span></span>

<span data-ttu-id="14f4a-161">Указывает путь к элементу для переименования.</span><span class="sxs-lookup"><span data-stu-id="14f4a-161">Specifies the path of the item to rename.</span></span>

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

### <span data-ttu-id="14f4a-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="14f4a-162">-Confirm</span></span>

<span data-ttu-id="14f4a-163">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="14f4a-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="14f4a-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="14f4a-164">-WhatIf</span></span>

<span data-ttu-id="14f4a-165">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="14f4a-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="14f4a-166">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="14f4a-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="14f4a-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="14f4a-167">CommonParameters</span></span>

<span data-ttu-id="14f4a-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14f4a-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14f4a-169">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-169">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="14f4a-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="14f4a-170">INPUTS</span></span>

### <span data-ttu-id="14f4a-171">System.String</span><span class="sxs-lookup"><span data-stu-id="14f4a-171">System.String</span></span>

<span data-ttu-id="14f4a-172">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="14f4a-172">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="14f4a-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="14f4a-173">OUTPUTS</span></span>

### <span data-ttu-id="14f4a-174">Отсутствует или объект, представляющий переименованный элемент.</span><span class="sxs-lookup"><span data-stu-id="14f4a-174">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="14f4a-175">Этот командлет создает объект, представляющий переименованный элемент, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="14f4a-175">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="14f4a-176">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="14f4a-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="14f4a-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="14f4a-177">NOTES</span></span>

<span data-ttu-id="14f4a-178">`Rename-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="14f4a-178">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="14f4a-179">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="14f4a-179">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="14f4a-180">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="14f4a-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="14f4a-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="14f4a-181">RELATED LINKS</span></span>

[<span data-ttu-id="14f4a-182">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-182">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="14f4a-183">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-183">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="14f4a-184">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="14f4a-184">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="14f4a-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="14f4a-186">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-186">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="14f4a-187">Move-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-187">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="14f4a-188">New-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-188">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="14f4a-189">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-189">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="14f4a-190">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="14f4a-190">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="14f4a-191">Set-Item</span><span class="sxs-lookup"><span data-stu-id="14f4a-191">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="14f4a-192">about_Providers</span><span class="sxs-lookup"><span data-stu-id="14f4a-192">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


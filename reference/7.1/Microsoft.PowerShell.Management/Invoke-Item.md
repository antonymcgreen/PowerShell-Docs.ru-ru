---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 030e65f2b78ba91ddd4f6e2626372c1716218a78
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226489"
---
# <span data-ttu-id="9378c-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-103">Invoke-Item</span></span>

## <span data-ttu-id="9378c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9378c-104">SYNOPSIS</span></span>
<span data-ttu-id="9378c-105">Выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="9378c-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="9378c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9378c-106">SYNTAX</span></span>

### <span data-ttu-id="9378c-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9378c-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9378c-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9378c-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9378c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9378c-109">DESCRIPTION</span></span>

<span data-ttu-id="9378c-110">`Invoke-Item`Командлет выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="9378c-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="9378c-111">Например, он запускает исполняемый файл или открывает файл документа в приложении, связанном с данным типом файла.</span><span class="sxs-lookup"><span data-stu-id="9378c-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="9378c-112">Действие по умолчанию зависит от типа элемента и определяется поставщиком PowerShell, предоставляющим доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="9378c-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="9378c-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="9378c-113">EXAMPLES</span></span>

### <span data-ttu-id="9378c-114">Пример 1. Открытие файла</span><span class="sxs-lookup"><span data-stu-id="9378c-114">Example 1: Open a file</span></span>

<span data-ttu-id="9378c-115">Эта команда открывает файл "aliasApr04.doc" в Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="9378c-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="9378c-116">В этом случае открытие в Word является действием по умолчанию для файлов с расширением doc.</span><span class="sxs-lookup"><span data-stu-id="9378c-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="9378c-117">Пример 2. Открытие всех файлов определенного типа</span><span class="sxs-lookup"><span data-stu-id="9378c-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="9378c-118">Эта команда открывает все Microsoft Office электронные таблицы Excel в `C:\Documents and
Settings\Lister\My Documents` папке.</span><span class="sxs-lookup"><span data-stu-id="9378c-118">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="9378c-119">Каждая таблица открывается в новом экземпляре Excel.</span><span class="sxs-lookup"><span data-stu-id="9378c-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="9378c-120">В этом случае открытие в Excel является действием по умолчанию для `.xls` файлов.</span><span class="sxs-lookup"><span data-stu-id="9378c-120">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="9378c-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9378c-121">PARAMETERS</span></span>

### <span data-ttu-id="9378c-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="9378c-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9378c-123">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9378c-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9378c-124">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="9378c-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9378c-125">-Exclude</span><span class="sxs-lookup"><span data-stu-id="9378c-125">-Exclude</span></span>

<span data-ttu-id="9378c-126">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="9378c-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9378c-127">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="9378c-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9378c-128">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="9378c-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9378c-129">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9378c-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="9378c-130">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="9378c-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9378c-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="9378c-131">-Filter</span></span>

<span data-ttu-id="9378c-132">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="9378c-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9378c-133">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="9378c-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="9378c-134">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="9378c-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="9378c-135">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="9378c-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="9378c-136">-Include</span><span class="sxs-lookup"><span data-stu-id="9378c-136">-Include</span></span>

<span data-ttu-id="9378c-137">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="9378c-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9378c-138">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="9378c-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9378c-139">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="9378c-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="9378c-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9378c-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="9378c-141">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="9378c-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9378c-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9378c-142">-LiteralPath</span></span>

<span data-ttu-id="9378c-143">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="9378c-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9378c-144">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="9378c-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9378c-145">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="9378c-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9378c-146">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9378c-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9378c-147">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="9378c-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9378c-148">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9378c-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="9378c-149">-Path</span><span class="sxs-lookup"><span data-stu-id="9378c-149">-Path</span></span>

<span data-ttu-id="9378c-150">Указывает путь к выбранному элементу.</span><span class="sxs-lookup"><span data-stu-id="9378c-150">Specifies the path to the selected item.</span></span>
<span data-ttu-id="9378c-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9378c-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9378c-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9378c-152">-Confirm</span></span>

<span data-ttu-id="9378c-153">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9378c-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9378c-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9378c-154">-WhatIf</span></span>

<span data-ttu-id="9378c-155">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9378c-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9378c-156">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9378c-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9378c-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9378c-157">CommonParameters</span></span>

<span data-ttu-id="9378c-158">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="9378c-158">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9378c-159">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9378c-159">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9378c-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9378c-160">INPUTS</span></span>

### <span data-ttu-id="9378c-161">System.String</span><span class="sxs-lookup"><span data-stu-id="9378c-161">System.String</span></span>

<span data-ttu-id="9378c-162">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="9378c-162">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9378c-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9378c-163">OUTPUTS</span></span>

### <span data-ttu-id="9378c-164">Нет</span><span class="sxs-lookup"><span data-stu-id="9378c-164">None</span></span>

<span data-ttu-id="9378c-165">Команда не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9378c-165">The command does not generate any output.</span></span>
<span data-ttu-id="9378c-166">Однако выходные данные могут быть созданы элементом, который он вызывает.</span><span class="sxs-lookup"><span data-stu-id="9378c-166">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="9378c-167">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9378c-167">NOTES</span></span>

<span data-ttu-id="9378c-168">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="9378c-168">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9378c-169">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="9378c-169">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9378c-170">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9378c-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9378c-171">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9378c-171">RELATED LINKS</span></span>

[<span data-ttu-id="9378c-172">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-172">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="9378c-173">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-173">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="9378c-174">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-174">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="9378c-175">Move-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-175">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="9378c-176">New-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-176">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="9378c-177">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-177">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="9378c-178">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-178">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="9378c-179">Set-Item</span><span class="sxs-lookup"><span data-stu-id="9378c-179">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="9378c-180">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9378c-180">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


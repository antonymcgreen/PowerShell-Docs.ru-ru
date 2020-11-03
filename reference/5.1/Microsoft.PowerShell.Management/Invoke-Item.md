---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 6aac74b9b084996377b97997ab78972cb28b0959
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228357"
---
# <span data-ttu-id="a732e-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-103">Invoke-Item</span></span>

## <span data-ttu-id="a732e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a732e-104">SYNOPSIS</span></span>
<span data-ttu-id="a732e-105">Выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="a732e-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="a732e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a732e-106">SYNTAX</span></span>

### <span data-ttu-id="a732e-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a732e-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a732e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a732e-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="a732e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a732e-109">DESCRIPTION</span></span>

<span data-ttu-id="a732e-110">`Invoke-Item`Командлет выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="a732e-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="a732e-111">Например, он запускает исполняемый файл или открывает файл документа в приложении, связанном с данным типом файла.</span><span class="sxs-lookup"><span data-stu-id="a732e-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="a732e-112">Действие по умолчанию зависит от типа элемента и определяется поставщиком PowerShell, предоставляющим доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="a732e-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="a732e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="a732e-113">EXAMPLES</span></span>

### <span data-ttu-id="a732e-114">Пример 1. Открытие файла</span><span class="sxs-lookup"><span data-stu-id="a732e-114">Example 1: Open a file</span></span>

<span data-ttu-id="a732e-115">Эта команда открывает файл "aliasApr04.doc" в Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="a732e-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="a732e-116">В этом случае открытие в Word является действием по умолчанию для файлов с расширением doc.</span><span class="sxs-lookup"><span data-stu-id="a732e-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="a732e-117">Пример 2. Открытие всех файлов определенного типа</span><span class="sxs-lookup"><span data-stu-id="a732e-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="a732e-118">Эта команда открывает все Microsoft Office электронные таблицы Excel в папке "C:\Documents and Сеттингс\листер\ми Documents".</span><span class="sxs-lookup"><span data-stu-id="a732e-118">This command opens all of the Microsoft Office Excel spreadsheets in the "C:\Documents and Settings\Lister\My Documents" folder.</span></span>
<span data-ttu-id="a732e-119">Каждая таблица открывается в новом экземпляре Excel.</span><span class="sxs-lookup"><span data-stu-id="a732e-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="a732e-120">В этом случае открытие в Excel является действием по умолчанию для файлов с расширением XLS.</span><span class="sxs-lookup"><span data-stu-id="a732e-120">In this case, opening in Excel is the default action for ".xls" files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="a732e-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a732e-121">PARAMETERS</span></span>

### <span data-ttu-id="a732e-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="a732e-122">-Credential</span></span>

<span data-ttu-id="a732e-123">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="a732e-123">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="a732e-124">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="a732e-124">The default is the current user.</span></span>

<span data-ttu-id="a732e-125">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="a732e-125">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="a732e-126">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="a732e-126">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="a732e-127">Этот параметр не поддерживается поставщиками, которые устанавливаются вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a732e-127">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="a732e-128">-Exclude</span><span class="sxs-lookup"><span data-stu-id="a732e-128">-Exclude</span></span>

<span data-ttu-id="a732e-129">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="a732e-129">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="a732e-130">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a732e-130">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a732e-131">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="a732e-131">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a732e-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a732e-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a732e-133">-Filter</span><span class="sxs-lookup"><span data-stu-id="a732e-133">-Filter</span></span>

<span data-ttu-id="a732e-134">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="a732e-134">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="a732e-135">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a732e-135">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="a732e-136">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="a732e-136">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="a732e-137">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="a732e-137">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a732e-138">-Include</span><span class="sxs-lookup"><span data-stu-id="a732e-138">-Include</span></span>

<span data-ttu-id="a732e-139">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="a732e-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="a732e-140">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a732e-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="a732e-141">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="a732e-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="a732e-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a732e-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a732e-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a732e-143">-LiteralPath</span></span>

<span data-ttu-id="a732e-144">Указывает путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="a732e-144">Specifies a path to the item.</span></span>
<span data-ttu-id="a732e-145">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="a732e-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="a732e-146">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="a732e-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="a732e-147">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a732e-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="a732e-148">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="a732e-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a732e-149">-Path</span><span class="sxs-lookup"><span data-stu-id="a732e-149">-Path</span></span>

<span data-ttu-id="a732e-150">Указывает путь к выбранному элементу.</span><span class="sxs-lookup"><span data-stu-id="a732e-150">Specifies the path to the selected item.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a732e-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="a732e-151">-UseTransaction</span></span>

<span data-ttu-id="a732e-152">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a732e-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="a732e-153">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="a732e-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="a732e-154">Дополнительные сведения см. в разделе about_transactions.</span><span class="sxs-lookup"><span data-stu-id="a732e-154">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a732e-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a732e-155">-Confirm</span></span>
<span data-ttu-id="a732e-156">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a732e-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a732e-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a732e-157">-WhatIf</span></span>

<span data-ttu-id="a732e-158">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a732e-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a732e-159">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a732e-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a732e-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a732e-160">CommonParameters</span></span>

<span data-ttu-id="a732e-161">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a732e-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a732e-162">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a732e-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a732e-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a732e-163">INPUTS</span></span>

### <span data-ttu-id="a732e-164">System.String</span><span class="sxs-lookup"><span data-stu-id="a732e-164">System.String</span></span>

<span data-ttu-id="a732e-165">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="a732e-165">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a732e-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a732e-166">OUTPUTS</span></span>

### <span data-ttu-id="a732e-167">Нет</span><span class="sxs-lookup"><span data-stu-id="a732e-167">None</span></span>

<span data-ttu-id="a732e-168">Команда не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a732e-168">The command does not generate any output.</span></span>
<span data-ttu-id="a732e-169">Однако выходные данные могут быть созданы элементом, который он вызывает.</span><span class="sxs-lookup"><span data-stu-id="a732e-169">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="a732e-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a732e-170">NOTES</span></span>

<span data-ttu-id="a732e-171">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a732e-171">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a732e-172">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="a732e-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a732e-173">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="a732e-173">For more information, see about_Providers.</span></span>

## <span data-ttu-id="a732e-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a732e-174">RELATED LINKS</span></span>

[<span data-ttu-id="a732e-175">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-175">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="a732e-176">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-176">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="a732e-177">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-177">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a732e-178">Move-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-178">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="a732e-179">New-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-179">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="a732e-180">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-180">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="a732e-181">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-181">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="a732e-182">Set-Item</span><span class="sxs-lookup"><span data-stu-id="a732e-182">Set-Item</span></span>](Set-Item.md)

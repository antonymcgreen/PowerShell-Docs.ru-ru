---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: ebb79f16447aef2dd194505d805a34353f710e69
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604780"
---
# <span data-ttu-id="444fa-102">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-102">Invoke-Item</span></span>

## <span data-ttu-id="444fa-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="444fa-103">SYNOPSIS</span></span>
<span data-ttu-id="444fa-104">Выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="444fa-104">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="444fa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="444fa-105">SYNTAX</span></span>

### <span data-ttu-id="444fa-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="444fa-106">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="444fa-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="444fa-107">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="444fa-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="444fa-108">DESCRIPTION</span></span>

<span data-ttu-id="444fa-109">`Invoke-Item`Командлет выполняет действие по умолчанию для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="444fa-109">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="444fa-110">Например, он запускает исполняемый файл или открывает файл документа в приложении, связанном с данным типом файла.</span><span class="sxs-lookup"><span data-stu-id="444fa-110">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="444fa-111">Действие по умолчанию зависит от типа элемента и определяется поставщиком PowerShell, предоставляющим доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="444fa-111">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="444fa-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="444fa-112">EXAMPLES</span></span>

### <span data-ttu-id="444fa-113">Пример 1. Открытие файла</span><span class="sxs-lookup"><span data-stu-id="444fa-113">Example 1: Open a file</span></span>

<span data-ttu-id="444fa-114">Эта команда открывает файл "aliasApr04.doc" в Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="444fa-114">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="444fa-115">В этом случае открытие в Word является действием по умолчанию для файлов с расширением doc.</span><span class="sxs-lookup"><span data-stu-id="444fa-115">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="444fa-116">Пример 2. Открытие всех файлов определенного типа</span><span class="sxs-lookup"><span data-stu-id="444fa-116">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="444fa-117">Эта команда открывает все Microsoft Office электронные таблицы Excel в `C:\Documents and
Settings\Lister\My Documents` папке.</span><span class="sxs-lookup"><span data-stu-id="444fa-117">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="444fa-118">Каждая таблица открывается в новом экземпляре Excel.</span><span class="sxs-lookup"><span data-stu-id="444fa-118">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="444fa-119">В этом случае открытие в Excel является действием по умолчанию для `.xls` файлов.</span><span class="sxs-lookup"><span data-stu-id="444fa-119">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="444fa-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="444fa-120">PARAMETERS</span></span>

### <span data-ttu-id="444fa-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="444fa-121">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="444fa-122">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="444fa-122">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="444fa-123">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="444fa-123">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="444fa-124">-Exclude</span><span class="sxs-lookup"><span data-stu-id="444fa-124">-Exclude</span></span>

<span data-ttu-id="444fa-125">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="444fa-125">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="444fa-126">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="444fa-126">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="444fa-127">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="444fa-127">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="444fa-128">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="444fa-128">Wildcard characters are permitted.</span></span> <span data-ttu-id="444fa-129">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="444fa-129">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="444fa-130">-Filter</span><span class="sxs-lookup"><span data-stu-id="444fa-130">-Filter</span></span>

<span data-ttu-id="444fa-131">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="444fa-131">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="444fa-132">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="444fa-132">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="444fa-133">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="444fa-133">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="444fa-134">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="444fa-134">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="444fa-135">-Include</span><span class="sxs-lookup"><span data-stu-id="444fa-135">-Include</span></span>

<span data-ttu-id="444fa-136">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="444fa-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="444fa-137">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="444fa-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="444fa-138">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="444fa-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="444fa-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="444fa-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="444fa-140">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="444fa-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="444fa-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="444fa-141">-LiteralPath</span></span>

<span data-ttu-id="444fa-142">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="444fa-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="444fa-143">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="444fa-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="444fa-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="444fa-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="444fa-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="444fa-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="444fa-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="444fa-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="444fa-147">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="444fa-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="444fa-148">-Path</span><span class="sxs-lookup"><span data-stu-id="444fa-148">-Path</span></span>

<span data-ttu-id="444fa-149">Указывает путь к выбранному элементу.</span><span class="sxs-lookup"><span data-stu-id="444fa-149">Specifies the path to the selected item.</span></span>
<span data-ttu-id="444fa-150">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="444fa-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="444fa-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="444fa-151">-Confirm</span></span>

<span data-ttu-id="444fa-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="444fa-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="444fa-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="444fa-153">-WhatIf</span></span>

<span data-ttu-id="444fa-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="444fa-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="444fa-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="444fa-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="444fa-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="444fa-156">CommonParameters</span></span>

<span data-ttu-id="444fa-157">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="444fa-157">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="444fa-158">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="444fa-158">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="444fa-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="444fa-159">INPUTS</span></span>

### <span data-ttu-id="444fa-160">System.String</span><span class="sxs-lookup"><span data-stu-id="444fa-160">System.String</span></span>

<span data-ttu-id="444fa-161">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="444fa-161">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="444fa-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="444fa-162">OUTPUTS</span></span>

### <span data-ttu-id="444fa-163">None</span><span class="sxs-lookup"><span data-stu-id="444fa-163">None</span></span>

<span data-ttu-id="444fa-164">Команда не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="444fa-164">The command does not generate any output.</span></span>
<span data-ttu-id="444fa-165">Однако выходные данные могут быть созданы элементом, который он вызывает.</span><span class="sxs-lookup"><span data-stu-id="444fa-165">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="444fa-166">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="444fa-166">NOTES</span></span>

<span data-ttu-id="444fa-167">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="444fa-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="444fa-168">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="444fa-168">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="444fa-169">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="444fa-169">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="444fa-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="444fa-170">RELATED LINKS</span></span>

[<span data-ttu-id="444fa-171">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-171">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="444fa-172">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-172">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="444fa-173">Get-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-173">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="444fa-174">Move-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-174">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="444fa-175">New-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-175">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="444fa-176">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-176">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="444fa-177">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-177">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="444fa-178">Set-Item</span><span class="sxs-lookup"><span data-stu-id="444fa-178">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="444fa-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="444fa-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)


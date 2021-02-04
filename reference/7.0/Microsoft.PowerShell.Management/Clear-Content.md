---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 9ffe7510745e92c6863cf08d143f89e214ae9133
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692971"
---
# <span data-ttu-id="6b17a-102">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="6b17a-102">Clear-Content</span></span>

## <span data-ttu-id="6b17a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6b17a-103">SYNOPSIS</span></span>
<span data-ttu-id="6b17a-104">Удаляет содержимое элемента без удаления самого элемента.</span><span class="sxs-lookup"><span data-stu-id="6b17a-104">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="6b17a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b17a-105">SYNTAX</span></span>

### <span data-ttu-id="6b17a-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6b17a-106">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="6b17a-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6b17a-107">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="6b17a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6b17a-108">DESCRIPTION</span></span>

<span data-ttu-id="6b17a-109">`Clear-Content`Командлет удаляет содержимое элемента, например удаление текста из файла, но не удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="6b17a-109">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="6b17a-110">В результате элемент существует, но является пустым.</span><span class="sxs-lookup"><span data-stu-id="6b17a-110">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="6b17a-111">Объект `Clear-Content` аналогичен `Clear-Item` , но он работает с элементами с содержимым, а не с элементами со значениями.</span><span class="sxs-lookup"><span data-stu-id="6b17a-111">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="6b17a-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="6b17a-112">EXAMPLES</span></span>

### <span data-ttu-id="6b17a-113">Пример 1. Удаление всего содержимого из каталога</span><span class="sxs-lookup"><span data-stu-id="6b17a-113">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="6b17a-114">Эта команда удаляет все содержимое файлов с именем "init.txt", содержащихся во всех вложенных каталогах каталога SmpUsers.</span><span class="sxs-lookup"><span data-stu-id="6b17a-114">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="6b17a-115">Сами файлы не удаляются, но становятся пустыми.</span><span class="sxs-lookup"><span data-stu-id="6b17a-115">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="6b17a-116">Пример 2. Удаление содержимого всех файлов с подстановочным знаком</span><span class="sxs-lookup"><span data-stu-id="6b17a-116">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="6b17a-117">Эта команда удаляет содержимое всех файлов из текущего каталога с расширением LOG, включая файлы с атрибутом «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="6b17a-117">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span> <span data-ttu-id="6b17a-118">Звездочка ( \* ) в пути представляет все элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6b17a-118">The asterisk (\*) in the path represents all items in the current directory.</span></span> <span data-ttu-id="6b17a-119">Параметр **Force** делает команду эффективной для файлов только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6b17a-119">The **Force** parameter makes the command effective on read-only files.</span></span> <span data-ttu-id="6b17a-120">Использование фильтра для ограничения команды файлами с расширением log, а не указанием \* . log в пути делает операцию быстрее.</span><span class="sxs-lookup"><span data-stu-id="6b17a-120">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="6b17a-121">Пример 3. Очистка всех данных из потока</span><span class="sxs-lookup"><span data-stu-id="6b17a-121">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="6b17a-122">В этом примере показано, как `Clear-Content` командлет очищает содержимое из альтернативного потока данных, оставляя поток нетронутым.</span><span class="sxs-lookup"><span data-stu-id="6b17a-122">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="6b17a-123">Первая команда использует `Get-Content` командлет для получения содержимого `Zone.Identifier` потока в файле Copy-Script.ps1, который был скачан из Интернета.</span><span class="sxs-lookup"><span data-stu-id="6b17a-123">The first command uses the `Get-Content` cmdlet to get the content of the `Zone.Identifier` stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="6b17a-124">Вторая команда использует `Clear-Content` командлет для очистки содержимого.</span><span class="sxs-lookup"><span data-stu-id="6b17a-124">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="6b17a-125">Третья команда повторяет первую команду.</span><span class="sxs-lookup"><span data-stu-id="6b17a-125">The third command repeats the first command.</span></span> <span data-ttu-id="6b17a-126">Он проверяет, что содержимое сброшено, но поток остается.</span><span class="sxs-lookup"><span data-stu-id="6b17a-126">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="6b17a-127">Если поток был удален, команда выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="6b17a-127">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="6b17a-128">Для очистки содержимого альтернативного потока данных можно использовать метод, подобный этому.</span><span class="sxs-lookup"><span data-stu-id="6b17a-128">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="6b17a-129">Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="6b17a-129">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="6b17a-130">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="6b17a-130">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="6b17a-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b17a-131">PARAMETERS</span></span>

### <span data-ttu-id="6b17a-132">-Stream</span><span class="sxs-lookup"><span data-stu-id="6b17a-132">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="6b17a-133">Этот параметр доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="6b17a-133">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="6b17a-134">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="6b17a-134">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="6b17a-135">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="6b17a-135">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="6b17a-136">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6b17a-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="6b17a-137">Stream — это динамический параметр, к которому добавляется поставщик FileSystem `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="6b17a-137">Stream is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="6b17a-138">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="6b17a-138">This parameter works only in file system drives.</span></span>

<span data-ttu-id="6b17a-139">`Clear-Content`С помощью командлета можно изменить содержимое файла с альтернативным потоком данных, например `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="6b17a-139">You can use the `Clear-Content` cmdlet to change the content of amy alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="6b17a-140">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="6b17a-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="6b17a-141">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="6b17a-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b17a-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="6b17a-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="6b17a-143">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b17a-143">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="6b17a-144">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте команду Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="6b17a-144">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="6b17a-145">-Exclude</span><span class="sxs-lookup"><span data-stu-id="6b17a-145">-Exclude</span></span>

<span data-ttu-id="6b17a-146">Указывает в виде строкового массива строки, которые этот командлет опускает из пути к содержимому.</span><span class="sxs-lookup"><span data-stu-id="6b17a-146">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span> <span data-ttu-id="6b17a-147">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="6b17a-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6b17a-148">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="6b17a-148">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="6b17a-149">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6b17a-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="6b17a-150">-Filter</span></span>

<span data-ttu-id="6b17a-151">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="6b17a-151">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="6b17a-152">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="6b17a-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6b17a-153">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="6b17a-153">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="6b17a-154">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="6b17a-154">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="6b17a-155">-Force</span><span class="sxs-lookup"><span data-stu-id="6b17a-155">-Force</span></span>

<span data-ttu-id="6b17a-156">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="6b17a-156">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6b17a-157">-Include</span><span class="sxs-lookup"><span data-stu-id="6b17a-157">-Include</span></span>

<span data-ttu-id="6b17a-158">Указывает в виде массива строк содержимое, которое очищает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="6b17a-158">Specifies, as a string array, content that this cmdlet clears.</span></span> <span data-ttu-id="6b17a-159">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="6b17a-159">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6b17a-160">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="6b17a-160">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="6b17a-161">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-161">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6b17a-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6b17a-162">-LiteralPath</span></span>

<span data-ttu-id="6b17a-163">Задает путь к элементам, содержимое которых требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="6b17a-163">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="6b17a-164">В отличие от параметра **Path**, значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="6b17a-164">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="6b17a-165">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-165">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="6b17a-166">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-166">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6b17a-167">Одинарные кавычки указывают, что PowerShell не интерпретирует какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="6b17a-167">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="6b17a-168">-Path</span><span class="sxs-lookup"><span data-stu-id="6b17a-168">-Path</span></span>

<span data-ttu-id="6b17a-169">Задает путь к элементам, содержимое которых требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="6b17a-169">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="6b17a-170">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-170">Wildcards are permitted.</span></span> <span data-ttu-id="6b17a-171">Пути должны вести к элементам, а не к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="6b17a-171">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="6b17a-172">Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="6b17a-172">For example, you must specify a path to one or more files, not a path to a directory.</span></span> <span data-ttu-id="6b17a-173">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6b17a-173">Wildcards are permitted.</span></span> <span data-ttu-id="6b17a-174">Этот параметр обязателен, но его имя (Path) можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="6b17a-174">This parameter is required, but the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6b17a-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6b17a-175">-Confirm</span></span>

<span data-ttu-id="6b17a-176">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6b17a-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b17a-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6b17a-177">-WhatIf</span></span>

<span data-ttu-id="6b17a-178">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6b17a-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6b17a-179">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6b17a-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6b17a-180">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6b17a-180">CommonParameters</span></span>

<span data-ttu-id="6b17a-181">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6b17a-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b17a-182">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6b17a-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>


## <span data-ttu-id="6b17a-183">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6b17a-183">INPUTS</span></span>

### <span data-ttu-id="6b17a-184">Нет</span><span class="sxs-lookup"><span data-stu-id="6b17a-184">None</span></span>

<span data-ttu-id="6b17a-185">Вы не можете передать объекты в `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="6b17a-185">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="6b17a-186">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6b17a-186">OUTPUTS</span></span>

### <span data-ttu-id="6b17a-187">Нет</span><span class="sxs-lookup"><span data-stu-id="6b17a-187">None</span></span>

<span data-ttu-id="6b17a-188">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="6b17a-188">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="6b17a-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6b17a-189">NOTES</span></span>

<span data-ttu-id="6b17a-190">Можно использовать `Clear-Content` с поставщиком файловой системы PowerShell и с другими поставщиками, которые управляют содержимым.</span><span class="sxs-lookup"><span data-stu-id="6b17a-190">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span> <span data-ttu-id="6b17a-191">Чтобы очистить элементы, которые не считаются содержимым, например элементы, управляемые сертификатом PowerShell или поставщиками реестра, используйте `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="6b17a-191">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="6b17a-192">`Clear-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="6b17a-192">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="6b17a-193">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="6b17a-193">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="6b17a-194">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6b17a-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="6b17a-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6b17a-195">RELATED LINKS</span></span>

[<span data-ttu-id="6b17a-196">Add-Content</span><span class="sxs-lookup"><span data-stu-id="6b17a-196">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="6b17a-197">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6b17a-197">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="6b17a-198">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6b17a-198">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="6b17a-199">Set-Content</span><span class="sxs-lookup"><span data-stu-id="6b17a-199">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="6b17a-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6b17a-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

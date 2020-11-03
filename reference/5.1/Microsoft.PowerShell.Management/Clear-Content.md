---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: b318abb06d36be5e28b9dcc3dc62fd4a70ab38fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228449"
---
# <span data-ttu-id="beb7a-103">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="beb7a-103">Clear-Content</span></span>

## <span data-ttu-id="beb7a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="beb7a-104">SYNOPSIS</span></span>
<span data-ttu-id="beb7a-105">Удаляет содержимое элемента без удаления самого элемента.</span><span class="sxs-lookup"><span data-stu-id="beb7a-105">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="beb7a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="beb7a-106">SYNTAX</span></span>

### <span data-ttu-id="beb7a-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="beb7a-107">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="beb7a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="beb7a-108">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="beb7a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="beb7a-109">DESCRIPTION</span></span>

<span data-ttu-id="beb7a-110">`Clear-Content`Командлет удаляет содержимое элемента, например удаление текста из файла, но не удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="beb7a-110">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="beb7a-111">В результате элемент существует, но является пустым.</span><span class="sxs-lookup"><span data-stu-id="beb7a-111">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="beb7a-112">Объект `Clear-Content` аналогичен `Clear-Item` , но он работает с элементами с содержимым, а не с элементами со значениями.</span><span class="sxs-lookup"><span data-stu-id="beb7a-112">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="beb7a-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="beb7a-113">EXAMPLES</span></span>

### <span data-ttu-id="beb7a-114">Пример 1. Удаление всего содержимого из каталога</span><span class="sxs-lookup"><span data-stu-id="beb7a-114">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="beb7a-115">Эта команда удаляет все содержимое файлов с именем "init.txt", содержащихся во всех вложенных каталогах каталога SmpUsers.</span><span class="sxs-lookup"><span data-stu-id="beb7a-115">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="beb7a-116">Сами файлы не удаляются, но становятся пустыми.</span><span class="sxs-lookup"><span data-stu-id="beb7a-116">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="beb7a-117">Пример 2. Удаление содержимого всех файлов с подстановочным знаком</span><span class="sxs-lookup"><span data-stu-id="beb7a-117">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="beb7a-118">Эта команда удаляет содержимое всех файлов из текущего каталога с расширением LOG, включая файлы с атрибутом «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="beb7a-118">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span>
<span data-ttu-id="beb7a-119">Звездочка ( \* ) в пути представляет все элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="beb7a-119">The asterisk (\*) in the path represents all items in the current directory.</span></span>
<span data-ttu-id="beb7a-120">Параметр **Force** делает команду эффективной для файлов только для чтения.</span><span class="sxs-lookup"><span data-stu-id="beb7a-120">The **Force** parameter makes the command effective on read-only files.</span></span>
<span data-ttu-id="beb7a-121">Использование фильтра для ограничения команды файлами с расширением log, а не указанием \* . log в пути делает операцию быстрее.</span><span class="sxs-lookup"><span data-stu-id="beb7a-121">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="beb7a-122">Пример 3. Очистка всех данных из потока</span><span class="sxs-lookup"><span data-stu-id="beb7a-122">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="beb7a-123">В этом примере показано, как `Clear-Content` командлет очищает содержимое из альтернативного потока данных, оставляя поток нетронутым.</span><span class="sxs-lookup"><span data-stu-id="beb7a-123">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="beb7a-124">Первая команда использует `Get-Content` командлет для получения содержимого зоны. идентификатор потока в файле Copy-Script.ps1, скачанном из Интернета.</span><span class="sxs-lookup"><span data-stu-id="beb7a-124">The first command uses the `Get-Content` cmdlet to get the content of the Zone.Identifier stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="beb7a-125">Вторая команда использует `Clear-Content` командлет для очистки содержимого.</span><span class="sxs-lookup"><span data-stu-id="beb7a-125">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="beb7a-126">Третья команда повторяет первую команду.</span><span class="sxs-lookup"><span data-stu-id="beb7a-126">The third command repeats the first command.</span></span> <span data-ttu-id="beb7a-127">Он проверяет, что содержимое сброшено, но поток остается.</span><span class="sxs-lookup"><span data-stu-id="beb7a-127">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="beb7a-128">Если поток был удален, команда выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="beb7a-128">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="beb7a-129">Для очистки содержимого альтернативного потока данных можно использовать метод, подобный этому.</span><span class="sxs-lookup"><span data-stu-id="beb7a-129">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="beb7a-130">Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="beb7a-130">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="beb7a-131">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="beb7a-131">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```powershell
Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
[ZoneTransfer]
ZoneId=3
```

```powershell
Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output

```

## <span data-ttu-id="beb7a-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="beb7a-132">PARAMETERS</span></span>

### <span data-ttu-id="beb7a-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="beb7a-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="beb7a-134">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb7a-134">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="beb7a-135">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте команду Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="beb7a-135">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="beb7a-136">-Exclude</span><span class="sxs-lookup"><span data-stu-id="beb7a-136">-Exclude</span></span>

<span data-ttu-id="beb7a-137">Указывает в виде строкового массива строки, которые этот командлет опускает из пути к содержимому.</span><span class="sxs-lookup"><span data-stu-id="beb7a-137">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span>
<span data-ttu-id="beb7a-138">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="beb7a-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="beb7a-139">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="beb7a-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="beb7a-140">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-140">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="beb7a-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="beb7a-141">-Filter</span></span>

<span data-ttu-id="beb7a-142">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="beb7a-142">Specifies a filter in the provider's format or language.</span></span>
<span data-ttu-id="beb7a-143">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="beb7a-143">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="beb7a-144">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="beb7a-144">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span>
<span data-ttu-id="beb7a-145">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="beb7a-145">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="beb7a-146">-Force</span><span class="sxs-lookup"><span data-stu-id="beb7a-146">-Force</span></span>

<span data-ttu-id="beb7a-147">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="beb7a-147">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="beb7a-148">-Include</span><span class="sxs-lookup"><span data-stu-id="beb7a-148">-Include</span></span>

<span data-ttu-id="beb7a-149">Указывает в виде массива строк содержимое, которое очищает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="beb7a-149">Specifies, as a string array, content that this cmdlet clears.</span></span>
<span data-ttu-id="beb7a-150">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="beb7a-150">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="beb7a-151">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="beb7a-151">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="beb7a-152">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-152">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="beb7a-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="beb7a-153">-LiteralPath</span></span>

<span data-ttu-id="beb7a-154">Задает путь к элементам, содержимое которых требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="beb7a-154">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="beb7a-155">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="beb7a-155">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="beb7a-156">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-156">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="beb7a-157">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="beb7a-158">Одинарные кавычки указывают, что PowerShell не интерпретирует какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="beb7a-158">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="beb7a-159">-Path</span><span class="sxs-lookup"><span data-stu-id="beb7a-159">-Path</span></span>

<span data-ttu-id="beb7a-160">Задает путь к элементам, содержимое которых требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="beb7a-160">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="beb7a-161">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-161">Wildcards are permitted.</span></span>
<span data-ttu-id="beb7a-162">Пути должны вести к элементам, а не к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="beb7a-162">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="beb7a-163">Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="beb7a-163">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="beb7a-164">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="beb7a-164">Wildcards are permitted.</span></span>
<span data-ttu-id="beb7a-165">Этот параметр обязателен, но его имя (Path) можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="beb7a-165">This parameter is required, but the parameter name ("Path") is optional.</span></span>

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

### <span data-ttu-id="beb7a-166">-Stream</span><span class="sxs-lookup"><span data-stu-id="beb7a-166">-Stream</span></span>

<span data-ttu-id="beb7a-167">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="beb7a-167">Specifies an alternative data stream for content.</span></span>
<span data-ttu-id="beb7a-168">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="beb7a-168">If the stream does not exist, this cmdlet creates it.</span></span>
<span data-ttu-id="beb7a-169">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="beb7a-169">Wildcard characters are not supported.</span></span>

<span data-ttu-id="beb7a-170">**Stream** — это динамический параметр, к которому добавляется поставщик FileSystem `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="beb7a-170">**Stream** is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="beb7a-171">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="beb7a-171">This parameter works only in file system drives.</span></span>

<span data-ttu-id="beb7a-172">`Clear-Content`С помощью командлета можно изменить содержимое зоны. альтернативный поток данных идентификатора.</span><span class="sxs-lookup"><span data-stu-id="beb7a-172">You can use the `Clear-Content` cmdlet to change the content of the Zone.Identifier alternate data stream.</span></span>
<span data-ttu-id="beb7a-173">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="beb7a-173">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span>
<span data-ttu-id="beb7a-174">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="beb7a-174">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="beb7a-175">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="beb7a-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="beb7a-176">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="beb7a-176">-UseTransaction</span></span>

<span data-ttu-id="beb7a-177">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="beb7a-177">Includes the command in the active transaction.</span></span>
<span data-ttu-id="beb7a-178">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="beb7a-178">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="beb7a-179">Дополнительные сведения см. в разделе [about_transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="beb7a-179">For more information, see [about_transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="beb7a-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="beb7a-180">-Confirm</span></span>

<span data-ttu-id="beb7a-181">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="beb7a-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="beb7a-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="beb7a-182">-WhatIf</span></span>

<span data-ttu-id="beb7a-183">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="beb7a-183">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="beb7a-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="beb7a-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="beb7a-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="beb7a-185">CommonParameters</span></span>

<span data-ttu-id="beb7a-186">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="beb7a-186">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="beb7a-187">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="beb7a-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="beb7a-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="beb7a-188">INPUTS</span></span>

### <span data-ttu-id="beb7a-189">Нет</span><span class="sxs-lookup"><span data-stu-id="beb7a-189">None</span></span>

<span data-ttu-id="beb7a-190">Вы не можете передать объекты в `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="beb7a-190">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="beb7a-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="beb7a-191">OUTPUTS</span></span>

### <span data-ttu-id="beb7a-192">Нет</span><span class="sxs-lookup"><span data-stu-id="beb7a-192">None</span></span>

<span data-ttu-id="beb7a-193">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="beb7a-193">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="beb7a-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="beb7a-194">NOTES</span></span>

<span data-ttu-id="beb7a-195">Можно использовать `Clear-Content` с поставщиком файловой системы PowerShell и с другими поставщиками, которые управляют содержимым.</span><span class="sxs-lookup"><span data-stu-id="beb7a-195">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span>
<span data-ttu-id="beb7a-196">Чтобы очистить элементы, которые не считаются содержимым, например элементы, управляемые сертификатом PowerShell или поставщиками реестра, используйте `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="beb7a-196">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="beb7a-197">`Clear-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="beb7a-197">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="beb7a-198">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="beb7a-198">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="beb7a-199">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="beb7a-199">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="beb7a-200">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="beb7a-200">RELATED LINKS</span></span>

[<span data-ttu-id="beb7a-201">Add-Content</span><span class="sxs-lookup"><span data-stu-id="beb7a-201">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="beb7a-202">Get-Content</span><span class="sxs-lookup"><span data-stu-id="beb7a-202">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="beb7a-203">Get-Item</span><span class="sxs-lookup"><span data-stu-id="beb7a-203">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="beb7a-204">Set-Content</span><span class="sxs-lookup"><span data-stu-id="beb7a-204">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="beb7a-205">about_Providers</span><span class="sxs-lookup"><span data-stu-id="beb7a-205">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: 32d8893190489be0a102b2db4dee3482133a4243
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860847"
---
# <span data-ttu-id="f6896-103">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="f6896-103">Start-Transcript</span></span>

## <span data-ttu-id="f6896-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f6896-104">Synopsis</span></span>
<span data-ttu-id="f6896-105">Создает запись для всего сеанса PowerShell или его части в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f6896-105">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="f6896-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6896-106">Syntax</span></span>

### <span data-ttu-id="f6896-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f6896-107">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="f6896-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f6896-108">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="f6896-109">бйоутпутдиректори</span><span class="sxs-lookup"><span data-stu-id="f6896-109">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="f6896-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f6896-110">Description</span></span>

<span data-ttu-id="f6896-111">`Start-Transcript`Командлет создает запись или часть сеанса PowerShell в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="f6896-111">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="f6896-112">Запись включает в себя все команды, вводимые пользователем, и все выходные данные, выводимые в консоли.</span><span class="sxs-lookup"><span data-stu-id="f6896-112">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="f6896-113">Начиная с Windows PowerShell 5,0, `Start-Transcript` содержит имя узла в созданном файле для всех записей.</span><span class="sxs-lookup"><span data-stu-id="f6896-113">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="f6896-114">Это особенно полезно, если ведение журнала предприятия является централизованным.</span><span class="sxs-lookup"><span data-stu-id="f6896-114">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="f6896-115">Файлы, создаваемые `Start-Transcript` командлетом, содержат случайные символы в именах, чтобы предотвратить возможную перезапись или дублирование при одновременном запуске двух или более записей.</span><span class="sxs-lookup"><span data-stu-id="f6896-115">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="f6896-116">Это также предотвращает несанкционированный Поиск записей, хранящихся в централизованном файловом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="f6896-116">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

<span data-ttu-id="f6896-117">При использовании параметра **append** , если целевой файл не имеет метки порядка БАЙТОВ (BOM), `Start-Transcript` по умолчанию используется `ASCII` Кодировка в целевом файле.</span><span class="sxs-lookup"><span data-stu-id="f6896-117">When using the **Append** parameter, if the target file doesn't have a Byte Order Mark (BOM) `Start-Transcript` defaults to `ASCII` encoding in the target file.</span></span> <span data-ttu-id="f6896-118">Такое поведение может привести к неправильному кодированию мулитбите символов в записи.</span><span class="sxs-lookup"><span data-stu-id="f6896-118">This behavior can result in improper encoding of mulitbyte characters in the transcript.</span></span>

## <span data-ttu-id="f6896-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="f6896-119">Examples</span></span>

### <span data-ttu-id="f6896-120">Пример 1. Запуск файла транскрипции с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f6896-120">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="f6896-121">Эта команда начинает записывать сеанс в файл в папке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6896-121">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="f6896-122">Пример 2. Запуск файла транскрипции в указанном расположении</span><span class="sxs-lookup"><span data-stu-id="f6896-122">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="f6896-123">Эта команда запускает запись в `Transcript0.txt` файле в `C:\transcripts` .</span><span class="sxs-lookup"><span data-stu-id="f6896-123">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="f6896-124">Так как используется параметр **NoClobber** , команда предотвращает перезапись существующих файлов.</span><span class="sxs-lookup"><span data-stu-id="f6896-124">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="f6896-125">Если `Transcript0.txt` файл уже существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f6896-125">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="f6896-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6896-126">Parameters</span></span>

### <span data-ttu-id="f6896-127">— Добавление</span><span class="sxs-lookup"><span data-stu-id="f6896-127">-Append</span></span>

<span data-ttu-id="f6896-128">Указывает, что этот командлет добавляет новую запись в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="f6896-128">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="f6896-129">Используйте параметр **path** , чтобы указать файл.</span><span class="sxs-lookup"><span data-stu-id="f6896-129">Use the **Path** parameter to specify the file.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-130">-Force</span><span class="sxs-lookup"><span data-stu-id="f6896-130">-Force</span></span>

<span data-ttu-id="f6896-131">Позволяет командлету добавить запись к существующему файлу, доступному только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f6896-131">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="f6896-132">При использовании применительно к файлу, доступному только для чтения, этот командлет изменяет разрешения файла, делая его доступным для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="f6896-132">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="f6896-133">Командлет не может переопределить ограничения безопасности при использовании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f6896-133">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-134">-Инклудеинвокатионхеадер</span><span class="sxs-lookup"><span data-stu-id="f6896-134">-IncludeInvocationHeader</span></span>

<span data-ttu-id="f6896-135">Указывает, что этот командлет регистрирует метку времени при выполнении команд.</span><span class="sxs-lookup"><span data-stu-id="f6896-135">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-136">-Усеминималхеадер</span><span class="sxs-lookup"><span data-stu-id="f6896-136">-UseMinimalHeader</span></span>

<span data-ttu-id="f6896-137">Добавьте в начало краткого заголовка записи, а не подробный заголовок, который включается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6896-137">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="f6896-138">Этот параметр был добавлен в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="f6896-138">This parameter was added in PowerShell 6.2.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f6896-139">-LiteralPath</span></span>

<span data-ttu-id="f6896-140">Задает расположение файла транскрипции.</span><span class="sxs-lookup"><span data-stu-id="f6896-140">Specifies a location to the transcript file.</span></span> <span data-ttu-id="f6896-141">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="f6896-141">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f6896-142">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f6896-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f6896-143">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f6896-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f6896-144">Одинарные кавычки сообщают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f6896-144">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-145">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="f6896-145">-NoClobber</span></span>

<span data-ttu-id="f6896-146">Указывает, что этот командлет не будет перезаписывать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="f6896-146">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="f6896-147">По умолчанию, если файл транскрипции существует по указанному пути, `Start-Transcript` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f6896-147">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-148">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="f6896-148">-OutputDirectory</span></span>

<span data-ttu-id="f6896-149">Указывает конкретный путь и папку для сохранения записи.</span><span class="sxs-lookup"><span data-stu-id="f6896-149">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="f6896-150">PowerShell автоматически назначает имя транскрипции.</span><span class="sxs-lookup"><span data-stu-id="f6896-150">PowerShell automatically assigns the transcript name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-151">-Path</span><span class="sxs-lookup"><span data-stu-id="f6896-151">-Path</span></span>

<span data-ttu-id="f6896-152">Задает расположение файла транскрипции.</span><span class="sxs-lookup"><span data-stu-id="f6896-152">Specifies a location to the transcript file.</span></span> <span data-ttu-id="f6896-153">Введите путь к `.txt` файлу.</span><span class="sxs-lookup"><span data-stu-id="f6896-153">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="f6896-154">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="f6896-154">Wildcards are not permitted.</span></span>

<span data-ttu-id="f6896-155">Если путь не указан, `Start-Transcript` использует путь в значении `$Transcript` глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="f6896-155">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="f6896-156">Если эта переменная не создана, сохраняет записи `Start-Transcript` в `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="f6896-156">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="f6896-157">Если какие-либо каталоги, указанные в пути, отсутствуют, команда завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="f6896-157">If any of the directories in the path do not exist, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6896-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f6896-158">-Confirm</span></span>

<span data-ttu-id="f6896-159">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f6896-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f6896-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f6896-160">-WhatIf</span></span>

<span data-ttu-id="f6896-161">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f6896-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f6896-162">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f6896-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f6896-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f6896-163">CommonParameters</span></span>

<span data-ttu-id="f6896-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f6896-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6896-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f6896-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6896-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f6896-166">Inputs</span></span>

### <span data-ttu-id="f6896-167">None</span><span class="sxs-lookup"><span data-stu-id="f6896-167">None</span></span>

<span data-ttu-id="f6896-168">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="f6896-168">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="f6896-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f6896-169">Outputs</span></span>

### <span data-ttu-id="f6896-170">System.String</span><span class="sxs-lookup"><span data-stu-id="f6896-170">System.String</span></span>

<span data-ttu-id="f6896-171">Этот командлет возвращает строку, содержащую сообщение подтверждения и путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="f6896-171">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="f6896-172">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6896-172">Notes</span></span>

<span data-ttu-id="f6896-173">Чтобы отключить запись разговора, используйте `Stop-Transcript` командлет.</span><span class="sxs-lookup"><span data-stu-id="f6896-173">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="f6896-174">Чтобы записать весь сеанс, добавьте `Start-Transcript` команду в профиль.</span><span class="sxs-lookup"><span data-stu-id="f6896-174">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="f6896-175">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f6896-175">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="f6896-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f6896-176">Related Links</span></span>

[<span data-ttu-id="f6896-177">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="f6896-177">Stop-Transcript</span></span>](Stop-Transcript.md)

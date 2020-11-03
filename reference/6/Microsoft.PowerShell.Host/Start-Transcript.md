---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: 2e4380163c7dc34c84460a1cfef3ef2f4b33507b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227262"
---
# <span data-ttu-id="67648-103">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="67648-103">Start-Transcript</span></span>

## <span data-ttu-id="67648-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="67648-104">SYNOPSIS</span></span>
<span data-ttu-id="67648-105">Создает запись для всего сеанса PowerShell или его части в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="67648-105">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="67648-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67648-106">SYNTAX</span></span>

### <span data-ttu-id="67648-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="67648-107">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="67648-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="67648-108">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="67648-109">бйоутпутдиректори</span><span class="sxs-lookup"><span data-stu-id="67648-109">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="67648-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67648-110">DESCRIPTION</span></span>

<span data-ttu-id="67648-111">`Start-Transcript`Командлет создает запись или часть сеанса PowerShell в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="67648-111">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="67648-112">Запись включает в себя все команды, вводимые пользователем, и все выходные данные, выводимые в консоли.</span><span class="sxs-lookup"><span data-stu-id="67648-112">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="67648-113">Начиная с Windows PowerShell 5,0, `Start-Transcript` содержит имя узла в созданном файле для всех записей.</span><span class="sxs-lookup"><span data-stu-id="67648-113">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="67648-114">Это особенно полезно, если ведение журнала предприятия является централизованным.</span><span class="sxs-lookup"><span data-stu-id="67648-114">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="67648-115">Файлы, создаваемые `Start-Transcript` командлетом, содержат случайные символы в именах, чтобы предотвратить возможную перезапись или дублирование при одновременном запуске двух или более записей.</span><span class="sxs-lookup"><span data-stu-id="67648-115">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="67648-116">Это также предотвращает несанкционированный Поиск записей, хранящихся в централизованном файловом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="67648-116">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

## <span data-ttu-id="67648-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="67648-117">EXAMPLES</span></span>

### <span data-ttu-id="67648-118">Пример 1. Запуск файла транскрипции с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="67648-118">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="67648-119">Эта команда начинает записывать сеанс в файл в папке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67648-119">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="67648-120">Пример 2. Запуск файла транскрипции в указанном расположении</span><span class="sxs-lookup"><span data-stu-id="67648-120">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="67648-121">Эта команда запускает запись в `Transcript0.txt` файле в `C:\transcripts` .</span><span class="sxs-lookup"><span data-stu-id="67648-121">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="67648-122">Так как используется параметр **NoClobber** , команда предотвращает перезапись существующих файлов.</span><span class="sxs-lookup"><span data-stu-id="67648-122">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="67648-123">Если `Transcript0.txt` файл уже существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="67648-123">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="67648-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67648-124">PARAMETERS</span></span>

### <span data-ttu-id="67648-125">— Добавление</span><span class="sxs-lookup"><span data-stu-id="67648-125">-Append</span></span>

<span data-ttu-id="67648-126">Указывает, что этот командлет добавляет новую запись в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="67648-126">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="67648-127">Используйте параметр **path** , чтобы указать файл.</span><span class="sxs-lookup"><span data-stu-id="67648-127">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="67648-128">-Force</span><span class="sxs-lookup"><span data-stu-id="67648-128">-Force</span></span>

<span data-ttu-id="67648-129">Позволяет командлету добавить запись к существующему файлу, доступному только для чтения.</span><span class="sxs-lookup"><span data-stu-id="67648-129">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="67648-130">При использовании применительно к файлу, доступному только для чтения, этот командлет изменяет разрешения файла, делая его доступным для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="67648-130">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="67648-131">Командлет не может переопределить ограничения безопасности при использовании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="67648-131">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="67648-132">-Инклудеинвокатионхеадер</span><span class="sxs-lookup"><span data-stu-id="67648-132">-IncludeInvocationHeader</span></span>

<span data-ttu-id="67648-133">Указывает, что этот командлет регистрирует метку времени при выполнении команд.</span><span class="sxs-lookup"><span data-stu-id="67648-133">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="67648-134">-Усеминималхеадер</span><span class="sxs-lookup"><span data-stu-id="67648-134">-UseMinimalHeader</span></span>

<span data-ttu-id="67648-135">Добавьте в начало краткого заголовка записи, а не подробный заголовок, который включается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67648-135">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="67648-136">Этот параметр был добавлен в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="67648-136">This parameter was added in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="67648-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67648-137">-LiteralPath</span></span>

<span data-ttu-id="67648-138">Задает расположение файла транскрипции.</span><span class="sxs-lookup"><span data-stu-id="67648-138">Specifies a location to the transcript file.</span></span> <span data-ttu-id="67648-139">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="67648-139">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="67648-140">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="67648-140">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="67648-141">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="67648-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="67648-142">Одинарные кавычки сообщают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="67648-142">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="67648-143">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="67648-143">-NoClobber</span></span>

<span data-ttu-id="67648-144">Указывает, что этот командлет не будет перезаписывать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="67648-144">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="67648-145">По умолчанию, если файл транскрипции существует по указанному пути, `Start-Transcript` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="67648-145">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="67648-146">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="67648-146">-OutputDirectory</span></span>

<span data-ttu-id="67648-147">Указывает конкретный путь и папку для сохранения записи.</span><span class="sxs-lookup"><span data-stu-id="67648-147">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="67648-148">PowerShell автоматически назначает имя транскрипции.</span><span class="sxs-lookup"><span data-stu-id="67648-148">PowerShell automatically assigns the transcript name.</span></span>

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

### <span data-ttu-id="67648-149">-Path</span><span class="sxs-lookup"><span data-stu-id="67648-149">-Path</span></span>

<span data-ttu-id="67648-150">Задает расположение файла транскрипции.</span><span class="sxs-lookup"><span data-stu-id="67648-150">Specifies a location to the transcript file.</span></span> <span data-ttu-id="67648-151">Введите путь к `.txt` файлу.</span><span class="sxs-lookup"><span data-stu-id="67648-151">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="67648-152">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="67648-152">Wildcards are not permitted.</span></span>

<span data-ttu-id="67648-153">Если путь не указан, `Start-Transcript` использует путь в значении `$Transcript` глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="67648-153">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="67648-154">Если эта переменная не создана, сохраняет записи `Start-Transcript` в `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="67648-154">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="67648-155">Если какие-либо каталоги, указанные в пути, отсутствуют, команда завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="67648-155">If any of the directories in the path do not exist, the command fails.</span></span>

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

### <span data-ttu-id="67648-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="67648-156">-Confirm</span></span>

<span data-ttu-id="67648-157">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="67648-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="67648-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="67648-158">-WhatIf</span></span>

<span data-ttu-id="67648-159">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="67648-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="67648-160">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="67648-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="67648-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="67648-161">CommonParameters</span></span>

<span data-ttu-id="67648-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="67648-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="67648-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="67648-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="67648-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="67648-164">INPUTS</span></span>

### <span data-ttu-id="67648-165">Нет</span><span class="sxs-lookup"><span data-stu-id="67648-165">None</span></span>

<span data-ttu-id="67648-166">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="67648-166">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="67648-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="67648-167">OUTPUTS</span></span>

### <span data-ttu-id="67648-168">System.String</span><span class="sxs-lookup"><span data-stu-id="67648-168">System.String</span></span>

<span data-ttu-id="67648-169">Этот командлет возвращает строку, содержащую сообщение подтверждения и путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="67648-169">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="67648-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="67648-170">NOTES</span></span>

<span data-ttu-id="67648-171">Чтобы отключить запись разговора, используйте `Stop-Transcript` командлет.</span><span class="sxs-lookup"><span data-stu-id="67648-171">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="67648-172">Чтобы записать весь сеанс, добавьте `Start-Transcript` команду в профиль.</span><span class="sxs-lookup"><span data-stu-id="67648-172">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="67648-173">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="67648-173">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="67648-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="67648-174">RELATED LINKS</span></span>

[<span data-ttu-id="67648-175">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="67648-175">Stop-Transcript</span></span>](Stop-Transcript.md)

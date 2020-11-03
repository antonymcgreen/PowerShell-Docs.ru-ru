---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: cbdb40edf85dd4645552f6e096a99384532b4443
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227422"
---
# <span data-ttu-id="75617-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="75617-103">Start-Trace</span></span>

## <span data-ttu-id="75617-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="75617-104">SYNOPSIS</span></span>
<span data-ttu-id="75617-105">Запустите сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="75617-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="75617-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75617-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="75617-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75617-107">DESCRIPTION</span></span>
<span data-ttu-id="75617-108">Этот командлет запускает сеанс ведения журнала трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="75617-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="75617-109">Этот командлет используется следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="75617-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="75617-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="75617-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="75617-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="75617-111">EXAMPLES</span></span>

### <span data-ttu-id="75617-112">Пример 1. Запуск сеанса ведения журнала трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="75617-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="75617-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75617-113">PARAMETERS</span></span>

### <span data-ttu-id="75617-114">-Буфферсизеинкб</span><span class="sxs-lookup"><span data-stu-id="75617-114">-BufferSizeInKB</span></span>
<span data-ttu-id="75617-115">Размер буфера сеанса трассировки событий в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="75617-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-116">-ETS</span><span class="sxs-lookup"><span data-stu-id="75617-116">-ETS</span></span>
<span data-ttu-id="75617-117">Отправка команд в сеансы трассировки событий напрямую без сохранения или планирования.</span><span class="sxs-lookup"><span data-stu-id="75617-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="75617-118">-Format</span><span class="sxs-lookup"><span data-stu-id="75617-118">-Format</span></span>
<span data-ttu-id="75617-119">Указывает формат журнала для сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="75617-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="75617-120">Для формата базы данных SQL необходимо использовать параметр **OutputFilePath** в командной строке со `dsn!log` значением.</span><span class="sxs-lookup"><span data-stu-id="75617-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="75617-121">Значение по умолчанию — binary (bin).</span><span class="sxs-lookup"><span data-stu-id="75617-121">The default is binary (bin).</span></span> <span data-ttu-id="75617-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="75617-122">The possible values are:</span></span>

- <span data-ttu-id="75617-123">bin — двоичный</span><span class="sxs-lookup"><span data-stu-id="75617-123">bin - binary</span></span>
- <span data-ttu-id="75617-124">бинЦирк-binary с циклическим ведением журнала</span><span class="sxs-lookup"><span data-stu-id="75617-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="75617-125">CSV — значения с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="75617-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="75617-126">TSV — значения, разделенные табуляцией</span><span class="sxs-lookup"><span data-stu-id="75617-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="75617-127">база данных SQL-SQL</span><span class="sxs-lookup"><span data-stu-id="75617-127">sql - SQL database</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-128">-Максбуфферс</span><span class="sxs-lookup"><span data-stu-id="75617-128">-MaxBuffers</span></span>
<span data-ttu-id="75617-129">Задает максимальное число буферов сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="75617-129">Sets the maximum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-130">-Макслогфилесизеинмб</span><span class="sxs-lookup"><span data-stu-id="75617-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="75617-131">Задает максимальный размер файла журнала в мегабайтах (МБ) или число записей для журналов SQL.</span><span class="sxs-lookup"><span data-stu-id="75617-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-132">-Минбуфферс</span><span class="sxs-lookup"><span data-stu-id="75617-132">-MinBuffers</span></span>
<span data-ttu-id="75617-133">Задает минимальное число буферов сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="75617-133">Sets the minimum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-134">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="75617-134">-OutputFilePath</span></span>
<span data-ttu-id="75617-135">Путь к выходному файлу журнала или имени DSN и набора журналов в базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="75617-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="75617-136">Путь по умолчанию: `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="75617-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-137">-Провидерфилепас</span><span class="sxs-lookup"><span data-stu-id="75617-137">-ProviderFilePath</span></span>
<span data-ttu-id="75617-138">Файл с указанием нескольких поставщиков трассировки событий для включения.</span><span class="sxs-lookup"><span data-stu-id="75617-138">File listing multiple Event Trace providers to enable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-139">-SessionName</span><span class="sxs-lookup"><span data-stu-id="75617-139">-SessionName</span></span>
<span data-ttu-id="75617-140">Имя сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="75617-140">The name of the Event Trace session.</span></span> <span data-ttu-id="75617-141">Для завершения сеанса трассировки необходимо иметь имя сеанса.</span><span class="sxs-lookup"><span data-stu-id="75617-141">To stop a trace session you must know the session name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75617-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="75617-142">CommonParameters</span></span>

<span data-ttu-id="75617-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75617-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75617-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75617-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75617-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="75617-145">INPUTS</span></span>

### <span data-ttu-id="75617-146">Нет</span><span class="sxs-lookup"><span data-stu-id="75617-146">None</span></span>

## <span data-ttu-id="75617-147">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="75617-147">OUTPUTS</span></span>

### <span data-ttu-id="75617-148">System.Object</span><span class="sxs-lookup"><span data-stu-id="75617-148">System.Object</span></span>

## <span data-ttu-id="75617-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="75617-149">NOTES</span></span>

## <span data-ttu-id="75617-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="75617-150">RELATED LINKS</span></span>

[<span data-ttu-id="75617-151">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="75617-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="75617-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="75617-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="75617-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="75617-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="75617-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="75617-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="75617-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="75617-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="75617-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="75617-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

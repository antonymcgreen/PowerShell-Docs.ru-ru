---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: b1c6a596f3dc35028b928c3a6b5459a805bc2512
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602284"
---
# <span data-ttu-id="6a64a-102">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="6a64a-102">Start-Trace</span></span>

## <span data-ttu-id="6a64a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6a64a-103">SYNOPSIS</span></span>
<span data-ttu-id="6a64a-104">Запустите сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="6a64a-104">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="6a64a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a64a-105">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="6a64a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a64a-106">DESCRIPTION</span></span>
<span data-ttu-id="6a64a-107">Этот командлет запускает сеанс ведения журнала трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="6a64a-107">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="6a64a-108">Этот командлет используется следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="6a64a-108">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="6a64a-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="6a64a-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="6a64a-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="6a64a-110">EXAMPLES</span></span>

### <span data-ttu-id="6a64a-111">Пример 1. Запуск сеанса ведения журнала трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="6a64a-111">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="6a64a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a64a-112">PARAMETERS</span></span>

### <span data-ttu-id="6a64a-113">-Буфферсизеинкб</span><span class="sxs-lookup"><span data-stu-id="6a64a-113">-BufferSizeInKB</span></span>
<span data-ttu-id="6a64a-114">Размер буфера сеанса трассировки событий в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="6a64a-114">Event Trace Session buffer size in kilobytes (KB).</span></span>

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

### <span data-ttu-id="6a64a-115">-ETS</span><span class="sxs-lookup"><span data-stu-id="6a64a-115">-ETS</span></span>
<span data-ttu-id="6a64a-116">Отправка команд в сеансы трассировки событий напрямую без сохранения или планирования.</span><span class="sxs-lookup"><span data-stu-id="6a64a-116">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="6a64a-117">-Format</span><span class="sxs-lookup"><span data-stu-id="6a64a-117">-Format</span></span>
<span data-ttu-id="6a64a-118">Указывает формат журнала для сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="6a64a-118">Specifies the log format for the data collector.</span></span> <span data-ttu-id="6a64a-119">Для формата базы данных SQL необходимо использовать параметр **OutputFilePath** в командной строке со `dsn!log` значением.</span><span class="sxs-lookup"><span data-stu-id="6a64a-119">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="6a64a-120">Значение по умолчанию — binary (bin).</span><span class="sxs-lookup"><span data-stu-id="6a64a-120">The default is binary (bin).</span></span> <span data-ttu-id="6a64a-121">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="6a64a-121">The possible values are:</span></span>

- <span data-ttu-id="6a64a-122">bin — двоичный</span><span class="sxs-lookup"><span data-stu-id="6a64a-122">bin - binary</span></span>
- <span data-ttu-id="6a64a-123">бинЦирк-binary с циклическим ведением журнала</span><span class="sxs-lookup"><span data-stu-id="6a64a-123">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="6a64a-124">CSV — значения с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="6a64a-124">csv - Comma-separated values</span></span>
- <span data-ttu-id="6a64a-125">TSV — значения, разделенные табуляцией</span><span class="sxs-lookup"><span data-stu-id="6a64a-125">tsv - Tab-separated values</span></span>
- <span data-ttu-id="6a64a-126">база данных SQL-SQL</span><span class="sxs-lookup"><span data-stu-id="6a64a-126">sql - SQL database</span></span>

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

### <span data-ttu-id="6a64a-127">-Максбуфферс</span><span class="sxs-lookup"><span data-stu-id="6a64a-127">-MaxBuffers</span></span>
<span data-ttu-id="6a64a-128">Задает максимальное число буферов сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="6a64a-128">Sets the maximum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="6a64a-129">-Макслогфилесизеинмб</span><span class="sxs-lookup"><span data-stu-id="6a64a-129">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="6a64a-130">Задает максимальный размер файла журнала в мегабайтах (МБ) или число записей для журналов SQL.</span><span class="sxs-lookup"><span data-stu-id="6a64a-130">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

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

### <span data-ttu-id="6a64a-131">-Минбуфферс</span><span class="sxs-lookup"><span data-stu-id="6a64a-131">-MinBuffers</span></span>
<span data-ttu-id="6a64a-132">Задает минимальное число буферов сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="6a64a-132">Sets the minimum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="6a64a-133">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="6a64a-133">-OutputFilePath</span></span>
<span data-ttu-id="6a64a-134">Путь к выходному файлу журнала или имени DSN и набора журналов в базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="6a64a-134">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="6a64a-135">Путь по умолчанию: `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="6a64a-135">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

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

### <span data-ttu-id="6a64a-136">-Провидерфилепас</span><span class="sxs-lookup"><span data-stu-id="6a64a-136">-ProviderFilePath</span></span>
<span data-ttu-id="6a64a-137">Файл с указанием нескольких поставщиков трассировки событий для включения.</span><span class="sxs-lookup"><span data-stu-id="6a64a-137">File listing multiple Event Trace providers to enable.</span></span>

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

### <span data-ttu-id="6a64a-138">-SessionName</span><span class="sxs-lookup"><span data-stu-id="6a64a-138">-SessionName</span></span>
<span data-ttu-id="6a64a-139">Имя сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="6a64a-139">The name of the Event Trace session.</span></span> <span data-ttu-id="6a64a-140">Для завершения сеанса трассировки необходимо иметь имя сеанса.</span><span class="sxs-lookup"><span data-stu-id="6a64a-140">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="6a64a-141">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6a64a-141">CommonParameters</span></span>

<span data-ttu-id="6a64a-142">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a64a-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a64a-143">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a64a-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a64a-144">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6a64a-144">INPUTS</span></span>

### <span data-ttu-id="6a64a-145">None</span><span class="sxs-lookup"><span data-stu-id="6a64a-145">None</span></span>

## <span data-ttu-id="6a64a-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6a64a-146">OUTPUTS</span></span>

### <span data-ttu-id="6a64a-147">None</span><span class="sxs-lookup"><span data-stu-id="6a64a-147">None</span></span>

## <span data-ttu-id="6a64a-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6a64a-148">NOTES</span></span>

## <span data-ttu-id="6a64a-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6a64a-149">RELATED LINKS</span></span>

[<span data-ttu-id="6a64a-150">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="6a64a-150">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="6a64a-151">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="6a64a-151">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="6a64a-152">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6a64a-152">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="6a64a-153">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6a64a-153">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="6a64a-154">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6a64a-154">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="6a64a-155">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6a64a-155">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)


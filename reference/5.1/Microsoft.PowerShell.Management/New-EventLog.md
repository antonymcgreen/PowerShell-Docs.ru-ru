---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227974"
---
# <span data-ttu-id="948e6-103">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-103">New-EventLog</span></span>

## <span data-ttu-id="948e6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="948e6-104">SYNOPSIS</span></span>
<span data-ttu-id="948e6-105">Создает новый журнал событий и новый источник событий на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="948e6-105">Creates a new event log and a new event source on a local or remote computer.</span></span>

## <span data-ttu-id="948e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="948e6-106">SYNTAX</span></span>

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## <span data-ttu-id="948e6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="948e6-107">DESCRIPTION</span></span>

<span data-ttu-id="948e6-108">Этот командлет создает классический журнал событий на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="948e6-108">This cmdlet creates a new classic event log on a local or remote computer.</span></span> <span data-ttu-id="948e6-109">С его помощью можно также зарегистрировать источник событий, записывающий данные в новый или существующий журнал.</span><span class="sxs-lookup"><span data-stu-id="948e6-109">It can also register an event source that writes to the new log or to an existing log.</span></span>

<span data-ttu-id="948e6-110">Командлеты с существительным EventLog (командлеты журнала событий) работают только с классическими журналами событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-110">The cmdlets that contain the EventLog noun (the Event log cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="948e6-111">Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="948e6-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use `Get-WinEvent`.</span></span>

## <span data-ttu-id="948e6-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="948e6-112">EXAMPLES</span></span>

### <span data-ttu-id="948e6-113">Пример 1. Создание нового журнала событий</span><span class="sxs-lookup"><span data-stu-id="948e6-113">Example 1 - create a new event log</span></span>

<span data-ttu-id="948e6-114">Эта команда создает журнал событий TestLog на локальном компьютере и регистрирует для него новый источник.</span><span class="sxs-lookup"><span data-stu-id="948e6-114">This command creates the TestLog event log on the local computer and registers a new source for it.</span></span>

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### <span data-ttu-id="948e6-115">Пример 2. Добавление нового источника событий в существующий журнал</span><span class="sxs-lookup"><span data-stu-id="948e6-115">Example 2 - add a new event source to an existing log</span></span>

<span data-ttu-id="948e6-116">Эта команда добавляет новый источник событий NewTestApp в журнал приложений на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="948e6-116">This command adds a new event source, NewTestApp, to the Application log on the Server01 remote computer.</span></span>

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

<span data-ttu-id="948e6-117">Команда требует, чтобы файл NewTestApp.dll находился на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="948e6-117">The command requires that the NewTestApp.dll file is located on the Server01 computer.</span></span>

## <span data-ttu-id="948e6-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="948e6-118">PARAMETERS</span></span>

### <span data-ttu-id="948e6-119">-Категориресаурцефиле</span><span class="sxs-lookup"><span data-stu-id="948e6-119">-CategoryResourceFile</span></span>

<span data-ttu-id="948e6-120">Указывает путь к файлу, содержащему строки категорий для исходных событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-120">Specifies the path to the file that contains category strings for the source events.</span></span> <span data-ttu-id="948e6-121">Этот файл также известен как файл сообщений о категориях.</span><span class="sxs-lookup"><span data-stu-id="948e6-121">This file is also known as the Category Message File.</span></span>

<span data-ttu-id="948e6-122">Он должен находиться на компьютере, на котором создается журнал событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-122">The file must be present on the computer on which the event log is being created.</span></span> <span data-ttu-id="948e6-123">Этот параметр не создает и не перемещает файлы.</span><span class="sxs-lookup"><span data-stu-id="948e6-123">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-124">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="948e6-124">-ComputerName</span></span>

<span data-ttu-id="948e6-125">Создает журналы событий на указанных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="948e6-125">Creates the new event logs on the specified computers.</span></span> <span data-ttu-id="948e6-126">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="948e6-126">The default is the local computer.</span></span>

<span data-ttu-id="948e6-127">Имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="948e6-127">The NetBIOS name, IP address, or fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="948e6-128">Чтобы указать локальный компьютер, введите имя компьютера, "localhost" или точку (.).</span><span class="sxs-lookup"><span data-stu-id="948e6-128">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="948e6-129">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="948e6-129">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="948e6-130">Параметр **ComputerName** можно использовать, `Get-EventLog` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="948e6-130">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-131">-LogName</span><span class="sxs-lookup"><span data-stu-id="948e6-131">-LogName</span></span>

<span data-ttu-id="948e6-132">Указывает имя журнала событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-132">Specifies the name of the event log.</span></span>

<span data-ttu-id="948e6-133">Если журнал не существует, `New-EventLog` создает журнал и использует это значение для свойств **log** и **LogDisplayName** нового журнала событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-133">If the log does not exist, `New-EventLog` creates the log and uses this value for the **Log** and **LogDisplayName** properties of the new event log.</span></span> <span data-ttu-id="948e6-134">Если журнал существует, `New-EventLog` регистрирует новый источник для журнала событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-134">If the log exists, `New-EventLog` registers a new source for the event log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-135">-Мессажересаурцефиле</span><span class="sxs-lookup"><span data-stu-id="948e6-135">-MessageResourceFile</span></span>

<span data-ttu-id="948e6-136">Указывает путь к файлу, содержащему строки форматирования сообщений для исходных событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-136">Specifies the path to the file that contains message formatting strings for the source events.</span></span>
<span data-ttu-id="948e6-137">Этот файл также известен как файл сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="948e6-137">This file is also known as the Event Message File.</span></span>

<span data-ttu-id="948e6-138">Он должен находиться на компьютере, на котором создается журнал событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-138">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="948e6-139">Этот параметр не создает и не перемещает файлы.</span><span class="sxs-lookup"><span data-stu-id="948e6-139">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-140">-Параметерресаурцефиле</span><span class="sxs-lookup"><span data-stu-id="948e6-140">-ParameterResourceFile</span></span>

<span data-ttu-id="948e6-141">Указывает путь к файлу, который содержит строки, используемые для подстановки параметров в описаниях событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-141">Specifies the path to the file that contains strings used for parameter substitutions in event descriptions.</span></span> <span data-ttu-id="948e6-142">Этот файл также известен как файл сообщений о параметрах.</span><span class="sxs-lookup"><span data-stu-id="948e6-142">This file is also known as the Parameter Message File.</span></span>

<span data-ttu-id="948e6-143">Он должен находиться на компьютере, на котором создается журнал событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-143">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="948e6-144">Этот параметр не создает и не перемещает файлы.</span><span class="sxs-lookup"><span data-stu-id="948e6-144">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-145">-Source</span><span class="sxs-lookup"><span data-stu-id="948e6-145">-Source</span></span>

<span data-ttu-id="948e6-146">Указывает имена источников журнала событий, например программ, записывающих данные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="948e6-146">Specifies the names of the event log sources, such as application programs that write to the event log.</span></span> <span data-ttu-id="948e6-147">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="948e6-147">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="948e6-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="948e6-148">CommonParameters</span></span>

<span data-ttu-id="948e6-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="948e6-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="948e6-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="948e6-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="948e6-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="948e6-151">INPUTS</span></span>

### <span data-ttu-id="948e6-152">Нет</span><span class="sxs-lookup"><span data-stu-id="948e6-152">None</span></span>

<span data-ttu-id="948e6-153">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="948e6-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="948e6-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="948e6-154">OUTPUTS</span></span>

### <span data-ttu-id="948e6-155">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="948e6-155">System.Diagnostics.EventLogEntry</span></span>

## <span data-ttu-id="948e6-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="948e6-156">NOTES</span></span>

<span data-ttu-id="948e6-157">Для использования `New-EventLog` в Windows Vista и более поздних версиях Windows откройте PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="948e6-157">To use `New-EventLog` on Windows Vista and later versions of Windows, open PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="948e6-158">Для создания источника событий в Windows Vista, Windows XP Professional или Windows Server 2003 необходимо быть членом группы "Администраторы" на компьютере.</span><span class="sxs-lookup"><span data-stu-id="948e6-158">To create an event source in Windows Vista, Windows XP Professional, or Windows Server 2003, you must be a member of the Administrators group on the computer.</span></span>

<span data-ttu-id="948e6-159">При создании журнала событий и источника событий система регистрирует источник для нового журнала, но журнал не создается, пока в него не будет внесена первая запись.</span><span class="sxs-lookup"><span data-stu-id="948e6-159">When you create a new event log and a new event source, the system registers the new source for the new log, but the log is not created until the first entry is written to it.</span></span>

<span data-ttu-id="948e6-160">Журналы событий сохраняются операционной системой как файлы.</span><span class="sxs-lookup"><span data-stu-id="948e6-160">The operating system stores event logs as files.</span></span>

<span data-ttu-id="948e6-161">При создании нового журнала событий связанный файл сохраняется в `$env:SystemRoot\System32\Config` каталоге на указанном компьютере.</span><span class="sxs-lookup"><span data-stu-id="948e6-161">When you create a new event log, the associated file is stored in the `$env:SystemRoot\System32\Config` directory on the specified computer.</span></span>

<span data-ttu-id="948e6-162">Имя файла — первые восемь символов свойства **log** с расширением evt.</span><span class="sxs-lookup"><span data-stu-id="948e6-162">The file name is the first eight characters of the **Log** property with an .evt file name extension.</span></span>

## <span data-ttu-id="948e6-163">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="948e6-163">RELATED LINKS</span></span>

[<span data-ttu-id="948e6-164">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-164">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="948e6-165">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-165">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="948e6-166">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="948e6-166">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="948e6-167">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-167">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="948e6-168">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-168">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="948e6-169">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-169">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="948e6-170">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-170">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="948e6-171">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="948e6-171">Write-EventLog</span></span>](Write-EventLog.md)

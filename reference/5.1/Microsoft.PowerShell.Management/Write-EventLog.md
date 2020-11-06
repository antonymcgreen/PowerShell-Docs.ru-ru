---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: cae34c4cf942d9aa4abb9a2d716ef9854f70de2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227813"
---
# <span data-ttu-id="030f9-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-103">Write-EventLog</span></span>

## <span data-ttu-id="030f9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="030f9-104">SYNOPSIS</span></span>
<span data-ttu-id="030f9-105">Записывает событие в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="030f9-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="030f9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="030f9-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="030f9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="030f9-107">DESCRIPTION</span></span>
<span data-ttu-id="030f9-108">Командлет **Write-EventLog** записывает событие в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="030f9-108">The **Write-EventLog** cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="030f9-109">Чтобы событие было записано в журнал событий, он должен существовать на компьютере и иметь зарегистрированный источник.</span><span class="sxs-lookup"><span data-stu-id="030f9-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="030f9-110">Командлеты, содержащие существительное в **EventLog** (командлеты **EventLog** ), работают только в классических журналах событий.</span><span class="sxs-lookup"><span data-stu-id="030f9-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="030f9-111">Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте командлет Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="030f9-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="030f9-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="030f9-112">EXAMPLES</span></span>

### <span data-ttu-id="030f9-113">Пример 1. запись события в журнал событий приложений</span><span class="sxs-lookup"><span data-stu-id="030f9-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="030f9-114">Эта команда записывает событие из источника MyApp в журнал событий Application.</span><span class="sxs-lookup"><span data-stu-id="030f9-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="030f9-115">Пример 2. запись события в журнал событий приложений на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="030f9-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="030f9-116">Эта команда записывает событие из источника MyApp в журнал событий Application на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="030f9-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="030f9-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="030f9-117">PARAMETERS</span></span>

### <span data-ttu-id="030f9-118">-Category</span><span class="sxs-lookup"><span data-stu-id="030f9-118">-Category</span></span>
<span data-ttu-id="030f9-119">Указывает категорию задач для события.</span><span class="sxs-lookup"><span data-stu-id="030f9-119">Specifies a task category for the event.</span></span>
<span data-ttu-id="030f9-120">Введите целочисленное значение, связанное со строками в файле сообщений категорий для журнала событий.</span><span class="sxs-lookup"><span data-stu-id="030f9-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="030f9-121">-ComputerName</span></span>
<span data-ttu-id="030f9-122">Указывает удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="030f9-122">Specifies a remote computer.</span></span>
<span data-ttu-id="030f9-123">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="030f9-123">The default is the local computer.</span></span>

<span data-ttu-id="030f9-124">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="030f9-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="030f9-125">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="030f9-125">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="030f9-126">Параметр *ComputerName* командлета Get-EventLog можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="030f9-126">You can use the *ComputerName* parameter of the Get-EventLog cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="030f9-127">-EntryType</span></span>
<span data-ttu-id="030f9-128">Указывает тип записи события.</span><span class="sxs-lookup"><span data-stu-id="030f9-128">Specifies the entry type of the event.</span></span>
<span data-ttu-id="030f9-129">Допустимые значения для этого параметра: Error, Warning, Information, SuccessAudit и FailureAudit.</span><span class="sxs-lookup"><span data-stu-id="030f9-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span>
<span data-ttu-id="030f9-130">По умолчанию используется значение Information.</span><span class="sxs-lookup"><span data-stu-id="030f9-130">The default value is Information.</span></span>

<span data-ttu-id="030f9-131">Описание значений см. в разделе [перечисление евентложентритипе](https://go.microsoft.com/fwlink/?LinkId=143599) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="030f9-131">For a description of the values, see [EventLogEntryType Enumeration](https://go.microsoft.com/fwlink/?LinkId=143599) in the MSDN library.</span></span>

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-132">-EventId</span><span class="sxs-lookup"><span data-stu-id="030f9-132">-EventId</span></span>
<span data-ttu-id="030f9-133">Указывает идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="030f9-133">Specifies the event identifier.</span></span>
<span data-ttu-id="030f9-134">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="030f9-134">This parameter is required.</span></span>
<span data-ttu-id="030f9-135">Максимальное значение для параметра *EventID* — 65535.</span><span class="sxs-lookup"><span data-stu-id="030f9-135">The maximum value for the *EventId* parameter is 65535.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="030f9-136">-LogName</span></span>
<span data-ttu-id="030f9-137">Указывает имя журнала, в который записывается событие.</span><span class="sxs-lookup"><span data-stu-id="030f9-137">Specifies the name of the log to which the event is written.</span></span>
<span data-ttu-id="030f9-138">Введите имя журнала.</span><span class="sxs-lookup"><span data-stu-id="030f9-138">Enter the log name.</span></span>
<span data-ttu-id="030f9-139">Имя журнала — это значение свойства **log** , а не **LogDisplayName** .</span><span class="sxs-lookup"><span data-stu-id="030f9-139">The log name is the value of the **Log** property, not the **LogDisplayName** .</span></span>
<span data-ttu-id="030f9-140">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="030f9-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="030f9-141">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="030f9-141">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-142">-Message</span><span class="sxs-lookup"><span data-stu-id="030f9-142">-Message</span></span>
<span data-ttu-id="030f9-143">Определяет сообщение о событии.</span><span class="sxs-lookup"><span data-stu-id="030f9-143">Specifies the event message.</span></span>
<span data-ttu-id="030f9-144">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="030f9-144">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="030f9-145">-RawData</span></span>
<span data-ttu-id="030f9-146">Указывает двоичные данные, связанные с событием, в байтах.</span><span class="sxs-lookup"><span data-stu-id="030f9-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-147">-Source</span><span class="sxs-lookup"><span data-stu-id="030f9-147">-Source</span></span>
<span data-ttu-id="030f9-148">Указывает источник события (обычно имя приложения, которое записывает события в журнал).</span><span class="sxs-lookup"><span data-stu-id="030f9-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="030f9-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="030f9-149">CommonParameters</span></span>
<span data-ttu-id="030f9-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="030f9-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="030f9-151">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="030f9-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="030f9-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="030f9-152">INPUTS</span></span>

### <span data-ttu-id="030f9-153">Нет</span><span class="sxs-lookup"><span data-stu-id="030f9-153">None</span></span>
<span data-ttu-id="030f9-154">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="030f9-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="030f9-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="030f9-155">OUTPUTS</span></span>

### <span data-ttu-id="030f9-156">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="030f9-156">System.Diagnostics.EventLogEntry</span></span>
<span data-ttu-id="030f9-157">Этот командлет возвращает объекты, представляющие события в журналах.</span><span class="sxs-lookup"><span data-stu-id="030f9-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="030f9-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="030f9-158">NOTES</span></span>

* <span data-ttu-id="030f9-159">Чтобы использовать **Write-EventLog** , запустите Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="030f9-159">To use **Write-EventLog** , start Windows PowerShell by using the Run as administrator option.</span></span>

*

## <span data-ttu-id="030f9-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="030f9-160">RELATED LINKS</span></span>

[<span data-ttu-id="030f9-161">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-161">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="030f9-162">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-162">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="030f9-163">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-163">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="030f9-164">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-164">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="030f9-165">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-165">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="030f9-166">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-166">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="030f9-167">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="030f9-167">Write-EventLog</span></span>](Write-EventLog.md)
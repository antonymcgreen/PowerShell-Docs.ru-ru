---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227869"
---
# <span data-ttu-id="d5d8f-103">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-103">Show-EventLog</span></span>

## <span data-ttu-id="d5d8f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d5d8f-104">SYNOPSIS</span></span>
<span data-ttu-id="d5d8f-105">Отображает журналы событий локального или удаленного компьютера в просмотре событий.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-105">Displays the event logs of the local or a remote computer in Event Viewer.</span></span>

## <span data-ttu-id="d5d8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5d8f-106">SYNTAX</span></span>

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="d5d8f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5d8f-107">DESCRIPTION</span></span>
<span data-ttu-id="d5d8f-108">Командлет Display **-EventLog** откроется Просмотр событий на локальном компьютере и отобразит в нем все классические журналы событий на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-108">The **Show-EventLog** cmdlet opens Event Viewer on the local computer and displays in it all of the classic event logs on the local computer or a remote computer.</span></span>

<span data-ttu-id="d5d8f-109">Чтобы открыть Просмотр событий в Windows Vista и более поздних версиях операционной системы Windows, текущий пользователь должен быть членом группы администраторов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-109">To open Event Viewer on Windows Vista and later versions of the Windows operating system, the current user must be a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="d5d8f-110">Командлеты, содержащие существительное в **EventLog** (командлеты **EventLog** ), работают только в классических журналах событий.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="d5d8f-111">Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте командлет Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="d5d8f-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5d8f-112">EXAMPLES</span></span>

### <span data-ttu-id="d5d8f-113">Пример 1. Отображение журналов событий для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="d5d8f-113">Example 1: Display event logs for the local computer</span></span>

```
PS C:\> Show-EventLog
```

<span data-ttu-id="d5d8f-114">Эта команда открывает просмотр событий и отображает в нем классические журналы событий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-114">This command opens Event Viewer and displays in it the classic event logs on the local computer.</span></span>

### <span data-ttu-id="d5d8f-115">Пример 2. Отображение журналов событий для удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="d5d8f-115">Example 2: Display event logs for a remote computer</span></span>

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

<span data-ttu-id="d5d8f-116">Эта команда открывает просмотр событий и отображает в нем классические журналы событий на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-116">This command opens Event Viewer and displays in it the classic event logs on the Server01 computer.</span></span>

## <span data-ttu-id="d5d8f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5d8f-117">PARAMETERS</span></span>

### <span data-ttu-id="d5d8f-118">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d5d8f-118">-ComputerName</span></span>
<span data-ttu-id="d5d8f-119">Указывает удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-119">Specifies a remote computer.</span></span>
<span data-ttu-id="d5d8f-120">**Показать-EventLog** отображает журналы событий с указанного компьютера в Просмотр событий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-120">**Show-EventLog** displays the event logs from the specified computer in Event Viewer on the local computer.</span></span>
<span data-ttu-id="d5d8f-121">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-121">The default is the local computer.</span></span>

<span data-ttu-id="d5d8f-122">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="d5d8f-123">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-123">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="d5d8f-124">Параметр *ComputerName* можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-124">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5d8f-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d5d8f-125">CommonParameters</span></span>
<span data-ttu-id="d5d8f-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5d8f-127">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5d8f-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5d8f-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d5d8f-128">INPUTS</span></span>

### <span data-ttu-id="d5d8f-129">Нет</span><span class="sxs-lookup"><span data-stu-id="d5d8f-129">None</span></span>
<span data-ttu-id="d5d8f-130">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d5d8f-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d5d8f-131">OUTPUTS</span></span>

### <span data-ttu-id="d5d8f-132">Нет</span><span class="sxs-lookup"><span data-stu-id="d5d8f-132">None</span></span>
<span data-ttu-id="d5d8f-133">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-133">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d5d8f-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d5d8f-134">NOTES</span></span>

* <span data-ttu-id="d5d8f-135">Командная строка Windows PowerShell возвращается сразу после открытия просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-135">The Windows PowerShell command prompt returns as soon as Event Viewer opens.</span></span> <span data-ttu-id="d5d8f-136">При открытом окне просмотра событий можно работать в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-136">You can work in the current session while Event Viewer is open.</span></span>

  <span data-ttu-id="d5d8f-137">Поскольку этот командлет требует наличия пользовательского интерфейса, он недоступен в варианте установки основных серверных компонентов операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d5d8f-137">Because this cmdlet requires a user interface, it does not work on Server Core installations of Windows Server.</span></span>

*

## <span data-ttu-id="d5d8f-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d5d8f-138">RELATED LINKS</span></span>

[<span data-ttu-id="d5d8f-139">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-139">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="d5d8f-140">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-140">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="d5d8f-141">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-141">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="d5d8f-142">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-142">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="d5d8f-143">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-143">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="d5d8f-144">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="d5d8f-144">Write-EventLog</span></span>](Write-EventLog.md)

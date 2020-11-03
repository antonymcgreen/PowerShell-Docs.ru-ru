---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 5f3579e002030715d7e5926de5f6209cd61b0367
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226677"
---
# <span data-ttu-id="3c1f1-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="3c1f1-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="3c1f1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3c1f1-104">SYNOPSIS</span></span>
<span data-ttu-id="3c1f1-105">Возвращает сведения о процессе для узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="3c1f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c1f1-106">SYNTAX</span></span>

### <span data-ttu-id="3c1f1-107">Процесснамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3c1f1-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3c1f1-108">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="3c1f1-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="3c1f1-109">процессидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="3c1f1-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="3c1f1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c1f1-110">DESCRIPTION</span></span>

<span data-ttu-id="3c1f1-111">`Get-PSHostProcessInfo`Командлет возвращает сведения о процессах узла PowerShell, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="3c1f1-112">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="3c1f1-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c1f1-113">EXAMPLES</span></span>

### <span data-ttu-id="3c1f1-114">1: получение списка узлов PowerShell, запущенных в системе</span><span class="sxs-lookup"><span data-stu-id="3c1f1-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
powershell       5184 DefaultAppDomain Windows PowerShell
```

### <span data-ttu-id="3c1f1-115">2. Получение сведений об узле PowerShell для определенного процесса</span><span class="sxs-lookup"><span data-stu-id="3c1f1-115">2: Get PowerShell host information for a specific process</span></span>

```powershell
Get-PSHostProcessInfo -Id 14676
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
```

## <span data-ttu-id="3c1f1-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c1f1-116">PARAMETERS</span></span>

### <span data-ttu-id="3c1f1-117">-Id</span><span class="sxs-lookup"><span data-stu-id="3c1f1-117">-Id</span></span>

<span data-ttu-id="3c1f1-118">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="3c1f1-119">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c1f1-120">-Name</span><span class="sxs-lookup"><span data-stu-id="3c1f1-120">-Name</span></span>

<span data-ttu-id="3c1f1-121">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-121">Specifies a process by the process name.</span></span> <span data-ttu-id="3c1f1-122">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c1f1-123">-Process</span><span class="sxs-lookup"><span data-stu-id="3c1f1-123">-Process</span></span>

<span data-ttu-id="3c1f1-124">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-124">Specifies a process by the process object.</span></span> <span data-ttu-id="3c1f1-125">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3c1f1-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3c1f1-126">CommonParameters</span></span>

<span data-ttu-id="3c1f1-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c1f1-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c1f1-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c1f1-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3c1f1-129">INPUTS</span></span>

### <span data-ttu-id="3c1f1-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="3c1f1-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="3c1f1-131">Объект **процесса** можно передать `Get-Process` в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3c1f1-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="3c1f1-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3c1f1-132">OUTPUTS</span></span>

### <span data-ttu-id="3c1f1-133">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="3c1f1-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="3c1f1-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3c1f1-134">NOTES</span></span>

## <span data-ttu-id="3c1f1-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3c1f1-135">RELATED LINKS</span></span>

[<span data-ttu-id="3c1f1-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3c1f1-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)

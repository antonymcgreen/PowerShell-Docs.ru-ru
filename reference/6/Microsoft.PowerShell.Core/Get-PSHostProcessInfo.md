---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 24ebb507b2f9544115d6309b0a91d8b19b0745ec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228721"
---
# <span data-ttu-id="0f156-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="0f156-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="0f156-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0f156-104">SYNOPSIS</span></span>
<span data-ttu-id="0f156-105">Возвращает сведения о процессе для узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f156-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="0f156-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f156-106">SYNTAX</span></span>

### <span data-ttu-id="0f156-107">Процесснамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0f156-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0f156-108">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f156-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="0f156-109">процессидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f156-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="0f156-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f156-110">DESCRIPTION</span></span>

<span data-ttu-id="0f156-111">`Get-PSHostProcessInfo`Командлет возвращает сведения о процессах узла PowerShell, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f156-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="0f156-112">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="0f156-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="0f156-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f156-113">EXAMPLES</span></span>

### <span data-ttu-id="0f156-114">1: получение списка узлов PowerShell, запущенных в системе</span><span class="sxs-lookup"><span data-stu-id="0f156-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="0f156-115">2. Получение сведений об узле PowerShell для определенного имени процесса</span><span class="sxs-lookup"><span data-stu-id="0f156-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="0f156-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f156-116">PARAMETERS</span></span>

### <span data-ttu-id="0f156-117">-Id</span><span class="sxs-lookup"><span data-stu-id="0f156-117">-Id</span></span>

<span data-ttu-id="0f156-118">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="0f156-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="0f156-119">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="0f156-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="0f156-120">-Name</span><span class="sxs-lookup"><span data-stu-id="0f156-120">-Name</span></span>

<span data-ttu-id="0f156-121">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="0f156-121">Specifies a process by the process name.</span></span> <span data-ttu-id="0f156-122">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="0f156-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="0f156-123">-Process</span><span class="sxs-lookup"><span data-stu-id="0f156-123">-Process</span></span>

<span data-ttu-id="0f156-124">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="0f156-124">Specifies a process by the process object.</span></span> <span data-ttu-id="0f156-125">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="0f156-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="0f156-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0f156-126">CommonParameters</span></span>

<span data-ttu-id="0f156-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f156-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f156-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f156-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f156-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0f156-129">INPUTS</span></span>

### <span data-ttu-id="0f156-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="0f156-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="0f156-131">Объект **процесса** можно передать `Get-Process` в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0f156-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="0f156-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0f156-132">OUTPUTS</span></span>

### <span data-ttu-id="0f156-133">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="0f156-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="0f156-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0f156-134">NOTES</span></span>

## <span data-ttu-id="0f156-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0f156-135">RELATED LINKS</span></span>

[<span data-ttu-id="0f156-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="0f156-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)

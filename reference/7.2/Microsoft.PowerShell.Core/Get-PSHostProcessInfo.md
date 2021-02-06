---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 6528d25ea706ac63927ef3d23cf661489caae8aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601492"
---
# <span data-ttu-id="1d808-102">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="1d808-102">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="1d808-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1d808-103">SYNOPSIS</span></span>
<span data-ttu-id="1d808-104">Возвращает сведения о процессе для узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d808-104">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="1d808-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d808-105">SYNTAX</span></span>

### <span data-ttu-id="1d808-106">Процесснамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1d808-106">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="1d808-107">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="1d808-107">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="1d808-108">процессидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1d808-108">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="1d808-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d808-109">DESCRIPTION</span></span>

<span data-ttu-id="1d808-110">`Get-PSHostProcessInfo`Командлет возвращает сведения о процессах узла PowerShell, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d808-110">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="1d808-111">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="1d808-111">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="1d808-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d808-112">EXAMPLES</span></span>

### <span data-ttu-id="1d808-113">1: получение списка узлов PowerShell, запущенных в системе</span><span class="sxs-lookup"><span data-stu-id="1d808-113">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="1d808-114">2. Получение сведений об узле PowerShell для определенного имени процесса</span><span class="sxs-lookup"><span data-stu-id="1d808-114">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="1d808-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d808-115">PARAMETERS</span></span>

### <span data-ttu-id="1d808-116">-Id</span><span class="sxs-lookup"><span data-stu-id="1d808-116">-Id</span></span>

<span data-ttu-id="1d808-117">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="1d808-117">Specifies a process by the process ID.</span></span> <span data-ttu-id="1d808-118">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="1d808-118">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="1d808-119">-Name</span><span class="sxs-lookup"><span data-stu-id="1d808-119">-Name</span></span>

<span data-ttu-id="1d808-120">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="1d808-120">Specifies a process by the process name.</span></span> <span data-ttu-id="1d808-121">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="1d808-121">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="1d808-122">-Process</span><span class="sxs-lookup"><span data-stu-id="1d808-122">-Process</span></span>

<span data-ttu-id="1d808-123">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="1d808-123">Specifies a process by the process object.</span></span> <span data-ttu-id="1d808-124">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="1d808-124">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="1d808-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1d808-125">CommonParameters</span></span>

<span data-ttu-id="1d808-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d808-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d808-127">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d808-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d808-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1d808-128">INPUTS</span></span>

### <span data-ttu-id="1d808-129">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="1d808-129">System.Diagnostics.Process</span></span>

<span data-ttu-id="1d808-130">Объект **процесса** можно передать `Get-Process` в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1d808-130">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="1d808-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d808-131">OUTPUTS</span></span>

### <span data-ttu-id="1d808-132">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="1d808-132">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="1d808-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1d808-133">NOTES</span></span>

## <span data-ttu-id="1d808-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d808-134">RELATED LINKS</span></span>

[<span data-ttu-id="1d808-135">Get-Process</span><span class="sxs-lookup"><span data-stu-id="1d808-135">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)


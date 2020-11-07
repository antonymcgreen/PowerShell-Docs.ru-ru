---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: bc16c7129dff2f2982d1756d5642d86481cd573d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344360"
---
# <span data-ttu-id="1c2ad-103">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="1c2ad-103">Out-Printer</span></span>

## <span data-ttu-id="1c2ad-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1c2ad-104">SYNOPSIS</span></span>
<span data-ttu-id="1c2ad-105">Отправляет выходные данные на принтер.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-105">Sends output to a printer.</span></span>

## <span data-ttu-id="1c2ad-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c2ad-106">SYNTAX</span></span>

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="1c2ad-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c2ad-107">DESCRIPTION</span></span>

<span data-ttu-id="1c2ad-108">`Out-Printer`Командлет отправляет выходные данные на принтер по умолчанию или на другой принтер, если он указан.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-108">The `Out-Printer` cmdlet sends output to the default printer or to an alternate printer, if one is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="1c2ad-109">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-109">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="1c2ad-110">Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-110">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="1c2ad-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="1c2ad-111">EXAMPLES</span></span>

### <span data-ttu-id="1c2ad-112">Пример 1. Отправка файла для печати на принтере по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1c2ad-112">Example 1 - Send a file to be printed on the default printer</span></span>

<span data-ttu-id="1c2ad-113">В этом примере показано, как напечатать файл, даже если у `Out-Printer` него нет параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="1c2ad-113">This example shows how to print a file, even though `Out-Printer` does not have a **Path** parameter.</span></span>

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

<span data-ttu-id="1c2ad-114">`Get-Content`Возвращает содержимое `readme.txt` файла в текущем каталоге и передает его в `Out-Printer` , который отправляется на принтер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-114">`Get-Content`gets the contents of the `readme.txt` file in the current directory and pipes it to `Out-Printer`, which sends it to the default printer.</span></span>

### <span data-ttu-id="1c2ad-115">Пример 2. Печать строки на удаленном принтере</span><span class="sxs-lookup"><span data-stu-id="1c2ad-115">Example 2: Print a string to a remote printer</span></span>

<span data-ttu-id="1c2ad-116">В этом примере выполняется печать на `Hello, World` принтере **PRT-6B Color** на Server01.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-116">This example prints `Hello, World` to the **Prt-6B Color** printer on Server01.</span></span>

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

<span data-ttu-id="1c2ad-117">Параметр **Name** выбирает конкретный принтер, а не используемый по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-117">The **Name** parameter selects a specific printer, rather than the default.</span></span>

### <span data-ttu-id="1c2ad-118">Пример 3. Печать раздела справки на принтере по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1c2ad-118">Example 3 - Print a help topic to the default printer</span></span>

<span data-ttu-id="1c2ad-119">В этом примере выводится полная версия раздела справки для `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="1c2ad-119">This example prints the full version of the Help topic for `Get-CimInstance`.</span></span>

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

<span data-ttu-id="1c2ad-120">`Get-Help` Возвращает полную версию раздела справки для `Get-CimInstance` и сохраняет ее в `$H` переменной.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-120">`Get-Help` gets the full version of the Help topic for `Get-CimInstance` and stores it in the `$H` variable.</span></span> <span data-ttu-id="1c2ad-121">Параметр **InputObject** передает значение `$H` в `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="1c2ad-121">The **InputObject** parameter passes the value of `$H` to `Out-Printer`.</span></span>

## <span data-ttu-id="1c2ad-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c2ad-122">PARAMETERS</span></span>

### <span data-ttu-id="1c2ad-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1c2ad-123">-InputObject</span></span>

<span data-ttu-id="1c2ad-124">Указывает объекты, которые нужно передать на принтер.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-124">Specifies the objects to be sent to the printer.</span></span> <span data-ttu-id="1c2ad-125">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-125">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1c2ad-126">-Name</span><span class="sxs-lookup"><span data-stu-id="1c2ad-126">-Name</span></span>

<span data-ttu-id="1c2ad-127">Отправляет выходные данные на указанный принтер.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-127">Sends the output to the specified printer.</span></span> <span data-ttu-id="1c2ad-128">**Имя параметра является** необязательным.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-128">The parameter name **Name** is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c2ad-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1c2ad-129">CommonParameters</span></span>

<span data-ttu-id="1c2ad-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c2ad-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1c2ad-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c2ad-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1c2ad-132">INPUTS</span></span>

### <span data-ttu-id="1c2ad-133">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1c2ad-133">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1c2ad-134">Любой объект можно передать по конвейеру в `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="1c2ad-134">You can pipe any object to `Out-Printer`.</span></span>

## <span data-ttu-id="1c2ad-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1c2ad-135">OUTPUTS</span></span>

### <span data-ttu-id="1c2ad-136">Нет</span><span class="sxs-lookup"><span data-stu-id="1c2ad-136">None</span></span>

<span data-ttu-id="1c2ad-137">`Out-Printer` не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-137">`Out-Printer` does not return any objects.</span></span>

## <span data-ttu-id="1c2ad-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1c2ad-138">NOTES</span></span>

<span data-ttu-id="1c2ad-139">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-139">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="1c2ad-140">Командлеты, содержащие `Out` команду, не отформатируют объекты.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-140">The cmdlets that contain the `Out` verb do not format objects.</span></span> <span data-ttu-id="1c2ad-141">Они просто отображают их и отправляют в указанное место назначения.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-141">They just render them and send them to the specified display destination.</span></span> <span data-ttu-id="1c2ad-142">При отправке неформатированного объекта в `Out` командлет командлет отправляет его в командлет форматирования перед отображением.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-142">If you send an unformatted object to an `Out` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="1c2ad-143">`Out-Printer` отправляет данные на принтер, но не выдает выходные объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-143">`Out-Printer` sends data to the printer, but does not emit any output objects to the pipeline.</span></span> <span data-ttu-id="1c2ad-144">При передаче выходных данных `Out-Printer` в в `Get-Member` `Get-Member` сообщает о том, что объекты не указаны.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-144">If you pipe the output of `Out-Printer` to `Get-Member`, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="1c2ad-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1c2ad-145">RELATED LINKS</span></span>

[<span data-ttu-id="1c2ad-146">Out-File</span><span class="sxs-lookup"><span data-stu-id="1c2ad-146">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="1c2ad-147">Out-String</span><span class="sxs-lookup"><span data-stu-id="1c2ad-147">Out-String</span></span>](Out-String.md)

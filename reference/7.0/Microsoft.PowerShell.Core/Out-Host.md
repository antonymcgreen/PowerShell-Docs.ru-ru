---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: e3b009ae92abde371a4a6380d0ac6d491093333f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225990"
---
# <span data-ttu-id="3a257-103">Out-Host</span><span class="sxs-lookup"><span data-stu-id="3a257-103">Out-Host</span></span>

## <span data-ttu-id="3a257-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3a257-104">SYNOPSIS</span></span>
<span data-ttu-id="3a257-105">Отправляет вывод в командную строку.</span><span class="sxs-lookup"><span data-stu-id="3a257-105">Sends output to the command line.</span></span>

## <span data-ttu-id="3a257-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a257-106">SYNTAX</span></span>

### <span data-ttu-id="3a257-107">Все</span><span class="sxs-lookup"><span data-stu-id="3a257-107">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="3a257-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a257-108">DESCRIPTION</span></span>

<span data-ttu-id="3a257-109">`Out-Host`Командлет отправляет выходные данные на узел PowerShell для вывода.</span><span class="sxs-lookup"><span data-stu-id="3a257-109">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="3a257-110">Основное приложение отображает вывод в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3a257-110">The host displays the output at the command line.</span></span> <span data-ttu-id="3a257-111">Поскольку параметр `Out-Host` является значением по умолчанию, нет необходимости указывать его, если не требуется использовать его параметры.</span><span class="sxs-lookup"><span data-stu-id="3a257-111">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="3a257-112">`Out-Host` автоматически добавляется к каждой выполняемой команде.</span><span class="sxs-lookup"><span data-stu-id="3a257-112">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="3a257-113">Он передает выходные данные конвейера на узел, на котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="3a257-113">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="3a257-114">`Out-Host` игнорирует escape-последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="3a257-114">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="3a257-115">Управляющие последовательности обрабатываются узлом.</span><span class="sxs-lookup"><span data-stu-id="3a257-115">The escape sequences are handled by the host.</span></span> <span data-ttu-id="3a257-116">`Out-Host` передает escape-последовательности ANSI на узел, не пытаясь интерпретировать или изменять их.</span><span class="sxs-lookup"><span data-stu-id="3a257-116">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="3a257-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="3a257-117">EXAMPLES</span></span>

### <span data-ttu-id="3a257-118">Пример 1. Отображение выходных данных на одной странице за раз</span><span class="sxs-lookup"><span data-stu-id="3a257-118">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="3a257-119">Этот пример показывает, что система обрабатывается по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="3a257-119">This example displays the system processes one page at a time.</span></span>

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="3a257-120">`Get-Process` Возвращает системные процессы и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3a257-120">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="3a257-121">`Out-Host` использует параметр **разбиения по страницам** для одновременного вывода одной страницы данных.</span><span class="sxs-lookup"><span data-stu-id="3a257-121">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="3a257-122">Пример 2. Использование переменной в качестве входных данных</span><span class="sxs-lookup"><span data-stu-id="3a257-122">Example 2: Use a variable as input</span></span>

<span data-ttu-id="3a257-123">В этом примере используются объекты, хранящиеся в переменной, в качестве входных данных для `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="3a257-123">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="3a257-124">`Get-History` Возвращает журнал сеанса PowerShell и сохраняет объекты в `$io` переменной.</span><span class="sxs-lookup"><span data-stu-id="3a257-124">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="3a257-125">`Out-Host` использует параметр **InputObject** для указания `$io` переменной и отображает журнал.</span><span class="sxs-lookup"><span data-stu-id="3a257-125">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="3a257-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a257-126">PARAMETERS</span></span>

### <span data-ttu-id="3a257-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3a257-127">-InputObject</span></span>

<span data-ttu-id="3a257-128">Задает объекты, которые будут выведены на консоль.</span><span class="sxs-lookup"><span data-stu-id="3a257-128">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="3a257-129">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="3a257-129">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3a257-130">— Разбиение на страницы</span><span class="sxs-lookup"><span data-stu-id="3a257-130">-Paging</span></span>

<span data-ttu-id="3a257-131">Указывает, что `Out-Host` отображает одну страницу выходных данных за раз и ожидает ввода данных пользователем перед отображением оставшихся страниц.</span><span class="sxs-lookup"><span data-stu-id="3a257-131">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="3a257-132">По умолчанию все выходные данные отображаются на одной странице.</span><span class="sxs-lookup"><span data-stu-id="3a257-132">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="3a257-133">Размер страницы определяется характеристиками основного приложения.</span><span class="sxs-lookup"><span data-stu-id="3a257-133">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="3a257-134">Нажмите клавишу <kbd>пробел</kbd> , чтобы отобразить следующую страницу выходных данных, или клавишу <kbd>Ввод</kbd> , чтобы просмотреть следующую строку выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3a257-134">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="3a257-135">Нажмите клавишу <kbd>Q</kbd> , чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="3a257-135">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="3a257-136">**Подкачка страниц** аналогична команде **More** .</span><span class="sxs-lookup"><span data-stu-id="3a257-136">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="3a257-137">Параметр **подкачки** не поддерживается узлом интегрированной среды сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a257-137">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="3a257-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3a257-138">CommonParameters</span></span>

<span data-ttu-id="3a257-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a257-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a257-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a257-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a257-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3a257-141">INPUTS</span></span>

### <span data-ttu-id="3a257-142">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="3a257-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3a257-143">Объекты можно отправить по конвейеру в `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="3a257-143">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="3a257-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3a257-144">OUTPUTS</span></span>

### <span data-ttu-id="3a257-145">Нет</span><span class="sxs-lookup"><span data-stu-id="3a257-145">None</span></span>

<span data-ttu-id="3a257-146">`Out-Host` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3a257-146">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="3a257-147">Он отправляет объекты на узел для вывода.</span><span class="sxs-lookup"><span data-stu-id="3a257-147">It sends objects to the host for display.</span></span>

## <span data-ttu-id="3a257-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3a257-148">NOTES</span></span>

<span data-ttu-id="3a257-149">Параметр **подкачки** не поддерживается всеми узлами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a257-149">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="3a257-150">Например, если вы используете параметр **разбиения по страницам** в интегрированной среде сценариев PowerShell, отображается следующая ошибка: `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="3a257-150">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="3a257-151">Командлеты, которые содержат команду **out** , `Out-` не отформатируют объекты.</span><span class="sxs-lookup"><span data-stu-id="3a257-151">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="3a257-152">Они визуализируют объекты и отправляют их в указанное назначение отображения.</span><span class="sxs-lookup"><span data-stu-id="3a257-152">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="3a257-153">При отправке неформатированного объекта в `Out-` командлет командлет отправляет его в командлет форматирования перед отображением.</span><span class="sxs-lookup"><span data-stu-id="3a257-153">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="3a257-154">`Out-`Командлеты не имеют параметров для имен или путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="3a257-154">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="3a257-155">Чтобы отправить данные в `Out-` командлет, используйте конвейер для отправки выходных данных команды PowerShell в командлет.</span><span class="sxs-lookup"><span data-stu-id="3a257-155">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="3a257-156">Или можно сохранить данные в переменной и использовать параметр **InputObject** для передачи данных в командлет.</span><span class="sxs-lookup"><span data-stu-id="3a257-156">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="3a257-157">`Out-Host` отправляет данные, но не создает никаких выходных объектов.</span><span class="sxs-lookup"><span data-stu-id="3a257-157">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="3a257-158">Если выходные данные конвейера `Out-Host` `Get-Member` передаются в командлет, то `Get-Member` сообщает о том, что объекты не указаны.</span><span class="sxs-lookup"><span data-stu-id="3a257-158">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="3a257-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3a257-159">RELATED LINKS</span></span>

[<span data-ttu-id="3a257-160">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="3a257-160">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="3a257-161">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="3a257-161">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="3a257-162">Out-File</span><span class="sxs-lookup"><span data-stu-id="3a257-162">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="3a257-163">Out-Null</span><span class="sxs-lookup"><span data-stu-id="3a257-163">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="3a257-164">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="3a257-164">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="3a257-165">Out-String</span><span class="sxs-lookup"><span data-stu-id="3a257-165">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="3a257-166">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3a257-166">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)

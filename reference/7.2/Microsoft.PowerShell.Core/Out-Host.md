---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: 4fefb133416b3db6c19c71a916d73fe00f86f3a4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604475"
---
# <span data-ttu-id="85a69-102">Out-Host</span><span class="sxs-lookup"><span data-stu-id="85a69-102">Out-Host</span></span>

## <span data-ttu-id="85a69-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="85a69-103">SYNOPSIS</span></span>
<span data-ttu-id="85a69-104">Отправляет вывод в командную строку.</span><span class="sxs-lookup"><span data-stu-id="85a69-104">Sends output to the command line.</span></span>

## <span data-ttu-id="85a69-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85a69-105">SYNTAX</span></span>

### <span data-ttu-id="85a69-106">Все</span><span class="sxs-lookup"><span data-stu-id="85a69-106">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="85a69-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85a69-107">DESCRIPTION</span></span>

<span data-ttu-id="85a69-108">`Out-Host`Командлет отправляет выходные данные на узел PowerShell для вывода.</span><span class="sxs-lookup"><span data-stu-id="85a69-108">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="85a69-109">Основное приложение отображает вывод в командной строке.</span><span class="sxs-lookup"><span data-stu-id="85a69-109">The host displays the output at the command line.</span></span> <span data-ttu-id="85a69-110">Поскольку параметр `Out-Host` является значением по умолчанию, нет необходимости указывать его, если не требуется использовать его параметры.</span><span class="sxs-lookup"><span data-stu-id="85a69-110">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="85a69-111">`Out-Host` автоматически добавляется к каждой выполняемой команде.</span><span class="sxs-lookup"><span data-stu-id="85a69-111">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="85a69-112">Он передает выходные данные конвейера на узел, на котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="85a69-112">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="85a69-113">`Out-Host` игнорирует escape-последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="85a69-113">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="85a69-114">Управляющие последовательности обрабатываются узлом.</span><span class="sxs-lookup"><span data-stu-id="85a69-114">The escape sequences are handled by the host.</span></span> <span data-ttu-id="85a69-115">`Out-Host` передает escape-последовательности ANSI на узел, не пытаясь интерпретировать или изменять их.</span><span class="sxs-lookup"><span data-stu-id="85a69-115">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="85a69-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="85a69-116">EXAMPLES</span></span>

### <span data-ttu-id="85a69-117">Пример 1. Отображение выходных данных на одной странице за раз</span><span class="sxs-lookup"><span data-stu-id="85a69-117">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="85a69-118">Этот пример показывает, что система обрабатывается по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="85a69-118">This example displays the system processes one page at a time.</span></span>

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

<span data-ttu-id="85a69-119">`Get-Process` Возвращает системные процессы и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="85a69-119">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="85a69-120">`Out-Host` использует параметр **разбиения по страницам** для одновременного вывода одной страницы данных.</span><span class="sxs-lookup"><span data-stu-id="85a69-120">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="85a69-121">Пример 2. Использование переменной в качестве входных данных</span><span class="sxs-lookup"><span data-stu-id="85a69-121">Example 2: Use a variable as input</span></span>

<span data-ttu-id="85a69-122">В этом примере используются объекты, хранящиеся в переменной, в качестве входных данных для `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="85a69-122">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="85a69-123">`Get-History` Возвращает журнал сеанса PowerShell и сохраняет объекты в `$io` переменной.</span><span class="sxs-lookup"><span data-stu-id="85a69-123">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="85a69-124">`Out-Host` использует параметр **InputObject** для указания `$io` переменной и отображает журнал.</span><span class="sxs-lookup"><span data-stu-id="85a69-124">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="85a69-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85a69-125">PARAMETERS</span></span>

### <span data-ttu-id="85a69-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="85a69-126">-InputObject</span></span>

<span data-ttu-id="85a69-127">Задает объекты, которые будут выведены на консоль.</span><span class="sxs-lookup"><span data-stu-id="85a69-127">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="85a69-128">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="85a69-128">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="85a69-129">— Разбиение на страницы</span><span class="sxs-lookup"><span data-stu-id="85a69-129">-Paging</span></span>

<span data-ttu-id="85a69-130">Указывает, что `Out-Host` отображает одну страницу выходных данных за раз и ожидает ввода данных пользователем перед отображением оставшихся страниц.</span><span class="sxs-lookup"><span data-stu-id="85a69-130">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="85a69-131">По умолчанию все выходные данные отображаются на одной странице.</span><span class="sxs-lookup"><span data-stu-id="85a69-131">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="85a69-132">Размер страницы определяется характеристиками основного приложения.</span><span class="sxs-lookup"><span data-stu-id="85a69-132">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="85a69-133">Нажмите клавишу <kbd>пробел</kbd> , чтобы отобразить следующую страницу выходных данных, или клавишу <kbd>Ввод</kbd> , чтобы просмотреть следующую строку выходных данных.</span><span class="sxs-lookup"><span data-stu-id="85a69-133">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="85a69-134">Нажмите клавишу <kbd>Q</kbd> , чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="85a69-134">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="85a69-135">**Подкачка страниц** аналогична команде **More** .</span><span class="sxs-lookup"><span data-stu-id="85a69-135">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="85a69-136">Параметр **подкачки** не поддерживается узлом интегрированной среды сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85a69-136">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="85a69-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="85a69-137">CommonParameters</span></span>

<span data-ttu-id="85a69-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85a69-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85a69-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85a69-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85a69-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="85a69-140">INPUTS</span></span>

### <span data-ttu-id="85a69-141">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="85a69-141">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="85a69-142">Объекты можно отправить по конвейеру в `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="85a69-142">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="85a69-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="85a69-143">OUTPUTS</span></span>

### <span data-ttu-id="85a69-144">None</span><span class="sxs-lookup"><span data-stu-id="85a69-144">None</span></span>

<span data-ttu-id="85a69-145">`Out-Host` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="85a69-145">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="85a69-146">Он отправляет объекты на узел для вывода.</span><span class="sxs-lookup"><span data-stu-id="85a69-146">It sends objects to the host for display.</span></span>

## <span data-ttu-id="85a69-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="85a69-147">NOTES</span></span>

<span data-ttu-id="85a69-148">Параметр **подкачки** не поддерживается всеми узлами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85a69-148">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="85a69-149">Например, если вы используете параметр **разбиения по страницам** в интегрированной среде сценариев PowerShell, отображается следующая ошибка: `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="85a69-149">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="85a69-150">Командлеты, которые содержат команду **out** , `Out-` не отформатируют объекты.</span><span class="sxs-lookup"><span data-stu-id="85a69-150">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="85a69-151">Они визуализируют объекты и отправляют их в указанное назначение отображения.</span><span class="sxs-lookup"><span data-stu-id="85a69-151">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="85a69-152">При отправке неформатированного объекта в `Out-` командлет командлет отправляет его в командлет форматирования перед отображением.</span><span class="sxs-lookup"><span data-stu-id="85a69-152">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="85a69-153">`Out-`Командлеты не имеют параметров для имен или путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="85a69-153">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="85a69-154">Чтобы отправить данные в `Out-` командлет, используйте конвейер для отправки выходных данных команды PowerShell в командлет.</span><span class="sxs-lookup"><span data-stu-id="85a69-154">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="85a69-155">Или можно сохранить данные в переменной и использовать параметр **InputObject** для передачи данных в командлет.</span><span class="sxs-lookup"><span data-stu-id="85a69-155">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="85a69-156">`Out-Host` отправляет данные, но не создает никаких выходных объектов.</span><span class="sxs-lookup"><span data-stu-id="85a69-156">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="85a69-157">Если выходные данные конвейера `Out-Host` `Get-Member` передаются в командлет, то `Get-Member` сообщает о том, что объекты не указаны.</span><span class="sxs-lookup"><span data-stu-id="85a69-157">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="85a69-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="85a69-158">RELATED LINKS</span></span>

[<span data-ttu-id="85a69-159">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="85a69-159">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="85a69-160">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="85a69-160">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="85a69-161">Out-File</span><span class="sxs-lookup"><span data-stu-id="85a69-161">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="85a69-162">Out-Null</span><span class="sxs-lookup"><span data-stu-id="85a69-162">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="85a69-163">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="85a69-163">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="85a69-164">Out-String</span><span class="sxs-lookup"><span data-stu-id="85a69-164">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="85a69-165">Write-Host</span><span class="sxs-lookup"><span data-stu-id="85a69-165">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)


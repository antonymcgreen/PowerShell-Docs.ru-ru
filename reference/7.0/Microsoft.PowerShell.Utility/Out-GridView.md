---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 37b5349c8ed39ff70453b59fe6758c57880f0087
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346944"
---
# <span data-ttu-id="1d7a1-103">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="1d7a1-103">Out-GridView</span></span>

## <span data-ttu-id="1d7a1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1d7a1-104">SYNOPSIS</span></span>
<span data-ttu-id="1d7a1-105">Отправляет выходные данные в интерактивную таблицу в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-105">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="1d7a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d7a1-106">SYNTAX</span></span>

### <span data-ttu-id="1d7a1-107">PassThru (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1d7a1-107">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="1d7a1-108">Ожидание</span><span class="sxs-lookup"><span data-stu-id="1d7a1-108">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="1d7a1-109">OutputMode</span><span class="sxs-lookup"><span data-stu-id="1d7a1-109">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="1d7a1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d7a1-110">DESCRIPTION</span></span>

<span data-ttu-id="1d7a1-111">`Out-GridView`Командлет отправляет выходные данные команды в окно представления сетки, в котором выходные данные отображаются в интерактивной таблице.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-111">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="1d7a1-112">Поскольку для этого командлета требуется пользовательский интерфейс, он не работает на Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-112">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="1d7a1-113">Можно использовать следующие функции таблицы для анализа данных:</span><span class="sxs-lookup"><span data-stu-id="1d7a1-113">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="1d7a1-114">Скрытие, отображение и переупорядочение столбцов</span><span class="sxs-lookup"><span data-stu-id="1d7a1-114">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="1d7a1-115">Сортировать строки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-115">Sort rows</span></span>
- <span data-ttu-id="1d7a1-116">Экспресс-фильтр</span><span class="sxs-lookup"><span data-stu-id="1d7a1-116">Quick Filter</span></span>
- <span data-ttu-id="1d7a1-117">Добавить фильтр критериев</span><span class="sxs-lookup"><span data-stu-id="1d7a1-117">Add Criteria Filter</span></span>
- <span data-ttu-id="1d7a1-118">Копирование и вставка</span><span class="sxs-lookup"><span data-stu-id="1d7a1-118">Copy and paste</span></span>

<span data-ttu-id="1d7a1-119">Полные инструкции см. в разделе « [Примечания](#notes) » этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-119">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1d7a1-120">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-120">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="1d7a1-121">Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-121">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="1d7a1-122">Сведения о кросс-платформенной версии этого командлета см. в модуле [графикалтулс](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) в коллекция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-122">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="1d7a1-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d7a1-123">EXAMPLES</span></span>

### <span data-ttu-id="1d7a1-124">Пример 1. вывод процессов в виде сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-124">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="1d7a1-125">Этот пример возвращает процессы, запущенные на локальном компьютере, и отправляет их в окно представления сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-125">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="1d7a1-126">Пример 2. Использование переменной для вывода процессов в представлении сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-126">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="1d7a1-127">Этот пример также получает процессы, запущенные на локальном компьютере, и отправляет их в окно представления сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-127">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="1d7a1-128">Выходные данные `Get-Process` командлета сохраняются в `$P` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-128">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="1d7a1-129">Затем `$P` передается в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-129">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="1d7a1-130">Пример 3. Отображение выбранных свойств в представлении сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-130">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="1d7a1-131">В этом примере отображаются выбранные свойства запущенных процессов в представлении сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-131">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="1d7a1-132">Выходные данные `Get-Process` передаются в, `Select-Object` чтобы выбрать свойства **Name** , **Working** и **пеакворкингсет** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-132">The output of `Get-Process` is piped to `Select-Object` to select the **Name** , **WorkingSet** , and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="1d7a1-133">Другой оператор конвейера отправляет отфильтрованные объекты в `Sort-Object` командлет, чтобы сортировать их в порядке убывания по значению свойства " **рабочее** множество".</span><span class="sxs-lookup"><span data-stu-id="1d7a1-133">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="1d7a1-134">Затем отсортированные результаты передаются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-134">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="1d7a1-135">Теперь можно использовать функции представления сетки для поиска, сортировки и фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-135">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="1d7a1-136">Пример 4. сохранение выходных данных в переменную, а затем вывод представления в виде сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-136">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="1d7a1-137">В этом примере выходные данные командлета сохраняются в переменной, а затем отправляются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-137">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="1d7a1-138">`Get-ChildItem` Получает все файлы в каталоге установки PowerShell и его подкаталогах, используя `$PSHOME` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-138">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="1d7a1-139">Круглые скобки в команде задают порядок операций.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-139">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="1d7a1-140">В результате выходные данные `Get-ChildItem` команды сохраняются в `$A` переменной перед их отправкой `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-140">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="1d7a1-141">Пример 5. выходные процессы для указанного компьютера в виде сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-141">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="1d7a1-142">В этом примере отображаются процессы, запущенные на компьютере Server01, в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-142">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="1d7a1-143">Ексамле использует `ogv` , который является псевдонимом для `Out-GridView` командлета.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-143">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="1d7a1-144">Параметр **Title** указывает заголовок окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-144">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="1d7a1-145">Пример 6. вывод данных с удаленных компьютеров в представление сетки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-145">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="1d7a1-146">В этом примере показано, как отправить данные, собранные с удаленных компьютеров, в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-146">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="1d7a1-147">`Invoke-Command` работает `Get-Culture` на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-147">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="1d7a1-148">Результирующие данные передаются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-148">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="1d7a1-149">Обратите внимание, что блок сценария, выполняемый на удаленном компьютере, не содержит `Out-GridView` команду.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-149">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="1d7a1-150">В противном случае команда завершится сбоем при попытке открыть окно представления сетки на каждом из удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-150">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="1d7a1-151">Пример 7. Передача нескольких элементов с помощью `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="1d7a1-151">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="1d7a1-152">Этот пример позволяет выбрать несколько процессов из `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-152">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="1d7a1-153">Выбранные процессы передаются в `Export-Csv` команду и записываются в `ProcessLog.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-153">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="1d7a1-154">Параметр **PassThru** параметра `Out-GridView` позволяет отправить несколько элементов по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-154">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="1d7a1-155">Параметр **PassThru** эквивалентен использованию значения **Multiple** параметра **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-155">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="1d7a1-156">Пример 8. Создание ярлыка Windows для `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="1d7a1-156">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="1d7a1-157">В этом примере показано, как использовать параметр **Wait** параметра, `Out-GridView` чтобы создать ярлык Windows для `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-157">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="1d7a1-158">Эту командную строку можно использовать в сочетаниях клавиш Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-158">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="1d7a1-159">Без параметра **Wait** работа PowerShell будет завершена сразу после `Out-GridView` открытия окна, что приведет к немедленному закрытию `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-159">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="1d7a1-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d7a1-160">PARAMETERS</span></span>

### <span data-ttu-id="1d7a1-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1d7a1-161">-InputObject</span></span>

<span data-ttu-id="1d7a1-162">Указывает объект, который командлет принимает в качестве входных данных для `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-162">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="1d7a1-163">При использовании параметра **InputObject** для отправки коллекции объектов в `Out-GridView` , `Out-GridView` обрабатывает коллекцию как один объект коллекции и отображает одну строку, представляющую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-163">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="1d7a1-164">Чтобы отобразить каждый объект в коллекции, используйте оператор конвейера ( `|` ) для отправки объектов в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-164">To display the each object in the collection, use a pipeline operator (`|`) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="1d7a1-165">-Аутпутмоде</span><span class="sxs-lookup"><span data-stu-id="1d7a1-165">-OutputMode</span></span>

<span data-ttu-id="1d7a1-166">Указывает элементы, которые интерактивное окно отправляет в конвейер в качестве входных данных для других команд.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-166">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="1d7a1-167">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-167">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="1d7a1-168">Чтобы отправить элементы из интерактивного окна в конвейер, выберите нужные элементы, а затем нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="1d7a1-168">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="1d7a1-169">Значения этого параметра определяют количество элементов, которое можно отправить по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-169">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="1d7a1-170">Нет.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-170">None.</span></span>  <span data-ttu-id="1d7a1-171">нет элементов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-171">No items.</span></span> <span data-ttu-id="1d7a1-172">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-172">This is the default value.</span></span>
- <span data-ttu-id="1d7a1-173">Одинарная.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-173">Single.</span></span> <span data-ttu-id="1d7a1-174">нуль элементов или один элемент.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-174">Zero items or one item.</span></span> <span data-ttu-id="1d7a1-175">Это значение используется, если следующая команда может принимать только один входной объект.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-175">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="1d7a1-176">Несколько.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-176">Multiple.</span></span> <span data-ttu-id="1d7a1-177">нуль, один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-177">Zero, one, or many items.</span></span> <span data-ttu-id="1d7a1-178">Это значение используется, если следующая команда может принимать несколько входных объектов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-178">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="1d7a1-179">Это значение эквивалентно параметру **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-179">This value is equivalent to the **Passthru** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d7a1-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1d7a1-180">-PassThru</span></span>

<span data-ttu-id="1d7a1-181">Указывает, что командлет отправляет элементы из интерактивного окна в конвейер в качестве входных данных для других команд.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-181">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="1d7a1-182">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-182">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="1d7a1-183">Этот параметр эквивалентен значению **Multiple** параметра **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-183">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="1d7a1-184">Чтобы отправить элементы из интерактивного окна в конвейер, выберите нужные элементы, а затем нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="1d7a1-184">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="1d7a1-185">Поддерживается выбор элементов с помощью клавиш SHIFT и CTRL.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-185">Shift-click and Ctrl-click are supported.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d7a1-186">-Title</span><span class="sxs-lookup"><span data-stu-id="1d7a1-186">-Title</span></span>

<span data-ttu-id="1d7a1-187">Задает текст, отображаемый в заголовке `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-187">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="1d7a1-188">По умолчанию в строке заголовка отображается команда, вызывающая `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-188">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d7a1-189">-Wait</span><span class="sxs-lookup"><span data-stu-id="1d7a1-189">-Wait</span></span>

<span data-ttu-id="1d7a1-190">Указывает, что командлет подавляет командную строку и предотвращает закрытие Windows PowerShell до `Out-GridView` закрытия окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-190">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="1d7a1-191">По умолчанию командная строка возвращается при `Out-GridView` открытии окна.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-191">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="1d7a1-192">Эта функция позволяет использовать `Out-GridView` командлеты в сочетаниях клавиш Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-192">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="1d7a1-193">Когда `Out-GridView` используется в ярлыке без параметра **Wait** , `Out-GridView` окно появляется только перед закрытием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-193">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d7a1-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1d7a1-194">CommonParameters</span></span>

<span data-ttu-id="1d7a1-195">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d7a1-196">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d7a1-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d7a1-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1d7a1-197">INPUTS</span></span>

### <span data-ttu-id="1d7a1-198">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1d7a1-198">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1d7a1-199">В этот командлет можно отправить любой объект.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-199">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="1d7a1-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d7a1-200">OUTPUTS</span></span>

### <span data-ttu-id="1d7a1-201">Нет</span><span class="sxs-lookup"><span data-stu-id="1d7a1-201">None</span></span>

<span data-ttu-id="1d7a1-202">Как правило, не `Out-GridView` возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-202">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="1d7a1-203">При использовании параметра **PassThru** объекты, представляющие выбранные строки, возвращаются в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-203">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="1d7a1-204">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1d7a1-204">NOTES</span></span>

<span data-ttu-id="1d7a1-205">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-205">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="1d7a1-206">Удаленную команду нельзя использовать для открытия окна представления сетки на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-206">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="1d7a1-207">Выходные данные команды, которые вы отправляете в, `Out-GridView` не могут быть отформатированы с помощью `Format` командлетов, например `Format-Table` `Format-Wide` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-207">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="1d7a1-208">Чтобы выбрать свойства, используйте `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-208">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="1d7a1-209">Десериализованные выходные данные из удаленных команд могут неправильно форматироваться в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-209">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="1d7a1-210">**Сочетания клавиш для**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="1d7a1-210">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="1d7a1-211">Клавиша</span><span class="sxs-lookup"><span data-stu-id="1d7a1-211">Use this key:</span></span>              |                                   <span data-ttu-id="1d7a1-212">Действие</span><span class="sxs-lookup"><span data-stu-id="1d7a1-212">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1d7a1-213"><kbd>Вкладка</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-213"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="1d7a1-214">Перемещает курсор из поля **Фильтр** в меню **Добавить критерии** в таблицу и обратно.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-214">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="1d7a1-215"><kbd>Стрелка вверх</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-215"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="1d7a1-216">Переместить вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-216">Move up one row.</span></span> <span data-ttu-id="1d7a1-217">Переходит к заголовкам столбцов из первой строки данных.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-217">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="1d7a1-218"><kbd>Стрелка вниз</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-218"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="1d7a1-219">Переместить на одну строку вниз.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-219">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="1d7a1-220"><kbd>Влево</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-220"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="1d7a1-221">В строке заголовка столбца переместитесь влево на один столбец.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-221">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="1d7a1-222"><kbd>RightArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-222"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="1d7a1-223">В строке заголовков столбцов переместитесь вправо на один столбец.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-223">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="1d7a1-224"><kbd>контекстменукэй</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-224"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="1d7a1-225">В строке заголовков столбцов отображается параметр Выбор столбцов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-225">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="1d7a1-226"><kbd>Ввод</kbd> или <kbd>пробел</kbd></span><span class="sxs-lookup"><span data-stu-id="1d7a1-226"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="1d7a1-227">В строке заголовков столбцов сортировать данные столбца (переключать A – Z, Z-A).</span><span class="sxs-lookup"><span data-stu-id="1d7a1-227">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="1d7a1-228">**Использование функций окна представления сетки**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-228">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="1d7a1-229">**Скрытие или отображение столбца**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-229">**To hide or show a column:**</span></span>

1. <span data-ttu-id="1d7a1-230">Щелкните правой кнопкой мыши заголовок любого столбца и выберите команду **выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-230">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="1d7a1-231">В диалоговом окне **Выбор столбцов** используйте клавиши со стрелками для перемещения столбцов между выбранными столбцами в поля Доступные столбцы.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-231">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="1d7a1-232">В окне представления сетки отображаются только столбцы в поле **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-232">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="1d7a1-233">**Изменение порядка столбцов**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-233">**To reorder columns:**</span></span>

<span data-ttu-id="1d7a1-234">Столбцы можно перетаскивать в нужное место.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-234">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="1d7a1-235">Или выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-235">Or use the following steps:</span></span>

1. <span data-ttu-id="1d7a1-236">Щелкните правой кнопкой мыши заголовок любого столбца и выберите команду **выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-236">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="1d7a1-237">В диалоговом окне **Выбор столбцов** используйте кнопки вверх **и** **вниз** , чтобы изменить порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-237">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="1d7a1-238">Столбцы в верхней части списка отображаются слева от столбцов в нижней части списка в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-238">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="1d7a1-239">**Сортировка данных таблицы**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-239">**How to Sort Table Data**</span></span>

- <span data-ttu-id="1d7a1-240">Чтобы отсортировать данные, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-240">To sort the data, click a column header.</span></span>
- <span data-ttu-id="1d7a1-241">Чтобы изменить порядок сортировки, еще раз щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-241">To change the sort order, click the column header again.</span></span> <span data-ttu-id="1d7a1-242">Каждый раз при щелчке одного и того же заголовка порядок сортировки (по убыванию или по возрастанию) переключается.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-242">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="1d7a1-243">Текущий порядок указывается значком треугольника в заголовке столбца.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-243">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="1d7a1-244">**Выбор данных таблицы**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-244">**How to Select Table Data**</span></span>

- <span data-ttu-id="1d7a1-245">Чтобы выбрать строку, выберите строку или используйте стрелку вверх или вниз для перехода к строке.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-245">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="1d7a1-246">Чтобы выбрать все строки (за исключением строки заголовка), нажмите клавиши <kbd>CTRL</kbd> + <kbd>A</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-246">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="1d7a1-247">Чтобы выбрать последовательные строки, нажмите и удерживайте клавишу <kbd>SHIFT</kbd> при щелчке по строкам или с помощью клавиш со стрелками.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-247">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="1d7a1-248">Чтобы выбрать непоследовательные строки, нажмите клавишу <kbd>CTRL</kbd> и щелкните, чтобы добавить строку к выделенному фрагменту.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-248">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="1d7a1-249">Нельзя выбирать столбцы, а также всю строку заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-249">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="1d7a1-250">**Копирование строк**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-250">**How to Copy Rows**</span></span>

- <span data-ttu-id="1d7a1-251">Чтобы скопировать одну или несколько строк из таблицы, выберите строки и нажмите клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-251">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="1d7a1-252">Данные можно вставить в любую программу работы с текстом или таблицами.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-252">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="1d7a1-253">Нельзя скопировать столбцы или части строк, а также строку заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-253">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="1d7a1-254">**Поиск в таблице (быстрый фильтр)**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-254">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="1d7a1-255">Используйте поле фильтра для поиска данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-255">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="1d7a1-256">При вводе значения в поле в таблице отображаются только те элементы, которые содержат введенный текст.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-256">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="1d7a1-257">Поиск текста.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-257">Search for text.</span></span> <span data-ttu-id="1d7a1-258">Чтобы найти текст в таблице, в поле Фильтр введите текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-258">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="1d7a1-259">Поиск нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-259">Search for multiple words.</span></span> <span data-ttu-id="1d7a1-260">Для поиска нескольких слов в таблице введите слова, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-260">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="1d7a1-261">`Out-GridView` Отображает строки, включающие все слова (логическое и).</span><span class="sxs-lookup"><span data-stu-id="1d7a1-261">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="1d7a1-262">Поиск литеральных фраз.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-262">Search for literal phrases.</span></span> <span data-ttu-id="1d7a1-263">Для поиска фраз, которые содержат пробелы или специальные символы, заключите фразу в кавычки.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-263">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="1d7a1-264">`Out-GridView` Отображает строки, содержащие точное совпадение для фразы.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-264">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="1d7a1-265">Поиск в столбцах.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-265">Search in columns.</span></span> <span data-ttu-id="1d7a1-266">Для поиска текста в одном или нескольких столбцах используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="1d7a1-266">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="1d7a1-267">Например, чтобы найти "NET" в столбце **DisplayName** , в поле **Фильтр** введите:</span><span class="sxs-lookup"><span data-stu-id="1d7a1-267">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="1d7a1-268">Чтобы найти строки с "NET" в столбцах **DisplayName** и **Name** , в поле **фильтра** введите:</span><span class="sxs-lookup"><span data-stu-id="1d7a1-268">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="1d7a1-269">Отключить поиск.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-269">Turn off search.</span></span> <span data-ttu-id="1d7a1-270">Чтобы снова отобразить всю таблицу, нажмите красную кнопку X в правом верхнем углу поля **фильтра** или удалите текст из поля **фильтра** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-270">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="1d7a1-271">**Использование условий для фильтрации таблицы**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-271">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="1d7a1-272">Для определения элементов, отображаемых в таблице, можно использовать правила или критерии.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-272">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="1d7a1-273">Элементы отображаются, только если они удовлетворяют всем установленным условиям.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-273">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="1d7a1-274">Доступные условия определяются свойствами объектов, отображаемых в окне представления сетки, и типами .NET Framework этих свойств.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-274">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="1d7a1-275">Каждое условие имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="1d7a1-275">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="1d7a1-276">Критерии для различных свойств соединяются с помощью **и**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-276">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="1d7a1-277">Условия для одного и того же свойства соединяются с помощью **или**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-277">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="1d7a1-278">Логические соединители изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-278">You cannot change the logical connectors.</span></span>

<span data-ttu-id="1d7a1-279">Условия влияют только на отображение.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-279">The criteria only affects the display.</span></span> <span data-ttu-id="1d7a1-280">Они не удаляют элементы из таблицы.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-280">It does not delete items from the table.</span></span>

<span data-ttu-id="1d7a1-281">**Добавление условий**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-281">**How to Add Criteria**</span></span>

1. <span data-ttu-id="1d7a1-282">Чтобы отобразить кнопку меню **Добавить критерий** , в правом верхнем углу окна щелкните стрелку Развернуть.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-282">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="1d7a1-283">Нажмите кнопку меню **Добавить критерий** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-283">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="1d7a1-284">Щелкните выбираемые столбцы (свойства).</span><span class="sxs-lookup"><span data-stu-id="1d7a1-284">Click to select columns (properties).</span></span> <span data-ttu-id="1d7a1-285">Можно выбрать одно или несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-285">You can select one or many properties.</span></span>
4. <span data-ttu-id="1d7a1-286">Завершив выбор свойств, нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-286">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="1d7a1-287">Чтобы отменить добавления, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-287">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="1d7a1-288">Чтобы добавить дополнительные условия, снова нажмите кнопку **Добавить условие** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-288">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="1d7a1-289">**Изменение условия**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-289">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="1d7a1-290">Чтобы изменить оператор, щелкните значение синего оператора, а затем выберите другой оператор из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-290">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="1d7a1-291">Чтобы ввести или изменить значение, введите значение в поле значение.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-291">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="1d7a1-292">Если введено недопустимое значение, отображается круглый значок "Х".</span><span class="sxs-lookup"><span data-stu-id="1d7a1-292">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="1d7a1-293">Он исчезает после изменения значения.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-293">To remove it, change the value.</span></span>
- <span data-ttu-id="1d7a1-294">Чтобы создать инструкцию **или** , добавьте условие с тем же свойством.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-294">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="1d7a1-295">**Удаление условий**</span><span class="sxs-lookup"><span data-stu-id="1d7a1-295">**How to Delete Criteria**</span></span>

- <span data-ttu-id="1d7a1-296">Чтобы удалить выбранные условия, щелкните красный крестик рядом с каждым критерием.</span><span class="sxs-lookup"><span data-stu-id="1d7a1-296">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="1d7a1-297">Чтобы удалить все условия, нажмите кнопку **Очистить все** .</span><span class="sxs-lookup"><span data-stu-id="1d7a1-297">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="1d7a1-298">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d7a1-298">RELATED LINKS</span></span>

[<span data-ttu-id="1d7a1-299">Out-File</span><span class="sxs-lookup"><span data-stu-id="1d7a1-299">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="1d7a1-300">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="1d7a1-300">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="1d7a1-301">Out-String</span><span class="sxs-lookup"><span data-stu-id="1d7a1-301">Out-String</span></span>](Out-String.md)

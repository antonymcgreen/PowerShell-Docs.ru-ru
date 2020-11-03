---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 73a2685947ac5980adab99a3f101a0c1f7f809d2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225830"
---
# <span data-ttu-id="257af-103">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="257af-103">Out-GridView</span></span>

## <span data-ttu-id="257af-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="257af-104">SYNOPSIS</span></span>
<span data-ttu-id="257af-105">Отправляет выходные данные в интерактивную таблицу в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="257af-105">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="257af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="257af-106">SYNTAX</span></span>

### <span data-ttu-id="257af-107">PassThru (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="257af-107">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="257af-108">Ожидание</span><span class="sxs-lookup"><span data-stu-id="257af-108">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="257af-109">OutputMode</span><span class="sxs-lookup"><span data-stu-id="257af-109">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="257af-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="257af-110">DESCRIPTION</span></span>

<span data-ttu-id="257af-111">`Out-GridView`Командлет отправляет выходные данные команды в окно представления сетки, в котором выходные данные отображаются в интерактивной таблице.</span><span class="sxs-lookup"><span data-stu-id="257af-111">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="257af-112">Поскольку для этого командлета требуется пользовательский интерфейс, он не работает на Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="257af-112">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="257af-113">Можно использовать следующие функции таблицы для анализа данных:</span><span class="sxs-lookup"><span data-stu-id="257af-113">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="257af-114">Скрытие, отображение и переупорядочение столбцов</span><span class="sxs-lookup"><span data-stu-id="257af-114">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="257af-115">Сортировать строки</span><span class="sxs-lookup"><span data-stu-id="257af-115">Sort rows</span></span>
- <span data-ttu-id="257af-116">Экспресс-фильтр</span><span class="sxs-lookup"><span data-stu-id="257af-116">Quick Filter</span></span>
- <span data-ttu-id="257af-117">Добавить фильтр критериев</span><span class="sxs-lookup"><span data-stu-id="257af-117">Add Criteria Filter</span></span>
- <span data-ttu-id="257af-118">Копирование и вставка</span><span class="sxs-lookup"><span data-stu-id="257af-118">Copy and paste</span></span>

<span data-ttu-id="257af-119">Полные инструкции см. в разделе « [Примечания](#notes) » этой статьи.</span><span class="sxs-lookup"><span data-stu-id="257af-119">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="257af-120">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="257af-120">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="257af-121">Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="257af-121">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="257af-122">Сведения о кросс-платформенной версии этого командлета см. в модуле [графикалтулс](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) в коллекция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="257af-122">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="257af-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="257af-123">EXAMPLES</span></span>

### <span data-ttu-id="257af-124">Пример 1. вывод процессов в виде сетки</span><span class="sxs-lookup"><span data-stu-id="257af-124">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="257af-125">Этот пример возвращает процессы, запущенные на локальном компьютере, и отправляет их в окно представления сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-125">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="257af-126">Пример 2. Использование переменной для вывода процессов в представлении сетки</span><span class="sxs-lookup"><span data-stu-id="257af-126">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="257af-127">Этот пример также получает процессы, запущенные на локальном компьютере, и отправляет их в окно представления сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-127">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="257af-128">Выходные данные `Get-Process` командлета сохраняются в `$P` переменной.</span><span class="sxs-lookup"><span data-stu-id="257af-128">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="257af-129">Затем `$P` передается в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-129">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="257af-130">Пример 3. Отображение выбранных свойств в представлении сетки</span><span class="sxs-lookup"><span data-stu-id="257af-130">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="257af-131">В этом примере отображаются выбранные свойства запущенных процессов в представлении сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-131">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="257af-132">Выходные данные `Get-Process` передаются в, `Select-Object` чтобы выбрать свойства **Name** , **Working** и **пеакворкингсет** .</span><span class="sxs-lookup"><span data-stu-id="257af-132">The output of `Get-Process` is piped to `Select-Object` to select the **Name** , **WorkingSet** , and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="257af-133">Другой оператор конвейера отправляет отфильтрованные объекты в `Sort-Object` командлет, чтобы сортировать их в порядке убывания по значению свойства " **рабочее** множество".</span><span class="sxs-lookup"><span data-stu-id="257af-133">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="257af-134">Затем отсортированные результаты передаются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-134">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="257af-135">Теперь можно использовать функции представления сетки для поиска, сортировки и фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="257af-135">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="257af-136">Пример 4. сохранение выходных данных в переменную, а затем вывод представления в виде сетки</span><span class="sxs-lookup"><span data-stu-id="257af-136">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="257af-137">В этом примере выходные данные командлета сохраняются в переменной, а затем отправляются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-137">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="257af-138">`Get-ChildItem` Получает все файлы в каталоге установки PowerShell и его подкаталогах, используя `$PSHOME` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="257af-138">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="257af-139">Круглые скобки в команде задают порядок операций.</span><span class="sxs-lookup"><span data-stu-id="257af-139">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="257af-140">В результате выходные данные `Get-ChildItem` команды сохраняются в `$A` переменной перед их отправкой `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-140">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="257af-141">Пример 5. выходные процессы для указанного компьютера в виде сетки</span><span class="sxs-lookup"><span data-stu-id="257af-141">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="257af-142">В этом примере отображаются процессы, запущенные на компьютере Server01, в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-142">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="257af-143">Ексамле использует `ogv` , который является псевдонимом для `Out-GridView` командлета.</span><span class="sxs-lookup"><span data-stu-id="257af-143">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="257af-144">Параметр **Title** указывает заголовок окна.</span><span class="sxs-lookup"><span data-stu-id="257af-144">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="257af-145">Пример 6. вывод данных с удаленных компьютеров в представление сетки</span><span class="sxs-lookup"><span data-stu-id="257af-145">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="257af-146">В этом примере показано, как отправить данные, собранные с удаленных компьютеров, в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-146">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="257af-147">`Invoke-Command` работает `Get-Culture` на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="257af-147">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="257af-148">Результирующие данные передаются в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-148">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="257af-149">Обратите внимание, что блок сценария, выполняемый на удаленном компьютере, не содержит `Out-GridView` команду.</span><span class="sxs-lookup"><span data-stu-id="257af-149">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="257af-150">В противном случае команда завершится сбоем при попытке открыть окно представления сетки на каждом из удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="257af-150">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="257af-151">Пример 7. Передача нескольких элементов с помощью `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="257af-151">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="257af-152">Этот пример позволяет выбрать несколько процессов из `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="257af-152">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="257af-153">Выбранные процессы передаются в `Export-Csv` команду и записываются в `ProcessLog.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="257af-153">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="257af-154">Параметр **PassThru** параметра `Out-GridView` позволяет отправить несколько элементов по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="257af-154">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="257af-155">Параметр **PassThru** эквивалентен использованию значения **Multiple** параметра **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="257af-155">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="257af-156">Пример 8. Создание ярлыка Windows для `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="257af-156">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="257af-157">В этом примере показано, как использовать параметр **Wait** параметра, `Out-GridView` чтобы создать ярлык Windows для `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="257af-157">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="257af-158">Эту командную строку можно использовать в сочетаниях клавиш Windows.</span><span class="sxs-lookup"><span data-stu-id="257af-158">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="257af-159">Без параметра **Wait** работа PowerShell будет завершена сразу после `Out-GridView` открытия окна, что приведет к немедленному закрытию `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="257af-159">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="257af-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="257af-160">PARAMETERS</span></span>

### <span data-ttu-id="257af-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="257af-161">-InputObject</span></span>

<span data-ttu-id="257af-162">Указывает объект, который командлет принимает в качестве входных данных для `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-162">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="257af-163">При использовании параметра **InputObject** для отправки коллекции объектов в `Out-GridView` , `Out-GridView` обрабатывает коллекцию как один объект коллекции и отображает одну строку, представляющую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="257af-163">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="257af-164">Чтобы отобразить каждый объект в коллекции, используйте оператор конвейера (|) для отправки объектов в `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-164">To display the each object in the collection, use a pipeline operator (|) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="257af-165">-Аутпутмоде</span><span class="sxs-lookup"><span data-stu-id="257af-165">-OutputMode</span></span>

<span data-ttu-id="257af-166">Указывает элементы, которые интерактивное окно отправляет в конвейер в качестве входных данных для других команд.</span><span class="sxs-lookup"><span data-stu-id="257af-166">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="257af-167">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="257af-167">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="257af-168">Чтобы отправить элементы из интерактивного окна в конвейер, выберите нужные элементы, а затем нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="257af-168">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="257af-169">Значения этого параметра определяют количество элементов, которое можно отправить по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="257af-169">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="257af-170">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="257af-170">None.</span></span>  <span data-ttu-id="257af-171">нет элементов.</span><span class="sxs-lookup"><span data-stu-id="257af-171">No items.</span></span> <span data-ttu-id="257af-172">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="257af-172">This is the default value.</span></span>
- <span data-ttu-id="257af-173">Одинарная.</span><span class="sxs-lookup"><span data-stu-id="257af-173">Single.</span></span> <span data-ttu-id="257af-174">нуль элементов или один элемент.</span><span class="sxs-lookup"><span data-stu-id="257af-174">Zero items or one item.</span></span> <span data-ttu-id="257af-175">Это значение используется, если следующая команда может принимать только один входной объект.</span><span class="sxs-lookup"><span data-stu-id="257af-175">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="257af-176">Несколько.</span><span class="sxs-lookup"><span data-stu-id="257af-176">Multiple.</span></span> <span data-ttu-id="257af-177">нуль, один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="257af-177">Zero, one, or many items.</span></span> <span data-ttu-id="257af-178">Это значение используется, если следующая команда может принимать несколько входных объектов.</span><span class="sxs-lookup"><span data-stu-id="257af-178">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="257af-179">Это значение эквивалентно параметру **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="257af-179">This value is equivalent to the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="257af-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="257af-180">-PassThru</span></span>

<span data-ttu-id="257af-181">Указывает, что командлет отправляет элементы из интерактивного окна в конвейер в качестве входных данных для других команд.</span><span class="sxs-lookup"><span data-stu-id="257af-181">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="257af-182">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="257af-182">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="257af-183">Этот параметр эквивалентен значению **Multiple** параметра **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="257af-183">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="257af-184">Чтобы отправить элементы из интерактивного окна в конвейер, выберите нужные элементы, а затем нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="257af-184">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="257af-185">Поддерживается выбор элементов с помощью клавиш SHIFT и CTRL.</span><span class="sxs-lookup"><span data-stu-id="257af-185">Shift-click and Ctrl-click are supported.</span></span>

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

### <span data-ttu-id="257af-186">-Title</span><span class="sxs-lookup"><span data-stu-id="257af-186">-Title</span></span>

<span data-ttu-id="257af-187">Задает текст, отображаемый в заголовке `Out-GridView` окна.</span><span class="sxs-lookup"><span data-stu-id="257af-187">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="257af-188">По умолчанию в строке заголовка отображается команда, вызывающая `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="257af-188">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

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

### <span data-ttu-id="257af-189">-Wait</span><span class="sxs-lookup"><span data-stu-id="257af-189">-Wait</span></span>

<span data-ttu-id="257af-190">Указывает, что командлет подавляет командную строку и предотвращает закрытие Windows PowerShell до `Out-GridView` закрытия окна.</span><span class="sxs-lookup"><span data-stu-id="257af-190">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="257af-191">По умолчанию командная строка возвращается при `Out-GridView` открытии окна.</span><span class="sxs-lookup"><span data-stu-id="257af-191">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="257af-192">Эта функция позволяет использовать `Out-GridView` командлеты в сочетаниях клавиш Windows.</span><span class="sxs-lookup"><span data-stu-id="257af-192">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="257af-193">Когда `Out-GridView` используется в ярлыке без параметра **Wait** , `Out-GridView` окно появляется только перед закрытием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="257af-193">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

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

### <span data-ttu-id="257af-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="257af-194">CommonParameters</span></span>

<span data-ttu-id="257af-195">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="257af-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="257af-196">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="257af-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="257af-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="257af-197">INPUTS</span></span>

### <span data-ttu-id="257af-198">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="257af-198">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="257af-199">В этот командлет можно отправить любой объект.</span><span class="sxs-lookup"><span data-stu-id="257af-199">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="257af-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="257af-200">OUTPUTS</span></span>

### <span data-ttu-id="257af-201">Нет</span><span class="sxs-lookup"><span data-stu-id="257af-201">None</span></span>

<span data-ttu-id="257af-202">Как правило, не `Out-GridView` возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="257af-202">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="257af-203">При использовании параметра **PassThru** объекты, представляющие выбранные строки, возвращаются в конвейер.</span><span class="sxs-lookup"><span data-stu-id="257af-203">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="257af-204">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="257af-204">NOTES</span></span>

<span data-ttu-id="257af-205">Удаленную команду нельзя использовать для открытия окна представления сетки на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="257af-205">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="257af-206">Выходные данные команды, которые вы отправляете в, `Out-GridView` не могут быть отформатированы с помощью `Format` командлетов, например `Format-Table` `Format-Wide` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="257af-206">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="257af-207">Чтобы выбрать свойства, используйте `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="257af-207">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="257af-208">Десериализованные выходные данные из удаленных команд могут неправильно форматироваться в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-208">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="257af-209">**Сочетания клавиш для**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="257af-209">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="257af-210">Клавиша</span><span class="sxs-lookup"><span data-stu-id="257af-210">Use this key:</span></span>              |                                   <span data-ttu-id="257af-211">Действие</span><span class="sxs-lookup"><span data-stu-id="257af-211">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="257af-212"><kbd>Вкладка</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-212"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="257af-213">Перемещает курсор из поля **Фильтр** в меню **Добавить критерии** в таблицу и обратно.</span><span class="sxs-lookup"><span data-stu-id="257af-213">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="257af-214"><kbd>Стрелка вверх</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-214"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="257af-215">Переместить вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="257af-215">Move up one row.</span></span> <span data-ttu-id="257af-216">Переходит к заголовкам столбцов из первой строки данных.</span><span class="sxs-lookup"><span data-stu-id="257af-216">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="257af-217"><kbd>Стрелка вниз</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-217"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="257af-218">Переместить на одну строку вниз.</span><span class="sxs-lookup"><span data-stu-id="257af-218">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="257af-219"><kbd>Влево</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-219"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="257af-220">В строке заголовка столбца переместитесь влево на один столбец.</span><span class="sxs-lookup"><span data-stu-id="257af-220">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="257af-221"><kbd>RightArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-221"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="257af-222">В строке заголовков столбцов переместитесь вправо на один столбец.</span><span class="sxs-lookup"><span data-stu-id="257af-222">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="257af-223"><kbd>контекстменукэй</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-223"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="257af-224">В строке заголовков столбцов отображается параметр Выбор столбцов.</span><span class="sxs-lookup"><span data-stu-id="257af-224">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="257af-225"><kbd>Ввод</kbd> или <kbd>пробел</kbd></span><span class="sxs-lookup"><span data-stu-id="257af-225"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="257af-226">В строке заголовков столбцов сортировать данные столбца (переключать A – Z, Z-A).</span><span class="sxs-lookup"><span data-stu-id="257af-226">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="257af-227">**Использование функций окна представления сетки**</span><span class="sxs-lookup"><span data-stu-id="257af-227">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="257af-228">**Скрытие или отображение столбца**</span><span class="sxs-lookup"><span data-stu-id="257af-228">**To hide or show a column:**</span></span>

1. <span data-ttu-id="257af-229">Щелкните правой кнопкой мыши заголовок любого столбца и выберите команду **выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="257af-229">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="257af-230">В диалоговом окне **Выбор столбцов** используйте клавиши со стрелками для перемещения столбцов между выбранными столбцами в поля Доступные столбцы.</span><span class="sxs-lookup"><span data-stu-id="257af-230">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="257af-231">В окне представления сетки отображаются только столбцы в поле **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="257af-231">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="257af-232">**Изменение порядка столбцов**</span><span class="sxs-lookup"><span data-stu-id="257af-232">**To reorder columns:**</span></span>

<span data-ttu-id="257af-233">Столбцы можно перетаскивать в нужное место.</span><span class="sxs-lookup"><span data-stu-id="257af-233">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="257af-234">Или выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="257af-234">Or use the following steps:</span></span>

1. <span data-ttu-id="257af-235">Щелкните правой кнопкой мыши заголовок любого столбца и выберите команду **выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="257af-235">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="257af-236">В диалоговом окне **Выбор столбцов** используйте кнопки вверх **и** **вниз** , чтобы изменить порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="257af-236">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="257af-237">Столбцы в верхней части списка отображаются слева от столбцов в нижней части списка в окне представления сетки.</span><span class="sxs-lookup"><span data-stu-id="257af-237">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="257af-238">**Сортировка данных таблицы**</span><span class="sxs-lookup"><span data-stu-id="257af-238">**How to Sort Table Data**</span></span>

- <span data-ttu-id="257af-239">Чтобы отсортировать данные, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="257af-239">To sort the data, click a column header.</span></span>
- <span data-ttu-id="257af-240">Чтобы изменить порядок сортировки, еще раз щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="257af-240">To change the sort order, click the column header again.</span></span> <span data-ttu-id="257af-241">Каждый раз при щелчке одного и того же заголовка порядок сортировки (по убыванию или по возрастанию) переключается.</span><span class="sxs-lookup"><span data-stu-id="257af-241">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="257af-242">Текущий порядок указывается значком треугольника в заголовке столбца.</span><span class="sxs-lookup"><span data-stu-id="257af-242">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="257af-243">**Выбор данных таблицы**</span><span class="sxs-lookup"><span data-stu-id="257af-243">**How to Select Table Data**</span></span>

- <span data-ttu-id="257af-244">Чтобы выбрать строку, выберите строку или используйте стрелку вверх или вниз для перехода к строке.</span><span class="sxs-lookup"><span data-stu-id="257af-244">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="257af-245">Чтобы выбрать все строки (за исключением строки заголовка), нажмите клавиши <kbd>CTRL</kbd> + <kbd>A</kbd>.</span><span class="sxs-lookup"><span data-stu-id="257af-245">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="257af-246">Чтобы выбрать последовательные строки, нажмите и удерживайте клавишу <kbd>SHIFT</kbd> при щелчке по строкам или с помощью клавиш со стрелками.</span><span class="sxs-lookup"><span data-stu-id="257af-246">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="257af-247">Чтобы выбрать непоследовательные строки, нажмите клавишу <kbd>CTRL</kbd> и щелкните, чтобы добавить строку к выделенному фрагменту.</span><span class="sxs-lookup"><span data-stu-id="257af-247">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="257af-248">Нельзя выбирать столбцы, а также всю строку заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="257af-248">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="257af-249">**Копирование строк**</span><span class="sxs-lookup"><span data-stu-id="257af-249">**How to Copy Rows**</span></span>

- <span data-ttu-id="257af-250">Чтобы скопировать одну или несколько строк из таблицы, выберите строки и нажмите клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="257af-250">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="257af-251">Данные можно вставить в любую программу работы с текстом или таблицами.</span><span class="sxs-lookup"><span data-stu-id="257af-251">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="257af-252">Нельзя скопировать столбцы или части строк, а также строку заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="257af-252">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="257af-253">**Поиск в таблице (быстрый фильтр)**</span><span class="sxs-lookup"><span data-stu-id="257af-253">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="257af-254">Используйте поле фильтра для поиска данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="257af-254">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="257af-255">При вводе значения в поле в таблице отображаются только те элементы, которые содержат введенный текст.</span><span class="sxs-lookup"><span data-stu-id="257af-255">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="257af-256">Поиск текста.</span><span class="sxs-lookup"><span data-stu-id="257af-256">Search for text.</span></span> <span data-ttu-id="257af-257">Чтобы найти текст в таблице, в поле Фильтр введите текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="257af-257">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="257af-258">Поиск нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="257af-258">Search for multiple words.</span></span> <span data-ttu-id="257af-259">Для поиска нескольких слов в таблице введите слова, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="257af-259">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="257af-260">`Out-GridView` Отображает строки, включающие все слова (логическое и).</span><span class="sxs-lookup"><span data-stu-id="257af-260">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="257af-261">Поиск литеральных фраз.</span><span class="sxs-lookup"><span data-stu-id="257af-261">Search for literal phrases.</span></span> <span data-ttu-id="257af-262">Для поиска фраз, которые содержат пробелы или специальные символы, заключите фразу в кавычки.</span><span class="sxs-lookup"><span data-stu-id="257af-262">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="257af-263">`Out-GridView` Отображает строки, содержащие точное совпадение для фразы.</span><span class="sxs-lookup"><span data-stu-id="257af-263">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="257af-264">Поиск в столбцах.</span><span class="sxs-lookup"><span data-stu-id="257af-264">Search in columns.</span></span> <span data-ttu-id="257af-265">Для поиска текста в одном или нескольких столбцах используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="257af-265">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="257af-266">Например, чтобы найти "NET" в столбце **DisplayName** , в поле **Фильтр** введите:</span><span class="sxs-lookup"><span data-stu-id="257af-266">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="257af-267">Чтобы найти строки с "NET" в столбцах **DisplayName** и **Name** , в поле **фильтра** введите:</span><span class="sxs-lookup"><span data-stu-id="257af-267">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="257af-268">Отключить поиск.</span><span class="sxs-lookup"><span data-stu-id="257af-268">Turn off search.</span></span> <span data-ttu-id="257af-269">Чтобы снова отобразить всю таблицу, нажмите красную кнопку X в правом верхнем углу поля **фильтра** или удалите текст из поля **фильтра** .</span><span class="sxs-lookup"><span data-stu-id="257af-269">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="257af-270">**Использование условий для фильтрации таблицы**</span><span class="sxs-lookup"><span data-stu-id="257af-270">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="257af-271">Для определения элементов, отображаемых в таблице, можно использовать правила или критерии.</span><span class="sxs-lookup"><span data-stu-id="257af-271">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="257af-272">Элементы отображаются, только если они удовлетворяют всем установленным условиям.</span><span class="sxs-lookup"><span data-stu-id="257af-272">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="257af-273">Доступные условия определяются свойствами объектов, отображаемых в окне представления сетки, и типами .NET Framework этих свойств.</span><span class="sxs-lookup"><span data-stu-id="257af-273">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="257af-274">Каждое условие имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="257af-274">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="257af-275">Критерии для различных свойств соединяются с помощью **и**.</span><span class="sxs-lookup"><span data-stu-id="257af-275">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="257af-276">Условия для одного и того же свойства соединяются с помощью **или**.</span><span class="sxs-lookup"><span data-stu-id="257af-276">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="257af-277">Логические соединители изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="257af-277">You cannot change the logical connectors.</span></span>

<span data-ttu-id="257af-278">Условия влияют только на отображение.</span><span class="sxs-lookup"><span data-stu-id="257af-278">The criteria only affects the display.</span></span> <span data-ttu-id="257af-279">Они не удаляют элементы из таблицы.</span><span class="sxs-lookup"><span data-stu-id="257af-279">It does not delete items from the table.</span></span>

<span data-ttu-id="257af-280">**Добавление условий**</span><span class="sxs-lookup"><span data-stu-id="257af-280">**How to Add Criteria**</span></span>

1. <span data-ttu-id="257af-281">Чтобы отобразить кнопку меню **Добавить критерий** , в правом верхнем углу окна щелкните стрелку Развернуть.</span><span class="sxs-lookup"><span data-stu-id="257af-281">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="257af-282">Нажмите кнопку меню **Добавить критерий** .</span><span class="sxs-lookup"><span data-stu-id="257af-282">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="257af-283">Щелкните выбираемые столбцы (свойства).</span><span class="sxs-lookup"><span data-stu-id="257af-283">Click to select columns (properties).</span></span> <span data-ttu-id="257af-284">Можно выбрать одно или несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="257af-284">You can select one or many properties.</span></span>
4. <span data-ttu-id="257af-285">Завершив выбор свойств, нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="257af-285">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="257af-286">Чтобы отменить добавления, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="257af-286">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="257af-287">Чтобы добавить дополнительные условия, снова нажмите кнопку **Добавить условие** .</span><span class="sxs-lookup"><span data-stu-id="257af-287">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="257af-288">**Изменение условия**</span><span class="sxs-lookup"><span data-stu-id="257af-288">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="257af-289">Чтобы изменить оператор, щелкните значение синего оператора, а затем выберите другой оператор из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="257af-289">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="257af-290">Чтобы ввести или изменить значение, введите значение в поле значение.</span><span class="sxs-lookup"><span data-stu-id="257af-290">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="257af-291">Если введено недопустимое значение, отображается круглый значок "Х".</span><span class="sxs-lookup"><span data-stu-id="257af-291">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="257af-292">Он исчезает после изменения значения.</span><span class="sxs-lookup"><span data-stu-id="257af-292">To remove it, change the value.</span></span>
- <span data-ttu-id="257af-293">Чтобы создать инструкцию **или** , добавьте условие с тем же свойством.</span><span class="sxs-lookup"><span data-stu-id="257af-293">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="257af-294">**Удаление условий**</span><span class="sxs-lookup"><span data-stu-id="257af-294">**How to Delete Criteria**</span></span>

- <span data-ttu-id="257af-295">Чтобы удалить выбранные условия, щелкните красный крестик рядом с каждым критерием.</span><span class="sxs-lookup"><span data-stu-id="257af-295">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="257af-296">Чтобы удалить все условия, нажмите кнопку **Очистить все** .</span><span class="sxs-lookup"><span data-stu-id="257af-296">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="257af-297">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="257af-297">RELATED LINKS</span></span>

[<span data-ttu-id="257af-298">Out-File</span><span class="sxs-lookup"><span data-stu-id="257af-298">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="257af-299">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="257af-299">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="257af-300">Out-String</span><span class="sxs-lookup"><span data-stu-id="257af-300">Out-String</span></span>](Out-String.md)

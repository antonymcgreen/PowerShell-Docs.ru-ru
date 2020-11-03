---
description: Компонент
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Function Provider
ms.openlocfilehash: 8789ceadbefed2dca47c10c26204f3e9ae82d36e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231117"
---
# <a name="function-provider"></a><span data-ttu-id="23d2e-104">Поставщик функций</span><span class="sxs-lookup"><span data-stu-id="23d2e-104">Function provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="23d2e-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="23d2e-105">Provider name</span></span>
<span data-ttu-id="23d2e-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="23d2e-106">Function</span></span>

## <a name="drives"></a><span data-ttu-id="23d2e-107">Диски</span><span class="sxs-lookup"><span data-stu-id="23d2e-107">Drives</span></span>

`Function:`

## <a name="capabilities"></a><span data-ttu-id="23d2e-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="23d2e-108">Capabilities</span></span>

<span data-ttu-id="23d2e-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="23d2e-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="23d2e-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="23d2e-110">Short description</span></span>

<span data-ttu-id="23d2e-111">Предоставляет доступ к функциям, определенным в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-111">Provides access to the functions defined in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="23d2e-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="23d2e-112">Detailed description</span></span>

<span data-ttu-id="23d2e-113">Поставщик **функций** PowerShell позволяет получать, добавлять, изменять, очищать и удалять функции и фильтры в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-113">The PowerShell **Function** provider lets you get, add, change, clear, and delete the functions and filters in PowerShell.</span></span>

<span data-ttu-id="23d2e-114">Функция представляет собой именованный блок кода, выполняющий некоторое действие.</span><span class="sxs-lookup"><span data-stu-id="23d2e-114">A function is a named block of code that performs an action.</span></span> <span data-ttu-id="23d2e-115">Если ввести имя функции, выполняется код этой функции.</span><span class="sxs-lookup"><span data-stu-id="23d2e-115">When you type the function name, the code in the function runs.</span></span> <span data-ttu-id="23d2e-116">Фильтр представляет собой именованный блок кода, устанавливающий условия выполнения некоторого действия.</span><span class="sxs-lookup"><span data-stu-id="23d2e-116">A filter is a named block of code that establishes conditions for an action.</span></span> <span data-ttu-id="23d2e-117">Можно ввести имя фильтра вместо условия, например в `Where-Object` команде.</span><span class="sxs-lookup"><span data-stu-id="23d2e-117">You can type the name of the filter in place of the condition, such as in a `Where-Object` command.</span></span>

<span data-ttu-id="23d2e-118">Диск **функции** является плоским пространством имен, которое содержит только объекты Function и Filter.</span><span class="sxs-lookup"><span data-stu-id="23d2e-118">The **Function** drive is a flat namespace that contains only the function and filter objects.</span></span> <span data-ttu-id="23d2e-119">Ни функции, ни фильтры не имеют дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="23d2e-119">Neither functions nor filters have child items.</span></span>

<span data-ttu-id="23d2e-120">Поставщик **функций** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="23d2e-120">The **Function** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="23d2e-121">Get-Location</span><span class="sxs-lookup"><span data-stu-id="23d2e-121">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="23d2e-122">Set-Location</span><span class="sxs-lookup"><span data-stu-id="23d2e-122">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="23d2e-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-123">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="23d2e-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="23d2e-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="23d2e-126">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-126">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="23d2e-127">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="23d2e-127">Types exposed by this provider</span></span>

<span data-ttu-id="23d2e-128">Каждая функция является экземпляром класса [System. Management. Automation. FunctionInfo](/dotnet/api/system.management.automation.functioninfo) .</span><span class="sxs-lookup"><span data-stu-id="23d2e-128">Each function is an instance of the [System.Management.Automation.FunctionInfo](/dotnet/api/system.management.automation.functioninfo) class.</span></span> <span data-ttu-id="23d2e-129">Каждый фильтр является экземпляром класса [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) .</span><span class="sxs-lookup"><span data-stu-id="23d2e-129">Each filter is an instance of the [System.Management.Automation.FilterInfo](/dotnet/api/system.management.automation.filterinfo) class.</span></span>

## <a name="navigating-the-function-drive"></a><span data-ttu-id="23d2e-130">Навигация по диску функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-130">Navigating the Function drive</span></span>

<span data-ttu-id="23d2e-131">Поставщик **функций** предоставляет хранилище данных на `Function:` диске.</span><span class="sxs-lookup"><span data-stu-id="23d2e-131">The **Function** provider exposes its data store in the `Function:` drive.</span></span> <span data-ttu-id="23d2e-132">Для работы с функциями можно изменить расположение на `Function:` диск ( `Set-Location Function:` ).</span><span class="sxs-lookup"><span data-stu-id="23d2e-132">To work with functions, you can change your location to the `Function:` drive (`Set-Location Function:`).</span></span> <span data-ttu-id="23d2e-133">Кроме того, можно работать с другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-133">Or, you can work from another PowerShell drive.</span></span> <span data-ttu-id="23d2e-134">Чтобы сослаться на функцию из другого расположения, используйте имя диска ( `Function:` ) в пути.</span><span class="sxs-lookup"><span data-stu-id="23d2e-134">To reference a function from another location, use the drive name (`Function:`) in the path.</span></span>

```powershell
Set-Location Function:
```

<span data-ttu-id="23d2e-135">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="23d2e-135">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="23d2e-136">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="23d2e-136">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="23d2e-137">Вы также можете работать с поставщиком **функций** из любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-137">You can also work with the **Function** provider from any other PowerShell drive.</span></span> <span data-ttu-id="23d2e-138">Чтобы сослаться на функцию из другого расположения, используйте имя диска `Function:` в пути.</span><span class="sxs-lookup"><span data-stu-id="23d2e-138">To reference an function from another location, use the drive name `Function:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="23d2e-139">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="23d2e-139">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="23d2e-140">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="23d2e-140">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="23d2e-141">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="23d2e-141">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-functions"></a><span data-ttu-id="23d2e-142">Получение функций</span><span class="sxs-lookup"><span data-stu-id="23d2e-142">Getting functions</span></span>

<span data-ttu-id="23d2e-143">Эта команда возвращает список всех функций в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="23d2e-143">This command gets the list of all the functions in the current session.</span></span> <span data-ttu-id="23d2e-144">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-144">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="23d2e-145">Поставщик функций не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-145">The Function provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="23d2e-146">Определение функции можно получить, обратившись к свойству **определения** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="23d2e-146">You can retrieve a function's definition by accessing the **Definition** property, as shown below.</span></span>

```powershell
(Get-Item -Path function:more).Definition
```

<span data-ttu-id="23d2e-147">Кроме того, можно получить определение функции, используя путь к поставщику с префиксом доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="23d2e-147">You can also retrieve a function's definition using its provider path prefixed by the dollar sign (`$`).</span></span>

```powershell
$function:more
```

### <a name="getting-selected-functions"></a><span data-ttu-id="23d2e-148">Получение выбранных функций</span><span class="sxs-lookup"><span data-stu-id="23d2e-148">Getting selected functions</span></span>

<span data-ttu-id="23d2e-149">Эта команда возвращает `man` функцию с `Function:` диска.</span><span class="sxs-lookup"><span data-stu-id="23d2e-149">This command gets the `man` function from the `Function:` drive.</span></span> <span data-ttu-id="23d2e-150">`Get-Item`Для получения функции используется командлет.</span><span class="sxs-lookup"><span data-stu-id="23d2e-150">It uses the `Get-Item` cmdlet to get the function.</span></span> <span data-ttu-id="23d2e-151">Оператор конвейера ( `|` ) отправляет результат в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-151">The pipeline operator (`|`) sends the result to `Format-Table`.</span></span> <span data-ttu-id="23d2e-152">`-Wrap`Параметр направляет текст, который не умещается на строке, на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="23d2e-152">The `-Wrap` parameter directs text that does not fit on the line onto the next line.</span></span> <span data-ttu-id="23d2e-153">`-Autosize`Параметр изменяет размер столбцов таблицы в соответствии с текстом.</span><span class="sxs-lookup"><span data-stu-id="23d2e-153">The `-Autosize` parameter resizes the table columns to accommodate the text.</span></span>

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a><span data-ttu-id="23d2e-154">Работа с путями поставщика функций</span><span class="sxs-lookup"><span data-stu-id="23d2e-154">Working with Function provider paths</span></span>

<span data-ttu-id="23d2e-155">Эти команды получают функцию с именем `c:` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-155">These commands both get the function named `c:`.</span></span> <span data-ttu-id="23d2e-156">Первую команду можно использовать на любом диске.</span><span class="sxs-lookup"><span data-stu-id="23d2e-156">The first command can be used in any drive.</span></span> <span data-ttu-id="23d2e-157">Вторая команда используется на `Function:` диске.</span><span class="sxs-lookup"><span data-stu-id="23d2e-157">The second command is used in the `Function:` drive.</span></span> <span data-ttu-id="23d2e-158">Поскольку имя функции оканчивается двоеточием, то есть имеет синтаксис имени диска, необходимо указать в пути имя диска.</span><span class="sxs-lookup"><span data-stu-id="23d2e-158">Because the name ends in a colon, which is the syntax for a drive, you must qualify the path with the drive name.</span></span> <span data-ttu-id="23d2e-159">На `Function:` диске можно использовать любой из этих форматов.</span><span class="sxs-lookup"><span data-stu-id="23d2e-159">Within the `Function:` drive, you can use either format.</span></span> <span data-ttu-id="23d2e-160">Во второй команде точка ( `.` ) представляет текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="23d2e-160">In the second command, the dot (`.`) represents the current location.</span></span>

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a><span data-ttu-id="23d2e-161">Создание функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-161">Creating a function</span></span>

<span data-ttu-id="23d2e-162">Эта команда использует `New-Item` командлет для создания функции с именем `Win32:` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-162">This command uses the `New-Item` cmdlet to create a function called `Win32:`.</span></span>
<span data-ttu-id="23d2e-163">Выражение в фигурных скобках является блоком скрипта, который представлен именем функции.</span><span class="sxs-lookup"><span data-stu-id="23d2e-163">The expression in braces is the script block that is represented by the function name.</span></span>

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

<span data-ttu-id="23d2e-164">Вы также можете создать функцию, введя ее в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23d2e-164">You can also create a function by typing it at the PowerShell command line.</span></span> <span data-ttu-id="23d2e-165">Например, типов `Function:Win32: {Set-Location C:\Windows\System32}` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-165">For example, tpe `Function:Win32: {Set-Location C:\Windows\System32}`.</span></span> <span data-ttu-id="23d2e-166">Если вы используете `Function:` диск, можно опустить имя диска.</span><span class="sxs-lookup"><span data-stu-id="23d2e-166">If you are in the `Function:` drive, you can omit the drive name.</span></span>

## <a name="deleting-a-function"></a><span data-ttu-id="23d2e-167">Удаление функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-167">Deleting a function</span></span>

<span data-ttu-id="23d2e-168">Эта команда удаляет `more:` функцию из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="23d2e-168">This command deletes the `more:` function from the current session.</span></span>

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a><span data-ttu-id="23d2e-169">Изменение функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-169">Changing a function</span></span>

<span data-ttu-id="23d2e-170">Эта команда использует `Set-Item` командлет для изменения `prompt` функции таким образом, чтобы она отображала время перед путем.</span><span class="sxs-lookup"><span data-stu-id="23d2e-170">This command uses the `Set-Item` cmdlet to change the `prompt` function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a><span data-ttu-id="23d2e-171">Переименование функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-171">Rename a function</span></span>

<span data-ttu-id="23d2e-172">Эта команда использует `Rename-Item` командлет, чтобы изменить имя `help` функции на `gh` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-172">This command uses the `Rename-Item` cmdlet to change the name of the `help` function to `gh`.</span></span>

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a><span data-ttu-id="23d2e-173">Копирование функции</span><span class="sxs-lookup"><span data-stu-id="23d2e-173">Copying a function</span></span>

<span data-ttu-id="23d2e-174">Эта команда копирует `prompt` функцию в `oldPrompt` , эффективно создавая новое имя для блока сценария, связанного с функцией prompt.</span><span class="sxs-lookup"><span data-stu-id="23d2e-174">This command copies the `prompt` function to `oldPrompt`, effectively creating a new name for the script block that is associated with the prompt function.</span></span>
<span data-ttu-id="23d2e-175">Таким образом можно сохранить исходную функцию prompt, если планируется изменить ее.</span><span class="sxs-lookup"><span data-stu-id="23d2e-175">You can use this to save the original prompt function if you plan to change it.</span></span>
<span data-ttu-id="23d2e-176">Свойство **Options** новой функции имеет значение `None` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-176">The **Options** property of the new function has a value of `None`.</span></span> <span data-ttu-id="23d2e-177">Чтобы изменить значение свойства **Options** , используйте `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-177">To change the value of the **Options** property, use `Set-Item`.</span></span>

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a><span data-ttu-id="23d2e-178">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="23d2e-178">Dynamic parameters</span></span>

<span data-ttu-id="23d2e-179">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="23d2e-179">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="23d2e-180">Параметры < [System. Management. Automation. Скопедитемоптионс] ></span><span class="sxs-lookup"><span data-stu-id="23d2e-180">Options <[System.Management.Automation.ScopedItemOptions]></span></span>

<span data-ttu-id="23d2e-181">Определяет значение свойства **Options** функции.</span><span class="sxs-lookup"><span data-stu-id="23d2e-181">Determines the value of the **Options** property of a function.</span></span>

- <span data-ttu-id="23d2e-182">`None`: Нет параметров.</span><span class="sxs-lookup"><span data-stu-id="23d2e-182">`None`: No options.</span></span> <span data-ttu-id="23d2e-183">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="23d2e-183">`None` is the default.</span></span>
- <span data-ttu-id="23d2e-184">`Constant`: Функция не может быть удалена, и ее свойства нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="23d2e-184">`Constant`: The function cannot be deleted, and its properties cannot be changed.</span></span> <span data-ttu-id="23d2e-185">`Constant` доступен только при создании функции.</span><span class="sxs-lookup"><span data-stu-id="23d2e-185">`Constant` is available only when you are creating a function.</span></span>
  <span data-ttu-id="23d2e-186">Нельзя изменить параметр существующей функции на `Constant` .</span><span class="sxs-lookup"><span data-stu-id="23d2e-186">You cannot change the option of an existing function to `Constant`.</span></span>
- <span data-ttu-id="23d2e-187">`Private`: Функция видима только в текущей области видимости</span><span class="sxs-lookup"><span data-stu-id="23d2e-187">`Private`: The function is visible only in the current scope</span></span>
- <span data-ttu-id="23d2e-188">(не в дочерних областях).</span><span class="sxs-lookup"><span data-stu-id="23d2e-188">(not in child scopes).</span></span>
- <span data-ttu-id="23d2e-189">`ReadOnly`: Свойства функции не могут быть изменены, за исключением использования `-Force` параметра.</span><span class="sxs-lookup"><span data-stu-id="23d2e-189">`ReadOnly`: The properties of the function cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="23d2e-190">`Remove-Item`Для удаления функции можно использовать.</span><span class="sxs-lookup"><span data-stu-id="23d2e-190">You can use `Remove-Item` to delete the function.</span></span>
- <span data-ttu-id="23d2e-191">`AllScope`: Функция копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="23d2e-191">`AllScope`: The function is copied to any new scopes that are created.</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="23d2e-192">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="23d2e-192">Cmdlets supported</span></span>

- [<span data-ttu-id="23d2e-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-193">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

- [<span data-ttu-id="23d2e-194">Set-Item</span><span class="sxs-lookup"><span data-stu-id="23d2e-194">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="23d2e-195">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="23d2e-195">Using the pipeline</span></span>

<span data-ttu-id="23d2e-196">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="23d2e-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="23d2e-197">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="23d2e-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="23d2e-198">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="23d2e-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="23d2e-199">Получение справки</span><span class="sxs-lookup"><span data-stu-id="23d2e-199">Getting help</span></span>

<span data-ttu-id="23d2e-200">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="23d2e-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="23d2e-201">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="23d2e-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a><span data-ttu-id="23d2e-202">См. также статью</span><span class="sxs-lookup"><span data-stu-id="23d2e-202">See also</span></span>

[<span data-ttu-id="23d2e-203">about_Functions</span><span class="sxs-lookup"><span data-stu-id="23d2e-203">about_Functions</span></span>](../About/about_Functions.md)

[<span data-ttu-id="23d2e-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="23d2e-204">about_Providers</span></span>](../About/about_Providers.md)


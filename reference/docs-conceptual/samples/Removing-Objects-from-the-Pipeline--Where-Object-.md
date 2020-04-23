---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Удаление объектов из конвейера (Where-Object)
ms.openlocfilehash: 370e7745341b70c0794352a690d5750d21f53ac2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737191"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="72228-103">Удаление объектов из конвейера (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="72228-103">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="72228-104">В PowerShell часто создается и передается в конвейер большее количество объектов, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="72228-104">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="72228-105">Чтобы указать свойства конкретного объекта, которые требуется отобразить, можно воспользоваться командлетом `Format-*`, но это не позволяет решить проблему удаления с экрана всех объектов.</span><span class="sxs-lookup"><span data-stu-id="72228-105">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="72228-106">Может потребоваться отфильтровать объекты до достижения конца конвейера, чтобы выполнить те или иные действия только с подмножеством объектов, созданных изначально.</span><span class="sxs-lookup"><span data-stu-id="72228-106">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="72228-107">В PowerShell есть командлет `Where-Object`, который позволяет протестировать каждый объект в конвейере и передать его дальше, только если он удовлетворяет определенному условию теста.</span><span class="sxs-lookup"><span data-stu-id="72228-107">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="72228-108">Объекты, не прошедшие проверку, удаляются из конвейера.</span><span class="sxs-lookup"><span data-stu-id="72228-108">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="72228-109">Условие теста передается в виде значения параметра **FilterScript**.</span><span class="sxs-lookup"><span data-stu-id="72228-109">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="72228-110">Выполнение простых проверок с использованием командлета Where-Object</span><span class="sxs-lookup"><span data-stu-id="72228-110">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="72228-111">Значение **FilterScript** представляет собой *блок сценария* (одну или несколько команд PowerShell, заключенных в фигурные скобки (`{}`)), который возвращает значение True или False.</span><span class="sxs-lookup"><span data-stu-id="72228-111">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="72228-112">Такие блоки сценариев могут быть очень простыми, но для их создания требуется понимание другой концепции PowerShell, а именно операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="72228-112">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="72228-113">Оператор сравнения сравнивает элементы, расположенные с обеих сторон оператора.</span><span class="sxs-lookup"><span data-stu-id="72228-113">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="72228-114">Запись операторов сравнения начинается знаком дефиса (`-`), после которого следует имя оператора.</span><span class="sxs-lookup"><span data-stu-id="72228-114">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="72228-115">Основные операторы сравнения работают, как правило, с любыми видами объектов.</span><span class="sxs-lookup"><span data-stu-id="72228-115">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="72228-116">Более сложные операторы сравнения работают только с текстом или массивами.</span><span class="sxs-lookup"><span data-stu-id="72228-116">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="72228-117">По умолчанию при работе с текстом в PowerShell операторы сравнения нечувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="72228-117">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="72228-118">Исходя из соображений синтаксического анализа, такие знаки, как `<`, `>` и `=`, не используются в качестве операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="72228-118">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="72228-119">Вместо этого операторы сравнения записываются в буквенной форме.</span><span class="sxs-lookup"><span data-stu-id="72228-119">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="72228-120">Основные операторы сравнения перечислены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="72228-120">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="72228-121">Оператор сравнения</span><span class="sxs-lookup"><span data-stu-id="72228-121">Comparison Operator</span></span> |                  <span data-ttu-id="72228-122">Значение</span><span class="sxs-lookup"><span data-stu-id="72228-122">Meaning</span></span>                   |    <span data-ttu-id="72228-123">Пример (возвращает значение True)</span><span class="sxs-lookup"><span data-stu-id="72228-123">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="72228-124">-eq</span><span class="sxs-lookup"><span data-stu-id="72228-124">-eq</span></span>                 | <span data-ttu-id="72228-125">равно</span><span class="sxs-lookup"><span data-stu-id="72228-125">is equal to</span></span>                                | <span data-ttu-id="72228-126">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="72228-126">1 -eq 1</span></span>                      |
| <span data-ttu-id="72228-127">-ne</span><span class="sxs-lookup"><span data-stu-id="72228-127">-ne</span></span>                 | <span data-ttu-id="72228-128">не равно</span><span class="sxs-lookup"><span data-stu-id="72228-128">Is not equal to</span></span>                            | <span data-ttu-id="72228-129">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="72228-129">1 -ne 2</span></span>                      |
| <span data-ttu-id="72228-130">-lt</span><span class="sxs-lookup"><span data-stu-id="72228-130">-lt</span></span>                 | <span data-ttu-id="72228-131">меньше</span><span class="sxs-lookup"><span data-stu-id="72228-131">Is less than</span></span>                               | <span data-ttu-id="72228-132">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="72228-132">1 -lt 2</span></span>                      |
| <span data-ttu-id="72228-133">-le</span><span class="sxs-lookup"><span data-stu-id="72228-133">-le</span></span>                 | <span data-ttu-id="72228-134">Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="72228-134">Is less than or equal to</span></span>                   | <span data-ttu-id="72228-135">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="72228-135">1 -le 2</span></span>                      |
| <span data-ttu-id="72228-136">-gt</span><span class="sxs-lookup"><span data-stu-id="72228-136">-gt</span></span>                 | <span data-ttu-id="72228-137">Больше</span><span class="sxs-lookup"><span data-stu-id="72228-137">Is greater than</span></span>                            | <span data-ttu-id="72228-138">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="72228-138">2 -gt 1</span></span>                      |
| <span data-ttu-id="72228-139">-ge</span><span class="sxs-lookup"><span data-stu-id="72228-139">-ge</span></span>                 | <span data-ttu-id="72228-140">Больше или равно</span><span class="sxs-lookup"><span data-stu-id="72228-140">Is greater than or equal to</span></span>                | <span data-ttu-id="72228-141">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="72228-141">2 -ge 1</span></span>                      |
| <span data-ttu-id="72228-142">-like</span><span class="sxs-lookup"><span data-stu-id="72228-142">-like</span></span>               | <span data-ttu-id="72228-143">сравнение на совпадение с учетом подстановочного знака в тексте</span><span class="sxs-lookup"><span data-stu-id="72228-143">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="72228-144">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="72228-144">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="72228-145">-notlike</span><span class="sxs-lookup"><span data-stu-id="72228-145">-notlike</span></span>            | <span data-ttu-id="72228-146">сравнение на несовпадение с учетом подстановочного знака в тексте</span><span class="sxs-lookup"><span data-stu-id="72228-146">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="72228-147">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="72228-147">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="72228-148">-contains</span><span class="sxs-lookup"><span data-stu-id="72228-148">-contains</span></span>           | <span data-ttu-id="72228-149">Содержит</span><span class="sxs-lookup"><span data-stu-id="72228-149">Contains</span></span>                                   | <span data-ttu-id="72228-150">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="72228-150">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="72228-151">-notcontains</span><span class="sxs-lookup"><span data-stu-id="72228-151">-notcontains</span></span>        | <span data-ttu-id="72228-152">Не содержит</span><span class="sxs-lookup"><span data-stu-id="72228-152">Does not contain</span></span>                           | <span data-ttu-id="72228-153">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="72228-153">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="72228-154">В блоках сценариев командлета `Where-Object` для обращения к текущему объекту конвейера используется специальная переменная `$_`.</span><span class="sxs-lookup"><span data-stu-id="72228-154">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="72228-155">Ниже приведен пример использования этой переменной.</span><span class="sxs-lookup"><span data-stu-id="72228-155">Here is an example of how it works.</span></span> <span data-ttu-id="72228-156">Если в списке содержатся числа и требуется вернуть только те, которые меньше 3, в командлете `Where-Object` можно настроить фильтр чисел:</span><span class="sxs-lookup"><span data-stu-id="72228-156">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="72228-157">Фильтрация, основанная на свойствах объектов</span><span class="sxs-lookup"><span data-stu-id="72228-157">Filtering Based on Object Properties</span></span>

<span data-ttu-id="72228-158">Так как переменная `$_` ссылается на текущий объект конвейера, для выполнения проверок можно обратиться к ее свойствам.</span><span class="sxs-lookup"><span data-stu-id="72228-158">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="72228-159">Например, в инструментарии WMI можно просмотреть класс **Win32_SystemDriver**.</span><span class="sxs-lookup"><span data-stu-id="72228-159">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="72228-160">В какой-то конкретной системе могут содержаться сотни системных драйверов, но для проверки необходим определенный набор системных драйверов — таких, которые запущены в данный момент.</span><span class="sxs-lookup"><span data-stu-id="72228-160">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="72228-161">Для класса **Win32_SystemDriver** соответствующим свойством является **State**.</span><span class="sxs-lookup"><span data-stu-id="72228-161">For the **Win32_SystemDriver** class the relevant property is **State**.</span></span> <span data-ttu-id="72228-162">Таким образом, фильтровать системные драйверы и выбирать только запущенные можно с помощью строки:</span><span class="sxs-lookup"><span data-stu-id="72228-162">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="72228-163">В результате будет получен длинный список.</span><span class="sxs-lookup"><span data-stu-id="72228-163">This still produces a long list.</span></span> <span data-ttu-id="72228-164">Чтобы отфильтровать эти драйверы для выбора только таких, запуск которых выполняется автоматически, можно проверить значение **StartMode**:</span><span class="sxs-lookup"><span data-stu-id="72228-164">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
...
```

<span data-ttu-id="72228-165">Результат выполнения этой команды содержит много ненужных сведений, поскольку драйверы, запущенные в данный момент, уже известны.</span><span class="sxs-lookup"><span data-stu-id="72228-165">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="72228-166">В действительности, из всех сведений на данном этапе требуется только имя и отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="72228-166">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="72228-167">Следующая команда включает только эти два свойства, что дает более простые выходные данные:</span><span class="sxs-lookup"><span data-stu-id="72228-167">The following command includes only those two properties, resulting in much simpler output:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

<span data-ttu-id="72228-168">Приведенная выше команда содержит два элемента `Where-Object`, но их можно объединить в один `Where-Object`, используя знак логический оператор `-and`:</span><span class="sxs-lookup"><span data-stu-id="72228-168">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="72228-169">Стандартные логические операторы перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="72228-169">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="72228-170">Логический оператор</span><span class="sxs-lookup"><span data-stu-id="72228-170">Logical Operator</span></span> |                 <span data-ttu-id="72228-171">Значение</span><span class="sxs-lookup"><span data-stu-id="72228-171">Meaning</span></span>                  |  <span data-ttu-id="72228-172">Пример (возвращает значение True)</span><span class="sxs-lookup"><span data-stu-id="72228-172">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="72228-173">-and</span><span class="sxs-lookup"><span data-stu-id="72228-173">-and</span></span>             | <span data-ttu-id="72228-174">Логическое И; возвращает значение True, если оба операнда принимают значение True</span><span class="sxs-lookup"><span data-stu-id="72228-174">Logical and; true if both sides are true</span></span> | <span data-ttu-id="72228-175">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="72228-175">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="72228-176">-or</span><span class="sxs-lookup"><span data-stu-id="72228-176">-or</span></span>              | <span data-ttu-id="72228-177">Логическое ИЛИ; возвращает значение True, если один из операндов принимает значение True</span><span class="sxs-lookup"><span data-stu-id="72228-177">Logical or; true if either side is true</span></span>  | <span data-ttu-id="72228-178">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="72228-178">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="72228-179">-not</span><span class="sxs-lookup"><span data-stu-id="72228-179">-not</span></span>             | <span data-ttu-id="72228-180">Логическое НЕ; изменяет значение (True или False) на противоположное</span><span class="sxs-lookup"><span data-stu-id="72228-180">Logical not; reverses true and false</span></span>     | <span data-ttu-id="72228-181">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="72228-181">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="72228-182">Логическое НЕ; изменяет значение (True или False) на противоположное</span><span class="sxs-lookup"><span data-stu-id="72228-182">Logical not; reverses true and false</span></span>     | <span data-ttu-id="72228-183">\! (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="72228-183">\!(1 -eq 2)</span></span>              |

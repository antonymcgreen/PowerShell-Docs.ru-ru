---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Удаление объектов из конвейера (Where-Object)
description: Командлет Where-Object позволяет фильтровать объекты, передаваемые по конвейеру.
ms.openlocfilehash: e744dc671303711f1cbe8cc724a97c3327c1da85
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500119"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="6c817-104">Удаление объектов из конвейера (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="6c817-104">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="6c817-105">В PowerShell часто создается и передается в конвейер большее количество объектов, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="6c817-105">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="6c817-106">Чтобы указать свойства конкретного объекта, которые требуется отобразить, можно воспользоваться командлетом `Format-*`, но это не позволяет решить проблему удаления с экрана всех объектов.</span><span class="sxs-lookup"><span data-stu-id="6c817-106">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="6c817-107">Может потребоваться отфильтровать объекты до достижения конца конвейера, чтобы выполнить те или иные действия только с подмножеством объектов, созданных изначально.</span><span class="sxs-lookup"><span data-stu-id="6c817-107">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="6c817-108">В PowerShell есть командлет `Where-Object`, который позволяет протестировать каждый объект в конвейере и передать его дальше, только если он удовлетворяет определенному условию теста.</span><span class="sxs-lookup"><span data-stu-id="6c817-108">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="6c817-109">Объекты, не прошедшие проверку, удаляются из конвейера.</span><span class="sxs-lookup"><span data-stu-id="6c817-109">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="6c817-110">Условие теста передается в виде значения параметра **FilterScript** .</span><span class="sxs-lookup"><span data-stu-id="6c817-110">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="6c817-111">Выполнение простых проверок с использованием командлета Where-Object</span><span class="sxs-lookup"><span data-stu-id="6c817-111">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="6c817-112">Значение **FilterScript** представляет собой *блок сценария* (одну или несколько команд PowerShell, заключенных в фигурные скобки (`{}`)), который возвращает значение True или False.</span><span class="sxs-lookup"><span data-stu-id="6c817-112">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="6c817-113">Такие блоки сценариев могут быть очень простыми, но для их создания требуется понимание другой концепции PowerShell, а именно операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="6c817-113">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="6c817-114">Оператор сравнения сравнивает элементы, расположенные с обеих сторон оператора.</span><span class="sxs-lookup"><span data-stu-id="6c817-114">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="6c817-115">Запись операторов сравнения начинается знаком дефиса (`-`), после которого следует имя оператора.</span><span class="sxs-lookup"><span data-stu-id="6c817-115">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="6c817-116">Основные операторы сравнения работают, как правило, с любыми видами объектов.</span><span class="sxs-lookup"><span data-stu-id="6c817-116">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="6c817-117">Более сложные операторы сравнения работают только с текстом или массивами.</span><span class="sxs-lookup"><span data-stu-id="6c817-117">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="6c817-118">По умолчанию при работе с текстом в PowerShell операторы сравнения нечувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="6c817-118">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="6c817-119">Исходя из соображений синтаксического анализа, такие знаки, как `<`, `>` и `=`, не используются в качестве операторов сравнения.</span><span class="sxs-lookup"><span data-stu-id="6c817-119">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="6c817-120">Вместо этого операторы сравнения записываются в буквенной форме.</span><span class="sxs-lookup"><span data-stu-id="6c817-120">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="6c817-121">Основные операторы сравнения перечислены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="6c817-121">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="6c817-122">Оператор сравнения</span><span class="sxs-lookup"><span data-stu-id="6c817-122">Comparison Operator</span></span> |                  <span data-ttu-id="6c817-123">Значение</span><span class="sxs-lookup"><span data-stu-id="6c817-123">Meaning</span></span>                   |    <span data-ttu-id="6c817-124">Пример (возвращает значение True)</span><span class="sxs-lookup"><span data-stu-id="6c817-124">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="6c817-125">-eq</span><span class="sxs-lookup"><span data-stu-id="6c817-125">-eq</span></span>                 | <span data-ttu-id="6c817-126">равно</span><span class="sxs-lookup"><span data-stu-id="6c817-126">is equal to</span></span>                                | <span data-ttu-id="6c817-127">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="6c817-127">1 -eq 1</span></span>                      |
| <span data-ttu-id="6c817-128">-ne</span><span class="sxs-lookup"><span data-stu-id="6c817-128">-ne</span></span>                 | <span data-ttu-id="6c817-129">не равно</span><span class="sxs-lookup"><span data-stu-id="6c817-129">Is not equal to</span></span>                            | <span data-ttu-id="6c817-130">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="6c817-130">1 -ne 2</span></span>                      |
| <span data-ttu-id="6c817-131">-lt</span><span class="sxs-lookup"><span data-stu-id="6c817-131">-lt</span></span>                 | <span data-ttu-id="6c817-132">Меньше</span><span class="sxs-lookup"><span data-stu-id="6c817-132">Is less than</span></span>                               | <span data-ttu-id="6c817-133">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="6c817-133">1 -lt 2</span></span>                      |
| <span data-ttu-id="6c817-134">-le</span><span class="sxs-lookup"><span data-stu-id="6c817-134">-le</span></span>                 | <span data-ttu-id="6c817-135">Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="6c817-135">Is less than or equal to</span></span>                   | <span data-ttu-id="6c817-136">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="6c817-136">1 -le 2</span></span>                      |
| <span data-ttu-id="6c817-137">-gt</span><span class="sxs-lookup"><span data-stu-id="6c817-137">-gt</span></span>                 | <span data-ttu-id="6c817-138">Больше</span><span class="sxs-lookup"><span data-stu-id="6c817-138">Is greater than</span></span>                            | <span data-ttu-id="6c817-139">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="6c817-139">2 -gt 1</span></span>                      |
| <span data-ttu-id="6c817-140">-ge</span><span class="sxs-lookup"><span data-stu-id="6c817-140">-ge</span></span>                 | <span data-ttu-id="6c817-141">Больше или равно</span><span class="sxs-lookup"><span data-stu-id="6c817-141">Is greater than or equal to</span></span>                | <span data-ttu-id="6c817-142">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="6c817-142">2 -ge 1</span></span>                      |
| <span data-ttu-id="6c817-143">-like</span><span class="sxs-lookup"><span data-stu-id="6c817-143">-like</span></span>               | <span data-ttu-id="6c817-144">сравнение на совпадение с учетом подстановочного знака в тексте</span><span class="sxs-lookup"><span data-stu-id="6c817-144">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="6c817-145">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="6c817-145">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="6c817-146">-notlike</span><span class="sxs-lookup"><span data-stu-id="6c817-146">-notlike</span></span>            | <span data-ttu-id="6c817-147">сравнение на несовпадение с учетом подстановочного знака в тексте</span><span class="sxs-lookup"><span data-stu-id="6c817-147">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="6c817-148">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="6c817-148">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="6c817-149">-contains</span><span class="sxs-lookup"><span data-stu-id="6c817-149">-contains</span></span>           | <span data-ttu-id="6c817-150">Содержит</span><span class="sxs-lookup"><span data-stu-id="6c817-150">Contains</span></span>                                   | <span data-ttu-id="6c817-151">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="6c817-151">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="6c817-152">-notcontains</span><span class="sxs-lookup"><span data-stu-id="6c817-152">-notcontains</span></span>        | <span data-ttu-id="6c817-153">Не содержит</span><span class="sxs-lookup"><span data-stu-id="6c817-153">Does not contain</span></span>                           | <span data-ttu-id="6c817-154">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="6c817-154">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="6c817-155">В блоках сценариев командлета `Where-Object` для обращения к текущему объекту конвейера используется специальная переменная `$_`.</span><span class="sxs-lookup"><span data-stu-id="6c817-155">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="6c817-156">Ниже приведен пример использования этой переменной.</span><span class="sxs-lookup"><span data-stu-id="6c817-156">Here is an example of how it works.</span></span> <span data-ttu-id="6c817-157">Если в списке содержатся числа и требуется вернуть только те, которые меньше 3, в командлете `Where-Object` можно настроить фильтр чисел:</span><span class="sxs-lookup"><span data-stu-id="6c817-157">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="6c817-158">Фильтрация, основанная на свойствах объектов</span><span class="sxs-lookup"><span data-stu-id="6c817-158">Filtering Based on Object Properties</span></span>

<span data-ttu-id="6c817-159">Так как переменная `$_` ссылается на текущий объект конвейера, для выполнения проверок можно обратиться к ее свойствам.</span><span class="sxs-lookup"><span data-stu-id="6c817-159">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="6c817-160">Например, в инструментарии WMI можно просмотреть класс **Win32_SystemDriver** .</span><span class="sxs-lookup"><span data-stu-id="6c817-160">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="6c817-161">В какой-то конкретной системе могут содержаться сотни системных драйверов, но для проверки необходим определенный набор системных драйверов — таких, которые запущены в данный момент.</span><span class="sxs-lookup"><span data-stu-id="6c817-161">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="6c817-162">Для класса **Win32_SystemDriver** соответствующим свойством является **State** .</span><span class="sxs-lookup"><span data-stu-id="6c817-162">For the **Win32_SystemDriver** class the relevant property is **State** .</span></span> <span data-ttu-id="6c817-163">Таким образом, фильтровать системные драйверы и выбирать только запущенные можно с помощью строки:</span><span class="sxs-lookup"><span data-stu-id="6c817-163">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="6c817-164">В результате будет получен длинный список.</span><span class="sxs-lookup"><span data-stu-id="6c817-164">This still produces a long list.</span></span> <span data-ttu-id="6c817-165">Чтобы отфильтровать эти драйверы для выбора только таких, запуск которых выполняется автоматически, можно проверить значение **StartMode** :</span><span class="sxs-lookup"><span data-stu-id="6c817-165">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

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

<span data-ttu-id="6c817-166">Результат выполнения этой команды содержит много ненужных сведений, поскольку драйверы, запущенные в данный момент, уже известны.</span><span class="sxs-lookup"><span data-stu-id="6c817-166">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="6c817-167">В действительности, из всех сведений на данном этапе требуется только имя и отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="6c817-167">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="6c817-168">Следующая команда включает только эти два свойства, что дает более простые выходные данные:</span><span class="sxs-lookup"><span data-stu-id="6c817-168">The following command includes only those two properties, resulting in much simpler output:</span></span>

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

<span data-ttu-id="6c817-169">Приведенная выше команда содержит два элемента `Where-Object`, но их можно объединить в один `Where-Object`, используя знак логический оператор `-and`:</span><span class="sxs-lookup"><span data-stu-id="6c817-169">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="6c817-170">Стандартные логические операторы перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6c817-170">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="6c817-171">Логический оператор</span><span class="sxs-lookup"><span data-stu-id="6c817-171">Logical Operator</span></span> |                 <span data-ttu-id="6c817-172">Значение</span><span class="sxs-lookup"><span data-stu-id="6c817-172">Meaning</span></span>                  |  <span data-ttu-id="6c817-173">Пример (возвращает значение True)</span><span class="sxs-lookup"><span data-stu-id="6c817-173">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="6c817-174">-and</span><span class="sxs-lookup"><span data-stu-id="6c817-174">-and</span></span>             | <span data-ttu-id="6c817-175">Логическое И; возвращает значение True, если оба операнда принимают значение True</span><span class="sxs-lookup"><span data-stu-id="6c817-175">Logical and; true if both sides are true</span></span> | <span data-ttu-id="6c817-176">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="6c817-176">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="6c817-177">-or</span><span class="sxs-lookup"><span data-stu-id="6c817-177">-or</span></span>              | <span data-ttu-id="6c817-178">Логическое ИЛИ; возвращает значение True, если один из операндов принимает значение True</span><span class="sxs-lookup"><span data-stu-id="6c817-178">Logical or; true if either side is true</span></span>  | <span data-ttu-id="6c817-179">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="6c817-179">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="6c817-180">-not</span><span class="sxs-lookup"><span data-stu-id="6c817-180">-not</span></span>             | <span data-ttu-id="6c817-181">Логическое НЕ; изменяет значение (True или False) на противоположное</span><span class="sxs-lookup"><span data-stu-id="6c817-181">Logical not; reverses true and false</span></span>     | <span data-ttu-id="6c817-182">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="6c817-182">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="6c817-183">Логическое НЕ; изменяет значение (True или False) на противоположное</span><span class="sxs-lookup"><span data-stu-id="6c817-183">Logical not; reverses true and false</span></span>     | <span data-ttu-id="6c817-184">\! (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="6c817-184">\!(1 -eq 2)</span></span>              |

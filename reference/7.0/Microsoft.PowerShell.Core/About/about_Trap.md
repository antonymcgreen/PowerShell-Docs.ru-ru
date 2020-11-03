---
description: Описывает ключевое слово, которое обрабатывает завершающую ошибку.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 1e5541ce45e4dea8ebe87aa76a984f7d3de8c51f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230925"
---
# <a name="about-trap"></a><span data-ttu-id="4a909-104">О ловушке</span><span class="sxs-lookup"><span data-stu-id="4a909-104">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="4a909-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="4a909-105">Short description</span></span>

<span data-ttu-id="4a909-106">Описывает ключевое слово, которое обрабатывает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="4a909-106">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="4a909-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4a909-107">Long description</span></span>

<span data-ttu-id="4a909-108">Завершающая ошибка останавливает выполнение инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a909-108">A terminating error stops a statement from running.</span></span> <span data-ttu-id="4a909-109">Если PowerShell каким-либо образом не обрабатывает завершающую ошибку, PowerShell также прекращает выполнение функции или скрипта в текущем конвейере.</span><span class="sxs-lookup"><span data-stu-id="4a909-109">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="4a909-110">На других языках, таких как C#, завершающие ошибки называются исключениями.</span><span class="sxs-lookup"><span data-stu-id="4a909-110">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="4a909-111">`trap`Ключевое слово указывает список инструкций, выполняемых при возникновении неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-111">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="4a909-112">`trap` операторы обработают завершающие ошибки следующими способами:</span><span class="sxs-lookup"><span data-stu-id="4a909-112">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="4a909-113">Отобразить ошибку после обработки `trap` блока инструкций и продолжить выполнение скрипта или функции, содержащей `trap` .</span><span class="sxs-lookup"><span data-stu-id="4a909-113">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="4a909-114">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4a909-114">This is the default behavior.</span></span>

- <span data-ttu-id="4a909-115">Отображение ошибки и прерывание выполнения скрипта или функции, содержащей `trap` оператор using, `break` в `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a909-115">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="4a909-116">Это приведет к ошибке, но продолжить выполнение скрипта или функции, содержащей, `trap` с помощью `continue` `trap` инструкции в операторе.</span><span class="sxs-lookup"><span data-stu-id="4a909-116">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="4a909-117">Список инструкций `trap` может включать несколько условий или вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="4a909-117">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="4a909-118">`trap`Может записывать журналы, условия теста или даже запускать другую программу.</span><span class="sxs-lookup"><span data-stu-id="4a909-118">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="4a909-119">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a909-119">Syntax</span></span>

<span data-ttu-id="4a909-120">`trap`Оператор имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a909-120">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="4a909-121">`trap`Инструкция включает список инструкций, которые выполняются при возникновении неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-121">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="4a909-122">`trap`Оператор состоит из `trap` ключевого слова, при необходимости за которым следует выражение типа, и блок инструкций, содержащий список инструкций, которые выполняются при перехвате ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-122">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="4a909-123">Выражение типа Уточнение типов ошибок, которые `trap` перехватываются.</span><span class="sxs-lookup"><span data-stu-id="4a909-123">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="4a909-124">Сценарий или команда может иметь несколько `trap` инструкций.</span><span class="sxs-lookup"><span data-stu-id="4a909-124">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="4a909-125">`trap` операторы могут находиться в любом месте скрипта или команды.</span><span class="sxs-lookup"><span data-stu-id="4a909-125">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="4a909-126">Перехват всех завершающих ошибок</span><span class="sxs-lookup"><span data-stu-id="4a909-126">Trapping all terminating errors</span></span>

<span data-ttu-id="4a909-127">При возникновении завершающей ошибки, которая не обрабатывается другим способом в скрипте или команде, PowerShell проверяет наличие `trap` инструкции, обрабатывающей ошибку.</span><span class="sxs-lookup"><span data-stu-id="4a909-127">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="4a909-128">Если указан `trap` оператор, PowerShell продолжит выполнение скрипта или команды в `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a909-128">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="4a909-129">Ниже приведен пример очень простой `trap` инструкции:</span><span class="sxs-lookup"><span data-stu-id="4a909-129">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="4a909-130">Эта `trap` инструкция захватывает все завершающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-130">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="4a909-131">В следующем примере функция включает строку серьезные, которая вызывает ошибку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a909-131">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="4a909-132">При выполнении этой функции возвращается следующее:</span><span class="sxs-lookup"><span data-stu-id="4a909-132">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="4a909-133">Следующий пример включает `trap` инструкцию, которая отображает ошибку с помощью `$_` автоматической переменной:</span><span class="sxs-lookup"><span data-stu-id="4a909-133">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="4a909-134">При выполнении этой версии функции возвращается следующее:</span><span class="sxs-lookup"><span data-stu-id="4a909-134">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the
name, or if a path was included, verify that the path is correct and try again.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

> [!IMPORTANT]
> <span data-ttu-id="4a909-135">`trap` операторы могут быть определены в любом месте заданной области, но всегда применяются ко всем операторам в этой области.</span><span class="sxs-lookup"><span data-stu-id="4a909-135">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="4a909-136">Во время выполнения `trap` инструкции в блоке определяются до выполнения других инструкций.</span><span class="sxs-lookup"><span data-stu-id="4a909-136">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="4a909-137">В JavaScript это называется [поднятием](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span><span class="sxs-lookup"><span data-stu-id="4a909-137">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="4a909-138">Это означает, что `trap` инструкции применяются ко всем операторам в этом блоке, даже если выполнение не было расширено до точки, в которой они определены.</span><span class="sxs-lookup"><span data-stu-id="4a909-138">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="4a909-139">Например, определение в `trap` конце скрипта и выдача ошибки в первой инструкции все еще активирует это `trap` .</span><span class="sxs-lookup"><span data-stu-id="4a909-139">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="4a909-140">Перехват конкретных ошибок</span><span class="sxs-lookup"><span data-stu-id="4a909-140">Trapping specific errors</span></span>

<span data-ttu-id="4a909-141">Сценарий или команда может иметь несколько `trap` инструкций.</span><span class="sxs-lookup"><span data-stu-id="4a909-141">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="4a909-142">`trap`Можно определить для обработки определенных ошибок.</span><span class="sxs-lookup"><span data-stu-id="4a909-142">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="4a909-143">В следующем примере показана `trap` инструкция, которая перехватывает определенную ошибку **комманднотфаундексцептион** :</span><span class="sxs-lookup"><span data-stu-id="4a909-143">The following example is a `trap` statement that traps the specific error **CommandNotFoundException** :</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="4a909-144">Если функция или скрипт встречает строку, которая не соответствует известной команде, эта `trap` инструкция выводит строку "Перехват ошибки команды".</span><span class="sxs-lookup"><span data-stu-id="4a909-144">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="4a909-145">После выполнения `trap` списка инструкций PowerShell записывает объект ошибки в поток ошибок, а затем возобновляет выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="4a909-145">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="4a909-146">PowerShell использует типы исключений .NET.</span><span class="sxs-lookup"><span data-stu-id="4a909-146">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="4a909-147">В следующем примере задается тип ошибки **System. Exception** :</span><span class="sxs-lookup"><span data-stu-id="4a909-147">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="4a909-148">Тип ошибки **комманднотфаундексцептион** наследуется от типа **System. Exception** .</span><span class="sxs-lookup"><span data-stu-id="4a909-148">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="4a909-149">Эта инструкция захватывает ошибку, созданную неизвестной командой.</span><span class="sxs-lookup"><span data-stu-id="4a909-149">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="4a909-150">Он также выполняет треппинг других типов ошибок.</span><span class="sxs-lookup"><span data-stu-id="4a909-150">It also traps other error types.</span></span>

<span data-ttu-id="4a909-151">В скрипте может быть несколько `trap` операторов.</span><span class="sxs-lookup"><span data-stu-id="4a909-151">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="4a909-152">Каждый тип ошибки может быть перехвачен только одной `trap` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="4a909-152">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="4a909-153">При возникновении неустранимой ошибки PowerShell ищет объект `trap` с наиболее конкретным совпадением, начиная с текущей области выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a909-153">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="4a909-154">Следующий пример скрипта содержит ошибку.</span><span class="sxs-lookup"><span data-stu-id="4a909-154">The following script example contains an error.</span></span> <span data-ttu-id="4a909-155">Скрипт включает в себя общий `trap` оператор, который захватывает все завершающие ошибки и определенную `trap` инструкцию, указывающую тип **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="4a909-155">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="4a909-156">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="4a909-156">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString:
Line |
   5 |  nonsenseString
     |  ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="4a909-157">Так как PowerShell не распознает "Нонсенсестринг" как командлет или другой элемент, он возвращает ошибку **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="4a909-157">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="4a909-158">Эта завершающая ошибка захватывается конкретной `trap` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="4a909-158">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="4a909-159">Следующий пример скрипта содержит те же `trap` инструкции с другой ошибкой:</span><span class="sxs-lookup"><span data-stu-id="4a909-159">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="4a909-160">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="4a909-160">Running this script produces the following result:</span></span>

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="4a909-161">Попытка деления на ноль не приводит к созданию ошибки **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="4a909-161">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="4a909-162">Вместо этого эта ошибка перехвачена другой `trap` инструкцией, которая перехватывает все завершающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-162">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="4a909-163">Перехват ошибок и области действия</span><span class="sxs-lookup"><span data-stu-id="4a909-163">Trapping errors and scope</span></span>

<span data-ttu-id="4a909-164">Если завершающая ошибка возникает в той же области, что и `trap` инструкция, то PowerShell выполняет список инструкций, определенных `trap` .</span><span class="sxs-lookup"><span data-stu-id="4a909-164">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="4a909-165">Выполнение продолжится в операторе после ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-165">Execution continues at the statement after the error.</span></span> <span data-ttu-id="4a909-166">Если `trap` инструкция находится в области, отличной от ошибки, выполнение переходит к следующему оператору, который находится в той же области, что и `trap` инструкция.</span><span class="sxs-lookup"><span data-stu-id="4a909-166">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="4a909-167">Например, если в функции возникает ошибка, а `trap` оператор находится в функции, скрипт переходит к следующему оператору.</span><span class="sxs-lookup"><span data-stu-id="4a909-167">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="4a909-168">Следующий скрипт содержит ошибку и `trap` инструкцию:</span><span class="sxs-lookup"><span data-stu-id="4a909-168">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="4a909-169">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="4a909-169">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   3 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
function1 was completed
```

<span data-ttu-id="4a909-170">`trap`Инструкция в функции перехватывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="4a909-170">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="4a909-171">После отображения сообщения PowerShell возобновляет выполнение функции.</span><span class="sxs-lookup"><span data-stu-id="4a909-171">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="4a909-172">Обратите внимание, что `Function1` выполнено.</span><span class="sxs-lookup"><span data-stu-id="4a909-172">Note that `Function1` was completed.</span></span>

<span data-ttu-id="4a909-173">Сравните это со следующим примером, который содержит ту же ошибку и `trap` оператор.</span><span class="sxs-lookup"><span data-stu-id="4a909-173">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="4a909-174">В этом примере `trap` оператор выполняется за пределами функции:</span><span class="sxs-lookup"><span data-stu-id="4a909-174">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="4a909-175">Выполнение `Function2` функции приведет к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="4a909-175">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   2 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="4a909-176">В этом примере команда "функция2 WAS" не была выполнена.</span><span class="sxs-lookup"><span data-stu-id="4a909-176">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="4a909-177">В обоих примерах завершающая ошибка возникает в функции.</span><span class="sxs-lookup"><span data-stu-id="4a909-177">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="4a909-178">Однако в этом примере `trap` оператор находится за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="4a909-178">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="4a909-179">PowerShell не выполняет возврат в функцию после `trap` выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a909-179">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="4a909-180">Если для одного и того же условия ошибки определено несколько ловушек, `trap` используется первая определенная лексическая (самая высокая в области).</span><span class="sxs-lookup"><span data-stu-id="4a909-180">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="4a909-181">В следующем примере `trap` выполняется только с параметром "whoops 1".</span><span class="sxs-lookup"><span data-stu-id="4a909-181">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="4a909-182">Оператор Trap ограничивает область, в которой она компилируется.</span><span class="sxs-lookup"><span data-stu-id="4a909-182">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="4a909-183">Если у вас есть `trap` оператор внутри функции или скрипта с точкой, находящегося в исходной среде, то при выходе из функции или сценария с источником точки все `trap` инструкции внутри удаляются.</span><span class="sxs-lookup"><span data-stu-id="4a909-183">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="4a909-184">Использование ключевых слов BREAK и Continue</span><span class="sxs-lookup"><span data-stu-id="4a909-184">Using the break and continue keywords</span></span>

<span data-ttu-id="4a909-185">Можно использовать `break` `continue` Ключевые слова и в инструкции, `trap` чтобы определить, продолжится ли выполнение скрипта или команды после завершающей ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a909-185">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="4a909-186">Если включить `break` инструкцию в `trap` список операторов, PowerShell остановит функцию или скрипт.</span><span class="sxs-lookup"><span data-stu-id="4a909-186">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="4a909-187">В следующем примере функции используется `break` ключевое слово в `trap` операторе:</span><span class="sxs-lookup"><span data-stu-id="4a909-187">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
ParentContainsErrorRecordException:
Line |
   6 |      1/$null
     |      ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="4a909-188">Так как `trap` инструкция включала `break` ключевое слово, она не запускается, а строка "функция завершена" не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4a909-188">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="4a909-189">Если включить `continue` в инструкцию ключевое слово `trap` , PowerShell возобновит работу после инструкции, которая вызвала ошибку, так же, как если бы она не была `break` `continue` .</span><span class="sxs-lookup"><span data-stu-id="4a909-189">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="4a909-190">Однако при использовании `continue` ключевого слова PowerShell не записывает ошибку в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="4a909-190">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="4a909-191">В следующем примере функции используется `continue` ключевое слово в `trap` операторе:</span><span class="sxs-lookup"><span data-stu-id="4a909-191">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

<span data-ttu-id="4a909-192">Функция возобновляется после перехвата ошибки и выполнения инструкции function Completed.</span><span class="sxs-lookup"><span data-stu-id="4a909-192">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="4a909-193">Ошибки в потоке ошибок не записываются.</span><span class="sxs-lookup"><span data-stu-id="4a909-193">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="4a909-194">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a909-194">Notes</span></span>

<span data-ttu-id="4a909-195">`trap` операторы предоставляют простой способ для широкого обеспечения обработки всех завершающих ошибок в области.</span><span class="sxs-lookup"><span data-stu-id="4a909-195">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="4a909-196">Для более детализированной обработки ошибок используйте `try` / `catch` блоки, в которых ловушки определяются с помощью `catch` инструкций.</span><span class="sxs-lookup"><span data-stu-id="4a909-196">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="4a909-197">`catch`Инструкции применяются только к коду внутри связанной `try` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a909-197">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="4a909-198">Дополнительные сведения см. в разделе [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span><span class="sxs-lookup"><span data-stu-id="4a909-198">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a909-199">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4a909-199">See also</span></span>

[<span data-ttu-id="4a909-200">about_Break</span><span class="sxs-lookup"><span data-stu-id="4a909-200">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="4a909-201">about_Continue</span><span class="sxs-lookup"><span data-stu-id="4a909-201">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="4a909-202">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="4a909-202">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="4a909-203">about_Throw</span><span class="sxs-lookup"><span data-stu-id="4a909-203">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="4a909-204">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="4a909-204">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

---
description: Описывает ключевое слово, которое обрабатывает завершающую ошибку.
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 30b03235cbc2338de3786e37416d1c1ce1d660e3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602287"
---
# <a name="about-trap"></a><span data-ttu-id="34215-103">О ловушке</span><span class="sxs-lookup"><span data-stu-id="34215-103">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="34215-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="34215-104">Short description</span></span>

<span data-ttu-id="34215-105">Описывает ключевое слово, которое обрабатывает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="34215-105">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="34215-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="34215-106">Long description</span></span>

<span data-ttu-id="34215-107">Завершающая ошибка останавливает выполнение инструкции.</span><span class="sxs-lookup"><span data-stu-id="34215-107">A terminating error stops a statement from running.</span></span> <span data-ttu-id="34215-108">Если PowerShell каким-либо образом не обрабатывает завершающую ошибку, PowerShell также прекращает выполнение функции или скрипта в текущем конвейере.</span><span class="sxs-lookup"><span data-stu-id="34215-108">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="34215-109">На других языках, таких как C#, завершающие ошибки называются исключениями.</span><span class="sxs-lookup"><span data-stu-id="34215-109">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="34215-110">`trap`Ключевое слово указывает список инструкций, выполняемых при возникновении неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-110">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="34215-111">`trap` операторы обработают завершающие ошибки следующими способами:</span><span class="sxs-lookup"><span data-stu-id="34215-111">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="34215-112">Отобразить ошибку после обработки `trap` блока инструкций и продолжить выполнение скрипта или функции, содержащей `trap` .</span><span class="sxs-lookup"><span data-stu-id="34215-112">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="34215-113">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34215-113">This is the default behavior.</span></span>

- <span data-ttu-id="34215-114">Отображение ошибки и прерывание выполнения скрипта или функции, содержащей `trap` оператор using, `break` в `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="34215-114">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="34215-115">Это приведет к ошибке, но продолжить выполнение скрипта или функции, содержащей, `trap` с помощью `continue` `trap` инструкции в операторе.</span><span class="sxs-lookup"><span data-stu-id="34215-115">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="34215-116">Список инструкций `trap` может включать несколько условий или вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="34215-116">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="34215-117">`trap`Может записывать журналы, условия теста или даже запускать другую программу.</span><span class="sxs-lookup"><span data-stu-id="34215-117">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="34215-118">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34215-118">Syntax</span></span>

<span data-ttu-id="34215-119">`trap`Оператор имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="34215-119">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="34215-120">`trap`Инструкция включает список инструкций, которые выполняются при возникновении неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-120">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="34215-121">`trap`Оператор состоит из `trap` ключевого слова, при необходимости за которым следует выражение типа, и блок инструкций, содержащий список инструкций, которые выполняются при перехвате ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-121">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="34215-122">Выражение типа Уточнение типов ошибок, которые `trap` перехватываются.</span><span class="sxs-lookup"><span data-stu-id="34215-122">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="34215-123">Сценарий или команда может иметь несколько `trap` инструкций.</span><span class="sxs-lookup"><span data-stu-id="34215-123">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="34215-124">`trap` операторы могут находиться в любом месте скрипта или команды.</span><span class="sxs-lookup"><span data-stu-id="34215-124">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="34215-125">Перехват всех завершающих ошибок</span><span class="sxs-lookup"><span data-stu-id="34215-125">Trapping all terminating errors</span></span>

<span data-ttu-id="34215-126">При возникновении завершающей ошибки, которая не обрабатывается другим способом в скрипте или команде, PowerShell проверяет наличие `trap` инструкции, обрабатывающей ошибку.</span><span class="sxs-lookup"><span data-stu-id="34215-126">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="34215-127">Если указан `trap` оператор, PowerShell продолжит выполнение скрипта или команды в `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="34215-127">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="34215-128">Ниже приведен пример очень простой `trap` инструкции:</span><span class="sxs-lookup"><span data-stu-id="34215-128">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="34215-129">Эта `trap` инструкция захватывает все завершающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-129">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="34215-130">В следующем примере функция включает строку серьезные, которая вызывает ошибку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="34215-130">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="34215-131">При выполнении этой функции возвращается следующее:</span><span class="sxs-lookup"><span data-stu-id="34215-131">Running this function returns the following:</span></span>

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

<span data-ttu-id="34215-132">Следующий пример включает `trap` инструкцию, которая отображает ошибку с помощью `$_` автоматической переменной:</span><span class="sxs-lookup"><span data-stu-id="34215-132">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="34215-133">При выполнении этой версии функции возвращается следующее:</span><span class="sxs-lookup"><span data-stu-id="34215-133">Running this version of the function returns the following:</span></span>

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
> <span data-ttu-id="34215-134">`trap` операторы могут быть определены в любом месте заданной области, но всегда применяются ко всем операторам в этой области.</span><span class="sxs-lookup"><span data-stu-id="34215-134">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="34215-135">Во время выполнения `trap` инструкции в блоке определяются до выполнения других инструкций.</span><span class="sxs-lookup"><span data-stu-id="34215-135">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="34215-136">В JavaScript это называется [поднятием](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span><span class="sxs-lookup"><span data-stu-id="34215-136">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="34215-137">Это означает, что `trap` инструкции применяются ко всем операторам в этом блоке, даже если выполнение не было расширено до точки, в которой они определены.</span><span class="sxs-lookup"><span data-stu-id="34215-137">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="34215-138">Например, определение в `trap` конце скрипта и выдача ошибки в первой инструкции все еще активирует это `trap` .</span><span class="sxs-lookup"><span data-stu-id="34215-138">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="34215-139">Перехват конкретных ошибок</span><span class="sxs-lookup"><span data-stu-id="34215-139">Trapping specific errors</span></span>

<span data-ttu-id="34215-140">Сценарий или команда может иметь несколько `trap` инструкций.</span><span class="sxs-lookup"><span data-stu-id="34215-140">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="34215-141">`trap`Можно определить для обработки определенных ошибок.</span><span class="sxs-lookup"><span data-stu-id="34215-141">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="34215-142">В следующем примере показана `trap` инструкция, которая перехватывает определенную ошибку **комманднотфаундексцептион**:</span><span class="sxs-lookup"><span data-stu-id="34215-142">The following example is a `trap` statement that traps the specific error **CommandNotFoundException**:</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="34215-143">Если функция или скрипт встречает строку, которая не соответствует известной команде, эта `trap` инструкция выводит строку "Перехват ошибки команды".</span><span class="sxs-lookup"><span data-stu-id="34215-143">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="34215-144">После выполнения `trap` списка инструкций PowerShell записывает объект ошибки в поток ошибок, а затем возобновляет выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="34215-144">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="34215-145">PowerShell использует типы исключений .NET.</span><span class="sxs-lookup"><span data-stu-id="34215-145">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="34215-146">В следующем примере задается тип ошибки **System. Exception** :</span><span class="sxs-lookup"><span data-stu-id="34215-146">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="34215-147">Тип ошибки **комманднотфаундексцептион** наследуется от типа **System. Exception** .</span><span class="sxs-lookup"><span data-stu-id="34215-147">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="34215-148">Эта инструкция захватывает ошибку, созданную неизвестной командой.</span><span class="sxs-lookup"><span data-stu-id="34215-148">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="34215-149">Он также выполняет треппинг других типов ошибок.</span><span class="sxs-lookup"><span data-stu-id="34215-149">It also traps other error types.</span></span>

<span data-ttu-id="34215-150">В скрипте может быть несколько `trap` операторов.</span><span class="sxs-lookup"><span data-stu-id="34215-150">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="34215-151">Каждый тип ошибки может быть перехвачен только одной `trap` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="34215-151">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="34215-152">При возникновении неустранимой ошибки PowerShell ищет объект `trap` с наиболее конкретным совпадением, начиная с текущей области выполнения.</span><span class="sxs-lookup"><span data-stu-id="34215-152">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="34215-153">Следующий пример скрипта содержит ошибку.</span><span class="sxs-lookup"><span data-stu-id="34215-153">The following script example contains an error.</span></span> <span data-ttu-id="34215-154">Скрипт включает в себя общий `trap` оператор, который захватывает все завершающие ошибки и определенную `trap` инструкцию, указывающую тип **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="34215-154">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="34215-155">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="34215-155">Running this script produces the following result:</span></span>

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

<span data-ttu-id="34215-156">Так как PowerShell не распознает "Нонсенсестринг" как командлет или другой элемент, он возвращает ошибку **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="34215-156">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="34215-157">Эта завершающая ошибка захватывается конкретной `trap` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="34215-157">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="34215-158">Следующий пример скрипта содержит те же `trap` инструкции с другой ошибкой:</span><span class="sxs-lookup"><span data-stu-id="34215-158">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="34215-159">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="34215-159">Running this script produces the following result:</span></span>

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="34215-160">Попытка деления на ноль не приводит к созданию ошибки **комманднотфаундексцептион** .</span><span class="sxs-lookup"><span data-stu-id="34215-160">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="34215-161">Вместо этого эта ошибка перехвачена другой `trap` инструкцией, которая перехватывает все завершающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-161">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="34215-162">Перехват ошибок и области действия</span><span class="sxs-lookup"><span data-stu-id="34215-162">Trapping errors and scope</span></span>

<span data-ttu-id="34215-163">Если завершающая ошибка возникает в той же области, что и `trap` инструкция, то PowerShell выполняет список инструкций, определенных `trap` .</span><span class="sxs-lookup"><span data-stu-id="34215-163">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="34215-164">Выполнение продолжится в операторе после ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-164">Execution continues at the statement after the error.</span></span> <span data-ttu-id="34215-165">Если `trap` инструкция находится в области, отличной от ошибки, выполнение переходит к следующему оператору, который находится в той же области, что и `trap` инструкция.</span><span class="sxs-lookup"><span data-stu-id="34215-165">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="34215-166">Например, если в функции возникает ошибка, а `trap` оператор находится в функции, скрипт переходит к следующему оператору.</span><span class="sxs-lookup"><span data-stu-id="34215-166">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="34215-167">Следующий скрипт содержит ошибку и `trap` инструкцию:</span><span class="sxs-lookup"><span data-stu-id="34215-167">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="34215-168">Выполнение этого скрипта приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="34215-168">Running this script produces the following result:</span></span>

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

<span data-ttu-id="34215-169">`trap`Инструкция в функции перехватывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="34215-169">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="34215-170">После отображения сообщения PowerShell возобновляет выполнение функции.</span><span class="sxs-lookup"><span data-stu-id="34215-170">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="34215-171">Обратите внимание, что `Function1` выполнено.</span><span class="sxs-lookup"><span data-stu-id="34215-171">Note that `Function1` was completed.</span></span>

<span data-ttu-id="34215-172">Сравните это со следующим примером, который содержит ту же ошибку и `trap` оператор.</span><span class="sxs-lookup"><span data-stu-id="34215-172">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="34215-173">В этом примере `trap` оператор выполняется за пределами функции:</span><span class="sxs-lookup"><span data-stu-id="34215-173">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="34215-174">Выполнение `Function2` функции приведет к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="34215-174">Running the `Function2` function produces the following result:</span></span>

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

<span data-ttu-id="34215-175">В этом примере команда "функция2 WAS" не была выполнена.</span><span class="sxs-lookup"><span data-stu-id="34215-175">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="34215-176">В обоих примерах завершающая ошибка возникает в функции.</span><span class="sxs-lookup"><span data-stu-id="34215-176">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="34215-177">Однако в этом примере `trap` оператор находится за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="34215-177">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="34215-178">PowerShell не выполняет возврат в функцию после `trap` выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="34215-178">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="34215-179">Если для одного и того же условия ошибки определено несколько ловушек, `trap` используется первая определенная лексическая (самая высокая в области).</span><span class="sxs-lookup"><span data-stu-id="34215-179">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="34215-180">В следующем примере `trap` выполняется только с параметром "whoops 1".</span><span class="sxs-lookup"><span data-stu-id="34215-180">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="34215-181">Оператор Trap ограничивает область, в которой она компилируется.</span><span class="sxs-lookup"><span data-stu-id="34215-181">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="34215-182">Если у вас есть `trap` оператор внутри функции или скрипта с точкой, находящегося в исходной среде, то при выходе из функции или сценария с источником точки все `trap` инструкции внутри удаляются.</span><span class="sxs-lookup"><span data-stu-id="34215-182">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="34215-183">Использование ключевых слов BREAK и Continue</span><span class="sxs-lookup"><span data-stu-id="34215-183">Using the break and continue keywords</span></span>

<span data-ttu-id="34215-184">Можно использовать `break` `continue` Ключевые слова и в инструкции, `trap` чтобы определить, продолжится ли выполнение скрипта или команды после завершающей ошибки.</span><span class="sxs-lookup"><span data-stu-id="34215-184">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="34215-185">Если включить `break` инструкцию в `trap` список операторов, PowerShell остановит функцию или скрипт.</span><span class="sxs-lookup"><span data-stu-id="34215-185">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="34215-186">В следующем примере функции используется `break` ключевое слово в `trap` операторе:</span><span class="sxs-lookup"><span data-stu-id="34215-186">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

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

<span data-ttu-id="34215-187">Так как `trap` инструкция включала `break` ключевое слово, она не запускается, а строка "функция завершена" не выполняется.</span><span class="sxs-lookup"><span data-stu-id="34215-187">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="34215-188">Если включить `continue` в инструкцию ключевое слово `trap` , PowerShell возобновит работу после инструкции, которая вызвала ошибку, так же, как если бы она не была `break` `continue` .</span><span class="sxs-lookup"><span data-stu-id="34215-188">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="34215-189">Однако при использовании `continue` ключевого слова PowerShell не записывает ошибку в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="34215-189">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="34215-190">В следующем примере функции используется `continue` ключевое слово в `trap` операторе:</span><span class="sxs-lookup"><span data-stu-id="34215-190">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

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

<span data-ttu-id="34215-191">Функция возобновляется после перехвата ошибки и выполнения инструкции function Completed.</span><span class="sxs-lookup"><span data-stu-id="34215-191">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="34215-192">Ошибки в потоке ошибок не записываются.</span><span class="sxs-lookup"><span data-stu-id="34215-192">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="34215-193">Примечания</span><span class="sxs-lookup"><span data-stu-id="34215-193">Notes</span></span>

<span data-ttu-id="34215-194">`trap` операторы предоставляют простой способ для широкого обеспечения обработки всех завершающих ошибок в области.</span><span class="sxs-lookup"><span data-stu-id="34215-194">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="34215-195">Для более детализированной обработки ошибок используйте `try` / `catch` блоки, в которых ловушки определяются с помощью `catch` инструкций.</span><span class="sxs-lookup"><span data-stu-id="34215-195">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="34215-196">`catch`Инструкции применяются только к коду внутри связанной `try` инструкции.</span><span class="sxs-lookup"><span data-stu-id="34215-196">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="34215-197">Дополнительные сведения см. в разделе [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span><span class="sxs-lookup"><span data-stu-id="34215-197">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34215-198">См. также</span><span class="sxs-lookup"><span data-stu-id="34215-198">See also</span></span>

[<span data-ttu-id="34215-199">about_Break</span><span class="sxs-lookup"><span data-stu-id="34215-199">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="34215-200">about_Continue</span><span class="sxs-lookup"><span data-stu-id="34215-200">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="34215-201">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="34215-201">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="34215-202">about_Throw</span><span class="sxs-lookup"><span data-stu-id="34215-202">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="34215-203">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="34215-203">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

---
description: Описывает использование `Try` `Catch` блоков, и `Finally` для управления завершающими ошибками.
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: c93fa69e3badd7777950a850dfe81b79f9197f68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601295"
---
# <a name="about-try-catch-finally"></a><span data-ttu-id="853d3-103">О программе try catch finally</span><span class="sxs-lookup"><span data-stu-id="853d3-103">About Try Catch Finally</span></span>

## <a name="short-description"></a><span data-ttu-id="853d3-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="853d3-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="853d3-105">Описывает использование `Try` `Catch` блоков, и `Finally` для управления завершающими ошибками.</span><span class="sxs-lookup"><span data-stu-id="853d3-105">Describes how to use the `Try`, `Catch`, and `Finally` blocks to handle terminating errors.</span></span>

## <a name="long-description"></a><span data-ttu-id="853d3-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="853d3-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="853d3-107">Используйте `Try` `Catch` блоки, и, `Finally` чтобы реагировать на ошибки в скриптах или обрабатывать их.</span><span class="sxs-lookup"><span data-stu-id="853d3-107">Use `Try`, `Catch`, and `Finally` blocks to respond to or handle terminating errors in scripts.</span></span> <span data-ttu-id="853d3-108">Эту `Trap` инструкцию также можно использовать для управления завершающими ошибками в скриптах.</span><span class="sxs-lookup"><span data-stu-id="853d3-108">The `Trap` statement can also be used to handle terminating errors in scripts.</span></span> <span data-ttu-id="853d3-109">Дополнительные сведения см. в разделе [about_Trap](about_Trap.md).</span><span class="sxs-lookup"><span data-stu-id="853d3-109">For more information, see [about_Trap](about_Trap.md).</span></span>

<span data-ttu-id="853d3-110">Завершающая ошибка останавливает выполнение инструкции.</span><span class="sxs-lookup"><span data-stu-id="853d3-110">A terminating error stops a statement from running.</span></span> <span data-ttu-id="853d3-111">Если PowerShell не обрабатывает завершающую ошибку каким-либо образом, PowerShell также прекращает выполнение функции или скрипта с помощью текущего конвейера.</span><span class="sxs-lookup"><span data-stu-id="853d3-111">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script using the current pipeline.</span></span> <span data-ttu-id="853d3-112">На других языках, таких как C \# , завершающие ошибки называются исключениями.</span><span class="sxs-lookup"><span data-stu-id="853d3-112">In other languages, such as C\#, terminating errors are referred to as exceptions.</span></span>

<span data-ttu-id="853d3-113">Используйте `Try` блок, чтобы определить раздел скрипта, в котором PowerShell должен отслеживать ошибки.</span><span class="sxs-lookup"><span data-stu-id="853d3-113">Use the `Try` block to define a section of a script in which you want PowerShell to monitor for errors.</span></span> <span data-ttu-id="853d3-114">При возникновении ошибки в `Try` блоке ошибка сначала сохраняется в `$Error` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="853d3-114">When an error occurs within the `Try` block, the error is first saved to the `$Error` automatic variable.</span></span> <span data-ttu-id="853d3-115">Затем PowerShell выполняет поиск `Catch` блока, обрабатывающего ошибку.</span><span class="sxs-lookup"><span data-stu-id="853d3-115">PowerShell then searches for a `Catch` block to handle the error.</span></span> <span data-ttu-id="853d3-116">Если `Try` инструкция не имеет соответствующего `Catch` блока, PowerShell продолжит поиск соответствующего `Catch` блока или `Trap` оператора в родительских областях.</span><span class="sxs-lookup"><span data-stu-id="853d3-116">If the `Try` statement does not have a matching `Catch` block, PowerShell continues to search for an appropriate `Catch` block or `Trap` statement in the parent scopes.</span></span> <span data-ttu-id="853d3-117">После `Catch` завершения блока или в случае, если соответствующий `Catch` блок или `Trap` инструкция не найдены, `Finally` выполняется блок.</span><span class="sxs-lookup"><span data-stu-id="853d3-117">After a `Catch` block is completed or if no appropriate `Catch` block or `Trap` statement is found, the `Finally` block is run.</span></span> <span data-ttu-id="853d3-118">Если ошибка не может быть обработана, эта ошибка записывается в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="853d3-118">If the error cannot be handled, the error is written to the error stream.</span></span>

<span data-ttu-id="853d3-119">`Catch`Блок может включать команды для отслеживания ошибки или для восстановления ожидаемого потока скрипта.</span><span class="sxs-lookup"><span data-stu-id="853d3-119">A `Catch` block can include commands for tracking the error or for recovering the expected flow of the script.</span></span> <span data-ttu-id="853d3-120">`Catch`Блок может указывать, какие типы ошибок перехватываются.</span><span class="sxs-lookup"><span data-stu-id="853d3-120">A `Catch` block can specify which error types it catches.</span></span> <span data-ttu-id="853d3-121">`Try`Инструкция может включать несколько `Catch` блоков для различных типов ошибок.</span><span class="sxs-lookup"><span data-stu-id="853d3-121">A `Try` statement can include multiple `Catch` blocks for different kinds of errors.</span></span>

<span data-ttu-id="853d3-122">`Finally`Блок можно использовать для высвобождения ресурсов, которые больше не нужны для скрипта.</span><span class="sxs-lookup"><span data-stu-id="853d3-122">A `Finally` block can be used to free any resources that are no longer needed by your script.</span></span>

<span data-ttu-id="853d3-123">`Try`, `Catch` и `Finally` похожи на `Try` `Catch` Ключевые слова, и, `Finally` используемые в \# языке программирования C.</span><span class="sxs-lookup"><span data-stu-id="853d3-123">`Try`, `Catch`, and `Finally` resemble the `Try`, `Catch`, and `Finally` keywords used in the C\# programming language.</span></span>

### <a name="syntax"></a><span data-ttu-id="853d3-124">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="853d3-124">SYNTAX</span></span>

<span data-ttu-id="853d3-125">`Try`Оператор содержит `Try` блок, ноль или более `Catch` блоков, а также ноль или один `Finally` блок.</span><span class="sxs-lookup"><span data-stu-id="853d3-125">A `Try` statement contains a `Try` block, zero or more `Catch` blocks, and zero or one `Finally` block.</span></span> <span data-ttu-id="853d3-126">`Try`Оператор должен иметь по крайней мере один `Catch` блок или один `Finally` блок.</span><span class="sxs-lookup"><span data-stu-id="853d3-126">A `Try` statement must have at least one `Catch` block or one `Finally` block.</span></span>

<span data-ttu-id="853d3-127">Ниже показан `Try` Синтаксис блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-127">The following shows the `Try` block syntax:</span></span>

```powershell
try {<statement list>}
```

<span data-ttu-id="853d3-128">`Try`За ключевым словом следует список операторов в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="853d3-128">The `Try` keyword is followed by a statement list in braces.</span></span> <span data-ttu-id="853d3-129">Если при выполнении инструкций в списке инструкций выполняется завершающая ошибка, скрипт передает объект ошибки из `Try` блока в соответствующий `Catch` блок.</span><span class="sxs-lookup"><span data-stu-id="853d3-129">If a terminating error occurs while the statements in the statement list are being run, the script passes the error object from the `Try` block to an appropriate `Catch` block.</span></span>

<span data-ttu-id="853d3-130">Ниже показан `Catch` Синтаксис блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-130">The following shows the `Catch` block syntax:</span></span>

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

<span data-ttu-id="853d3-131">Типы ошибок отображаются в квадратных скобках.</span><span class="sxs-lookup"><span data-stu-id="853d3-131">Error types appear in brackets.</span></span> <span data-ttu-id="853d3-132">Внешняя скобка указывает, что элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="853d3-132">The outermost brackets indicate the element is optional.</span></span>

<span data-ttu-id="853d3-133">`Catch`За ключевым словом следует необязательный список спецификаций типов ошибок и список инструкций.</span><span class="sxs-lookup"><span data-stu-id="853d3-133">The `Catch` keyword is followed by an optional list of error type specifications and a statement list.</span></span> <span data-ttu-id="853d3-134">Если в блоке возникает неустранимая ошибка `Try` , PowerShell выполняет поиск соответствующего `Catch` блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-134">If a terminating error occurs in the `Try` block, PowerShell searches for an appropriate `Catch` block.</span></span> <span data-ttu-id="853d3-135">Если он найден, выполняются инструкции в `Catch` блоке.</span><span class="sxs-lookup"><span data-stu-id="853d3-135">If one is found, the statements in the `Catch` block are executed.</span></span>

<span data-ttu-id="853d3-136">`Catch`Блок может указывать один или несколько типов ошибок.</span><span class="sxs-lookup"><span data-stu-id="853d3-136">The `Catch` block can specify one or more error types.</span></span> <span data-ttu-id="853d3-137">Тип ошибки является исключением Microsoft .NET Framework или исключением, производным от исключения платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="853d3-137">An error type is a Microsoft .NET Framework exception or an exception that is derived from a .NET Framework exception.</span></span> <span data-ttu-id="853d3-138">`Catch`Блок обрабатывает ошибки указанного платформа .NET Framework класса исключений или любого класса, производного от указанного класса.</span><span class="sxs-lookup"><span data-stu-id="853d3-138">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span>

<span data-ttu-id="853d3-139">Если `Catch` блок указывает тип ошибки, этот `Catch` блок обрабатывает этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="853d3-139">If a `Catch` block specifies an error type, that `Catch` block handles that type of error.</span></span> <span data-ttu-id="853d3-140">Если в `Catch` блоке не указан тип ошибки, этот `Catch` блок обрабатывает все ошибки, обнаруженные в `Try` блоке.</span><span class="sxs-lookup"><span data-stu-id="853d3-140">If a `Catch` block does not specify an error type, that `Catch` block handles any error encountered in the `Try` block.</span></span> <span data-ttu-id="853d3-141">`Try`Инструкция может включать несколько `Catch` блоков для различных указанных типов ошибок.</span><span class="sxs-lookup"><span data-stu-id="853d3-141">A `Try` statement can include multiple `Catch` blocks for the different specified error types.</span></span>

<span data-ttu-id="853d3-142">Ниже показан `Finally` Синтаксис блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-142">The following shows the `Finally` block syntax:</span></span>

```powershell
finally {<statement list>}
```

<span data-ttu-id="853d3-143">`Finally`За ключевым словом следует список операторов, который выполняется каждый раз при выполнении скрипта, даже если `Try` Инструкция выполнена без ошибок или в инструкции обнаружена ошибка `Catch` .</span><span class="sxs-lookup"><span data-stu-id="853d3-143">The `Finally` keyword is followed by a statement list that runs every time the script is run, even if the `Try` statement ran without error or an error was caught in a `Catch` statement.</span></span>

<span data-ttu-id="853d3-144">Обратите внимание, что нажатие клавиши <kbd>CTRL</kbd> + <kbd>C</kbd> останавливает конвейер.</span><span class="sxs-lookup"><span data-stu-id="853d3-144">Note that pressing <kbd>CTRL</kbd>+<kbd>C</kbd> stops the pipeline.</span></span> <span data-ttu-id="853d3-145">Объекты, отправленные в конвейер, не будут отображаться как выходные данные.</span><span class="sxs-lookup"><span data-stu-id="853d3-145">Objects that are sent to the pipeline will not be displayed as output.</span></span> <span data-ttu-id="853d3-146">Таким образом, если включить отображаемый оператор, например "выполнение блока finally", он не будет отображаться после нажатия клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>, даже если `Finally` блок был запущен.</span><span class="sxs-lookup"><span data-stu-id="853d3-146">Therefore, if you include a statement to be displayed, such as "Finally block has run", it will not be displayed after you press <kbd>CTRL</kbd>+<kbd>C</kbd>, even if the `Finally` block ran.</span></span>

### <a name="catching-errors"></a><span data-ttu-id="853d3-147">ПЕРЕХВАТ ОШИБОК</span><span class="sxs-lookup"><span data-stu-id="853d3-147">CATCHING ERRORS</span></span>

<span data-ttu-id="853d3-148">В следующем примере скрипта показан `Try` блок с `Catch` блоком:</span><span class="sxs-lookup"><span data-stu-id="853d3-148">The following sample script shows a `Try` block with a `Catch` block:</span></span>

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

<span data-ttu-id="853d3-149">`Catch`Ключевое слово должно следовать непосредственно за `Try` блоком или другим `Catch` блоком.</span><span class="sxs-lookup"><span data-stu-id="853d3-149">The `Catch` keyword must immediately follow the `Try` block or another `Catch` block.</span></span>

<span data-ttu-id="853d3-150">PowerShell не распознает "Нонсенсестринг" как командлет или другой элемент.</span><span class="sxs-lookup"><span data-stu-id="853d3-150">PowerShell does not recognize "NonsenseString" as a cmdlet or other item.</span></span>
<span data-ttu-id="853d3-151">Выполнение этого скрипта возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="853d3-151">Running this script returns the following result:</span></span>

```powershell
An error occurred.
```

<span data-ttu-id="853d3-152">Когда сценарий встречает "Нонсенсестринг", это приводит к завершающей ошибке.</span><span class="sxs-lookup"><span data-stu-id="853d3-152">When the script encounters "NonsenseString", it causes a terminating error.</span></span> <span data-ttu-id="853d3-153">`Catch`Блок обрабатывает ошибку, выполняя список инструкций внутри блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-153">The `Catch` block handles the error by running the statement list inside the block.</span></span>

### <a name="using-multiple-catch-statements"></a><span data-ttu-id="853d3-154">ИСПОЛЬЗОВАНИЕ НЕСКОЛЬКИХ ОПЕРАТОРОВ CATCH</span><span class="sxs-lookup"><span data-stu-id="853d3-154">USING MULTIPLE CATCH STATEMENTS</span></span>

<span data-ttu-id="853d3-155">`Try`Оператор может иметь любое количество `Catch` блоков.</span><span class="sxs-lookup"><span data-stu-id="853d3-155">A `Try` statement can have any number of `Catch` blocks.</span></span> <span data-ttu-id="853d3-156">Например, следующий сценарий содержит `Try` блок, который скачивается `MyDoc.doc` и содержит два блока `Catch` :</span><span class="sxs-lookup"><span data-stu-id="853d3-156">For example, the following script has a `Try` block that downloads `MyDoc.doc`, and it contains two `Catch` blocks:</span></span>

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

<span data-ttu-id="853d3-157">Первый `Catch` блок обрабатывает ошибки типов **System .NET., except** и **System. IO. IOException** .</span><span class="sxs-lookup"><span data-stu-id="853d3-157">The first `Catch` block handles errors of the **System.Net.WebException** and **System.IO.IOException** types.</span></span> <span data-ttu-id="853d3-158">Второй `Catch` блок не указывает тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="853d3-158">The second `Catch` block does not specify an error type.</span></span> <span data-ttu-id="853d3-159">Второй `Catch` блок обрабатывает любые другие возникающие ошибки.</span><span class="sxs-lookup"><span data-stu-id="853d3-159">The second `Catch` block handles any other terminating errors that occur.</span></span>

<span data-ttu-id="853d3-160">PowerShell сопоставляет типы ошибок путем наследования.</span><span class="sxs-lookup"><span data-stu-id="853d3-160">PowerShell matches error types by inheritance.</span></span> <span data-ttu-id="853d3-161">`Catch`Блок обрабатывает ошибки указанного платформа .NET Framework класса исключений или любого класса, производного от указанного класса.</span><span class="sxs-lookup"><span data-stu-id="853d3-161">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span> <span data-ttu-id="853d3-162">Следующий пример содержит `Catch` блок, который перехватывает ошибку "команда не найдена":</span><span class="sxs-lookup"><span data-stu-id="853d3-162">The following example contains a `Catch` block that catches a "Command Not Found" error:</span></span>

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

<span data-ttu-id="853d3-163">Указанный тип ошибки, **комманднотфаундексцептион**, наследуется от типа **темексцептионSystem.Sys** .</span><span class="sxs-lookup"><span data-stu-id="853d3-163">The specified error type, **CommandNotFoundException**, inherits from the **System.SystemException** type.</span></span> <span data-ttu-id="853d3-164">В следующем примере также перехватывается ошибка "команда не найдена":</span><span class="sxs-lookup"><span data-stu-id="853d3-164">The following example also catches a Command Not Found error:</span></span>

```powershell
catch [System.SystemException] {"Base Exception" }
```

<span data-ttu-id="853d3-165">Этот `Catch` блок обрабатывает ошибку "команда не найдена" и другие ошибки, унаследованные от типа **SystemException** .</span><span class="sxs-lookup"><span data-stu-id="853d3-165">This `Catch` block handles the "Command Not Found" error and other errors that inherit from the **SystemException** type.</span></span>

<span data-ttu-id="853d3-166">Если указать класс Error и один из его производных классов, поместите `Catch` блок для производного класса перед `Catch` блоком для общего класса.</span><span class="sxs-lookup"><span data-stu-id="853d3-166">If you specify an error class and one of its derived classes, place the `Catch` block for the derived class before the `Catch` block for the general class.</span></span>

### <a name="using-traps-in-a-try-catch"></a><span data-ttu-id="853d3-167">Использование ловушек в блоке try catch</span><span class="sxs-lookup"><span data-stu-id="853d3-167">Using Traps in a Try Catch</span></span>

<span data-ttu-id="853d3-168">При возникновении завершающей ошибки в `Try` блоке с `Trap` определенным внутри `Try` блока, даже если существует соответствующий `Catch` блок, `Trap` оператор получает управление.</span><span class="sxs-lookup"><span data-stu-id="853d3-168">When a terminating error occurs in a `Try` block with a `Trap` defined within the `Try` block, even if there is a matching `Catch` block, the `Trap` statement takes control.</span></span>

<span data-ttu-id="853d3-169">Если объект `Trap` существует в блоке более высокого уровня `Try` , чем, и в `Catch` текущей области нет соответствующего блока, то `Trap` будет принимать управление, даже если в какой-либо родительской области есть соответствующий `Catch` блок.</span><span class="sxs-lookup"><span data-stu-id="853d3-169">If a `Trap` exists at a higher block than the `Try`, and there is no matching `Catch` block within the current scope, the `Trap` will take control, even if any parent scope has a matching `Catch` block.</span></span>

### <a name="accessing-exception-information"></a><span data-ttu-id="853d3-170">ДОСТУП К СВЕДЕНИЯМ ОБ ИСКЛЮЧЕНИЯХ</span><span class="sxs-lookup"><span data-stu-id="853d3-170">ACCESSING EXCEPTION INFORMATION</span></span>

<span data-ttu-id="853d3-171">В `Catch` блоке доступ к текущей ошибке можно получить с помощью `$_` , который также называется `$PSItem` .</span><span class="sxs-lookup"><span data-stu-id="853d3-171">Within a `Catch` block, the current error can be accessed using `$_`, which is also known as `$PSItem`.</span></span> <span data-ttu-id="853d3-172">Объект имеет тип **ерроррекорд**.</span><span class="sxs-lookup"><span data-stu-id="853d3-172">The object is of type **ErrorRecord**.</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

<span data-ttu-id="853d3-173">Выполнение этого скрипта возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="853d3-173">Running this script returns the following result:</span></span>

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

<span data-ttu-id="853d3-174">Существуют дополнительные свойства, к которым можно получить доступ, например **скриптстакктраце**, **Exception** и **ErrorDetails**.</span><span class="sxs-lookup"><span data-stu-id="853d3-174">There are additional properties that can be accessed, such as **ScriptStackTrace**, **Exception**, and **ErrorDetails**.</span></span>  <span data-ttu-id="853d3-175">Например, если мы изменим сценарий следующим образом:</span><span class="sxs-lookup"><span data-stu-id="853d3-175">For example, if we change the script to the following:</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

<span data-ttu-id="853d3-176">Результат будет следующим:</span><span class="sxs-lookup"><span data-stu-id="853d3-176">The result will be similar to:</span></span>

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a><span data-ttu-id="853d3-177">ОСВОБОЖДЕНИЕ РЕСУРСОВ С ПОМОЩЬЮ FINALLY</span><span class="sxs-lookup"><span data-stu-id="853d3-177">FREEING RESOURCES BY USING FINALLY</span></span>

<span data-ttu-id="853d3-178">Чтобы освободить ресурсы, используемые сценарием, добавьте `Finally` блок после `Try` `Catch` блоков и.</span><span class="sxs-lookup"><span data-stu-id="853d3-178">To free resources used by a script, add a `Finally` block after the `Try` and `Catch` blocks.</span></span> <span data-ttu-id="853d3-179">`Finally`Операторы блока выполняются независимо от того, обнаруживает ли `Try` блок завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="853d3-179">The `Finally` block statements run regardless of whether the `Try` block encounters a terminating error.</span></span> <span data-ttu-id="853d3-180">PowerShell выполняет `Finally` блок до завершения сценария или до выхода из области действия текущего блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-180">PowerShell runs the `Finally` block before the script terminates or before the current block goes out of scope.</span></span>

<span data-ttu-id="853d3-181">`Finally`Блок выполняется, даже если для его завершения используется <kbd>сочетание клавиш CTRL</kbd> + <kbd>C</kbd> .</span><span class="sxs-lookup"><span data-stu-id="853d3-181">A `Finally` block runs even if you use <kbd>CTRL</kbd>+<kbd>C</kbd> to stop the script.</span></span> <span data-ttu-id="853d3-182">`Finally`Блок также запускается, если ключевое слово Exit останавливает скрипт из `Catch` блока.</span><span class="sxs-lookup"><span data-stu-id="853d3-182">A `Finally` block also runs if an Exit keyword stops the script from within a `Catch` block.</span></span>

### <a name="see-also"></a><span data-ttu-id="853d3-183">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="853d3-183">SEE ALSO</span></span>

[<span data-ttu-id="853d3-184">about_Break</span><span class="sxs-lookup"><span data-stu-id="853d3-184">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="853d3-185">about_Continue</span><span class="sxs-lookup"><span data-stu-id="853d3-185">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="853d3-186">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="853d3-186">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="853d3-187">about_Throw</span><span class="sxs-lookup"><span data-stu-id="853d3-187">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="853d3-188">about_Trap</span><span class="sxs-lookup"><span data-stu-id="853d3-188">about_Trap</span></span>](about_Trap.md)


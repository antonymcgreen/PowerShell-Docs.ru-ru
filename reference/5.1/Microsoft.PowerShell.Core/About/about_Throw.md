---
description: Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: caac7679e2c7ecd21b4fa9e43ab76681ee3faed5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231906"
---
# <a name="about-throw"></a><span data-ttu-id="8ddf6-104">О вызове</span><span class="sxs-lookup"><span data-stu-id="8ddf6-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="8ddf6-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8ddf6-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="8ddf6-106">Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="8ddf6-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8ddf6-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8ddf6-108">Ключевое слово Throw вызывает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="8ddf6-109">Для завершения обработки команды, функции или скрипта можно использовать ключевое слово Throw.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="8ddf6-110">Например, можно использовать ключевое слово Throw в блоке script инструкции if для ответа на условие или в блоке catch оператора try-catch-finally.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="8ddf6-111">Можно также использовать ключевое слово Throw в объявлении параметра, чтобы сделать параметр функции обязательным.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="8ddf6-112">Ключевое слово Throw может вызывать любой объект, например строку сообщения пользователя или объект, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ddf6-113">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ddf6-113">SYNTAX</span></span>

<span data-ttu-id="8ddf6-114">Синтаксис ключевого слова Throw выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ddf6-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="8ddf6-115">Выражение в синтаксисе Throw является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="8ddf6-116">Если инструкция throw не отображается в блоке catch и не содержит выражение, возникает ошибка Скрипсалтед.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

<span data-ttu-id="8ddf6-117">Если ключевое слово Throw используется в блоке catch без выражения, оно снова выдает текущий RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="8ddf6-118">Дополнительные сведения см. в разделе about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="8ddf6-119">СОЗДАНИЕ СТРОКИ</span><span class="sxs-lookup"><span data-stu-id="8ddf6-119">THROWING A STRING</span></span>

<span data-ttu-id="8ddf6-120">Необязательное выражение в операторе Throw может быть строкой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8ddf6-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="8ddf6-121">ВЫЗОВ ДРУГИХ ОБЪЕКТОВ</span><span class="sxs-lookup"><span data-stu-id="8ddf6-121">THROWING OTHER OBJECTS</span></span>

<span data-ttu-id="8ddf6-122">Выражение также может быть объектом, создающим объект, который представляет процесс PowerShell, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8ddf6-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

<span data-ttu-id="8ddf6-123">Для проверки ошибки можно использовать свойство TargetObject объекта Ерроррекорд в автоматической переменной $error.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

<span data-ttu-id="8ddf6-124">Можно также вызвать исключение объекта Ерроррекорд или Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-124">You can also throw an ErrorRecord object or a Microsoft .NET Framework exception.</span></span> <span data-ttu-id="8ddf6-125">В следующем примере используется ключевое слово Throw для создания объекта System. FormatException.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a><span data-ttu-id="8ddf6-126">ИТОГОВАЯ ОШИБКА</span><span class="sxs-lookup"><span data-stu-id="8ddf6-126">RESULTING ERROR</span></span>

<span data-ttu-id="8ddf6-127">Ключевое слово Throw может создавать объект Ерроррекорд.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="8ddf6-128">Свойство Exception объекта Ерроррекорд содержит объект RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="8ddf6-129">Оставшаяся часть объекта Ерроррекорд и объекта RuntimeException зависят от объекта, который вызывает ключевое слово Throw.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="8ddf6-130">Объект RunTimeException упаковывается в объект Ерроррекорд, а объект Ерроррекорд автоматически сохраняется в $Error автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="8ddf6-131">ИСПОЛЬЗОВАНИЕ ИНСТРУКЦИИ THROW ДЛЯ СОЗДАНИЯ ОБЯЗАТЕЛЬНОГО ПАРАМЕТРА</span><span class="sxs-lookup"><span data-stu-id="8ddf6-131">USING THROW TO CREATE A MANDATORY PARAMETER</span></span>

<span data-ttu-id="8ddf6-132">Чтобы сделать параметр функции обязательным, можно использовать ключевое слово Throw.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-132">You can use the Throw keyword to make a function parameter mandatory.</span></span>

<span data-ttu-id="8ddf6-133">Это альтернатива использованию обязательного параметра ключевого слова Parameter.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-133">This is an alternative to using the Mandatory parameter of the Parameter keyword.</span></span> <span data-ttu-id="8ddf6-134">При использовании обязательного параметра система запрашивает у пользователя требуемое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-134">When you use the Mandatory parameter, the system prompts the user for the required parameter value.</span></span> <span data-ttu-id="8ddf6-135">При использовании ключевого слова Throw команда останавливается и отображает запись об ошибке.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-135">When you use the Throw keyword, the command stops and displays the error record.</span></span>

<span data-ttu-id="8ddf6-136">Например, ключевое слово Throw в подвыражении параметра делает параметр пути обязательным параметром в функции.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-136">For example, the Throw keyword in the parameter subexpression makes the Path parameter a required parameter in the function.</span></span>

<span data-ttu-id="8ddf6-137">В этом случае ключевое слово Throw выдает строку сообщения, но она является присутствием ключевого слова Throw, создающего завершающую ошибку, если параметр path не указан.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-137">In this case, the Throw keyword throws a message string, but it is the presence of the Throw keyword that generates the terminating error if the Path parameter is not specified.</span></span> <span data-ttu-id="8ddf6-138">Выражение, следующее за throw, является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8ddf6-138">The expression that follows Throw is optional.</span></span>

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a><span data-ttu-id="8ddf6-139">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="8ddf6-139">SEE ALSO</span></span>

[<span data-ttu-id="8ddf6-140">about_Break</span><span class="sxs-lookup"><span data-stu-id="8ddf6-140">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="8ddf6-141">about_Continue</span><span class="sxs-lookup"><span data-stu-id="8ddf6-141">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="8ddf6-142">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="8ddf6-142">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="8ddf6-143">about_Trap</span><span class="sxs-lookup"><span data-stu-id="8ddf6-143">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="8ddf6-144">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="8ddf6-144">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

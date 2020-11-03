---
description: Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: d4bf0ea00145c03522d4db952be201c877c9d50c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230926"
---
# <a name="about-throw"></a><span data-ttu-id="f1064-104">О вызове</span><span class="sxs-lookup"><span data-stu-id="f1064-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="f1064-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f1064-105">Short description</span></span>
<span data-ttu-id="f1064-106">Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="f1064-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="f1064-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f1064-107">Long description</span></span>

<span data-ttu-id="f1064-108">Ключевое слово Throw вызывает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="f1064-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="f1064-109">Для завершения обработки команды, функции или скрипта можно использовать ключевое слово Throw.</span><span class="sxs-lookup"><span data-stu-id="f1064-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="f1064-110">Например, можно использовать ключевое слово Throw в блоке script инструкции if для ответа на условие или в блоке catch оператора try-catch-finally.</span><span class="sxs-lookup"><span data-stu-id="f1064-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="f1064-111">Можно также использовать ключевое слово Throw в объявлении параметра, чтобы сделать параметр функции обязательным.</span><span class="sxs-lookup"><span data-stu-id="f1064-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="f1064-112">Ключевое слово Throw может вызывать любой объект, например строку сообщения пользователя или объект, вызвавший ошибку.</span><span class="sxs-lookup"><span data-stu-id="f1064-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1064-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1064-113">Syntax</span></span>

<span data-ttu-id="f1064-114">Синтаксис ключевого слова Throw выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f1064-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="f1064-115">Выражение в синтаксисе Throw является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f1064-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="f1064-116">Если инструкция throw не отображается в блоке catch и не содержит выражение, возникает ошибка Скрипсалтед.</span><span class="sxs-lookup"><span data-stu-id="f1064-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

Exception: ScriptHalted
```

<span data-ttu-id="f1064-117">Если ключевое слово Throw используется в блоке catch без выражения, оно снова выдает текущий RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="f1064-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="f1064-118">Дополнительные сведения см. в разделе about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="f1064-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="f1064-119">Создание строки</span><span class="sxs-lookup"><span data-stu-id="f1064-119">Throwing a string</span></span>

<span data-ttu-id="f1064-120">Необязательное выражение в операторе Throw может быть строкой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f1064-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="f1064-121">Вызов других объектов</span><span class="sxs-lookup"><span data-stu-id="f1064-121">Throwing other objects</span></span>

<span data-ttu-id="f1064-122">Выражение также может быть объектом, создающим объект, который представляет процесс PowerShell, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f1064-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

<span data-ttu-id="f1064-123">Для проверки ошибки можно использовать свойство TargetObject объекта Ерроррекорд в автоматической переменной $error.</span><span class="sxs-lookup"><span data-stu-id="f1064-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

<span data-ttu-id="f1064-124">Можно также вызвать исключение объекта Ерроррекорд или исключения .NET.</span><span class="sxs-lookup"><span data-stu-id="f1064-124">You can also throw an ErrorRecord object or a .NET exception.</span></span> <span data-ttu-id="f1064-125">В следующем примере используется ключевое слово Throw для создания объекта System. FormatException.</span><span class="sxs-lookup"><span data-stu-id="f1064-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a><span data-ttu-id="f1064-126">Итоговая ошибка</span><span class="sxs-lookup"><span data-stu-id="f1064-126">The resulting error</span></span>

<span data-ttu-id="f1064-127">Ключевое слово Throw может создавать объект Ерроррекорд.</span><span class="sxs-lookup"><span data-stu-id="f1064-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="f1064-128">Свойство Exception объекта Ерроррекорд содержит объект RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="f1064-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="f1064-129">Оставшаяся часть объекта Ерроррекорд и объекта RuntimeException зависят от объекта, который вызывает ключевое слово Throw.</span><span class="sxs-lookup"><span data-stu-id="f1064-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="f1064-130">Объект RunTimeException упаковывается в объект Ерроррекорд, а объект Ерроррекорд автоматически сохраняется в $Error автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="f1064-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="f1064-131">Использование инструкции THROW для создания обязательного параметра</span><span class="sxs-lookup"><span data-stu-id="f1064-131">Using Throw to create a mandatory parameter</span></span>

<span data-ttu-id="f1064-132">В отличие от прошлых версий PowerShell, не используйте ключевое слово Throw для проверки параметров.</span><span class="sxs-lookup"><span data-stu-id="f1064-132">Unlike past versions of PowerShell, do not use the Throw keyword for parameter validation.</span></span> <span data-ttu-id="f1064-133">Правильный способ см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) .</span><span class="sxs-lookup"><span data-stu-id="f1064-133">See [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) for the correct way.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1064-134">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f1064-134">See also</span></span>

- [<span data-ttu-id="f1064-135">about_Break</span><span class="sxs-lookup"><span data-stu-id="f1064-135">about_Break</span></span>](about_Break.md)
- [<span data-ttu-id="f1064-136">about_Continue</span><span class="sxs-lookup"><span data-stu-id="f1064-136">about_Continue</span></span>](about_Continue.md)
- [<span data-ttu-id="f1064-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="f1064-137">about_Scopes</span></span>](about_Scopes.md)
- [<span data-ttu-id="f1064-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="f1064-138">about_Trap</span></span>](about_Trap.md)
- [<span data-ttu-id="f1064-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="f1064-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

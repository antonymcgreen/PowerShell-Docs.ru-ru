---
ms.date: 09/13/2016
ms.topic: reference
title: Написание справки для командлетов PowerShell
description: Написание справки для командлетов PowerShell
ms.openlocfilehash: b1deaa5998dbc54add93764db785d57afcc0a779
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658101"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="27610-103">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="27610-103">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="27610-104">Командлеты PowerShell могут быть полезными, но если в разделах справки не ясно объясняется, что делает командлет и как его использовать, командлет может не использовать или, что еще хуже, может привести к невозможности разочарования пользователей.</span><span class="sxs-lookup"><span data-stu-id="27610-104">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span> <span data-ttu-id="27610-105">Формат файлов справки по командлетам на основе XML повышает согласованность, но для получения отличной справки требуется гораздо больше.</span><span class="sxs-lookup"><span data-stu-id="27610-105">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="27610-106">Если вы никогда не написали справку по командлетам, ознакомьтесь со следующими рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="27610-106">If you have never written cmdlet Help, review the following guidelines.</span></span> <span data-ttu-id="27610-107">Схема XML, необходимая для создания раздела справки по командлету, описана в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="27610-107">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span> <span data-ttu-id="27610-108">Начните с [создания файла справки по командлету](./how-to-create-the-cmdlet-help-file.md).</span><span class="sxs-lookup"><span data-stu-id="27610-108">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span> <span data-ttu-id="27610-109">Этот раздел включает описание XML-узлов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="27610-109">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="27610-110">Рекомендации по написанию справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="27610-110">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="27610-111">Запись хорошо</span><span class="sxs-lookup"><span data-stu-id="27610-111">Write well</span></span>

<span data-ttu-id="27610-112">Ничего не заменяет хорошо написанный раздел.</span><span class="sxs-lookup"><span data-stu-id="27610-112">Nothing replaces a well-written topic.</span></span> <span data-ttu-id="27610-113">Если вы не являетесь профессиональным средством записи, найдите средство записи или редактор, которые помогут вам.</span><span class="sxs-lookup"><span data-stu-id="27610-113">If you are not a professional writer, find a writer or editor to help you.</span></span> <span data-ttu-id="27610-114">Другой вариант — скопировать текст справки в Microsoft Word и использовать проверки грамматики и орфографии для улучшения работы.</span><span class="sxs-lookup"><span data-stu-id="27610-114">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="27610-115">Писать просто</span><span class="sxs-lookup"><span data-stu-id="27610-115">Write simply</span></span>

<span data-ttu-id="27610-116">Используйте простые слова и фразы.</span><span class="sxs-lookup"><span data-stu-id="27610-116">Use simple words and phrases.</span></span> <span data-ttu-id="27610-117">Избегайте профессиональных терминов.</span><span class="sxs-lookup"><span data-stu-id="27610-117">Avoid jargon.</span></span> <span data-ttu-id="27610-118">Учтите, что многие читатели оснащены только словарем на иностранном языке и вашим разделом справки.</span><span class="sxs-lookup"><span data-stu-id="27610-118">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="27610-119">Согласованная запись</span><span class="sxs-lookup"><span data-stu-id="27610-119">Write consistently</span></span>

<span data-ttu-id="27610-120">Справка по связанным командлетам должна быть похожей (например, Get-x и Set-x).</span><span class="sxs-lookup"><span data-stu-id="27610-120">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span> <span data-ttu-id="27610-121">Используйте стандартные описания для стандартных параметров, таких как **Force** и **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="27610-121">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span> <span data-ttu-id="27610-122">(Скопируйте их из справки по основным командлетам.) Используйте стандартные термины.</span><span class="sxs-lookup"><span data-stu-id="27610-122">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span> <span data-ttu-id="27610-123">Например, используйте параметр "Parameter", а не "Argument" и используйте "командлет", а не "Command" или "Command-let".</span><span class="sxs-lookup"><span data-stu-id="27610-123">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="27610-124">Запуск краткого обзорного элемента с помощью команды</span><span class="sxs-lookup"><span data-stu-id="27610-124">Start the synopsis with a verb</span></span>

<span data-ttu-id="27610-125">Поле «краткий обзор» информирует пользователя о том, что делает командлет, а не то, как он работает.</span><span class="sxs-lookup"><span data-stu-id="27610-125">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span> <span data-ttu-id="27610-126">Команды создают инструкцию на основе задачи, которая информирует пользователей, если этот командлет соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="27610-126">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span> <span data-ttu-id="27610-127">Используйте простые команды, такие как «Get», «CREATE» и «Change».</span><span class="sxs-lookup"><span data-stu-id="27610-127">Use simple verbs like "get", "create", and "change."</span></span> <span data-ttu-id="27610-128">Старайтесь избегать «Set», которые могут быть неясными и обсловными словами, например «Modify».</span><span class="sxs-lookup"><span data-stu-id="27610-128">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="27610-129">Сосредоточиться на объектах</span><span class="sxs-lookup"><span data-stu-id="27610-129">Focus on objects</span></span>

<span data-ttu-id="27610-130">Большинство командлетов Get отображают нечто, но их основная функция заключается в получении объекта.</span><span class="sxs-lookup"><span data-stu-id="27610-130">Most "get" cmdlets display something, but their primary function is to get an object.</span></span> <span data-ttu-id="27610-131">В справке Сосредоточьтесь на объекте, чтобы пользователи понимали, что по умолчанию отображается один из множества и что они могут использовать методы и свойства объекта, полученные для них различными способами.</span><span class="sxs-lookup"><span data-stu-id="27610-131">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="27610-132">Запись подробного описания</span><span class="sxs-lookup"><span data-stu-id="27610-132">Write detailed descriptions</span></span>

<span data-ttu-id="27610-133">Кратко перечислите все, что может делать командлет в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="27610-133">Briefly list everything that the cmdlet can do in the detailed description.</span></span> <span data-ttu-id="27610-134">Если функция Main должна изменить одно свойство, но командлет может изменить все свойства, перечислите его в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="27610-134">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="27610-135">Использовать стандартный синтаксис</span><span class="sxs-lookup"><span data-stu-id="27610-135">Use conventional syntax</span></span>

<span data-ttu-id="27610-136">Используйте стандартный формат Backus-Naur, который часто используется для справки командной строки Windows и UNIX.</span><span class="sxs-lookup"><span data-stu-id="27610-136">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-types-for-parameter-values"></a><span data-ttu-id="27610-137">Использование типов Microsoft .NET для значений параметров</span><span class="sxs-lookup"><span data-stu-id="27610-137">Use Microsoft .NET types for parameter values</span></span>

<span data-ttu-id="27610-138">Заполнители для значений параметров (в описании синтаксиса и параметров) показывают типы .NET Framework объектов, которые будет принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="27610-138">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span> <span data-ttu-id="27610-139">Группа разработчиков PowerShell разработала это соглашение, помогающее научить пользователей о .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="27610-139">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="27610-140">Описание параметров записи завершено</span><span class="sxs-lookup"><span data-stu-id="27610-140">Write complete parameter descriptions</span></span>

<span data-ttu-id="27610-141">Описания параметров должны информировать пользователей о двух вещах: о том, что делает параметр (его результат) и о том, что они должны вводить для значений параметров.</span><span class="sxs-lookup"><span data-stu-id="27610-141">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="27610-142">Напишите практические примеры</span><span class="sxs-lookup"><span data-stu-id="27610-142">Write practical examples</span></span>

<span data-ttu-id="27610-143">В примерах должно быть показано, как использовать все параметры, но самое важное — продемонстрировать, как использовать командлет в реальных задачах.</span><span class="sxs-lookup"><span data-stu-id="27610-143">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span> <span data-ttu-id="27610-144">Начните с простого примера и напишите все сложные примеры.</span><span class="sxs-lookup"><span data-stu-id="27610-144">Start with a simple example and write increasingly complex examples.</span></span> <span data-ttu-id="27610-145">В последнем примере показано, как использовать командлет в конвейере.</span><span class="sxs-lookup"><span data-stu-id="27610-145">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="27610-146">Использование поля "Примечания"</span><span class="sxs-lookup"><span data-stu-id="27610-146">Use the Notes field</span></span>

<span data-ttu-id="27610-147">Используйте поле Примечания для объяснения концепций, необходимых пользователям для понимания командлета.</span><span class="sxs-lookup"><span data-stu-id="27610-147">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span> <span data-ttu-id="27610-148">Также можно использовать заметки, чтобы помочь пользователям избежать распространенных ошибок.</span><span class="sxs-lookup"><span data-stu-id="27610-148">You can also use notes to help users avoid common errors.</span></span> <span data-ttu-id="27610-149">Избегайте URL-адресов при их изменении.</span><span class="sxs-lookup"><span data-stu-id="27610-149">Avoid URLs as they change.</span></span> <span data-ttu-id="27610-150">Вместо этого предоставьте пользователям условия поиска.</span><span class="sxs-lookup"><span data-stu-id="27610-150">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="27610-151">Тестирование справки</span><span class="sxs-lookup"><span data-stu-id="27610-151">Test your Help</span></span>

<span data-ttu-id="27610-152">Протестируйте справку так же, как при тестировании кода.</span><span class="sxs-lookup"><span data-stu-id="27610-152">Test the Help just like you test your code.</span></span> <span data-ttu-id="27610-153">Ваши друзья и коллеги читают содержимое справки и предоставляют отзывы.</span><span class="sxs-lookup"><span data-stu-id="27610-153">Have friends and colleagues read your Help content and provide feedback.</span></span> <span data-ttu-id="27610-154">Вы также можете запросить отзывы из групп новостей.</span><span class="sxs-lookup"><span data-stu-id="27610-154">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="27610-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="27610-155">See Also</span></span>

 [<span data-ttu-id="27610-156">Как создать файл справки командлета</span><span class="sxs-lookup"><span data-stu-id="27610-156">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="27610-157">Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-157">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-158">Добавление подробного описания в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="27610-158">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="27610-159">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-159">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-160">Добавление параметров в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="27610-160">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="27610-161">Добавление типов входных данных в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="27610-161">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-162">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-162">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-163">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-163">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-164">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-164">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-165">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="27610-165">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="27610-166">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27610-166">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

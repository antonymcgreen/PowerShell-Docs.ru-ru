---
title: Написание справки для командлетов PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55908d67-7cbe-482a-a105-5a6da93c5311
caps.latest.revision: 4
ms.openlocfilehash: 8d692cf88d1d356886ef973f0989294d6b51ee6d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083167"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="59fc6-102">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="59fc6-102">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="59fc6-103">Командлеты PowerShell может быть полезно, но если собственных разделов справки понятно объяснить, что делает командлет и способы ее использования, командлет может не использоваться, или, что еще хуже, он может разочаровать пользователей.</span><span class="sxs-lookup"><span data-stu-id="59fc6-103">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span>
<span data-ttu-id="59fc6-104">Формат файла справки командлета на основе XML улучшает согласованность, но отличный справочный требуется гораздо больше.</span><span class="sxs-lookup"><span data-stu-id="59fc6-104">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="59fc6-105">Если вы никогда не написали справки по командлетам, ознакомьтесь со следующими указаниями.</span><span class="sxs-lookup"><span data-stu-id="59fc6-105">If you have never written cmdlet Help, review the following guidelines.</span></span>
<span data-ttu-id="59fc6-106">XML-схемы, необходимые для создания раздела справки командлета описан в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="59fc6-106">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span>
<span data-ttu-id="59fc6-107">Начните с [Создание файла справки по командлетам](./how-to-create-the-cmdlet-help-file.md).</span><span class="sxs-lookup"><span data-stu-id="59fc6-107">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span>
<span data-ttu-id="59fc6-108">Этот раздел содержит описание верхнего уровня XML-узлов.</span><span class="sxs-lookup"><span data-stu-id="59fc6-108">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="59fc6-109">Записи, касающиеся справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="59fc6-109">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="59fc6-110">Также запись</span><span class="sxs-lookup"><span data-stu-id="59fc6-110">Write well</span></span>
<span data-ttu-id="59fc6-111">Ничего не заменяет правильно составленный раздела.</span><span class="sxs-lookup"><span data-stu-id="59fc6-111">Nothing replaces a well-written topic.</span></span>
<span data-ttu-id="59fc6-112">Если вы не составителем professional, найти модуль записи или редактор, которые помогут вам.</span><span class="sxs-lookup"><span data-stu-id="59fc6-112">If you are not a professional writer, find a writer or editor to help you.</span></span>
<span data-ttu-id="59fc6-113">Другой вариант — скопировать текст справки в Microsoft Word и использовании грамматики и орфографии проверяет, чтобы улучшить работу.</span><span class="sxs-lookup"><span data-stu-id="59fc6-113">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="59fc6-114">Просто написать</span><span class="sxs-lookup"><span data-stu-id="59fc6-114">Write simply</span></span>
<span data-ttu-id="59fc6-115">Используйте простые слова и фразы.</span><span class="sxs-lookup"><span data-stu-id="59fc6-115">Use simple words and phrases.</span></span>
<span data-ttu-id="59fc6-116">Избегайте жаргон.</span><span class="sxs-lookup"><span data-stu-id="59fc6-116">Avoid jargon.</span></span>
<span data-ttu-id="59fc6-117">Рассмотрим, что многие читатели обладают только с помощью внешнего словаря и справки.</span><span class="sxs-lookup"><span data-stu-id="59fc6-117">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="59fc6-118">Постоянно записи</span><span class="sxs-lookup"><span data-stu-id="59fc6-118">Write consistently</span></span>
<span data-ttu-id="59fc6-119">Справка для связанных с ним командлетов должно быть аналогично (для, например, get-x и set-x).</span><span class="sxs-lookup"><span data-stu-id="59fc6-119">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span>
<span data-ttu-id="59fc6-120">Используйте стандартные описания для стандартных параметров, например **Force** и **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="59fc6-120">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span>
<span data-ttu-id="59fc6-121">(Скопировать их из справки по основным командлетам.) Используйте стандартные условия.</span><span class="sxs-lookup"><span data-stu-id="59fc6-121">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span>
<span data-ttu-id="59fc6-122">Например, используйте «параметр», не «аргумент», и используйте «командлет» не «команду» или «команда let».</span><span class="sxs-lookup"><span data-stu-id="59fc6-122">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="59fc6-123">Запустить развернутое с помощью команды</span><span class="sxs-lookup"><span data-stu-id="59fc6-123">Start the synopsis with a verb</span></span>
<span data-ttu-id="59fc6-124">Поле краткий обзор пользователю не какой командлет, что это такое и как это работает.</span><span class="sxs-lookup"><span data-stu-id="59fc6-124">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span>
<span data-ttu-id="59fc6-125">Команды Создать инструкцию на основе задач, которая информирует пользователей, если этот командлет соответствует их требованиям.</span><span class="sxs-lookup"><span data-stu-id="59fc6-125">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span>
<span data-ttu-id="59fc6-126">Используйте простые команды, например «get», «создать» и «изменить».</span><span class="sxs-lookup"><span data-stu-id="59fc6-126">Use simple verbs like "get", "create", and "change."</span></span>
<span data-ttu-id="59fc6-127">Избегайте «set», который может быть неопределенным и она же, такие как «изменить».</span><span class="sxs-lookup"><span data-stu-id="59fc6-127">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="59fc6-128">Сосредоточиться на объекты</span><span class="sxs-lookup"><span data-stu-id="59fc6-128">Focus on objects</span></span>
<span data-ttu-id="59fc6-129">Большинство «get» отображение командлетов что-нибудь, но является их основной функцией для получения объекта.</span><span class="sxs-lookup"><span data-stu-id="59fc6-129">Most "get" cmdlets display something, but their primary function is to get an object.</span></span>
<span data-ttu-id="59fc6-130">В помощь рассмотрим объект, чтобы было понятно, что по умолчанию отображается одним из многих, и они могут использовать методы и свойства объекта, который вы получили для них по-разному.</span><span class="sxs-lookup"><span data-stu-id="59fc6-130">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="59fc6-131">Подробные описания</span><span class="sxs-lookup"><span data-stu-id="59fc6-131">Write detailed descriptions</span></span>
<span data-ttu-id="59fc6-132">Кратко перечислены все, что командлет можно делать в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="59fc6-132">Briefly list everything that the cmdlet can do in the detailed description.</span></span>
<span data-ttu-id="59fc6-133">Если основной функцией является изменение одного свойства, но командлет можно изменить все свойства, список это в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="59fc6-133">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="59fc6-134">Используйте обычные синтаксис</span><span class="sxs-lookup"><span data-stu-id="59fc6-134">Use conventional syntax</span></span>
<span data-ttu-id="59fc6-135">Используйте стандартный формат форма Бэкуса-Наура, которые являются общими для Windows и UNIX Справка по командной строке.</span><span class="sxs-lookup"><span data-stu-id="59fc6-135">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-framework-types-for-parameter-values"></a><span data-ttu-id="59fc6-136">Использование типов Microsoft .NET Framework для значений параметра</span><span class="sxs-lookup"><span data-stu-id="59fc6-136">Use Microsoft .NET Framework types for parameter values</span></span>
<span data-ttu-id="59fc6-137">Заполнители для значений параметров (в описании синтаксиса и параметром) показаны типы .NET Framework объектов, которые будет принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="59fc6-137">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span>
<span data-ttu-id="59fc6-138">Группа разработчиков PowerShell разработаны это соглашение, помогающие обучить пользователей работе с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59fc6-138">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="59fc6-139">Описание параметров завершения записи</span><span class="sxs-lookup"><span data-stu-id="59fc6-139">Write complete parameter descriptions</span></span>
<span data-ttu-id="59fc6-140">Описания параметров необходимо проинформировать пользователей о две вещи: какой параметр не (влияние) и их необходимо ввести для значения параметров.</span><span class="sxs-lookup"><span data-stu-id="59fc6-140">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="59fc6-141">Запись практические примеры</span><span class="sxs-lookup"><span data-stu-id="59fc6-141">Write practical examples</span></span>
<span data-ttu-id="59fc6-142">Примеры должны показано, как использовать все параметры, но самое главное — Показать, как использовать командлет в реальных задач.</span><span class="sxs-lookup"><span data-stu-id="59fc6-142">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span>
<span data-ttu-id="59fc6-143">Начать с простого примера и написать все более сложные примеры.</span><span class="sxs-lookup"><span data-stu-id="59fc6-143">Start with a simple example and write increasingly complex examples.</span></span>
<span data-ttu-id="59fc6-144">В последнем примере показано, как использовать командлет в конвейере.</span><span class="sxs-lookup"><span data-stu-id="59fc6-144">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="59fc6-145">Использовать поле «заметки»</span><span class="sxs-lookup"><span data-stu-id="59fc6-145">Use the Notes field</span></span>
<span data-ttu-id="59fc6-146">Используйте поле примечания для объяснения концепции, что пользователи должны знать командлет.</span><span class="sxs-lookup"><span data-stu-id="59fc6-146">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span>
<span data-ttu-id="59fc6-147">Заметки также можно использовать, чтобы помочь пользователям избежать распространенных ошибок.</span><span class="sxs-lookup"><span data-stu-id="59fc6-147">You can also use notes to help users avoid common errors.</span></span>
<span data-ttu-id="59fc6-148">Избегайте URL-адреса, как их изменения.</span><span class="sxs-lookup"><span data-stu-id="59fc6-148">Avoid URLs as they change.</span></span>
<span data-ttu-id="59fc6-149">Вместо этого предоставляют пользователям термины для поиска.</span><span class="sxs-lookup"><span data-stu-id="59fc6-149">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="59fc6-150">Тестирование помощь</span><span class="sxs-lookup"><span data-stu-id="59fc6-150">Test your Help</span></span>
<span data-ttu-id="59fc6-151">Тестирование окна справки, так же, как тестировать код.</span><span class="sxs-lookup"><span data-stu-id="59fc6-151">Test the Help just like you test your code.</span></span>
<span data-ttu-id="59fc6-152">Иметь друзей и коллег чтение содержимого справки и отправки отзывов.</span><span class="sxs-lookup"><span data-stu-id="59fc6-152">Have friends and colleagues read your Help content and provide feedback.</span></span>
<span data-ttu-id="59fc6-153">Можно также запросить отзывы от участников групп новостей.</span><span class="sxs-lookup"><span data-stu-id="59fc6-153">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="59fc6-154">См. также</span><span class="sxs-lookup"><span data-stu-id="59fc6-154">See Also</span></span>

 [<span data-ttu-id="59fc6-155">Создание файла справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="59fc6-155">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="59fc6-156">Как добавить имя командлета и краткий обзор раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-156">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-157">Как добавить подробное описание раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-157">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="59fc6-158">Как добавить синтаксис для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-158">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-159">Как добавить параметры для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-159">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="59fc6-160">Как добавлять типы входных данных для раздела справки командлета</span><span class="sxs-lookup"><span data-stu-id="59fc6-160">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-161">Как добавить возвращаемые значения для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-161">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-162">Добавление заметки для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-162">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-163">Как добавить примеры для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-163">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-164">Добавление ссылки по теме раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="59fc6-164">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="59fc6-165">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59fc6-165">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
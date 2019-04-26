---
title: Поддержка подстановочных знаков в параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcards [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide], wildcards
ms.assetid: 9b26e1e9-9350-4a5a-aad5-ddcece658d93
caps.latest.revision: 12
ms.openlocfilehash: 6c762d3889bc4b649252390625525db4735f4c1d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067405"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="13e79-102">Поддержка подстановочных знаков в параметрах командлета</span><span class="sxs-lookup"><span data-stu-id="13e79-102">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="13e79-103">Часто необходимо будет создать командлет для запуска группы ресурсов, а не один ресурс.</span><span class="sxs-lookup"><span data-stu-id="13e79-103">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="13e79-104">Например командлет может потребоваться найти все файлы в хранилище данных с тем же именем или расширения.</span><span class="sxs-lookup"><span data-stu-id="13e79-104">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="13e79-105">При проектировании командлет, который будет выполняться для группы ресурсов, вы должны предоставить поддержку для подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="13e79-105">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="13e79-106">Использование символов-шаблонов иногда называется *глобализации*.</span><span class="sxs-lookup"><span data-stu-id="13e79-106">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="13e79-107">Командлеты Windows PowerShell, которые используются подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="13e79-107">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="13e79-108">Многие командлеты Windows PowerShell поддерживает символы-шаблоны для своих значений параметров.</span><span class="sxs-lookup"><span data-stu-id="13e79-108">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="13e79-109">Например, почти каждый командлет с `Name` или `Path` параметр поддерживает символы-шаблоны для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="13e79-109">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="13e79-110">(Несмотря на то, что большинство командлетов, имеющих `Path` параметр также иметь `LiteralPath` параметр, который не поддерживает подстановочные знаки.) Следующая команда показывает, как подстановочный знак используется для возврата всех командлетов в текущем сеансе, имя которого содержит команду Get.</span><span class="sxs-lookup"><span data-stu-id="13e79-110">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 <span data-ttu-id="13e79-111">**PS > get-command get -\***</span><span class="sxs-lookup"><span data-stu-id="13e79-111">**PS>get-command get-\***</span></span>

## <a name="supported-wildcard-characters"></a><span data-ttu-id="13e79-112">Поддерживаемые подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="13e79-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="13e79-113">Windows PowerShell поддерживает следующие подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="13e79-113">Windows PowerShell supports the following wildcard characters.</span></span>

|<span data-ttu-id="13e79-114">подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="13e79-114">Wildcard character</span></span>|<span data-ttu-id="13e79-115">Описание</span><span class="sxs-lookup"><span data-stu-id="13e79-115">Description</span></span>|<span data-ttu-id="13e79-116">Пример</span><span class="sxs-lookup"><span data-stu-id="13e79-116">Example</span></span>|<span data-ttu-id="13e79-117">Совпадения</span><span class="sxs-lookup"><span data-stu-id="13e79-117">Matches</span></span>|<span data-ttu-id="13e79-118">Не соответствует</span><span class="sxs-lookup"><span data-stu-id="13e79-118">Does not match</span></span>|
|------------------------|-----------------|-------------|-------------|--------------------|
|*|<span data-ttu-id="13e79-119">Совпадает с нуля или более символов, начиная с указанной позиции</span><span class="sxs-lookup"><span data-stu-id="13e79-119">Matches zero or more characters, starting at the specified position</span></span>|<span data-ttu-id="13e79-120">\*</span><span class="sxs-lookup"><span data-stu-id="13e79-120">a\*</span></span>|<span data-ttu-id="13e79-121">, Ag Apple</span><span class="sxs-lookup"><span data-stu-id="13e79-121">A, ag, Apple</span></span>||
|<span data-ttu-id="13e79-122">?</span><span class="sxs-lookup"><span data-stu-id="13e79-122">?</span></span>|<span data-ttu-id="13e79-123">Anycharacter совпадений в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="13e79-123">Matches anycharacter at the specified position</span></span>|<span data-ttu-id="13e79-124">? n</span><span class="sxs-lookup"><span data-stu-id="13e79-124">?n</span></span>|<span data-ttu-id="13e79-125">В, на</span><span class="sxs-lookup"><span data-stu-id="13e79-125">An, in, on</span></span>|<span data-ttu-id="13e79-126">запустили</span><span class="sxs-lookup"><span data-stu-id="13e79-126">ran</span></span>|
|<span data-ttu-id="13e79-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="13e79-127">[ ]</span></span>|<span data-ttu-id="13e79-128">Сопоставляет диапазон символов</span><span class="sxs-lookup"><span data-stu-id="13e79-128">Matches a range of characters</span></span>|<span data-ttu-id="13e79-129">[a-l] игу</span><span class="sxs-lookup"><span data-stu-id="13e79-129">[a-l]ook</span></span>|<span data-ttu-id="13e79-130">книги, оформление, Кука</span><span class="sxs-lookup"><span data-stu-id="13e79-130">book, cook, look</span></span>|<span data-ttu-id="13e79-131">заняло</span><span class="sxs-lookup"><span data-stu-id="13e79-131">took</span></span>|
|<span data-ttu-id="13e79-132">[ ]</span><span class="sxs-lookup"><span data-stu-id="13e79-132">[ ]</span></span>|<span data-ttu-id="13e79-133">Соответствует указанным символам</span><span class="sxs-lookup"><span data-stu-id="13e79-133">Matches the specified characters</span></span>|<span data-ttu-id="13e79-134">игу [bc]</span><span class="sxs-lookup"><span data-stu-id="13e79-134">[bc]ook</span></span>|<span data-ttu-id="13e79-135">книги, Кука</span><span class="sxs-lookup"><span data-stu-id="13e79-135">book, cook</span></span>|<span data-ttu-id="13e79-136">внешний вид</span><span class="sxs-lookup"><span data-stu-id="13e79-136">look</span></span>|

<span data-ttu-id="13e79-137">При создании командлетов, которые поддерживают символы-шаблоны позволяют комбинации подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="13e79-137">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="13e79-138">Например, приведенная ниже команда использует `Get-ChildItem` командлет, чтобы получить все файлы .txt, находятся в папке c:\Techdocs и, которые начинаются с буквы «» до «l.»</span><span class="sxs-lookup"><span data-stu-id="13e79-138">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

<span data-ttu-id="13e79-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="13e79-139">**get-childitem c:\techdocs\\[a-l]\*.txt**</span></span>

<span data-ttu-id="13e79-140">Предыдущая команда используется подстановочный знак диапазон **[a-l]** для указания, что имя файла должно начинаться с символов при «» до «l.»</span><span class="sxs-lookup"><span data-stu-id="13e79-140">The previous command uses the range wildcard **[a-l]** to specify that the file name should begin with the characters "a" through "l."</span></span> <span data-ttu-id="13e79-141">Затем с помощью \* подстановочный знак в качестве заполнителя для любыми символами между первая буква имени файла и расширение .txt.</span><span class="sxs-lookup"><span data-stu-id="13e79-141">The command then uses the \* wildcard character as a placeholder for any characters between the first letter of the file name and the .txt extension.</span></span>

<span data-ttu-id="13e79-142">В следующем примере используется шаблон с подстановочными знаками диапазон, который исключает буквы «d», но включает в себя все другие буквы от «» до «f.»</span><span class="sxs-lookup"><span data-stu-id="13e79-142">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

<span data-ttu-id="13e79-143">**get-childitem c:\techdocs\\[a-cef]\*.txt**</span><span class="sxs-lookup"><span data-stu-id="13e79-143">**get-childitem c:\techdocs\\[a-cef]\*.txt**</span></span>

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="13e79-144">Обработка литеральными символами в шаблоны с подстановочными знаками</span><span class="sxs-lookup"><span data-stu-id="13e79-144">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="13e79-145">Если шаблон подстановочного знака, указанную вами содержит литералы, используйте символ обратного апострофа (') как escape-символ.</span><span class="sxs-lookup"><span data-stu-id="13e79-145">If the wildcard pattern you specify contains literal characters, use the backtick character (\`) as an escape character.</span></span> <span data-ttu-id="13e79-146">При указании литералы программным способом, используйте — единый обратный апостроф.</span><span class="sxs-lookup"><span data-stu-id="13e79-146">When you specify literal characters programmatically, use a single backtick.</span></span> <span data-ttu-id="13e79-147">При указании литеральных символов, в командной строке, используйте два обратных апострофа.</span><span class="sxs-lookup"><span data-stu-id="13e79-147">When you specify literal characters at the command prompt, use two backticks.</span></span> <span data-ttu-id="13e79-148">Например следующий шаблон содержит две квадратные скобки, которые необходимо принимать буквально.</span><span class="sxs-lookup"><span data-stu-id="13e79-148">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="13e79-149">«Иван Кузнецов \`[\* "]» (программно задана)</span><span class="sxs-lookup"><span data-stu-id="13e79-149">"John Smith \`[\*\`]" (specified programmatically)</span></span>

<span data-ttu-id="13e79-150">«Иван Кузнецов \` \`[\*\`"]» (заданный в командной строке)</span><span class="sxs-lookup"><span data-stu-id="13e79-150">"John Smith \`\`[\*\`\`]"  (specified at the command prompt)</span></span>

<span data-ttu-id="13e79-151">Этот шаблон соответствует «Иван Кузнецов [маркетинга]» или «Иван Кузнецов [Разработка решений]».</span><span class="sxs-lookup"><span data-stu-id="13e79-151">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span>

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="13e79-152">Выходные данные командлета и символы-шаблоны</span><span class="sxs-lookup"><span data-stu-id="13e79-152">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="13e79-153">При параметры командлета поддерживает подстановочные знаки, операция командлет обычно создает выходной массив.</span><span class="sxs-lookup"><span data-stu-id="13e79-153">When cmdlet parameters support wildcard characters, a cmdlet operation usually generates an array output.</span></span> <span data-ttu-id="13e79-154">В некоторых случаях нет смысла для поддержки массив выходных данных, так как пользователь может использовать только одного элемента за раз.</span><span class="sxs-lookup"><span data-stu-id="13e79-154">Occasionally, it makes no sense to support an array output because the user might use only a single item at a time.</span></span> <span data-ttu-id="13e79-155">Например `Set-Location` командлет поддерживает массив выходных данных, так как пользователь задает в одном месте.</span><span class="sxs-lookup"><span data-stu-id="13e79-155">For example, the `Set-Location` cmdlet does support an array output because the user sets only a single location.</span></span> <span data-ttu-id="13e79-156">В этом случае командлет по-прежнему поддерживает подстановочные знаки, но он заставляет разрешения в одном месте.</span><span class="sxs-lookup"><span data-stu-id="13e79-156">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="13e79-157">См. также</span><span class="sxs-lookup"><span data-stu-id="13e79-157">See Also</span></span>

[<span data-ttu-id="13e79-158">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13e79-158">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="13e79-159">Класс WildcardPattern</span><span class="sxs-lookup"><span data-stu-id="13e79-159">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)

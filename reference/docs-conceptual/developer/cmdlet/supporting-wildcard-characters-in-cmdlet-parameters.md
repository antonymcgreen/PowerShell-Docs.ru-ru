---
ms.date: 08/26/2019
ms.topic: reference
title: Поддержка подстановочных знаков в параметрах командлета
description: Поддержка подстановочных знаков в параметрах командлета
ms.openlocfilehash: 06693c62cd2613050bdeb9d6b12ad6e9597a9894
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646388"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="485dd-103">Поддержка подстановочных знаков в параметрах командлета</span><span class="sxs-lookup"><span data-stu-id="485dd-103">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="485dd-104">Часто приходится проектировать командлет, который будет выполняться для группы ресурсов, а не для отдельного ресурса.</span><span class="sxs-lookup"><span data-stu-id="485dd-104">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="485dd-105">Например, командлету может потребоваться поиск всех файлов в хранилище данных с одинаковым именем или расширением.</span><span class="sxs-lookup"><span data-stu-id="485dd-105">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="485dd-106">При проектировании командлета, который будет выполняться для группы ресурсов, необходимо предоставить поддержку подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="485dd-106">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="485dd-107">Использование подстановочных знаков иногда называется *глобализации*.</span><span class="sxs-lookup"><span data-stu-id="485dd-107">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="485dd-108">Командлеты Windows PowerShell, использующие подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="485dd-108">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="485dd-109">Многие командлеты Windows PowerShell поддерживают подстановочные знаки для значений их параметров.</span><span class="sxs-lookup"><span data-stu-id="485dd-109">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="485dd-110">Например, почти каждый командлет, имеющий `Name` параметр или, `Path` поддерживает подстановочные знаки для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="485dd-110">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="485dd-111">(Хотя большинство командлетов, у которых есть `Path` параметр, также имеют `LiteralPath` параметр, который не поддерживает подстановочные знаки.) Следующая команда показывает, как использовать подстановочный знак для возврата всех командлетов в текущем сеансе, имя которых содержит команду Get.</span><span class="sxs-lookup"><span data-stu-id="485dd-111">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="485dd-112">Поддерживаемые подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="485dd-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="485dd-113">Windows PowerShell поддерживает следующие подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="485dd-113">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="485dd-114">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="485dd-114">Wildcard</span></span> |                             <span data-ttu-id="485dd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="485dd-115">Description</span></span>                             |  <span data-ttu-id="485dd-116">Пример</span><span class="sxs-lookup"><span data-stu-id="485dd-116">Example</span></span>   |     <span data-ttu-id="485dd-117">Соответствует</span><span class="sxs-lookup"><span data-stu-id="485dd-117">Matches</span></span>      | <span data-ttu-id="485dd-118">Не соответствует</span><span class="sxs-lookup"><span data-stu-id="485dd-118">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="485dd-119">Соответствует нулю или большему числу символов, начиная с указанной позиции</span><span class="sxs-lookup"><span data-stu-id="485dd-119">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="485dd-120">A, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="485dd-120">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="485dd-121">?</span><span class="sxs-lookup"><span data-stu-id="485dd-121">?</span></span>        | <span data-ttu-id="485dd-122">Соответствует любому символу в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="485dd-122">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="485dd-123">Объект, в, на</span><span class="sxs-lookup"><span data-stu-id="485dd-123">An, in, on</span></span>       | <span data-ttu-id="485dd-124">обнаружил</span><span class="sxs-lookup"><span data-stu-id="485dd-124">ran</span></span>            |
| <span data-ttu-id="485dd-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="485dd-125">[ ]</span></span>      | <span data-ttu-id="485dd-126">Соответствует диапазону символов</span><span class="sxs-lookup"><span data-stu-id="485dd-126">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="485dd-127">книга, Кука, взгляд</span><span class="sxs-lookup"><span data-stu-id="485dd-127">book, cook, look</span></span> | <span data-ttu-id="485dd-128">Нук, занял</span><span class="sxs-lookup"><span data-stu-id="485dd-128">nook, took</span></span>     |
| <span data-ttu-id="485dd-129">[ ]</span><span class="sxs-lookup"><span data-stu-id="485dd-129">[ ]</span></span>      | <span data-ttu-id="485dd-130">Соответствует указанным символам</span><span class="sxs-lookup"><span data-stu-id="485dd-130">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="485dd-131">книга, Нук</span><span class="sxs-lookup"><span data-stu-id="485dd-131">book, nook</span></span>       | <span data-ttu-id="485dd-132">Кука, взгляд</span><span class="sxs-lookup"><span data-stu-id="485dd-132">cook, look</span></span>     |

<span data-ttu-id="485dd-133">При проектировании командлетов, поддерживающих символы-шаблоны, можно использовать сочетания символов-шаблонов.</span><span class="sxs-lookup"><span data-stu-id="485dd-133">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="485dd-134">Например, следующая команда использует `Get-ChildItem` командлет для получения всех TXT-файлов, которые находятся в папке к:\течдокс и начинаются с букв "a" до "l".</span><span class="sxs-lookup"><span data-stu-id="485dd-134">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="485dd-135">Предыдущая команда использует подстановочный знак диапазона, `[a-l]` чтобы указать, что имя файла должно начинаться с символов "a" до "l" и использовать `*` подстановочный знак в качестве заполнителя для любых символов между первой буквой имени файла и расширением **txt** .</span><span class="sxs-lookup"><span data-stu-id="485dd-135">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="485dd-136">В следующем примере используется шаблон шаблона диапазона, который исключает букву "d", но включает все остальные буквы из "a" в "f".</span><span class="sxs-lookup"><span data-stu-id="485dd-136">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="485dd-137">Обработка литеральных символов в шаблонах с подстановочными знаками</span><span class="sxs-lookup"><span data-stu-id="485dd-137">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="485dd-138">Если указанный шаблон шаблона содержит литеральные символы, которые не должны быть интерпреттед в качестве подстановочных знаков, используйте символ обратной кавычки ( `` ` `` ) в качестве escape-символа.</span><span class="sxs-lookup"><span data-stu-id="485dd-138">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="485dd-139">Если вы указываете литеральные символы int API PowerShell, используйте один обратный символ.</span><span class="sxs-lookup"><span data-stu-id="485dd-139">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="485dd-140">При указании литеральных символов в командной строке PowerShell используйте два обратных импульса.</span><span class="sxs-lookup"><span data-stu-id="485dd-140">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="485dd-141">Например, следующий шаблон содержит две квадратные скобки, которые должны быть выполнены буквально.</span><span class="sxs-lookup"><span data-stu-id="485dd-141">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="485dd-142">При использовании в API PowerShell используется:</span><span class="sxs-lookup"><span data-stu-id="485dd-142">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="485dd-143">"Джон Смит \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="485dd-143">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="485dd-144">При использовании из командной строки PowerShell:</span><span class="sxs-lookup"><span data-stu-id="485dd-144">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="485dd-145">"Джон Смит \` \` [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="485dd-145">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="485dd-146">Этот шаблон соответствует "Джон Смит [Marketing]" или "Джон Смит [разработка]".</span><span class="sxs-lookup"><span data-stu-id="485dd-146">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="485dd-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="485dd-147">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="485dd-148">Выходные данные командлета и подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="485dd-148">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="485dd-149">Если параметры командлета поддерживают подстановочные знаки, операция обычно создает выходные данные массива.</span><span class="sxs-lookup"><span data-stu-id="485dd-149">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="485dd-150">Иногда не имеет смысла поддерживать выходные данные массива, поскольку пользователь может использовать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="485dd-150">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="485dd-151">Например, командлет не `Set-Location` поддерживает вывод массива, поскольку пользователь устанавливает только одно расположение.</span><span class="sxs-lookup"><span data-stu-id="485dd-151">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="485dd-152">В этом случае командлет по-прежнему поддерживает подстановочные знаки, но обеспечивает разрешение в одном месте.</span><span class="sxs-lookup"><span data-stu-id="485dd-152">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="485dd-153">См. также</span><span class="sxs-lookup"><span data-stu-id="485dd-153">See Also</span></span>

[<span data-ttu-id="485dd-154">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="485dd-154">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="485dd-155">Класс Вилдкардпаттерн</span><span class="sxs-lookup"><span data-stu-id="485dd-155">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)

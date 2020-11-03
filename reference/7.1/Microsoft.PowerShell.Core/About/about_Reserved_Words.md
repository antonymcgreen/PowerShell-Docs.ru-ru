---
description: Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: edf37ce528c8fd98ce3ca7741a1a6c9e0443173a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232630"
---
# <a name="about-reserved-words"></a><span data-ttu-id="f549a-104">О зарезервированных словах</span><span class="sxs-lookup"><span data-stu-id="f549a-104">About Reserved Words</span></span>

## <a name="short-description"></a><span data-ttu-id="f549a-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f549a-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f549a-106">Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f549a-106">Lists the reserved words that cannot be used as identifiers because they have a special meaning in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f549a-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f549a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f549a-108">В PowerShell есть определенные слова, имеющие специальное значение.</span><span class="sxs-lookup"><span data-stu-id="f549a-108">There are certain words that have special meaning in PowerShell.</span></span> <span data-ttu-id="f549a-109">Когда эти слова отображаются без кавычек, PowerShell пытается применить специальное значение вместо того, чтобы рассматривать их как символьные строки.</span><span class="sxs-lookup"><span data-stu-id="f549a-109">When these words appear without quotation marks, PowerShell attempts to apply their special meaning rather than treating them as character strings.</span></span> <span data-ttu-id="f549a-110">Чтобы использовать эти слова в качестве аргументов параметров в команде или скрипте без вызова их специального значения, заключите зарезервированные слова в кавычки.</span><span class="sxs-lookup"><span data-stu-id="f549a-110">To use these words as parameter arguments in a command or script without invoking their special meaning, enclose the reserved words in quotation marks.</span></span>

<span data-ttu-id="f549a-111">Ниже приведены зарезервированные слова в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f549a-111">The following are the reserved words in PowerShell:</span></span>

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

<span data-ttu-id="f549a-112">Некоторые ключевые слова языка, включая `Foreach` ,, `If` `For` и `While` , имеют собственные справочные статьи.</span><span class="sxs-lookup"><span data-stu-id="f549a-112">Several language keywords, including `Foreach`, `If`, `For`, and `While`, have their own help articles.</span></span> <span data-ttu-id="f549a-113">Чтобы просмотреть их, введите `Get-Help about_` и добавьте ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="f549a-113">To view them, type `Get-Help about_` and add the keyword.</span></span> <span data-ttu-id="f549a-114">Например, чтобы получить сведения о `Foreach` инструкции, введите:</span><span class="sxs-lookup"><span data-stu-id="f549a-114">For example, to get information about the `Foreach` statement, type:</span></span>

```powershell
Get-Help about_ForEach
```

<span data-ttu-id="f549a-115">Для получения сведений о `Filter` инструкции или `Return` синтаксисе инструкции введите:</span><span class="sxs-lookup"><span data-stu-id="f549a-115">For information about the `Filter` statement or the `Return` statement syntax, type:</span></span>

```powershell
Get-Help about_Functions
```

<span data-ttu-id="f549a-116">Для получения сведений о других зарезервированных словах введите:</span><span class="sxs-lookup"><span data-stu-id="f549a-116">For information about other reserved words, type:</span></span>

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> <span data-ttu-id="f549a-117">Не все зарезервированные слова имеют собственную справочную статью.</span><span class="sxs-lookup"><span data-stu-id="f549a-117">Not every reserved word has its own help article.</span></span> <span data-ttu-id="f549a-118">Если не `Get-Help` возвращает статью, можно выполнить поиск статей, которые говорят о зарезервированном слове, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="f549a-118">If `Get-Help` does not return an article, you can search for articles that talk about the reserved word using the following command:</span></span>
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a><span data-ttu-id="f549a-119">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f549a-119">SEE ALSO</span></span>

- [<span data-ttu-id="f549a-120">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="f549a-120">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="f549a-121">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="f549a-121">about_Language_Keywords</span></span>](about_Language_Keywords.md)
- [<span data-ttu-id="f549a-122">about_Parsing</span><span class="sxs-lookup"><span data-stu-id="f549a-122">about_Parsing</span></span>](about_Parsing.md)
- [<span data-ttu-id="f549a-123">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="f549a-123">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="f549a-124">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="f549a-124">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="f549a-125">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="f549a-125">about_Special_Characters</span></span>](about_Special_Characters.md)

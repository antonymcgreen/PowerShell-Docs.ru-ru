---
description: Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: 95911e328a50c173235f47a7610393124781555d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600478"
---
# <a name="about-reserved-words"></a><span data-ttu-id="21f01-103">О зарезервированных словах</span><span class="sxs-lookup"><span data-stu-id="21f01-103">About Reserved Words</span></span>

## <a name="short-description"></a><span data-ttu-id="21f01-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="21f01-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="21f01-105">Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f01-105">Lists the reserved words that cannot be used as identifiers because they have a special meaning in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="21f01-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="21f01-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="21f01-107">В PowerShell есть определенные слова, имеющие специальное значение.</span><span class="sxs-lookup"><span data-stu-id="21f01-107">There are certain words that have special meaning in PowerShell.</span></span> <span data-ttu-id="21f01-108">Когда эти слова отображаются без кавычек, PowerShell пытается применить специальное значение вместо того, чтобы рассматривать их как символьные строки.</span><span class="sxs-lookup"><span data-stu-id="21f01-108">When these words appear without quotation marks, PowerShell attempts to apply their special meaning rather than treating them as character strings.</span></span> <span data-ttu-id="21f01-109">Чтобы использовать эти слова в качестве аргументов параметров в команде или скрипте без вызова их специального значения, заключите зарезервированные слова в кавычки.</span><span class="sxs-lookup"><span data-stu-id="21f01-109">To use these words as parameter arguments in a command or script without invoking their special meaning, enclose the reserved words in quotation marks.</span></span>

<span data-ttu-id="21f01-110">Ниже приведены зарезервированные слова в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f01-110">The following are the reserved words in PowerShell:</span></span>

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

<span data-ttu-id="21f01-111">Некоторые ключевые слова языка, включая `Foreach` ,, `If` `For` и `While` , имеют собственные справочные статьи.</span><span class="sxs-lookup"><span data-stu-id="21f01-111">Several language keywords, including `Foreach`, `If`, `For`, and `While`, have their own help articles.</span></span> <span data-ttu-id="21f01-112">Чтобы просмотреть их, введите `Get-Help about_` и добавьте ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="21f01-112">To view them, type `Get-Help about_` and add the keyword.</span></span> <span data-ttu-id="21f01-113">Например, чтобы получить сведения о `Foreach` инструкции, введите:</span><span class="sxs-lookup"><span data-stu-id="21f01-113">For example, to get information about the `Foreach` statement, type:</span></span>

```powershell
Get-Help about_ForEach
```

<span data-ttu-id="21f01-114">Для получения сведений о `Filter` инструкции или `Return` синтаксисе инструкции введите:</span><span class="sxs-lookup"><span data-stu-id="21f01-114">For information about the `Filter` statement or the `Return` statement syntax, type:</span></span>

```powershell
Get-Help about_Functions
```

<span data-ttu-id="21f01-115">Для получения сведений о других зарезервированных словах введите:</span><span class="sxs-lookup"><span data-stu-id="21f01-115">For information about other reserved words, type:</span></span>

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> <span data-ttu-id="21f01-116">Не все зарезервированные слова имеют собственную справочную статью.</span><span class="sxs-lookup"><span data-stu-id="21f01-116">Not every reserved word has its own help article.</span></span> <span data-ttu-id="21f01-117">Если не `Get-Help` возвращает статью, можно выполнить поиск статей, которые говорят о зарезервированном слове, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="21f01-117">If `Get-Help` does not return an article, you can search for articles that talk about the reserved word using the following command:</span></span>
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a><span data-ttu-id="21f01-118">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="21f01-118">SEE ALSO</span></span>

- [<span data-ttu-id="21f01-119">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="21f01-119">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="21f01-120">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="21f01-120">about_Language_Keywords</span></span>](about_Language_Keywords.md)
- [<span data-ttu-id="21f01-121">about_Parsing</span><span class="sxs-lookup"><span data-stu-id="21f01-121">about_Parsing</span></span>](about_Parsing.md)
- [<span data-ttu-id="21f01-122">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="21f01-122">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="21f01-123">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="21f01-123">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="21f01-124">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="21f01-124">about_Special_Characters</span></span>](about_Special_Characters.md)

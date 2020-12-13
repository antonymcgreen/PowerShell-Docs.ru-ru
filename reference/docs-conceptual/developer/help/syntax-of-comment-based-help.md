---
ms.date: 09/12/2016
ms.topic: reference
title: Синтаксис справки на основе комментариев
description: Синтаксис справки на основе комментариев
ms.openlocfilehash: 3866f25b40fc970e8d219af6f423b7a25f5b875c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659516"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="c3662-103">Синтаксис справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="c3662-103">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="c3662-104">В этом разделе описывается синтаксис справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="c3662-104">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="c3662-105">Схема синтаксиса</span><span class="sxs-lookup"><span data-stu-id="c3662-105">Syntax Diagram</span></span>

 <span data-ttu-id="c3662-106">Синтаксис для справки на основе комментариев выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c3662-106">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="c3662-107">Описание синтаксиса</span><span class="sxs-lookup"><span data-stu-id="c3662-107">Syntax Description</span></span>

 <span data-ttu-id="c3662-108">Справка на основе комментариев записывается в виде набора комментариев.</span><span class="sxs-lookup"><span data-stu-id="c3662-108">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="c3662-109">Можно ввести символ комментария ( `#` ) перед каждой строкой комментариев или использовать `<#` `#>` символы и для создания блока комментариев.</span><span class="sxs-lookup"><span data-stu-id="c3662-109">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="c3662-110">Все строки внутри блока комментариев обрабатываются как комментарии.</span><span class="sxs-lookup"><span data-stu-id="c3662-110">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="c3662-111">Каждый раздел справки на основе комментариев определяется по ключевому слову, а каждому ключевому слову предшествует точка ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="c3662-111">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="c3662-112">Ключевые слова могут отображаться в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="c3662-112">The keywords can appear in any order.</span></span> <span data-ttu-id="c3662-113">Имена ключевых слов не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="c3662-113">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="c3662-114">Блок комментариев должен содержать по крайней мере одно ключевое слово справки.</span><span class="sxs-lookup"><span data-stu-id="c3662-114">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="c3662-115">Некоторые ключевые слова, такие как **example**, могут встречаться много раз в одном блоке комментариев.</span><span class="sxs-lookup"><span data-stu-id="c3662-115">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="c3662-116">Содержимое справки для каждого ключевого слова начинается в строке после ключевого слова и может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="c3662-116">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="c3662-117">Все строки в разделе справки на основе комментариев должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="c3662-117">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="c3662-118">Если раздел справки на основе комментариев следует за комментарием, который не является частью раздела справки, должна существовать хотя бы одна пустая строка между последней строкой комментария, отличной от справки, и началом справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="c3662-118">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="c3662-119">Например, следующий раздел справки на основе комментариев содержит. Ключевое слово Description и его значение, которое является описанием функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="c3662-119">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```

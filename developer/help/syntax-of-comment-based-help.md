---
title: Синтаксис справки на основе комментариев | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8adc997-1a71-48e9-9383-513ef13da7cf
caps.latest.revision: 4
ms.openlocfilehash: 584e5923008e8369a83c699478844f0e0c295adc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855550"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="0bca0-102">Синтаксис справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="0bca0-102">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="0bca0-103">В этом разделе описывается синтаксис справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="0bca0-103">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="0bca0-104">Диаграмма синтаксиса</span><span class="sxs-lookup"><span data-stu-id="0bca0-104">Syntax Diagram</span></span>

 <span data-ttu-id="0bca0-105">Ниже приведен синтаксис для получения справки на основе комментариев:</span><span class="sxs-lookup"><span data-stu-id="0bca0-105">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="0bca0-106">Описание синтаксиса</span><span class="sxs-lookup"><span data-stu-id="0bca0-106">Syntax Description</span></span>

 <span data-ttu-id="0bca0-107">Справка на основе комментариев записывается в виде набора комментариев.</span><span class="sxs-lookup"><span data-stu-id="0bca0-107">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="0bca0-108">Можно ввести символ комментария (#) перед каждой строки комментариев, или можно использовать "\<#» и «#>» символы, чтобы создать блок комментариев.</span><span class="sxs-lookup"><span data-stu-id="0bca0-108">You can type a comment symbol (#) before each line of comments, or you can use the "\<#" and "#>" symbols to create a comment block.</span></span> <span data-ttu-id="0bca0-109">Все строки в пределах блока комментария, интерпретируются как комментарии.</span><span class="sxs-lookup"><span data-stu-id="0bca0-109">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="0bca0-110">Каждый раздел справки на основе комментариев определяется ключевым словом и каждое ключевое слово стоит точка (.).</span><span class="sxs-lookup"><span data-stu-id="0bca0-110">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (.).</span></span> <span data-ttu-id="0bca0-111">Ключевые слова могут отображаться в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="0bca0-111">The keywords can appear in any order.</span></span> <span data-ttu-id="0bca0-112">Имен регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="0bca0-112">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="0bca0-113">Блок комментариев должен содержать по крайней мере одно ключевое слово справки.</span><span class="sxs-lookup"><span data-stu-id="0bca0-113">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="0bca0-114">Некоторые из ключевых слов, например, может появляться множество раз в одном блоке комментариев.</span><span class="sxs-lookup"><span data-stu-id="0bca0-114">Some of the keywords, such as EXAMPLE, can appear many times in the same comment block.</span></span> <span data-ttu-id="0bca0-115">Содержимое справки для каждого ключевого слова начинается в строке после ключевого слова и может занимать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="0bca0-115">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="0bca0-116">Все строки в раздел справки, основанной на комментариях должны быть смежными.</span><span class="sxs-lookup"><span data-stu-id="0bca0-116">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="0bca0-117">Если раздел справки, основанной на комментариях следует комментарий, который не является частью раздела справки, должно существовать по крайней мере одну пустую строку между последней строки комментария не Help и началом справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="0bca0-117">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="0bca0-118">Например, содержит следующий раздел справки, основанной на комментариях. Описание ключевого слова и его значение, которое представляет собой описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="0bca0-118">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
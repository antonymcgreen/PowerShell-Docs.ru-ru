---
title: Написание разделов справки на основе комментариев | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e619ab16-90ad-46e9-9bde-d6dce492ba56
caps.latest.revision: 4
ms.openlocfilehash: e3d32f36b597088abc41e229bb0955c1b25504e6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361083"
---
# <a name="writing-comment-based-help-topics"></a><span data-ttu-id="2adc0-102">Написание разделов справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="2adc0-102">Writing Comment-Based Help Topics</span></span>

<span data-ttu-id="2adc0-103">Разделы справки на основе комментариев можно писать для функций и скриптов с помощью специальных ключевых слов комментария справки.</span><span class="sxs-lookup"><span data-stu-id="2adc0-103">You can write comment-based Help topics for functions and scripts by using special Help comment keywords.</span></span>

 <span data-ttu-id="2adc0-104">Командлет `Get-Help` отображает справку на основе комментариев в том же формате, в котором отображаются разделы справки по командлетам, созданные из XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="2adc0-104">The `Get-Help` cmdlet displays comment-based Help in the same format in which it displays the cmdlet Help topics that are generated from XML files.</span></span> <span data-ttu-id="2adc0-105">Пользователи могут использовать все параметры `Get-Help`, например подробный, полный, пример и режим "в сети", для вывода справки по функциям и сценариям.</span><span class="sxs-lookup"><span data-stu-id="2adc0-105">Users can use all of the parameters of `Get-Help`, such as Detailed, Full, Example, and Online, to display function and script Help.</span></span>

 <span data-ttu-id="2adc0-106">Также можно писать разделы справки на основе XML для сценариев и функций и использовать ключевые слова комментариев справки для перенаправления пользователей в разделы на основе XML или в другие разделы.</span><span class="sxs-lookup"><span data-stu-id="2adc0-106">You can also write XML-based Help topics for scripts and functions and use the Help comment keywords to redirect users to the XML-based topics or other topics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2adc0-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="2adc0-107">In This Section</span></span>

 <span data-ttu-id="2adc0-108">[Синтаксис справки на основе комментариев](./syntax-of-comment-based-help.md) Описывает синтаксис справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="2adc0-108">[Syntax of Comment-Based Help](./syntax-of-comment-based-help.md) Describes the syntax of comment-based help.</span></span>

 <span data-ttu-id="2adc0-109">[Ключевые слова справки на основе комментариев](./comment-based-help-keywords.md) Список ключевых слов в справке на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="2adc0-109">[Comment-Based Help Keywords](./comment-based-help-keywords.md) Lists the keywords in comment-based help.</span></span>

 <span data-ttu-id="2adc0-110">[Размещение справки на основе комментариев в функциях](./placing-comment-based-help-in-functions.md) Показывает, куда поместить справку на основе комментариев для функции.</span><span class="sxs-lookup"><span data-stu-id="2adc0-110">[Placing Comment-Based Help in Functions](./placing-comment-based-help-in-functions.md) Shows where to place comment-based help for a function.</span></span>

 <span data-ttu-id="2adc0-111">[Размещение справки на основе комментариев в скриптах](./placing-comment-based-help-in-scripts.md) Показывает, куда поместить справку на основе комментариев для скрипта.</span><span class="sxs-lookup"><span data-stu-id="2adc0-111">[Placing Comment-Based Help in Scripts](./placing-comment-based-help-in-scripts.md) Shows where to place comment-based help for a script.</span></span>
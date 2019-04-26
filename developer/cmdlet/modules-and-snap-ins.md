---
title: Модули и оснастки | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: 157cd64e286392f3fd770e1e34542682b1e63625
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067626"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="ae567-102">Модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="ae567-102">Modules and Snap-ins</span></span>

<span data-ttu-id="ae567-103">Командлеты могут добавляться к сеансу с помощью модулей (впервые появилась в Windows PowerShell 2.0) или оснастки. После добавления командлета в сеанс, в котором он может выполняться программным образом ведущим приложением, или интерактивном режиме из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ae567-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="ae567-104">Мы рекомендуем использовать модули в качестве метода доставки для добавления командлетов в сеанс по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="ae567-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="ae567-105">Модули позволяют добавлять командлетов, загрузив сборку, где определен этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ae567-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="ae567-106">Нет необходимости реализовать класс оснастки.</span><span class="sxs-lookup"><span data-stu-id="ae567-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="ae567-107">Модули позволяют добавлять другие ресурсы, такие как переменные, функции, скрипты, типов и форматирования файлы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="ae567-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="ae567-108">Оснастки можно использовать только для того, чтобы добавить командлеты и поставщики в сеанс.</span><span class="sxs-lookup"><span data-stu-id="ae567-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae567-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ae567-109">See Also</span></span>

[<span data-ttu-id="ae567-110">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae567-110">Writing a Windows PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

[<span data-ttu-id="ae567-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae567-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

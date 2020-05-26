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
ms.openlocfilehash: b3d8209ea7e3e8353e73ebce1531991ec9519c74
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811663"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="f07b2-102">Модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="f07b2-102">Modules and Snap-ins</span></span>

<span data-ttu-id="f07b2-103">Командлеты можно добавить в сеанс с помощью модулей (представленных в Windows PowerShell 2,0) или оснасток. После добавления командлета в сеанс его можно запустить программно ведущим приложением или интерактивно в командной строке.</span><span class="sxs-lookup"><span data-stu-id="f07b2-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="f07b2-104">В качестве метода доставки для добавления командлетов в сеанс рекомендуется использовать модули по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="f07b2-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="f07b2-105">Модули позволяют добавлять командлеты путем загрузки сборки, в которой определен командлет.</span><span class="sxs-lookup"><span data-stu-id="f07b2-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="f07b2-106">Реализовывать класс оснастки не требуется.</span><span class="sxs-lookup"><span data-stu-id="f07b2-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="f07b2-107">Модули позволяют добавлять другие ресурсы, такие как переменные, функции, скрипты, типы и файлы форматирования, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="f07b2-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="f07b2-108">Оснастки могут использоваться только для добавления командлетов и поставщиков в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f07b2-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="f07b2-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="f07b2-109">See Also</span></span>

[<span data-ttu-id="f07b2-110">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f07b2-110">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="f07b2-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f07b2-111">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)

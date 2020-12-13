---
ms.date: 09/13/2016
ms.topic: reference
title: Модули и оснастки
description: Модули и оснастки
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658688"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="79610-103">Модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="79610-103">Modules and Snap-ins</span></span>

<span data-ttu-id="79610-104">Командлеты можно добавить в сеанс с помощью модулей (представленных в Windows PowerShell 2,0) или оснасток. После добавления командлета в сеанс его можно запустить программно ведущим приложением или интерактивно в командной строке.</span><span class="sxs-lookup"><span data-stu-id="79610-104">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="79610-105">В качестве метода доставки для добавления командлетов в сеанс рекомендуется использовать модули по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="79610-105">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="79610-106">Модули позволяют добавлять командлеты путем загрузки сборки, в которой определен командлет.</span><span class="sxs-lookup"><span data-stu-id="79610-106">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="79610-107">Реализовывать класс оснастки не требуется.</span><span class="sxs-lookup"><span data-stu-id="79610-107">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="79610-108">Модули позволяют добавлять другие ресурсы, такие как переменные, функции, скрипты, типы и файлы форматирования, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="79610-108">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="79610-109">Оснастки могут использоваться только для добавления командлетов и поставщиков в сеанс.</span><span class="sxs-lookup"><span data-stu-id="79610-109">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="79610-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="79610-110">See Also</span></span>

[<span data-ttu-id="79610-111">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79610-111">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="79610-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79610-112">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)

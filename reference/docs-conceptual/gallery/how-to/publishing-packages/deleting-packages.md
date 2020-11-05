---
ms.date: 06/12/2017
title: Как удалить пакеты из коллекции PowerShell
description: Как удалить пакеты из коллекции PowerShell
ms.openlocfilehash: e02fad61ce8ab808ba9fdf4ab16b9ae236a49e80
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662577"
---
# <a name="deleting-packages"></a><span data-ttu-id="0e363-103">Удаление пакетов</span><span class="sxs-lookup"><span data-stu-id="0e363-103">Deleting Packages</span></span>

<span data-ttu-id="0e363-104">Коллекция PowerShell не поддерживает полное удаление пакетов, так как это помешает работе пользователей, которым они необходимы для работы.</span><span class="sxs-lookup"><span data-stu-id="0e363-104">The PowerShell Gallery does not support permanent deletion of packages, because that would break anyone who is depending on it remaining available.</span></span>

<span data-ttu-id="0e363-105">Вместо этого пакет можно исключить из коллекции PowerShell. Для этого используется страница управления пакетами на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="0e363-105">Instead, the PowerShell Gallery supports a way to 'unlist' a package, which can be done in the package management page on the web site.</span></span> <span data-ttu-id="0e363-106">Исключенный пакет больше не будет отображаться в результатах поиска и списках пакетов в коллекции PowerShell и при использовании команд PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="0e363-106">When a package is unlisted, it no longer shows up in search and in any package listing, both on the PowerShell Gallery and using PowerShellGet commands.</span></span>
<span data-ttu-id="0e363-107">При этом он будет доступен для загрузки при указании точной версии, что обеспечит сохранение работоспособности автоматических скриптов.</span><span class="sxs-lookup"><span data-stu-id="0e363-107">However, it remains downloadable by specifying its exact version, which is what allows the automated scripts to continue working.</span></span>

<span data-ttu-id="0e363-108">Если возникнет исключительная ситуация и нужно будет удалить какой-либо пакет, это можно сделать вручную рабочей группой, ответственной за коллекцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e363-108">If you run into an exceptional situation where you think one of your packages must be deleted, this can be handled manually by the PowerShell Gallery team.</span></span> <span data-ttu-id="0e363-109">Например, уважительной причиной для удаления элемента может стать нарушение авторских прав или если он включает потенциально вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="0e363-109">For example, if there is a copyright infringement issue, or potentially harmful content, that could be a valid reason to delete it.</span></span> <span data-ttu-id="0e363-110">Нужно отправить запрос поддержки через [коллекцию PowerShell](https://www.PowerShellGallery.com) в этом случае.</span><span class="sxs-lookup"><span data-stu-id="0e363-110">You should submit a support request through [PowerShell Gallery](https://www.PowerShellGallery.com) in that case.</span></span>

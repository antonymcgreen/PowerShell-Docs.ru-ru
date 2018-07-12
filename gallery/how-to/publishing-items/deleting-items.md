---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Удаление элементов
ms.openlocfilehash: 454cd404437bf1c31b9a1b81cd9dd0ac81e6b0f6
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893099"
---
# <a name="deleting-items"></a><span data-ttu-id="9f257-103">Удаление элементов</span><span class="sxs-lookup"><span data-stu-id="9f257-103">Deleting items</span></span>

<span data-ttu-id="9f257-104">Коллекция PowerShell не поддерживает полное удаление элементов, так как это помешает работе пользователей, которым они необходимы для работы.</span><span class="sxs-lookup"><span data-stu-id="9f257-104">The PowerShell Gallery does not support permanent deletion of items, because that would break anyone who is depending on it remaining available.</span></span>

<span data-ttu-id="9f257-105">Вместо этого элемент из коллекции PowerShell можно исключить — для этого используется страница управления элементами на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="9f257-105">Instead, the PowerShell Gallery supports a way to 'unlist' an item, which can be done in the item management page on the web site.</span></span>
<span data-ttu-id="9f257-106">Исключенный элемент больше не будет отображаться в результатах поиска и списках элементов ни в коллекции PowerShell, ни при использовании команд PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="9f257-106">When an item is unlisted, it no longer shows up in search and in any item listing, both on the PowerShell Gallery and using PowerShellGet commands.</span></span>
<span data-ttu-id="9f257-107">При этом он будет доступен для загрузки при указании точной версии, что обеспечит сохранение работоспособности автоматических скриптов.</span><span class="sxs-lookup"><span data-stu-id="9f257-107">However, it remains downloadable by specifying its exact version, which is what allows the automated scripts to continue working.</span></span>

<span data-ttu-id="9f257-108">Если возникнет исключительная ситуация и нужно будет удалить какой-либо элемент, это можно сделать вручную через рабочую группу, ответственную за коллекцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f257-108">If you run into an exceptional situation where you think one of your items must be deleted, this can be handled manually by the PowerShell Gallery team.</span></span>
<span data-ttu-id="9f257-109">Например, уважительной причиной для удаления элемента может стать нарушение авторских прав или если он включает потенциально вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="9f257-109">For example, if there is a copyright infringement issue, or potentially harmful content, that could be a valid reason to delete it.</span></span>
<span data-ttu-id="9f257-110">Нужно отправить запрос поддержки через [коллекцию PowerShell](http://www.PowerShellGallery.com) в этом случае.</span><span class="sxs-lookup"><span data-stu-id="9f257-110">You should submit a support request through [PowerShell Gallery](http://www.PowerShellGallery.com) in that case.</span></span>
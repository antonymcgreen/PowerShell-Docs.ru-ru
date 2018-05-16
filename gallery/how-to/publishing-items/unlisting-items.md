---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery
title: Исключение элементов
ms.openlocfilehash: 35dcd283ddace5aec62d692b0ede12ae0bada765
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="unlisting-items"></a><span data-ttu-id="02c40-103">Исключение элементов</span><span class="sxs-lookup"><span data-stu-id="02c40-103">Unlisting items</span></span>

<span data-ttu-id="02c40-104">**Почему в программе нет команды, позволяющей удалить элемент из коллекции PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="02c40-104">**Why is removing an item from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="02c40-105">Коллекция PowerShell не позволяет пользователям полностью удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="02c40-105">The PowerShell Gallery does not support users permanently deleting their items.</span></span>
<span data-ttu-id="02c40-106">Это позволяет другим разработчикам использовать ваши элементы в качестве зависимостей и не беспокоиться, что в будущем что-то может сломаться.</span><span class="sxs-lookup"><span data-stu-id="02c40-106">This enables others to take dependencies on your items without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="02c40-107">Например, если модуль Pester зависит от модуля Azure и этот модуль удаляется из коллекции, пользователь больше не сможет использовать модуль Pester.</span><span class="sxs-lookup"><span data-stu-id="02c40-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then user can no longer uses the Pester module.</span></span>

<span data-ttu-id="02c40-108">Вместо того, чтобы удалять элемент, его можно исключить.</span><span class="sxs-lookup"><span data-stu-id="02c40-108">Instead of removing an item, however, you can unlist it instead.</span></span>

<span data-ttu-id="02c40-109">**Что происходит при исключении элемента из коллекции PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="02c40-109">**What does unlisting an item on PowerShell Gallery do?**</span></span>

<span data-ttu-id="02c40-110">Элемент, исключенный из числа модулей или скриптов в коллекции PowerShell, будет удален с вкладки "Элементы". Кроме того, исключенные элементы не отображаются в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="02c40-110">Unlisting an item such as module or script on PowerShell Gallery will remove it from the Items tab. In addition, unlisted items will not be discoverable using the search bar.</span></span>
<span data-ttu-id="02c40-111">Единственный способ загрузить исключенный элемент — это указать его точное имя и версию.</span><span class="sxs-lookup"><span data-stu-id="02c40-111">The only way to download an unlisted item is to specify the exact name and version of the item.</span></span>
<span data-ttu-id="02c40-112">Таким образом, исключение элемента не нарушает связи с другими модулями или скриптами, которые от него зависят.</span><span class="sxs-lookup"><span data-stu-id="02c40-112">Because of this, the unlisting of an item will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="02c40-113">Чтобы исключить элемент, откройте страницу подробностей об элементе и выберите команду "Удалить элемент".</span><span class="sxs-lookup"><span data-stu-id="02c40-113">To unlist your item, visit the item details page and select 'Delete Item'.</span></span> <span data-ttu-id="02c40-114">Снимите флажок "В списке" и нажмите кнопку "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="02c40-114">Uncheck the 'Listed' checkbox, and click Save.</span></span>

<span data-ttu-id="02c40-115">**Как удалить элемент?**</span><span class="sxs-lookup"><span data-stu-id="02c40-115">**How can I remove an item?**</span></span>

<span data-ttu-id="02c40-116">В ситуации, когда элемент необходимо удалить, обратитесь к администраторам коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02c40-116">If you experience a scenario where item deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="02c40-117">Удаление элементов будет оправдано в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="02c40-117">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="02c40-118">Проблемы с нарушением авторских прав.</span><span class="sxs-lookup"><span data-stu-id="02c40-118">Issues of copyright infringement.</span></span>
- <span data-ttu-id="02c40-119">Элементы содержат потенциально вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="02c40-119">Item contains potentially harmful content.</span></span>
- <span data-ttu-id="02c40-120">Элемент содержит конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="02c40-120">Item contains sensitive data.</span></span>

<span data-ttu-id="02c40-121">Чтобы отправить запрос об удалении элементов администраторам коллекции PowerShell, откройте страницу подробностей об элементе и выберите команду "Обратиться в службу поддержки".</span><span class="sxs-lookup"><span data-stu-id="02c40-121">To submit a Delete Item Request to the PowerShell Gallery Administrators, visit your item's detail page and select Contact Support.</span></span>
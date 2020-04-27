---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Исключение пакетов
ms.openlocfilehash: b7404420db531ac5d97debd46e1b84c6fdd49d9a
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "80978276"
---
# <a name="unlisting-packages"></a><span data-ttu-id="5b8c6-103">Исключение пакетов</span><span class="sxs-lookup"><span data-stu-id="5b8c6-103">Unlisting Packages</span></span>

<span data-ttu-id="5b8c6-104">**Почему в программе нет команды, позволяющей удалить пакет из коллекции PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="5b8c6-104">**Why is removing a package from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="5b8c6-105">Коллекция PowerShell не позволяет пользователям полностью удалять пакеты.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-105">The PowerShell Gallery does not support users permanently deleting their packages.</span></span>
<span data-ttu-id="5b8c6-106">Это позволяет другим разработчикам использовать зависимости с вашими пакетами и не беспокоиться об их нарушении в будущем.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-106">This enables others to take dependencies on your packages without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="5b8c6-107">Например, если модуль Pester зависит от модуля Azure и этот модуль удаляется из коллекции, пользователи больше не смогут использовать модуль Pester.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then users can no longer use the Pester module.</span></span>

<span data-ttu-id="5b8c6-108">Вместо того, чтобы удалять пакет, его можно исключить.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-108">Instead of removing a package you can unlist it.</span></span>

<span data-ttu-id="5b8c6-109">**Что происходит при исключении пакета из коллекции PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="5b8c6-109">**What does unlisting a package on PowerShell Gallery do?**</span></span>

<span data-ttu-id="5b8c6-110">Пакет, исключенный из списка модулей или скриптов в коллекции PowerShell, будет удален из вкладки "Пакеты". Кроме того, исключенные пакеты не отображаются в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-110">Unlisting a package such as a module or script in the PowerShell Gallery removes it from the Packages tab. In addition, unlisted packages will not be discoverable using the search bar.</span></span>
<span data-ttu-id="5b8c6-111">Единственный способ загрузить исключенный пакет — это точно указать его имя и версию.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-111">The only way to download an unlisted package is to specify the exact name and version of the package.</span></span>
<span data-ttu-id="5b8c6-112">Таким образом, исключение пакета не нарушает работу других модулей или скриптов, которые от него зависят.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-112">Because of this, the unlisting of a package will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="5b8c6-113">Чтобы исключить пакет, откройте страницу сведений о пакете и выберите "Удалить модуль".</span><span class="sxs-lookup"><span data-stu-id="5b8c6-113">To unlist your package, visit the package details page and select 'Delete Module'.</span></span> <span data-ttu-id="5b8c6-114">Снимите флажок "В списке" и нажмите кнопку "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="5b8c6-114">Uncheck the 'Listed' checkbox, and select 'Save'.</span></span>

<span data-ttu-id="5b8c6-115">**Как удалить пакет?**</span><span class="sxs-lookup"><span data-stu-id="5b8c6-115">**How can I remove a package?**</span></span>

<span data-ttu-id="5b8c6-116">В ситуации, когда пакет необходимо удалить, обратитесь к администраторам коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-116">If you experience a scenario where package deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="5b8c6-117">Удаление элементов будет оправдано в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="5b8c6-117">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="5b8c6-118">Проблемы с нарушением авторских прав.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-118">Issues of copyright infringement.</span></span>
- <span data-ttu-id="5b8c6-119">Пакет содержит потенциально вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-119">Package contains potentially harmful content.</span></span>
- <span data-ttu-id="5b8c6-120">Пакет содержит конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="5b8c6-120">Package contains sensitive data.</span></span>

<span data-ttu-id="5b8c6-121">Чтобы отправить запрос об удалении пакета администраторам коллекции PowerShell, откройте страницу сведений о пакете и выберите "Обратиться в службу поддержки".</span><span class="sxs-lookup"><span data-stu-id="5b8c6-121">To submit a Delete Package Request to the PowerShell Gallery Administrators, visit your package's detail page and select Contact Support.</span></span>

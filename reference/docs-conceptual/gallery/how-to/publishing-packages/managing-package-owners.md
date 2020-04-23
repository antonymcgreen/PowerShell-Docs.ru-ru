---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Управление владельцами пакетов
ms.openlocfilehash: 5cf26a7195ac446177cbb7f3a055e8e0a78569cc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71328265"
---
# <a name="managing-package-owners"></a><span data-ttu-id="ce404-103">Управление владельцами пакетов</span><span class="sxs-lookup"><span data-stu-id="ce404-103">Managing package owners</span></span>

<span data-ttu-id="ce404-104">Право собственности на пакет в коллекции PowerShell определяется тем, кто опубликовал пакет в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ce404-104">Ownership of a package in the PowerShell Gallery is defined by who published the package to the gallery.</span></span>
<span data-ttu-id="ce404-105">Иногда этими метаданными необходимо управлять после первоначальной публикации пакета, а значит метаданные о владельцах пакета должны быть изменяемыми, даже если сам пакет таковым не является.</span><span class="sxs-lookup"><span data-stu-id="ce404-105">Sometimes this metadata needs to be managed beyond the initial package publishing, which means the owner metadata needs to be mutable while the package itself is not.</span></span>

<span data-ttu-id="ce404-106">Все владельцы пакета имеют равные права.</span><span class="sxs-lookup"><span data-stu-id="ce404-106">All package owners are peers.</span></span>
<span data-ttu-id="ce404-107">Это значит, что любой владелец пакета может опубликовать его новую версию.</span><span class="sxs-lookup"><span data-stu-id="ce404-107">This means any package owner can publish a new version of an package.</span></span> <span data-ttu-id="ce404-108">Это также означает, что любой владелец пакета может удалить любого другого владельца этого пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-108">It also means that any package owner can remove any other package owner.</span></span>
<span data-ttu-id="ce404-109">Ни один владелец не имеет больше полномочий, чем другие.</span><span class="sxs-lookup"><span data-stu-id="ce404-109">No owner has more authority than other owners.</span></span>

## <a name="setting-a-packages-initial-owner"></a><span data-ttu-id="ce404-110">Установка первоначального владельца пакета</span><span class="sxs-lookup"><span data-stu-id="ce404-110">Setting a Package's Initial Owner</span></span>

<span data-ttu-id="ce404-111">При публикации пакета в коллекции PowerShell статус первоначального владельца получает пользователь, опубликовавший пакет.</span><span class="sxs-lookup"><span data-stu-id="ce404-111">When a new package is published to PowerShell Gallery, the initial owner is defined by the user that published the package.</span></span> <span data-ttu-id="ce404-112">Он определяется по ключу интерфейса API, который использовался в командлете Publish-Module.</span><span class="sxs-lookup"><span data-stu-id="ce404-112">This is determined by whose API key was used in the Publish-Module cmdlet.</span></span>

## <a name="adding-owners"></a><span data-ttu-id="ce404-113">Добавление владельцев</span><span class="sxs-lookup"><span data-stu-id="ce404-113">Adding Owners</span></span>

<span data-ttu-id="ce404-114">После публикации пакета в коллекции PowerShell можно пригласить других пользователей стать его владельцами.</span><span class="sxs-lookup"><span data-stu-id="ce404-114">Once a package has been published to the PowerShell Gallery, it's easy to invite additional users to become owners of a package.</span></span>

1. <span data-ttu-id="ce404-115">[Войдите](https://powershellgallery.com/users/account/LogOn) в коллекцию PowerShell с помощью учетной записи текущего владельца пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-115">[Log on](https://powershellgallery.com/users/account/LogOn) to the PowerShell Gallery with the account that is the current owner of a package.</span></span>
2. <span data-ttu-id="ce404-116">Перейдите на страницу пакета, открыв вкладку "Пакеты", выполнив поиск или щелкнув свое имя пользователя, и выберите пункт [**Управление моими пакетами**](https://www.powershellgallery.com/account/Packages).</span><span class="sxs-lookup"><span data-stu-id="ce404-116">Navigate to a package page using the 'Items' tab, searching, or clicking your username and then [**Manage My Packages**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="ce404-117">Если вход в систему выполнен владельцем пакета, слева будет доступна ссылка "Управление владельцами".</span><span class="sxs-lookup"><span data-stu-id="ce404-117">When logged on as an package's owner, there is a 'Manage Owners' link on the left side to click.</span></span>
4. <span data-ttu-id="ce404-118">Введите имя пользователя, которого нужно добавить в качестве владельца, и нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="ce404-118">Enter the username of the person to add as an owner and click 'Add'.</span></span>
5. <span data-ttu-id="ce404-119">После этого новому совладельцу будет отправлено электронное письмо с приглашением стать владельцем пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-119">An email is then sent to the new co-owner, as an invitation to become an owner of a package.</span></span>
6. <span data-ttu-id="ce404-120">Щелкнув ссылку в этом письме, пользователь станет совладельцем пакета со всеми правами, включая возможность удалять других владельцев пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-120">Once that user clicks the link, they are a full co-owner with full control over a package, including the ability to remove other users as owners.</span></span>

<span data-ttu-id="ce404-121">**Примечание**. Пока новый владелец не подтвердит свой статус владельца, он *не будет* указан как владелец пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-121">**NOTE**: Until the new owner confirms ownership, they *will not* be listed as an owner of a package.</span></span>
<span data-ttu-id="ce404-122">В списке текущих владельцев на странице **Управление владельцами** для него будет отображаться запись "Ожидает подтверждения".</span><span class="sxs-lookup"><span data-stu-id="ce404-122">When viewing the **Manage Owners** page, you will see a "pending approval" entry in the current owners.</span></span>
<span data-ttu-id="ce404-123">Приглашение, как и других владельцев, можно удалить.</span><span class="sxs-lookup"><span data-stu-id="ce404-123">That invitation can be removed; just as other owners can be removed.</span></span>
<span data-ttu-id="ce404-124">Процедура приглашения защищает пользователей от ошибочного добавления других пользователей в число владельцев пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-124">This process of invitations prevents users from falsely adding other users as owners of their packages.</span></span>

<span data-ttu-id="ce404-125">Обратите внимание, что метаданные "Авторы" заполняются произвольно, контролируются только "Владельцы".</span><span class="sxs-lookup"><span data-stu-id="ce404-125">Note that the "Authors" metadata is purely freeform text; only "Owners" are controlled.</span></span>


## <a name="removing-owners"></a><span data-ttu-id="ce404-126">Удаление владельцев</span><span class="sxs-lookup"><span data-stu-id="ce404-126">Removing Owners</span></span>

<span data-ttu-id="ce404-127">Если у пакета несколько владельцев и одного из них нужно удалить, это делается очень просто:</span><span class="sxs-lookup"><span data-stu-id="ce404-127">When a package has multiple owners and one needs to be removed, the process is simple:</span></span>

1. <span data-ttu-id="ce404-128">[Войдите](https://powershellgallery.com/users/account/LogOn) в коллекцию PowerShell по учетной записи текущего владельца пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-128">[Log on](https://powershellgallery.com/users/account/LogOn) to PowerShell Gallery with the account that is the current owner of a package;</span></span>
2. <span data-ttu-id="ce404-129">Перейдите на страницу пакета, открыв вкладку "Пакеты", выполнив поиск или щелкнув свое имя пользователя, и выберите пункт [**Управление моими пакетами**](https://www.powershellgallery.com/account/Packages).</span><span class="sxs-lookup"><span data-stu-id="ce404-129">Navigate to a package page using the Packages tab, searching, or clicking your username and then [**Manage My Packages**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="ce404-130">Если вход в систему выполнен владельцем пакета, слева будет доступна ссылка "Управление владельцами".</span><span class="sxs-lookup"><span data-stu-id="ce404-130">When logged on as a package's owner, there is a 'Manage Owners' link on the left side to click;</span></span>
4. <span data-ttu-id="ce404-131">Щелкните ссылку "Удалить" рядом с удаляемым владельцем.</span><span class="sxs-lookup"><span data-stu-id="ce404-131">Click the 'remove' link next to the owner to be removed.</span></span>



## <a name="transferring-package-ownership"></a><span data-ttu-id="ce404-132">Передача права собственности на пакет</span><span class="sxs-lookup"><span data-stu-id="ce404-132">Transferring Package Ownership</span></span>

<span data-ttu-id="ce404-133">В службу поддержки периодически поступают запросы о передаче права собственности на пакет от одного пользователя к другому, но почти всегда вы можете сделать это сами.</span><span class="sxs-lookup"><span data-stu-id="ce404-133">We sometimes get support requests to transfer package ownership from one user to another, but you can almost always accomplish this yourself.</span></span>
<span data-ttu-id="ce404-134">Передача владения от одного пользователя другому представляет собой простую комбинацию двух описанных выше функций.</span><span class="sxs-lookup"><span data-stu-id="ce404-134">Transferring ownership from one user to another is simply a combination of the two features above.</span></span>

1. <span data-ttu-id="ce404-135">Текущий владелец приглашает нового пользователя в качестве совладельца, а новый пользователь принимает приглашение.</span><span class="sxs-lookup"><span data-stu-id="ce404-135">The current owner invites the new user to become a co-owner and the new user accepts the invite;</span></span>
2. <span data-ttu-id="ce404-136">Новый пользователь удаляет старого пользователя из списка владельцев.</span><span class="sxs-lookup"><span data-stu-id="ce404-136">The new user removes the old user from the list of owners.</span></span>

<span data-ttu-id="ce404-137">Это действие может потребоваться по ряду причин, но процедура всегда одна и та же.</span><span class="sxs-lookup"><span data-stu-id="ce404-137">This request has come in under a couple forms but the process works the same.</span></span>

- <span data-ttu-id="ce404-138">Право собственности на пакет переходит от одного разработчика к другому.</span><span class="sxs-lookup"><span data-stu-id="ce404-138">The package ownership is changing from one developer to another</span></span>
- <span data-ttu-id="ce404-139">Пакет был ошибочно опубликован с помощью другой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ce404-139">The package was accidentally published using the wrong account</span></span>


## <a name="orphaned-packages"></a><span data-ttu-id="ce404-140">У пакетов нет владельца.</span><span class="sxs-lookup"><span data-stu-id="ce404-140">Orphaned Packages</span></span>

<span data-ttu-id="ce404-141">Возможна и еще одна ситуация, но встречается она нечасто.</span><span class="sxs-lookup"><span data-stu-id="ce404-141">One last scenario has occurred, but not many times.</span></span>
<span data-ttu-id="ce404-142">Пакет остается без владельца, а учетную запись единственного владельца пакета нельзя использовать, чтобы добавить новых владельцев.</span><span class="sxs-lookup"><span data-stu-id="ce404-142">Packages have become orphans and the only package owner account cannot be used to add new owners.</span></span>
<span data-ttu-id="ce404-143">Приведем несколько примеров такой ситуации.</span><span class="sxs-lookup"><span data-stu-id="ce404-143">Here are some examples of this scenario:</span></span>

- <span data-ttu-id="ce404-144">Учетная запись владельца связана с адресом электронной почты, который больше не существует, либо пользователь забыл пароль.</span><span class="sxs-lookup"><span data-stu-id="ce404-144">The owner's account is associated with an email address that no longer exists and the user has forgotten their password</span></span>
- <span data-ttu-id="ce404-145">Зарегистрированный владелец уволился из компании, в которой был создан пакет, и с ним не удается связаться, чтобы передать право собственности на пакет.</span><span class="sxs-lookup"><span data-stu-id="ce404-145">The registered owner has left the company that produces the package and cannot be reached to update the package ownership</span></span>
- <span data-ttu-id="ce404-146">Из-за ошибки, затронувшей небольшое количество пакетов, пакет остался в коллекции без владельца.</span><span class="sxs-lookup"><span data-stu-id="ce404-146">Due to a bug that has only affected a handful of packages, the package is somehow ownerless on the gallery</span></span>

<span data-ttu-id="ce404-147">Администраторы коллекции PowerShell имеют доступ к ссылке "Управление владельцами" любого пакета.</span><span class="sxs-lookup"><span data-stu-id="ce404-147">The PowerShell Gallery Administrators can access the 'Manage Owners' link for any package.</span></span>
<span data-ttu-id="ce404-148">Если вы являетесь действительным владельцем пакета и не можете связаться с текущим владельцем, чтобы получить право собственности, щелкните ссылку "Сообщить о нарушении" в коллекции, чтобы связаться с администраторами коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-148">If you are the rightful owner of a package and cannot reach the current owner to gain ownership permissions, then use the 'Report Abuse' link on the gallery to reach the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="ce404-149">Мы проверим ваше право собственности на этот пакет.</span><span class="sxs-lookup"><span data-stu-id="ce404-149">We will then follow a process to verify your ownership of the package.</span></span>
<span data-ttu-id="ce404-150">Если подтвердится, что владельцем пакета должны быть вы, мы воспользуемся ссылкой "Управление владельцами" и отправим вам приглашение стать владельцем.</span><span class="sxs-lookup"><span data-stu-id="ce404-150">If we determine you should be an owner of the package, we will use the 'Manage Owners' link for the package ourselves and send you the invite to become an owner.</span></span>
<span data-ttu-id="ce404-151">Мы сделаем это только после того, как убедимся, что вы должны быть владельцем; дальнейший порядок действий зависит от ситуации.</span><span class="sxs-lookup"><span data-stu-id="ce404-151">We will only do this after verifying that you should be an owner and the process for this varies by circumstances.</span></span>
<span data-ttu-id="ce404-152">Как правило, мы пытаемся связаться с владельцем проекта, используя URL-адрес проекта этого пакета, но можем также искать его в социальных сетях, с помощью электронной почты или других средств.</span><span class="sxs-lookup"><span data-stu-id="ce404-152">Often times, we will use the package's Project URL to find a way to contact the project owner, but we may also use Twitter, Email, or other means for contacting the project owner.</span></span>

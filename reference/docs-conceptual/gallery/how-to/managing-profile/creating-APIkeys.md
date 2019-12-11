---
ms.date: 09/10/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Управление ключами API
ms.openlocfilehash: 954eb27c25babdb8efe50c13caf5f2d287c6b3e3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328295"
---
# <a name="managing-api-keys"></a><span data-ttu-id="d7b6a-103">Управление ключами API</span><span class="sxs-lookup"><span data-stu-id="d7b6a-103">Managing API keys</span></span>

<span data-ttu-id="d7b6a-104">В коллекции PowerShell доступна возможность создания нескольких ключей API для поддержки ряда требований к публикации.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-104">The PowerShell Gallery supports creating multiple API keys to support a range of publishing requirements.</span></span> <span data-ttu-id="d7b6a-105">Ключ API можно применять к одному или нескольким пакетам, он предоставляет определенные привилегии и имеет срок действия.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-105">An API key can apply to one or more packages, grants specific privileges, and has an expiration date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7b6a-106">Пользователи, которые выполняли публикацию в коллекцию PowerShell до появления ключей API с заданной областью действия, получат ключ API полного доступа.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-106">Users who published to the PowerShell Gallery prior to the introduction of scoped API keys will have a "Full access API key".</span></span> <span data-ttu-id="d7b6a-107">В ключах полного доступа отсутствуют усовершенствования системы безопасности, встроенные в ключи API с заданной областью.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-107">The full access keys do not have the security improvements built into scoped API keys.</span></span> <span data-ttu-id="d7b6a-108">Ключи полного доступа имеют неограниченный срок действия и применяются ко всем элементам, принадлежащим пользователю.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-108">The full access keys never expires and apply to everything owned by the user.</span></span> <span data-ttu-id="d7b6a-109">Удаленный ключ нельзя создать повторно.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-109">If you delete this key, it cannot be recreated.</span></span>

<span data-ttu-id="d7b6a-110">Ниже показаны параметры, доступные при создании ключа API с заданной областью.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-110">The following image shows the options available when creating a scoped API key.</span></span>

![Создание ключей API](../../Images/PSGallery_KeyScoped.png)

<span data-ttu-id="d7b6a-112">В этом примере создан ключ API с именем **AzureRMDataFactory**.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-112">In this example, we created an API key named **AzureRMDataFactory**.</span></span> <span data-ttu-id="d7b6a-113">Это значение ключа можно использовать для отправки пакетов, имена которых начинаются с AzureRM.DataFactory. Ключ действителен в течение 365 дней.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-113">This key value can be used to push packages with names that begin with 'AzureRM.DataFactory' and is valid for 365 days.</span></span> <span data-ttu-id="d7b6a-114">Это типичный сценарий, когда разные команды в одной организации работают с разными пакетами.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-114">This is a typical scenario when different teams within the same organization work on different packages.</span></span> <span data-ttu-id="d7b6a-115">У членов группы есть ключ, который предоставляет им привилегии, необходимые для работы с определенным пакетом.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-115">The members of the team have a key that grants them privileges for the specific package they work on.</span></span>
<span data-ttu-id="d7b6a-116">Поскольку ключ имеет ограниченный срок действия, использовать устаревшие или забытые ключи невозможно.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-116">The expiration value prevents the use of stale or forgotten keys.</span></span>

## <a name="using-glob-patterns"></a><span data-ttu-id="d7b6a-117">Использование стандартных масок</span><span class="sxs-lookup"><span data-stu-id="d7b6a-117">Using glob patterns</span></span>

<span data-ttu-id="d7b6a-118">При работе с несколькими пакетами можно использовать стандартные маски для сопоставления нескольких пакетов в виде группы.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-118">If you work on multiple packages, you can use globbing patterns to match multiple packages as a group.</span></span> <span data-ttu-id="d7b6a-119">Разрешения ключа API применяются ко всем новым пакетам, соответствующим стандартной маске.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-119">API key permissions apply to all new packages matching the glob pattern.</span></span> <span data-ttu-id="d7b6a-120">Например, в предыдущем примере используется значение **стандартной маски** AzureRM.DataFactory \*.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-120">For example, the previous example uses a **Glob Pattern** value of 'AzureRM.DataFactory\*'.</span></span> <span data-ttu-id="d7b6a-121">С помощью этого ключа можно отправить пакет AzureRm.DataFactoryV2.Netcore, так как пакет соответствует стандартной маске.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-121">You can push a package named 'AzureRm.DataFactoryV2.Netcore' using this key since the package matches the glob pattern.</span></span>

## <a name="create-api-keys-securely"></a><span data-ttu-id="d7b6a-122">Безопасное создание ключей API</span><span class="sxs-lookup"><span data-stu-id="d7b6a-122">Create API keys securely</span></span>

<span data-ttu-id="d7b6a-123">В целях безопасности значение созданного ключа никогда не отображается на экране и доступно только с помощью кнопки копирования, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-123">For security, a newly created key value is never shown on the screen and is only available with the Copy button, as shown below.</span></span>

![Получение нового значения ключа API](../../Images/PSGallery_CopyCreatedKey.png)

> [!IMPORTANT]
> <span data-ttu-id="d7b6a-125">Скопировать значение ключа API можно только сразу после его создания или обновления.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-125">You can only copy the API key value immediately after creating or refreshing it.</span></span> <span data-ttu-id="d7b6a-126">Оно не будет отображается и будет недоступно после обновления страницы.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-126">It will not be displayed, and will not be accessible again after the page is refreshed.</span></span> <span data-ttu-id="d7b6a-127">В случае утери значения ключа необходимо воспользоваться кнопкой "Повторно создать" и скопировать ключ после его повторного создания.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-127">If you lose the key value, you must use Regenerate, and copy the key after it is regenerated.</span></span>

## <a name="key-permissions-and-expiration"></a><span data-ttu-id="d7b6a-128">Разрешения и срок действия ключа</span><span class="sxs-lookup"><span data-stu-id="d7b6a-128">Key permissions and expiration</span></span>

<span data-ttu-id="d7b6a-129">Ключи API с заданной областью можно использовать для назначения следующих разрешений:</span><span class="sxs-lookup"><span data-stu-id="d7b6a-129">Scoped API keys can assign any of the following permissions:</span></span>

- <span data-ttu-id="d7b6a-130">отправка новых пакетов;</span><span class="sxs-lookup"><span data-stu-id="d7b6a-130">Push new packages</span></span>
- <span data-ttu-id="d7b6a-131">отправка новых пакетов или обновление пакетов;</span><span class="sxs-lookup"><span data-stu-id="d7b6a-131">Push new or update packages</span></span>
- <span data-ttu-id="d7b6a-132">удаление пакетов из списка.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-132">Unlist packages</span></span>

<span data-ttu-id="d7b6a-133">Каждый новый ключ имеет срок действия.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-133">Every new key has an expiration.</span></span> <span data-ttu-id="d7b6a-134">Значение срока действия измеряется в днях.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-134">The expiration value is measured in days.</span></span> <span data-ttu-id="d7b6a-135">Ниже приведены возможные значения срока действия.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-135">The possible values for expiration are:</span></span>

- <span data-ttu-id="d7b6a-136">1 день</span><span class="sxs-lookup"><span data-stu-id="d7b6a-136">1 day</span></span>
- <span data-ttu-id="d7b6a-137">90 дней</span><span class="sxs-lookup"><span data-stu-id="d7b6a-137">90 days</span></span>
- <span data-ttu-id="d7b6a-138">180 дней</span><span class="sxs-lookup"><span data-stu-id="d7b6a-138">180 days</span></span>
- <span data-ttu-id="d7b6a-139">270 дней</span><span class="sxs-lookup"><span data-stu-id="d7b6a-139">270 days</span></span>
- <span data-ttu-id="d7b6a-140">365 дней (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d7b6a-140">365 days (default)</span></span>

<span data-ttu-id="d7b6a-141">После создания ключа эти параметры изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-141">These settings cannot be changed once the key is created.</span></span> <span data-ttu-id="d7b6a-142">Нельзя создать ключ с неограниченным сроком действия.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-142">You cannot create a new key that never expires.</span></span>

## <a name="editing-and-deleting-existing-api-keys"></a><span data-ttu-id="d7b6a-143">Изменение и удаление существующих ключей API</span><span class="sxs-lookup"><span data-stu-id="d7b6a-143">Editing and deleting existing API keys</span></span>

<span data-ttu-id="d7b6a-144">Можно изменить некоторые параметры существующего ключа.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-144">You can change some settings of an existing key.</span></span> <span data-ttu-id="d7b6a-145">Как уже отмечалось, нельзя изменить область безопасности для существующего ключа API или изменить срок его действия.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-145">As previously noted, you cannot modify the security scope for an existing API key or change the expiration.</span></span> <span data-ttu-id="d7b6a-146">На следующем снимке экрана показаны изменяемые параметры.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-146">The changeable options are shown in the following screenshot:</span></span>

![Получение нового значения ключа API](../../Images/PSGallery_EditAPIKey.png)

<span data-ttu-id="d7b6a-148">Чтобы изменить пакеты, управляемые с помощью ключа, можно выбрать отдельные пакеты в списке или изменить стандартную маску.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-148">To change the packages controlled by a key, you can choose individual packages from the list or change the glob pattern.</span></span>

<span data-ttu-id="d7b6a-149">Нажмите кнопку **Повторно создать**, чтобы создать значение ключа.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-149">Clicking **Regenerate** creates a new key value.</span></span> <span data-ttu-id="d7b6a-150">Так же, как при первоначальном создании ключа, необходимо **скопировать** значение ключа сразу же после его обновления.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-150">Just like when you initially created the key, you must **Copy** the key value immediately after updating it.</span></span> <span data-ttu-id="d7b6a-151">После закрытия этой страницы возможность **копирования** будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-151">The **Copy** option is not available once you leave this page.</span></span>

<span data-ttu-id="d7b6a-152">После нажатия кнопки **Удалить** появится сообщение с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-152">Clicking **Delete** displays a confirmation message.</span></span> <span data-ttu-id="d7b6a-153">После удаления ключ будет непригоден для использования.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-153">Once a key is deleted, it will be unusable.</span></span>

## <a name="key-expiration"></a><span data-ttu-id="d7b6a-154">Окончание срока действия ключа</span><span class="sxs-lookup"><span data-stu-id="d7b6a-154">Key expiration</span></span>

<span data-ttu-id="d7b6a-155">За десять дней до окончания срока действия коллекция PowerShell отправляет владельцу ключа API предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-155">Ten days before the expiration, the PowerShell Gallery sends a warning email the account holder of the API key.</span></span> <span data-ttu-id="d7b6a-156">После окончания срока действия ключ будет непригоден для использования.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-156">After expiration, the key is unusable.</span></span> <span data-ttu-id="d7b6a-157">Предупреждение с перечнем недействительных ключей отображается в верхней части страницы управления ключами API.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-157">A warning message is displayed at the top of the API key management page showing which keys are no longer valid.</span></span> <span data-ttu-id="d7b6a-158">Можно создать новое значение ключа.</span><span class="sxs-lookup"><span data-stu-id="d7b6a-158">You can generate a new key value.</span></span>

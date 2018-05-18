---
ms.date: 03/27/2018
contributor: JKeithB
ms.topic: conceptual
keywords: коллекция,powershell,psgallery,GDPR
title: Соответствие коллекции PowerShell регламенту GDPR
ms.openlocfilehash: 0a9e76325a2a5cf8f509e1a6317c8ed88d133f1d
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="powershell-gallery-gdpr-compliance"></a><span data-ttu-id="38182-103">Соответствие коллекции PowerShell регламенту GDPR</span><span class="sxs-lookup"><span data-stu-id="38182-103">PowerShell Gallery GDPR compliance</span></span>

## <a name="overview"></a><span data-ttu-id="38182-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="38182-104">Overview</span></span>

<span data-ttu-id="38182-105">В мае 2018 г. вступает в силу европейский закон о конфиденциальности — Общий регламент по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="38182-105">In May 2018, a European privacy law, the General Data Protection Regulation (GDPR), takes effect.</span></span>
<span data-ttu-id="38182-106">GDPR налагает новые требования на компании, государственные учреждения, некоммерческие и другие организации, которые предоставляют товары и услуги жителям ЕС либо собирают и анализируют данные, связанные с резидентами ЕС.</span><span class="sxs-lookup"><span data-stu-id="38182-106">The GDPR imposes new rules on companies, government agencies, non-profits, and other organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data tied to EU residents.</span></span>
<span data-ttu-id="38182-107">GDPR применяется независимо от того, где вы находитесь.</span><span class="sxs-lookup"><span data-stu-id="38182-107">The GDPR applies no matter where you are located.</span></span>

> [!NOTE]
> <span data-ttu-id="38182-108">Эта статья описывает шаги по удалению персональных данных из коллекции PowerShell и помогает вам выполнить обязательства в рамках GDPR.</span><span class="sxs-lookup"><span data-stu-id="38182-108">This article provides steps for how to delete personal data from the PowerShell Gallery and can be used to support your obligations under the GDPR.</span></span> <span data-ttu-id="38182-109">Если вы ищете общие сведения о GDPR, см. [раздел о GDPR на Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span><span class="sxs-lookup"><span data-stu-id="38182-109">If you’re looking for general info about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="personally-identifiable-data"></a><span data-ttu-id="38182-110">Персональные данные</span><span class="sxs-lookup"><span data-stu-id="38182-110">Personally identifiable data</span></span>

<span data-ttu-id="38182-111">Коллекция PowerShell хранит следующие сведения, в том числе и предоставляемые пользователями, куда могут входить и персональные данные.</span><span class="sxs-lookup"><span data-stu-id="38182-111">The PowerShell Gallery stores the following information that may be provided by users, which may contain personal information:</span></span>

* <span data-ttu-id="38182-112">Учетная запись коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="38182-112">PowerShell Gallery account</span></span>
* <span data-ttu-id="38182-113">Элементы, опубликованные в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="38182-113">Items published to the PowerShell Gallery</span></span>
* <span data-ttu-id="38182-114">Переписка с группой коллекции PowerShell по электронной почте</span><span class="sxs-lookup"><span data-stu-id="38182-114">Email correspondence with the PowerShell Gallery team</span></span>

<span data-ttu-id="38182-115">Большинство пользователей не создает учетную запись коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-115">Most users do not create a PowerShell Gallery account.</span></span>
<span data-ttu-id="38182-116">Учетная запись не требуется, если только вы не захотите опубликовать элемент или воспользоваться функцией Contact Owner (Связаться с владельцем) в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-116">An account is not required unless you are going to publish an item or use the "Contact Owner" feature in the PowerShell Gallery.</span></span>
<span data-ttu-id="38182-117">Кроме переписки по электронной почте, начатой пользователем, коллекция PowerShell не сохраняет персональные данные для пользователей без учетной записи.</span><span class="sxs-lookup"><span data-stu-id="38182-117">Other than email correspondence initiated by the user, the PowerShell Gallery does not store personally identifiable data for users who have not created an account.</span></span>

<span data-ttu-id="38182-118">Пользователи, создающие учетную запись, могут публиковать элементы в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-118">Users who create a PowerShell Gallery account can publish items to the PowerShell Gallery.</span></span>
<span data-ttu-id="38182-119">Эти элементы должны быть кодом PowerShell, но могут содержать и другие сведения, включая личные данные.</span><span class="sxs-lookup"><span data-stu-id="38182-119">Those items are expected to be PowerShell code, but may contain other information including personal information.</span></span>
<span data-ttu-id="38182-120">Приведенные ниже сведения показывают, как получить все элементы, опубликованные вами в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-120">The information below will show how you can get all the items you have published to the PowerShell Gallery.</span></span>

## <a name="dsr-export-of-powershell-gallery-data"></a><span data-ttu-id="38182-121">Экспорт данных из коллекции PowerShell по запросу DSR</span><span class="sxs-lookup"><span data-stu-id="38182-121">DSR Export of PowerShell Gallery Data</span></span>

<span data-ttu-id="38182-122">Следующие разделы описывают, как коллекция PowerShell поддерживает запросы субъекта данных (DSR), и поясняют, как экспортировать данные, хранящиеся в коллекции PowerShell, и запросить их удаление.</span><span class="sxs-lookup"><span data-stu-id="38182-122">The following sections describe how the PowerShell Gallery supports data subject requests (DSR), by explaining how to export information stored in the PowerShell Gallery, and how to request deletion of this information.</span></span>

### <a name="email"></a><span data-ttu-id="38182-123">Электронная почта</span><span class="sxs-lookup"><span data-stu-id="38182-123">Email</span></span>

<span data-ttu-id="38182-124">Переписка по электронной почте может содержать любые из следующих сведений.</span><span class="sxs-lookup"><span data-stu-id="38182-124">Email correspondence may include any of the following:</span></span>

* <span data-ttu-id="38182-125">Сообщение, отправленное владельцам элементов в коллекции PowerShell, если анализ кода выявил проблему с любым из опубликованных ими элементов.</span><span class="sxs-lookup"><span data-stu-id="38182-125">Email sent to the owners of PowerShell Gallery items if the code analysis scans detected an issue with any item they have published to the PowerShell Gallery</span></span>
* <span data-ttu-id="38182-126">Сообщение, отправленное любым сотрудником группы коллекции PowerShell с использованием адреса электронной почты на странице контактов (cgadmin@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="38182-126">Email sent by anyone to the PowerShell Gallery team using the email address in the "Contact Us" page (cgadmin@microsoft.com)</span></span>
* <span data-ttu-id="38182-127">Зарегистрированные пользователи, использующие функцию Contact Owner (Связаться с владельцем) для отправки сообщения владельцу элемента.</span><span class="sxs-lookup"><span data-stu-id="38182-127">Registered users who use the "Contact Owner" feature in the PowerShell Gallery to send email to the owner of an item in the PowerShell Gallery</span></span>

<span data-ttu-id="38182-128">Для сообщений, которыми пользователи обмениваются с группой коллекции PowerShell, действует политика хранения в течение 90 дней для проведения возможных расследований в случае обнаружения вредоносного кода в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-128">Emails sent by or to the PowerShell Gallery have a retention policy of 90 days to support possible security investigations should malicious code be discovered on the PowerShell Gallery.</span></span>
<span data-ttu-id="38182-129">Через 90 дней сообщения удаляются.</span><span class="sxs-lookup"><span data-stu-id="38182-129">Emails are deleted by policy after 90 days.</span></span>

<span data-ttu-id="38182-130">Вы можете запросить копии всех сообщений, которыми вы обменивались с группой коллекции PowerShell со своего адреса электронной почты за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="38182-130">You may request copies of all emails sent to or from your email address and the PowerShell Gallery within the previous 90 days.</span></span>
<span data-ttu-id="38182-131">Чтобы запросить эту переписку, отправьте на адрес cgadmin@microsoft.com сообщение электронной почты с заголовком DSR Request for emails relating to this account (Запрос DSR на получение сообщений электронной почты, связанных с этой учетной записью).</span><span class="sxs-lookup"><span data-stu-id="38182-131">To request this correspondence, send an email to cgadmin@microsoft.com, with the title: "DSR Request for emails relating to this account".</span></span>
<span data-ttu-id="38182-132">В тексте сообщения укажите, какую именно информацию вы запрашиваете (например, попросите отправить все сообщения электронной почты, отправленные или полученные с помощью этого адреса электронной почты). Все сообщения, связанные с вашим адресом электронной почты, за 90 дней будут отправлены вам в течение 7 рабочих дней.</span><span class="sxs-lookup"><span data-stu-id="38182-132">In the body of the message, state what information you are requesting (for example: Please send all emails sent to or received from this email address.) All emails involving your email address within 90 days of the request will be sent within 7 business days.</span></span>

### <a name="powershell-gallery-account-information"></a><span data-ttu-id="38182-133">Информация об учетной записи коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="38182-133">PowerShell Gallery Account Information</span></span>

<span data-ttu-id="38182-134">Если вы создали учетную запись коллекции PowerShell, то можете найти все хранящиеся в коллекции персональные данные, сделав следующее.</span><span class="sxs-lookup"><span data-stu-id="38182-134">If you have created a PowerShell Gallery account, you can find all personal information that has been stored in PowerShell Gallery by taking the following steps:</span></span>

1. <span data-ttu-id="38182-135">Войдите в коллекцию PowerShell и щелкните свое имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="38182-135">Sign in to the PowerShell Gallery, then click on your username</span></span>
2. <span data-ttu-id="38182-136">Отображается страница учетной записи, где указан адрес электронной почты, используемый для этой учетной записи коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-136">The next page displayed is the Account page, which shows the email address used for the PowerShell Gallery account</span></span>

<span data-ttu-id="38182-137">Если вы создали в коллекции PowerShell несколько учетных записей, потребуется повторить эти шаги для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="38182-137">If you have created more than one account in the PowerShell Gallery, you will need to repeat these steps for each account.</span></span>

### <a name="items-in-the-powershell-gallery"></a><span data-ttu-id="38182-138">Элементы в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="38182-138">Items in the PowerShell Gallery</span></span>

<span data-ttu-id="38182-139">Чтобы упростить экспорт элементов, опубликованных в коллекции PowerShell, корпорация Майкрософт опубликовала сценарий GetPSGalleryItemsForAuthor в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-139">To facilitate exporting items published to the PowerShell Gallery, we have published the script "GetPSGalleryItemsForAuthor" to the PowerShell Gallery.</span></span>
<span data-ttu-id="38182-140">Он экспортирует копию каждой версии каждого элемента, помещенного в коллекцию PowerShell, на основе хранящихся в элементе сведений об авторе.</span><span class="sxs-lookup"><span data-stu-id="38182-140">This script exports a copy of every version of every item put into the PowerShell Gallery based on the author information stored in the item.</span></span>

> [!NOTE]
> <span data-ttu-id="38182-141">Автор сохраняется в манифесте элемента при публикации элемента.</span><span class="sxs-lookup"><span data-stu-id="38182-141">The Author is stored in the item manifest when you publish your item.</span></span>
> <span data-ttu-id="38182-142">Нет никакой гарантии, что автор относится к тому же удостоверению, что и учетная запись, используемая вами в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-142">There is no guarantee that the Author is the same identity as the account you use in the PowerShell Gallery.</span></span>
> <span data-ttu-id="38182-143">Если в поле "Автор" вы используете другое значение, нужно указать его при использовании этого сценария.</span><span class="sxs-lookup"><span data-stu-id="38182-143">If you use some other value in the Author field, you will need to supply that value when using this script.</span></span>

<span data-ttu-id="38182-144">Вы можете скачать сценарий, используя следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38182-144">You may download the script by using the following PowerShell command:</span></span>

```powershell
Save-Script GetPSGalleryItemsForAuthor -path <local folder location> -repository psgallery
```

<span data-ttu-id="38182-145">После этого его можно запустить напрямую с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38182-145">You can then run the script directly, by running the following PowerShell commands:</span></span>

```powershell
cd <local folder location >
.\GetPSGalleryItemsForAuthor.ps1
```

<span data-ttu-id="38182-146">Вам будет предложено указать автора и папку в системе, куда требуется сохранить элементы.</span><span class="sxs-lookup"><span data-stu-id="38182-146">You will be prompted to supply the Author and a folder on your system where you want the items to be saved.</span></span>

## <a name="deleting-personal-data-from-the-powershell-gallery"></a><span data-ttu-id="38182-147">Удаление персональных данных из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="38182-147">Deleting Personal Data From The PowerShell Gallery</span></span>

<span data-ttu-id="38182-148">Чтобы удалить учетную запись коллекции PowerShell или любой принадлежащий вам элемент в этой коллекции, отправьте на адрес cgadmin@microsoft.com сообщение электронной почты с заголовком GDPR Request for items relating to this account (Запрос GDPR по элементам, связанным с этой учетной записью).</span><span class="sxs-lookup"><span data-stu-id="38182-148">To delete your PowerShell Gallery account or any item you own in the PowerShell Gallery, send email to cgadmin@microsoft.com with the title: "GDPR Request for items relating to this account".</span></span>
<span data-ttu-id="38182-149">В тексте сообщения укажите, какую информацию требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="38182-149">In the body of the message state what information you want deleted.</span></span> <span data-ttu-id="38182-150">Например:</span><span class="sxs-lookup"><span data-stu-id="38182-150">For example:</span></span>

* <span data-ttu-id="38182-151">попросите удалить версию x.y.z своего элемента "имя элемента";</span><span class="sxs-lookup"><span data-stu-id="38182-151">Please delete version x.y.z of my item "item name"</span></span>
* <span data-ttu-id="38182-152">попросите удалить все версии своего элемента "имя элемента";</span><span class="sxs-lookup"><span data-stu-id="38182-152">Please delete all versions of my item "item name"</span></span>
* <span data-ttu-id="38182-153">попросите удалить свою учетную запись коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38182-153">Please delete my PowerShell Gallery account</span></span>

<span data-ttu-id="38182-154">Администраторы коллекции PowerShell ответят вам в течение 7 рабочих дней.</span><span class="sxs-lookup"><span data-stu-id="38182-154">The PowerShell Gallery administrators will reply within 7 business days.</span></span>
<span data-ttu-id="38182-155">Указанные элементы будут удалены в течение 30 дней после отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="38182-155">The items specified will be deleted within 30 days after the request is sent.</span></span>

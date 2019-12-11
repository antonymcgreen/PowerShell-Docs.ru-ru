---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Отправка отзывов через социальные сети или комментарии
ms.openlocfilehash: 95e5db22b94151c3974189c30f1d4e580b47eeb5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71327885"
---
# <a name="providing-feedback-via-social-media-or-comments"></a><span data-ttu-id="fd81a-103">Отправка отзывов через социальные сети или комментарии</span><span class="sxs-lookup"><span data-stu-id="fd81a-103">Providing Feedback via social media or comments</span></span>

<span data-ttu-id="fd81a-104">Коллекция PowerShell предоставляет пользователям два способа отправки общедоступных отзывов о пакете:</span><span class="sxs-lookup"><span data-stu-id="fd81a-104">The PowerShell Gallery supports two approaches for users to provide public feedback on a package:</span></span>

- <span data-ttu-id="fd81a-105">Ссылки слева на странице, чтобы поделиться пакетом в социальных сетях Facebook, LinkedIn и Twitter.</span><span class="sxs-lookup"><span data-stu-id="fd81a-105">Use the links on the left edge to "share" a package in Facebook, LinkedIn, or Twitter social media sites;</span></span>
- <span data-ttu-id="fd81a-106">Функция комментариев, чтобы опубликовать комментарии к пакету и сделать их доступными для авторов опубликованных пакетов.</span><span class="sxs-lookup"><span data-stu-id="fd81a-106">Use the Comment feature to post comments on a package, and to allow Authors to watch for comments on packages they publish.</span></span>

## <a name="social-media-feedback"></a><span data-ttu-id="fd81a-107">Отзывы в социальных сетях</span><span class="sxs-lookup"><span data-stu-id="fd81a-107">Social Media Feedback</span></span>

<span data-ttu-id="fd81a-108">Для каждого пакета в коллекции PowerShell есть ссылки на сайты Facebook, LinkedIn и Twitter в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="fd81a-108">On the left side of the page for each package in the PowerShell Gallery there are links for Facebook, LinkedIn, and Twitter.</span></span>
<span data-ttu-id="fd81a-109">Если вы щелкнете их, откроется сайт социальной сети и вы сможете быстро поделиться ссылкой на этот пакет.</span><span class="sxs-lookup"><span data-stu-id="fd81a-109">Clicking on these links will open the social media site, and allow quickly sharing a link to the package.</span></span>

<span data-ttu-id="fd81a-110">Пользователям необходимо войти на сайт, на котором они хотят поделиться пакетом коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd81a-110">Users must log in to the site they have chosen in order to share the PowerShell Gallery package.</span></span>

<span data-ttu-id="fd81a-111">Мы рекомендуем делать это, если пользователь считает, что следует посоветовать этот пакет другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="fd81a-111">Users are encouraged to do this if they find that a package is something they would recommend to others.</span></span>
<span data-ttu-id="fd81a-112">Коллекция PowerShell проверяет, сколько раз пакет был "рекомендован" на каждом сайте социальной сети, и отображает эти данные по пакету для каждого сайта социальной сети.</span><span class="sxs-lookup"><span data-stu-id="fd81a-112">The PowerShell Gallery will check each social media site for "shares" of the package, and display how many times that package has been shared in each of the social media sites.</span></span>
<span data-ttu-id="fd81a-113">Так как отображается только количество рекомендаций, другие пользователи воспримут это как отметку "Нравится".</span><span class="sxs-lookup"><span data-stu-id="fd81a-113">Since this shows only the count of times something has been shared, it will be interpreted other users as "liking" the package.</span></span>

## <a name="comments"></a><span data-ttu-id="fd81a-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fd81a-114">Comments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd81a-115">Возможность комментирования Livefyre предоставляется сторонним поставщиком и больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fd81a-115">Livefyre commenting is provided by a third-party vendor and is no longer supported.</span></span>
> <span data-ttu-id="fd81a-116">С 1 мая 019 г. возможность комментирования Livefyre больше не будут доступна в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd81a-116">Livefyre commenting will no longer be available on the PowerShell Gallery starting 05/01/2019.</span></span> 

<span data-ttu-id="fd81a-117">Коллекции PowerShell используют службу LiveFyre, чтобы позволить пользователям комментировать пакеты.</span><span class="sxs-lookup"><span data-stu-id="fd81a-117">The PowerShell Gallery uses the LiveFyre service to allow users to comment on packages.</span></span>
<span data-ttu-id="fd81a-118">Пользователи, которые хотят поделиться советом или отзывом, могут использовать эту функцию, чтобы оставить отзыв, который виден всем, кто посещает страницу пакета.</span><span class="sxs-lookup"><span data-stu-id="fd81a-118">Users who have recommendations or feedback can use this feature to provide feedback that is visible to anyone who visits the package page.</span></span>
<span data-ttu-id="fd81a-119">Владельцы пакетов могут подписаться на отзывы и получать уведомления, когда кто-то публикует комментарий.</span><span class="sxs-lookup"><span data-stu-id="fd81a-119">Package owners can Follow this feedback, and be notified when someone posts a comment.</span></span>

<span data-ttu-id="fd81a-120">Система комментариев основана на отдельной службе LiveFyre. Этой службой не управляет корпорация Майкрософт, и она требует использования уникального имени для входа.</span><span class="sxs-lookup"><span data-stu-id="fd81a-120">The Comment system is based on LiveFyre, which is a separate service that is not managed by Microsoft, and requires unique login to use.</span></span>
<span data-ttu-id="fd81a-121">Когда вы решите впервые оставить комментарий или подписаться на комментарии к одному из своих пакетов, вам будет предложено создать учетную запись LiveFyre.</span><span class="sxs-lookup"><span data-stu-id="fd81a-121">The first time you choose to leave a comment or follow comments on one of your packages, you will be prompted to create a LiveFyre account.</span></span>

<span data-ttu-id="fd81a-122">Если вы создали учетную запись LiveFyre и вошли в систему, вы можете создать комментарий с отзывом о пакете, а затем щелкнуть "Опубликовать комментарий...". Комментарий появится не сразу.</span><span class="sxs-lookup"><span data-stu-id="fd81a-122">If you have created a LiveFyre account and logged in, you can craft a comment that provides feedback on the package, then click on "Post comment..." The comment will not be visible immediately.</span></span>
<span data-ttu-id="fd81a-123">Комментарии к пакетам коллекции модерируют администраторы коллекции PowerShell. Модераторы просматривают все сообщения перед их публикацией и отображением для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd81a-123">Comments for gallery packages are moderated by the PowerShell Gallery administrators, and all posts are reviewed by the moderators before being published and visible to others.</span></span>
<span data-ttu-id="fd81a-124">Наша цель при модерировании комментариев состоит в том, чтобы они соответствовали нормам общественного поведения согласно [условиям использования](https://www.powershellgallery.com/policies/Terms) коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd81a-124">Our purpose in moderating the comments is to ensure that they align with public behavior consistent with the PowerShell Gallery [Terms of Use](https://www.powershellgallery.com/policies/Terms).</span></span>

<span data-ttu-id="fd81a-125">Мы рекомендуем владельцам пакетов подписываться на комментарии, которые публикуются в LiveFyre.</span><span class="sxs-lookup"><span data-stu-id="fd81a-125">Package owners are encouraged to Follow comments that are posted to LiveFyre.</span></span>
<span data-ttu-id="fd81a-126">Для этого необходима учетная запись LiveFyre. Мы советуем использовать тот же адрес электронной почты, который используется при публикации пакета в LiveFyre.</span><span class="sxs-lookup"><span data-stu-id="fd81a-126">A LiveFyre account is required, and it is recommended to use the same email address you use for publishing your package in LiveFyre.</span></span>
<span data-ttu-id="fd81a-127">Чтобы подписаться на комментарии, зайдите в LiveFyre и перейдите к любому пакету, где вы числитесь владельцем.</span><span class="sxs-lookup"><span data-stu-id="fd81a-127">To Follow comments, log into LiveFyre, and navigate to any package where you are listed as an Owner.</span></span>
<span data-ttu-id="fd81a-128">Под полем комментариев под каждым пакетом вы увидите кнопку +Follow (Подписаться).</span><span class="sxs-lookup"><span data-stu-id="fd81a-128">Below the Comment box at the bottom of each package you will see "+Follow".</span></span>
<span data-ttu-id="fd81a-129">После того как вы щелкните ее, от LiveFyre будут приходить уведомления по зарегистрированному адресу электронной почты каждый раз, когда будут публиковаться новые комментарии к пакету.</span><span class="sxs-lookup"><span data-stu-id="fd81a-129">Once you click on this, LiveFyre will send an email to the registered email address any time new comments made on the package.</span></span>

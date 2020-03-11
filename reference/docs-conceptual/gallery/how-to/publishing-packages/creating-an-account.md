---
ms.date: 09/11/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Создание учетной записи коллекции PowerShell
ms.openlocfilehash: f43d7e65bb8bf9a9bbdda9790cc622786377fa38
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278792"
---
# <a name="creating-a-powershell-gallery-account"></a><span data-ttu-id="6747e-103">Создание учетной записи коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="6747e-103">Creating a PowerShell Gallery account</span></span>

<span data-ttu-id="6747e-104">Перед публикацией чего-либо в коллекцию PowerShell необходимо создать учетную запись коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6747e-104">You must create a PowerShell Gallery account before publishing anything to the PowerShell Gallery.</span></span>
<span data-ttu-id="6747e-105">Учетные записи коллекции PowerShell должны быть связаны с учетной записью входа с поддержкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6747e-105">PowerShell Gallery accounts must be linked to an email-enabled login account.</span></span> <span data-ttu-id="6747e-106">Эта учетная запись может быть учетной записью Azure Active Directory или идентификатором Майкрософт, таким как учетная запись электронной почты outlook.com или hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="6747e-106">This account can be an Azure Active Directory account or a Microsoft ID, like an email account from outlook.com or hotmail.com.</span></span>

<span data-ttu-id="6747e-107">Чтобы создать учетную запись коллекции PowerShell, перейдите на веб-сайт по адресу [https://PowerShellGallery.com](https://PowerShellGallery.com) и выберите пункт **Войти**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="6747e-107">To create a PowerShell Gallery account, go to [https://PowerShellGallery.com](https://PowerShellGallery.com) and click on **Sign in** as shown in the following image.</span></span>

![Регистрация новой учетной записи](media/creating-an-account/CreateAccount-Register.png)

<span data-ttu-id="6747e-109">Чтобы использовать учетную запись Azure Active Directory, щелкните **Рабочая или учебная учетная запись** и выполните вход с помощью своей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6747e-109">To use an Azure Active Directory account, select **Work or School Account**, and sign in with your account.</span></span> <span data-ttu-id="6747e-110">Чтобы использовать идентификатор Майкрософт, выберите **Личная учетная запись** и выполните вход.</span><span class="sxs-lookup"><span data-stu-id="6747e-110">To use a Microsoft ID, choose **Personal Account** and sign in.</span></span>

<span data-ttu-id="6747e-111">Затем вам будет предложено создать имя пользователя для коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6747e-111">Next, you are prompted to create a username for the PowerShell Gallery.</span></span> <span data-ttu-id="6747e-112">Ознакомьтесь с условиями использования и политикой конфиденциальности, введите имя пользователя и щелкните **Зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="6747e-112">Review the Terms of Use and Privacy Policy, enter a username, and then click **Register**.</span></span>

> [!NOTE]
> <span data-ttu-id="6747e-113">Имя учетной записи нельзя изменить после ее создания.</span><span class="sxs-lookup"><span data-stu-id="6747e-113">The account name cannot be changed once it is created.</span></span> <span data-ttu-id="6747e-114">См. дополнительные сведения об [управлении владельцами пакетов](managing-package-owners.md).</span><span class="sxs-lookup"><span data-stu-id="6747e-114">For more information, see [Managing Package Owners](managing-package-owners.md).</span></span>

## <a name="recommended-practices-for-powershell-gallery-accounts"></a><span data-ttu-id="6747e-115">Рекомендации по использованию учетных записей коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="6747e-115">Recommended practices for PowerShell Gallery accounts</span></span>

<span data-ttu-id="6747e-116">Важно постоянно отслеживать учетную запись электронной почты, используемую с вашей учетной записью коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6747e-116">It's important to actively monitor the email account used with your PowerShell Gallery account.</span></span> <span data-ttu-id="6747e-117">Общение с владельцами пакетов коллекции PowerShell осуществляется через этот адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6747e-117">All communication with owners of PowerShell Gallery packages is through this email address.</span></span> <span data-ttu-id="6747e-118">Если группе эксплуатации не удается связаться с владельцем пакета, может потребоваться удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="6747e-118">If the PowerShell Gallery Operations team is unable to contact a package owner, we may be required to delete a package.</span></span>

<span data-ttu-id="6747e-119">Организации, которые публикуют в коллекцию PowerShell, часто создают для этого уникальные внешние учетные записи.</span><span class="sxs-lookup"><span data-stu-id="6747e-119">Organizations that publish to the PowerShell Gallery often create a unique external account for that purpose.</span></span> <span data-ttu-id="6747e-120">Для пересылки уведомлений на адрес организации рекомендуется использовать функцию пересылки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6747e-120">We recommend you use email forwarding to forward notifications to an address within your organization.</span></span>

<span data-ttu-id="6747e-121">Если с пакетом связаны несколько владельцев, все уведомления коллекции PowerShell отправляются всем владельцам.</span><span class="sxs-lookup"><span data-stu-id="6747e-121">When multiple owners are associated with a package, all PowerShell Gallery notifications are sent to all owners.</span></span> <span data-ttu-id="6747e-122">См. дополнительные сведения об [управлении владельцами пакетов](managing-package-owners.md).</span><span class="sxs-lookup"><span data-stu-id="6747e-122">For more information, see [Managing Package Owners](managing-package-owners.md).</span></span>

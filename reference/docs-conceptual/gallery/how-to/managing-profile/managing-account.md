---
ms.date: 09/05/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Параметры учетной записи коллекции PowerShell
ms.openlocfilehash: b71c7f0658c24ec2eeddb050e48b777a37c11917
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771793"
---
# <a name="powershell-gallery-account-settings"></a><span data-ttu-id="7eed1-103">Параметры учетной записи коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eed1-103">PowerShell Gallery Account Settings</span></span>

<span data-ttu-id="7eed1-104">Учетная запись коллекции PowerShell представляет собой видимое для обычных пользователей имя, связанное с удостоверением.</span><span class="sxs-lookup"><span data-stu-id="7eed1-104">Your PowerShell Gallery account is a publicly visible name that is linked to an identity.</span></span> <span data-ttu-id="7eed1-105">Этим удостоверением является либо идентификатор Майкрософт, такой как `user@hotmail.com` или `user@outlook.com`, либо учетная запись Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="7eed1-105">That identity is either a Microsoft ID, like `user@hotmail.com` or `user@outlook.com`, or an Azure Active Directory (AAD) account.</span></span>

<span data-ttu-id="7eed1-106">Коллекция PowerShell предоставляет следующие параметры учетной записи:</span><span class="sxs-lookup"><span data-stu-id="7eed1-106">The PowerShell Gallery provides the following account settings:</span></span>

- <span data-ttu-id="7eed1-107">учетная запись электронной почты, связанная с вашей учетной записью коллекции PowerShell;</span><span class="sxs-lookup"><span data-stu-id="7eed1-107">The email account associated with your PowerShell Gallery account</span></span>
- <span data-ttu-id="7eed1-108">параметры для уведомлений по электронной почте, отправляемых из коллекции PowerShell;</span><span class="sxs-lookup"><span data-stu-id="7eed1-108">Options for email notifications sent from the PowerShell Gallery</span></span>
- <span data-ttu-id="7eed1-109">учетная запись пользователя, связанная с вашей учетной записью коллекции PowerShell;</span><span class="sxs-lookup"><span data-stu-id="7eed1-109">The user account associated with your PowerShell Gallery account</span></span>
- <span data-ttu-id="7eed1-110">изображение, связанное с вашей учетной записью коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eed1-110">The picture associated with your PowerShell Gallery account</span></span>

## <a name="email-address"></a><span data-ttu-id="7eed1-111">Адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="7eed1-111">Email address</span></span>

<span data-ttu-id="7eed1-112">Адрес электронной почты является назначением для уведомлений коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eed1-112">The email address is the destination for PowerShell Gallery notifications.</span></span> <span data-ttu-id="7eed1-113">Он не должен совпадать с учетной записью входа.</span><span class="sxs-lookup"><span data-stu-id="7eed1-113">It does not have to match the login account.</span></span> <span data-ttu-id="7eed1-114">Можно использовать любую доступную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7eed1-114">You may use any email account you have access to.</span></span> <span data-ttu-id="7eed1-115">Коллекция PowerShell никогда напрямую не предоставляет ваш адрес электронной почты другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="7eed1-115">Your email address is never directly provided by the PowerShell Gallery to other users.</span></span>

![Изменение адреса электронной почты](media/managing-account/PSGallery_AcccountEmailAddress.png)

<span data-ttu-id="7eed1-117">Когда вы вводите новый адрес электронной почты, коллекция PowerShell отправляет на него проверочное сообщение.</span><span class="sxs-lookup"><span data-stu-id="7eed1-117">When you enter a new email address, the PowerShell Gallery sends a verification mail to that address.</span></span> <span data-ttu-id="7eed1-118">В этом сообщении содержится ссылка на коллекцию PowerShell для завершения процесса изменения.</span><span class="sxs-lookup"><span data-stu-id="7eed1-118">The verification mail contains a link back to the PowerShell Gallery to complete the change process.</span></span> <span data-ttu-id="7eed1-119">Пока вы не завершите процесс проверки, все уведомления отправляются на предыдущий адрес.</span><span class="sxs-lookup"><span data-stu-id="7eed1-119">Until you complete the verification process, all notifications are sent to the previous address.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="7eed1-120">Уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="7eed1-120">Email notifications</span></span>

<span data-ttu-id="7eed1-121">Коллекция PowerShell предоставляет следующие параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7eed1-121">PowerShell Gallery provides the following notification options:</span></span>

- <span data-ttu-id="7eed1-122">Users can contact me through the PowerShell Gallery (Пользователи могут связываться со мной с помощью коллекции PowerShell)</span><span class="sxs-lookup"><span data-stu-id="7eed1-122">Users can contact me through the PowerShell Gallery</span></span>
- <span data-ttu-id="7eed1-123">Notify me when an item is pushed to the PowerShell Gallery using my account (Уведомлять об отправке пакета в коллекцию PowerShell с помощью моей учетной записи)</span><span class="sxs-lookup"><span data-stu-id="7eed1-123">Notify me when an package is pushed to the PowerShell Gallery using my account</span></span>

![Выбор параметров адреса электронной почты](media/managing-account/PSGallery_AccountEmailOptions.png)

<span data-ttu-id="7eed1-125">Как указано на странице, критически важные уведомления из коллекции PowerShell отключить невозможно.</span><span class="sxs-lookup"><span data-stu-id="7eed1-125">As noted on the page, critical notifications from the PowerShell Gallery can't be disabled.</span></span>
<span data-ttu-id="7eed1-126">К ним относятся следующие объекты.</span><span class="sxs-lookup"><span data-stu-id="7eed1-126">These include:</span></span>

- <span data-ttu-id="7eed1-127">уведомления безопасности;</span><span class="sxs-lookup"><span data-stu-id="7eed1-127">Security notifications</span></span>
- <span data-ttu-id="7eed1-128">уведомления об управлении учетными записями от администраторов коллекции PowerShell;</span><span class="sxs-lookup"><span data-stu-id="7eed1-128">Account management notifications from PowerShell Gallery administrators</span></span>
- <span data-ttu-id="7eed1-129">уведомления о тестах, запускаемых коллекцией PowerShell, для выполненной отправки.</span><span class="sxs-lookup"><span data-stu-id="7eed1-129">Notifications about the tests run by the PowerShell Gallery for submissions you have made</span></span>

## <a name="change-your-login-account"></a><span data-ttu-id="7eed1-130">Изменение учетной записи входа</span><span class="sxs-lookup"><span data-stu-id="7eed1-130">Change your login account</span></span>

<span data-ttu-id="7eed1-131">Чтобы изменить учетную запись входа, необходимо выполнить вход с помощью текущей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7eed1-131">To change the login account, you must be signed in with the current account.</span></span> <span data-ttu-id="7eed1-132">Выполните следующие действия для изменения учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7eed1-132">Use the following steps to complete the change.</span></span>

![Изменение параметров учетной записи](media/managing-account/PSGallery_LoginAccountSettings.png)

1. <span data-ttu-id="7eed1-134">Щелкните **Изменить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="7eed1-134">Click on **Change Account**.</span></span> <span data-ttu-id="7eed1-135">Появится всплывающее окно объясняющее, что изменение учетной записи входа применяется ко всем случаям использования этой учетной записи в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eed1-135">A pop-up window explains that changing the login account applies to all uses of that account in the PowerShell Gallery.</span></span> <span data-ttu-id="7eed1-136">Ознакомьтесь с информацией и нажмите кнопку **ОК**, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="7eed1-136">Review the information, then click **OK** to continue.</span></span>

   ![Подтверждение изменения — OK/отмена](media/managing-account/PSGallery_LoginAccountChange-1.png)

2. <span data-ttu-id="7eed1-138">Затем вам будет предложено выполнить вход с помощью _новой учетной записи_.</span><span class="sxs-lookup"><span data-stu-id="7eed1-138">You are then prompted to sign in using the _new account_.</span></span>

   ![Войти с помощью новой учетной записи](media/managing-account/PSGallery_LoginAccountChange-2.png)

3. <span data-ttu-id="7eed1-140">После нажатия кнопки **Далее** появится сообщение, информирующее о входе с использованием текущей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7eed1-140">When you click **Next**, you see a message that you are signed in using the current account.</span></span>
   <span data-ttu-id="7eed1-141">Щелкните **Выйти и выполнить вход с использованием другой учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="7eed1-141">Click **Sign out and sign in with a different account**.</span></span>

   ![Выйти и войти в другую учетную запись](media/managing-account/PSGallery_LoginAccountChange-3.png)

4. <span data-ttu-id="7eed1-143">Введите пароль новой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7eed1-143">Enter the password of the new account.</span></span> <span data-ttu-id="7eed1-144">После ввода пароля вы вернетесь на страницу параметров учетной записи, где отображается обновленная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="7eed1-144">After entering the password, you are returned to the Account Settings page showing you that the login account has been updated.</span></span>

## <a name="enable-two-factor-authentication-2fa"></a><span data-ttu-id="7eed1-145">Включение двухфакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="7eed1-145">Enable Two-Factor Authentication (2FA)</span></span>

<span data-ttu-id="7eed1-146">Двухфакторную проверку подлинности рекомендуется проходить всем пользователям, которые вручную публикуют данные в коллекцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eed1-146">Two-factor authentication is recommended for all users who publish manually to the PowerShell Gallery.</span></span> <span data-ttu-id="7eed1-147">Чтобы включить двухфакторную проверку подлинности, для учетной записи входа должны быть зарегистрированы по крайней мере две формы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7eed1-147">To enable two-factor authentication, the login account must have at least two forms of authentication registered.</span></span> <span data-ttu-id="7eed1-148">Одной является использование пароля, а другими могут быть:</span><span class="sxs-lookup"><span data-stu-id="7eed1-148">One is a password and the other forms can be:</span></span>

- <span data-ttu-id="7eed1-149">номер телефона с поддержкой приема текстовых сообщений;</span><span class="sxs-lookup"><span data-stu-id="7eed1-149">A phone number that can receive text messages</span></span>
- <span data-ttu-id="7eed1-150">зарегистрированное приложение для проверки подлинности, например Microsoft Authenticator, для мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="7eed1-150">A registered authenticator application, such as Microsoft Authenticator for your mobile phone</span></span>

<span data-ttu-id="7eed1-151">Эти формы проверки подлинности должны быть настроены в разделе сведений об учетной записи AAD или в параметрах безопасности учетной записи ИД Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7eed1-151">These forms of authentication must be configured in your AAD account information or in your Microsoft ID Account Security settings.</span></span>

<span data-ttu-id="7eed1-152">После включения двухфакторной проверки подлинности вам требуется проходить проверку подлинности с помощью настроенных форм при каждом входе в коллекцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eed1-152">Once 2FA is enabled, you are required to authenticate using the configured forms of authentication every time you sign in to the PowerShell Gallery.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7eed1-153">При включении двухфакторной проверки подлинности для сайта коллекции PowerShell не нужно включать двухфакторную проверку подлинности для всех случаев использования учетной записи входа.</span><span class="sxs-lookup"><span data-stu-id="7eed1-153">Enabling two-factor authentication for the PowerShell Gallery site does not require you to enable 2FA for all uses of your login account.</span></span> <span data-ttu-id="7eed1-154">Дополнительные сведения см. в статье [Сведения о двухфакторной проверке подлинности](https://support.microsoft.com/help/12408/microsoft-account-about-two-step-verification).</span><span class="sxs-lookup"><span data-stu-id="7eed1-154">For more information, see [About two-step verification](https://support.microsoft.com/help/12408/microsoft-account-about-two-step-verification).</span></span>

## <a name="change-your-profile-picture"></a><span data-ttu-id="7eed1-155">Изменение изображения в профиле</span><span class="sxs-lookup"><span data-stu-id="7eed1-155">Change your profile picture</span></span>

<span data-ttu-id="7eed1-156">Для хранения и отображения изображения, связанного с профилем, коллекция PowerShell использует Gravatar.</span><span class="sxs-lookup"><span data-stu-id="7eed1-156">The PowerShell Gallery relies on Gravatar to store and display the picture associated with your profile.</span></span> <span data-ttu-id="7eed1-157">Чтобы обновить изображение в профиле, посетите веб-сайт [Gravatar.com](http://www.gravatar.com/).</span><span class="sxs-lookup"><span data-stu-id="7eed1-157">To update your profile image, visit [Gravatar.com](http://www.gravatar.com/).</span></span>

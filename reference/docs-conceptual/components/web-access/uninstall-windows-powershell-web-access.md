---
ms.date: 08/23/2017
keywords: powershell,командлет
title: Удаление Windows PowerShell Web Access
ms.openlocfilehash: 3c2c83525f5a240976eef215b5eac939796c91e8
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "78279016"
---
# <a name="uninstall-windows-powershell-web-access"></a><span data-ttu-id="47270-103">Удаление Windows PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="47270-103">Uninstall Windows PowerShell Web Access</span></span>

<span data-ttu-id="47270-104">Обновлено: 24 июня 2013 г.</span><span class="sxs-lookup"><span data-stu-id="47270-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="47270-105">Область применения: Windows Server 2012 R2, Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="47270-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="47270-106">В этом разделе приведена процедура удаления веб-сайта Windows PowerShell Web Access и соответствующего приложения с сервера шлюза, где они установлены.</span><span class="sxs-lookup"><span data-stu-id="47270-106">The steps in this topic remove the Windows PowerShell Web Access website and corresponding application from the gateway server where it is installed.</span></span>

## <a name="notify-users"></a><span data-ttu-id="47270-107">Уведомить пользователей</span><span class="sxs-lookup"><span data-stu-id="47270-107">Notify users</span></span>

<span data-ttu-id="47270-108">Прежде чем начать, известите пользователей веб-консоли, что вы удаляете веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="47270-108">Before you begin, notify users of the web-based console that you are removing the website.</span></span>

<span data-ttu-id="47270-109">Удаление Windows PowerShell Web Access не приводит к удалению IIS или любых других компонентов, которые были установлены автоматически, поскольку они требуются для выполнения Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="47270-109">Uninstalling Windows PowerShell Web Access does not uninstall IIS or any other features that were installed automatically because Windows PowerShell Web Access requires them to run.</span></span> <span data-ttu-id="47270-110">В процессе удаления остаются установленными компоненты, от которых зависит Windows PowerShell Web Access. Вы можете удалить эти компоненты при необходимости.</span><span class="sxs-lookup"><span data-stu-id="47270-110">The uninstallation process leaves features installed upon which Windows PowerShell Web Access was dependent; you can uninstall those features separately if needed.</span></span>

## <a name="recommended-quick-uninstallation"></a><span data-ttu-id="47270-111">Рекомендуемое (быстрое) удаление</span><span class="sxs-lookup"><span data-stu-id="47270-111">Recommended (quick) uninstallation</span></span>

<span data-ttu-id="47270-112">Процедуры этого раздела используются для удаления:</span><span class="sxs-lookup"><span data-stu-id="47270-112">Procedures in this section help you uninstall both:</span></span>

- <span data-ttu-id="47270-113">веб-приложения Windows PowerShell Web Access и</span><span class="sxs-lookup"><span data-stu-id="47270-113">the Windows PowerShell Web Access web application, and</span></span>
- <span data-ttu-id="47270-114">компонента Windows PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="47270-114">the Windows PowerShell Web Access feature</span></span>

<span data-ttu-id="47270-115">с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47270-115">by using Windows PowerShell cmdlets.</span></span>

### <a name="step-1-delete-the-web-application-using-cmdlets"></a><span data-ttu-id="47270-116">Шаг 1. Удаление веб-приложения с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="47270-116">Step 1: Delete the web application using cmdlets</span></span>

1. <span data-ttu-id="47270-117">Выполните одно из следующих действий, чтобы открыть сеанс Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47270-117">Do one of the following to open a Windows PowerShell session.</span></span>

   - <span data-ttu-id="47270-118">На рабочем столе Windows щелкните правой кнопкой мыши **Windows PowerShell** на панели задач.</span><span class="sxs-lookup"><span data-stu-id="47270-118">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>
   - <span data-ttu-id="47270-119">На **начальном** экране Windows щелкните **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="47270-119">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2. <span data-ttu-id="47270-120">Введите `Uninstall-PswaWebApplication` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="47270-120">Type `Uninstall-PswaWebApplication`, and then press **Enter**.</span></span>

   1. <span data-ttu-id="47270-121">Если вы задали собственное имя веб-сайта, добавьте параметр `-WebsiteName` в команду и укажите имя веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="47270-121">If you have specified your own, custom website name, add the `-WebsiteName` parameter to your command, and specify the website name.</span></span>

      `Uninstall-PswaWebApplication -WebsiteName <web-site-name>`

   1. <span data-ttu-id="47270-122">Если использовалось настраиваемое веб-приложение (не приложение **pswa** по умолчанию), добавьте параметр `-WebApplicationName` в команду и укажите имя веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="47270-122">If you have used a custom web application (not the default application, **pswa**, add the `-WebApplicationName` parameter to your command, and specify the name of the web application.</span></span>

      `Uninstall-PswaWebApplication -WebApplicationName <web-application-name>`

   1. <span data-ttu-id="47270-123">Если используется тестовый сертификат, добавьте в командлет параметр `DeleteTestCertificate`, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="47270-123">If you are using a test certificate, add the `DeleteTestCertificate` parameter to the cmdlet, as shown in the following example.</span></span>

      `Uninstall-PswaWebApplication -DeleteTestCertificate`

### <a name="step-2-uninstall-windows-powershell-web-access-using-cmdlets"></a><span data-ttu-id="47270-124">Шаг 2. Удаление Windows PowerShell Web Access с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="47270-124">Step 2: Uninstall Windows PowerShell Web Access using cmdlets</span></span>

1. <span data-ttu-id="47270-125">Выполните одно из следующих действий, чтобы открыть сеанс Windows PowerShell с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="47270-125">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span> <span data-ttu-id="47270-126">Если сеанс уже открыт, переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="47270-126">If a session is already open, go on to the next step.</span></span>

    - <span data-ttu-id="47270-127">На рабочем столе Windows щелкните правой кнопкой мыши **Windows PowerShell** на панели задач и выберите команду **Запустить от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="47270-127">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>
    - <span data-ttu-id="47270-128">На **начальном экране** Windows щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запустить от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="47270-128">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

1. <span data-ttu-id="47270-129">Введите следующую команду и нажмите клавишу **ВВОД**, где *computer_name* представляет удаленный сервер, с которого требуется удалить Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="47270-129">Type the following, and then press **Enter**, where *computer_name* represents a remote server from which you want to remove Windows PowerShell Web Access.</span></span> <span data-ttu-id="47270-130">Параметр `-Restart` автоматически перезапускает конечные серверы, если это требуется при удалении.</span><span class="sxs-lookup"><span data-stu-id="47270-130">The `-Restart` parameter automatically restarts destination servers if required by the removal.</span></span>

    `Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -Restart`

    <span data-ttu-id="47270-131">Чтобы удалить роли и компоненты с автономного виртуального жесткого диска, необходимо добавить оба параметра, `-ComputerName` и `-VHD`.</span><span class="sxs-lookup"><span data-stu-id="47270-131">To remove roles and features from an offline VHD, you must add both the `-ComputerName` parameter and the `-VHD` parameter.</span></span> <span data-ttu-id="47270-132">В параметре `-ComputerName` содержится имя сервера, на котором требуется подключить виртуальный жесткий диск, а в параметре `-VHD` — путь к VHD-файлу на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="47270-132">The `-ComputerName` parameter contains the name of the server on which to mount the VHD, and the `-VHD` parameter contains the path to the VHD file on the specified server.</span></span>

    `Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -Restart`

1. <span data-ttu-id="47270-133">После завершения удаления Windows PowerShell Web Access откройте для проверки страницу **Все серверы** в диспетчере серверов, выберите сервер, с которого был удален компонент, и просмотрите плитку **Роли и компоненты** на странице для выбранного сервера.</span><span class="sxs-lookup"><span data-stu-id="47270-133">When removal is finished, verify that you removed Windows PowerShell Web Access by opening the **All Servers** page in Server Manager, selecting a server from which you removed the feature, and viewing the **Roles and Features** tile on the page for the selected server.</span></span>

    <span data-ttu-id="47270-134">Можно также выполнить командлет `Get-WindowsFeature`, нацеленный на выбранный сервер (Get-WindowsFeature-ComputerName &lt;*имя_компьютера*&gt;), чтобы просмотреть список ролей и компонентов, установленных на сервере.</span><span class="sxs-lookup"><span data-stu-id="47270-134">You can also run the `Get-WindowsFeature` cmdlet targeted at the selected server  (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) to view a list of roles and features  that are installed on the server.</span></span>

## <a name="custom-uninstallation"></a><span data-ttu-id="47270-135">Настраиваемое удаление</span><span class="sxs-lookup"><span data-stu-id="47270-135">Custom uninstallation</span></span>

<span data-ttu-id="47270-136">В этом разделе приводятся процедуры для удаления веб-приложения Windows PowerShell Web Access и компонента Windows PowerShell Web Access с помощью мастера удаления ролей и компонентов в диспетчере серверов и на консоли диспетчера служб IIS.</span><span class="sxs-lookup"><span data-stu-id="47270-136">Procedures in this section help you uninstall both the Windows PowerShell Web Access web application and the Windows PowerShell Web Access feature by using the Remove Roles and Features Wizard in Server Manager, and the IIS Manager console.</span></span>

### <a name="step-1-delete-the-web-application-using-iis-manager"></a><span data-ttu-id="47270-137">Шаг 1. Удаление веб-приложения с помощью диспетчера IIS</span><span class="sxs-lookup"><span data-stu-id="47270-137">Step 1: Delete the web application using IIS Manager</span></span>

1. <span data-ttu-id="47270-138">Откройте консоль "Диспетчер служб IIS", выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="47270-138">Open the IIS Manager console by doing one of the following.</span></span> <span data-ttu-id="47270-139">Если консоль уже открыта, переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="47270-139">If it is already open, go on to the next step.</span></span>

   - <span data-ttu-id="47270-140">На рабочем столе Windows запустите диспетчер серверов, щелкнув **Диспетчер серверов** на панели задач Windows.</span><span class="sxs-lookup"><span data-stu-id="47270-140">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="47270-141">В диспетчере серверов откройте меню **Сервис** и выберите пункт **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="47270-141">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

   - <span data-ttu-id="47270-142">На **начальном** экране Windows введите любую часть имени **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="47270-142">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="47270-143">Щелкните ярлык, когда он появится в списке результатов **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="47270-143">Click the shortcut when it is displayed in the **Apps** results.</span></span>

1. <span data-ttu-id="47270-144">В области дерева диспетчера служб IIS выберите веб-сайт, на котором выполняется веб-приложение Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="47270-144">In the IIS Manager tree pane, select the website that is running the Windows PowerShell Web Access web application.</span></span>

1. <span data-ttu-id="47270-145">В области **Действия** в разделе **Управление веб-сайтом** щелкните **Остановить**.</span><span class="sxs-lookup"><span data-stu-id="47270-145">In the **Actions** pane, under **Manage Website**, click **Stop**.</span></span>

1. <span data-ttu-id="47270-146">В области дерева щелкните правой кнопкой мыши веб-приложение на веб-сайте, на котором выполняется веб-приложение Windows PowerShell Web Access, а затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="47270-146">In the tree pane, right-click the web application in the website that is running the Windows PowerShell Web Access web application, and then click **Remove**.</span></span>

1. <span data-ttu-id="47270-147">В области дерева выберите **Пулы приложений**, выберите папку пула приложений Windows PowerShell Web Access, щелкните **Остановить** в области **Действия**, а затем щелкните **Удалить** в области содержимого.</span><span class="sxs-lookup"><span data-stu-id="47270-147">In the tree pane, select **Application Pools**, select the Windows PowerShell Web Access application pool folder, click **Stop** in the **Actions** pane, and then click **Remove** in the content pane.</span></span>

1. <span data-ttu-id="47270-148">Закройте диспетчер IIS.</span><span class="sxs-lookup"><span data-stu-id="47270-148">Close IIS Manager.</span></span>

   > [!WARNING]
   > <span data-ttu-id="47270-149">Сертификат не удаляется при этой операции удаления.</span><span class="sxs-lookup"><span data-stu-id="47270-149">The certificate is not deleted during uninstallation.</span></span> <span data-ttu-id="47270-150">Если вы создали самозаверяющий сертификат или использовали тестовый сертификат и хотите удалить его, удалите сертификат в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="47270-150">If you created a self-signed certificate or used a test certificate and want to remove it, delete the certificate in IIS Manager.</span></span>

### <a name="step-2-uninstall-windows-powershell-web-access-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="47270-151">Шаг 2. Удаление Windows PowerShell Web Access с помощью мастера удаления ролей и компонентов</span><span class="sxs-lookup"><span data-stu-id="47270-151">Step 2: Uninstall Windows PowerShell Web Access using the Remove Roles and Features Wizard</span></span>

1. <span data-ttu-id="47270-152">Если диспетчер серверов уже открыт, переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="47270-152">If Server Manager is already open, go on to the next step.</span></span> <span data-ttu-id="47270-153">Если диспетчер серверов еще не открыт, откройте его одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="47270-153">If Server Manager is not already open, open it by doing one of the following.</span></span>

    - <span data-ttu-id="47270-154">На рабочем столе Windows запустите диспетчер серверов, щелкнув **Диспетчер серверов** на панели задач Windows.</span><span class="sxs-lookup"><span data-stu-id="47270-154">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span>
    - <span data-ttu-id="47270-155">На **начальном** экране в Windows выберите **Диспетчер серверов**.</span><span class="sxs-lookup"><span data-stu-id="47270-155">On the Windows **Start** screen, click **Server Manager**.</span></span>

1. <span data-ttu-id="47270-156">В меню **Управление** выберите команду **Удалить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="47270-156">On the **Manage** menu, click **Remove Roles and Features**.</span></span>

1. <span data-ttu-id="47270-157">На странице **Выбор целевого сервера** выберите сервер или виртуальный жесткий диск, с которого следует удалить компонент.</span><span class="sxs-lookup"><span data-stu-id="47270-157">On the **Select destination server** page, select the server or offline VHD from which you want to remove the feature.</span></span> <span data-ttu-id="47270-158">Чтобы выбрать автономный виртуальный жесткий диск, сначала выберите сервер, на котором будет подключен виртуальный жесткий диск, а затем выберите VHD-файл.</span><span class="sxs-lookup"><span data-stu-id="47270-158">To select an offline VHD, first select the server on which to mount the VHD, and then select the VHD file.</span></span> <span data-ttu-id="47270-159">Выбрав конечный сервер, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47270-159">After you have selected the destination server, click **Next**.</span></span>

1. <span data-ttu-id="47270-160">Еще раз щелкните **Далее**, чтобы пропустить страницу **Удаление компонентов**.</span><span class="sxs-lookup"><span data-stu-id="47270-160">Click **Next** again to skip to the **Remove features** page.</span></span>

1. <span data-ttu-id="47270-161">Снимите флажок **Windows PowerShell Web Access** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47270-161">Clear the check box for **Windows PowerShell Web Access**, and then click **Next**.</span></span>

1. <span data-ttu-id="47270-162">На странице **Подтверждение удаления компонентов** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="47270-162">On the **Confirm removal selections** page, click **Remove**.</span></span>

## <a name="see-also"></a><span data-ttu-id="47270-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="47270-163">See Also</span></span>

- [<span data-ttu-id="47270-164">Установка и использование Windows PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="47270-164">Install and Use Windows PowerShell Web Access</span></span>](install-and-use-windows-powershell-web-access.md)
- [<span data-ttu-id="47270-165">Справка по диспетчеру IIS 7.0</span><span class="sxs-lookup"><span data-stu-id="47270-165">IIS Manager 7.0 Help</span></span>](https://technet.microsoft.com/library/cc732664.aspx)
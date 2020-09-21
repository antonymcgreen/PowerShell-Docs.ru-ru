---
title: Начало работы с PowerShell
description: Сведения для начинающих пользователей о том, где найти и как запустить PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e8938a5d36cd1c9c5a74eed1c22cd5d0e1a91966
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786753"
---
# <a name="chapter-1---getting-started-with-powershell"></a><span data-ttu-id="49b12-103">Глава 1. Начало работы с PowerShell</span><span class="sxs-lookup"><span data-stu-id="49b12-103">Chapter 1 - Getting Started with PowerShell</span></span>

<span data-ttu-id="49b12-104">Я часто вижу, что выступающие на конференциях и собраниях групп пользователей уже работают с PowerShell, когда демонстрируют презентации начального уровня.</span><span class="sxs-lookup"><span data-stu-id="49b12-104">I often find that presenters at conferences and user group meetings already have PowerShell running when they start entry-level presentations.</span></span> <span data-ttu-id="49b12-105">Эта книга начинается с ответов на вопросы, которые задавали участники мероприятий, ранее не использовавшие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-105">This book begins by answering the questions I've heard attendees who haven't previously used PowerShell ask in those sessions.</span></span>

<span data-ttu-id="49b12-106">В частности, эта глава посвящена поиску и запуску PowerShell, а также решению некоторых первоначальных проблем, с которыми сталкиваются новые пользователи при работе с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-106">Specifically, this chapter focuses on finding and launching PowerShell, and solving some of the initial pain points that new users experience with PowerShell.</span></span> <span data-ttu-id="49b12-107">Обязательно ознакомьтесь с примерами, приведенными в этой главе, и выполните их на компьютере Windows 10 с лабораторной средой.</span><span class="sxs-lookup"><span data-stu-id="49b12-107">Be sure to follow along and walk through the examples shown in this chapter on your Windows 10 lab environment computer.</span></span>

## <a name="what-do-i-need-to-get-started-with-powershell"></a><span data-ttu-id="49b12-108">Что нужно, чтобы начать работу с PowerShell?</span><span class="sxs-lookup"><span data-stu-id="49b12-108">What do I need to get started with PowerShell?</span></span>

<span data-ttu-id="49b12-109">Все современные версии операционных систем Windows поставляются с установленной оболочкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-109">All modern versions of Windows operating systems ship with PowerShell installed.</span></span> <span data-ttu-id="49b12-110">Если вы используете версию, предшествующую 5.1, следует установить последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="49b12-110">If you're running a version older than 5.1, you should install the latest version.</span></span>

- <span data-ttu-id="49b12-111">Сведения об обновлении до версии PowerShell 5.1 см. в разделе [Обновление существующей версии Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="49b12-111">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][]</span></span>
- <span data-ttu-id="49b12-112">Сведения об установке последней версии PowerShell см. в статье [Installing Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="49b12-112">To install the latest version of PowerShell, see [Installing PowerShell][]</span></span>

## <a name="where-do-i-find-powershell"></a><span data-ttu-id="49b12-113">Где найти PowerShell?</span><span class="sxs-lookup"><span data-stu-id="49b12-113">Where do I find PowerShell?</span></span>

<span data-ttu-id="49b12-114">Самый простой способ найти PowerShell в Windows 10 — ввести **PowerShell** в строке поиска, как показано на рис. 1-1.</span><span class="sxs-lookup"><span data-stu-id="49b12-114">The easiest way to find PowerShell on Windows 10 is to type **PowerShell** into the search bar as shown in Figure 1-1.</span></span>

![Рис. 1-1. Поиск PowerShell в меню "Пуск"](media/figure1-1.png)

<span data-ttu-id="49b12-116">Обратите внимание, что на рис. 1-1 показаны четыре разных ярлыка для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-116">Notice that four different shortcuts for PowerShell are shown in Figure 1-1.</span></span> <span data-ttu-id="49b12-117">Компьютер, используемый в демонстрационных целях в этой книге, работает под управлением 64-разрядной версии Windows 10, поэтому существует 64-разрядная версия консоли PowerShell и PowerShell ISE (интегрированной среды сценариев) и 32-разрядная версия каждой из них (обозначена суффиксом (x86) на ярлыках).</span><span class="sxs-lookup"><span data-stu-id="49b12-117">The computer used for demonstration purposes in this book is running the 64-bit version of Windows 10 so there's a 64-bit version of the PowerShell console and the PowerShell ISE (Integrated Scripting Environment), and a 32-bit version of each one as denoted by the (x86) suffix on the shortcuts.</span></span> <span data-ttu-id="49b12-118">Если вы работаете с 32-разрядной версией Windows 10, у вас будет только два ярлыка.</span><span class="sxs-lookup"><span data-stu-id="49b12-118">If you happen to be running a 32-bit version of Windows 10, you'll only have two shortcuts.</span></span> <span data-ttu-id="49b12-119">У этих элементов нет суффикса (x86), но они являются 32-разрядными версиями.</span><span class="sxs-lookup"><span data-stu-id="49b12-119">Those items don't have the (x86) suffix, but are 32-bit versions.</span></span> <span data-ttu-id="49b12-120">Если у вас установлена 64-разрядная операционная система, рекомендуется запускать 64-разрядную версию PowerShell, только если вас нет особой причины для запуска 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="49b12-120">If you have a 64-bit operating system, my recommendation is to run the 64-bit version of PowerShell unless you have a specific reason for running the 32-bit version.</span></span>

<span data-ttu-id="49b12-121">Сведения о запуске PowerShell в других версиях Windows см. в статье [Запуск Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="49b12-121">For information about starting PowerShell on other versions of Windows, see [Starting Windows PowerShell][].</span></span>

## <a name="how-do-i-launch-powershell"></a><span data-ttu-id="49b12-122">Как запустить PowerShell?</span><span class="sxs-lookup"><span data-stu-id="49b12-122">How do I launch PowerShell?</span></span>

<span data-ttu-id="49b12-123">В производственной среде предприятия, которую я поддерживаю, я работаю с тремя разными учетными записями пользователей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49b12-123">In the production enterprise environments that I support, I use three different Active Directory user accounts.</span></span> <span data-ttu-id="49b12-124">В лабораторной среде в этой книге используются зеркальные экземпляры этих учетных записей.</span><span class="sxs-lookup"><span data-stu-id="49b12-124">I've mirrored those accounts in the lab environment used in this book.</span></span> <span data-ttu-id="49b12-125">Я вошел на компьютер с Windows 10 в качестве пользователя домена, который не является администратором домена или локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="49b12-125">I log into the Windows 10 computer as a domain user who is not a domain or local administrator.</span></span>

<span data-ttu-id="49b12-126">Я запустил консоль PowerShell, щелкнув ярлык Windows PowerShell, как показано на рис. 1-1.</span><span class="sxs-lookup"><span data-stu-id="49b12-126">I've launched the PowerShell console by clicking on the "Windows PowerShell" shortcut as shown in Figure 1-1.</span></span>

![Рис. 1-4. Заголовок окна PowerShell](media/figure1-4.png)

<span data-ttu-id="49b12-128">Обратите внимание, что в строке заголовка консоли PowerShell указано "Windows PowerShell", как показано на рис. 1-4.</span><span class="sxs-lookup"><span data-stu-id="49b12-128">Notice that the title bar of the PowerShell console says "Windows PowerShell" as shown in Figure 1-4.</span></span> <span data-ttu-id="49b12-129">Некоторые команды выполняются нормально, но PowerShell не поддерживает управление доступом пользователей (UAC).</span><span class="sxs-lookup"><span data-stu-id="49b12-129">Some commands run fine, but PowerShell can't participate in User Access Control (UAC).</span></span> <span data-ttu-id="49b12-130">Это означает, что оболочка не может запрашивать повышение прав для задач, требующих утверждения администратором.</span><span class="sxs-lookup"><span data-stu-id="49b12-130">That means it's unable to prompt for elevation for tasks that require the approval of an administrator.</span></span>
<span data-ttu-id="49b12-131">Выдается следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="49b12-131">The following error message is generated:</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service
```

```Output
Stop-Service : Service 'Windows Time (W32Time)' cannot be stopped due to the following
error: Cannot open W32Time service on computer '.'.
At line:1 char:29
+ Get-Service -Name W32Time | Stop-Service
+
    + CategoryInfo          : CloseError: (System.ServiceProcess.ServiceController:ServiceController)
     [Stop-Service], ServiceCommandException
    + FullyQualifiedErrorId : CouldNotStopService,Microsoft.PowerShell.Commands.StopServiceCommand
```

<span data-ttu-id="49b12-132">Решение этой проблемы заключается в запуске PowerShell от имени пользователя домена, который является локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="49b12-132">The solution to this problem is to run PowerShell as a domain user who is a local administrator.</span></span>
<span data-ttu-id="49b12-133">Именно так настроена моя вторая учетная запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="49b12-133">This is how my second domain user account is configured.</span></span> <span data-ttu-id="49b12-134">Согласно принципу наименьших привилегий эта учетная запись НЕ должна быть администратором домена или иметь повышенные привилегии в домене.</span><span class="sxs-lookup"><span data-stu-id="49b12-134">Using the principal of least privilege, this account should NOT be a domain administrator, or have any elevated privileges in the domain.</span></span>

<span data-ttu-id="49b12-135">Закройте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-135">Close PowerShell.</span></span> <span data-ttu-id="49b12-136">Перезапустите консоль PowerShell, только на этот раз щелкните правой кнопкой мыши ярлык **Windows PowerShell** и выберите пункт **Запуск от имени администратора**, как показано на рис. 1-5.</span><span class="sxs-lookup"><span data-stu-id="49b12-136">Relaunch the PowerShell console, except this time right-click on the **Windows PowerShell** shortcut and select **Run as administrator** as shown in Figure 1-5.</span></span>

![Рис. 1-5. Контекстное меню "Запуск от имени администратора"](media/figure1-5.png)

<span data-ttu-id="49b12-138">Если вы выполнили вход в Windows в качестве обычного пользователя, вам будет предложено ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="49b12-138">If you're logged into Windows as a normal user, you'll be prompted for credentials.</span></span> <span data-ttu-id="49b12-139">Я буду вводить учетные данные учетной записи пользователя, которая является пользователем домена и локальным администратором, как показано на рис. 1-6.</span><span class="sxs-lookup"><span data-stu-id="49b12-139">I'll enter the credentials for my user account who is a domain user and local admin as shown in Figure 1-6.</span></span>

![Рис. 1-6](media/figure1-6.png)

<span data-ttu-id="49b12-141">После повторного запуска PowerShell с правами администратора в строке заголовка должно быть указано "Администратор: Windows PowerShell", как показано на рис. 1-7.</span><span class="sxs-lookup"><span data-stu-id="49b12-141">Once PowerShell is relaunched as an administrator, the title bar should say "Administrator: Windows PowerShell" as shown in Figure 1-7.</span></span>

![Рис. 1-7](media/figure1-7.png)

<span data-ttu-id="49b12-143">Теперь, когда PowerShell работает с повышенными привилегиями локального администратора, управление доступом пользователей больше не будет проблемой в случае запуска на локальном компьютере команды, для выполнения которой обычно требуется запрос на повышение прав.</span><span class="sxs-lookup"><span data-stu-id="49b12-143">Now that PowerShell is being run elevated as a local administrator, UAC will no longer be a problem when a command is run on the local computer that would normally require a prompt for elevation.</span></span> <span data-ttu-id="49b12-144">Следует иметь в виду, что любая команда, выполняемая из этого экземпляра консоли PowerShell с повышенными привилегиями, также запускается с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="49b12-144">Keep in mind though that any command run from this elevated instance of the PowerShell console, also runs elevated.</span></span>

<span data-ttu-id="49b12-145">Чтобы упростить поиск PowerShell и запускать оболочку от имени администратора, рекомендуется закрепить ее на панели задач и настроить автоматический запуск от имени администратора при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="49b12-145">To simplify finding PowerShell and launching it as an administrator, I recommend pinning it to the taskbar and setting it to automatically launch as an admin each time it's run.</span></span>

<span data-ttu-id="49b12-146">Еще раз выполните поиск PowerShell, только на этот раз щелкните ее правой кнопкой мыши и выберите пункт "Закрепить на панели задач", как показано на рис. 1-8.</span><span class="sxs-lookup"><span data-stu-id="49b12-146">Search for PowerShell again, except this time right-click on it and select "Pin to taskbar" as shown in Figure 1-8.</span></span>

![Рис. 1-8](media/figure1-8.png)

<span data-ttu-id="49b12-148">Щелкните правой кнопкой мыши ярлык PowerShell, который теперь закреплен на панели задач, и выберите пункт "Свойства", как показано на рис. 1-9.</span><span class="sxs-lookup"><span data-stu-id="49b12-148">Right-click on the PowerShell shortcut that's now pinned to the taskbar and select properties as shown in Figure 1-9.</span></span>

![Рис. 1-9. Управление учетными записями пользователей — ввод учетных данных](media/figure1-9.png)

<span data-ttu-id="49b12-150">Щелкните "Дополнительно", как показано в первой части рис. 1-10, установите флажок "Запуск от имени администратора", как показано во второй части рис. 1-10, а затем дважды нажмите кнопку OK, чтобы принять изменения и выйти из обоих диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="49b12-150">Click on "Advanced" as denoted by #1 in Figure 1-10, then check the "Run as administrator" checkbox as denoted by #2 in Figure 1-10, and then click OK twice to accept the changes and exit out of both dialog boxes.</span></span>

![Рис. 1-10. Заголовок окна "Администратор"](media/figure1-10.png)

<span data-ttu-id="49b12-152">Вам больше никогда не придется беспокоиться о поиске PowerShell или о том, запущена ли оболочка от имени администратора или нет.</span><span class="sxs-lookup"><span data-stu-id="49b12-152">You'll never have to worry about finding PowerShell or whether or not it's running as an administrator again.</span></span>

<span data-ttu-id="49b12-153">Запуск PowerShell с повышенными привилегиями для предотвращения проблем, связанных с управлением доступом пользователей, влияет только на команды, выполняемые на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="49b12-153">Running PowerShell elevated as an administrator to prevent having problems with UAC only impacts commands that are run against the local computer.</span></span> <span data-ttu-id="49b12-154">Он не влияет на команды, предназначенные для запуска на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="49b12-154">It has no effect on commands that target remote computers.</span></span>

## <a name="what-version-of-powershell-am-i-running"></a><span data-ttu-id="49b12-155">Какую версию PowerShell я использую?</span><span class="sxs-lookup"><span data-stu-id="49b12-155">What version of PowerShell am I running?</span></span>

<span data-ttu-id="49b12-156">В PowerShell существует ряд автоматических переменных, в которых хранятся сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="49b12-156">There are a number of automatic variables in PowerShell that store state information.</span></span> <span data-ttu-id="49b12-157">Одной из этих переменных является `$PSVersionTable`, содержащая хэш-таблицу, которую можно использовать для вывода соответствующих сведений о версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-157">One of these variables is `$PSVersionTable`, which contains a hashtable that can be used to display the relevant PowerShell version information:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      5.1.19041.1
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.19041.1
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

<span data-ttu-id="49b12-158">Более новые версии Windows PowerShell распространяются в составе Windows Management Framework (WMF).</span><span class="sxs-lookup"><span data-stu-id="49b12-158">Newer versions of Windows PowerShell are distributed as part of the Windows Management Framework (WMF).</span></span> <span data-ttu-id="49b12-159">Конкретная версия .NET Framework зависит от версии WMF.</span><span class="sxs-lookup"><span data-stu-id="49b12-159">A specific version of the .NET Framework is required depending on the WMF version.</span></span> <span data-ttu-id="49b12-160">Сведения об обновлении до версии PowerShell 5.1 см. в разделе [Обновление существующей версии Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="49b12-160">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][].</span></span>

## <a name="execution-policy"></a><span data-ttu-id="49b12-161">Политика выполнения</span><span class="sxs-lookup"><span data-stu-id="49b12-161">Execution Policy</span></span>

<span data-ttu-id="49b12-162">Вопреки распространенному мнению, политика выполнения в PowerShell не является средством обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="49b12-162">Contrary to popular belief, the execution policy in PowerShell is not a security boundary.</span></span> <span data-ttu-id="49b12-163">Она предназначена для предотвращения непреднамеренного выполнения сценария пользователем.</span><span class="sxs-lookup"><span data-stu-id="49b12-163">It's designed to prevent a user from unknowingly running a script.</span></span> <span data-ttu-id="49b12-164">Определенный пользователь может без труда обойти политику выполнения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-164">A determined user can easily bypass the execution policy in PowerShell.</span></span> <span data-ttu-id="49b12-165">В таблице 1-2 показана политика выполнения по умолчанию для текущих операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="49b12-165">Table 1-2 shows the default execution policy for current Windows operating systems.</span></span>

| <span data-ttu-id="49b12-166">Версия операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="49b12-166">Windows Operating System Version</span></span> | <span data-ttu-id="49b12-167">Политика выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="49b12-167">Default Execution Policy</span></span> |
| -------------------------------- | ------------------------ |
| <span data-ttu-id="49b12-168">Server 2019</span><span class="sxs-lookup"><span data-stu-id="49b12-168">Server 2019</span></span>                      | <span data-ttu-id="49b12-169">Удаленно подписанная</span><span class="sxs-lookup"><span data-stu-id="49b12-169">Remote Signed</span></span>            |
| <span data-ttu-id="49b12-170">Server 2016</span><span class="sxs-lookup"><span data-stu-id="49b12-170">Server 2016</span></span>                      | <span data-ttu-id="49b12-171">Удаленно подписанная</span><span class="sxs-lookup"><span data-stu-id="49b12-171">Remote Signed</span></span>            |
| <span data-ttu-id="49b12-172">Windows 10</span><span class="sxs-lookup"><span data-stu-id="49b12-172">Windows 10</span></span>                       | <span data-ttu-id="49b12-173">С ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="49b12-173">Restricted</span></span>               |

<span data-ttu-id="49b12-174">Любая команда PowerShell может выполняться в интерактивном режиме, независимо от настройки политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="49b12-174">Regardless of the execution policy setting, any PowerShell command can be run interactively.</span></span> <span data-ttu-id="49b12-175">Политика выполнения влияет только на команды, выполняемые в сценарии.</span><span class="sxs-lookup"><span data-stu-id="49b12-175">The execution policy only affects commands running in a script.</span></span> <span data-ttu-id="49b12-176">Командлет `Get-ExecutionPolicy` используется для определения текущего параметра политики выполнения, а командлет `Set-ExecutionPolicy` используется для изменения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="49b12-176">The `Get-ExecutionPolicy` cmdlet is used to determine what the current execution policy setting is and the `Set-ExecutionPolicy` cmdlet is used to change the execution policy.</span></span> <span data-ttu-id="49b12-177">Рекомендуется использовать политику **RemoteSigned**, которая требует, чтобы предназначенные для выполнения скачиваемые сценарии были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="49b12-177">My recommendation is to use the **RemoteSigned** policy, which requires downloaded scripts to be signed by a trusted publisher in order to be run.</span></span>

<span data-ttu-id="49b12-178">Проверка текущей политики выполнения</span><span class="sxs-lookup"><span data-stu-id="49b12-178">Check the current execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

```Output
Restricted
```

<span data-ttu-id="49b12-179">Если для политики выполнения задано **С ограниченным доступом**, сценарии PowerShell вообще не запускаются.</span><span class="sxs-lookup"><span data-stu-id="49b12-179">PowerShell scripts can't be run at all when the execution policy is set to **Restricted**.</span></span> <span data-ttu-id="49b12-180">Это параметр по умолчанию для всех клиентских операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="49b12-180">This is the default setting on all Windows client operating systems.</span></span> <span data-ttu-id="49b12-181">Чтобы продемонстрировать проблему, сохраните следующий код как файл `.ps1` с именем `Stop-TimeService.ps1`.</span><span class="sxs-lookup"><span data-stu-id="49b12-181">To demonstrate the problem, save the following code as a `.ps1` file named `Stop-TimeService.ps1`.</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service -PassThru
```

<span data-ttu-id="49b12-182">Эта команда выполняется в интерактивном режиме без ошибок при условии, что PowerShell запущена с повышенными правами администратора.</span><span class="sxs-lookup"><span data-stu-id="49b12-182">That command runs interactively without error as long as PowerShell is run elevated as an administrator.</span></span> <span data-ttu-id="49b12-183">Но при сохранении в виде файла сценария и попытке выполнить сценарий выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="49b12-183">But as soon as it's saved as a script file and you try to execute the script, it generates an error:</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
.\Stop-TimeService.ps1 : File C:\demo\Stop-TimeService.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see
about_Execution_Policies at http://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Stop-TimeService.ps1
+
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="49b12-184">Обратите внимание, что в сообщении об ошибке, приведенном в предыдущем наборе результатов, указывается точная проблема (в этой системе отключено выполнение сценариев).</span><span class="sxs-lookup"><span data-stu-id="49b12-184">Notice that the error shown in the previous set of results tells you exactly what the problem is (running scripts is disabled on this system).</span></span> <span data-ttu-id="49b12-185">При выполнении в PowerShell команды, которая создает сообщение об ошибке, обязательно следует прочесть сообщение об ошибке, а не просто перезапустить команду и надеяться на ее успешное завершение.</span><span class="sxs-lookup"><span data-stu-id="49b12-185">When you run a command in PowerShell that generates an error message, be sure to read the error message instead of just rerunning the command and hoping that it runs successfully.</span></span>

<span data-ttu-id="49b12-186">Измените политику выполнения PowerShell на удаленно подписанную.</span><span class="sxs-lookup"><span data-stu-id="49b12-186">Change the PowerShell execution policy to remote signed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

```Output
Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution
policy might expose you to the security risks described in the about_Execution_Policies help topic
at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default is "N"):y
```

<span data-ttu-id="49b12-187">Обязательно прочтите предупреждение, которое отображается при изменении политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="49b12-187">Be sure to read the warning that's displayed when changing the execution policy.</span></span> <span data-ttu-id="49b12-188">Кроме того, рекомендуется ознакомиться с разделом справки [about_Execution_Policies][], чтобы знать о влиянии изменения политики выполнения на безопасность.</span><span class="sxs-lookup"><span data-stu-id="49b12-188">I also recommend taking a look at the [about_Execution_Policies][] help topic to make sure you understand the security implications of changing the execution policy.</span></span>

<span data-ttu-id="49b12-189">Теперь, когда для политики выполнения задано значение **Удаленно подписанная**, сценарий `Stop-TimeService.ps1` будет выполняться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="49b12-189">Now that the execution policy has been set to **RemoteSigned**, the `Stop-TimeService.ps1` script runs error free.</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  W32Time            Windows Time
```

<span data-ttu-id="49b12-190">Прежде чем продолжить, запустите службу времени Windows. В противном случае могут возникнуть непредвиденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="49b12-190">Be sure to start your Windows Time service before continuing otherwise you may run into unforeseen problems.</span></span>

```powershell
Start-Service -Name w32time
```

## <a name="summary"></a><span data-ttu-id="49b12-191">Сводка</span><span class="sxs-lookup"><span data-stu-id="49b12-191">Summary</span></span>

<span data-ttu-id="49b12-192">В этой главе вы узнали, как найти и запустить PowerShell, а также как создать ярлык для запуска PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="49b12-192">In this chapter, you've learned how to find and launch PowerShell, and how to create a shortcut that launches PowerShell as an administrator.</span></span> <span data-ttu-id="49b12-193">Вы также ознакомились с политикой выполнения по умолчанию и поняли, как ее изменять.</span><span class="sxs-lookup"><span data-stu-id="49b12-193">You've also learned about the default execution policy and how to change it.</span></span>

## <a name="review"></a><span data-ttu-id="49b12-194">Просмотр</span><span class="sxs-lookup"><span data-stu-id="49b12-194">Review</span></span>

1. <span data-ttu-id="49b12-195">Как определить версию PowerShell, установленную на компьютере?</span><span class="sxs-lookup"><span data-stu-id="49b12-195">How do you determine what PowerShell version a computer is running?</span></span>
1. <span data-ttu-id="49b12-196">Почему важно запускать PowerShell с повышенными правами администратора?</span><span class="sxs-lookup"><span data-stu-id="49b12-196">Why is it important to launch PowerShell elevated as an administrator?</span></span>
1. <span data-ttu-id="49b12-197">Как определить текущую политику выполнения PowerShell?</span><span class="sxs-lookup"><span data-stu-id="49b12-197">How do you determine the current PowerShell execution policy?</span></span>
1. <span data-ttu-id="49b12-198">Чему препятствует политика выполнения PowerShell по умолчанию на клиентских компьютерах Windows?</span><span class="sxs-lookup"><span data-stu-id="49b12-198">What does the default PowerShell execution policy on Windows client computers prevent from occurring?</span></span>
1. <span data-ttu-id="49b12-199">Как изменить политику выполнения PowerShell?</span><span class="sxs-lookup"><span data-stu-id="49b12-199">How do you change the PowerShell execution policy?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="49b12-200">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="49b12-200">Recommended Reading</span></span>

<span data-ttu-id="49b12-201">Тем, кто хочет более подробно изучить темы, описанные в этой главе, рекомендуется ознакомиться со следующими разделами справки по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-201">For those who want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="49b12-202">[about_Automatic_Variables][]</span><span class="sxs-lookup"><span data-stu-id="49b12-202">[about_Automatic_Variables][]</span></span>
- <span data-ttu-id="49b12-203">[about_Hash_Tables][]</span><span class="sxs-lookup"><span data-stu-id="49b12-203">[about_Hash_Tables][]</span></span>
- <span data-ttu-id="49b12-204">[about_Execution_Policies][]</span><span class="sxs-lookup"><span data-stu-id="49b12-204">[about_Execution_Policies][]</span></span>

<span data-ttu-id="49b12-205">В следующей главе вы узнаете о возможности обнаружения команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49b12-205">In the next chapter, you'll learn about the discoverability of commands in PowerShell.</span></span> <span data-ttu-id="49b12-206">Помимо прочих вопросов в ней будет рассматриваться обновление PowerShell, после которого разделы справки можно будет просматривать непосредственно в PowerShell, а не в Интернете.</span><span class="sxs-lookup"><span data-stu-id="49b12-206">One of the things that will be covered is how to update PowerShell so those help topics can be viewed right from within PowerShell instead of having to view them on the internet.</span></span>

<!-- link references -->
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[about_Hash_Tables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[about_Execution_Policies]: /powershell/module/microsoft.powershell.core/about/about_execution_policies
[Обновление существующей версии Windows PowerShell]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Upgrading existing Windows PowerShell]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Installing Windows PowerShell]: /powershell/scripting/install/installing-powershell (Установка Windows PowerShell)
[Installing PowerShell]: /powershell/scripting/install/installing-powershell
[Запуск Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
[Starting Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell

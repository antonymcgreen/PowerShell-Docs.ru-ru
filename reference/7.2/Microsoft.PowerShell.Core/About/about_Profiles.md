---
description: Описание создания и использования профиля PowerShell.
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: 3c739d6fd65714d5b6ef0f45990b614486d4e5ff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602083"
---
# <a name="about-profiles"></a><span data-ttu-id="29ab6-103">О профилях</span><span class="sxs-lookup"><span data-stu-id="29ab6-103">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="29ab6-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="29ab6-104">Short Description</span></span>
<span data-ttu-id="29ab6-105">Описание создания и использования профиля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-105">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="29ab6-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="29ab6-106">Long Description</span></span>

<span data-ttu-id="29ab6-107">Можно создать профиль PowerShell для настройки вашей среды и добавления элементов, относящихся к каждому сеансу PowerShell, который вы запускаете.</span><span class="sxs-lookup"><span data-stu-id="29ab6-107">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="29ab6-108">Профиль PowerShell — это скрипт, выполняющийся при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-108">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="29ab6-109">Профиль можно использовать в качестве сценария входа в систему для настройки среды.</span><span class="sxs-lookup"><span data-stu-id="29ab6-109">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="29ab6-110">Вы можете добавлять команды, псевдонимы, функции, переменные, оснастки, модули и диски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-110">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="29ab6-111">Можно также добавить в профиль другие элементы, относящиеся к сеансу, чтобы они были доступны в каждом сеансе без необходимости их импорта или повторного создания.</span><span class="sxs-lookup"><span data-stu-id="29ab6-111">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="29ab6-112">PowerShell поддерживает несколько профилей для пользователей и ведущих программ.</span><span class="sxs-lookup"><span data-stu-id="29ab6-112">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="29ab6-113">Однако профили не создаются.</span><span class="sxs-lookup"><span data-stu-id="29ab6-113">However, it does not create the profiles for you.</span></span> <span data-ttu-id="29ab6-114">В этом разделе описываются профили и описывается создание и обслуживание профилей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="29ab6-114">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="29ab6-115">В этом разделе объясняется, как использовать параметр " **Непрофиль** " консоли powershell (PowerShell.exe) для запуска PowerShell без профилей.</span><span class="sxs-lookup"><span data-stu-id="29ab6-115">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="29ab6-116">Кроме того, в нем объясняется воздействие политики выполнения PowerShell на профили.</span><span class="sxs-lookup"><span data-stu-id="29ab6-116">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="29ab6-117">Файлы профиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-117">The Profile Files</span></span>

<span data-ttu-id="29ab6-118">PowerShell поддерживает несколько файлов профилей.</span><span class="sxs-lookup"><span data-stu-id="29ab6-118">PowerShell supports several profile files.</span></span> <span data-ttu-id="29ab6-119">Кроме того, ведущие программы PowerShell могут поддерживать собственные профили конкретных узлов.</span><span class="sxs-lookup"><span data-stu-id="29ab6-119">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="29ab6-120">Например, консоль PowerShell поддерживает следующие файлы с базовым профилем.</span><span class="sxs-lookup"><span data-stu-id="29ab6-120">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="29ab6-121">Профили перечислены в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="29ab6-121">The profiles are listed in precedence order.</span></span> <span data-ttu-id="29ab6-122">Первый профиль имеет наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="29ab6-122">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="29ab6-123">Описание</span><span class="sxs-lookup"><span data-stu-id="29ab6-123">Description</span></span>               | <span data-ttu-id="29ab6-124">Путь</span><span class="sxs-lookup"><span data-stu-id="29ab6-124">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="29ab6-125">Все пользователи, все узлы</span><span class="sxs-lookup"><span data-stu-id="29ab6-125">All Users, All Hosts</span></span>      |<span data-ttu-id="29ab6-126">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-126">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="29ab6-127">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-127">All Users, Current Host</span></span>   |<span data-ttu-id="29ab6-128">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-128">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="29ab6-129">Текущий пользователь, все узлы</span><span class="sxs-lookup"><span data-stu-id="29ab6-129">Current User, All Hosts</span></span>   |<span data-ttu-id="29ab6-130">$Home \\ [мои] документы \\ PowerShell \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-130">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="29ab6-131">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-131">Current user, Current Host</span></span>|<span data-ttu-id="29ab6-132">$Home \\ [мои] документы \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ab6-132">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="29ab6-133">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-133">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="29ab6-134">Пути к профилю включают следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="29ab6-134">The profile paths include the following variables:</span></span>

- <span data-ttu-id="29ab6-135">`$PSHOME`Переменная, в которой хранится каталог установки для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-135">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="29ab6-136">`$Home`Переменная, в которой хранится домашний каталог текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="29ab6-136">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="29ab6-137">Кроме того, другие программы, на которых размещается PowerShell, могут поддерживать собственные профили.</span><span class="sxs-lookup"><span data-stu-id="29ab6-137">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="29ab6-138">Например, Visual Studio Code поддерживает следующие профили конкретных узлов.</span><span class="sxs-lookup"><span data-stu-id="29ab6-138">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="29ab6-139">Описание</span><span class="sxs-lookup"><span data-stu-id="29ab6-139">Description</span></span>               | <span data-ttu-id="29ab6-140">Путь</span><span class="sxs-lookup"><span data-stu-id="29ab6-140">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="29ab6-141">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-141">All users, Current Host</span></span>   |<span data-ttu-id="29ab6-142">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-142">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="29ab6-143">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-143">Current user, Current Host</span></span>|<span data-ttu-id="29ab6-144">$Home \\ [мои] документы \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ab6-144">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="29ab6-145">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="29ab6-145">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="29ab6-146">В справке PowerShell профиль "CurrentUser, текущий узел" является профилем, который чаще всего называется "вашим профилем PowerShell".</span><span class="sxs-lookup"><span data-stu-id="29ab6-146">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="29ab6-147">Переменная $PROFILE</span><span class="sxs-lookup"><span data-stu-id="29ab6-147">The $PROFILE variable</span></span>

<span data-ttu-id="29ab6-148">`$PROFILE`Автоматическая переменная сохраняет пути к профилям PowerShell, доступным в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="29ab6-148">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="29ab6-149">Чтобы просмотреть путь к профилю, отобразите значение `$PROFILE` переменной.</span><span class="sxs-lookup"><span data-stu-id="29ab6-149">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="29ab6-150">Можно также использовать `$PROFILE` переменную в команде для представления пути.</span><span class="sxs-lookup"><span data-stu-id="29ab6-150">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="29ab6-151">`$PROFILE`Переменная хранит путь к профилю "текущий пользователь, текущий узел".</span><span class="sxs-lookup"><span data-stu-id="29ab6-151">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="29ab6-152">Другие профили сохраняются в свойствах заметки `$PROFILE` переменной.</span><span class="sxs-lookup"><span data-stu-id="29ab6-152">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="29ab6-153">Например, `$PROFILE` переменная имеет следующие значения в консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-153">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="29ab6-154">Описание</span><span class="sxs-lookup"><span data-stu-id="29ab6-154">Description</span></span>                |<span data-ttu-id="29ab6-155">Имя</span><span class="sxs-lookup"><span data-stu-id="29ab6-155">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="29ab6-156">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-156">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="29ab6-157">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-157">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="29ab6-158">Текущий пользователь, все узлы</span><span class="sxs-lookup"><span data-stu-id="29ab6-158">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="29ab6-159">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="29ab6-159">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="29ab6-160">Все пользователи, все узлы</span><span class="sxs-lookup"><span data-stu-id="29ab6-160">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="29ab6-161">Поскольку значения `$PROFILE` переменной изменяются для каждого пользователя и в каждом ведущем приложении, убедитесь, что значения переменных профиля отображаются в каждом используемом хост-приложении PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-161">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="29ab6-162">Чтобы просмотреть текущие значения `$PROFILE` переменной, введите:</span><span class="sxs-lookup"><span data-stu-id="29ab6-162">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="29ab6-163">Переменную можно использовать `$PROFILE` во многих командах.</span><span class="sxs-lookup"><span data-stu-id="29ab6-163">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="29ab6-164">Например, следующая команда открывает профиль "текущий пользователь, текущий узел" в блокноте:</span><span class="sxs-lookup"><span data-stu-id="29ab6-164">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="29ab6-165">Следующая команда определяет, был ли создан профиль "все пользователи, все узлы" на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="29ab6-165">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="29ab6-166">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-166">How to create a profile</span></span>

<span data-ttu-id="29ab6-167">Чтобы создать профиль PowerShell, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="29ab6-167">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="29ab6-168">Например, чтобы создать профиль для текущего пользователя в текущем хост-приложении PowerShell, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="29ab6-168">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="29ab6-169">В этой команде `If` инструкция не позволяет перезаписывать существующий профиль.</span><span class="sxs-lookup"><span data-stu-id="29ab6-169">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="29ab6-170">Замените значение \<profile-path\> заполнителя на путь к файлу профиля, который необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="29ab6-170">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="29ab6-171">Чтобы создать профили "все пользователи" в Windows Vista и более поздних версиях Windows, запустите PowerShell с параметром " **Запуск от имени администратора** ".</span><span class="sxs-lookup"><span data-stu-id="29ab6-171">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="29ab6-172">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-172">How to edit a profile</span></span>

<span data-ttu-id="29ab6-173">Любой профиль PowerShell можно открыть в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="29ab6-173">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="29ab6-174">Чтобы открыть профиль текущего пользователя в текущем ведущем приложении PowerShell в блокноте, введите:</span><span class="sxs-lookup"><span data-stu-id="29ab6-174">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="29ab6-175">Чтобы открыть другие профили, укажите имя профиля.</span><span class="sxs-lookup"><span data-stu-id="29ab6-175">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="29ab6-176">Например, чтобы открыть профиль для всех пользователей всех ведущих приложений, введите:</span><span class="sxs-lookup"><span data-stu-id="29ab6-176">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="29ab6-177">Чтобы применить изменения, сохраните файл профиля и перезапустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-177">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="29ab6-178">Выбор профиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-178">How to choose a profile</span></span>

<span data-ttu-id="29ab6-179">Если вы используете несколько ведущих приложений, помещайте элементы, используемые во всех ведущих приложениях, в `$PROFILE.CurrentUserAllHosts` профиль.</span><span class="sxs-lookup"><span data-stu-id="29ab6-179">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="29ab6-180">Размещение элементов, относящихся к ведущему приложению, например команды, устанавливающей цвет фона для ведущего приложения, в профиле, характерном для этого хост-приложения.</span><span class="sxs-lookup"><span data-stu-id="29ab6-180">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="29ab6-181">Если вы являетесь администратором, который настраивает PowerShell для многих пользователей, следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="29ab6-181">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="29ab6-182">Хранение общих элементов в `$PROFILE.AllUsersAllHosts` профиле</span><span class="sxs-lookup"><span data-stu-id="29ab6-182">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="29ab6-183">Хранение элементов, относящихся к ведущему приложению, в `$PROFILE.AllUsersCurrentHost` профилях, относящихся к ведущему приложению</span><span class="sxs-lookup"><span data-stu-id="29ab6-183">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="29ab6-184">Хранение элементов для конкретных пользователей в пользовательских профилях</span><span class="sxs-lookup"><span data-stu-id="29ab6-184">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="29ab6-185">Обязательно ознакомьтесь с документацией по ведущему приложению, чтобы получить специальные реализации профилей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-185">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="29ab6-186">Как использовать профиль</span><span class="sxs-lookup"><span data-stu-id="29ab6-186">How to use a profile</span></span>

<span data-ttu-id="29ab6-187">Многие элементы, создаваемые в PowerShell, и большинство выполняемых команд влияют только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="29ab6-187">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="29ab6-188">После завершения сеанса элементы удаляются.</span><span class="sxs-lookup"><span data-stu-id="29ab6-188">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="29ab6-189">Команды и элементы, относящиеся к сеансу, включают переменные, привилегированные переменные, псевдонимы, функции, команды (кроме [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)) и модули PowerShell, добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="29ab6-189">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="29ab6-190">Чтобы сохранить эти элементы и сделать их доступными во всех будущих сеансах, добавьте их в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-190">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="29ab6-191">Другим распространенным применением профилей является сохранение часто используемых функций, псевдонимов и переменных.</span><span class="sxs-lookup"><span data-stu-id="29ab6-191">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="29ab6-192">При сохранении элементов в профиле их можно использовать в любом соответствующем сеансе без их повторного создания.</span><span class="sxs-lookup"><span data-stu-id="29ab6-192">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="29ab6-193">Как запустить профиль</span><span class="sxs-lookup"><span data-stu-id="29ab6-193">How to start a profile</span></span>

<span data-ttu-id="29ab6-194">При открытии файла профиля он остается пустым.</span><span class="sxs-lookup"><span data-stu-id="29ab6-194">When you open the profile file, it is blank.</span></span> <span data-ttu-id="29ab6-195">Однако его можно заполнить переменными, псевдонимами и командами, которые часто используются.</span><span class="sxs-lookup"><span data-stu-id="29ab6-195">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="29ab6-196">Вот несколько советов, которые помогут вам приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="29ab6-196">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="29ab6-197">Добавьте команды, упрощающие открытие профиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-197">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="29ab6-198">Это особенно полезно, если используется профиль, отличный от профиля "текущий пользователь, текущий узел".</span><span class="sxs-lookup"><span data-stu-id="29ab6-198">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="29ab6-199">Например, добавьте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="29ab6-199">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="29ab6-200">Добавление функции, которая перечисляет псевдонимы для любого командлета</span><span class="sxs-lookup"><span data-stu-id="29ab6-200">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="29ab6-201">Настройка консоли</span><span class="sxs-lookup"><span data-stu-id="29ab6-201">Customize your console</span></span>

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="29ab6-202">Добавление настраиваемой командной строки PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ab6-202">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="29ab6-203">Дополнительные сведения о командной строке PowerShell см. в разделе [about_Prompts](about_Prompts.md).</span><span class="sxs-lookup"><span data-stu-id="29ab6-203">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="29ab6-204">Параметр параметра непрофиля</span><span class="sxs-lookup"><span data-stu-id="29ab6-204">The NoProfile parameter</span></span>

<span data-ttu-id="29ab6-205">Чтобы запустить PowerShell без профилей, **используйте параметр** **PowerShell.exe**, программу, запускающую PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-205">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe**, the program that starts PowerShell.</span></span>

<span data-ttu-id="29ab6-206">Для начала откройте программу, в которой можно запустить PowerShell, например Cmd.exe или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ab6-206">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="29ab6-207">Можно также использовать диалоговое окно Запуск в Windows.</span><span class="sxs-lookup"><span data-stu-id="29ab6-207">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="29ab6-208">Тип:</span><span class="sxs-lookup"><span data-stu-id="29ab6-208">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="29ab6-209">Чтобы получить полный список параметров PowerShell.exe, введите:</span><span class="sxs-lookup"><span data-stu-id="29ab6-209">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="29ab6-210">Профили и политика выполнения</span><span class="sxs-lookup"><span data-stu-id="29ab6-210">Profiles and Execution Policy</span></span>

<span data-ttu-id="29ab6-211">Политика выполнения PowerShell определяет, можно ли выполнять сценарии и загружать файлы конфигурации, включая профили.</span><span class="sxs-lookup"><span data-stu-id="29ab6-211">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="29ab6-212">Политика выполнения **ограничена** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29ab6-212">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="29ab6-213">Это предотвращает запуск всех скриптов, включая профили.</span><span class="sxs-lookup"><span data-stu-id="29ab6-213">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="29ab6-214">Если используется политика "ограничено", профиль не запускается и его содержимое не применяется.</span><span class="sxs-lookup"><span data-stu-id="29ab6-214">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="29ab6-215">`Set-ExecutionPolicy`Команда задает и изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="29ab6-215">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="29ab6-216">Это одна из нескольких команд, которые применяются во всех сеансах PowerShell, поскольку значение сохраняется в реестре.</span><span class="sxs-lookup"><span data-stu-id="29ab6-216">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="29ab6-217">Его не нужно задавать при открытии консоли, и нет необходимости хранить `Set-ExecutionPolicy` команду в профиле.</span><span class="sxs-lookup"><span data-stu-id="29ab6-217">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="29ab6-218">Профили и удаленные сеансы</span><span class="sxs-lookup"><span data-stu-id="29ab6-218">Profiles and remote sessions</span></span>

<span data-ttu-id="29ab6-219">Профили PowerShell не запускаются автоматически в удаленных сеансах, поэтому команды, добавленные профилями, отсутствуют в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="29ab6-219">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="29ab6-220">Кроме того, `$PROFILE` Автоматическая переменная не заполняется в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="29ab6-220">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="29ab6-221">Чтобы запустить профиль в сеансе, используйте командлет [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="29ab6-221">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="29ab6-222">Например, следующая команда запускает профиль "текущий пользователь, текущий узел" с локального компьютера в сеансе `$s` .</span><span class="sxs-lookup"><span data-stu-id="29ab6-222">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="29ab6-223">Следующая команда запускает профиль "текущий пользователь, текущий узел" с удаленного компьютера в сеансе `$s` .</span><span class="sxs-lookup"><span data-stu-id="29ab6-223">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="29ab6-224">Так как `$PROFILE` переменная не заполнена, команда использует явный путь к профилю.</span><span class="sxs-lookup"><span data-stu-id="29ab6-224">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="29ab6-225">Мы используем оператор "точка с точкой", чтобы профиль выполнялся в текущей области на удаленном компьютере, а не в собственной области.</span><span class="sxs-lookup"><span data-stu-id="29ab6-225">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="29ab6-226">После выполнения этой команды команды, которые профиль добавляет в сеанс, будут доступны в `$s` .</span><span class="sxs-lookup"><span data-stu-id="29ab6-226">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="29ab6-227">См. также:</span><span class="sxs-lookup"><span data-stu-id="29ab6-227">See Also</span></span>

[<span data-ttu-id="29ab6-228">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="29ab6-228">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="29ab6-229">about_Functions</span><span class="sxs-lookup"><span data-stu-id="29ab6-229">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="29ab6-230">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="29ab6-230">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="29ab6-231">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="29ab6-231">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="29ab6-232">about_Signing</span><span class="sxs-lookup"><span data-stu-id="29ab6-232">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="29ab6-233">about_Remote</span><span class="sxs-lookup"><span data-stu-id="29ab6-233">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="29ab6-234">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="29ab6-234">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="29ab6-235">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="29ab6-235">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)


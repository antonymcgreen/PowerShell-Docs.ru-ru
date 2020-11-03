---
description: Описание создания и использования профиля PowerShell.
keywords: powershell,командлет
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: d0457cf485528f675840161383aa24d0f63781fb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231346"
---
# <a name="about-profiles"></a><span data-ttu-id="7c3e1-104">О профилях</span><span class="sxs-lookup"><span data-stu-id="7c3e1-104">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="7c3e1-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7c3e1-105">Short Description</span></span>
<span data-ttu-id="7c3e1-106">Описание создания и использования профиля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-106">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="7c3e1-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="7c3e1-107">Long Description</span></span>

<span data-ttu-id="7c3e1-108">Можно создать профиль PowerShell для настройки вашей среды и добавления элементов, относящихся к каждому сеансу PowerShell, который вы запускаете.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-108">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="7c3e1-109">Профиль PowerShell — это скрипт, выполняющийся при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-109">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="7c3e1-110">Профиль можно использовать в качестве сценария входа в систему для настройки среды.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-110">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="7c3e1-111">Вы можете добавлять команды, псевдонимы, функции, переменные, оснастки, модули и диски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-111">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="7c3e1-112">Можно также добавить в профиль другие элементы, относящиеся к сеансу, чтобы они были доступны в каждом сеансе без необходимости их импорта или повторного создания.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-112">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="7c3e1-113">PowerShell поддерживает несколько профилей для пользователей и ведущих программ.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-113">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="7c3e1-114">Однако профили не создаются.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-114">However, it does not create the profiles for you.</span></span> <span data-ttu-id="7c3e1-115">В этом разделе описываются профили и описывается создание и обслуживание профилей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-115">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="7c3e1-116">В этом разделе объясняется, как использовать параметр " **Непрофиль** " консоли powershell (PowerShell.exe) для запуска PowerShell без профилей.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-116">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="7c3e1-117">Кроме того, в нем объясняется воздействие политики выполнения PowerShell на профили.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-117">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="7c3e1-118">Файлы профиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-118">The Profile Files</span></span>

<span data-ttu-id="7c3e1-119">PowerShell поддерживает несколько файлов профилей.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-119">PowerShell supports several profile files.</span></span> <span data-ttu-id="7c3e1-120">Кроме того, ведущие программы PowerShell могут поддерживать собственные профили конкретных узлов.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-120">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="7c3e1-121">Например, консоль PowerShell поддерживает следующие файлы с базовым профилем.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-121">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="7c3e1-122">Профили перечислены в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-122">The profiles are listed in precedence order.</span></span> <span data-ttu-id="7c3e1-123">Первый профиль имеет наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-123">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="7c3e1-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7c3e1-124">Description</span></span>               | <span data-ttu-id="7c3e1-125">Путь</span><span class="sxs-lookup"><span data-stu-id="7c3e1-125">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="7c3e1-126">Все пользователи, все узлы</span><span class="sxs-lookup"><span data-stu-id="7c3e1-126">All Users, All Hosts</span></span>      |<span data-ttu-id="7c3e1-127">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-127">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="7c3e1-128">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-128">All Users, Current Host</span></span>   |<span data-ttu-id="7c3e1-129">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-129">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="7c3e1-130">Текущий пользователь, все узлы</span><span class="sxs-lookup"><span data-stu-id="7c3e1-130">Current User, All Hosts</span></span>   |<span data-ttu-id="7c3e1-131">$Home \\ [мои] документы \\ PowerShell \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-131">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="7c3e1-132">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-132">Current user, Current Host</span></span>|<span data-ttu-id="7c3e1-133">$Home \\ [мои] документы \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c3e1-133">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="7c3e1-134">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-134">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="7c3e1-135">Пути к профилю включают следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-135">The profile paths include the following variables:</span></span>

- <span data-ttu-id="7c3e1-136">`$PSHOME`Переменная, в которой хранится каталог установки для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-136">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="7c3e1-137">`$Home`Переменная, в которой хранится домашний каталог текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-137">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="7c3e1-138">Кроме того, другие программы, на которых размещается PowerShell, могут поддерживать собственные профили.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-138">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="7c3e1-139">Например, Visual Studio Code поддерживает следующие профили конкретных узлов.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-139">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="7c3e1-140">Описание</span><span class="sxs-lookup"><span data-stu-id="7c3e1-140">Description</span></span>               | <span data-ttu-id="7c3e1-141">Путь</span><span class="sxs-lookup"><span data-stu-id="7c3e1-141">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="7c3e1-142">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-142">All users, Current Host</span></span>   |<span data-ttu-id="7c3e1-143">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-143">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="7c3e1-144">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-144">Current user, Current Host</span></span>|<span data-ttu-id="7c3e1-145">$Home \\ [мои] документы \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c3e1-145">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="7c3e1-146">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="7c3e1-146">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="7c3e1-147">В справке PowerShell профиль "CurrentUser, текущий узел" является профилем, который чаще всего называется "вашим профилем PowerShell".</span><span class="sxs-lookup"><span data-stu-id="7c3e1-147">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="7c3e1-148">Переменная $PROFILE</span><span class="sxs-lookup"><span data-stu-id="7c3e1-148">The $PROFILE variable</span></span>

<span data-ttu-id="7c3e1-149">`$PROFILE`Автоматическая переменная сохраняет пути к профилям PowerShell, доступным в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-149">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="7c3e1-150">Чтобы просмотреть путь к профилю, отобразите значение `$PROFILE` переменной.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-150">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="7c3e1-151">Можно также использовать `$PROFILE` переменную в команде для представления пути.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-151">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="7c3e1-152">`$PROFILE`Переменная хранит путь к профилю "текущий пользователь, текущий узел".</span><span class="sxs-lookup"><span data-stu-id="7c3e1-152">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="7c3e1-153">Другие профили сохраняются в свойствах заметки `$PROFILE` переменной.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-153">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="7c3e1-154">Например, `$PROFILE` переменная имеет следующие значения в консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-154">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="7c3e1-155">Описание</span><span class="sxs-lookup"><span data-stu-id="7c3e1-155">Description</span></span>                |<span data-ttu-id="7c3e1-156">name</span><span class="sxs-lookup"><span data-stu-id="7c3e1-156">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="7c3e1-157">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-157">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="7c3e1-158">Текущий пользователь, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-158">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="7c3e1-159">Текущий пользователь, все узлы</span><span class="sxs-lookup"><span data-stu-id="7c3e1-159">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="7c3e1-160">Все пользователи, текущий узел</span><span class="sxs-lookup"><span data-stu-id="7c3e1-160">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="7c3e1-161">Все пользователи, все узлы</span><span class="sxs-lookup"><span data-stu-id="7c3e1-161">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="7c3e1-162">Поскольку значения `$PROFILE` переменной изменяются для каждого пользователя и в каждом ведущем приложении, убедитесь, что значения переменных профиля отображаются в каждом используемом хост-приложении PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-162">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="7c3e1-163">Чтобы просмотреть текущие значения `$PROFILE` переменной, введите:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-163">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="7c3e1-164">Переменную можно использовать `$PROFILE` во многих командах.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-164">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="7c3e1-165">Например, следующая команда открывает профиль "текущий пользователь, текущий узел" в блокноте:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-165">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="7c3e1-166">Следующая команда определяет, был ли создан профиль "все пользователи, все узлы" на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-166">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="7c3e1-167">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-167">How to create a profile</span></span>

<span data-ttu-id="7c3e1-168">Чтобы создать профиль PowerShell, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-168">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="7c3e1-169">Например, чтобы создать профиль для текущего пользователя в текущем хост-приложении PowerShell, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-169">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="7c3e1-170">В этой команде `If` инструкция не позволяет перезаписывать существующий профиль.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-170">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="7c3e1-171">Замените значение \<profile-path\> заполнителя на путь к файлу профиля, который необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-171">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="7c3e1-172">Чтобы создать профили "все пользователи" в Windows Vista и более поздних версиях Windows, запустите PowerShell с параметром " **Запуск от имени администратора** ".</span><span class="sxs-lookup"><span data-stu-id="7c3e1-172">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="7c3e1-173">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-173">How to edit a profile</span></span>

<span data-ttu-id="7c3e1-174">Любой профиль PowerShell можно открыть в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-174">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="7c3e1-175">Чтобы открыть профиль текущего пользователя в текущем ведущем приложении PowerShell в блокноте, введите:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-175">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="7c3e1-176">Чтобы открыть другие профили, укажите имя профиля.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-176">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="7c3e1-177">Например, чтобы открыть профиль для всех пользователей всех ведущих приложений, введите:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-177">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="7c3e1-178">Чтобы применить изменения, сохраните файл профиля и перезапустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-178">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="7c3e1-179">Выбор профиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-179">How to choose a profile</span></span>

<span data-ttu-id="7c3e1-180">Если вы используете несколько ведущих приложений, помещайте элементы, используемые во всех ведущих приложениях, в `$PROFILE.CurrentUserAllHosts` профиль.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-180">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="7c3e1-181">Размещение элементов, относящихся к ведущему приложению, например команды, устанавливающей цвет фона для ведущего приложения, в профиле, характерном для этого хост-приложения.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-181">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="7c3e1-182">Если вы являетесь администратором, который настраивает PowerShell для многих пользователей, следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-182">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="7c3e1-183">Хранение общих элементов в `$PROFILE.AllUsersAllHosts` профиле</span><span class="sxs-lookup"><span data-stu-id="7c3e1-183">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="7c3e1-184">Хранение элементов, относящихся к ведущему приложению, в `$PROFILE.AllUsersCurrentHost` профилях, относящихся к ведущему приложению</span><span class="sxs-lookup"><span data-stu-id="7c3e1-184">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="7c3e1-185">Хранение элементов для конкретных пользователей в пользовательских профилях</span><span class="sxs-lookup"><span data-stu-id="7c3e1-185">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="7c3e1-186">Обязательно ознакомьтесь с документацией по ведущему приложению, чтобы получить специальные реализации профилей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-186">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="7c3e1-187">Как использовать профиль</span><span class="sxs-lookup"><span data-stu-id="7c3e1-187">How to use a profile</span></span>

<span data-ttu-id="7c3e1-188">Многие элементы, создаваемые в PowerShell, и большинство выполняемых команд влияют только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-188">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="7c3e1-189">После завершения сеанса элементы удаляются.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-189">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="7c3e1-190">Команды и элементы, относящиеся к сеансу, включают переменные, привилегированные переменные, псевдонимы, функции, команды (кроме [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)) и модули PowerShell, добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-190">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="7c3e1-191">Чтобы сохранить эти элементы и сделать их доступными во всех будущих сеансах, добавьте их в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-191">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="7c3e1-192">Другим распространенным применением профилей является сохранение часто используемых функций, псевдонимов и переменных.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-192">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="7c3e1-193">При сохранении элементов в профиле их можно использовать в любом соответствующем сеансе без их повторного создания.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-193">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="7c3e1-194">Как запустить профиль</span><span class="sxs-lookup"><span data-stu-id="7c3e1-194">How to start a profile</span></span>

<span data-ttu-id="7c3e1-195">При открытии файла профиля он остается пустым.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-195">When you open the profile file, it is blank.</span></span> <span data-ttu-id="7c3e1-196">Однако его можно заполнить переменными, псевдонимами и командами, которые часто используются.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-196">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="7c3e1-197">Вот несколько советов, которые помогут вам приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-197">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="7c3e1-198">Добавьте команды, упрощающие открытие профиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-198">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="7c3e1-199">Это особенно полезно, если используется профиль, отличный от профиля "текущий пользователь, текущий узел".</span><span class="sxs-lookup"><span data-stu-id="7c3e1-199">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="7c3e1-200">Например, добавьте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-200">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="7c3e1-201">Добавление функции, которая перечисляет псевдонимы для любого командлета</span><span class="sxs-lookup"><span data-stu-id="7c3e1-201">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="7c3e1-202">Настройка консоли</span><span class="sxs-lookup"><span data-stu-id="7c3e1-202">Customize your console</span></span>

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

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="7c3e1-203">Добавление настраиваемой командной строки PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c3e1-203">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="7c3e1-204">Дополнительные сведения о командной строке PowerShell см. в разделе [about_Prompts](about_Prompts.md).</span><span class="sxs-lookup"><span data-stu-id="7c3e1-204">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="7c3e1-205">Параметр параметра непрофиля</span><span class="sxs-lookup"><span data-stu-id="7c3e1-205">The NoProfile parameter</span></span>

<span data-ttu-id="7c3e1-206">Чтобы запустить PowerShell без профилей, **используйте параметр** **PowerShell.exe** , программу, запускающую PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-206">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe** , the program that starts PowerShell.</span></span>

<span data-ttu-id="7c3e1-207">Для начала откройте программу, в которой можно запустить PowerShell, например Cmd.exe или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-207">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="7c3e1-208">Можно также использовать диалоговое окно Запуск в Windows.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-208">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="7c3e1-209">Тип:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-209">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="7c3e1-210">Чтобы получить полный список параметров PowerShell.exe, введите:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-210">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="7c3e1-211">Профили и политика выполнения</span><span class="sxs-lookup"><span data-stu-id="7c3e1-211">Profiles and Execution Policy</span></span>

<span data-ttu-id="7c3e1-212">Политика выполнения PowerShell определяет, можно ли выполнять сценарии и загружать файлы конфигурации, включая профили.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-212">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="7c3e1-213">Политика выполнения **ограничена** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-213">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="7c3e1-214">Это предотвращает запуск всех скриптов, включая профили.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-214">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="7c3e1-215">Если используется политика "ограничено", профиль не запускается и его содержимое не применяется.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-215">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="7c3e1-216">`Set-ExecutionPolicy`Команда задает и изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-216">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="7c3e1-217">Это одна из нескольких команд, которые применяются во всех сеансах PowerShell, поскольку значение сохраняется в реестре.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-217">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="7c3e1-218">Его не нужно задавать при открытии консоли, и нет необходимости хранить `Set-ExecutionPolicy` команду в профиле.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-218">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="7c3e1-219">Профили и удаленные сеансы</span><span class="sxs-lookup"><span data-stu-id="7c3e1-219">Profiles and remote sessions</span></span>

<span data-ttu-id="7c3e1-220">Профили PowerShell не запускаются автоматически в удаленных сеансах, поэтому команды, добавленные профилями, отсутствуют в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-220">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="7c3e1-221">Кроме того, `$PROFILE` Автоматическая переменная не заполняется в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-221">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="7c3e1-222">Чтобы запустить профиль в сеансе, используйте командлет [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="7c3e1-222">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="7c3e1-223">Например, следующая команда запускает профиль "текущий пользователь, текущий узел" с локального компьютера в сеансе `$s` .</span><span class="sxs-lookup"><span data-stu-id="7c3e1-223">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="7c3e1-224">Следующая команда запускает профиль "текущий пользователь, текущий узел" с удаленного компьютера в сеансе `$s` .</span><span class="sxs-lookup"><span data-stu-id="7c3e1-224">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="7c3e1-225">Так как `$PROFILE` переменная не заполнена, команда использует явный путь к профилю.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-225">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="7c3e1-226">Мы используем оператор "точка с точкой", чтобы профиль выполнялся в текущей области на удаленном компьютере, а не в собственной области.</span><span class="sxs-lookup"><span data-stu-id="7c3e1-226">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="7c3e1-227">После выполнения этой команды команды, которые профиль добавляет в сеанс, будут доступны в `$s` .</span><span class="sxs-lookup"><span data-stu-id="7c3e1-227">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c3e1-228">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c3e1-228">See Also</span></span>

[<span data-ttu-id="7c3e1-229">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7c3e1-229">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="7c3e1-230">about_Functions</span><span class="sxs-lookup"><span data-stu-id="7c3e1-230">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="7c3e1-231">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="7c3e1-231">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="7c3e1-232">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="7c3e1-232">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="7c3e1-233">about_Signing</span><span class="sxs-lookup"><span data-stu-id="7c3e1-233">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="7c3e1-234">about_Remote</span><span class="sxs-lookup"><span data-stu-id="7c3e1-234">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="7c3e1-235">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7c3e1-235">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="7c3e1-236">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7c3e1-236">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

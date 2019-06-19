---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Использование профилей в интегрированной среде сценариев Windows PowerShell
ms.openlocfilehash: 28354f39aaaa577cec69c1b3f62cfe16ef091218
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030602"
---
# <a name="how-to-use-profiles-in-windows-powershell-ise"></a><span data-ttu-id="b9f00-103">Использование профилей в интегрированной среде сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f00-103">How to Use Profiles in Windows PowerShell ISE</span></span>

<span data-ttu-id="b9f00-104">В этой статье объясняется, как использовать профили в интегрированной среде скриптов Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="b9f00-104">This topic explains how to use Profiles in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="b9f00-105">Перед выполнением задач из этого раздела рекомендуется ознакомиться со статьей [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) либо в области консоли ввести `Get-Help about_Profiles` и нажать клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="b9f00-105">We recommend that before performing the tasks in this section, you review [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles), or in the Console Pane, type, `Get-Help about_Profiles` and press **ENTER**.</span></span>

<span data-ttu-id="b9f00-106">Профиль — это сценарий интегрированной среды сценариев Windows PowerShell, который выполняется автоматически при запуске нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="b9f00-106">A profile is a Windows PowerShell ISE script that runs automatically when you start a new session.</span></span>  <span data-ttu-id="b9f00-107">Можно создать один или несколько профилей Windows PowerShell для интегрированной среды сценариев Windows PowerShell и использовать их для настройки среды Windows PowerShell для интегрированной среды сценариев Windows PowerShell, подготавливая ее к работе с помощью переменных, псевдонимов, функций, а также настроек цветов и шрифтов, которые должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="b9f00-107">You can create one or more Windows PowerShell profiles for Windows PowerShell ISE and use them to add the configure the Windows PowerShell or Windows PowerShell ISE environment, preparing it for your use, with variables, aliases, functions, and color and font preferences that you want available.</span></span> <span data-ttu-id="b9f00-108">Профиль затрагивает каждый запускаемый сеанс интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-108">A profile affects every Windows PowerShell ISE session that you start.</span></span>

> [!NOTE]
> <span data-ttu-id="b9f00-109">Политика выполнения Windows PowerShell определяет, можно ли запускать сценарии и загружать профиль.</span><span class="sxs-lookup"><span data-stu-id="b9f00-109">The Windows PowerShell execution policy determines whether you can run scripts and load a profile.</span></span> <span data-ttu-id="b9f00-110">Политика выполнения по умолчанию (Restricted) запрещает выполнение всех сценариев, включая профили.</span><span class="sxs-lookup"><span data-stu-id="b9f00-110">The default execution policy, “Restricted,” prevents all scripts from running, including profiles.</span></span> <span data-ttu-id="b9f00-111">При использовании политики "Restricted" загрузить профиль нельзя.</span><span class="sxs-lookup"><span data-stu-id="b9f00-111">If you use the “Restricted” policy, the profile cannot load.</span></span> <span data-ttu-id="b9f00-112">Дополнительные сведения о политике выполнения см. в статье [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="b9f00-112">For more information about execution policy, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="selecting-a-profile-to-use-in-the-windows-powershell-ise"></a><span data-ttu-id="b9f00-113">Выбор профиля для использования в интегрированной среде сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f00-113">Selecting a profile to use in the Windows PowerShell ISE</span></span>

<span data-ttu-id="b9f00-114">Интегрированная среда сценариев Windows PowerShell поддерживает профили для текущего пользователя и для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="b9f00-114">Windows PowerShell ISE supports profiles for the current user and all users.</span></span> <span data-ttu-id="b9f00-115">Он также поддерживает профили Windows PowerShell, затрагивающие все узлы.</span><span class="sxs-lookup"><span data-stu-id="b9f00-115">It also supports the Windows PowerShell profiles that apply to all hosts.</span></span>

<span data-ttu-id="b9f00-116">Выбор профиля зависит от того, каким образом вы используете Windows PowerShell и интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-116">The profile that you use is determined by how you use Windows PowerShell and Windows PowerShell ISE.</span></span>

- <span data-ttu-id="b9f00-117">Если для запуска Windows PowerShell используется только интегрированная среда сценариев Windows PowerShell, сохраните все элементы в одном из профилей интегрированной среды сценариев, таком как CurrentUserCurrentHost или AllUsersCurrentHost для интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-117">If you use only Windows PowerShell ISE to run Windows PowerShell, then save all your items in one of the ISE-specific profiles, such as the CurrentUserCurrentHost profile for Windows PowerShell ISE or the AllUsersCurrentHost profile for Windows PowerShell ISE.</span></span>

- <span data-ttu-id="b9f00-118">Если для запуска Windows PowerShell используется несколько основных программ, сохраните свои функции, псевдонимы, переменные и команды в профиле, затрагивающем все основные программы, таком как CurrentUserAllHosts или AllUsersAllHosts, и сохраните функции интегрированной среды сценариев, такие как настройки цветов и шрифтов, в CurrentUserCurrentHost или AllUsersCurrentHost для интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-118">If you use multiple host programs to run Windows PowerShell, save your functions, aliases, variables, and commands in a profile that affects all host programs, such as the CurrentUserAllHosts or the AllUsersAllHosts profile, and save ISE-specific features, like color and font customization in the CurrentUserCurrentHost profile for Windows PowerShell ISE profile or the AllUsersCurrentHost profile for Windows PowerShell ISE.</span></span>

<span data-ttu-id="b9f00-119">Ниже указаны профили, которые можно создать и использовать в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-119">The following are profiles that can be created and used in Windows PowerShell ISE.</span></span> <span data-ttu-id="b9f00-120">Каждый профиль сохраняется по собственному пути.</span><span class="sxs-lookup"><span data-stu-id="b9f00-120">Each profile is saved to its own specific path.</span></span>

| <span data-ttu-id="b9f00-121">Тип профиля</span><span class="sxs-lookup"><span data-stu-id="b9f00-121">Profile Type</span></span> | <span data-ttu-id="b9f00-122">Путь к профилю</span><span class="sxs-lookup"><span data-stu-id="b9f00-122">Profile Path</span></span> |
| --- | --- |
| <span data-ttu-id="b9f00-123">**Текущий пользователь, интегрированная среда сценариев PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b9f00-123">**Current user, PowerShell ISE**</span></span>| <span data-ttu-id="b9f00-124">`$PROFILE.CurrentUserCurrentHost` или `$PROFILE`</span><span class="sxs-lookup"><span data-stu-id="b9f00-124">`$PROFILE.CurrentUserCurrentHost`, or `$PROFILE`</span></span> |
| <span data-ttu-id="b9f00-125">**Все пользователи, интегрированная среда сценариев PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b9f00-125">**All users, PowerShell ISE**</span></span>| `$PROFILE.AllUsersCurrentHost` |
| <span data-ttu-id="b9f00-126">**Текущий пользователь, все узлы**</span><span class="sxs-lookup"><span data-stu-id="b9f00-126">**Current user, All hosts**</span></span>| `$PROFILE.CurrentUserAllHosts` |
| <span data-ttu-id="b9f00-127">**Все пользователи, все узлы**</span><span class="sxs-lookup"><span data-stu-id="b9f00-127">**All users, All hosts**</span></span> | `$PROFILE.AllUsersAllHosts` |

## <a name="to-create-a-new-profile"></a><span data-ttu-id="b9f00-128">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="b9f00-128">To create a new profile</span></span>

<span data-ttu-id="b9f00-129">Для создания профиля "Текущий пользователь, интегрированная среда сценариев PowerShell" выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b9f00-129">To create a new “Current user, Windows PowerShell ISE” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE ))
{ New-Item -Type File -Path $PROFILE -Force }
```

<span data-ttu-id="b9f00-130">Для создания профиля "Все пользователи, интегрированная среда сценариев PowerShell" выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b9f00-130">To create a new “All users, Windows PowerShell ISE” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.AllUsersCurrentHost))
{ New-Item -Type File -Path $PROFILE.AllUsersCurrentHost -Force }
```

<span data-ttu-id="b9f00-131">Для создания профиля "Текущий пользователь, все узлы" выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b9f00-131">To create a new “Current user, All Hosts” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.CurrentUserAllHosts))
{ New-Item -Type File -Path $PROFILE.CurrentUserAllHosts -Force }
```

<span data-ttu-id="b9f00-132">Для создания профиля "Все пользователи, все узлы" введите следующее:</span><span class="sxs-lookup"><span data-stu-id="b9f00-132">To create a new “All users, All Hosts” profile, type:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.AllUsersAllHosts))
{ New-Item -Type File -Path $PROFILE.AllUsersAllHosts -Force }
```

## <a name="to-edit-a-profile"></a><span data-ttu-id="b9f00-133">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="b9f00-133">To edit a profile</span></span>

1. <span data-ttu-id="b9f00-134">Чтобы открыть профиль, запустите команду psedit с переменной, которая указывает изменяемый профиль.</span><span class="sxs-lookup"><span data-stu-id="b9f00-134">To open the profile, run the command psedit with the variable that specifies the profile you want to edit.</span></span> <span data-ttu-id="b9f00-135">Например, для открытия профиля "Текущий пользователь, интегрированная среда сценариев PowerShell" введите: `psEdit $PROFILE`</span><span class="sxs-lookup"><span data-stu-id="b9f00-135">For example, to open the “Current user, Windows PowerShell ISE” profile, type: `psEdit $PROFILE`</span></span>

2. <span data-ttu-id="b9f00-136">Добавьте несколько элементов в профиль.</span><span class="sxs-lookup"><span data-stu-id="b9f00-136">Add some items to your profile.</span></span> <span data-ttu-id="b9f00-137">Ниже приведено несколько примеров, как можно приступить к работе:</span><span class="sxs-lookup"><span data-stu-id="b9f00-137">The following are a few examples to get you started:</span></span>

   - <span data-ttu-id="b9f00-138">Чтобы изменить цвет фона по умолчанию для области консоли на синий, введите в файле профиля следующее: `$psISE.Options.OutputPaneBackground = 'blue'` .</span><span class="sxs-lookup"><span data-stu-id="b9f00-138">To change the default background color of the Console Pane to blue, in the profile file type: `$psISE.Options.OutputPaneBackground = 'blue'` .</span></span> <span data-ttu-id="b9f00-139">Дополнительные сведения о переменной $psISE см. в статье [Справочник по объектной модели интегрированной среды сценариев Windows PowerShell](object-model/The-ISE-Object-Model-Hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="b9f00-139">For more information about the $psISE variable, see [Windows PowerShell ISE Object Model Reference](object-model/The-ISE-Object-Model-Hierarchy.md).</span></span>

   - <span data-ttu-id="b9f00-140">Чтобы изменить размер шрифта на 20, введите в файле профиля следующее: `$psISE.Options.FontSize =20`</span><span class="sxs-lookup"><span data-stu-id="b9f00-140">To change font size to 20, in the profile file type: `$psISE.Options.FontSize =20`</span></span>

3. <span data-ttu-id="b9f00-141">Чтобы сохранить файл профиля, в меню **Файл** щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9f00-141">To save your profile file, on the **File** menu, click **Save**.</span></span> <span data-ttu-id="b9f00-142">Внесенные изменения применяются при следующем открытии интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f00-142">Next time you open the Windows PowerShell ISE, your customizations are applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9f00-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b9f00-143">See Also</span></span>

- [<span data-ttu-id="b9f00-144">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="b9f00-144">about_Profiles</span></span>](/powershell/module/microsoft.powershell.core/about/about_profiles)
- [<span data-ttu-id="b9f00-145">Введение в интегрированную среду сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f00-145">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)

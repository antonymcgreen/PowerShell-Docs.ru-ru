---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Предварительные условия JEA
description: В этой статье описываются предварительные условия, которые нужно выполнить, чтобы начать работу с JEA.
ms.openlocfilehash: 5cc70a06887a2d0a840cc83117f865d3148056e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501734"
---
# <a name="prerequisites"></a><span data-ttu-id="680c3-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="680c3-104">Prerequisites</span></span>

<span data-ttu-id="680c3-105">Just Enough Administration — это функция, входящая в состав PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="680c3-105">Just Enough Administration is a feature included in PowerShell 5.0 and higher.</span></span> <span data-ttu-id="680c3-106">В этой статье описываются предварительные условия, которые нужно выполнить, чтобы начать работу с JEA.</span><span class="sxs-lookup"><span data-stu-id="680c3-106">This article describes the prerequisites that must be satisfied to start using JEA.</span></span>

## <a name="check-which-version-of-powershell-is-installed"></a><span data-ttu-id="680c3-107">Определение установленной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="680c3-107">Check which version of PowerShell is installed</span></span>

<span data-ttu-id="680c3-108">Чтобы узнать, какая версия PowerShell установлена на компьютере, проверьте переменную `$PSVersionTable` в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="680c3-108">To check which version of PowerShell is installed on your system, check the `$PSVersionTable` variable in a Windows PowerShell prompt.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

<span data-ttu-id="680c3-109">JEA доступна с PowerShell 5.0 и более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="680c3-109">JEA is available with PowerShell 5.0 and higher.</span></span> <span data-ttu-id="680c3-110">Для полной функциональности рекомендуется установить последнюю версию PowerShell, доступную для вашей системы.</span><span class="sxs-lookup"><span data-stu-id="680c3-110">For full functionality, it's recommended that you install the latest version of PowerShell available for your system.</span></span> <span data-ttu-id="680c3-111">В следующей таблице описывается доступность JEA на Windows Server:</span><span class="sxs-lookup"><span data-stu-id="680c3-111">The following table describes JEA's availability on Windows Server:</span></span>

| <span data-ttu-id="680c3-112">операционная система сервера</span><span class="sxs-lookup"><span data-stu-id="680c3-112">Server Operating System</span></span> |                <span data-ttu-id="680c3-113">Доступность JEA</span><span class="sxs-lookup"><span data-stu-id="680c3-113">JEA Availability</span></span>                |
| ----------------------- | ---------------------------------------------- |
| <span data-ttu-id="680c3-114">Windows Server 2016+</span><span class="sxs-lookup"><span data-stu-id="680c3-114">Windows Server 2016+</span></span>    | <span data-ttu-id="680c3-115">Предустанавливается</span><span class="sxs-lookup"><span data-stu-id="680c3-115">Preinstalled</span></span>                                   |
| <span data-ttu-id="680c3-116">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="680c3-116">Windows Server 2012 R2</span></span>  | <span data-ttu-id="680c3-117">Полный набор функций с WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="680c3-117">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="680c3-118">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="680c3-118">Windows Server 2012</span></span>     | <span data-ttu-id="680c3-119">Полный набор функций с WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="680c3-119">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="680c3-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="680c3-120">Windows Server 2008 R2</span></span>  | <span data-ttu-id="680c3-121">Ограниченная функциональность<sup>1</sup> с WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="680c3-121">Reduced functionality<sup>1</sup> with WMF 5.1</span></span> |

<span data-ttu-id="680c3-122">Вы можете также использовать JEA на домашнем или рабочем компьютере:</span><span class="sxs-lookup"><span data-stu-id="680c3-122">You can also use JEA on your home or work computer:</span></span>

| <span data-ttu-id="680c3-123">клиентская операционная система</span><span class="sxs-lookup"><span data-stu-id="680c3-123">Client Operating System</span></span> |                   <span data-ttu-id="680c3-124">Доступность JEA</span><span class="sxs-lookup"><span data-stu-id="680c3-124">JEA Availability</span></span>                   |
| ----------------------- | ---------------------------------------------------- |
| <span data-ttu-id="680c3-125">Windows 10 1607+</span><span class="sxs-lookup"><span data-stu-id="680c3-125">Windows 10 1607+</span></span>        | <span data-ttu-id="680c3-126">Предустанавливается</span><span class="sxs-lookup"><span data-stu-id="680c3-126">Preinstalled</span></span>                                         |
| <span data-ttu-id="680c3-127">Windows 10 1603, 1511</span><span class="sxs-lookup"><span data-stu-id="680c3-127">Windows 10 1603, 1511</span></span>   | <span data-ttu-id="680c3-128">Предустанавливается, с неполной функциональностью<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="680c3-128">Preinstalled, with reduced functionality<sup>2</sup></span></span> |
| <span data-ttu-id="680c3-129">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="680c3-129">Windows 10 1507</span></span>         | <span data-ttu-id="680c3-130">Недоступно</span><span class="sxs-lookup"><span data-stu-id="680c3-130">Not available</span></span>                                        |
| <span data-ttu-id="680c3-131">Windows 8, 8.1</span><span class="sxs-lookup"><span data-stu-id="680c3-131">Windows 8, 8.1</span></span>          | <span data-ttu-id="680c3-132">Полный набор функций с WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="680c3-132">Full functionality with WMF 5.1</span></span>                      |
| <span data-ttu-id="680c3-133">Windows 7</span><span class="sxs-lookup"><span data-stu-id="680c3-133">Windows 7</span></span>               | <span data-ttu-id="680c3-134">Ограниченная функциональность<sup>1</sup> с WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="680c3-134">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>       |

- <span data-ttu-id="680c3-135"><sup>1</sup> В JEA невозможно настроить использование групповых управляемых учетных записей служб в операционных системах Windows Server 2008 R2 или Windows 7.</span><span class="sxs-lookup"><span data-stu-id="680c3-135"><sup>1</sup> JEA can't be configured to use group-managed service accounts on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="680c3-136">Виртуальные учетные записи и другие возможности JEA *поддерживаются*.</span><span class="sxs-lookup"><span data-stu-id="680c3-136">Virtual accounts and other JEA features *are* supported.</span></span>

- <span data-ttu-id="680c3-137"><sup>2</sup> Следующие функции JEA не поддерживаются в Windows 10 версии 1511 и 1603.</span><span class="sxs-lookup"><span data-stu-id="680c3-137"><sup>2</sup> The following JEA features aren't supported on Windows 10 versions 1511 and 1603:</span></span>

  - <span data-ttu-id="680c3-138">Запуск от имени групповой управляемой учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="680c3-138">Running as a group-managed service account</span></span>
  - <span data-ttu-id="680c3-139">Правила условного доступа в конфигурациях сеанса.</span><span class="sxs-lookup"><span data-stu-id="680c3-139">Conditional access rules in session configurations</span></span>
  - <span data-ttu-id="680c3-140">Диск пользователя.</span><span class="sxs-lookup"><span data-stu-id="680c3-140">The user drive</span></span>
  - <span data-ttu-id="680c3-141">Предоставление разрешений для учетных записей локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="680c3-141">Granting access to local user accounts</span></span>

  <span data-ttu-id="680c3-142">Для обеспечения поддержки этих функций выполните обновление Windows до версии 1607 (юбилейное обновление) или более поздней.</span><span class="sxs-lookup"><span data-stu-id="680c3-142">To get support for these features, update Windows to version 1607 (Anniversary Update) or higher.</span></span>

### <a name="install-windows-management-framework"></a><span data-ttu-id="680c3-143">Установка Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="680c3-143">Install Windows Management Framework</span></span>

<span data-ttu-id="680c3-144">Если вы используете более старую версию PowerShell, может понадобиться установить в системе последнее обновление Windows Management Framework (WMF).</span><span class="sxs-lookup"><span data-stu-id="680c3-144">If you're running an older version of PowerShell, you may need to update your system with the latest Windows Management Framework (WMF) update.</span></span> <span data-ttu-id="680c3-145">Дополнительные сведения см. в документации по [WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="680c3-145">For more information, see the [WMF documentation](/powershell/scripting/wmf/overview).</span></span>

<span data-ttu-id="680c3-146">Рекомендуется проверить совместимость рабочей нагрузки с WMF до обновления всех серверов.</span><span class="sxs-lookup"><span data-stu-id="680c3-146">It's recommended that you test your workload's compatibility with WMF before upgrading all of your servers.</span></span>

<span data-ttu-id="680c3-147">Пользователям Windows 10 нужно установить последние обновления компонентов для получения текущей версии Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="680c3-147">Windows 10 users should install the latest feature updates to obtain the current version of Windows PowerShell.</span></span>

## <a name="enable-powershell-remoting"></a><span data-ttu-id="680c3-148">Включение удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="680c3-148">Enable PowerShell Remoting</span></span>

<span data-ttu-id="680c3-149">Удаленное взаимодействие PowerShell предоставляет собой основу, на которой построена функция JEA.</span><span class="sxs-lookup"><span data-stu-id="680c3-149">PowerShell Remoting provides the foundation on which JEA is built.</span></span> <span data-ttu-id="680c3-150">Перед использованием JEA необходимо включить удаленное взаимодействие PowerShell и должным образом защитить его в своей системе.</span><span class="sxs-lookup"><span data-stu-id="680c3-150">It's necessary to ensure PowerShell Remoting is enabled and properly secured before you can use JEA.</span></span> <span data-ttu-id="680c3-151">Дополнительные сведения см. в статье [Безопасность WinRM](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="680c3-151">For more information, see [WinRM Security](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

<span data-ttu-id="680c3-152">В Windows Server 2012, 2012 R2 и 2016 удаленное взаимодействие PowerShell включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="680c3-152">PowerShell Remoting is enabled by default on Windows Server 2012, 2012 R2, and 2016.</span></span> <span data-ttu-id="680c3-153">Удаленное взаимодействие PowerShell можно включить, выполнив приведенную ниже команду в окне PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="680c3-153">You can enable PowerShell Remoting by running the following command in an elevated PowerShell window.</span></span>

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a><span data-ttu-id="680c3-154">Включение ведения журнала для блока сценариев и модуля PowerShell (необязательно)</span><span class="sxs-lookup"><span data-stu-id="680c3-154">Enable PowerShell module and script block logging (optional)</span></span>

<span data-ttu-id="680c3-155">Указанные ниже действия позволят включить ведение журнала действий PowerShell в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="680c3-155">The following steps enable logging for all PowerShell actions on your system.</span></span> <span data-ttu-id="680c3-156">Ведение журнала модуля PowerShell не является обязательным для JEA, однако рекомендуется включить его, чтобы выполняемые пользователями команды регистрировались в центральном расположении.</span><span class="sxs-lookup"><span data-stu-id="680c3-156">PowerShell Module Logging isn't required for JEA, however it's recommended you turn on logging to ensure the commands users run are logged in a central location.</span></span>

<span data-ttu-id="680c3-157">Политику ведения журнала модуля PowerShell можно настроить с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="680c3-157">You can configure the PowerShell Module Logging policy using Group Policy.</span></span>

1. <span data-ttu-id="680c3-158">Откройте редактор локальных групповых политик на рабочей станции или объект групповой политики в консоли управления групповыми политиками на контроллере домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="680c3-158">Open the Local Group Policy Editor on a workstation or a Group Policy Object in the Group Policy Management Console on an Active Directory Domain Controller</span></span>
2. <span data-ttu-id="680c3-159">Откройте папку **Конфигурация компьютера\\Административные шаблоны\\Компоненты Windows\\Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="680c3-159">Navigate to **Computer Configuration\\Administrative Templates\\Windows Components\\Windows PowerShell**</span></span>
3. <span data-ttu-id="680c3-160">Дважды щелкните пункт **Включить ведение журнала модулей**.</span><span class="sxs-lookup"><span data-stu-id="680c3-160">Double-click on **Turn on Module Logging**</span></span>
4. <span data-ttu-id="680c3-161">Нажмите кнопку **Включено**.</span><span class="sxs-lookup"><span data-stu-id="680c3-161">Click **Enabled**</span></span>
5. <span data-ttu-id="680c3-162">В разделе "Параметры" нажмите кнопку **Показать** рядом с именами модулей.</span><span class="sxs-lookup"><span data-stu-id="680c3-162">In the Options section, click on **Show** next to Module Names</span></span>
6. <span data-ttu-id="680c3-163">Введите `*` во всплывающем окне, чтобы регистрировать в журнале команды из всех модулей.</span><span class="sxs-lookup"><span data-stu-id="680c3-163">Type `*` in the pop-up window to log commands from all modules.</span></span>
7. <span data-ttu-id="680c3-164">Нажмите кнопку **ОК** для применения политики.</span><span class="sxs-lookup"><span data-stu-id="680c3-164">Click **OK** to set the policy</span></span>
8. <span data-ttu-id="680c3-165">Дважды щелкните **Включить регистрацию блоков сценариев PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="680c3-165">Double-click on **Turn on PowerShell Script Block Logging**</span></span>
9. <span data-ttu-id="680c3-166">Нажмите кнопку **Включено**.</span><span class="sxs-lookup"><span data-stu-id="680c3-166">Click **Enabled**</span></span>
10. <span data-ttu-id="680c3-167">Нажмите кнопку **ОК** для применения политики.</span><span class="sxs-lookup"><span data-stu-id="680c3-167">Click **OK** to set the policy</span></span>
11. <span data-ttu-id="680c3-168">Запустите `gpupdate` или дождитесь обработки обновленной политики и применения этих параметров групповой политикой (только на компьютерах, присоединенных к домену).</span><span class="sxs-lookup"><span data-stu-id="680c3-168">(On domain-joined machines only) Run `gpupdate` or wait for Group Policy to process the updated policy and apply the settings</span></span>

<span data-ttu-id="680c3-169">С помощью групповой политики также можно включить запись действий PowerShell в масштабе всей системы.</span><span class="sxs-lookup"><span data-stu-id="680c3-169">You can also enable system-wide PowerShell transcription through Group Policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="680c3-170">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="680c3-170">Next steps</span></span>

[<span data-ttu-id="680c3-171">Создание файла возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="680c3-171">Create a role capability file</span></span>](role-capabilities.md)

[<span data-ttu-id="680c3-172">Создание файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="680c3-172">Create a session configuration file</span></span>](session-configurations.md)

## <a name="see-also"></a><span data-ttu-id="680c3-173">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="680c3-173">See also</span></span>

[<span data-ttu-id="680c3-174">Безопасность WinRM</span><span class="sxs-lookup"><span data-stu-id="680c3-174">WinRM Security</span></span>](/powershell/scripting/learn/remoting/winrmsecurity)

[<span data-ttu-id="680c3-175">PowerShell ♥ the Blue Team</span><span class="sxs-lookup"><span data-stu-id="680c3-175">PowerShell ♥ the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

---
description: Описывает файлы конфигурации сеанса, которые используются в конфигурации сеанса (также называемой конечной точкой) для определения среды сеансов, использующих конфигурацию сеанса.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 45c8a6e0ba8478e0a49cb287cd4311d7556a42ea
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231085"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="223fb-104">Сведения о файлах конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-104">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="223fb-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="223fb-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="223fb-106">Описывает файлы конфигурации сеанса, которые используются в конфигурации сеанса (также называемой конечной точкой) для определения среды сеансов, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-106">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="223fb-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="223fb-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="223fb-108">"Файл конфигурации сеанса" — это текстовый файл с расширением pssc, который содержит хэш-таблицу свойств и значений конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-108">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="223fb-109">Для задания свойств конфигурации сеанса можно использовать файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-109">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="223fb-110">Это определяет среду всех сеансов PowerShell, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-110">Doing so defines the environment of any PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="223fb-111">Файлы конфигурации сеанса упрощают создание пользовательских конфигураций сеансов без использования сложных сборок или скриптов C#.</span><span class="sxs-lookup"><span data-stu-id="223fb-111">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="223fb-112">"Конфигурация сеанса" или "конечная точка" — это коллекция параметров локального компьютера, определяющая, как пользователи могут создавать сеансы на компьютере. команды, которые пользователи могут выполнять в этих сеансах; и должен ли сеанс запускаться как привилегированная виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="223fb-112">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="223fb-113">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="223fb-113">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="223fb-114">Конфигурации сеансов появились в Windows PowerShell 2,0, а файлы конфигурации сеанса появились в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="223fb-114">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="223fb-115">Для включения файла конфигурации сеанса в конфигурацию сеанса необходимо использовать Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="223fb-115">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="223fb-116">Тем не менее пользователи Windows PowerShell 2,0 (и более поздние версии) зависят от параметров в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-116">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="223fb-117">Создание пользовательских сеансов</span><span class="sxs-lookup"><span data-stu-id="223fb-117">Creating Custom Sessions</span></span>

<span data-ttu-id="223fb-118">Вы можете настроить множество функций сеанса PowerShell, указав свойства сеанса в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-118">You can customize many features of a PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="223fb-119">Вы можете настроить сеанс, написав программу на C#, которая определяет пользовательское пространство выполнения, или можно использовать файл конфигурации сеанса для определения свойств сеансов, созданных с помощью конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-119">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="223fb-120">В качестве общего правила проще использовать файл конфигурации сеанса, чем написание программы на C#.</span><span class="sxs-lookup"><span data-stu-id="223fb-120">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="223fb-121">Файл конфигурации сеанса можно использовать для создания таких элементов, как полнофункциональные сеансы для пользователей с высоким уровнем доверия. Заблокированные сеансы, которые обеспечивают минимальный доступ; сеансы, предназначенные для конкретных и содержащие только модули, необходимые для этих задач; и сеансы, в которых непривилегированные пользователи могут выполнять только определенные команды в качестве привилегированной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="223fb-121">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="223fb-122">Помимо этого, можно управлять тем, могут ли пользователи сеанса использовать элементы языка PowerShell, такие как блоки скриптов, или могут ли они выполнять только команды.</span><span class="sxs-lookup"><span data-stu-id="223fb-122">In addition to that, you can manage whether users of the session can use PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="223fb-123">Вы можете управлять версией пользователей PowerShell, которые могут выполняться в сеансе. Управление тем, какие модули импортируются в сеанс; и управлять тем, какие командлеты, функции и псевдонимы могут выполнять пользователи сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-123">You can manage the version of PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="223fb-124">При использовании поля RoleDefinitions можно предоставить пользователям различные возможности в сеансе на основе членства в группе.</span><span class="sxs-lookup"><span data-stu-id="223fb-124">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="223fb-125">Дополнительные сведения о RoleDefinitions и определении этого значения см. в разделе справки по командлету New-PSRoleCapabilityFile.</span><span class="sxs-lookup"><span data-stu-id="223fb-125">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="223fb-126">Создание файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-126">Creating a Session Configuration File</span></span>

<span data-ttu-id="223fb-127">Самый простой способ создать файл конфигурации сеанса — с помощью командлета New-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="223fb-127">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="223fb-128">Этот командлет создает файл, использующий правильный синтаксис и формат, который автоматически проверяет многие значения свойств файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="223fb-128">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="223fb-129">Подробное описание свойств, которые можно задать в файле конфигурации сеанса, см. в разделе справки по командлету New-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="223fb-129">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="223fb-130">Следующая команда создает файл конфигурации сеанса, в котором используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="223fb-130">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="223fb-131">В результирующем файле конфигурации используются только значения по умолчанию, так как в них включены параметры, отличные от параметра Path (который указывает путь к файлу).</span><span class="sxs-lookup"><span data-stu-id="223fb-131">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="223fb-132">Чтобы просмотреть новый файл конфигурации в текстовом редакторе по умолчанию, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="223fb-132">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="223fb-133">Чтобы создать конфигурацию сеанса для сеансов, в которых пользователь может выполнять команды, но не использовать другие элементы языка PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="223fb-133">To create a session configuration for sessions in which user can run commands, but not use other elements of the PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="223fb-134">В предыдущей команде Присвоение параметру Лангуажемоде значения "не язык" запрещает пользователям выполнять такие действия, как написание или выполнение скриптов, а также использование переменных.</span><span class="sxs-lookup"><span data-stu-id="223fb-134">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="223fb-135">Чтобы создать конфигурацию сеанса для сеансов, в которых пользователи могут использовать только командлеты Get, введите:</span><span class="sxs-lookup"><span data-stu-id="223fb-135">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="223fb-136">В предыдущем примере при присвоении параметру VisibleCmdlets значения GET-\* ограничивается число пользователей командлетами, имена которых начинаются со строки со строковым значением Get-.</span><span class="sxs-lookup"><span data-stu-id="223fb-136">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="223fb-137">Чтобы создать конфигурацию сеанса для сеансов, работающих под привилегированной виртуальной учетной записью, а не учетных данных пользователя, введите:</span><span class="sxs-lookup"><span data-stu-id="223fb-137">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="223fb-138">Чтобы создать конфигурацию сеанса для сеансов, в которых команды, видимые пользователю, указаны в файле возможностей роли, введите:</span><span class="sxs-lookup"><span data-stu-id="223fb-138">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="223fb-139">Использование файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-139">Using a Session Configuration File</span></span>

<span data-ttu-id="223fb-140">Файл конфигурации сеанса можно включить во время создания конфигурации сеанса или добавить файл в конфигурацию сеанса позднее.</span><span class="sxs-lookup"><span data-stu-id="223fb-140">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="223fb-141">Чтобы включить файл конфигурации сеанса при создании конфигурации сеанса, используйте параметр Path командлета Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="223fb-141">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="223fb-142">Например, следующая команда использует файл языка pssc при создании конфигурации сеанса на основе языка.</span><span class="sxs-lookup"><span data-stu-id="223fb-142">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="223fb-143">Когда запускается новый сеанс на языке, пользователи получают доступ только к командам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="223fb-143">When a new NoLanguage session starts, users will only have access to PowerShell commands.</span></span>

<span data-ttu-id="223fb-144">Чтобы добавить файл конфигурации сеанса в существующую конфигурацию сеанса, используйте командлет Set-PSSessionConfiguration и параметр path.</span><span class="sxs-lookup"><span data-stu-id="223fb-144">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="223fb-145">Это влияет на все новые сеансы, созданные с помощью указанной конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-145">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="223fb-146">Обратите внимание, что командлет Set-PSSessionConfiguration изменяет сам сеанс и не изменяет файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-146">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="223fb-147">Например, следующая команда добавляет файл. pssc в конфигурацию сеанса Локкеддовн.</span><span class="sxs-lookup"><span data-stu-id="223fb-147">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="223fb-148">Когда пользователи используют конфигурацию сеанса Локкеддовн для создания сеанса, они смогут выполнять командлеты, но не смогут создавать или использовать переменные, назначать значения или использовать другие языковые элементы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="223fb-148">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other PowerShell language elements.</span></span>

<span data-ttu-id="223fb-149">Следующая команда использует командлет New-PSSession для создания сеанса на компьютере SRV01, который использует конфигурацию сеанса Локкеддовн, сохраняя ссылку на объект в сеансе в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="223fb-149">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="223fb-150">Список управления доступом (ACL) конфигурации сеанса определяет, кто может использовать его для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-150">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="223fb-151">Так как ограничения языка не были добавлены в конфигурацию сеанса Локкеддовн, пользователи в сеансах Локкеддовн смогут выполнять только команды и командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="223fb-151">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run PowerShell commands and cmdlets.</span></span> <span data-ttu-id="223fb-152">Например, следующие две команды используют командлет Invoke-Command для выполнения команд в сеансе, на который ссылается переменная $s.</span><span class="sxs-lookup"><span data-stu-id="223fb-152">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="223fb-153">Первая команда, которая запускает командлет Get-UICulture и не использует переменные, выполняется с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="223fb-153">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="223fb-154">Вторая команда, которая получает значение переменной $PSUICulture, завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="223fb-154">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="223fb-155">Изменение файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-155">Editing a Session Configuration File</span></span>

<span data-ttu-id="223fb-156">Все параметры в конфигурации сеанса, за исключением RunAsVirtualAccount и Рунасвиртуалаккаунтграупс, могут быть изменены путем изменения файла конфигурации сеанса, используемого конфигурацией сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-156">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="223fb-157">Для этого сначала найдите активную копию файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-157">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="223fb-158">При использовании файла конфигурации сеанса в конфигурации сеанса PowerShell создает активную копию файла конфигурации сеанса и сохраняет ее в \$ \\ каталоге pshome сессионконфиг на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="223fb-158">When you use a session configuration file in a session configuration, PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="223fb-159">Расположение активной копии файла конфигурации сеанса хранится в свойстве Конфигфилепас объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-159">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="223fb-160">Следующая команда возвращает расположение файла конфигурации сеанса для конфигурации сеанса на языке.</span><span class="sxs-lookup"><span data-stu-id="223fb-160">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="223fb-161">Эта команда возвращает путь к файлу, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="223fb-161">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="223fb-162">Файл. pssc можно изменить в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="223fb-162">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="223fb-163">После сохранения файла он будет использоваться всеми новыми сеансами, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-163">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="223fb-164">Если необходимо изменить параметры RunAsVirtualAccount или Рунасвиртуалаккаунтграупс, необходимо отменить регистрацию конфигурации сеанса и повторно зарегистрировать файл конфигурации сеанса, содержащий измененные значения.</span><span class="sxs-lookup"><span data-stu-id="223fb-164">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="223fb-165">Тестирование файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-165">Testing a Session Configuration File</span></span>

<span data-ttu-id="223fb-166">Используйте командлет Test-PSSessionConfigurationFile для тестирования файлов конфигурации сеанса, измененных вручную.</span><span class="sxs-lookup"><span data-stu-id="223fb-166">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="223fb-167">Это важно. Если синтаксис и значения файла не являются допустимыми, пользователи не смогут использовать конфигурацию сеанса для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-167">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="223fb-168">Например, следующая команда проверяет файл конфигурации активного сеанса в конфигурации сеанса на языке.</span><span class="sxs-lookup"><span data-stu-id="223fb-168">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="223fb-169">Если синтаксис и значения в файле конфигурации являются допустимыми Test-PSSessionConfigurationFile возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="223fb-169">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="223fb-170">Если синтаксис и значения не являются допустимыми, командлет возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="223fb-170">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="223fb-171">Test-PSSessionConfigurationFile можно использовать для тестирования любого файла конфигурации сеанса, включая файлы, создаваемые командлетом New-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="223fb-171">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="223fb-172">Дополнительные сведения см. в разделе справки по командлету Test-PSSessionConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="223fb-172">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="223fb-173">Удаление файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="223fb-173">Removing a Session Configuration File</span></span>

<span data-ttu-id="223fb-174">Невозможно удалить файл конфигурации сеанса из конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-174">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="223fb-175">Однако можно заменить файл новым файлом, использующим параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="223fb-175">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="223fb-176">Это фактически отменяет параметры, используемые исходным файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="223fb-176">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="223fb-177">Чтобы заменить файл конфигурации сеанса, создайте новый файл конфигурации сеанса, который использует параметры по умолчанию, а затем используйте командлет Set-PSSessionConfiguration, чтобы заменить файл конфигурации пользовательского сеанса новым файлом.</span><span class="sxs-lookup"><span data-stu-id="223fb-177">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="223fb-178">Например, следующие команды создают файл конфигурации сеанса по умолчанию, а затем заменяют файл конфигурации активного сеанса в конфигурации сеанса на языке.</span><span class="sxs-lookup"><span data-stu-id="223fb-178">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="223fb-179">Когда эти команды будут завершены, конфигурация сеанса неязыкового интерфейса будет обеспечивать полную языковую поддержку (параметр по умолчанию) для всех сеансов, созданных с помощью этой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-179">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="223fb-180">Просмотр свойств конфигурации сеанса. объекты конфигурации сеанса, представляющие конфигурации сеансов с помощью файлов конфигурации сеанса, имеют дополнительные свойства, которые упрощают обнаружение и анализ конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="223fb-180">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="223fb-181">(Обратите внимание, что имя типа, приведенное ниже, включает в себя форматированное определение представления.) Свойства можно просмотреть, выполнив командлет Get-PSSessionConfiguration и передав возвращенные данные в командлет Get-Member:</span><span class="sxs-lookup"><span data-stu-id="223fb-181">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

<span data-ttu-id="223fb-182">Эти свойства упрощают поиск конкретных конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="223fb-182">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="223fb-183">Например, свойство ExecutionPolicy можно использовать для поиска конфигурации сеанса, которая поддерживает сеансы с политикой выполнения RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="223fb-183">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="223fb-184">Обратите внимание, что, поскольку свойство ExecutionPolicy существует только в сеансах, использующих файлы конфигурации сеанса, команда может не возвращать все конфигурации соответствующих сеансов.</span><span class="sxs-lookup"><span data-stu-id="223fb-184">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="223fb-185">Следующая команда получает конфигурации сеанса, в которых выполняющий является администратор Exchange.</span><span class="sxs-lookup"><span data-stu-id="223fb-185">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="223fb-186">Чтобы просмотреть сведения об определениях ролей, связанных с конфигурацией, используйте командлет Get-PSSessionCapability.</span><span class="sxs-lookup"><span data-stu-id="223fb-186">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="223fb-187">Этот командлет позволяет определить команды и среду, доступные конкретным пользователям в конкретных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="223fb-187">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="223fb-188">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="223fb-188">NOTES</span></span>

<span data-ttu-id="223fb-189">Конфигурации сеансов также поддерживают тип сеанса, называемый пустым сеансом.</span><span class="sxs-lookup"><span data-stu-id="223fb-189">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="223fb-190">Пустой тип сеанса позволяет создавать пользовательские сеансы с выбранными командами.</span><span class="sxs-lookup"><span data-stu-id="223fb-190">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="223fb-191">Если не добавить модули, функции или скрипты в пустой сеанс, сеанс будет ограничен выражениями и может не быть ни в каких практических случаях использовать.</span><span class="sxs-lookup"><span data-stu-id="223fb-191">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="223fb-192">Свойство SessionType указывает, работаете ли вы с пустым сеансом.</span><span class="sxs-lookup"><span data-stu-id="223fb-192">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="223fb-193">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="223fb-193">SEE ALSO</span></span>

[<span data-ttu-id="223fb-194">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="223fb-194">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="223fb-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="223fb-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="223fb-196">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-196">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="223fb-197">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-197">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="223fb-198">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-198">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="223fb-199">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="223fb-199">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="223fb-200">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-200">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="223fb-201">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-201">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="223fb-202">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="223fb-202">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="223fb-203">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="223fb-203">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="223fb-204">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="223fb-204">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="223fb-205">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="223fb-205">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)


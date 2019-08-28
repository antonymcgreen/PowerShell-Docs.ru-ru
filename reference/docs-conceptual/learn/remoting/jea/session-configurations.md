---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Конфигурации сеансов JEA
ms.openlocfilehash: 650d0d11ef13605847d0822249e29e3491180629
ms.sourcegitcommit: e894ed833cef57967cdaf002f8c883f66864e836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2019
ms.locfileid: "70017735"
---
# <a name="jea-session-configurations"></a><span data-ttu-id="fe541-103">Конфигурации сеансов JEA</span><span class="sxs-lookup"><span data-stu-id="fe541-103">JEA Session Configurations</span></span>

<span data-ttu-id="fe541-104">Конечная точка JEA регистрируется в системе путем создания и регистрации файла конфигурации сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe541-104">A JEA endpoint is registered on a system by creating and registering a PowerShell session configuration file.</span></span> <span data-ttu-id="fe541-105">Конфигурации сеансов определяют, кто может использовать конечную точку JEA и к каким ролям будет предоставлен доступ.</span><span class="sxs-lookup"><span data-stu-id="fe541-105">Session configurations define who can use the JEA endpoint and which roles they have access to.</span></span> <span data-ttu-id="fe541-106">Они также определяют глобальные параметры, которые применяются ко всем пользователям в сеансе JEA.</span><span class="sxs-lookup"><span data-stu-id="fe541-106">They also define global settings that apply to all users of the JEA session.</span></span>

## <a name="create-a-session-configuration-file"></a><span data-ttu-id="fe541-107">Создание файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="fe541-107">Create a session configuration file</span></span>

<span data-ttu-id="fe541-108">Чтобы зарегистрировать конечную точку JEA, следует указать способ ее настройки.</span><span class="sxs-lookup"><span data-stu-id="fe541-108">To register a JEA endpoint, you must specify how that endpoint is configured.</span></span> <span data-ttu-id="fe541-109">Существует множество факторов, которые следует учитывать.</span><span class="sxs-lookup"><span data-stu-id="fe541-109">There are many options to consider.</span></span> <span data-ttu-id="fe541-110">Ниже приведены наиболее важные из них.</span><span class="sxs-lookup"><span data-stu-id="fe541-110">The most important options are:</span></span>

- <span data-ttu-id="fe541-111">Кто имеет доступ к конечной точке JEA?</span><span class="sxs-lookup"><span data-stu-id="fe541-111">Who has access to the JEA endpoint</span></span>
- <span data-ttu-id="fe541-112">Какие роли им назначены</span><span class="sxs-lookup"><span data-stu-id="fe541-112">Which roles they be assigned</span></span>
- <span data-ttu-id="fe541-113">Какое удостоверение JEA использует на самом деле</span><span class="sxs-lookup"><span data-stu-id="fe541-113">Which identity JEA uses under the covers</span></span>
- <span data-ttu-id="fe541-114">Имя конечной точки JEA</span><span class="sxs-lookup"><span data-stu-id="fe541-114">The name of the JEA endpoint</span></span>

<span data-ttu-id="fe541-115">Все они определяются в файле конфигурации сеанса PowerShell, который представляет собой файл данных PowerShell с расширением `.pssc`.</span><span class="sxs-lookup"><span data-stu-id="fe541-115">These options are defined in a PowerShell data file with a `.pssc` extension known as a PowerShell session configuration file.</span></span> <span data-ttu-id="fe541-116">Файл конфигурации сеанса можно открыть в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="fe541-116">The session configuration file can be edited using any text editor.</span></span>

<span data-ttu-id="fe541-117">Выполните следующую команду, чтобы создать пустой шаблон файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fe541-117">Run the following command to create a blank template configuration file.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> <span data-ttu-id="fe541-118">По умолчанию файл шаблона включает только основные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fe541-118">Only the most common configuration options are included in the template file by default.</span></span> <span data-ttu-id="fe541-119">Чтобы включить в создаваемый PSSC-файл все применимые настройки, используйте параметр `-Full`.</span><span class="sxs-lookup"><span data-stu-id="fe541-119">Use the `-Full` switch to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="fe541-120">Поле `-SessionType RestrictedRemoteServer` указывает, что конфигурация сеанса будет использоваться JEA для безопасного управления.</span><span class="sxs-lookup"><span data-stu-id="fe541-120">The `-SessionType RestrictedRemoteServer` field indicates that the session configuration is used by JEA for secure management.</span></span> <span data-ttu-id="fe541-121">Настроенные таким образом сеансы работают в режиме **NoLanguage** и содержат только следующие команды (и псевдонимы) по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="fe541-121">Sessions of this type operate in **NoLanguage** mode and only have access to the following default commands (and aliases):</span></span>

- <span data-ttu-id="fe541-122">Clear-Host (cls, clear)</span><span class="sxs-lookup"><span data-stu-id="fe541-122">Clear-Host (cls, clear)</span></span>
- <span data-ttu-id="fe541-123">Exit-PSSession (exsn, exit)</span><span class="sxs-lookup"><span data-stu-id="fe541-123">Exit-PSSession (exsn, exit)</span></span>
- <span data-ttu-id="fe541-124">Get-Command (gcm)</span><span class="sxs-lookup"><span data-stu-id="fe541-124">Get-Command (gcm)</span></span>
- <span data-ttu-id="fe541-125">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="fe541-125">Get-FormatData</span></span>
- <span data-ttu-id="fe541-126">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fe541-126">Get-Help</span></span>
- <span data-ttu-id="fe541-127">Measure-Object (measure)</span><span class="sxs-lookup"><span data-stu-id="fe541-127">Measure-Object (measure)</span></span>
- <span data-ttu-id="fe541-128">Out-Default</span><span class="sxs-lookup"><span data-stu-id="fe541-128">Out-Default</span></span>
- <span data-ttu-id="fe541-129">Select-Object (select)</span><span class="sxs-lookup"><span data-stu-id="fe541-129">Select-Object (select)</span></span>

<span data-ttu-id="fe541-130">Поставщики PowerShell недоступны, как и внешние программы (исполняемые файлы, скрипты).</span><span class="sxs-lookup"><span data-stu-id="fe541-130">No PowerShell providers are available, nor are any external programs (executables or scripts).</span></span>

<span data-ttu-id="fe541-131">Дополнительные сведения о режимах языка см. в разделе [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).</span><span class="sxs-lookup"><span data-stu-id="fe541-131">For more information about language modes, see [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).</span></span>

### <a name="choose-the-jea-identity"></a><span data-ttu-id="fe541-132">Выбор удостоверения JEA</span><span class="sxs-lookup"><span data-stu-id="fe541-132">Choose the JEA identity</span></span>

<span data-ttu-id="fe541-133">Для выполнения команд подключенных пользователей JEA требуется удостоверение (учетная запись).</span><span class="sxs-lookup"><span data-stu-id="fe541-133">Behind the scenes, JEA needs an identity (account) to use when running a connected user's commands.</span></span>
<span data-ttu-id="fe541-134">Определить используемое JEA удостоверение можно в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe541-134">You define which identity JEA uses in the session configuration file.</span></span>

#### <a name="local-virtual-account"></a><span data-ttu-id="fe541-135">Локальная виртуальная учетная запись</span><span class="sxs-lookup"><span data-stu-id="fe541-135">Local Virtual Account</span></span>

<span data-ttu-id="fe541-136">Если роли, поддерживаемые этой конечной точкой JEA, используются для управления локальным компьютером, а для успешного выполнения команд достаточно учетной записи локального администратора, следует настроить в JEA использование локальной виртуальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="fe541-136">Local virtual accounts are useful when all roles defined for the JEA endpoint are used to manage the local machine and a local administrator account is sufficient to run the commands successfully.</span></span>
<span data-ttu-id="fe541-137">Виртуальные учетные записи — это временные записи, уникальные для определенного пользователя, срок действия которых ограничен длительностью его сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe541-137">Virtual accounts are temporary accounts that are unique to a specific user and only last for the duration of their PowerShell session.</span></span> <span data-ttu-id="fe541-138">На рядовом сервере или рабочей станции виртуальные учетные записи принадлежат к группе **Администраторы** локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe541-138">On a member server or workstation, virtual accounts belong to the local computer's **Administrators** group.</span></span> <span data-ttu-id="fe541-139">На контроллере домена Active Directory виртуальные учетные записи принадлежат к группе **Администраторы домена** домена.</span><span class="sxs-lookup"><span data-stu-id="fe541-139">On an Active Directory Domain Controller, virtual accounts belong to the domain's **Domain Admins** group.</span></span>

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

<span data-ttu-id="fe541-140">Если ролям, определенным в конфигурации сеанса, не требуются полные права администратора, можно указать группы безопасности, к которым будет принадлежать виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="fe541-140">If the roles defined by the session configuration don't require full administrative privilege, you can specify the security groups to which the virtual account will belong.</span></span> <span data-ttu-id="fe541-141">На рядовом сервере или рабочей станции указанные группы безопасности должны быть локальными, а не из домена.</span><span class="sxs-lookup"><span data-stu-id="fe541-141">On a member server or workstation, the specified security groups must be local groups, not groups from a domain.</span></span>

<span data-ttu-id="fe541-142">Если указаны группы безопасности, виртуальная учетная запись не будет принадлежать к группе локальных администраторов или администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="fe541-142">When one or more security groups are specified, the virtual account isn't assigned to the local or domain administrators group.</span></span>

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

> [!NOTE]
> <span data-ttu-id="fe541-143">Виртуальные учетные записи временно получают право на вход качестве службы в политике безопасности на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="fe541-143">Virtual accounts are temporarily granted the Logon as a service right in the local server security policy.</span></span> <span data-ttu-id="fe541-144">Если одной из указанных групп VirtualAccountGroup уже предоставлено это право в политике, отдельная виртуальная учетная запись больше не добавляется и удаляется из политики.</span><span class="sxs-lookup"><span data-stu-id="fe541-144">If one of the VirtualAccountGroups specified has already been granted this right in the policy, the individual virtual account will no longer be added and removed from the policy.</span></span> <span data-ttu-id="fe541-145">Это может быть полезно в таких сценариях, как контроллеры домена, где ведется детальный аудит изменений в политике безопасности контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="fe541-145">This can be useful in scenarios such as domain controllers where revisions to the domain controller security policy are closely audited.</span></span> <span data-ttu-id="fe541-146">Эта возможность доступна только в Windows Server 2016 с накопительным пакетом обновления за ноябрь 2018 года или более поздней версии и Windows Server 2019 с накопительным пакетом обновления за январь 2019 года или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fe541-146">This is only available in Windows Server 2016 with the November 2018 or later rollup and Windows Server 2019 with the January 2019 or later rollup.</span></span>

#### <a name="group-managed-service-account"></a><span data-ttu-id="fe541-147">Групповая управляемая учетная запись службы</span><span class="sxs-lookup"><span data-stu-id="fe541-147">Group-managed service account</span></span>

<span data-ttu-id="fe541-148">Если пользователям JEA нужен доступ к таким сетевым ресурсам, как другие компьютеры или веб-службы, наиболее подходящим удостоверением является групповая управляемая учетная запись службы (gMSA).</span><span class="sxs-lookup"><span data-stu-id="fe541-148">A group-managed service account (GMSA) is the appropriate identity to use when JEA users need to access network resources such as file shares and web services.</span></span> <span data-ttu-id="fe541-149">Эти учетные записи предоставляют удостоверение домена, которое можно использовать для проверки подлинности при доступе к ресурсам на любом компьютере в домене.</span><span class="sxs-lookup"><span data-stu-id="fe541-149">GMSAs give you a domain identity that is used to authenticate with resources on any machine within the domain.</span></span> <span data-ttu-id="fe541-150">Права, предоставляемые GMSA, определяются ресурсами, к которым вы обращаетесь.</span><span class="sxs-lookup"><span data-stu-id="fe541-150">The rights that a GMSA provides are determined by the resources you're accessing.</span></span> <span data-ttu-id="fe541-151">Вы не получите права администратора на компьютерах или в службах автоматически, пока администратор компьютера или службы явно не предоставит их учетной записи GMSA.</span><span class="sxs-lookup"><span data-stu-id="fe541-151">You don't have admin rights on any machines or services unless the machine or service administrator has explicitly granted those rights to the GMSA.</span></span>

```powershell
# Configure JEA sessions to use the GMSA in the local computer's domain
# with the sAMAccountName of 'MyJEAGMSA'
GroupManagedServiceAccount = 'Domain\MyJEAGMSA'
```

<span data-ttu-id="fe541-152">GMSA следует использовать только в том случае, когда это необходимо:</span><span class="sxs-lookup"><span data-stu-id="fe541-152">GMSAs should only be used when necessary:</span></span>

- <span data-ttu-id="fe541-153">Сложно отследить связь действий с пользователями при использовании GMSA.</span><span class="sxs-lookup"><span data-stu-id="fe541-153">It's difficult to trace back actions to a user when using a GMSA.</span></span> <span data-ttu-id="fe541-154">Каждый пользователь использует одно и то же удостоверение запуска от имени.</span><span class="sxs-lookup"><span data-stu-id="fe541-154">Every user shares the same run-as identity.</span></span> <span data-ttu-id="fe541-155">Для сопоставления отдельных пользователей с действиями потребуется обратиться к записям сеансов и журналам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe541-155">You must review PowerShell session transcripts and logs to correlate individual users with their actions.</span></span>

- <span data-ttu-id="fe541-156">GMSA может иметь доступ к различным ресурсам сети, обращаться к которым подключающемуся пользователю не требуется.</span><span class="sxs-lookup"><span data-stu-id="fe541-156">The GMSA may have access to many network resources that the connecting user doesn't need access to.</span></span> <span data-ttu-id="fe541-157">Всегда старайтесь ограничить действующие разрешения в рамках сеанса JEA и следуйте принципу предоставления минимальных прав.</span><span class="sxs-lookup"><span data-stu-id="fe541-157">Always try to limit effective permissions in a JEA session to follow the principle of least privilege.</span></span>

> [!NOTE]
> <span data-ttu-id="fe541-158">Групповые управляемые учетные записи доступны только в PowerShell 5.1 или более поздней версии на компьютерах, присоединенных к домену.</span><span class="sxs-lookup"><span data-stu-id="fe541-158">Group managed service accounts are only available on domain-joined machines using PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="fe541-159">Дополнительные сведения об обеспечении безопасности сеансов JEA см. в статье [Вопросы безопасности](security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="fe541-159">For more information about securing a JEA session, see the [security considerations](security-considerations.md) article.</span></span>

### <a name="session-transcripts"></a><span data-ttu-id="fe541-160">Записи сеансов</span><span class="sxs-lookup"><span data-stu-id="fe541-160">Session transcripts</span></span>

<span data-ttu-id="fe541-161">Рекомендуется настроить на конечной точке JEA автоматическую запись сеансов пользователей.</span><span class="sxs-lookup"><span data-stu-id="fe541-161">It's recommended that you configure a JEA endpoint to automatically record transcripts of users' sessions.</span></span> <span data-ttu-id="fe541-162">Записи сеансов PowerShell содержат сведения о подключающемся пользователе, назначенном ему удостоверении запуска от имени и выполняемых им командах.</span><span class="sxs-lookup"><span data-stu-id="fe541-162">PowerShell session transcripts contain information about the connecting user, the run as identity assigned to them, and the commands run by the user.</span></span> <span data-ttu-id="fe541-163">Их удобно использовать для аудита группы, когда необходимо знать, кто именно внес определенное изменение в систему.</span><span class="sxs-lookup"><span data-stu-id="fe541-163">They can be useful to an auditing team who needs to understand who made a specific change to a system.</span></span>

<span data-ttu-id="fe541-164">Чтобы настроить автоматическую запись в файле конфигурации сеанса, укажите путь к папке, где должны храниться записи.</span><span class="sxs-lookup"><span data-stu-id="fe541-164">To configure automatic transcription in the session configuration file, provide a path to a folder where the transcripts should be stored.</span></span>

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

<span data-ttu-id="fe541-165">Записи помещаются в папку с учетной записью **Local System**, которой требуются права на чтение и запись в каталоге.</span><span class="sxs-lookup"><span data-stu-id="fe541-165">Transcripts are written to the folder by the **Local System** account, which requires read and write access to the directory.</span></span> <span data-ttu-id="fe541-166">У стандартных пользователей не должно быть доступа к этой папке.</span><span class="sxs-lookup"><span data-stu-id="fe541-166">Standard users should have no access to the folder.</span></span> <span data-ttu-id="fe541-167">Ограничьте число администраторов безопасности, которые имеют доступ для аудита записей.</span><span class="sxs-lookup"><span data-stu-id="fe541-167">Limit the number of security administrators that have access to audit the transcripts.</span></span>

### <a name="user-drive"></a><span data-ttu-id="fe541-168">Диск пользователя</span><span class="sxs-lookup"><span data-stu-id="fe541-168">User drive</span></span>

<span data-ttu-id="fe541-169">Если подключающимся пользователям требуется скопировать файлы с конечной точки JEA или на нее для выполнения команды, можно включить диск пользователя в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe541-169">If your connecting users need to copy files to or from the JEA endpoint, you can enable the user drive in the session configuration file.</span></span> <span data-ttu-id="fe541-170">Диск пользователя — это **PSDrive**, сопоставленный с уникальной папкой каждого подключающегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe541-170">The user drive is a **PSDrive** that is mapped to a unique folder for each connecting user.</span></span> <span data-ttu-id="fe541-171">Эта папка служит для копирования файлов из системы и в нее без назначения пользователям прав доступа ко всей файловой системе или предоставления поставщика FileSystem.</span><span class="sxs-lookup"><span data-stu-id="fe541-171">This folder allows users to copy files to or from the system without giving them access to the full file system or exposing the FileSystem provider.</span></span> <span data-ttu-id="fe541-172">Содержимое диска пользователя сохраняется между сеансами на случай, если сетевое подключение будет прервано.</span><span class="sxs-lookup"><span data-stu-id="fe541-172">The user drive contents are persistent across sessions to accommodate situations where network connectivity may be interrupted.</span></span>

```powershell
MountUserDrive = $true
```

<span data-ttu-id="fe541-173">По умолчанию этот диск позволяет хранить до 50 МБ данных на пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe541-173">By default, the user drive allows you to store a maximum of 50MB of data per user.</span></span> <span data-ttu-id="fe541-174">Вы можете ограничить объем данных, доступных пользователю, с помощью поля *UserDriveMaximumSize*.</span><span class="sxs-lookup"><span data-stu-id="fe541-174">You can limit the amount of data a user can consume with the *UserDriveMaximumSize* field.</span></span>

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

<span data-ttu-id="fe541-175">Если хранить данные на диске пользователя не требуется, можно настроить в системе запланированное задание, автоматически очищающее папку каждую ночь.</span><span class="sxs-lookup"><span data-stu-id="fe541-175">If you don't want data in the user drive to be persistent, you can configure a scheduled task on the system to automatically clean up the folder every night.</span></span>

> [!NOTE]
> <span data-ttu-id="fe541-176">Диск пользователя доступен только в PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fe541-176">The user drive is only available in PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="fe541-177">Дополнительные сведения о накопителях PSDrive см. в разделе [Управление дисками PowerShell](/powershell/scripting/samples/managing-windows-powershell-drives).</span><span class="sxs-lookup"><span data-stu-id="fe541-177">For more information about PSDrives, see [Managing PowerShell drives](/powershell/scripting/samples/managing-windows-powershell-drives).</span></span>

### <a name="role-definitions"></a><span data-ttu-id="fe541-178">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="fe541-178">Role definitions</span></span>

<span data-ttu-id="fe541-179">Определения ролей в файле конфигурации сеанса определяют сопоставление **пользователей** с **ролями**.</span><span class="sxs-lookup"><span data-stu-id="fe541-179">Role definitions in a session configuration file define the mapping of **users** to **roles**.</span></span> <span data-ttu-id="fe541-180">Все пользователи или группы, включенные в это поле, получают разрешение на конечную точку JEA после ее регистрации.</span><span class="sxs-lookup"><span data-stu-id="fe541-180">Every user or group included in this field is granted permission to the JEA endpoint when it's registered.</span></span>
<span data-ttu-id="fe541-181">Пользователя или группу можно включить в качестве ключа в хэш-таблицу только один раз, однако им можно назначить несколько ролей.</span><span class="sxs-lookup"><span data-stu-id="fe541-181">Each user or group can be included as a key in the hashtable only once, but can be assigned multiple roles.</span></span> <span data-ttu-id="fe541-182">Имя возможности роли должно соответствовать имени файла возможности роли без расширения `.psrc`.</span><span class="sxs-lookup"><span data-stu-id="fe541-182">The name of the role capability should be the name of the role capability file, without the `.psrc` extension.</span></span>

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

<span data-ttu-id="fe541-183">Если пользователи принадлежат к нескольким группам в определении роли, они получат доступ к ролям в каждой из них.</span><span class="sxs-lookup"><span data-stu-id="fe541-183">If a user belongs to more than one group in the role definition, they get access to the roles of each.</span></span> <span data-ttu-id="fe541-184">Если две роли предоставляют доступ к одним и тем же командлетам, пользователю назначается наиболее нестрогий набор параметров.</span><span class="sxs-lookup"><span data-stu-id="fe541-184">When two roles grant access to the same cmdlets, the most permissive parameter set is granted to the user.</span></span>

<span data-ttu-id="fe541-185">При указании локальных пользователей и группы в поле определения роли перед обратной косой чертой обязательно укажите имя компьютера (не **localhost** и не подстановочный знак).</span><span class="sxs-lookup"><span data-stu-id="fe541-185">When specifying local users or groups in the role definitions field, be sure to use the computer name, not **localhost** or wildcards.</span></span> <span data-ttu-id="fe541-186">Чтобы проверить имя компьютера, проверьте имя переменной `$env:COMPUTERNAME`.</span><span class="sxs-lookup"><span data-stu-id="fe541-186">You can check the computer name by inspecting the `$env:COMPUTERNAME` variable.</span></span>

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a><span data-ttu-id="fe541-187">Порядок поиска возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="fe541-187">Role capability search order</span></span>

<span data-ttu-id="fe541-188">Как показано в приведенном выше примере, ссылка на возможности ролей осуществляется по базовому имени файла возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="fe541-188">As shown in the example above, role capabilities are referenced by the base name of the role capability file.</span></span> <span data-ttu-id="fe541-189">Базовое имя файла — имя файла без расширения.</span><span class="sxs-lookup"><span data-stu-id="fe541-189">The base name of a file is the filename without the extension.</span></span> <span data-ttu-id="fe541-190">Если несколько возможностей ролей доступны в системе с одинаковым именем, PowerShell использует неявный порядок поиска для выбора действующего файла возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="fe541-190">If multiple role capabilities are available on the system with the same name, PowerShell uses its implicit search order to select the effective role capability file.</span></span> <span data-ttu-id="fe541-191">При этом JEA **не** предоставляет доступ всем файлам возможностей ролей с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="fe541-191">JEA does **not** give access to all role capability files with the same name.</span></span>

<span data-ttu-id="fe541-192">JEA использует переменную `$env:PSModulePath` среды, чтобы определить искомые пути для файлов возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="fe541-192">JEA uses the `$env:PSModulePath` environment variable to determine which paths to scan for role capability files.</span></span> <span data-ttu-id="fe541-193">В пределах каждого из этих путей JEA будет искать допустимые модули PowerShell, которые содержат вложенную папку RoleCapabilities.</span><span class="sxs-lookup"><span data-stu-id="fe541-193">Within each of those paths, JEA looks for valid PowerShell modules that contain a "RoleCapabilities" subfolder.</span></span> <span data-ttu-id="fe541-194">Как и при импорте модулей JEA использует возможности роли, доступные в Windows, а не пользовательские возможности роли с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="fe541-194">As with importing modules, JEA prefers role capabilities that are shipped with Windows to custom role capabilities with the same name.</span></span>

<span data-ttu-id="fe541-195">При всех других конфликтах имен приоритет определяется порядком, в котором Windows перечисляет файлы в каталоге</span><span class="sxs-lookup"><span data-stu-id="fe541-195">For all other naming conflicts, precedence is determined by the order in which Windows enumerates the files in the directory.</span></span> <span data-ttu-id="fe541-196">(не обязательно в алфавитном порядке).</span><span class="sxs-lookup"><span data-stu-id="fe541-196">The order isn't guaranteed to be alphabetical.</span></span> <span data-ttu-id="fe541-197">Первый найденный файл возможности роли, соответствующий указанному имени, будет использоваться для подключающегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe541-197">The first role capability file found that matches the specified name is used for the connecting user.</span></span> <span data-ttu-id="fe541-198">Так как поиск возможностей ролей не имеет детерминированного порядка, **настоятельно рекомендуется** использовать уникальные имена файлов возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="fe541-198">Since the role capability search order isn't deterministic, it's **strongly recommended** that role capabilities have unique filenames.</span></span>

### <a name="conditional-access-rules"></a><span data-ttu-id="fe541-199">Правила условного доступа</span><span class="sxs-lookup"><span data-stu-id="fe541-199">Conditional access rules</span></span>

<span data-ttu-id="fe541-200">Все пользователи и группы, включенные в поле **RoleDefinitions**, автоматически получают доступ к конечным точкам JEA.</span><span class="sxs-lookup"><span data-stu-id="fe541-200">All users and groups included in the **RoleDefinitions** field are automatically granted access to JEA endpoints.</span></span> <span data-ttu-id="fe541-201">Правила условного доступа позволяют уточнить такой доступ и потребовать от пользователей принадлежности к дополнительным группам безопасности, не оказывающим влияния на роли, которым они назначены.</span><span class="sxs-lookup"><span data-stu-id="fe541-201">Conditional access rules allow you to refine this access and require users to belong to additional security groups that don't impact the roles to which they're assigned.</span></span> <span data-ttu-id="fe541-202">Это может быть полезно, если требуется интегрировать решение управления привилегированным доступом "JIT", проверку подлинности смарт-карт или другое решение многофакторной проверки подлинности с помощью JEA.</span><span class="sxs-lookup"><span data-stu-id="fe541-202">This is useful when you want to integrate a just-in-time privileged access management solution, smartcard authentication, or other multifactor authentication solution with JEA.</span></span>

<span data-ttu-id="fe541-203">Правила условного доступа определяются в поле RequiredGroups файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe541-203">Conditional access rules are defined in the RequiredGroups field in a session configuration file.</span></span>
<span data-ttu-id="fe541-204">Там можно задать хэш-таблицу (при необходимости вложенной), которая использует ключи "And" и "Or" для создания правил.</span><span class="sxs-lookup"><span data-stu-id="fe541-204">There, you can provide a hashtable (optionally nested) that uses 'And' and 'Or' keys to construct your rules.</span></span> <span data-ttu-id="fe541-205">Ниже представлены примеры использования этого поля.</span><span class="sxs-lookup"><span data-stu-id="fe541-205">Here are some examples of how to use this field:</span></span>

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

> [!NOTE]
> <span data-ttu-id="fe541-206">Правила условного доступа доступны только в PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fe541-206">Conditional access rules are only available in PowerShell 5.1 or newer.</span></span>

### <a name="other-properties"></a><span data-ttu-id="fe541-207">Другие свойства</span><span class="sxs-lookup"><span data-stu-id="fe541-207">Other properties</span></span>

<span data-ttu-id="fe541-208">Файлы конфигурации сеанса позволяют выполнять те же операции, что и файл возможностей ролей, за исключением предоставления подключающимся пользователям доступа к другим командам.</span><span class="sxs-lookup"><span data-stu-id="fe541-208">Session configuration files can also do everything a role capability file can do, just without the ability to give connecting users access to different commands.</span></span> <span data-ttu-id="fe541-209">Если вы хотите разрешить всем пользователям доступ к определенным командлетам, функциям или поставщикам, это можно сделать прямо в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe541-209">If you want to allow all users access to specific cmdlets, functions, or providers, you can do so right in the session configuration file.</span></span>
<span data-ttu-id="fe541-210">Чтобы вывести полный список поддерживаемых свойств в файле конфигурации сеанса, запустите `Get-Help New-PSSessionConfigurationFile -Full`.</span><span class="sxs-lookup"><span data-stu-id="fe541-210">For a full list of supported properties in the session configuration file, run `Get-Help New-PSSessionConfigurationFile -Full`.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="fe541-211">Проверка файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="fe541-211">Testing a session configuration file</span></span>

<span data-ttu-id="fe541-212">Конфигурацию сеанса можно проверить с помощью командлета [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile).</span><span class="sxs-lookup"><span data-stu-id="fe541-212">You can test a session configuration using the [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile) cmdlet.</span></span> <span data-ttu-id="fe541-213">Рекомендуется проверить файл конфигурации сеанса, если вы вручную редактировали `.pssc`-файл.</span><span class="sxs-lookup"><span data-stu-id="fe541-213">It's recommended that you test your session configuration file if you've manually edited the `.pssc` file.</span></span> <span data-ttu-id="fe541-214">Тестирование гарантирует, что используется правильный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="fe541-214">Testing ensures the syntax is correct.</span></span> <span data-ttu-id="fe541-215">Если файл конфигурации сеанса не пройдет проверку, он не регистрируется в системе.</span><span class="sxs-lookup"><span data-stu-id="fe541-215">If a session configuration file fails this test, it can't be registered on the system.</span></span>

## <a name="sample-session-configuration-file"></a><span data-ttu-id="fe541-216">Пример файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="fe541-216">Sample session configuration file</span></span>

<span data-ttu-id="fe541-217">Ниже приведен пример, показывающий, как создать и проверить конфигурацию сеанса для JEA.</span><span class="sxs-lookup"><span data-stu-id="fe541-217">The following example shows how to create and validate a session configuration for JEA.</span></span> <span data-ttu-id="fe541-218">Для удобства использования и чтения определения роли создаются и хранятся в переменной `$roles`.</span><span class="sxs-lookup"><span data-stu-id="fe541-218">The role definitions are created and stored in the `$roles` variable for convenience and readability.</span></span> <span data-ttu-id="fe541-219">Это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fe541-219">It isn't a requirement to do so.</span></span>

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a><span data-ttu-id="fe541-220">Изменение файлов конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="fe541-220">Updating session configuration files</span></span>

<span data-ttu-id="fe541-221">Чтобы изменить свойства конфигурации сеанса JEA, включая сопоставление пользователей с ролями, следует [отменить регистрацию](register-jea.md#unregistering-jea-configurations).</span><span class="sxs-lookup"><span data-stu-id="fe541-221">To change the properties of a JEA session configuration, including the mapping of users to roles, you must [unregister](register-jea.md#unregistering-jea-configurations).</span></span> <span data-ttu-id="fe541-222">Затем [перерегистрируйте](register-jea.md) конфигурацию сеанса JEA, используя измененный файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe541-222">Then, [re-register](register-jea.md) the JEA session configuration using an updated session configuration file.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe541-223">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fe541-223">Next steps</span></span>

- [<span data-ttu-id="fe541-224">Регистрация конфигурации JEA</span><span class="sxs-lookup"><span data-stu-id="fe541-224">Register a JEA configuration</span></span>](register-jea.md)
- [<span data-ttu-id="fe541-225">Создание ролей JEA</span><span class="sxs-lookup"><span data-stu-id="fe541-225">Author JEA roles</span></span>](role-capabilities.md)

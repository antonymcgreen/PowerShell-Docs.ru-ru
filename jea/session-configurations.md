---
ms.date: 06/12/2017
keywords: jea,powershell,безопасность
title: Конфигурации сеансов JEA
ms.openlocfilehash: b98726ea7ed3aabdfd05034c3b70118e327160cd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62059072"
---
# <a name="jea-session-configurations"></a><span data-ttu-id="ae629-103">Конфигурации сеансов JEA</span><span class="sxs-lookup"><span data-stu-id="ae629-103">JEA Session Configurations</span></span>

> <span data-ttu-id="ae629-104">Применяется к: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ae629-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="ae629-105">Конечная точка JEA регистрируется в системе путем создания и регистрации файла конфигурации сеанса PowerShell особым образом.</span><span class="sxs-lookup"><span data-stu-id="ae629-105">A JEA endpoint is registered on a system by creating and registering a PowerShell session configuration file in a specific way.</span></span>
<span data-ttu-id="ae629-106">Конфигурации сеансов определяют, *кто* может использовать конечную точку JEA и к каким ролям он будет иметь доступ.</span><span class="sxs-lookup"><span data-stu-id="ae629-106">Session configurations determine *who* can use the JEA endpoint, and which role(s) they will have access to.</span></span>
<span data-ttu-id="ae629-107">Они также определяют глобальные параметры, которые применяются к пользователям с любой ролью в сеансе JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-107">They also define global settings that apply to users of any role in the JEA session.</span></span>

<span data-ttu-id="ae629-108">Этот раздел описывает, как создать файл конфигурации сеанса PowerShell и зарегистрировать конечную точку JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-108">This topic describes how to create a PowerShell session configuration file and register a JEA endpoint.</span></span>

## <a name="create-a-session-configuration-file"></a><span data-ttu-id="ae629-109">Создание файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="ae629-109">Create a session configuration file</span></span>

<span data-ttu-id="ae629-110">Чтобы зарегистрировать конечную точку JEA, следует указать способ ее настройки.</span><span class="sxs-lookup"><span data-stu-id="ae629-110">In order to register a JEA endpoint, you need to specify how that endpoint should be configured.</span></span>
<span data-ttu-id="ae629-111">При этом следует учитывать множество параметров. Наиболее важные из них — кто должен иметь доступ к конечной точке JEA, какие роли будут назначаться этим пользователям, какое удостоверение будет использоваться внутри JEA, а также какое имя будет иметь конечная точка JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-111">There are many options to consider here, the most important of which being who should have access to the JEA endpoint, which roles will they be assigned, which identity will JEA use under the covers, and what will be the name of the JEA endpoint.</span></span>
<span data-ttu-id="ae629-112">Все они определяются в файле конфигурации сеанса PowerShell, который представляет собой файл данных PowerShell с расширением PSSC.</span><span class="sxs-lookup"><span data-stu-id="ae629-112">These are all defined in a PowerShell session configuration file, which is a PowerShell data file ending with a .pssc extension.</span></span>

<span data-ttu-id="ae629-113">Чтобы создать каркасный файл конфигурации сеанса для конечных точек JEA, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ae629-113">To create a skeleton session configuration file for JEA endpoints, run the following command.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> <span data-ttu-id="ae629-114">По умолчанию каркасный файл включает только основные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ae629-114">Only the most common configuration options are included in the skeleton file by default.</span></span>
> <span data-ttu-id="ae629-115">Чтобы включить в создаваемый PSSC-файл все применимые настройки, используйте параметр `-Full`.</span><span class="sxs-lookup"><span data-stu-id="ae629-115">Use the `-Full` switch to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="ae629-116">Файл конфигурации сеанса можно открыть в любом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="ae629-116">You can open the session configuration file in any text editor.</span></span>
<span data-ttu-id="ae629-117">Поле `-SessionType RestrictedRemoteServer` указывает, что конфигурация сеанса будет использоваться JEA для безопасного управления.</span><span class="sxs-lookup"><span data-stu-id="ae629-117">The `-SessionType RestrictedRemoteServer` field indicates that the session configuration will be used by JEA for secure management.</span></span>
<span data-ttu-id="ae629-118">Настроенные таким образом сеансы работают в [режиме NoLanguage](https://technet.microsoft.com/library/dn433292.aspx) и содержат только восемь следующих команд (и псевдонимов) по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ae629-118">Sessions configured this way will operate in [NoLanguage mode](https://technet.microsoft.com/library/dn433292.aspx) and only have the following 8 default commands (and aliases) available:</span></span>

- <span data-ttu-id="ae629-119">Clear-Host (cls, clear)</span><span class="sxs-lookup"><span data-stu-id="ae629-119">Clear-Host (cls, clear)</span></span>
- <span data-ttu-id="ae629-120">Exit-PSSession (exsn, exit)</span><span class="sxs-lookup"><span data-stu-id="ae629-120">Exit-PSSession (exsn, exit)</span></span>
- <span data-ttu-id="ae629-121">Get-Command (gcm)</span><span class="sxs-lookup"><span data-stu-id="ae629-121">Get-Command (gcm)</span></span>
- <span data-ttu-id="ae629-122">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="ae629-122">Get-FormatData</span></span>
- <span data-ttu-id="ae629-123">Get-Help</span><span class="sxs-lookup"><span data-stu-id="ae629-123">Get-Help</span></span>
- <span data-ttu-id="ae629-124">Measure-Object (measure)</span><span class="sxs-lookup"><span data-stu-id="ae629-124">Measure-Object (measure)</span></span>
- <span data-ttu-id="ae629-125">Out-Default</span><span class="sxs-lookup"><span data-stu-id="ae629-125">Out-Default</span></span>
- <span data-ttu-id="ae629-126">Select-Object (select)</span><span class="sxs-lookup"><span data-stu-id="ae629-126">Select-Object (select)</span></span>

<span data-ttu-id="ae629-127">Поставщики PowerShell недоступны, как и внешние программы (исполняемые файлы, скрипты и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ae629-127">No PowerShell providers are available, nor are any external programs (executables, scripts, etc.).</span></span>

<span data-ttu-id="ae629-128">Существует несколько полей, которые потребуется настроить для сеанса JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-128">There are several other fields you will want to configure for the JEA session.</span></span>
<span data-ttu-id="ae629-129">Они описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ae629-129">They are covered in the following sections.</span></span>

### <a name="choose-the-jea-identity"></a><span data-ttu-id="ae629-130">Выбор удостоверения JEA</span><span class="sxs-lookup"><span data-stu-id="ae629-130">Choose the JEA identity</span></span>

<span data-ttu-id="ae629-131">Для выполнения команд подключенных пользователей JEA требуется удостоверение (учетная запись).</span><span class="sxs-lookup"><span data-stu-id="ae629-131">Behind the scenes, JEA needs an identity (account) to use when running a connected user's commands.</span></span>
<span data-ttu-id="ae629-132">Задать используемое JEA удостоверение можно в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae629-132">You decide which identity JEA will use in the session configuration file.</span></span>

#### <a name="local-virtual-account"></a><span data-ttu-id="ae629-133">Локальная виртуальная учетная запись</span><span class="sxs-lookup"><span data-stu-id="ae629-133">Local Virtual Account</span></span>

<span data-ttu-id="ae629-134">Если роли, поддерживаемые этой конечной точкой JEA, используются для управления локальным компьютером, а для успешного выполнения команд достаточно учетной записи локального администратора, следует настроить JEA для использования локальной виртуальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ae629-134">If the roles supported by this JEA endpoint are all used to manage the local machine, and a local administrator account is sufficient to run the commands successfully, you should configure JEA to use a local virtual account.</span></span>
<span data-ttu-id="ae629-135">Виртуальные учетные записи — это временные записи, уникальные для определенного пользователя, срок действия которых ограничен длительностью его сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae629-135">Virtual accounts are temporary accounts that are unique to a specific user and only last for the duration of their PowerShell session.</span></span>
<span data-ttu-id="ae629-136">На рядовом сервере или рабочей станции виртуальные учетные записи принадлежат к группе **Администраторы** локального компьютера и обладают доступом к большинству системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ae629-136">On a member server or workstation, virtual accounts belong to the local computer's **Administrators** group, and have access to most system resources.</span></span>
<span data-ttu-id="ae629-137">На контроллере домена Active Directory виртуальные учетные записи принадлежат к группе **Администраторы домена** домена.</span><span class="sxs-lookup"><span data-stu-id="ae629-137">On an Active Directory Domain Controller, virtual accounts belong to the domain's **Domain Admins** group.</span></span>

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

<span data-ttu-id="ae629-138">Если ролям, включенным в конфигурацию сеанса, не требуются такие широкие права, можно дополнительно указать группы безопасности, к которым будет принадлежать виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="ae629-138">If the roles supported by the session configuration do not require such broad privileges, you can optionally specify the security groups to which the virtual account will belong.</span></span>
<span data-ttu-id="ae629-139">На рядовом сервере или рабочей станции указанные группы безопасности должны быть локальными, а не из домена.</span><span class="sxs-lookup"><span data-stu-id="ae629-139">On a member server or workstation, the specified security groups must be local groups, not groups from a domain.</span></span>

<span data-ttu-id="ae629-140">Если указана одна или несколько групп безопасности, виртуальная учетная запись больше не будет принадлежать к группе локальных администраторов или администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="ae629-140">When one or more security groups is specified, the virtual account will no longer belong to the local or domain administrators group.</span></span>

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

> [!NOTE]
> <span data-ttu-id="ae629-141">Виртуальные учетные записи временно получают право на вход качестве службы в политике безопасности на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="ae629-141">Virtual accounts are temporarily granted the Logon as a service right in the local server security policy.</span></span>  <span data-ttu-id="ae629-142">Если одной из указанных групп VirtualAccountGroup уже предоставлено это право в политике, отдельная виртуальная учетная запись больше не добавляется и удаляется из политики.</span><span class="sxs-lookup"><span data-stu-id="ae629-142">If one of the VirtualAccountGroups specified has already been granted this right in the policy, the individual virtual account will no longer be added and removed from the policy.</span></span>  <span data-ttu-id="ae629-143">Это может быть полезно в таких сценариях, как контроллеры домена, где ведется детальный аудит изменений в политике безопасности контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="ae629-143">This can be useful in scenarios such as domain controllers where revisions to the domain controller security policy are closely audited.</span></span>  <span data-ttu-id="ae629-144">Эта возможность доступна только в Windows Server 2016 с накопительным пакетом обновления за ноябрь 2018 года или более поздней версии и Windows Server 2019 с накопительным пакетом обновления за январь 2019 года или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ae629-144">This is only available in Windows Server 2016 with the November 2018 or later rollup and Windows Server 2019 with the January 2019 or later rollup.</span></span>

#### <a name="group-managed-service-account"></a><span data-ttu-id="ae629-145">Групповая управляемая учетная запись службы</span><span class="sxs-lookup"><span data-stu-id="ae629-145">Group Managed Service Account</span></span>


<span data-ttu-id="ae629-146">В сценариях, где пользователю JEA требуется доступ к сетевым ресурсам, например другим компьютерам или веб-службам, наиболее подходящим удостоверением является групповая управляемая учетная запись службы (gMSA).</span><span class="sxs-lookup"><span data-stu-id="ae629-146">For scenarios requiring the JEA user to access network resources such as other machines or web services, a group managed service account (gMSA) is a more appropriate identity to use.</span></span>
<span data-ttu-id="ae629-147">Групповые управляемые учетные записи службы предоставляют удостоверение домена, которое можно использовать для проверки подлинности с использованием ресурсов на любом компьютере в домене.</span><span class="sxs-lookup"><span data-stu-id="ae629-147">gMSA accounts give you a domain identity which can be used to authenticate against resources on any machine within the domain.</span></span>
<span data-ttu-id="ae629-148">Права, предоставляемые учетной записью gMSA, зависят от тех ресурсов, к которым вы обращаетесь.</span><span class="sxs-lookup"><span data-stu-id="ae629-148">The rights the gMSA account gives you is determined by the resources you are accessing.</span></span>
<span data-ttu-id="ae629-149">Вы не будете автоматически получать права администратора на компьютерах или в службах, пока администратор компьютера или службы явно не предоставит учетной записи gMSA права администратора.</span><span class="sxs-lookup"><span data-stu-id="ae629-149">You will not automatically have admin rights on any machines or services unless the machine/service administrator has explicitly granted the gMSA account admin privileges.</span></span>

```powershell
# Configure JEA sessions to use the gMSA account in the local computer's domain with the sAMAccountName of 'MyJEAgMSA'
GroupManagedServiceAccount = 'Domain\MyJEAgMSA'
```

<span data-ttu-id="ae629-150">Учетные записи gMSA следует использовать только тогда, когда по нескольким причинам требуется доступ к сетевым ресурсам:</span><span class="sxs-lookup"><span data-stu-id="ae629-150">gMSA accounts should only be used when access to network resources are required for a few reasons:</span></span>

- <span data-ttu-id="ae629-151">При использовании учетной записи gMSA труднее установить связь действий с пользователем, так как каждый пользователь использует одно удостоверение запуска от имени.</span><span class="sxs-lookup"><span data-stu-id="ae629-151">It is harder to trace back actions to a user when using a gMSA account since every user shares the same run-as identity.</span></span> <span data-ttu-id="ae629-152">Для сопоставления пользователей с действиями потребуется обратиться к записям сеанса и журналам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae629-152">You will need to consult PowerShell session transcripts and logs to correlate users with their actions.</span></span>

- <span data-ttu-id="ae629-153">Учетная запись gMSA может иметь доступ к различным ресурсам сети, обращаться к которым подключающемуся пользователю не требуется.</span><span class="sxs-lookup"><span data-stu-id="ae629-153">The gMSA account may have access to many network resources which the connecting user does not need access to.</span></span> <span data-ttu-id="ae629-154">Всегда старайтесь ограничить действующие разрешения в рамках сеанса JEA и следуйте принципу предоставления минимальных прав.</span><span class="sxs-lookup"><span data-stu-id="ae629-154">Always try to limit effective permissions in a JEA session to follow the principle of least privilege.</span></span>

> [!NOTE]
> <span data-ttu-id="ae629-155">Групповые управляемые учетные записи доступны только в Windows PowerShell 5.1 или более поздней версии и на компьютерах, присоединенных к домену.</span><span class="sxs-lookup"><span data-stu-id="ae629-155">Group managed service accounts are only available in Windows PowerShell 5.1 or newer and on domain-joined machines.</span></span>

#### <a name="more-information-about-run-as-users"></a><span data-ttu-id="ae629-156">Дополнительные сведения о запуске от имени</span><span class="sxs-lookup"><span data-stu-id="ae629-156">More information about run as users</span></span>

<span data-ttu-id="ae629-157">Дополнительные сведения об удостоверениях запуска от имени и их роли в обеспечении безопасности сеанса JEA можно найти в статье [Вопросы безопасности](security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="ae629-157">Additional information about run as identities and how they factor into the security of a JEA session can be found in the [security considerations](security-considerations.md) article.</span></span>

### <a name="session-transcripts"></a><span data-ttu-id="ae629-158">Записи сеансов</span><span class="sxs-lookup"><span data-stu-id="ae629-158">Session transcripts</span></span>

<span data-ttu-id="ae629-159">Рекомендуется настроить файл конфигурации сеанса JEA для автоматической записи сеансов пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae629-159">It is recommended that you configure a JEA session configuration file to automatically record transcripts of users' sessions.</span></span>
<span data-ttu-id="ae629-160">Записи сеансов PowerShell содержат сведения о подключающемся пользователе, назначенном ему удостоверении запуска от имени и выполняемых им командах.</span><span class="sxs-lookup"><span data-stu-id="ae629-160">PowerShell session transcripts contain information about the connecting user, the run as identity assigned to them, and the commands run by the user.</span></span>
<span data-ttu-id="ae629-161">Их удобно использовать для аудита группы, когда необходимо знать, кто именно внес определенное изменение в систему.</span><span class="sxs-lookup"><span data-stu-id="ae629-161">They can be useful to an auditing team who needs to understand who performed a specific change to a system.</span></span>

<span data-ttu-id="ae629-162">Чтобы настроить автоматическую запись в файле конфигурации сеанса, укажите путь к папке, где должны храниться записи.</span><span class="sxs-lookup"><span data-stu-id="ae629-162">To configure automatic transcription in the session configuration file, provide a path to a folder where the transcripts should be stored.</span></span>

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

<span data-ttu-id="ae629-163">Указанная папка должна быть настроена так, чтобы запретить пользователям изменять ее или удалять в ней данные.</span><span class="sxs-lookup"><span data-stu-id="ae629-163">The specified folder should be configured to prevent users from modifying or deleting any data in it.</span></span>
<span data-ttu-id="ae629-164">Записи помещаются в папку с учетной записью Local System, которой требуются права на чтение и запись в каталоге.</span><span class="sxs-lookup"><span data-stu-id="ae629-164">Transcripts are written to the folder by the Local System account, which requires read and write access to the directory.</span></span>
<span data-ttu-id="ae629-165">У обычных пользователей не должно быть доступа к этой папке, а ограниченный набор администраторов безопасности должен иметь такой доступ для аудита записей.</span><span class="sxs-lookup"><span data-stu-id="ae629-165">Standard users should have no access to the folder, and a limited set of security administrators should have access to audit the transcripts.</span></span>

### <a name="user-drive"></a><span data-ttu-id="ae629-166">Диск пользователя</span><span class="sxs-lookup"><span data-stu-id="ae629-166">User drive</span></span>

<span data-ttu-id="ae629-167">Если подключающимся пользователям потребуется скопировать файлы с конечной точки JEA или на нее для выполнения команды, можно включить диск пользователя в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae629-167">If your connecting users will need to copy files to/from the JEA endpoint in order to run a command, you can enable the user drive in the session configuration file.</span></span>
<span data-ttu-id="ae629-168">Диск пользователя — это [PSDrive](https://msdn.microsoft.com/powershell/scripting/getting-started/cookbooks/managing-windows-powershell-drives), сопоставленный с уникальной папкой каждого подключающегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae629-168">The user drive is a [PSDrive](https://msdn.microsoft.com/powershell/scripting/getting-started/cookbooks/managing-windows-powershell-drives) that is mapped to a unique folder for each connecting user.</span></span>
<span data-ttu-id="ae629-169">Эта папка служит для копирования файлов из системы и в нее без назначения пользователям прав доступа ко всей файловой системе или предоставления поставщика FileSystem.</span><span class="sxs-lookup"><span data-stu-id="ae629-169">This folder serves as a space for them to copy files to/from the system, without giving them access to the full file system or exposing the FileSystem provider.</span></span>
<span data-ttu-id="ae629-170">Содержимое диска пользователя сохраняется между сеансами на случай, если сетевое подключение будет прервано.</span><span class="sxs-lookup"><span data-stu-id="ae629-170">The user drive contents are persistent across sessions to accommodate situations where network connectivity may be interrupted.</span></span>

```powershell
MountUserDrive = $true
```

<span data-ttu-id="ae629-171">По умолчанию этот диск позволяет хранить до 50 МБ данных на пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae629-171">By default, the user drive allows you to store a maximum of 50MB of data per user.</span></span>
<span data-ttu-id="ae629-172">Вы можете ограничить объем данных, доступных пользователю, с помощью поля *UserDriveMaximumSize*.</span><span class="sxs-lookup"><span data-stu-id="ae629-172">You can limit the amount of data a user can consume with the *UserDriveMaximumSize* field.</span></span>

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

<span data-ttu-id="ae629-173">Если хранить данные на диске пользователя не требуется, можно настроить в системе запланированное задание, автоматически очищающее папку каждую ночь.</span><span class="sxs-lookup"><span data-stu-id="ae629-173">If you do not want data in the user drive to be persistent, you can configure a scheduled task on the system to automatically clean up the folder every night.</span></span>

> [!NOTE]
> <span data-ttu-id="ae629-174">Диск пользователя доступен только в Windows PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ae629-174">The user drive is only available in Windows PowerShell 5.1 or newer.</span></span>

### <a name="role-definitions"></a><span data-ttu-id="ae629-175">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="ae629-175">Role definitions</span></span>

<span data-ttu-id="ae629-176">Определения ролей в файле конфигурации сеанса определяют сопоставление *пользователей* с *ролями*.</span><span class="sxs-lookup"><span data-stu-id="ae629-176">Role definitions in a session configuration file define the mapping of *users* to *roles*.</span></span>
<span data-ttu-id="ae629-177">Все пользователи или группы, включенные в это поле, автоматически получат разрешение на конечную точку JEA после ее регистрации.</span><span class="sxs-lookup"><span data-stu-id="ae629-177">Every user or group included in this field will automatically be granted permission to the JEA endpoint when it is registered.</span></span>
<span data-ttu-id="ae629-178">Пользователя или группу можно включить в качестве ключа в хэш-таблицу только один раз, однако им можно назначить несколько ролей.</span><span class="sxs-lookup"><span data-stu-id="ae629-178">Each user or group can be included as a key in the hashtable only once, but can be assigned multiple roles.</span></span>
<span data-ttu-id="ae629-179">Имя возможности роли должно соответствовать имени файла возможности роли без расширения PSRC.</span><span class="sxs-lookup"><span data-stu-id="ae629-179">The name of the role capability should be the name of the role capability file, without the .psrc extension.</span></span>

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

<span data-ttu-id="ae629-180">Если пользователь принадлежит к нескольким группам в определении роли, они получат доступ к ролям в каждой из них.</span><span class="sxs-lookup"><span data-stu-id="ae629-180">If a user belongs to more than one group in the role definition, they will get access to the roles of each.</span></span>
<span data-ttu-id="ae629-181">Если две роли предоставляют доступ к одним командлетам, пользователю назначается наиболее нестрогий набор параметров.</span><span class="sxs-lookup"><span data-stu-id="ae629-181">If two roles grant access to the same cmdlets, the most permissive parameter set will be granted to the user.</span></span>

<span data-ttu-id="ae629-182">При указании локальных пользователей и группы в поле определения роли перед обратной косой чертой обязательно укажите имя компьютера (не *localhost* или *.*).</span><span class="sxs-lookup"><span data-stu-id="ae629-182">When specifying local users or groups in the role definitions field, be sure to use the computer name (not *localhost* or *.*) before the backslash.</span></span>
<span data-ttu-id="ae629-183">Чтобы проверить имя компьютера, проверьте имя переменной `$env:computername`.</span><span class="sxs-lookup"><span data-stu-id="ae629-183">You can check the computer name by inspecting the `$env:computername` variable.</span></span>

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a><span data-ttu-id="ae629-184">Порядок поиска возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="ae629-184">Role capability search order</span></span>

<span data-ttu-id="ae629-185">Как показано в приведенном выше примере, ссылка на возможности ролей осуществляется по плоскому имени (имя без расширения) файла возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="ae629-185">As shown in the example above, role capabilities are referenced by the flat name (filename without the extension) of the role capability file.</span></span>
<span data-ttu-id="ae629-186">Если несколько возможностей ролей доступны в системе с одинаковым плоским именем, PowerShell использует неявный порядок поиска для выбора действующего файла возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="ae629-186">If multiple role capabilities are available on the system with the same flat name, PowerShell will use its implicit search order to select the effective role capability file.</span></span>
<span data-ttu-id="ae629-187">При этом система **не** предоставляет доступ всем файлам возможностей ролей с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="ae629-187">It will **not** give access to all role capability files with the same name.</span></span>

<span data-ttu-id="ae629-188">JEA использует переменную `$env:PSModulePath` среды, чтобы определить искомые пути для файлов возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="ae629-188">JEA uses the `$env:PSModulePath` environment variable to determine which paths to scan for role capability files.</span></span>
<span data-ttu-id="ae629-189">В пределах каждого из этих путей JEA будет искать допустимые модули PowerShell, которые содержат вложенную папку RoleCapabilities.</span><span class="sxs-lookup"><span data-stu-id="ae629-189">Within each of those paths, JEA will look for valid PowerShell modules that contain a "RoleCapabilities" subfolder.</span></span>
<span data-ttu-id="ae629-190">Как и при импорте модулей JEA использует возможности роли, доступные в Windows, а не пользовательские возможности роли с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="ae629-190">As with importing modules, JEA prefers role capabilities that are shipped with Windows to custom role capabilities with the same name.</span></span>
<span data-ttu-id="ae629-191">При всех других конфликтах имен приоритет определяется порядком, в котором Windows перечисляет файлы в каталоге (не обязательно в алфавитном порядке).</span><span class="sxs-lookup"><span data-stu-id="ae629-191">For all other naming conflicts, precedence is determined by the order in which Windows enumerates the files in the directory (not guaranteed to be alphabetically).</span></span>
<span data-ttu-id="ae629-192">Первый найденный файл возможности роли, соответствующий нужному имени, будет использоваться для подключающегося пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae629-192">The first role capability file found that matches the desired name will be used for the connecting user.</span></span>

<span data-ttu-id="ae629-193">Порядок, в котором выполняется поиск возможностей роли, не является детерминированным. Поэтому если два или несколько наборов возможностей роли имеют одинаковые имена, **настоятельно рекомендуется** присвоить возможностям роли уникальные имена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae629-193">Since the role capability search order is not deterministic when two or more role capabilities share the same name, it is **strongly recommended** that you ensure role capabilities have unique names on your machine.</span></span>

### <a name="conditional-access-rules"></a><span data-ttu-id="ae629-194">Правила условного доступа</span><span class="sxs-lookup"><span data-stu-id="ae629-194">Conditional access rules</span></span>

<span data-ttu-id="ae629-195">Все пользователи и группы, включенные в поле RoleDefinitions, автоматически получают доступ к конечным точкам JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-195">All users and groups included in the RoleDefinitions field are automatically granted access to JEA endpoints.</span></span>
<span data-ttu-id="ae629-196">Правила условного доступа позволяют уточнить такой доступ и потребовать от пользователей принадлежности к дополнительным группам безопасности, не оказывающим влияния на роли, которым они назначены.</span><span class="sxs-lookup"><span data-stu-id="ae629-196">Conditional access rules allow you to refine this access and require users to belong to additional security groups which do not impact the roles which they are assigned.</span></span>
<span data-ttu-id="ae629-197">Это может быть полезно, если требуется интегрировать решение управления привилегированным доступом "JIT", проверку подлинности смарт-карт или другое решение многофакторной проверки подлинности с помощью JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-197">This can be useful if you want to integrate a "just in time" privileged access management solution, smartcard authentication, or other multifactor authentication solution with JEA.</span></span>

<span data-ttu-id="ae629-198">Правила условного доступа определяются в поле RequiredGroups файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae629-198">Conditional access rules are defined in the RequiredGroups field in a session configuration file.</span></span>
<span data-ttu-id="ae629-199">Там можно задать хэш-таблицу (при необходимости вложенной), которая использует ключи "And" и "Or" для создания правил.</span><span class="sxs-lookup"><span data-stu-id="ae629-199">There, you can provide a hashtable (optionally nested) that uses 'And' and 'Or' keys to construct your rules.</span></span>
<span data-ttu-id="ae629-200">Ниже представлены примеры использования этого поля.</span><span class="sxs-lookup"><span data-stu-id="ae629-200">Here are some examples of how to leverage this field:</span></span>

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
> <span data-ttu-id="ae629-201">Правила условного доступа доступны только в Windows PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ae629-201">Conditional access rules are only available in Windows PowerShell 5.1 or newer.</span></span>

### <a name="other-properties"></a><span data-ttu-id="ae629-202">Другие свойства</span><span class="sxs-lookup"><span data-stu-id="ae629-202">Other properties</span></span>

<span data-ttu-id="ae629-203">Файлы конфигурации сеанса позволяют выполнять те же операции, что и файл возможностей ролей, за исключением предоставления подключающимся пользователям доступа к другим командам.</span><span class="sxs-lookup"><span data-stu-id="ae629-203">Session configuration files can also do everything a role capability file can do, just without the ability to give connecting users access to different commands.</span></span>
<span data-ttu-id="ae629-204">Если вы хотите разрешить всем пользователям доступ к определенным командлетам, функциям или поставщикам, это можно сделать прямо в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae629-204">If you want to allow all users access to specific cmdlets, functions, or providers, you can do so right in the session configuration file.</span></span>
<span data-ttu-id="ae629-205">Чтобы вывести полный список поддерживаемых свойств в файле конфигурации сеанса, запустите `Get-Help New-PSSessionConfigurationFile -Full`.</span><span class="sxs-lookup"><span data-stu-id="ae629-205">For a full list of supported properties in the session configuration file, run `Get-Help New-PSSessionConfigurationFile -Full`.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="ae629-206">Проверка файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="ae629-206">Testing a session configuration file</span></span>

<span data-ttu-id="ae629-207">Конфигурацию сеанса можно проверить с помощью командлета [Test-PSSessionConfigurationFile](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/test-pssessionconfigurationfile).</span><span class="sxs-lookup"><span data-stu-id="ae629-207">You can test a session configuration using the [Test-PSSessionConfigurationFile](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/test-pssessionconfigurationfile) cmdlet.</span></span>
<span data-ttu-id="ae629-208">Настоятельно рекомендуется проверить файл конфигурации сеанса после редактирования PSSC-файла вручную с помощью текстового редактора, чтобы убедиться в правильности синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ae629-208">It is strongly recommended that you test your session configuration file if you have edited the pssc file manually using a text editor to ensure the syntax is correct.</span></span>
<span data-ttu-id="ae629-209">Если файл конфигурации сеанса не проходит эту проверку, его не удастся успешно зарегистрировать в системе.</span><span class="sxs-lookup"><span data-stu-id="ae629-209">If a session configuration file does not pass this test, it will not be able to be successfully registered on the system.</span></span>

## <a name="sample-session-configuration-file"></a><span data-ttu-id="ae629-210">Пример файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="ae629-210">Sample session configuration file</span></span>

<span data-ttu-id="ae629-211">Ниже приведен полноценный пример, показывающий, как создать и проверить конфигурацию сеанса для JEA.</span><span class="sxs-lookup"><span data-stu-id="ae629-211">Below is a complete example showing how to create and validate a session configuration for JEA.</span></span>
<span data-ttu-id="ae629-212">Обратите внимание, что для удобства использования и чтения определения роли создаются и хранятся в переменной `$roles`.</span><span class="sxs-lookup"><span data-stu-id="ae629-212">Note that the role definitions are created and stored in the `$roles` variable for convenience and readability.</span></span>
<span data-ttu-id="ae629-213">Это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ae629-213">It is not a requirement to do so.</span></span>

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a><span data-ttu-id="ae629-214">Изменение файлов конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="ae629-214">Updating session configuration files</span></span>

<span data-ttu-id="ae629-215">Если необходимо изменить свойства конфигурации сеанса JEA, включая сопоставление пользователей с ролями, следует [отменить регистрацию](register-jea.md#unregistering-jea-configurations) конфигурации сеанса JEA и [повторно зарегистрировать ее](register-jea.md).</span><span class="sxs-lookup"><span data-stu-id="ae629-215">If you need to change properties of a JEA session configuration, including the mapping of users to roles, you must [unregister](register-jea.md#unregistering-jea-configurations) and [re-register](register-jea.md) the JEA session configuration.</span></span>
<span data-ttu-id="ae629-216">В случае повторной регистрации конфигурации сеанса JEA используйте обновленный файл конфигурации сеанса PowerShell, включающий нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="ae629-216">When you re-register the JEA session configuration, use an updated PowerShell session configuration file that includes your desired changes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae629-217">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ae629-217">Next steps</span></span>

- [<span data-ttu-id="ae629-218">Регистрация конфигурации JEA</span><span class="sxs-lookup"><span data-stu-id="ae629-218">Register a JEA configuration</span></span>](register-jea.md)
- [<span data-ttu-id="ae629-219">Создание ролей JEA</span><span class="sxs-lookup"><span data-stu-id="ae629-219">Author JEA roles</span></span>](role-capabilities.md)

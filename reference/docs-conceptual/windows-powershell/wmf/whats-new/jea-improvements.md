---
ms.date: 06/12/2017
title: Улучшения Just Enough Administration (JEA)
description: JEA — это новая функция в WMF 5.0, позволяющая осуществлять ролевое администрирование через удаленное взаимодействие PowerShell. Она расширяет существующую инфраструктуру ограниченных конечных точек, позволяя пользователям, которые не являются администраторами, выполнять определенные команды, скрипты и исполняемые файлы с правами администратора.
ms.openlocfilehash: f255d0ecbd4bbd9a5ade4b6e19f066cc007481fb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654024"
---
# <a name="improvements-to-just-enough-administration-jea"></a><span data-ttu-id="a1594-104">Улучшения Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="a1594-104">Improvements to Just Enough Administration (JEA)</span></span>

<span data-ttu-id="a1594-105">Just Enough Administration — это новая функция в WMF 5.0, позволяющая осуществлять ролевое администрирование через удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1594-105">Just Enough Administration is a new feature in WMF 5.0 that enables role-based administration through PowerShell remoting.</span></span> <span data-ttu-id="a1594-106">Она расширяет существующую инфраструктуру ограниченных конечных точек, позволяя пользователям, которые не являются администраторами, выполнять определенные команды, скрипты и исполняемые файлы с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="a1594-106">It extends the existing constrained endpoint infrastructure by allowing non-administrators to run specific commands, scripts, and executables as an administrator.</span></span> <span data-ttu-id="a1594-107">Это помогает уменьшить число полных администраторов в среде и повысить безопасность.</span><span class="sxs-lookup"><span data-stu-id="a1594-107">This enables you to reduce the number of full administrators in your environment and improve security.</span></span>

## <a name="constrained-file-copy-tofrom-jea-endpoints"></a><span data-ttu-id="a1594-108">Ограниченное копирование файлов в конечные точки JEA и из них</span><span class="sxs-lookup"><span data-stu-id="a1594-108">Constrained file copy to/from JEA endpoints</span></span>

<span data-ttu-id="a1594-109">Теперь вы можете удаленно копировать файлы в конечную точку JEA и из нее, не беспокоясь о том, что подключающийся пользователь сможет скопировать *любой* файл в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="a1594-109">You can now remotely copy files to/from a JEA endpoint and be assured that the connecting user can't copy just *any* file on your system.</span></span> <span data-ttu-id="a1594-110">Это возможно благодаря настройке подключения диска пользователя в PSSC-файле.</span><span class="sxs-lookup"><span data-stu-id="a1594-110">This is possible by configuring your PSSC file to mount a user drive for connecting users.</span></span> <span data-ttu-id="a1594-111">Диск пользователя — это новый PSDrive, уникальный для каждого подключающегося пользователя; он сохраняется между сеансами.</span><span class="sxs-lookup"><span data-stu-id="a1594-111">The user drive is a new PSDrive that is unique to each connecting user and persists across sessions.</span></span> <span data-ttu-id="a1594-112">Когда для копирования файлов в сеанс JEA или из него используется `Copy-Item`, доступ разрешен только на диск пользователя.</span><span class="sxs-lookup"><span data-stu-id="a1594-112">When `Copy-Item` is used to copy files to or from a JEA session, it is constrained to only allow access to the user drive.</span></span> <span data-ttu-id="a1594-113">Копировать файлы на другой PSDrive будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="a1594-113">Attempts to copy files to any other PSDrive will fail.</span></span>

<span data-ttu-id="a1594-114">Чтобы настроить диск пользователя в файле конфигурации сеанса JEA, используйте следующие новые поля.</span><span class="sxs-lookup"><span data-stu-id="a1594-114">To set up the user drive in your JEA session configuration file, use the following new fields:</span></span>

```powershell
MountUserDrive = $true
UserDriveMaximumSize = 10485760    # 10 MB
```

<span data-ttu-id="a1594-115">Папка для размещения пользовательского диска создается по адресу `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span><span class="sxs-lookup"><span data-stu-id="a1594-115">The folder backing the user drive is created at `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="a1594-116">Для каждого пользователя, подключающегося к конечной точке, создается папка с именем `$env:USERDOMAIN_$env:USERNAME`.</span><span class="sxs-lookup"><span data-stu-id="a1594-116">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="a1594-117">Чтобы использовать диск пользователя и копировать файлы в конечную точку JEA с доступом к диску пользователя и из нее, используйте параметры `-ToSession` и `-FromSession` в `Copy-Item`.</span><span class="sxs-lookup"><span data-stu-id="a1594-117">To utilize the user drive and copy files to/from a JEA endpoint configured to expose the User drive, use the `-ToSession` and `-FromSession` parameters on `Copy-Item`.</span></span>

```powershell
# Connect to the JEA endpoint
$jeasession = New-PSSession -ComputerName 'srv01' -ConfigurationName 'UserDemo'

# Copy a file in the local folder to the remote machine.
# Note: you cannot specify the file name or subfolder on the remote machine.
# You must exactly type "User:"
Copy-Item -Path .\SampleFile.txt -Destination User: -ToSession $jeasession

# Copy the file back from the remote machine to your local machine
Copy-Item -Path User:\SampleFile.txt -Destination . -FromSession $jeasession
```

<span data-ttu-id="a1594-118">Затем вы сможете записать пользовательские функции для обработки данных, хранящихся на диске пользователя, и предоставить их пользователям в файле возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="a1594-118">You can then write custom functions to process the data stored in the user drive and make those available to users in your Role Capability file.</span></span>

## <a name="support-for-group-managed-service-accounts"></a><span data-ttu-id="a1594-119">Поддержка групповых учетных записей управляемой службы</span><span class="sxs-lookup"><span data-stu-id="a1594-119">Support for Group Managed Service Accounts</span></span>

<span data-ttu-id="a1594-120">В некоторых случаях для выполнения задачи пользователем в сеансе JEA может потребоваться доступ к ресурсам за пределами локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a1594-120">In some cases, a task a user needs to perform in a JEA session may need to access resources beyond the local machine.</span></span> <span data-ttu-id="a1594-121">Если в сеансе JEA настроено использование виртуальной учетной записи, любые попытки подключиться к таким ресурсам будут отображаться как полученные из удостоверения локального компьютера, а не из виртуальной учетной записи или от подключенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a1594-121">When a JEA session is configured to use a virtual account, any attempt to reach such resources will appear to come from the local machine's identity, not the virtual account or connected user.</span></span> <span data-ttu-id="a1594-122">В TP5 включена поддержка работы JEA в контексте [групповой управляемой учетной записи службы](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj128431\(v=ws.11\)), что значительно облегчает доступ к сетевым ресурсам с использованием идентификатора домена.</span><span class="sxs-lookup"><span data-stu-id="a1594-122">In TP5, we have enabled support for running JEA under the context of a [Group Managed Service Account](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj128431\(v=ws.11\)), making it much easier to access network resources by using a domain identity.</span></span>

<span data-ttu-id="a1594-123">Чтобы настроить работу сеанса JEA в учетной записи gMSA, используйте следующий новый ключ в PSSC-файле:</span><span class="sxs-lookup"><span data-stu-id="a1594-123">To configure a JEA session to run under a gMSA account, use the following new key in your PSSC file:</span></span>

```powershell
# Provide the name of your gMSA account here (don't include a trailing $)
# The local machine must be privileged to use this gMSA in Active Directory
GroupManagedServiceAccount = 'myGMSAforJEA'

# You cannot configure a JEA endpoint to use both a gMSA and virtual account
# You can leave the RunAsVirtualAccount field commented out or explicitly set it to false
RunAsVirtualAccount = $false
```

> [!NOTE]
> <span data-ttu-id="a1594-124">Групповые управляемые учетные записи службы не допускают изоляцию или ограниченную область виртуальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="a1594-124">Group Managed Service Accounts do not afford the isolation or limited scope of virtual accounts.</span></span>
> <span data-ttu-id="a1594-125">Каждый подключающийся пользователь будет иметь такое удостоверение gMSA, у которого могут быть разрешения во всей организации.</span><span class="sxs-lookup"><span data-stu-id="a1594-125">Every connecting user will share the same gMSA identity, which may have permissions across your entire enterprise.</span></span> <span data-ttu-id="a1594-126">Будьте внимательны при использовании gMSA. По возможности всегда рекомендуется использовать виртуальные учетные записи, действующие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1594-126">Be very careful when selecting to use a gMSA, and always prefer virtual accounts which are limited to the local machine when possible.</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="a1594-127">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="a1594-127">Conditional access policies</span></span>

<span data-ttu-id="a1594-128">JEA отлично подходит для ограничения действий управления при подключении к системе, но что, если вы также хотите ограничить *время* использования JEA?</span><span class="sxs-lookup"><span data-stu-id="a1594-128">JEA is great at limiting what someone can do when they've connected to a system to manage it, but what if you also want to limit *when* someone can use JEA?</span></span> <span data-ttu-id="a1594-129">Мы добавили варианты настройки в файлы конфигурации сеанса (PSSC), чтобы вы могли указать группы безопасности, к которым должен принадлежать пользователь для запуска сеанса JEA.</span><span class="sxs-lookup"><span data-stu-id="a1594-129">We have added configuration options into the session configuration files (.pssc) to let you specify security groups to which a user must belong in order to establish a JEA session.</span></span> <span data-ttu-id="a1594-130">Это может быть особенно полезным, если в вашей среде установлена система Just In Time (JIT) и вам нужно, чтобы пользователи повышали свои права перед доступом к привилегированной конечной точке JEA.</span><span class="sxs-lookup"><span data-stu-id="a1594-130">This is especially helpful if you have a Just In Time (JIT) system in your environment, and want to make your users elevate their privileges before accessing a highly-privileged JEA endpoint.</span></span>

<span data-ttu-id="a1594-131">Новое поле *RequiredGroups* в PSSC-файле позволяет указать, может ли пользователь подключиться к JEA.</span><span class="sxs-lookup"><span data-stu-id="a1594-131">The new *RequiredGroups* field in the PSSC file allows you to specify the logic to determine if a user can connect to JEA.</span></span> <span data-ttu-id="a1594-132">Логика состоит в указании хэш-таблицы (при необходимости вложенной), которая использует ключи And и Or для создания правил.</span><span class="sxs-lookup"><span data-stu-id="a1594-132">It consists of specifying a hashtable (optionally nested) that uses the 'And' and 'Or' keys to construct your rules.</span></span> <span data-ttu-id="a1594-133">Ниже представлены примеры использования этого поля.</span><span class="sxs-lookup"><span data-stu-id="a1594-133">Here are some examples of how to use this field:</span></span>

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

## <a name="fixed-virtual-accounts-are-now-supported-on-windows-server-2008-r2"></a><span data-ttu-id="a1594-134">Исправлено: виртуальные учетные записи теперь поддерживаются в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a1594-134">Fixed: Virtual accounts are now supported on Windows Server 2008 R2</span></span>

<span data-ttu-id="a1594-135">Теперь в WMF 5.1 вы можете использовать виртуальные учетные записи в Windows Server 2008 R2, включив согласованные конфигурации и паритет функций в Windows Server 2008 R2 — 2016.</span><span class="sxs-lookup"><span data-stu-id="a1594-135">In WMF 5.1, you are now able to use virtual accounts on Windows Server 2008 R2, enabling consistent configurations and feature parity across Windows Server 2008 R2 - 2016.</span></span> <span data-ttu-id="a1594-136">Виртуальные учетные записи по-прежнему не поддерживаются при использовании JEA в Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a1594-136">Virtual accounts remain unsupported when using JEA on Windows 7.</span></span>

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 54b65a636fe05ed82d4f022b5bb8cbf8acaf7bab
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602850"
---
# <span data-ttu-id="cd257-102">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="cd257-102">New-PSDrive</span></span>

## <span data-ttu-id="cd257-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cd257-103">SYNOPSIS</span></span>
<span data-ttu-id="cd257-104">Создает временные и постоянные сопоставленные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="cd257-104">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="cd257-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd257-105">SYNTAX</span></span>

### <span data-ttu-id="cd257-106">Все</span><span class="sxs-lookup"><span data-stu-id="cd257-106">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="cd257-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd257-107">DESCRIPTION</span></span>

<span data-ttu-id="cd257-108">`New-PSDrive`Командлет создает временные и постоянные диски, сопоставленные с расположением в хранилище данных или связанные с ним, например сетевой диск, каталог на локальном компьютере или раздел реестра, а также постоянные сопоставленные сетевые диски Windows, связанные с расположением файловой системы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-108">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="cd257-109">Временные диски существуют только в текущем сеансе PowerShell и в сеансах, создаваемых в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cd257-109">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="cd257-110">Они могут иметь любое имя, допустимое в PowerShell, и могут быть сопоставлены с любым локальным или удаленным ресурсом.</span><span class="sxs-lookup"><span data-stu-id="cd257-110">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="cd257-111">Вы можете использовать временные диски PowerShell для доступа к данным в связанном хранилище данных так же, как и с любым подключенным сетевым диском.</span><span class="sxs-lookup"><span data-stu-id="cd257-111">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="cd257-112">Можно изменить расположение на диске, используя и `Set-Location` получить доступ к содержимому диска с помощью `Get-Item` или `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="cd257-112">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="cd257-113">Поскольку временные диски известны только для PowerShell, к ним нельзя получить доступ с помощью проводника, инструментарий управления Windows (WMI) (WMI), модели COM, Microsoft .NET Framework или с помощью таких средств, как **net use**.</span><span class="sxs-lookup"><span data-stu-id="cd257-113">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use**.</span></span>

<span data-ttu-id="cd257-114">В PowerShell 3,0 добавлены следующие функции `New-PSDrive` :</span><span class="sxs-lookup"><span data-stu-id="cd257-114">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="cd257-115">Подключенные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="cd257-115">Mapped network drives.</span></span> <span data-ttu-id="cd257-116">Параметр **Persist** параметра можно использовать `New-PSDrive` для создания сопоставленных сетевых дисков Windows.</span><span class="sxs-lookup"><span data-stu-id="cd257-116">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="cd257-117">В отличие от временных дисков PowerShell, сопоставленные сетевые диски Windows не зависят от сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd257-117">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="cd257-118">Они сохраняются в Windows и могут управляться с помощью стандартных средств Windows, таких как проводник и **net use**.</span><span class="sxs-lookup"><span data-stu-id="cd257-118">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use**.</span></span> <span data-ttu-id="cd257-119">Сопоставленным сетевым дискам должно быть присвоено имя буквы диска, и они должны подключаться к расположению удаленной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="cd257-119">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="cd257-120">Если команда находится локально, без точки-источника, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="cd257-120">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="cd257-121">Если вы используете `New-PSDrive` внутри сценария и хотите, чтобы диск сохранялся бессрочно, необходимо создать точку сценария с точкой.</span><span class="sxs-lookup"><span data-stu-id="cd257-121">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="cd257-122">Для достижения лучших результатов, чтобы принудительно сохранить новый диск в течение неограниченного времени, добавьте в команду параметр **Scope** и присвойте ему значение **Global**.</span><span class="sxs-lookup"><span data-stu-id="cd257-122">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global**.</span></span> <span data-ttu-id="cd257-123">Дополнительные сведения об использовании источников см. в разделе [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="cd257-123">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="cd257-124">Внешние диски.</span><span class="sxs-lookup"><span data-stu-id="cd257-124">External drives.</span></span> <span data-ttu-id="cd257-125">При подключении к компьютеру внешнего диска PowerShell автоматически добавляет **PSDrive** в файловую систему, представляющую новый диск.</span><span class="sxs-lookup"><span data-stu-id="cd257-125">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="cd257-126">Не нужно перезапускать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-126">You don't have to restart PowerShell.</span></span> <span data-ttu-id="cd257-127">Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет **PSDrive** , представляющий удаленный диск.</span><span class="sxs-lookup"><span data-stu-id="cd257-127">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="cd257-128">Учетные данные для UNC-путей.</span><span class="sxs-lookup"><span data-stu-id="cd257-128">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="cd257-129">Если параметр **root** имеет путь UNC, например `\\Server\Share` , для создания **PSDrive** используется учетные данные, указанные в значении параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="cd257-129">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive**.</span></span> <span data-ttu-id="cd257-130">В противном случае **учетные данные** не вступают в силу при создании новых дисков файловой системы.</span><span class="sxs-lookup"><span data-stu-id="cd257-130">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="cd257-131">В некоторых примерах кода используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости.</span><span class="sxs-lookup"><span data-stu-id="cd257-131">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="cd257-132">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="cd257-132">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="cd257-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="cd257-133">EXAMPLES</span></span>

### <span data-ttu-id="cd257-134">Пример 1. Создание временного диска, сопоставленного с общей сетевой папкой</span><span class="sxs-lookup"><span data-stu-id="cd257-134">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="cd257-135">В этом примере создается временный диск PowerShell, сопоставленный с общей сетевой папкой.</span><span class="sxs-lookup"><span data-stu-id="cd257-135">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="cd257-136">`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `Public` и параметр **psprovider** для указания `FileSystem` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-136">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="cd257-137">Параметр **root** указывает UNC-путь к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="cd257-137">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="cd257-138">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="cd257-138">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="cd257-139">Пример 2. Создание временного диска, сопоставленного с локальным каталогом</span><span class="sxs-lookup"><span data-stu-id="cd257-139">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="cd257-140">В этом примере создается временный диск PowerShell, который предоставляет доступ к каталогу на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-140">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

<span data-ttu-id="cd257-141">Сплаттинг создает ключи и значения параметров.</span><span class="sxs-lookup"><span data-stu-id="cd257-141">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="cd257-142">Параметр **Name** указывает имя диска **MyDocs**.</span><span class="sxs-lookup"><span data-stu-id="cd257-142">The **Name** parameter specifies the drive name, **MyDocs**.</span></span> <span data-ttu-id="cd257-143">Параметр **psprovider** указывает `FileSystem` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-143">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="cd257-144">**Root** указывает каталог локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="cd257-144">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="cd257-145">Параметр **Description** описывает назначение диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-145">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="cd257-146">`New-PSDrive` использует параметры сплаттед для создания `MyDocs` диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-146">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="cd257-147">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="cd257-147">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="cd257-148">Пример 3. Создание временного диска для раздела реестра</span><span class="sxs-lookup"><span data-stu-id="cd257-148">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="cd257-149">В этом примере создается временный диск PowerShell, который предоставляет доступ к разделу реестра.</span><span class="sxs-lookup"><span data-stu-id="cd257-149">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="cd257-150">Он создает диск с именем MyCompany, сопоставленный с `HKLM:\Software\MyCompany` разделом реестра.</span><span class="sxs-lookup"><span data-stu-id="cd257-150">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="cd257-151">`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `MyCompany` и параметр **psprovider** для указания `Registry` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-151">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="cd257-152">Параметр **root** указывает расположение реестра.</span><span class="sxs-lookup"><span data-stu-id="cd257-152">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="cd257-153">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="cd257-153">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="cd257-154">Пример 4. Создание постоянного сопоставленного сетевого диска с использованием учетных данных</span><span class="sxs-lookup"><span data-stu-id="cd257-154">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="cd257-155">Этот пример сопоставляет сетевой диск, который прошел проверку подлинности, с учетными данными учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="cd257-155">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="cd257-156">Дополнительные сведения об объекте **PSCredential** , в котором хранятся учетные данные и о том, как хранятся пароли в качестве **SecureString**, см. в описании параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="cd257-156">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString**, see the **Credential** parameter's description.</span></span>

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> <span data-ttu-id="cd257-157">Помните, что при использовании приведенного выше фрагмента в скрипте задайте для параметра **области** значение "Global", чтобы диск сохранялся вне текущей области.</span><span class="sxs-lookup"><span data-stu-id="cd257-157">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="cd257-158">`$cred`Переменная сохраняет объект **PSCredential** , содержащий учетные данные учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="cd257-158">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="cd257-159">`Get-Credential` предлагает ввести пароль, хранящийся в **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="cd257-159">`Get-Credential` prompts you to enter the password that's stored in a **SecureString**.</span></span>

<span data-ttu-id="cd257-160">`New-PSDrive` создает сопоставленный сетевой диск с помощью нескольких параметров.</span><span class="sxs-lookup"><span data-stu-id="cd257-160">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="cd257-161">**Имя** указывает `S` букву диска, которую Windows принимает.</span><span class="sxs-lookup"><span data-stu-id="cd257-161">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="cd257-162">и **root** определяют `\\Server01\Scripts` расположение на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-162">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="cd257-163">**Сохранить** создает сопоставленный сетевой диск Windows, сохраненный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-163">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="cd257-164">**Psprovider** указывает `FileSystem` поставщика.</span><span class="sxs-lookup"><span data-stu-id="cd257-164">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="cd257-165">**Учетные** данные используют `$cred` переменную для получения учетных данных учетной записи службы для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cd257-165">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="cd257-166">Подключенный диск можно просмотреть на локальном компьютере в сеансах PowerShell, проводнике и с помощью таких средств, как **net use**.</span><span class="sxs-lookup"><span data-stu-id="cd257-166">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use**.</span></span> <span data-ttu-id="cd257-167">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="cd257-167">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="cd257-168">Пример 5. Создание постоянных и временных дисков</span><span class="sxs-lookup"><span data-stu-id="cd257-168">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="cd257-169">В этом примере показано различие между постоянным подключенным сетевым диском и временным диском PowerShell, сопоставленным с одной и той же сетевой папкой.</span><span class="sxs-lookup"><span data-stu-id="cd257-169">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="cd257-170">Если закрыть сеанс PowerShell, а затем открыть новый сеанс, временная память `PSDrive:` недоступна, а постоянный `X:` диск будет доступен.</span><span class="sxs-lookup"><span data-stu-id="cd257-170">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="cd257-171">При принятии решения о том, какой метод следует использовать для подключения сетевых дисков, рассмотрите способ использования диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-171">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="cd257-172">Например, должен ли он быть постоянным и должен ли диск отображаться для других компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="cd257-172">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## <span data-ttu-id="cd257-173">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd257-173">PARAMETERS</span></span>

### <span data-ttu-id="cd257-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cd257-174">-Confirm</span></span>

<span data-ttu-id="cd257-175">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cd257-175">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="cd257-176">-Credential</span></span>

<span data-ttu-id="cd257-177">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="cd257-177">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="cd257-178">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="cd257-178">The default is the current user.</span></span>

<span data-ttu-id="cd257-179">Начиная с PowerShell 3,0, если параметр **root** является путем в формате UNC, для создания дисков файловой системы можно использовать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="cd257-179">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="cd257-180">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="cd257-180">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="cd257-181">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="cd257-181">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="cd257-182">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="cd257-182">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="cd257-183">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="cd257-183">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-184">-Description</span><span class="sxs-lookup"><span data-stu-id="cd257-184">-Description</span></span>

<span data-ttu-id="cd257-185">Указывает краткое описание диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-185">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="cd257-186">Введите любую строку.</span><span class="sxs-lookup"><span data-stu-id="cd257-186">Type any string.</span></span>

<span data-ttu-id="cd257-187">Чтобы просмотреть описания всех дисков сеанса, `Get-PSDrive | Format-Table Name, Description` .</span><span class="sxs-lookup"><span data-stu-id="cd257-187">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="cd257-188">Чтобы просмотреть описание конкретного диска, введите `(Get-PSDrive <DriveName>).Description` .</span><span class="sxs-lookup"><span data-stu-id="cd257-188">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-189">-Name</span><span class="sxs-lookup"><span data-stu-id="cd257-189">-Name</span></span>

<span data-ttu-id="cd257-190">Указывает имя нового диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-190">Specifies a name for the new drive.</span></span> <span data-ttu-id="cd257-191">Для постоянных сопоставленных сетевых дисков используйте букву диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-191">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="cd257-192">Для временных дисков PowerShell вы не ограничены буквами дисков, используйте любую допустимую строку.</span><span class="sxs-lookup"><span data-stu-id="cd257-192">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-193">— Сохранить</span><span class="sxs-lookup"><span data-stu-id="cd257-193">-Persist</span></span>

<span data-ttu-id="cd257-194">Указывает, что этот командлет создает сопоставленный сетевой диск Windows.</span><span class="sxs-lookup"><span data-stu-id="cd257-194">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="cd257-195">Параметр **Persist** доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="cd257-195">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="cd257-196">Сопоставленные сетевые диски сохраняются в Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-196">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="cd257-197">Они являются постоянными, а не специфичными для сеанса, и их можно просматривать и контролировать в проводнике и других средствах.</span><span class="sxs-lookup"><span data-stu-id="cd257-197">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="cd257-198">Если команда выполняется локально, без точки с точками, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполнялась команда.</span><span class="sxs-lookup"><span data-stu-id="cd257-198">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="cd257-199">Если вы запустили `New-PSDrive` внутри скрипта и хотите, чтобы новый диск сохранялся бессрочно, необходимо создать точку сценария с точкой.</span><span class="sxs-lookup"><span data-stu-id="cd257-199">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="cd257-200">Для получения наилучших результатов, чтобы принудительно сохранить новый диск, укажите **Global** в качестве значения параметра **Scope** и включите **хранимые** команды.</span><span class="sxs-lookup"><span data-stu-id="cd257-200">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="cd257-201">Имя диска должно быть буквой, например `D` или `E` .</span><span class="sxs-lookup"><span data-stu-id="cd257-201">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="cd257-202">Значение параметра **root** должно быть UNC-путем к другому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="cd257-202">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="cd257-203">Значение параметра **psprovider** должно быть `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="cd257-203">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="cd257-204">Чтобы отключить сопоставленный сетевой диск Windows, используйте `Remove-PSDrive` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd257-204">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="cd257-205">При отключении сопоставленного сетевого диска Windows сопоставление удаляется без возможности восстановления с компьютера, а не только из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd257-205">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="cd257-206">Сопоставленные сетевые диски относятся только к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd257-206">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="cd257-207">Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других</span><span class="sxs-lookup"><span data-stu-id="cd257-207">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-208">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="cd257-208">-PSProvider</span></span>

<span data-ttu-id="cd257-209">Указывает поставщика PowerShell, который поддерживает диски такого типа.</span><span class="sxs-lookup"><span data-stu-id="cd257-209">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="cd257-210">Например, если диск связан с сетевой папкой или каталогом файловой системы, то поставщиком PowerShell является `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="cd257-210">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="cd257-211">Если диск связан с разделом реестра, поставщик имеет значение `Registry` .</span><span class="sxs-lookup"><span data-stu-id="cd257-211">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="cd257-212">Временные диски PowerShell могут быть связаны с любым поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-212">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="cd257-213">Сопоставленные сетевые диски могут быть связаны только с `FileSystem` поставщиком.</span><span class="sxs-lookup"><span data-stu-id="cd257-213">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="cd257-214">Чтобы просмотреть список поставщиков в сеансе PowerShell, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd257-214">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-215">-Root</span><span class="sxs-lookup"><span data-stu-id="cd257-215">-Root</span></span>

<span data-ttu-id="cd257-216">Указывает расположение хранилища данных, с которым сопоставлен диск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd257-216">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="cd257-217">Например, укажите сетевую папку, например, `\\Server01\Public` локальный каталог, например `C:\Program Files` , или раздел реестра, например `HKLM:\Software\Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="cd257-217">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="cd257-218">Временные диски PowerShell могут быть связаны с локальным или удаленным расположением на любом поддерживаемом диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="cd257-218">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="cd257-219">Сопоставленные сетевые диски можно связать только с расположением файловой системы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd257-219">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-220">-Scope</span><span class="sxs-lookup"><span data-stu-id="cd257-220">-Scope</span></span>

<span data-ttu-id="cd257-221">Указывает область для диска.</span><span class="sxs-lookup"><span data-stu-id="cd257-221">Specifies a scope for the drive.</span></span> <span data-ttu-id="cd257-222">Допустимые значения для этого параметра: **Global**, **Local** и **script** или Number, относящихся к текущей области.</span><span class="sxs-lookup"><span data-stu-id="cd257-222">The acceptable values for this parameter are: **Global**, **Local**, and **Script**, or a number relative to the current scope.</span></span> <span data-ttu-id="cd257-223">Области с номером 0 по числу областей.</span><span class="sxs-lookup"><span data-stu-id="cd257-223">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="cd257-224">Текущий номер области равен 0, а его родительский элемент — 1.</span><span class="sxs-lookup"><span data-stu-id="cd257-224">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="cd257-225">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="cd257-225">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-226">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cd257-226">-WhatIf</span></span>

<span data-ttu-id="cd257-227">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cd257-227">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cd257-228">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cd257-228">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd257-229">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cd257-229">CommonParameters</span></span>

<span data-ttu-id="cd257-230">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="cd257-230">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="cd257-231">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cd257-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd257-232">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cd257-232">INPUTS</span></span>

### <span data-ttu-id="cd257-233">None</span><span class="sxs-lookup"><span data-stu-id="cd257-233">None</span></span>

<span data-ttu-id="cd257-234">Вы не можете конвейерировать входные данные для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="cd257-234">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="cd257-235">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cd257-235">OUTPUTS</span></span>

### <span data-ttu-id="cd257-236">System.Management.Automation.PSDРивеинфо</span><span class="sxs-lookup"><span data-stu-id="cd257-236">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="cd257-237">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cd257-237">NOTES</span></span>

<span data-ttu-id="cd257-238">`New-PSDrive` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="cd257-238">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="cd257-239">Чтобы получить список поставщиков, доступных в вашем сеансе, используйте `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="cd257-239">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="cd257-240">Дополнительные сведения о поставщиках см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="cd257-240">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="cd257-241">Сопоставленные сетевые диски относятся только к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd257-241">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="cd257-242">Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других</span><span class="sxs-lookup"><span data-stu-id="cd257-242">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="cd257-243">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cd257-243">RELATED LINKS</span></span>

[<span data-ttu-id="cd257-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cd257-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="cd257-245">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="cd257-245">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="cd257-246">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="cd257-246">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="cd257-247">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="cd257-247">Remove-PSDrive</span></span>](Remove-PSDrive.md)


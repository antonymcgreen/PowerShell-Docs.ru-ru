---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 04346a3bd324b2d7033405546f131d2d56c5a2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227241"
---
# <span data-ttu-id="6e054-103">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="6e054-103">New-PSDrive</span></span>

## <span data-ttu-id="6e054-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6e054-104">SYNOPSIS</span></span>
<span data-ttu-id="6e054-105">Создает временные и постоянные сопоставленные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="6e054-105">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="6e054-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e054-106">SYNTAX</span></span>

### <span data-ttu-id="6e054-107">Все</span><span class="sxs-lookup"><span data-stu-id="6e054-107">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="6e054-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e054-108">DESCRIPTION</span></span>

<span data-ttu-id="6e054-109">`New-PSDrive`Командлет создает временные и постоянные диски, сопоставленные с расположением в хранилище данных или связанные с ним, например сетевой диск, каталог на локальном компьютере или раздел реестра, а также постоянные сопоставленные сетевые диски Windows, связанные с расположением файловой системы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-109">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="6e054-110">Временные диски существуют только в текущем сеансе PowerShell и в сеансах, создаваемых в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6e054-110">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="6e054-111">Они могут иметь любое имя, допустимое в PowerShell, и могут быть сопоставлены с любым локальным или удаленным ресурсом.</span><span class="sxs-lookup"><span data-stu-id="6e054-111">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="6e054-112">Вы можете использовать временные диски PowerShell для доступа к данным в связанном хранилище данных так же, как и с любым подключенным сетевым диском.</span><span class="sxs-lookup"><span data-stu-id="6e054-112">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="6e054-113">Можно изменить расположение на диске, используя и `Set-Location` получить доступ к содержимому диска с помощью `Get-Item` или `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="6e054-113">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="6e054-114">Поскольку временные диски известны только для PowerShell, к ним нельзя получить доступ с помощью проводника, инструментарий управления Windows (WMI) (WMI), модели COM, Microsoft .NET Framework или с помощью таких средств, как **net use**.</span><span class="sxs-lookup"><span data-stu-id="6e054-114">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use**.</span></span>

<span data-ttu-id="6e054-115">В PowerShell 3,0 добавлены следующие функции `New-PSDrive` :</span><span class="sxs-lookup"><span data-stu-id="6e054-115">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="6e054-116">Подключенные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="6e054-116">Mapped network drives.</span></span> <span data-ttu-id="6e054-117">Параметр **Persist** параметра можно использовать `New-PSDrive` для создания сопоставленных сетевых дисков Windows.</span><span class="sxs-lookup"><span data-stu-id="6e054-117">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="6e054-118">В отличие от временных дисков PowerShell, сопоставленные сетевые диски Windows не зависят от сеанса.</span><span class="sxs-lookup"><span data-stu-id="6e054-118">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="6e054-119">Они сохраняются в Windows и могут управляться с помощью стандартных средств Windows, таких как проводник и **net use**.</span><span class="sxs-lookup"><span data-stu-id="6e054-119">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use**.</span></span> <span data-ttu-id="6e054-120">Сопоставленным сетевым дискам должно быть присвоено имя буквы диска, и они должны подключаться к расположению удаленной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="6e054-120">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="6e054-121">Если команда находится локально, без точки-источника, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="6e054-121">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="6e054-122">Если вы используете `New-PSDrive` внутри сценария и хотите, чтобы диск сохранялся бессрочно, необходимо создать точку сценария с точкой.</span><span class="sxs-lookup"><span data-stu-id="6e054-122">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="6e054-123">Для достижения лучших результатов, чтобы принудительно сохранить новый диск в течение неограниченного времени, добавьте в команду параметр **Scope** и присвойте ему значение **Global**.</span><span class="sxs-lookup"><span data-stu-id="6e054-123">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global**.</span></span> <span data-ttu-id="6e054-124">Дополнительные сведения об использовании источников см. в разделе [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="6e054-124">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="6e054-125">Внешние диски.</span><span class="sxs-lookup"><span data-stu-id="6e054-125">External drives.</span></span> <span data-ttu-id="6e054-126">При подключении к компьютеру внешнего диска PowerShell автоматически добавляет **PSDrive** в файловую систему, представляющую новый диск.</span><span class="sxs-lookup"><span data-stu-id="6e054-126">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="6e054-127">Не нужно перезапускать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-127">You don't have to restart PowerShell.</span></span> <span data-ttu-id="6e054-128">Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет **PSDrive** , представляющий удаленный диск.</span><span class="sxs-lookup"><span data-stu-id="6e054-128">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="6e054-129">Учетные данные для UNC-путей.</span><span class="sxs-lookup"><span data-stu-id="6e054-129">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="6e054-130">Если параметр **root** имеет путь UNC, например `\\Server\Share` , для создания **PSDrive** используется учетные данные, указанные в значении параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="6e054-130">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive**.</span></span> <span data-ttu-id="6e054-131">В противном случае **учетные данные** не вступают в силу при создании новых дисков файловой системы.</span><span class="sxs-lookup"><span data-stu-id="6e054-131">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="6e054-132">В некоторых примерах кода используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости.</span><span class="sxs-lookup"><span data-stu-id="6e054-132">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="6e054-133">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="6e054-133">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="6e054-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="6e054-134">EXAMPLES</span></span>

### <span data-ttu-id="6e054-135">Пример 1. Создание временного диска, сопоставленного с общей сетевой папкой</span><span class="sxs-lookup"><span data-stu-id="6e054-135">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="6e054-136">В этом примере создается временный диск PowerShell, сопоставленный с общей сетевой папкой.</span><span class="sxs-lookup"><span data-stu-id="6e054-136">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="6e054-137">`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `Public` и параметр **psprovider** для указания `FileSystem` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-137">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="6e054-138">Параметр **root** указывает UNC-путь к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="6e054-138">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="6e054-139">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="6e054-139">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="6e054-140">Пример 2. Создание временного диска, сопоставленного с локальным каталогом</span><span class="sxs-lookup"><span data-stu-id="6e054-140">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="6e054-141">В этом примере создается временный диск PowerShell, который предоставляет доступ к каталогу на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-141">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

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

<span data-ttu-id="6e054-142">Сплаттинг создает ключи и значения параметров.</span><span class="sxs-lookup"><span data-stu-id="6e054-142">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="6e054-143">Параметр **Name** указывает имя диска **MyDocs**.</span><span class="sxs-lookup"><span data-stu-id="6e054-143">The **Name** parameter specifies the drive name, **MyDocs**.</span></span> <span data-ttu-id="6e054-144">Параметр **psprovider** указывает `FileSystem` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-144">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="6e054-145">**Root** указывает каталог локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="6e054-145">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="6e054-146">Параметр **Description** описывает назначение диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-146">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="6e054-147">`New-PSDrive` использует параметры сплаттед для создания `MyDocs` диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-147">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="6e054-148">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="6e054-148">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="6e054-149">Пример 3. Создание временного диска для раздела реестра</span><span class="sxs-lookup"><span data-stu-id="6e054-149">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="6e054-150">В этом примере создается временный диск PowerShell, который предоставляет доступ к разделу реестра.</span><span class="sxs-lookup"><span data-stu-id="6e054-150">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="6e054-151">Он создает диск с именем MyCompany, сопоставленный с `HKLM:\Software\MyCompany` разделом реестра.</span><span class="sxs-lookup"><span data-stu-id="6e054-151">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="6e054-152">`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `MyCompany` и параметр **psprovider** для указания `Registry` поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-152">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="6e054-153">Параметр **root** указывает расположение реестра.</span><span class="sxs-lookup"><span data-stu-id="6e054-153">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="6e054-154">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="6e054-154">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="6e054-155">Пример 4. Создание постоянного сопоставленного сетевого диска с использованием учетных данных</span><span class="sxs-lookup"><span data-stu-id="6e054-155">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="6e054-156">Этот пример сопоставляет сетевой диск, который прошел проверку подлинности, с учетными данными учетной записи службы домена.</span><span class="sxs-lookup"><span data-stu-id="6e054-156">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="6e054-157">Дополнительные сведения об объекте **PSCredential** , в котором хранятся учетные данные и о том, как хранятся пароли в качестве **SecureString** , см. в описании параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="6e054-157">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString** , see the **Credential** parameter's description.</span></span>

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
> <span data-ttu-id="6e054-158">Помните, что при использовании приведенного выше фрагмента в скрипте задайте для параметра **области** значение "Global", чтобы диск сохранялся вне текущей области.</span><span class="sxs-lookup"><span data-stu-id="6e054-158">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="6e054-159">`$cred`Переменная сохраняет объект **PSCredential** , содержащий учетные данные учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="6e054-159">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="6e054-160">`Get-Credential` предлагает ввести пароль, хранящийся в **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="6e054-160">`Get-Credential` prompts you to enter the password that's stored in a **SecureString**.</span></span>

<span data-ttu-id="6e054-161">`New-PSDrive` создает сопоставленный сетевой диск с помощью нескольких параметров.</span><span class="sxs-lookup"><span data-stu-id="6e054-161">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="6e054-162">**Имя** указывает `S` букву диска, которую Windows принимает.</span><span class="sxs-lookup"><span data-stu-id="6e054-162">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="6e054-163">и **root** определяют `\\Server01\Scripts` расположение на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-163">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="6e054-164">**Сохранить** создает сопоставленный сетевой диск Windows, сохраненный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-164">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="6e054-165">**Psprovider** указывает `FileSystem` поставщика.</span><span class="sxs-lookup"><span data-stu-id="6e054-165">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="6e054-166">**Учетные** данные используют `$cred` переменную для получения учетных данных учетной записи службы для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6e054-166">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="6e054-167">Подключенный диск можно просмотреть на локальном компьютере в сеансах PowerShell, проводнике и с помощью таких средств, как **net use**.</span><span class="sxs-lookup"><span data-stu-id="6e054-167">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use**.</span></span> <span data-ttu-id="6e054-168">Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="6e054-168">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="6e054-169">Пример 5. Создание постоянных и временных дисков</span><span class="sxs-lookup"><span data-stu-id="6e054-169">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="6e054-170">В этом примере показано различие между постоянным подключенным сетевым диском и временным диском PowerShell, сопоставленным с одной и той же сетевой папкой.</span><span class="sxs-lookup"><span data-stu-id="6e054-170">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="6e054-171">Если закрыть сеанс PowerShell, а затем открыть новый сеанс, временная память `PSDrive:` недоступна, а постоянный `X:` диск будет доступен.</span><span class="sxs-lookup"><span data-stu-id="6e054-171">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="6e054-172">При принятии решения о том, какой метод следует использовать для подключения сетевых дисков, рассмотрите способ использования диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-172">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="6e054-173">Например, должен ли он быть постоянным и должен ли диск отображаться для других компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="6e054-173">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

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

## <span data-ttu-id="6e054-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e054-174">PARAMETERS</span></span>

### <span data-ttu-id="6e054-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6e054-175">-Confirm</span></span>

<span data-ttu-id="6e054-176">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6e054-176">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6e054-177">-Credential</span><span class="sxs-lookup"><span data-stu-id="6e054-177">-Credential</span></span>

<span data-ttu-id="6e054-178">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="6e054-178">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="6e054-179">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6e054-179">The default is the current user.</span></span>

<span data-ttu-id="6e054-180">Начиная с PowerShell 3,0, если параметр **root** является путем в формате UNC, для создания дисков файловой системы можно использовать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6e054-180">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="6e054-181">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="6e054-181">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="6e054-182">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="6e054-182">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="6e054-183">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="6e054-183">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="6e054-184">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="6e054-184">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="6e054-185">-Description</span><span class="sxs-lookup"><span data-stu-id="6e054-185">-Description</span></span>

<span data-ttu-id="6e054-186">Указывает краткое описание диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-186">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="6e054-187">Введите любую строку.</span><span class="sxs-lookup"><span data-stu-id="6e054-187">Type any string.</span></span>

<span data-ttu-id="6e054-188">Чтобы просмотреть описания всех дисков сеанса, `Get-PSDrive | Format-Table Name, Description` .</span><span class="sxs-lookup"><span data-stu-id="6e054-188">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="6e054-189">Чтобы просмотреть описание конкретного диска, введите `(Get-PSDrive <DriveName>).Description` .</span><span class="sxs-lookup"><span data-stu-id="6e054-189">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

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

### <span data-ttu-id="6e054-190">-Name</span><span class="sxs-lookup"><span data-stu-id="6e054-190">-Name</span></span>

<span data-ttu-id="6e054-191">Указывает имя нового диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-191">Specifies a name for the new drive.</span></span> <span data-ttu-id="6e054-192">Для постоянных сопоставленных сетевых дисков используйте букву диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-192">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="6e054-193">Для временных дисков PowerShell вы не ограничены буквами дисков, используйте любую допустимую строку.</span><span class="sxs-lookup"><span data-stu-id="6e054-193">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

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

### <span data-ttu-id="6e054-194">— Сохранить</span><span class="sxs-lookup"><span data-stu-id="6e054-194">-Persist</span></span>

<span data-ttu-id="6e054-195">Указывает, что этот командлет создает сопоставленный сетевой диск Windows.</span><span class="sxs-lookup"><span data-stu-id="6e054-195">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="6e054-196">Параметр **Persist** доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="6e054-196">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="6e054-197">Сопоставленные сетевые диски сохраняются в Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-197">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="6e054-198">Они являются постоянными, а не специфичными для сеанса, и их можно просматривать и контролировать в проводнике и других средствах.</span><span class="sxs-lookup"><span data-stu-id="6e054-198">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="6e054-199">Если команда выполняется локально, без точки с точками, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполнялась команда.</span><span class="sxs-lookup"><span data-stu-id="6e054-199">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="6e054-200">Если вы запустили `New-PSDrive` внутри скрипта и хотите, чтобы новый диск сохранялся бессрочно, необходимо создать точку сценария с точкой.</span><span class="sxs-lookup"><span data-stu-id="6e054-200">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="6e054-201">Для получения наилучших результатов, чтобы принудительно сохранить новый диск, укажите **Global** в качестве значения параметра **Scope** и включите **хранимые** команды.</span><span class="sxs-lookup"><span data-stu-id="6e054-201">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="6e054-202">Имя диска должно быть буквой, например `D` или `E` .</span><span class="sxs-lookup"><span data-stu-id="6e054-202">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="6e054-203">Значение параметра **root** должно быть UNC-путем к другому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="6e054-203">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="6e054-204">Значение параметра **psprovider** должно быть `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="6e054-204">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="6e054-205">Чтобы отключить сопоставленный сетевой диск Windows, используйте `Remove-PSDrive` командлет.</span><span class="sxs-lookup"><span data-stu-id="6e054-205">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="6e054-206">При отключении сопоставленного сетевого диска Windows сопоставление удаляется без возможности восстановления с компьютера, а не только из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6e054-206">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="6e054-207">Сопоставленные сетевые диски относятся только к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6e054-207">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="6e054-208">Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других</span><span class="sxs-lookup"><span data-stu-id="6e054-208">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

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

### <span data-ttu-id="6e054-209">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="6e054-209">-PSProvider</span></span>

<span data-ttu-id="6e054-210">Указывает поставщика PowerShell, который поддерживает диски такого типа.</span><span class="sxs-lookup"><span data-stu-id="6e054-210">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="6e054-211">Например, если диск связан с сетевой папкой или каталогом файловой системы, то поставщиком PowerShell является `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="6e054-211">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="6e054-212">Если диск связан с разделом реестра, поставщик имеет значение `Registry` .</span><span class="sxs-lookup"><span data-stu-id="6e054-212">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="6e054-213">Временные диски PowerShell могут быть связаны с любым поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-213">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="6e054-214">Сопоставленные сетевые диски могут быть связаны только с `FileSystem` поставщиком.</span><span class="sxs-lookup"><span data-stu-id="6e054-214">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="6e054-215">Чтобы просмотреть список поставщиков в сеансе PowerShell, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="6e054-215">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

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

### <span data-ttu-id="6e054-216">-Root</span><span class="sxs-lookup"><span data-stu-id="6e054-216">-Root</span></span>

<span data-ttu-id="6e054-217">Указывает расположение хранилища данных, с которым сопоставлен диск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e054-217">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="6e054-218">Например, укажите сетевую папку, например, `\\Server01\Public` локальный каталог, например `C:\Program Files` , или раздел реестра, например `HKLM:\Software\Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="6e054-218">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="6e054-219">Временные диски PowerShell могут быть связаны с локальным или удаленным расположением на любом поддерживаемом диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="6e054-219">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="6e054-220">Сопоставленные сетевые диски можно связать только с расположением файловой системы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6e054-220">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

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

### <span data-ttu-id="6e054-221">-Scope</span><span class="sxs-lookup"><span data-stu-id="6e054-221">-Scope</span></span>

<span data-ttu-id="6e054-222">Указывает область для диска.</span><span class="sxs-lookup"><span data-stu-id="6e054-222">Specifies a scope for the drive.</span></span> <span data-ttu-id="6e054-223">Допустимые значения для этого параметра: **Global** , **Local** и **script** или Number, относящихся к текущей области.</span><span class="sxs-lookup"><span data-stu-id="6e054-223">The acceptable values for this parameter are: **Global** , **Local** , and **Script** , or a number relative to the current scope.</span></span> <span data-ttu-id="6e054-224">Области с номером 0 по числу областей.</span><span class="sxs-lookup"><span data-stu-id="6e054-224">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="6e054-225">Текущий номер области равен 0, а его родительский элемент — 1.</span><span class="sxs-lookup"><span data-stu-id="6e054-225">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="6e054-226">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="6e054-226">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="6e054-227">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6e054-227">-WhatIf</span></span>

<span data-ttu-id="6e054-228">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6e054-228">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6e054-229">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6e054-229">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6e054-230">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6e054-230">CommonParameters</span></span>

<span data-ttu-id="6e054-231">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="6e054-231">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="6e054-232">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e054-232">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e054-233">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6e054-233">INPUTS</span></span>

### <span data-ttu-id="6e054-234">Нет</span><span class="sxs-lookup"><span data-stu-id="6e054-234">None</span></span>

<span data-ttu-id="6e054-235">Вы не можете конвейерировать входные данные для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="6e054-235">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="6e054-236">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6e054-236">OUTPUTS</span></span>

### <span data-ttu-id="6e054-237">System.Management.Automation.PSDРивеинфо</span><span class="sxs-lookup"><span data-stu-id="6e054-237">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="6e054-238">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6e054-238">NOTES</span></span>

<span data-ttu-id="6e054-239">`New-PSDrive` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="6e054-239">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="6e054-240">Чтобы получить список поставщиков, доступных в вашем сеансе, используйте `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="6e054-240">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="6e054-241">Дополнительные сведения о поставщиках см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6e054-241">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="6e054-242">Сопоставленные сетевые диски относятся только к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6e054-242">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="6e054-243">Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других</span><span class="sxs-lookup"><span data-stu-id="6e054-243">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="6e054-244">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6e054-244">RELATED LINKS</span></span>

[<span data-ttu-id="6e054-245">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6e054-245">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="6e054-246">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="6e054-246">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="6e054-247">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="6e054-247">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="6e054-248">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="6e054-248">Remove-PSDrive</span></span>](Remove-PSDrive.md)

---
description: Реестр
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Registry Provider
ms.openlocfilehash: 2d57afc164885b4d207108a360215e63a5431632
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599374"
---
# <a name="registry-provider"></a><span data-ttu-id="2d59f-103">Поставщик реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-103">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="2d59f-104">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="2d59f-104">Provider name</span></span>

<span data-ttu-id="2d59f-105">Реестр</span><span class="sxs-lookup"><span data-stu-id="2d59f-105">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="2d59f-106">Диски</span><span class="sxs-lookup"><span data-stu-id="2d59f-106">Drives</span></span>

<span data-ttu-id="2d59f-107">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="2d59f-107">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="2d59f-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="2d59f-108">Capabilities</span></span>

<span data-ttu-id="2d59f-109">**ShouldProcess**, **усетрансактионс**</span><span class="sxs-lookup"><span data-stu-id="2d59f-109">**ShouldProcess**, **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="2d59f-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="2d59f-110">Short description</span></span>

<span data-ttu-id="2d59f-111">Предоставляет доступ к разделам реестра, записям и значениям в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d59f-111">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="2d59f-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="2d59f-112">Detailed description</span></span>

<span data-ttu-id="2d59f-113">Поставщик **реестра** PowerShell позволяет получать, добавлять, изменять, очищать и удалять разделы реестра, записи и значения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d59f-113">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="2d59f-114">Диски **реестра** — это иерархическое пространство имен, содержащее разделы реестра и подразделы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d59f-114">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="2d59f-115">Записи и значения реестра не являются компонентами этой иерархии.</span><span class="sxs-lookup"><span data-stu-id="2d59f-115">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="2d59f-116">Но они являются свойствами каждого из разделов.</span><span class="sxs-lookup"><span data-stu-id="2d59f-116">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="2d59f-117">Поставщик **реестра** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2d59f-117">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="2d59f-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="2d59f-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="2d59f-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="2d59f-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="2d59f-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="2d59f-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="2d59f-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="2d59f-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="2d59f-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="2d59f-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="2d59f-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="2d59f-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="2d59f-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="2d59f-128">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-128">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="2d59f-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="2d59f-130">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="2d59f-130">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="2d59f-131">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="2d59f-131">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="2d59f-132">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="2d59f-132">Types exposed by this provider</span></span>

<span data-ttu-id="2d59f-133">Разделы реестра представлены как экземпляры класса [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) .</span><span class="sxs-lookup"><span data-stu-id="2d59f-133">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="2d59f-134">Записи реестра представлены как экземпляры класса [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) .</span><span class="sxs-lookup"><span data-stu-id="2d59f-134">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="2d59f-135">Навигация по дискам реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-135">Navigating the Registry drives</span></span>

<span data-ttu-id="2d59f-136">Поставщик **реестра** предоставляет свое хранилище данных в виде двух дисков по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d59f-136">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="2d59f-137">Расположение реестра HKEY_LOCAL_MACHINE сопоставлено с `HKLM:` диском, и HKEY_CURRENT_USER сопоставлено с `HKCU:` диском.</span><span class="sxs-lookup"><span data-stu-id="2d59f-137">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="2d59f-138">Для работы с реестром можно изменить расположение на `HKLM:` диск с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="2d59f-138">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="2d59f-139">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="2d59f-139">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="2d59f-140">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="2d59f-140">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="2d59f-141">Вы также можете работать с поставщиком **реестра** с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d59f-141">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="2d59f-142">Чтобы сослаться на раздел реестра из другого расположения, используйте имя диска ( `HKLM:` , `HKCU:` ) в пути.</span><span class="sxs-lookup"><span data-stu-id="2d59f-142">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="2d59f-143">Используйте обратную косую черту ( \\ ) или косую черту (/), чтобы указать уровень диска **реестра** .</span><span class="sxs-lookup"><span data-stu-id="2d59f-143">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="2d59f-144">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="2d59f-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="2d59f-145">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для командлета [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)и `pwd` являются псевдонимом для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="2d59f-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="2d59f-146">В последнем примере показан другой синтаксис пути, который можно использовать для навигации по поставщику **реестра** .</span><span class="sxs-lookup"><span data-stu-id="2d59f-146">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="2d59f-147">В этом синтаксисе используется имя поставщика, за которым следуют два двоеточия `::` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-147">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="2d59f-148">Этот синтаксис позволяет использовать полное имя КУСТА вместо имени сопоставленного диска `HKLM` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-148">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="2d59f-149">Отображение содержимого разделов реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-149">Displaying the contents of registry keys</span></span>

<span data-ttu-id="2d59f-150">Реестр разделен на разделы, подразделы и записи.</span><span class="sxs-lookup"><span data-stu-id="2d59f-150">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="2d59f-151">Дополнительные сведения о структуре реестра см. [в разделе Структура реестра](/windows/desktop/sysinfo/structure-of-the-registry).</span><span class="sxs-lookup"><span data-stu-id="2d59f-151">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="2d59f-152">В диске **реестра** каждый раздел является контейнером.</span><span class="sxs-lookup"><span data-stu-id="2d59f-152">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="2d59f-153">Ключ может содержать любое количество ключей.</span><span class="sxs-lookup"><span data-stu-id="2d59f-153">A key can contain any number of keys.</span></span> <span data-ttu-id="2d59f-154">Раздел реестра с родительским ключом называется подразделом.</span><span class="sxs-lookup"><span data-stu-id="2d59f-154">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="2d59f-155">С помощью можно `Get-ChildItem` просматривать разделы реестра и `Set-Location` переходить по пути к ключу.</span><span class="sxs-lookup"><span data-stu-id="2d59f-155">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="2d59f-156">Значения реестра — это атрибуты раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-156">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="2d59f-157">На диске **реестра** они называются **свойствами элементов**.</span><span class="sxs-lookup"><span data-stu-id="2d59f-157">In the **Registry** drive, they are called **Item Properties**.</span></span> <span data-ttu-id="2d59f-158">Раздел реестра может иметь как дочерние ключи, так и свойства элементов.</span><span class="sxs-lookup"><span data-stu-id="2d59f-158">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="2d59f-159">В этом примере показана разница между `Get-Item` и `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-159">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="2d59f-160">При использовании `Get-Item` в разделе реестра "Диспетчер очереди" можно просмотреть его свойства.</span><span class="sxs-lookup"><span data-stu-id="2d59f-160">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

<span data-ttu-id="2d59f-161">Каждый раздел реестра может также содержать подразделы.</span><span class="sxs-lookup"><span data-stu-id="2d59f-161">Each registry key can also have subkeys.</span></span> <span data-ttu-id="2d59f-162">При использовании `Get-Item` в разделе реестра подразделы не отображаются.</span><span class="sxs-lookup"><span data-stu-id="2d59f-162">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="2d59f-163">`Get-ChildItem`Командлет покажет вам дочерние элементы ключа "Диспетчер очереди сообщений", включая свойства каждого подраздела.</span><span class="sxs-lookup"><span data-stu-id="2d59f-163">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="2d59f-164">Свойства родительского ключа не отображаются при использовании `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-164">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

<span data-ttu-id="2d59f-165">`Get-Item`Командлет также можно использовать в текущем расположении.</span><span class="sxs-lookup"><span data-stu-id="2d59f-165">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="2d59f-166">В следующем примере выполняется переход к разделу реестра "spool" и получение свойств элемента.</span><span class="sxs-lookup"><span data-stu-id="2d59f-166">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="2d59f-167">Точка `.` используется для указания текущего положения.</span><span class="sxs-lookup"><span data-stu-id="2d59f-167">The dot `.` is used to indicate the current location.</span></span>

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

<span data-ttu-id="2d59f-168">Дополнительные сведения о командлетах, описываемых в этом разделе, см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-168">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="2d59f-169">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="2d59f-169">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="2d59f-170">Просмотр значений разделов реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-170">Viewing registry key values</span></span>

<span data-ttu-id="2d59f-171">Значения разделов реестра хранятся в виде свойств каждого раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-171">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="2d59f-172">`Get-ItemProperty`Командлет просматривает свойства раздела реестра, используя указанное имя.</span><span class="sxs-lookup"><span data-stu-id="2d59f-172">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="2d59f-173">Результатом является **PSCustomObject** , содержащий заданное вами свойство.</span><span class="sxs-lookup"><span data-stu-id="2d59f-173">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="2d59f-174">В следующем примере командлет используется `Get-ItemProperty` для просмотра всех свойств.</span><span class="sxs-lookup"><span data-stu-id="2d59f-174">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="2d59f-175">Сохранение результирующего объекта в переменной позволяет получить доступ к требуемому значению свойства.</span><span class="sxs-lookup"><span data-stu-id="2d59f-175">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="2d59f-176">Указание значения для `-Name` параметра позволяет выбрать указанные свойства и возвращает **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="2d59f-176">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject**.</span></span>  <span data-ttu-id="2d59f-177">В следующем примере показано различие в выходных данных при использовании `-Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-177">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

<span data-ttu-id="2d59f-178">Начиная с PowerShell 5,0 `Get-ItemPropertyValue` командлет возвращает только указанное значение свойства.</span><span class="sxs-lookup"><span data-stu-id="2d59f-178">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="2d59f-179">Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-179">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="2d59f-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-180">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="2d59f-181">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="2d59f-181">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="2d59f-182">Изменение значений разделов реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-182">Changing registry key values</span></span>

<span data-ttu-id="2d59f-183">`Set-ItemProperty`Командлет установит атрибуты для разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-183">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="2d59f-184">В следующем примере используется `Set-ItemProperty` для изменения типа запуска службы диспетчера очереди печати на ручной.</span><span class="sxs-lookup"><span data-stu-id="2d59f-184">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="2d59f-185">В этом примере **старттипе** возвращается к *автоматическому* использованию `Set-Service` командлета.</span><span class="sxs-lookup"><span data-stu-id="2d59f-185">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

<span data-ttu-id="2d59f-186">Каждый раздел реестра имеет значение *по умолчанию* .</span><span class="sxs-lookup"><span data-stu-id="2d59f-186">Each registry key has a *default* value.</span></span> <span data-ttu-id="2d59f-187">Можно изменить значение *по умолчанию* для раздела реестра с помощью `Set-Item` или `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-187">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="2d59f-188">Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-188">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="2d59f-189">Set-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-189">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="2d59f-190">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-190">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="2d59f-191">Создание разделов и значений реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-191">Creating registry keys and values</span></span>

<span data-ttu-id="2d59f-192">`New-Item`Командлет создаст разделы реестра с предоставленным именем.</span><span class="sxs-lookup"><span data-stu-id="2d59f-192">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="2d59f-193">Можно также использовать `mkdir` функцию, которая вызывает `New-Item` командлет внутри.</span><span class="sxs-lookup"><span data-stu-id="2d59f-193">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="2d59f-194">`New-ItemProperty`С помощью командлета можно создавать значения в указанном разделе реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-194">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="2d59f-195">В следующем примере создается новое значение DWORD для раздела реестра Контосокомпани.</span><span class="sxs-lookup"><span data-stu-id="2d59f-195">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="2d59f-196">Другие допустимые значения типов см. в разделе динамические параметры этой статьи.</span><span class="sxs-lookup"><span data-stu-id="2d59f-196">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="2d59f-197">Подробные сведения об использовании командлетов см. в разделе [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="2d59f-197">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="2d59f-198">Копирование разделов и значений реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-198">Copying registry keys and values</span></span>

<span data-ttu-id="2d59f-199">В поставщике **реестра** используйте командлет, чтобы `Copy-Item` скопировать разделы и значения реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-199">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="2d59f-200">Используйте `Copy-ItemProperty` командлет, чтобы скопировать только значения реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-200">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="2d59f-201">Следующая команда копирует раздел реестра Contoso и его свойства в указанное расположение "HKLM: \ Софтваре\фабрикам".</span><span class="sxs-lookup"><span data-stu-id="2d59f-201">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="2d59f-202">`Copy-Item` создает ключ назначения, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="2d59f-202">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="2d59f-203">Если целевой ключ существует, `Copy-Item` создает дубликат исходного ключа в виде дочернего элемента (подраздела) целевого ключа.</span><span class="sxs-lookup"><span data-stu-id="2d59f-203">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="2d59f-204">Следующая команда использует командлет, `Copy-ItemProperty` чтобы скопировать значение "Server" из ключа Contoso в ключ "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="2d59f-204">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="2d59f-205">Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-205">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="2d59f-206">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-206">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="2d59f-207">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-207">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="2d59f-208">Перемещение разделов и значений реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-208">Moving registry keys and values</span></span>

<span data-ttu-id="2d59f-209">`Move-Item` `Move-ItemProperty` Командлеты и ведут себя как аналоги копирования.</span><span class="sxs-lookup"><span data-stu-id="2d59f-209">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="2d59f-210">Если место назначения существует, `Move-Item` перемещает исходный ключ под конечным ключом.</span><span class="sxs-lookup"><span data-stu-id="2d59f-210">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="2d59f-211">Если целевой ключ не существует, исходный ключ перемещается в целевой путь.</span><span class="sxs-lookup"><span data-stu-id="2d59f-211">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="2d59f-212">Следующая команда перемещает ключ Contoso в путь "HKLM: \ Софтваре\фабрикам".</span><span class="sxs-lookup"><span data-stu-id="2d59f-212">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="2d59f-213">Эта команда перемещает все свойства из "HKLM: \ Софтваре\контосокомпани" в "HKLM: \ Софтваре\фабрикам".</span><span class="sxs-lookup"><span data-stu-id="2d59f-213">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="2d59f-214">Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-214">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="2d59f-215">Move-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-215">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="2d59f-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-216">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="2d59f-217">Переименование разделов и значений реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-217">Renaming registry keys and values</span></span>

<span data-ttu-id="2d59f-218">Разделы и значения реестра можно переименовывать точно так же, как и файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="2d59f-218">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="2d59f-219">`Rename-Item` Переименовывает разделы реестра, в то же время `Rename-ItemProperty` переименовывает значения реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-219">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="2d59f-220">Изменение дескрипторов безопасности</span><span class="sxs-lookup"><span data-stu-id="2d59f-220">Changing security descriptors</span></span>

<span data-ttu-id="2d59f-221">Доступ к разделам реестра можно ограничить с помощью `Get-Acl` `Set-Acl` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="2d59f-221">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="2d59f-222">В следующем примере добавляется новый пользователь с полным доступом к разделу реестра "HKLM: \ Софтваре\контосо".</span><span class="sxs-lookup"><span data-stu-id="2d59f-222">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="2d59f-223">Дополнительные примеры и сведения об использовании командлетов см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-223">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="2d59f-224">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="2d59f-224">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="2d59f-225">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="2d59f-225">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="2d59f-226">Удаление и очистка разделов и значений реестра</span><span class="sxs-lookup"><span data-stu-id="2d59f-226">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="2d59f-227">Вы можете удалить содержащиеся элементы с помощью **Remove-Item**, но вам будет предложено подтвердить удаление, если элемент содержит что-нибудь еще.</span><span class="sxs-lookup"><span data-stu-id="2d59f-227">You can remove contained items by using **Remove-Item**, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="2d59f-228">В следующем примере предпринимается попытка удалить раздел HKLM: \ Софтваре\контосо.</span><span class="sxs-lookup"><span data-stu-id="2d59f-228">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="2d59f-229">Чтобы удалить содержащиеся элементы без запроса, укажите `-Recurse` параметр.</span><span class="sxs-lookup"><span data-stu-id="2d59f-229">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="2d59f-230">Если требуется удалить все элементы в "HKLM: \ Софтваре\контосо", но не само "HKLM: \ Софтваре\контосо", используйте обратную косую черту, `\` за которой следует подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="2d59f-230">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="2d59f-231">Эта команда удаляет значение реестра "ContosoTest" из раздела реестра "HKLM: \ Софтваре\контосо".</span><span class="sxs-lookup"><span data-stu-id="2d59f-231">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="2d59f-232">`Clear-Item` Удаляет все значения реестра для ключа.</span><span class="sxs-lookup"><span data-stu-id="2d59f-232">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="2d59f-233">В следующем примере удаляются все значения из раздела реестра "HKLM: \ Софтваре\контосо".</span><span class="sxs-lookup"><span data-stu-id="2d59f-233">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="2d59f-234">Чтобы очистить только конкретное свойство, используйте `Clear-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="2d59f-234">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

<span data-ttu-id="2d59f-235">Дополнительные примеры и сведения об использовании командлетов см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="2d59f-235">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="2d59f-236">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-236">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="2d59f-237">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-237">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="2d59f-238">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-238">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="2d59f-239">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-239">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="2d59f-240">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="2d59f-240">Dynamic parameters</span></span>

<span data-ttu-id="2d59f-241">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="2d59f-241">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="2d59f-242">Введите <Microsoft. Win32. RegistryValueKind></span><span class="sxs-lookup"><span data-stu-id="2d59f-242">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="2d59f-243">Задает или изменяет тип данных значения реестра.</span><span class="sxs-lookup"><span data-stu-id="2d59f-243">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="2d59f-244">Значение по умолчанию — `String` (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="2d59f-244">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="2d59f-245">Этот параметр функционирует соответствующим образом для командлета [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="2d59f-245">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="2d59f-246">Этот параметр также доступен для использования с командлетом [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) на дисках реестра, но он не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="2d59f-246">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="2d59f-247">Значение</span><span class="sxs-lookup"><span data-stu-id="2d59f-247">Value</span></span> | <span data-ttu-id="2d59f-248">Описание</span><span class="sxs-lookup"><span data-stu-id="2d59f-248">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="2d59f-249">Определяет строку, заканчивающуюся символом NULL.</span><span class="sxs-lookup"><span data-stu-id="2d59f-249">Specifies a null-terminated string.</span></span> <span data-ttu-id="2d59f-250">Эквивалентно типу REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="2d59f-250">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="2d59f-251">Задает завершающуюся нулем строку, содержащую нераскрытные</span><span class="sxs-lookup"><span data-stu-id="2d59f-251">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="2d59f-252">ссылки на переменные среды, развернутые при</span><span class="sxs-lookup"><span data-stu-id="2d59f-252">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="2d59f-253">значение извлекается.</span><span class="sxs-lookup"><span data-stu-id="2d59f-253">the value is retrieved.</span></span> <span data-ttu-id="2d59f-254">Эквивалентно типу REG_EXPAND_SZ.</span><span class="sxs-lookup"><span data-stu-id="2d59f-254">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="2d59f-255">Определяет двоичные данные в любой форме.</span><span class="sxs-lookup"><span data-stu-id="2d59f-255">Specifies binary data in any form.</span></span> <span data-ttu-id="2d59f-256">Эквивалентно типу REG_BINARY.</span><span class="sxs-lookup"><span data-stu-id="2d59f-256">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="2d59f-257">Определяет 32-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="2d59f-257">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="2d59f-258">Эквивалентно типу REG_DWORD.</span><span class="sxs-lookup"><span data-stu-id="2d59f-258">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="2d59f-259">Указывает массив строк, заканчивающихся нулем, заканчивающийся на</span><span class="sxs-lookup"><span data-stu-id="2d59f-259">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="2d59f-260">два пустых символа.</span><span class="sxs-lookup"><span data-stu-id="2d59f-260">two null characters.</span></span> <span data-ttu-id="2d59f-261">Эквивалентно типу REG_MULTI_SZ.</span><span class="sxs-lookup"><span data-stu-id="2d59f-261">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="2d59f-262">Задает 64-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="2d59f-262">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="2d59f-263">Эквивалентно типу REG_QWORD.</span><span class="sxs-lookup"><span data-stu-id="2d59f-263">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="2d59f-264">Указывает на неподдерживаемый тип данных реестра, например</span><span class="sxs-lookup"><span data-stu-id="2d59f-264">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="2d59f-265">REG_RESOURCE_LIST.</span><span class="sxs-lookup"><span data-stu-id="2d59f-265">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="2d59f-266">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="2d59f-266">Cmdlets supported</span></span>

- [<span data-ttu-id="2d59f-267">Set-Item</span><span class="sxs-lookup"><span data-stu-id="2d59f-267">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="2d59f-268">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d59f-268">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="2d59f-269">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="2d59f-269">Using the pipeline</span></span>

<span data-ttu-id="2d59f-270">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="2d59f-270">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="2d59f-271">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="2d59f-271">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="2d59f-272">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2d59f-272">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="2d59f-273">Получение справки</span><span class="sxs-lookup"><span data-stu-id="2d59f-273">Getting help</span></span>

<span data-ttu-id="2d59f-274">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2d59f-274">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="2d59f-275">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните `Get-Help` команду на диске файловой системы или используйте параметр **path** , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2d59f-275">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="2d59f-276">См. также</span><span class="sxs-lookup"><span data-stu-id="2d59f-276">See also</span></span>

 [<span data-ttu-id="2d59f-277">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2d59f-277">about_Providers</span></span>](../About/about_Providers.md)


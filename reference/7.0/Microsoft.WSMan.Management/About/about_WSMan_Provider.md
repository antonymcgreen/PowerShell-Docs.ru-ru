---
description: WSMan
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WSMan Provider
ms.openlocfilehash: 52a36a9246c3d98650eaeed352aa46fb67ed9bc0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231142"
---
# <a name="wsman-provider"></a><span data-ttu-id="c44bb-104">WSMan Provider</span><span class="sxs-lookup"><span data-stu-id="c44bb-104">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="c44bb-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="c44bb-105">Provider name</span></span>

<span data-ttu-id="c44bb-106">WSMan</span><span class="sxs-lookup"><span data-stu-id="c44bb-106">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="c44bb-107">Диски</span><span class="sxs-lookup"><span data-stu-id="c44bb-107">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="c44bb-108">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="c44bb-108">Short description</span></span>

<span data-ttu-id="c44bb-109">Обеспечивает доступ к конфигурационной информации веб-служб WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-109">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="c44bb-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c44bb-110">Detailed description</span></span>

<span data-ttu-id="c44bb-111">Поставщик **WSMan** для PowerShell позволяет добавлять, изменять, очищать и удалять WS-Management данные конфигурации на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="c44bb-111">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="c44bb-112">Поставщик **WSMan** предоставляет диск PowerShell со структурой каталогов, соответствующей логической группировке параметров конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-112">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="c44bb-113">Эти группы называются контейнерами.</span><span class="sxs-lookup"><span data-stu-id="c44bb-113">These groupings are known as containers.</span></span>

<span data-ttu-id="c44bb-114">Начиная с Windows PowerShell 3,0, поставщик **WSMan** был обновлен для поддержки новых свойств конфигураций сеансов, таких как **аутпутбуфферингмоде**.</span><span class="sxs-lookup"><span data-stu-id="c44bb-114">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="c44bb-115">Конфигурации сеансов отображаются как элементы в каталоге подключаемого модуля `WSMan:` диска, и свойства отображаются в виде элементов в каждой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c44bb-115">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="c44bb-116">Поставщик **WSMan** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c44bb-116">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="c44bb-117">Get-Location</span><span class="sxs-lookup"><span data-stu-id="c44bb-117">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="c44bb-118">Set-Location</span><span class="sxs-lookup"><span data-stu-id="c44bb-118">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="c44bb-119">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-119">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="c44bb-120">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="c44bb-120">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="c44bb-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="c44bb-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="c44bb-123">`WSMan:`Для изменения значений новых свойств можно использовать команды на диске.</span><span class="sxs-lookup"><span data-stu-id="c44bb-123">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="c44bb-124">Однако вы не можете использовать `WSMan:` диск в PowerShell 2,0, чтобы изменить свойства, появившиеся в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c44bb-124">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="c44bb-125">Несмотря на то, что ошибки не возникают, команды не могут изменить эти параметры, используйте диск **WSMan** в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c44bb-125">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="c44bb-126">Организация диска WSMan:</span><span class="sxs-lookup"><span data-stu-id="c44bb-126">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="c44bb-127">**Клиент**. можно настроить различные аспекты клиента WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-127">**Client** : You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="c44bb-128">Сведения о конфигурации сохраняются в реестре.</span><span class="sxs-lookup"><span data-stu-id="c44bb-128">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="c44bb-129">**Служба**. можно настроить различные аспекты службы WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-129">**Service** : You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="c44bb-130">Сведения о конфигурации сохраняются в реестре.</span><span class="sxs-lookup"><span data-stu-id="c44bb-130">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-131">Конфигурация службы иногда называется конфигурацией сервера.</span><span class="sxs-lookup"><span data-stu-id="c44bb-131">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="c44bb-132">**Shell** : можно настроить различные аспекты оболочки WS-Management, такие как параметр, разрешающий доступ к удаленной оболочке ( **алловремотешеллакцесс** ), и максимальное разрешенное число пользователей ( **максконкуррентусерс** ).</span><span class="sxs-lookup"><span data-stu-id="c44bb-132">**Shell** : You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access ( **AllowRemoteShellAccess** ) and the maximum number of concurrent users allowed ( **MaxConcurrentUsers** ).</span></span>

- <span data-ttu-id="c44bb-133">**Прослушиватель**. Вы можете создать и настроить прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="c44bb-133">**Listener** : You can create and configure a listener.</span></span> <span data-ttu-id="c44bb-134">Прослушиватель — это служба управления, реализующая протокол WS-Management для отправки и получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="c44bb-134">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="c44bb-135">**Подключаемый модуль**. подключаемые модули загружаются и используются службой WS-Management для предоставления различных функций.</span><span class="sxs-lookup"><span data-stu-id="c44bb-135">**Plugin** : Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="c44bb-136">По умолчанию PowerShell предоставляет три подключаемых модуля:</span><span class="sxs-lookup"><span data-stu-id="c44bb-136">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="c44bb-137">Подключаемый модуль пересылки событий.</span><span class="sxs-lookup"><span data-stu-id="c44bb-137">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="c44bb-138">Подключаемый модуль Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-138">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="c44bb-139">Подключаемый модуль поставщика инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="c44bb-139">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="c44bb-140">Эти три подключаемые модули поддерживают пересылку событий, конфигурацию и доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-140">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="c44bb-141">**Clientcertificate**. Вы можете создать и настроить сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="c44bb-141">**ClientCertificate** : You can create and configure a client certificate.</span></span>
  <span data-ttu-id="c44bb-142">Сертификат клиента применяется в том случае, если клиент WS-Management настроен для использования проверки подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="c44bb-142">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="c44bb-143">Иерархия каталогов поставщика WSMan</span><span class="sxs-lookup"><span data-stu-id="c44bb-143">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="c44bb-144">Иерархия каталогов поставщика WSMan для локального компьютера выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c44bb-144">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

<span data-ttu-id="c44bb-145">Иерархия каталогов поставщика WS-Management для удаленного компьютера аналогична иерархии каталогов для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c44bb-145">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="c44bb-146">Однако для доступа к параметрам конфигурации удаленного компьютера необходимо установить подключение к удаленному компьютеру с помощью командлета [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="c44bb-146">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="c44bb-147">После установления подключения к удаленному компьютеру имя удаленного компьютера появляется в поставщике.</span><span class="sxs-lookup"><span data-stu-id="c44bb-147">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="c44bb-148">Навигация по диску WSMan:</span><span class="sxs-lookup"><span data-stu-id="c44bb-148">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="c44bb-149">Эта команда использует `Set-Location` командлет для изменения текущего расположения на `WSMan:` диск.</span><span class="sxs-lookup"><span data-stu-id="c44bb-149">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="c44bb-150">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="c44bb-150">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="c44bb-151">Например, введите.</span><span class="sxs-lookup"><span data-stu-id="c44bb-151">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="c44bb-152">Переход к расположению удаленного системного хранилища</span><span class="sxs-lookup"><span data-stu-id="c44bb-152">Navigating to a remote system store location</span></span>

<span data-ttu-id="c44bb-153">Эта команда использует `Set-Location` команду, чтобы изменить текущее расположение на корневое расположение в расположении удаленного хранилища системы.</span><span class="sxs-lookup"><span data-stu-id="c44bb-153">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="c44bb-154">Используйте обратную косую черту или косую `\` черту, `/` чтобы указать уровень `WSMan:` диска.</span><span class="sxs-lookup"><span data-stu-id="c44bb-154">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="c44bb-155">Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c44bb-155">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="c44bb-156">Отображение содержимого диска WSMan:</span><span class="sxs-lookup"><span data-stu-id="c44bb-156">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="c44bb-157">Эта команда использует `Get-Childitem` командлет для вывода хранилищ WS-Management в расположении хранилища localhost.</span><span class="sxs-lookup"><span data-stu-id="c44bb-157">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="c44bb-158">Если вы используете `WSMan:` диск, можно опустить имя диска.</span><span class="sxs-lookup"><span data-stu-id="c44bb-158">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="c44bb-159">Эта команда использует `Get-Childitem` командлет для показа WS-Management хранилищ в расположении хранилища на удаленном компьютере "Server01".</span><span class="sxs-lookup"><span data-stu-id="c44bb-159">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="c44bb-160">Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c44bb-160">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="c44bb-161">Установка значения элементов на диске WSMAN:</span><span class="sxs-lookup"><span data-stu-id="c44bb-161">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="c44bb-162">`Set-Item`С помощью командлета можно изменить параметры конфигурации на `WSMAN` диске.</span><span class="sxs-lookup"><span data-stu-id="c44bb-162">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="c44bb-163">В следующем примере задается значение **TrustedHosts** , которое принимает все узлы с суффиксом "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="c44bb-163">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="c44bb-164">`Set-Item`Командлет поддерживает дополнительный параметр `-Concatenate` , который добавляет значение вместо изменения.</span><span class="sxs-lookup"><span data-stu-id="c44bb-164">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="c44bb-165">В следующем примере новое значение "\*. domain2.com" добавляется к старому значению, хранящемуся в `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="c44bb-165">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="c44bb-166">Создание элементов на диске WSMAN:</span><span class="sxs-lookup"><span data-stu-id="c44bb-166">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="c44bb-167">Создание нового прослушивателя</span><span class="sxs-lookup"><span data-stu-id="c44bb-167">Creating a new listener</span></span>

<span data-ttu-id="c44bb-168">`New-Item`Командлет создает элементы на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="c44bb-168">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="c44bb-169">Каждый поставщик имеет различные типы элементов, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="c44bb-169">Each provider has different item types that you can create.</span></span> <span data-ttu-id="c44bb-170">На `WSMAN:` диске можно создавать *прослушиватели* , настроенные для получения и реагирования на удаленные запросы.</span><span class="sxs-lookup"><span data-stu-id="c44bb-170">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="c44bb-171">Следующая команда создает новый прослушиватель HTTP с помощью `New-Item` командлета.</span><span class="sxs-lookup"><span data-stu-id="c44bb-171">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="c44bb-172">Создание нового подключаемого модуля</span><span class="sxs-lookup"><span data-stu-id="c44bb-172">Creating a new plug-in</span></span>

<span data-ttu-id="c44bb-173">Эта команда создает (регистрирует) подключаемый модуль для службы WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-173">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="c44bb-174">Создание новой записи ресурса</span><span class="sxs-lookup"><span data-stu-id="c44bb-174">Creating a new resource entry</span></span>

<span data-ttu-id="c44bb-175">Эта команда создает запись ресурса в каталоге Resources объекта Тестплугин.</span><span class="sxs-lookup"><span data-stu-id="c44bb-175">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="c44bb-176">Эта команда предполагает, что Тестплугин был создан с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="c44bb-176">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="c44bb-177">Создание новой записи безопасности для ресурса</span><span class="sxs-lookup"><span data-stu-id="c44bb-177">Creating a new security entry for a resource</span></span>

<span data-ttu-id="c44bb-178">Эта команда создает запись безопасности в каталоге Security ресурса Resource_5967683 (конкретного ресурса).</span><span class="sxs-lookup"><span data-stu-id="c44bb-178">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="c44bb-179">Эта команда предполагает, что запись ресурса была создана с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="c44bb-179">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="c44bb-180">Создание нового сертификата клиента</span><span class="sxs-lookup"><span data-stu-id="c44bb-180">Creating a new Client Certificate</span></span>

<span data-ttu-id="c44bb-181">Эта команда создает запись **clientcertificate** , которая может использоваться клиентом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-181">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="c44bb-182">Новый **clientcertificate** будет отображаться в каталоге **ClientCertificate** как "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="c44bb-182">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="c44bb-183">Все параметры являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="c44bb-183">All of the parameters are mandatory.</span></span> <span data-ttu-id="c44bb-184">**Издатель** должен быть отпечаткой сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="c44bb-184">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="c44bb-185">Создание нового параметра инициализации</span><span class="sxs-lookup"><span data-stu-id="c44bb-185">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="c44bb-186">Эта команда создает параметр инициализации с именем "тестпараметернаме" в каталоге "Инитиализатионпараметерс".</span><span class="sxs-lookup"><span data-stu-id="c44bb-186">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="c44bb-187">Эта команда предполагает, что "Тестплугин" был создан с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="c44bb-187">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="c44bb-188">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="c44bb-188">Dynamic parameters</span></span>

<span data-ttu-id="c44bb-189">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="c44bb-189">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="c44bb-190">Address \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-190">Address \<String\></span></span>

<span data-ttu-id="c44bb-191">Задает адрес, для которого был создан данный прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="c44bb-191">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="c44bb-192">Он может иметь одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c44bb-192">The value can be one of the following:</span></span>

- <span data-ttu-id="c44bb-193">Строка литерала "\*".</span><span class="sxs-lookup"><span data-stu-id="c44bb-193">The literal string "\*".</span></span> <span data-ttu-id="c44bb-194">(Подстановочный знак ( `*` ) делает команду привязать все IP-адреса ко всем сетевым адаптерам.)</span><span class="sxs-lookup"><span data-stu-id="c44bb-194">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="c44bb-195">Строка литерала "IP:", за которой следует допустимый IP-адрес в точечно-десятичном формате IPv4 или в шестнадцатеричном формате IPv6.</span><span class="sxs-lookup"><span data-stu-id="c44bb-195">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="c44bb-196">Строка литерала "MAC:", за которой следует MAC-адрес адаптера.</span><span class="sxs-lookup"><span data-stu-id="c44bb-196">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="c44bb-197">Например: MAC: 32-a3-58 -90-to-CC.</span><span class="sxs-lookup"><span data-stu-id="c44bb-197">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="c44bb-198">Значение параметра Address задается при создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="c44bb-198">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-199">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-199">Cmdlets supported</span></span>

- [<span data-ttu-id="c44bb-200">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-200">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="c44bb-201">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="c44bb-201">Capability \<Enumeration\></span></span>

<span data-ttu-id="c44bb-202">При работе с *подключаемыми модулями* этот параметр указывает операцию, которая поддерживается для этого универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c44bb-202">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="c44bb-203">Необходимо создать по одной записи для каждого типа операций, поддерживаемого URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-203">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="c44bb-204">Можно указать любые допустимые атрибуты для данной операции, если она поддерживается операцией.</span><span class="sxs-lookup"><span data-stu-id="c44bb-204">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="c44bb-205">Эти атрибуты включают **SupportsFiltering имеет** и **суппортсфрагмент**.</span><span class="sxs-lookup"><span data-stu-id="c44bb-205">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="c44bb-206">**CREATE** : операции создания поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-206">**Create** : Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-207">Атрибут **суппортфрагмент**  используется, если операция создания поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="c44bb-207">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="c44bb-208">Атрибут **суппортфилтеринг** недопустим для операций создания и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-208">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-209">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-209">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-210">**Delete** : операции Delete поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-210">**Delete** : Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-211">Атрибут **суппортфрагмент** используется, если операция удаления поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="c44bb-211">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="c44bb-212">Атрибут **суппортфилтеринг** недопустим для операций DELETE и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-212">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-213">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-213">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-214">**Перечисление**. операции перечисления поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-214">**Enumerate** : Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-215">Атрибут **СУППОРТФРАГМЕНТ** не поддерживается для операций перечисления и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="c44bb-215">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="c44bb-216">Атрибут **суппортфилтеринг** является допустимым, и если подключаемый модуль поддерживает фильтрацию, этот атрибут должен иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="c44bb-216">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-217">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-217">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-218">**Get** : операции Get поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-218">**Get** : Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-219">Атрибут **суппортфрагмент** используется, если операция get поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="c44bb-219">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="c44bb-220">Атрибут **суппортфилтеринг** недопустим для операций Get и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-220">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-221">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-221">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-222">**Invoke** : операции Invoke поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-222">**Invoke** : Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-223">Атрибут **суппортфрагмент** не поддерживается для операций Invoke и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="c44bb-223">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="c44bb-224">Атрибут **суппортфилтеринг** является недопустимым и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-224">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-225">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-225">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-226">Операция **размещения** : операции размещения поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-226">**Put** : Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-227">Атрибут **суппортфрагмент** используется, если операция размещения поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="c44bb-227">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="c44bb-228">Атрибут **суппортфилтеринг** недопустим для операций размещения и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-228">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-229">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-229">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-230">**Subscribe** : операции подписки поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-230">**Subscribe** : Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-231">Атрибут **суппортфрагмент** не поддерживается для операций подписки и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="c44bb-231">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="c44bb-232">Атрибут **суппортфилтеринг** недопустим для операций Subscribe и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-232">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-233">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-233">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="c44bb-234">**Shell** : операции оболочки поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="c44bb-234">**Shell** : Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="c44bb-235">Атрибут **суппортфрагмент** не поддерживается для операций оболочки и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-235">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="c44bb-236">Атрибут **суппортфилтеринг** недопустим для операций оболочки и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="c44bb-236">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-237">Эта операция недопустима для URI, если также поддерживается любая другая операция.</span><span class="sxs-lookup"><span data-stu-id="c44bb-237">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c44bb-238">Если для URI настроена операция Shell, операции Get, Put, Create, Delete, Invoke и Enumerate обрабатываются в рамках службы WS-Management (WinRM) для управления оболочками.</span><span class="sxs-lookup"><span data-stu-id="c44bb-238">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="c44bb-239">В результате подключаемый модуль не может обрабатывать операции.</span><span class="sxs-lookup"><span data-stu-id="c44bb-239">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-240">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-240">Cmdlets supported</span></span>

- [<span data-ttu-id="c44bb-241">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-241">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="c44bb-242">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-242">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="c44bb-243">Указывает отпечаток сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="c44bb-243">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="c44bb-244">Это значение представляет собой строку двузначных шестнадцатеричных значений в поле Thumbprint сертификата.</span><span class="sxs-lookup"><span data-stu-id="c44bb-244">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="c44bb-245">Оно задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="c44bb-245">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="c44bb-246">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="c44bb-246">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="c44bb-247">Они могут сопоставляться только с локальными учетными записями пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="c44bb-247">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="c44bb-248">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на `Cert:` диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44bb-248">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-249">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-249">Cmdlets supported</span></span>

- [<span data-ttu-id="c44bb-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-250">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="c44bb-251">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="c44bb-251">Enabled \<Boolean\></span></span>

<span data-ttu-id="c44bb-252">Указывает, включен или отключен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="c44bb-252">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="c44bb-253">Значение по умолчанию равно True.</span><span class="sxs-lookup"><span data-stu-id="c44bb-253">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-254">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-254">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-255">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-255">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="c44bb-256">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-256">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="c44bb-257">Указывает имя файла подключаемого модуля операций.</span><span class="sxs-lookup"><span data-stu-id="c44bb-257">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="c44bb-258">Все переменные среды, помещаемые в эту запись, будут развернуты в контексте пользователей при получении запроса.</span><span class="sxs-lookup"><span data-stu-id="c44bb-258">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="c44bb-259">Так как каждый пользователь может иметь другую версию одной и той же переменной среды, у каждого пользователя может быть другой подключаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="c44bb-259">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="c44bb-260">Эта запись не может быть пустой и должна указывать на допустимый подключаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="c44bb-260">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-261">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-261">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-262">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-262">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="c44bb-263">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-263">HostName \<String\></span></span>

<span data-ttu-id="c44bb-264">Указывает имя компьютера, на котором выполняется служба WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="c44bb-264">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="c44bb-265">Значением должно быть полное доменное имя, символьная строка IPv4 или IPv6 или подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="c44bb-265">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-266">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-266">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-267">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-267">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="c44bb-268">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-268">Issuer \<String\></span></span>

<span data-ttu-id="c44bb-269">Задает имя центра сертификации, выдавшего сертификат.</span><span class="sxs-lookup"><span data-stu-id="c44bb-269">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-270">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-270">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-271">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-271">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="c44bb-272">\<\>Подключаемые модули WS-Management подключаемых модулей — это собственные библиотеки динамической компоновки (DLL)</span><span class="sxs-lookup"><span data-stu-id="c44bb-272">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="c44bb-273">который подключается к и расширяет функциональные возможности WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-273">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="c44bb-274">Интерфейс API подключаемого модуля WSW-Management предоставляет функции, позволяющие пользователю создавать подключаемые модули, реализуя определенные API для поддерживаемых URI и операций с ресурсами.</span><span class="sxs-lookup"><span data-stu-id="c44bb-274">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="c44bb-275">После настройки подключаемых модулей под службу WS-Management (WinRM) или службы IIS подключаемые модули загружаются на узел WS-Management или узел служб IIS соответственно.</span><span class="sxs-lookup"><span data-stu-id="c44bb-275">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="c44bb-276">Удаленные запросы передаются входным точкам этих подключаемых модулей для выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="c44bb-276">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-277">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-277">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-278">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-278">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="c44bb-279">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="c44bb-279">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="c44bb-280">Задает TCP-порт, для которого создается данный прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="c44bb-280">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="c44bb-281">Можно указать любое значение от 1 до 65535.</span><span class="sxs-lookup"><span data-stu-id="c44bb-281">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-282">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="c44bb-284">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-284">Resource \<String\></span></span>

<span data-ttu-id="c44bb-285">Задает конечную точку, которая представляет определенный тип операции управления или значение.</span><span class="sxs-lookup"><span data-stu-id="c44bb-285">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="c44bb-286">Служба предоставляет один или несколько ресурсов, и некоторые ресурсы могут иметь более одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c44bb-286">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="c44bb-287">Ресурс управления сходен с классом WMI или с таблицей базы данных, а экземпляр сходен с экземпляром класса или со строкой в таблице.</span><span class="sxs-lookup"><span data-stu-id="c44bb-287">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="c44bb-288">Например, класс **Win32_LogicalDisk** представляет ресурс.</span><span class="sxs-lookup"><span data-stu-id="c44bb-288">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="c44bb-289">`Win32_LogicalDisk="C:\\"` — Это конкретный экземпляр ресурса.</span><span class="sxs-lookup"><span data-stu-id="c44bb-289">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="c44bb-290">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c44bb-290">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="c44bb-291">Пример:</span><span class="sxs-lookup"><span data-stu-id="c44bb-291">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-292">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-292">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-293">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-293">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="c44bb-294">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-294">Resource \<String\></span></span>

<span data-ttu-id="c44bb-295">Задает универсальный идентификатор ресурса (URI), который идентифицирует конкретный тип ресурса, например диск или процесс, на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c44bb-295">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="c44bb-296">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c44bb-296">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="c44bb-297">Пример:</span><span class="sxs-lookup"><span data-stu-id="c44bb-297">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-298">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-298">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-299">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-299">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="c44bb-300">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-300">SDKVersion \<String\></span></span>

<span data-ttu-id="c44bb-301">Указывает версию пакета SDK подключаемого модуля WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-301">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="c44bb-302">Единственное допустимое значение:</span><span class="sxs-lookup"><span data-stu-id="c44bb-302">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-303">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-303">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-304">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-304">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="c44bb-305">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-305">Subject \<String\></span></span>

<span data-ttu-id="c44bb-306">Задает сущность, которая идентифицируется с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="c44bb-306">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-307">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-307">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-308">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-308">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="c44bb-309">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-309">Transport \<String\></span></span>

<span data-ttu-id="c44bb-310">Указывает транспорт для отправки и получения запросов и ответов протокола WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c44bb-310">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="c44bb-311">Значением должен быть протокол HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c44bb-311">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="c44bb-312">Примечание. значение транспорта задается при создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="c44bb-312">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-313">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-313">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-314">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-314">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="c44bb-315">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-315">URI \<String\></span></span>

<span data-ttu-id="c44bb-316">Определяет URI, доступ к которому авторизуется на основании значения параметра.</span><span class="sxs-lookup"><span data-stu-id="c44bb-316">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-317">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-317">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-318">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-318">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="c44bb-319">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-319">URLPrefix \<String\></span></span>

<span data-ttu-id="c44bb-320">Префикс URL-адреса для получения HTTP- или HTTPS-запросов.</span><span class="sxs-lookup"><span data-stu-id="c44bb-320">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="c44bb-321">Это строка, содержащая только символы `[a-z]` , `[A-Z]` ,, символы `[9-0]` подчеркивания ( `_` ) и обратную косую черту ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="c44bb-321">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="c44bb-322">Строка не должна начинаться с или заканчиваться обратной косой чертой ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="c44bb-322">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="c44bb-323">Например, если имя компьютера — "Самплекомпутер", клиент WS-Management будет указывать `http://SampleMachine/URLPrefix` в адресе назначения.</span><span class="sxs-lookup"><span data-stu-id="c44bb-323">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-324">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-324">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-325">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-325">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="c44bb-326">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-326">Value \<String\></span></span>

<span data-ttu-id="c44bb-327">Задает значение параметра инициализации, которое является специфичным для подключаемого модуля и используется для указания параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c44bb-327">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-328">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-328">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-329">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-329">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="c44bb-330">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="c44bb-330">XMLRenderingType \<String\></span></span>

<span data-ttu-id="c44bb-331">Указывает формат, в котором XML передается подключаемым модулям через объект **WSMAN_DATA** .</span><span class="sxs-lookup"><span data-stu-id="c44bb-331">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="c44bb-332">Допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="c44bb-332">The following are valid values:</span></span>

- <span data-ttu-id="c44bb-333">Text: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_TEXT** , которая представляет XML в качестве буфера памяти **пквстр** .</span><span class="sxs-lookup"><span data-stu-id="c44bb-333">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="c44bb-334">XMLReader: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_WS_XML_READER** , которая представляет XML как объект **XmlReader** , который определен в файле заголовка "WebService. h".</span><span class="sxs-lookup"><span data-stu-id="c44bb-334">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="c44bb-335">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="c44bb-335">Cmdlets Supported</span></span>

- [<span data-ttu-id="c44bb-336">New-Item</span><span class="sxs-lookup"><span data-stu-id="c44bb-336">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="c44bb-337">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="c44bb-337">Using the pipeline</span></span>

<span data-ttu-id="c44bb-338">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="c44bb-338">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="c44bb-339">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="c44bb-339">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="c44bb-340">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c44bb-340">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="c44bb-341">Получение справки</span><span class="sxs-lookup"><span data-stu-id="c44bb-341">Getting help</span></span>

<span data-ttu-id="c44bb-342">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="c44bb-342">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="c44bb-343">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="c44bb-343">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="c44bb-344">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c44bb-344">See also</span></span>

[<span data-ttu-id="c44bb-345">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c44bb-345">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

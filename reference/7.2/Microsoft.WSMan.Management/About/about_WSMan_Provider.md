---
description: WSMan
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WSMan Provider
ms.openlocfilehash: 32baaaec3589fc9d6f4c2319f47d56bca777f738
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604790"
---
# <a name="wsman-provider"></a><span data-ttu-id="89ccf-103">WSMan Provider</span><span class="sxs-lookup"><span data-stu-id="89ccf-103">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="89ccf-104">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="89ccf-104">Provider name</span></span>

<span data-ttu-id="89ccf-105">WSMan</span><span class="sxs-lookup"><span data-stu-id="89ccf-105">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="89ccf-106">Диски</span><span class="sxs-lookup"><span data-stu-id="89ccf-106">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="89ccf-107">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="89ccf-107">Short description</span></span>

<span data-ttu-id="89ccf-108">Обеспечивает доступ к конфигурационной информации веб-служб WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-108">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="89ccf-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="89ccf-109">Detailed description</span></span>

<span data-ttu-id="89ccf-110">Поставщик **WSMan** для PowerShell позволяет добавлять, изменять, очищать и удалять WS-Management данные конфигурации на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="89ccf-110">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="89ccf-111">Поставщик **WSMan** предоставляет диск PowerShell со структурой каталогов, соответствующей логической группировке параметров конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-111">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="89ccf-112">Эти группы называются контейнерами.</span><span class="sxs-lookup"><span data-stu-id="89ccf-112">These groupings are known as containers.</span></span>

<span data-ttu-id="89ccf-113">Начиная с Windows PowerShell 3,0, поставщик **WSMan** был обновлен для поддержки новых свойств конфигураций сеансов, таких как **аутпутбуфферингмоде**.</span><span class="sxs-lookup"><span data-stu-id="89ccf-113">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="89ccf-114">Конфигурации сеансов отображаются как элементы в каталоге подключаемого модуля `WSMan:` диска, и свойства отображаются в виде элементов в каждой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="89ccf-114">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="89ccf-115">Поставщик **WSMan** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="89ccf-115">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="89ccf-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="89ccf-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="89ccf-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="89ccf-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="89ccf-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="89ccf-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="89ccf-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="89ccf-120">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-120">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="89ccf-121">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-121">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="89ccf-122">`WSMan:`Для изменения значений новых свойств можно использовать команды на диске.</span><span class="sxs-lookup"><span data-stu-id="89ccf-122">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="89ccf-123">Однако вы не можете использовать `WSMan:` диск в PowerShell 2,0, чтобы изменить свойства, появившиеся в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="89ccf-123">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="89ccf-124">Несмотря на то, что ошибки не возникают, команды не могут изменить эти параметры, используйте диск **WSMan** в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="89ccf-124">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="89ccf-125">Организация диска WSMan:</span><span class="sxs-lookup"><span data-stu-id="89ccf-125">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="89ccf-126">**Клиент**. можно настроить различные аспекты клиента WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-126">**Client**: You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="89ccf-127">Сведения о конфигурации сохраняются в реестре.</span><span class="sxs-lookup"><span data-stu-id="89ccf-127">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="89ccf-128">**Служба**. можно настроить различные аспекты службы WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-128">**Service**: You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="89ccf-129">Сведения о конфигурации сохраняются в реестре.</span><span class="sxs-lookup"><span data-stu-id="89ccf-129">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-130">Конфигурация службы иногда называется конфигурацией сервера.</span><span class="sxs-lookup"><span data-stu-id="89ccf-130">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="89ccf-131">**Shell**: можно настроить различные аспекты оболочки WS-Management, такие как параметр, разрешающий доступ к удаленной оболочке (**алловремотешеллакцесс**), и максимальное разрешенное число пользователей (**максконкуррентусерс**).</span><span class="sxs-lookup"><span data-stu-id="89ccf-131">**Shell**: You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access (**AllowRemoteShellAccess**) and the maximum number of concurrent users allowed (**MaxConcurrentUsers**).</span></span>

- <span data-ttu-id="89ccf-132">**Прослушиватель**. Вы можете создать и настроить прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="89ccf-132">**Listener**: You can create and configure a listener.</span></span> <span data-ttu-id="89ccf-133">Прослушиватель — это служба управления, реализующая протокол WS-Management для отправки и получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="89ccf-133">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="89ccf-134">**Подключаемый модуль**. подключаемые модули загружаются и используются службой WS-Management для предоставления различных функций.</span><span class="sxs-lookup"><span data-stu-id="89ccf-134">**Plugin**: Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="89ccf-135">По умолчанию PowerShell предоставляет три подключаемых модуля:</span><span class="sxs-lookup"><span data-stu-id="89ccf-135">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="89ccf-136">Подключаемый модуль пересылки событий.</span><span class="sxs-lookup"><span data-stu-id="89ccf-136">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="89ccf-137">Подключаемый модуль Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-137">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="89ccf-138">Подключаемый модуль поставщика инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="89ccf-138">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="89ccf-139">Эти три подключаемые модули поддерживают пересылку событий, конфигурацию и доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-139">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="89ccf-140">**Clientcertificate**. Вы можете создать и настроить сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="89ccf-140">**ClientCertificate**: You can create and configure a client certificate.</span></span>
  <span data-ttu-id="89ccf-141">Сертификат клиента применяется в том случае, если клиент WS-Management настроен для использования проверки подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="89ccf-141">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="89ccf-142">Иерархия каталогов поставщика WSMan</span><span class="sxs-lookup"><span data-stu-id="89ccf-142">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="89ccf-143">Иерархия каталогов поставщика WSMan для локального компьютера выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="89ccf-143">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

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

<span data-ttu-id="89ccf-144">Иерархия каталогов поставщика WS-Management для удаленного компьютера аналогична иерархии каталогов для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="89ccf-144">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="89ccf-145">Однако для доступа к параметрам конфигурации удаленного компьютера необходимо установить подключение к удаленному компьютеру с помощью командлета [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="89ccf-145">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="89ccf-146">После установления подключения к удаленному компьютеру имя удаленного компьютера появляется в поставщике.</span><span class="sxs-lookup"><span data-stu-id="89ccf-146">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="89ccf-147">Навигация по диску WSMan:</span><span class="sxs-lookup"><span data-stu-id="89ccf-147">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="89ccf-148">Эта команда использует `Set-Location` командлет для изменения текущего расположения на `WSMan:` диск.</span><span class="sxs-lookup"><span data-stu-id="89ccf-148">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="89ccf-149">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="89ccf-149">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="89ccf-150">Например, введите.</span><span class="sxs-lookup"><span data-stu-id="89ccf-150">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="89ccf-151">Переход к расположению удаленного системного хранилища</span><span class="sxs-lookup"><span data-stu-id="89ccf-151">Navigating to a remote system store location</span></span>

<span data-ttu-id="89ccf-152">Эта команда использует `Set-Location` команду, чтобы изменить текущее расположение на корневое расположение в расположении удаленного хранилища системы.</span><span class="sxs-lookup"><span data-stu-id="89ccf-152">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="89ccf-153">Используйте обратную косую черту или косую `\` черту, `/` чтобы указать уровень `WSMan:` диска.</span><span class="sxs-lookup"><span data-stu-id="89ccf-153">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="89ccf-154">Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="89ccf-154">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="89ccf-155">Отображение содержимого диска WSMan:</span><span class="sxs-lookup"><span data-stu-id="89ccf-155">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="89ccf-156">Эта команда использует `Get-Childitem` командлет для вывода хранилищ WS-Management в расположении хранилища localhost.</span><span class="sxs-lookup"><span data-stu-id="89ccf-156">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="89ccf-157">Если вы используете `WSMan:` диск, можно опустить имя диска.</span><span class="sxs-lookup"><span data-stu-id="89ccf-157">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="89ccf-158">Эта команда использует `Get-Childitem` командлет для показа WS-Management хранилищ в расположении хранилища на удаленном компьютере "Server01".</span><span class="sxs-lookup"><span data-stu-id="89ccf-158">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="89ccf-159">Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="89ccf-159">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="89ccf-160">Установка значения элементов на диске WSMAN:</span><span class="sxs-lookup"><span data-stu-id="89ccf-160">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="89ccf-161">`Set-Item`С помощью командлета можно изменить параметры конфигурации на `WSMAN` диске.</span><span class="sxs-lookup"><span data-stu-id="89ccf-161">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="89ccf-162">В следующем примере задается значение **TrustedHosts** , которое принимает все узлы с суффиксом "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="89ccf-162">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="89ccf-163">`Set-Item`Командлет поддерживает дополнительный параметр `-Concatenate` , который добавляет значение вместо изменения.</span><span class="sxs-lookup"><span data-stu-id="89ccf-163">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="89ccf-164">В следующем примере новое значение "\*. domain2.com" добавляется к старому значению, хранящемуся в `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="89ccf-164">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="89ccf-165">Создание элементов на диске WSMAN:</span><span class="sxs-lookup"><span data-stu-id="89ccf-165">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="89ccf-166">Создание нового прослушивателя</span><span class="sxs-lookup"><span data-stu-id="89ccf-166">Creating a new listener</span></span>

<span data-ttu-id="89ccf-167">`New-Item`Командлет создает элементы на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="89ccf-167">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="89ccf-168">Каждый поставщик имеет различные типы элементов, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="89ccf-168">Each provider has different item types that you can create.</span></span> <span data-ttu-id="89ccf-169">На `WSMAN:` диске можно создавать *прослушиватели* , настроенные для получения и реагирования на удаленные запросы.</span><span class="sxs-lookup"><span data-stu-id="89ccf-169">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="89ccf-170">Следующая команда создает новый прослушиватель HTTP с помощью `New-Item` командлета.</span><span class="sxs-lookup"><span data-stu-id="89ccf-170">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="89ccf-171">Создание нового подключаемого модуля</span><span class="sxs-lookup"><span data-stu-id="89ccf-171">Creating a new plug-in</span></span>

<span data-ttu-id="89ccf-172">Эта команда создает (регистрирует) подключаемый модуль для службы WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-172">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="89ccf-173">Создание новой записи ресурса</span><span class="sxs-lookup"><span data-stu-id="89ccf-173">Creating a new resource entry</span></span>

<span data-ttu-id="89ccf-174">Эта команда создает запись ресурса в каталоге Resources объекта Тестплугин.</span><span class="sxs-lookup"><span data-stu-id="89ccf-174">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="89ccf-175">Эта команда предполагает, что Тестплугин был создан с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="89ccf-175">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="89ccf-176">Создание новой записи безопасности для ресурса</span><span class="sxs-lookup"><span data-stu-id="89ccf-176">Creating a new security entry for a resource</span></span>

<span data-ttu-id="89ccf-177">Эта команда создает запись безопасности в каталоге Security ресурса Resource_5967683 (конкретного ресурса).</span><span class="sxs-lookup"><span data-stu-id="89ccf-177">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="89ccf-178">Эта команда предполагает, что запись ресурса была создана с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="89ccf-178">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="89ccf-179">Создание нового сертификата клиента</span><span class="sxs-lookup"><span data-stu-id="89ccf-179">Creating a new Client Certificate</span></span>

<span data-ttu-id="89ccf-180">Эта команда создает запись **clientcertificate** , которая может использоваться клиентом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-180">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="89ccf-181">Новый **clientcertificate** будет отображаться в каталоге **ClientCertificate** как "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="89ccf-181">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="89ccf-182">Все параметры являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="89ccf-182">All of the parameters are mandatory.</span></span> <span data-ttu-id="89ccf-183">**Издатель** должен быть отпечаткой сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="89ccf-183">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="89ccf-184">Создание нового параметра инициализации</span><span class="sxs-lookup"><span data-stu-id="89ccf-184">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="89ccf-185">Эта команда создает параметр инициализации с именем "тестпараметернаме" в каталоге "Инитиализатионпараметерс".</span><span class="sxs-lookup"><span data-stu-id="89ccf-185">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="89ccf-186">Эта команда предполагает, что "Тестплугин" был создан с помощью отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="89ccf-186">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="89ccf-187">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="89ccf-187">Dynamic parameters</span></span>

<span data-ttu-id="89ccf-188">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="89ccf-188">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="89ccf-189">Address \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-189">Address \<String\></span></span>

<span data-ttu-id="89ccf-190">Задает адрес, для которого был создан данный прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="89ccf-190">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="89ccf-191">Он может иметь одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="89ccf-191">The value can be one of the following:</span></span>

- <span data-ttu-id="89ccf-192">Строка литерала "\*".</span><span class="sxs-lookup"><span data-stu-id="89ccf-192">The literal string "\*".</span></span> <span data-ttu-id="89ccf-193">(Подстановочный знак ( `*` ) делает команду привязать все IP-адреса ко всем сетевым адаптерам.)</span><span class="sxs-lookup"><span data-stu-id="89ccf-193">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="89ccf-194">Строка литерала "IP:", за которой следует допустимый IP-адрес в точечно-десятичном формате IPv4 или в шестнадцатеричном формате IPv6.</span><span class="sxs-lookup"><span data-stu-id="89ccf-194">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="89ccf-195">Строка литерала "MAC:", за которой следует MAC-адрес адаптера.</span><span class="sxs-lookup"><span data-stu-id="89ccf-195">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="89ccf-196">Например: MAC: 32-a3-58 -90-to-CC.</span><span class="sxs-lookup"><span data-stu-id="89ccf-196">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="89ccf-197">Значение параметра Address задается при создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="89ccf-197">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-198">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-198">Cmdlets supported</span></span>

- [<span data-ttu-id="89ccf-199">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-199">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="89ccf-200">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="89ccf-200">Capability \<Enumeration\></span></span>

<span data-ttu-id="89ccf-201">При работе с *подключаемыми модулями* этот параметр указывает операцию, которая поддерживается для этого универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="89ccf-201">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="89ccf-202">Необходимо создать по одной записи для каждого типа операций, поддерживаемого URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-202">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="89ccf-203">Можно указать любые допустимые атрибуты для данной операции, если она поддерживается операцией.</span><span class="sxs-lookup"><span data-stu-id="89ccf-203">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="89ccf-204">Эти атрибуты включают **SupportsFiltering имеет** и **суппортсфрагмент**.</span><span class="sxs-lookup"><span data-stu-id="89ccf-204">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="89ccf-205">**CREATE**: операции создания поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-205">**Create**: Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-206">Атрибут **суппортфрагмент**  используется, если операция создания поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="89ccf-206">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="89ccf-207">Атрибут **суппортфилтеринг** недопустим для операций создания и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-207">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-208">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-208">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-209">**Delete**: операции Delete поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-209">**Delete**: Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-210">Атрибут **суппортфрагмент** используется, если операция удаления поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="89ccf-210">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="89ccf-211">Атрибут **суппортфилтеринг** недопустим для операций DELETE и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-211">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-212">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-212">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-213">**Перечисление**. операции перечисления поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-213">**Enumerate**: Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-214">Атрибут **СУППОРТФРАГМЕНТ** не поддерживается для операций перечисления и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="89ccf-214">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="89ccf-215">Атрибут **суппортфилтеринг** является допустимым, и если подключаемый модуль поддерживает фильтрацию, этот атрибут должен иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="89ccf-215">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-216">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-216">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-217">**Get**: операции Get поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-217">**Get**: Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-218">Атрибут **суппортфрагмент** используется, если операция get поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="89ccf-218">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="89ccf-219">Атрибут **суппортфилтеринг** недопустим для операций Get и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-219">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-220">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-220">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-221">**Invoke**: операции Invoke поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-221">**Invoke**: Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-222">Атрибут **суппортфрагмент** не поддерживается для операций Invoke и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="89ccf-222">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="89ccf-223">Атрибут **суппортфилтеринг** является недопустимым и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-223">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-224">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-224">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-225">Операция **размещения**: операции размещения поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-225">**Put**: Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-226">Атрибут **суппортфрагмент** используется, если операция размещения поддерживает концепцию.</span><span class="sxs-lookup"><span data-stu-id="89ccf-226">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="89ccf-227">Атрибут **суппортфилтеринг** недопустим для операций размещения и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-227">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-228">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-228">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-229">**Subscribe**: операции подписки поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-229">**Subscribe**: Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-230">Атрибут **суппортфрагмент** не поддерживается для операций подписки и должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="89ccf-230">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="89ccf-231">Атрибут **суппортфилтеринг** недопустим для операций Subscribe и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-231">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-232">Эта операция недопустима для URI, если поддерживаются операции Shell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-232">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="89ccf-233">**Shell**: операции оболочки поддерживаются в URI.</span><span class="sxs-lookup"><span data-stu-id="89ccf-233">**Shell**: Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="89ccf-234">Атрибут **суппортфрагмент** не поддерживается для операций оболочки и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-234">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="89ccf-235">Атрибут **суппортфилтеринг** недопустим для операций оболочки и должен иметь значение "false".</span><span class="sxs-lookup"><span data-stu-id="89ccf-235">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-236">Эта операция недопустима для URI, если также поддерживается любая другая операция.</span><span class="sxs-lookup"><span data-stu-id="89ccf-236">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="89ccf-237">Если для URI настроена операция Shell, операции Get, Put, Create, Delete, Invoke и Enumerate обрабатываются в рамках службы WS-Management (WinRM) для управления оболочками.</span><span class="sxs-lookup"><span data-stu-id="89ccf-237">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="89ccf-238">В результате подключаемый модуль не может обрабатывать операции.</span><span class="sxs-lookup"><span data-stu-id="89ccf-238">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-239">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-239">Cmdlets supported</span></span>

- [<span data-ttu-id="89ccf-240">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-240">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="89ccf-241">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-241">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="89ccf-242">Указывает отпечаток сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="89ccf-242">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="89ccf-243">Это значение представляет собой строку двузначных шестнадцатеричных значений в поле Thumbprint сертификата.</span><span class="sxs-lookup"><span data-stu-id="89ccf-243">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="89ccf-244">Оно задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="89ccf-244">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="89ccf-245">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="89ccf-245">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="89ccf-246">Они могут сопоставляться только с локальными учетными записями пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="89ccf-246">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="89ccf-247">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на `Cert:` диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ccf-247">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-248">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-248">Cmdlets supported</span></span>

- [<span data-ttu-id="89ccf-249">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-249">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="89ccf-250">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="89ccf-250">Enabled \<Boolean\></span></span>

<span data-ttu-id="89ccf-251">Указывает, включен или отключен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="89ccf-251">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="89ccf-252">Значение по умолчанию равно True.</span><span class="sxs-lookup"><span data-stu-id="89ccf-252">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-253">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-253">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-254">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="89ccf-255">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-255">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="89ccf-256">Указывает имя файла подключаемого модуля операций.</span><span class="sxs-lookup"><span data-stu-id="89ccf-256">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="89ccf-257">Все переменные среды, помещаемые в эту запись, будут развернуты в контексте пользователей при получении запроса.</span><span class="sxs-lookup"><span data-stu-id="89ccf-257">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="89ccf-258">Так как каждый пользователь может иметь другую версию одной и той же переменной среды, у каждого пользователя может быть другой подключаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="89ccf-258">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="89ccf-259">Эта запись не может быть пустой и должна указывать на допустимый подключаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="89ccf-259">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-260">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-260">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-261">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-261">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="89ccf-262">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-262">HostName \<String\></span></span>

<span data-ttu-id="89ccf-263">Указывает имя компьютера, на котором выполняется служба WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="89ccf-263">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="89ccf-264">Значением должно быть полное доменное имя, символьная строка IPv4 или IPv6 или подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="89ccf-264">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-265">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-265">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-266">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-266">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="89ccf-267">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-267">Issuer \<String\></span></span>

<span data-ttu-id="89ccf-268">Задает имя центра сертификации, выдавшего сертификат.</span><span class="sxs-lookup"><span data-stu-id="89ccf-268">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-269">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-269">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-270">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-270">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="89ccf-271">\<\>Подключаемые модули WS-Management подключаемых модулей — это собственные библиотеки динамической компоновки (DLL)</span><span class="sxs-lookup"><span data-stu-id="89ccf-271">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="89ccf-272">который подключается к и расширяет функциональные возможности WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-272">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="89ccf-273">Интерфейс API подключаемого модуля WSW-Management предоставляет функции, позволяющие пользователю создавать подключаемые модули, реализуя определенные API для поддерживаемых URI и операций с ресурсами.</span><span class="sxs-lookup"><span data-stu-id="89ccf-273">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="89ccf-274">После настройки подключаемых модулей под службу WS-Management (WinRM) или службы IIS подключаемые модули загружаются на узел WS-Management или узел служб IIS соответственно.</span><span class="sxs-lookup"><span data-stu-id="89ccf-274">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="89ccf-275">Удаленные запросы передаются входным точкам этих подключаемых модулей для выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="89ccf-275">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-276">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-276">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-277">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-277">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="89ccf-278">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="89ccf-278">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="89ccf-279">Задает TCP-порт, для которого создается данный прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="89ccf-279">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="89ccf-280">Можно указать любое значение от 1 до 65535.</span><span class="sxs-lookup"><span data-stu-id="89ccf-280">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-281">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-281">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-282">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-282">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="89ccf-283">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-283">Resource \<String\></span></span>

<span data-ttu-id="89ccf-284">Задает конечную точку, которая представляет определенный тип операции управления или значение.</span><span class="sxs-lookup"><span data-stu-id="89ccf-284">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="89ccf-285">Служба предоставляет один или несколько ресурсов, и некоторые ресурсы могут иметь более одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="89ccf-285">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="89ccf-286">Ресурс управления сходен с классом WMI или с таблицей базы данных, а экземпляр сходен с экземпляром класса или со строкой в таблице.</span><span class="sxs-lookup"><span data-stu-id="89ccf-286">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="89ccf-287">Например, класс **Win32_LogicalDisk** представляет ресурс.</span><span class="sxs-lookup"><span data-stu-id="89ccf-287">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="89ccf-288">`Win32_LogicalDisk="C:\\"` — Это конкретный экземпляр ресурса.</span><span class="sxs-lookup"><span data-stu-id="89ccf-288">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="89ccf-289">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="89ccf-289">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="89ccf-290">Пример:</span><span class="sxs-lookup"><span data-stu-id="89ccf-290">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-291">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-291">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-292">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-292">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="89ccf-293">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-293">Resource \<String\></span></span>

<span data-ttu-id="89ccf-294">Задает универсальный идентификатор ресурса (URI), который идентифицирует конкретный тип ресурса, например диск или процесс, на компьютере.</span><span class="sxs-lookup"><span data-stu-id="89ccf-294">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="89ccf-295">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="89ccf-295">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="89ccf-296">Пример:</span><span class="sxs-lookup"><span data-stu-id="89ccf-296">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-297">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-297">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-298">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-298">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="89ccf-299">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-299">SDKVersion \<String\></span></span>

<span data-ttu-id="89ccf-300">Указывает версию пакета SDK подключаемого модуля WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-300">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="89ccf-301">Единственное допустимое значение:</span><span class="sxs-lookup"><span data-stu-id="89ccf-301">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-302">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-302">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-303">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-303">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="89ccf-304">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-304">Subject \<String\></span></span>

<span data-ttu-id="89ccf-305">Задает сущность, которая идентифицируется с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="89ccf-305">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-306">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-306">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-307">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-307">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="89ccf-308">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-308">Transport \<String\></span></span>

<span data-ttu-id="89ccf-309">Указывает транспорт для отправки и получения запросов и ответов протокола WS-Management.</span><span class="sxs-lookup"><span data-stu-id="89ccf-309">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="89ccf-310">Значением должен быть протокол HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89ccf-310">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="89ccf-311">Примечание. значение транспорта задается при создании прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="89ccf-311">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-312">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-312">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-313">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-313">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="89ccf-314">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-314">URI \<String\></span></span>

<span data-ttu-id="89ccf-315">Определяет URI, доступ к которому авторизуется на основании значения параметра.</span><span class="sxs-lookup"><span data-stu-id="89ccf-315">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-316">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-316">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-317">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-317">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="89ccf-318">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-318">URLPrefix \<String\></span></span>

<span data-ttu-id="89ccf-319">Префикс URL-адреса для получения HTTP- или HTTPS-запросов.</span><span class="sxs-lookup"><span data-stu-id="89ccf-319">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="89ccf-320">Это строка, содержащая только символы `[a-z]` , `[A-Z]` ,, символы `[9-0]` подчеркивания ( `_` ) и обратную косую черту ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="89ccf-320">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="89ccf-321">Строка не должна начинаться с или заканчиваться обратной косой чертой ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="89ccf-321">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="89ccf-322">Например, если имя компьютера — "Самплекомпутер", клиент WS-Management будет указывать `http://SampleMachine/URLPrefix` в адресе назначения.</span><span class="sxs-lookup"><span data-stu-id="89ccf-322">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-323">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-323">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-324">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-324">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="89ccf-325">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-325">Value \<String\></span></span>

<span data-ttu-id="89ccf-326">Задает значение параметра инициализации, которое является специфичным для подключаемого модуля и используется для указания параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89ccf-326">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-327">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-327">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-328">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-328">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="89ccf-329">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="89ccf-329">XMLRenderingType \<String\></span></span>

<span data-ttu-id="89ccf-330">Указывает формат, в котором XML передается подключаемым модулям через объект **WSMAN_DATA** .</span><span class="sxs-lookup"><span data-stu-id="89ccf-330">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="89ccf-331">Допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="89ccf-331">The following are valid values:</span></span>

- <span data-ttu-id="89ccf-332">Text: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_TEXT** , которая представляет XML в качестве буфера памяти **пквстр** .</span><span class="sxs-lookup"><span data-stu-id="89ccf-332">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="89ccf-333">XMLReader: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_WS_XML_READER** , которая представляет XML как объект **XmlReader** , который определен в файле заголовка "WebService. h".</span><span class="sxs-lookup"><span data-stu-id="89ccf-333">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="89ccf-334">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="89ccf-334">Cmdlets Supported</span></span>

- [<span data-ttu-id="89ccf-335">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ccf-335">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="89ccf-336">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="89ccf-336">Using the pipeline</span></span>

<span data-ttu-id="89ccf-337">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="89ccf-337">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="89ccf-338">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="89ccf-338">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="89ccf-339">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="89ccf-339">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="89ccf-340">Получение справки</span><span class="sxs-lookup"><span data-stu-id="89ccf-340">Getting help</span></span>

<span data-ttu-id="89ccf-341">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="89ccf-341">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="89ccf-342">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="89ccf-342">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="89ccf-343">См. также</span><span class="sxs-lookup"><span data-stu-id="89ccf-343">See also</span></span>

[<span data-ttu-id="89ccf-344">about_Providers</span><span class="sxs-lookup"><span data-stu-id="89ccf-344">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)


---
ms.date: 05/14/2020
keywords: powershell,командлет
title: Выполнение второго прыжка при удаленном взаимодействии PowerShell
ms.openlocfilehash: 3a9db11726d4c02dc69e52c45da304f7422def39
ms.sourcegitcommit: 843756c8277e7afb874867703963248abc8a6c91
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83439382"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="e1223-103">Выполнение второго прыжка при удаленном взаимодействии PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1223-103">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="e1223-104">"Проблема второго прыжка" относится к ситуации, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="e1223-104">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="e1223-105">Вы вошли на сервер _ServerA_.</span><span class="sxs-lookup"><span data-stu-id="e1223-105">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="e1223-106">С сервера _ServerA_ вы запускаете удаленный сеанс PowerShell для подключения к серверу _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="e1223-106">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="e1223-107">Команда, запущенная вами на сервере _ServerB_ через сеанс удаленного взаимодействия PowerShell, пытается получить доступ к ресурсу на сервере _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="e1223-107">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="e1223-108">Доступ к ресурсу на _ServerC_ запрещен, так как учетные данные, используемые вами для создания сеанса удаленного взаимодействия PowerShell, не передаются с сервера _ServerB_ на сервер _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="e1223-108">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="e1223-109">Существует несколько способов для решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e1223-109">There are several ways to address this problem.</span></span> <span data-ttu-id="e1223-110">В следующей таблице перечислены методы в порядке предпочтения.</span><span class="sxs-lookup"><span data-stu-id="e1223-110">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="e1223-111">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e1223-111">Configuration</span></span>                       |                                  <span data-ttu-id="e1223-112">Примечание</span><span class="sxs-lookup"><span data-stu-id="e1223-112">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="e1223-113">CredSSP</span><span class="sxs-lookup"><span data-stu-id="e1223-113">CredSSP</span></span>                                                  | <span data-ttu-id="e1223-114">Сбалансированное сочетание простоты использования и безопасности</span><span class="sxs-lookup"><span data-stu-id="e1223-114">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="e1223-115">Ограниченное делегирование Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="e1223-115">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="e1223-116">Более высокая безопасность с простой настройкой</span><span class="sxs-lookup"><span data-stu-id="e1223-116">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="e1223-117">Ограниченное делегирование Kerberos</span><span class="sxs-lookup"><span data-stu-id="e1223-117">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="e1223-118">Высокий уровень безопасности, но с необходимостью прав администратора домена</span><span class="sxs-lookup"><span data-stu-id="e1223-118">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="e1223-119">Делегирование Kerberos (без ограничений)</span><span class="sxs-lookup"><span data-stu-id="e1223-119">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="e1223-120">Не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="e1223-120">Not recommended</span></span>                                                        |
| <span data-ttu-id="e1223-121">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="e1223-121">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="e1223-122">Потенциально наилучшая безопасность, но с необходимостью тщательной настройки</span><span class="sxs-lookup"><span data-stu-id="e1223-122">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="e1223-123">PSSessionConfiguration с использованием RunAs</span><span class="sxs-lookup"><span data-stu-id="e1223-123">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="e1223-124">Более простая настройка, но с необходимостью управления учетными данными</span><span class="sxs-lookup"><span data-stu-id="e1223-124">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="e1223-125">Передача учетных данных внутри блока сценария `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="e1223-125">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="e1223-126">Максимальная простота использования, но с необходимостью указания учетных данных</span><span class="sxs-lookup"><span data-stu-id="e1223-126">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="e1223-127">CredSSP</span><span class="sxs-lookup"><span data-stu-id="e1223-127">CredSSP</span></span>

<span data-ttu-id="e1223-128">Для проверки подлинности можно использовать [протокол CredSSP][credssp].</span><span class="sxs-lookup"><span data-stu-id="e1223-128">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="e1223-129">Протокол CredSSP кэширует учетные данные на удаленном сервере (_ServerB_), что делает их уязвимыми для атак, направленных на кражу учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e1223-129">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="e1223-130">Если безопасность удаленного компьютера нарушена, злоумышленник получает доступ к учетным данным пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1223-130">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="e1223-131">Протокол CredSSP по умолчанию отключен на компьютерах клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="e1223-131">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="e1223-132">Включать протокол CredSSP следует только в самых надежных средах.</span><span class="sxs-lookup"><span data-stu-id="e1223-132">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="e1223-133">Например, при подключении администратора домена к контроллеру домена, так как контроллер домена является высоконадежным.</span><span class="sxs-lookup"><span data-stu-id="e1223-133">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="e1223-134">Дополнительные сведения о вопросах безопасности при использовании протокола CredSSP для удаленного взаимодействия PowerShell см. в статье [Accidental Sabotage: Beware of CredSSP][beware] (Непреднамеренный саботаж: берегитесь CredSSP).</span><span class="sxs-lookup"><span data-stu-id="e1223-134">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="e1223-135">Дополнительные сведения об атаках, направленных на хищение учетных данных, см. в техническом документе [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span><span class="sxs-lookup"><span data-stu-id="e1223-135">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="e1223-136">См. пример того, как [включить и использовать CredSSP для удаленного взаимодействия PowerShell][credssp-psblog].</span><span class="sxs-lookup"><span data-stu-id="e1223-136">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="e1223-137">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-137">**Pros**</span></span>

- <span data-ttu-id="e1223-138">Это работает для всех серверов с Windows Server 2008 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1223-138">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="e1223-139">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-139">**Cons**</span></span>

- <span data-ttu-id="e1223-140">Имеет уязвимости.</span><span class="sxs-lookup"><span data-stu-id="e1223-140">Has security vulnerabilities.</span></span>
- <span data-ttu-id="e1223-141">Требует настройки как клиентских, так и серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="e1223-141">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="e1223-142">Не работает с группой "Защищенные пользователи".</span><span class="sxs-lookup"><span data-stu-id="e1223-142">Does not work with the Protected Users group.</span></span> <span data-ttu-id="e1223-143">Дополнительные сведения см. в разделе [Группа безопасности "Защищенные пользователи"][protected-users].</span><span class="sxs-lookup"><span data-stu-id="e1223-143">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="e1223-144">Ограниченное делегирование Kerberos</span><span class="sxs-lookup"><span data-stu-id="e1223-144">Kerberos constrained delegation</span></span>

<span data-ttu-id="e1223-145">Для выполнения второго прыжка можно использовать устаревшее ограниченное делегирование (не на основе ресурсов).</span><span class="sxs-lookup"><span data-stu-id="e1223-145">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="e1223-146">Настройте ограниченное делегирование Kerberos с параметром "Использовать любой протокол проверки подлинности", чтобы разрешить переход протокола.</span><span class="sxs-lookup"><span data-stu-id="e1223-146">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="e1223-147">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-147">**Pros**</span></span>

- <span data-ttu-id="e1223-148">Не требует специального кода.</span><span class="sxs-lookup"><span data-stu-id="e1223-148">Requires no special coding</span></span>
- <span data-ttu-id="e1223-149">Учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e1223-149">Credentials are not stored.</span></span>

<span data-ttu-id="e1223-150">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-150">**Cons**</span></span>

- <span data-ttu-id="e1223-151">Не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="e1223-151">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="e1223-152">Для настройки требуются права администратора домена.</span><span class="sxs-lookup"><span data-stu-id="e1223-152">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="e1223-153">Требует настройки для объекта Active Directory удаленного сервера (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="e1223-153">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="e1223-154">Ограничен одним доменом.</span><span class="sxs-lookup"><span data-stu-id="e1223-154">Limited to one domain.</span></span> <span data-ttu-id="e1223-155">Не может использоваться между доменами или лесами.</span><span class="sxs-lookup"><span data-stu-id="e1223-155">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="e1223-156">Требует права на обновление объектов и имен субъектов-служб (SPN).</span><span class="sxs-lookup"><span data-stu-id="e1223-156">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="e1223-157">_ServerB_ может получить билет Kerberos для _ServerC_ от имени пользователя без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1223-157">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="e1223-158">Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы.</span><span class="sxs-lookup"><span data-stu-id="e1223-158">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="e1223-159">Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="e1223-159">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="e1223-160">Ограниченное делегирование Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="e1223-160">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="e1223-161">С помощью ограниченного делегирования Kerberos на основе ресурсов (которое впервые появилось в Windows Server 2012) можно настроить делегирование учетных данных на объект сервера, где находятся ресурсы.</span><span class="sxs-lookup"><span data-stu-id="e1223-161">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="e1223-162">В описанном выше сценарии второго прыжка вы настраиваете сервер _ServerC_, чтобы указать, откуда он будет принимать делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e1223-162">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="e1223-163">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-163">**Pros**</span></span>

- <span data-ttu-id="e1223-164">Учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e1223-164">Credentials are not stored.</span></span>
- <span data-ttu-id="e1223-165">Настраивается с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1223-165">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="e1223-166">Не требует написания специального кода.</span><span class="sxs-lookup"><span data-stu-id="e1223-166">No special coding required.</span></span>
- <span data-ttu-id="e1223-167">Не требует для настройки доступ с правами администратора домена.</span><span class="sxs-lookup"><span data-stu-id="e1223-167">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="e1223-168">Работает между доменами и лесами.</span><span class="sxs-lookup"><span data-stu-id="e1223-168">Works across domains and forests.</span></span>

<span data-ttu-id="e1223-169">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-169">**Cons**</span></span>

- <span data-ttu-id="e1223-170">Требует Windows Server 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1223-170">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="e1223-171">Не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="e1223-171">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="e1223-172">Требует права на обновление объектов и имен субъектов-служб (SPN).</span><span class="sxs-lookup"><span data-stu-id="e1223-172">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="e1223-173">Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы.</span><span class="sxs-lookup"><span data-stu-id="e1223-173">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="e1223-174">Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="e1223-174">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="e1223-175">Пример</span><span class="sxs-lookup"><span data-stu-id="e1223-175">Example</span></span>

<span data-ttu-id="e1223-176">Рассмотрим пример PowerShell, который настраивает на _ServerC_ ограниченное делегирование на основе ресурсов, разрешающее использовать делегированные учетные данные с _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="e1223-176">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="e1223-177">В этом примере предполагается, что все серверы работают под управлением Windows Server 2012 или более поздней версии и существует по меньшей мере один контроллер домена Windows Server 2012 в каждом домене, к которому относятся какие-либо из серверов.</span><span class="sxs-lookup"><span data-stu-id="e1223-177">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="e1223-178">Перед настройкой ограниченного делегирования следует добавить компонент `RSAT-AD-PowerShell`, чтобы установить модуль Active Directory PowerShell, а затем импортировать этот модуль в сеанс:</span><span class="sxs-lookup"><span data-stu-id="e1223-178">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="e1223-179">Сейчас параметр несколько доступных командлетов имеют параметр **PrincipalsAllowedToDelegateToAccount**:</span><span class="sxs-lookup"><span data-stu-id="e1223-179">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="e1223-180">Параметр **PrincipalsAllowedToDelegateToAccount** задает атрибут объекта Active Directory **msDS-AllowedToActOnBehalfOfOtherIdentity**, содержащий список управления доступом (ACL), который указывает, какие учетные записи имеют разрешение на делегирование учетных данных для связанной учетной записи (в нашем примере это будет учетная запись компьютера для _ServerA_).</span><span class="sxs-lookup"><span data-stu-id="e1223-180">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="e1223-181">Теперь давайте настроим переменные, которые будем использовать для представления серверов:</span><span class="sxs-lookup"><span data-stu-id="e1223-181">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="e1223-182">WinRM (и поэтому удаленное взаимодействие PowerShell) по умолчанию выполняется как учетная запись компьютера.</span><span class="sxs-lookup"><span data-stu-id="e1223-182">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="e1223-183">Это можно проверить, просмотрев свойство **StartName** службы `winrm`:</span><span class="sxs-lookup"><span data-stu-id="e1223-183">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="e1223-184">Чтобы _ServerC_ разрешал делегирование из сеанса удаленного взаимодействия PowerShell на _ServerB_, мы должны задать в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на _ServerC_ объект компьютера _ServerB_:</span><span class="sxs-lookup"><span data-stu-id="e1223-184">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="e1223-185">[Центр распространения ключей](/windows/win32/secauthn/key-distribution-center) Kerberos кэширует отклоненные попытки доступа (негативный кэш) в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="e1223-185">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="e1223-186">Если сервер _ServerB_ ранее пытался получить доступ к серверу _ServerC_, потребуется очистить кэш на сервере _ServerB_, вызвав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e1223-186">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="e1223-187">Можно также перезагрузить компьютер или подождать не менее 15 минут для очистки кэша.</span><span class="sxs-lookup"><span data-stu-id="e1223-187">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="e1223-188">После очистки кэша можно запустить код с _ServerA_ через _ServerB_ и до _ServerC_:</span><span class="sxs-lookup"><span data-stu-id="e1223-188">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

<span data-ttu-id="e1223-189">В этом примере переменная `$using` используется, чтобы сделать переменную `$ServerC` видимой для сервера _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="e1223-189">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="e1223-190">Дополнительные сведения о переменной `$using` см. в разделе [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span><span class="sxs-lookup"><span data-stu-id="e1223-190">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="e1223-191">Чтобы разрешить нескольким серверам делегировать учетные данные серверу _ServerC_, задайте в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ в массив:</span><span class="sxs-lookup"><span data-stu-id="e1223-191">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

<span data-ttu-id="e1223-192">Если вы хотите сделать второй прыжок между доменами, добавьте полное доменное имя (FQDN) контроллера домена для того домена, к которому принадлежит _ServerB_:</span><span class="sxs-lookup"><span data-stu-id="e1223-192">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="e1223-193">Чтобы запретить нескольким серверам делегировать учетные данные серверу ServerC, задайте для параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ значение `$null`:</span><span class="sxs-lookup"><span data-stu-id="e1223-193">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="e1223-194">Информация об ограниченном делегировании Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="e1223-194">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="e1223-195">[Новые возможности проверки подлинности Kerberos][whats-new]</span><span class="sxs-lookup"><span data-stu-id="e1223-195">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="e1223-196">[Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 1][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="e1223-196">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="e1223-197">[Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 2][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="e1223-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="e1223-198">[Основные сведения об ограниченном делегировании Kerberos для развертывания прокси приложения Azure Active Directory со встроенной проверкой подлинности Windows][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="e1223-198">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="e1223-199">[[MS-ADA2] Атрибуты схемы Active Directory на букву M — 2.210. Атрибут msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="e1223-199">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="e1223-200">[[MS-SFU] Расширения протокола Kerberos: Service for User и протокол ограниченного делегирования — 1.3.2. S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="e1223-200">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="e1223-201">[Удаленное администрирование без ограниченного делегирования с помощью PrincipalsAllowedToDelegateToAccount][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="e1223-201">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="e1223-202">Делегирование Kerberos (без ограничений)</span><span class="sxs-lookup"><span data-stu-id="e1223-202">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="e1223-203">Для выполнения второго прыжка можно также использовать делегирование Kerberos без ограничений.</span><span class="sxs-lookup"><span data-stu-id="e1223-203">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="e1223-204">Как и во всех сценариях Kerberos, учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="e1223-204">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="e1223-205">Этот метод не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="e1223-205">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="e1223-206">Этот метод не позволяет контролировать, где используются делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e1223-206">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="e1223-207">Он менее безопасен, чем CredSSP.</span><span class="sxs-lookup"><span data-stu-id="e1223-207">It is less secure than CredSSP.</span></span> <span data-ttu-id="e1223-208">Этот метод следует использовать только для сценариев тестирования.</span><span class="sxs-lookup"><span data-stu-id="e1223-208">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="e1223-209">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="e1223-209">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="e1223-210">JEA позволяет ограничить команды, доступные администратору во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1223-210">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="e1223-211">Это позволяет решить проблему второго прыжка.</span><span class="sxs-lookup"><span data-stu-id="e1223-211">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="e1223-212">Сведения о JEA см. в разделе [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span><span class="sxs-lookup"><span data-stu-id="e1223-212">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="e1223-213">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-213">**Pros**</span></span>

- <span data-ttu-id="e1223-214">При использовании виртуальной учетной записи обслуживание паролей не требуется.</span><span class="sxs-lookup"><span data-stu-id="e1223-214">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="e1223-215">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-215">**Cons**</span></span>

- <span data-ttu-id="e1223-216">Требуется WMF 5.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1223-216">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="e1223-217">Требует настройки на каждом промежуточном сервере (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="e1223-217">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="e1223-218">PSSessionConfiguration с использованием RunAs</span><span class="sxs-lookup"><span data-stu-id="e1223-218">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="e1223-219">Можно создать конфигурацию сеанса на сервере _ServerB_ и задать ее параметр **RunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="e1223-219">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="e1223-220">Сведения об использовании **PSSessionConfiguration** и **RunAs** для решения проблемы второго прыжка см. в статье [Another solution to multi-hop PowerShell remoting][pssessionconfig] (Другое решение для удаленного взаимодействия PowerShell с несколькими прыжками).</span><span class="sxs-lookup"><span data-stu-id="e1223-220">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="e1223-221">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-221">**Pros**</span></span>

- <span data-ttu-id="e1223-222">Работает для любого сервера с WMF 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1223-222">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="e1223-223">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-223">**Cons**</span></span>

- <span data-ttu-id="e1223-224">Требует настройки **PSSessionConfiguration** и **RunAs** на каждом промежуточном сервере (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="e1223-224">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="e1223-225">Требуется обслуживание паролей при использовании учетной записи **запуска от имени** домена.</span><span class="sxs-lookup"><span data-stu-id="e1223-225">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="e1223-226">Передача учетных данных внутри блока сценария Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e1223-226">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="e1223-227">Можно передать учетные данные внутри параметра **ScriptBlock** вызова командлета [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="e1223-227">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="e1223-228">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="e1223-228">**Pros**</span></span>

- <span data-ttu-id="e1223-229">Не требуется специальной настройки серверов.</span><span class="sxs-lookup"><span data-stu-id="e1223-229">Does not require special server configuration.</span></span>
- <span data-ttu-id="e1223-230">Работает на любом сервере с WMF 2.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e1223-230">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="e1223-231">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="e1223-231">**Cons**</span></span>

- <span data-ttu-id="e1223-232">Требует внимательного составления кода.</span><span class="sxs-lookup"><span data-stu-id="e1223-232">Requires an awkward code technique.</span></span>
- <span data-ttu-id="e1223-233">При использовании WMF 2.0 требуется использовать иной синтаксис для передачи аргументов в удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="e1223-233">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="e1223-234">Пример</span><span class="sxs-lookup"><span data-stu-id="e1223-234">Example</span></span>

<span data-ttu-id="e1223-235">Следующий пример показывает, как передать учетные данные внутри блока сценария **Invoke-Command**:</span><span class="sxs-lookup"><span data-stu-id="e1223-235">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="e1223-236">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1223-236">See also</span></span>

[<span data-ttu-id="e1223-237">Вопросы обеспечения безопасности для удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1223-237">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group

---
ms.date: 05/14/2020
keywords: powershell,командлет
title: Выполнение второго прыжка при удаленном взаимодействии PowerShell
description: В этой статье объясняются различные методы настройки проверки подлинности второго прыжка для удаленного взаимодействия PowerShell, включая возможные последствия и рекомендации по безопасности.
ms.openlocfilehash: 905b27b4e6c612249c945a741bbe0d2ba9ae28aa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501377"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="17b9d-104">Выполнение второго прыжка при удаленном взаимодействии PowerShell</span><span class="sxs-lookup"><span data-stu-id="17b9d-104">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="17b9d-105">"Проблема второго прыжка" относится к ситуации, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="17b9d-105">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="17b9d-106">Вы вошли на сервер _ServerA_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-106">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="17b9d-107">С сервера _ServerA_ вы запускаете удаленный сеанс PowerShell для подключения к серверу _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-107">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="17b9d-108">Команда, запущенная вами на сервере _ServerB_ через сеанс удаленного взаимодействия PowerShell, пытается получить доступ к ресурсу на сервере _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-108">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="17b9d-109">Доступ к ресурсу на _ServerC_ запрещен, так как учетные данные, используемые вами для создания сеанса удаленного взаимодействия PowerShell, не передаются с сервера _ServerB_ на сервер _ServerC_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-109">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="17b9d-110">Существует несколько способов для решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="17b9d-110">There are several ways to address this problem.</span></span> <span data-ttu-id="17b9d-111">В следующей таблице перечислены методы в порядке предпочтения.</span><span class="sxs-lookup"><span data-stu-id="17b9d-111">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="17b9d-112">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="17b9d-112">Configuration</span></span>                       |                                  <span data-ttu-id="17b9d-113">Примечание</span><span class="sxs-lookup"><span data-stu-id="17b9d-113">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="17b9d-114">CredSSP</span><span class="sxs-lookup"><span data-stu-id="17b9d-114">CredSSP</span></span>                                                  | <span data-ttu-id="17b9d-115">Сбалансированное сочетание простоты использования и безопасности</span><span class="sxs-lookup"><span data-stu-id="17b9d-115">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="17b9d-116">Ограниченное делегирование Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="17b9d-116">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="17b9d-117">Более высокая безопасность с простой настройкой</span><span class="sxs-lookup"><span data-stu-id="17b9d-117">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="17b9d-118">Ограниченное делегирование Kerberos</span><span class="sxs-lookup"><span data-stu-id="17b9d-118">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="17b9d-119">Высокий уровень безопасности, но с необходимостью прав администратора домена</span><span class="sxs-lookup"><span data-stu-id="17b9d-119">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="17b9d-120">Делегирование Kerberos (без ограничений)</span><span class="sxs-lookup"><span data-stu-id="17b9d-120">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="17b9d-121">Не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="17b9d-121">Not recommended</span></span>                                                        |
| <span data-ttu-id="17b9d-122">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="17b9d-122">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="17b9d-123">Потенциально наилучшая безопасность, но с необходимостью тщательной настройки</span><span class="sxs-lookup"><span data-stu-id="17b9d-123">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="17b9d-124">PSSessionConfiguration с использованием RunAs</span><span class="sxs-lookup"><span data-stu-id="17b9d-124">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="17b9d-125">Более простая настройка, но с необходимостью управления учетными данными</span><span class="sxs-lookup"><span data-stu-id="17b9d-125">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="17b9d-126">Передача учетных данных внутри блока сценария `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="17b9d-126">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="17b9d-127">Максимальная простота использования, но с необходимостью указания учетных данных</span><span class="sxs-lookup"><span data-stu-id="17b9d-127">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="17b9d-128">CredSSP</span><span class="sxs-lookup"><span data-stu-id="17b9d-128">CredSSP</span></span>

<span data-ttu-id="17b9d-129">Для проверки подлинности можно использовать [протокол CredSSP][credssp].</span><span class="sxs-lookup"><span data-stu-id="17b9d-129">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="17b9d-130">Протокол CredSSP кэширует учетные данные на удаленном сервере (_ServerB_), что делает их уязвимыми для атак, направленных на кражу учетных данных.</span><span class="sxs-lookup"><span data-stu-id="17b9d-130">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="17b9d-131">Если безопасность удаленного компьютера нарушена, злоумышленник получает доступ к учетным данным пользователя.</span><span class="sxs-lookup"><span data-stu-id="17b9d-131">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="17b9d-132">Протокол CredSSP по умолчанию отключен на компьютерах клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="17b9d-132">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="17b9d-133">Включать протокол CredSSP следует только в самых надежных средах.</span><span class="sxs-lookup"><span data-stu-id="17b9d-133">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="17b9d-134">Например, при подключении администратора домена к контроллеру домена, так как контроллер домена является высоконадежным.</span><span class="sxs-lookup"><span data-stu-id="17b9d-134">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="17b9d-135">Дополнительные сведения о вопросах безопасности при использовании протокола CredSSP для удаленного взаимодействия PowerShell см. в статье [Accidental Sabotage: Beware of CredSSP][beware] (Непреднамеренный саботаж: берегитесь CredSSP).</span><span class="sxs-lookup"><span data-stu-id="17b9d-135">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="17b9d-136">Дополнительные сведения об атаках, направленных на хищение учетных данных, см. в техническом документе [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span><span class="sxs-lookup"><span data-stu-id="17b9d-136">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="17b9d-137">См. пример того, как [включить и использовать CredSSP для удаленного взаимодействия PowerShell][credssp-psblog].</span><span class="sxs-lookup"><span data-stu-id="17b9d-137">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="17b9d-138">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-138">**Pros**</span></span>

- <span data-ttu-id="17b9d-139">Это работает для всех серверов с Windows Server 2008 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="17b9d-139">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="17b9d-140">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-140">**Cons**</span></span>

- <span data-ttu-id="17b9d-141">Имеет уязвимости.</span><span class="sxs-lookup"><span data-stu-id="17b9d-141">Has security vulnerabilities.</span></span>
- <span data-ttu-id="17b9d-142">Требует настройки как клиентских, так и серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="17b9d-142">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="17b9d-143">Не работает с группой "Защищенные пользователи".</span><span class="sxs-lookup"><span data-stu-id="17b9d-143">Does not work with the Protected Users group.</span></span> <span data-ttu-id="17b9d-144">Дополнительные сведения см. в разделе [Группа безопасности "Защищенные пользователи"][protected-users].</span><span class="sxs-lookup"><span data-stu-id="17b9d-144">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="17b9d-145">Ограниченное делегирование Kerberos</span><span class="sxs-lookup"><span data-stu-id="17b9d-145">Kerberos constrained delegation</span></span>

<span data-ttu-id="17b9d-146">Для выполнения второго прыжка можно использовать устаревшее ограниченное делегирование (не на основе ресурсов).</span><span class="sxs-lookup"><span data-stu-id="17b9d-146">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="17b9d-147">Настройте ограниченное делегирование Kerberos с параметром "Использовать любой протокол проверки подлинности", чтобы разрешить переход протокола.</span><span class="sxs-lookup"><span data-stu-id="17b9d-147">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="17b9d-148">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-148">**Pros**</span></span>

- <span data-ttu-id="17b9d-149">Не требует специального кода.</span><span class="sxs-lookup"><span data-stu-id="17b9d-149">Requires no special coding</span></span>
- <span data-ttu-id="17b9d-150">Учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="17b9d-150">Credentials are not stored.</span></span>

<span data-ttu-id="17b9d-151">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-151">**Cons**</span></span>

- <span data-ttu-id="17b9d-152">Не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="17b9d-152">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="17b9d-153">Для настройки требуются права администратора домена.</span><span class="sxs-lookup"><span data-stu-id="17b9d-153">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="17b9d-154">Требует настройки для объекта Active Directory удаленного сервера (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="17b9d-154">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="17b9d-155">Ограничен одним доменом.</span><span class="sxs-lookup"><span data-stu-id="17b9d-155">Limited to one domain.</span></span> <span data-ttu-id="17b9d-156">Не может использоваться между доменами или лесами.</span><span class="sxs-lookup"><span data-stu-id="17b9d-156">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="17b9d-157">Требует права на обновление объектов и имен субъектов-служб (SPN).</span><span class="sxs-lookup"><span data-stu-id="17b9d-157">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="17b9d-158">_ServerB_ может получить билет Kerberos для _ServerC_ от имени пользователя без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="17b9d-158">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="17b9d-159">Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы.</span><span class="sxs-lookup"><span data-stu-id="17b9d-159">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="17b9d-160">Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="17b9d-160">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="17b9d-161">Ограниченное делегирование Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="17b9d-161">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="17b9d-162">С помощью ограниченного делегирования Kerberos на основе ресурсов (которое впервые появилось в Windows Server 2012) можно настроить делегирование учетных данных на объект сервера, где находятся ресурсы.</span><span class="sxs-lookup"><span data-stu-id="17b9d-162">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="17b9d-163">В описанном выше сценарии второго прыжка вы настраиваете сервер _ServerC_, чтобы указать, откуда он будет принимать делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="17b9d-163">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="17b9d-164">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-164">**Pros**</span></span>

- <span data-ttu-id="17b9d-165">Учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="17b9d-165">Credentials are not stored.</span></span>
- <span data-ttu-id="17b9d-166">Настраивается с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17b9d-166">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="17b9d-167">Не требует написания специального кода.</span><span class="sxs-lookup"><span data-stu-id="17b9d-167">No special coding required.</span></span>
- <span data-ttu-id="17b9d-168">Не требует для настройки доступ с правами администратора домена.</span><span class="sxs-lookup"><span data-stu-id="17b9d-168">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="17b9d-169">Работает между доменами и лесами.</span><span class="sxs-lookup"><span data-stu-id="17b9d-169">Works across domains and forests.</span></span>

<span data-ttu-id="17b9d-170">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-170">**Cons**</span></span>

- <span data-ttu-id="17b9d-171">Требует Windows Server 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="17b9d-171">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="17b9d-172">Не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="17b9d-172">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="17b9d-173">Требует права на обновление объектов и имен субъектов-служб (SPN).</span><span class="sxs-lookup"><span data-stu-id="17b9d-173">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="17b9d-174">Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы.</span><span class="sxs-lookup"><span data-stu-id="17b9d-174">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="17b9d-175">Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].</span><span class="sxs-lookup"><span data-stu-id="17b9d-175">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="17b9d-176">Пример</span><span class="sxs-lookup"><span data-stu-id="17b9d-176">Example</span></span>

<span data-ttu-id="17b9d-177">Рассмотрим пример PowerShell, который настраивает на _ServerC_ ограниченное делегирование на основе ресурсов, разрешающее использовать делегированные учетные данные с _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-177">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="17b9d-178">В этом примере предполагается, что все серверы работают под управлением Windows Server 2012 или более поздней версии и существует по меньшей мере один контроллер домена Windows Server 2012 в каждом домене, к которому относятся какие-либо из серверов.</span><span class="sxs-lookup"><span data-stu-id="17b9d-178">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="17b9d-179">Перед настройкой ограниченного делегирования следует добавить компонент `RSAT-AD-PowerShell`, чтобы установить модуль Active Directory PowerShell, а затем импортировать этот модуль в сеанс:</span><span class="sxs-lookup"><span data-stu-id="17b9d-179">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="17b9d-180">Сейчас параметр несколько доступных командлетов имеют параметр **PrincipalsAllowedToDelegateToAccount**:</span><span class="sxs-lookup"><span data-stu-id="17b9d-180">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

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

<span data-ttu-id="17b9d-181">Параметр **PrincipalsAllowedToDelegateToAccount** задает атрибут объекта Active Directory **msDS-AllowedToActOnBehalfOfOtherIdentity**, содержащий список управления доступом (ACL), который указывает, какие учетные записи имеют разрешение на делегирование учетных данных для связанной учетной записи (в нашем примере это будет учетная запись компьютера для _ServerA_).</span><span class="sxs-lookup"><span data-stu-id="17b9d-181">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="17b9d-182">Теперь давайте настроим переменные, которые будем использовать для представления серверов:</span><span class="sxs-lookup"><span data-stu-id="17b9d-182">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="17b9d-183">WinRM (и поэтому удаленное взаимодействие PowerShell) по умолчанию выполняется как учетная запись компьютера.</span><span class="sxs-lookup"><span data-stu-id="17b9d-183">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="17b9d-184">Это можно проверить, просмотрев свойство **StartName** службы `winrm`:</span><span class="sxs-lookup"><span data-stu-id="17b9d-184">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="17b9d-185">Чтобы _ServerC_ разрешал делегирование из сеанса удаленного взаимодействия PowerShell на _ServerB_, мы должны задать в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на _ServerC_ объект компьютера _ServerB_:</span><span class="sxs-lookup"><span data-stu-id="17b9d-185">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="17b9d-186">[Центр распространения ключей](/windows/win32/secauthn/key-distribution-center) Kerberos кэширует отклоненные попытки доступа (негативный кэш) в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="17b9d-186">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="17b9d-187">Если сервер _ServerB_ ранее пытался получить доступ к серверу _ServerC_, потребуется очистить кэш на сервере _ServerB_, вызвав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="17b9d-187">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="17b9d-188">Можно также перезагрузить компьютер или подождать не менее 15 минут для очистки кэша.</span><span class="sxs-lookup"><span data-stu-id="17b9d-188">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="17b9d-189">После очистки кэша можно запустить код с _ServerA_ через _ServerB_ и до _ServerC_:</span><span class="sxs-lookup"><span data-stu-id="17b9d-189">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

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

<span data-ttu-id="17b9d-190">В этом примере переменная `$using` используется, чтобы сделать переменную `$ServerC` видимой для сервера _ServerB_.</span><span class="sxs-lookup"><span data-stu-id="17b9d-190">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="17b9d-191">Дополнительные сведения о переменной `$using` см. в разделе [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span><span class="sxs-lookup"><span data-stu-id="17b9d-191">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="17b9d-192">Чтобы разрешить нескольким серверам делегировать учетные данные серверу _ServerC_, задайте в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ в массив:</span><span class="sxs-lookup"><span data-stu-id="17b9d-192">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

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

<span data-ttu-id="17b9d-193">Если вы хотите сделать второй прыжок между доменами, добавьте полное доменное имя (FQDN) контроллера домена для того домена, к которому принадлежит _ServerB_:</span><span class="sxs-lookup"><span data-stu-id="17b9d-193">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="17b9d-194">Чтобы запретить нескольким серверам делегировать учетные данные серверу ServerC, задайте для параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ значение `$null`:</span><span class="sxs-lookup"><span data-stu-id="17b9d-194">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="17b9d-195">Информация об ограниченном делегировании Kerberos на основе ресурсов</span><span class="sxs-lookup"><span data-stu-id="17b9d-195">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="17b9d-196">[Новые возможности проверки подлинности Kerberos][whats-new]</span><span class="sxs-lookup"><span data-stu-id="17b9d-196">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="17b9d-197">[Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 1][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="17b9d-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="17b9d-198">[Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 2][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="17b9d-198">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="17b9d-199">[Основные сведения об ограниченном делегировании Kerberos для развертывания прокси приложения Azure Active Directory со встроенной проверкой подлинности Windows][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="17b9d-199">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="17b9d-200">[[MS-ADA2] Атрибуты схемы Active Directory на букву M — 2.210. Атрибут msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="17b9d-200">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="17b9d-201">[[MS-SFU] Расширения протокола Kerberos: Service for User и протокол ограниченного делегирования — 1.3.2. S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="17b9d-201">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="17b9d-202">[Удаленное администрирование без ограниченного делегирования с помощью PrincipalsAllowedToDelegateToAccount][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="17b9d-202">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="17b9d-203">Делегирование Kerberos (без ограничений)</span><span class="sxs-lookup"><span data-stu-id="17b9d-203">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="17b9d-204">Для выполнения второго прыжка можно также использовать делегирование Kerberos без ограничений.</span><span class="sxs-lookup"><span data-stu-id="17b9d-204">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="17b9d-205">Как и во всех сценариях Kerberos, учетные данные не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="17b9d-205">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="17b9d-206">Этот метод не поддерживает второй прыжок для WinRM.</span><span class="sxs-lookup"><span data-stu-id="17b9d-206">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="17b9d-207">Этот метод не позволяет контролировать, где используются делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="17b9d-207">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="17b9d-208">Он менее безопасен, чем CredSSP.</span><span class="sxs-lookup"><span data-stu-id="17b9d-208">It is less secure than CredSSP.</span></span> <span data-ttu-id="17b9d-209">Этот метод следует использовать только для сценариев тестирования.</span><span class="sxs-lookup"><span data-stu-id="17b9d-209">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="17b9d-210">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="17b9d-210">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="17b9d-211">JEA позволяет ограничить команды, доступные администратору во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17b9d-211">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="17b9d-212">Это позволяет решить проблему второго прыжка.</span><span class="sxs-lookup"><span data-stu-id="17b9d-212">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="17b9d-213">Сведения о JEA см. в разделе [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span><span class="sxs-lookup"><span data-stu-id="17b9d-213">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="17b9d-214">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-214">**Pros**</span></span>

- <span data-ttu-id="17b9d-215">При использовании виртуальной учетной записи обслуживание паролей не требуется.</span><span class="sxs-lookup"><span data-stu-id="17b9d-215">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="17b9d-216">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-216">**Cons**</span></span>

- <span data-ttu-id="17b9d-217">Требуется WMF 5.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="17b9d-217">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="17b9d-218">Требует настройки на каждом промежуточном сервере (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="17b9d-218">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="17b9d-219">PSSessionConfiguration с использованием RunAs</span><span class="sxs-lookup"><span data-stu-id="17b9d-219">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="17b9d-220">Можно создать конфигурацию сеанса на сервере _ServerB_ и задать ее параметр **RunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="17b9d-220">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="17b9d-221">Сведения об использовании **PSSessionConfiguration** и **RunAs** для решения проблемы второго прыжка см. в статье [Another solution to multi-hop PowerShell remoting][pssessionconfig] (Другое решение для удаленного взаимодействия PowerShell с несколькими прыжками).</span><span class="sxs-lookup"><span data-stu-id="17b9d-221">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="17b9d-222">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-222">**Pros**</span></span>

- <span data-ttu-id="17b9d-223">Работает для любого сервера с WMF 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="17b9d-223">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="17b9d-224">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-224">**Cons**</span></span>

- <span data-ttu-id="17b9d-225">Требует настройки **PSSessionConfiguration** и **RunAs** на каждом промежуточном сервере (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="17b9d-225">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="17b9d-226">Требуется обслуживание паролей при использовании учетной записи **запуска от имени** домена.</span><span class="sxs-lookup"><span data-stu-id="17b9d-226">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="17b9d-227">Передача учетных данных внутри блока сценария Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="17b9d-227">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="17b9d-228">Можно передать учетные данные внутри параметра **ScriptBlock** вызова командлета [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="17b9d-228">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="17b9d-229">**Преимущества**</span><span class="sxs-lookup"><span data-stu-id="17b9d-229">**Pros**</span></span>

- <span data-ttu-id="17b9d-230">Не требуется специальной настройки серверов.</span><span class="sxs-lookup"><span data-stu-id="17b9d-230">Does not require special server configuration.</span></span>
- <span data-ttu-id="17b9d-231">Работает на любом сервере с WMF 2.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="17b9d-231">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="17b9d-232">**Недостатки**</span><span class="sxs-lookup"><span data-stu-id="17b9d-232">**Cons**</span></span>

- <span data-ttu-id="17b9d-233">Требует внимательного составления кода.</span><span class="sxs-lookup"><span data-stu-id="17b9d-233">Requires an awkward code technique.</span></span>
- <span data-ttu-id="17b9d-234">При использовании WMF 2.0 требуется использовать иной синтаксис для передачи аргументов в удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="17b9d-234">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="17b9d-235">Пример</span><span class="sxs-lookup"><span data-stu-id="17b9d-235">Example</span></span>

<span data-ttu-id="17b9d-236">Следующий пример показывает, как передать учетные данные внутри блока сценария **Invoke-Command**:</span><span class="sxs-lookup"><span data-stu-id="17b9d-236">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="17b9d-237">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="17b9d-237">See also</span></span>

[<span data-ttu-id="17b9d-238">Вопросы обеспечения безопасности для удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="17b9d-238">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

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

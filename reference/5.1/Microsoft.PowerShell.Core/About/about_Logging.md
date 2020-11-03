---
description: PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов.
keywords: powershell
Locale: en-US
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging
ms.openlocfilehash: 5d061b38b5b0fa45cf0a86c2f5b7e0efcb8d1f7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232017"
---
# <a name="about-logging"></a><span data-ttu-id="ad683-104">Сведения о ведении журнала</span><span class="sxs-lookup"><span data-stu-id="ad683-104">About Logging</span></span>

## <a name="short-description"></a><span data-ttu-id="ad683-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ad683-105">Short description</span></span>

<span data-ttu-id="ad683-106">PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов.</span><span class="sxs-lookup"><span data-stu-id="ad683-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="ad683-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ad683-107">Long description</span></span>

<span data-ttu-id="ad683-108">PowerShell регистрирует сведения об операциях PowerShell, таких как запуск и остановка подсистемы и поставщиков, а также выполнение команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad683-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="ad683-109">В Windows PowerShell версии 3,0, 4,0, 5,0 и 5,1 включены командлеты **EventLog** для журналов событий Windows.</span><span class="sxs-lookup"><span data-stu-id="ad683-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="ad683-110">В этих версиях для вывода списка типов командлетов **EventLog** : `Get-Command -Noun EventLog` .</span><span class="sxs-lookup"><span data-stu-id="ad683-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="ad683-111">Дополнительные сведения см. в документации по командлетам и about_EventLogs для вашей версии Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad683-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="ad683-112">Просмотр записей журнала событий PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="ad683-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="ad683-113">Журналы PowerShell можно просмотреть с помощью Просмотр событий Windows.</span><span class="sxs-lookup"><span data-stu-id="ad683-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="ad683-114">Журнал событий находится в группе Журналы приложений и служб и называется `Microsoft-Windows-PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="ad683-114">The event log is located in the Application and Services Logs group and is named `Microsoft-Windows-PowerShell`.</span></span> <span data-ttu-id="ad683-115">Связанным поставщиком ETW `GUID` является `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}` .</span><span class="sxs-lookup"><span data-stu-id="ad683-115">The associated ETW provider `GUID` is `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}`.</span></span>

<span data-ttu-id="ad683-116">Если включено ведение журнала блокировки сценариев, PowerShell регистрирует в журнале следующие события `Microsoft-Windows-PowerShell/Operational` :</span><span class="sxs-lookup"><span data-stu-id="ad683-116">When Script Block Logging is enabled, PowerShell logs the following events to the `Microsoft-Windows-PowerShell/Operational` log:</span></span>

|<span data-ttu-id="ad683-117">Поле</span><span class="sxs-lookup"><span data-stu-id="ad683-117">Field</span></span>| <span data-ttu-id="ad683-118">Значение</span><span class="sxs-lookup"><span data-stu-id="ad683-118">Value</span></span>|
|-|-|
|<span data-ttu-id="ad683-119">EventId</span><span class="sxs-lookup"><span data-stu-id="ad683-119">EventId</span></span>|`4104` / `0x1008`|
|<span data-ttu-id="ad683-120">Канал</span><span class="sxs-lookup"><span data-stu-id="ad683-120">Channel</span></span>|`Operational`|
|<span data-ttu-id="ad683-121">Level</span><span class="sxs-lookup"><span data-stu-id="ad683-121">Level</span></span>|`Verbose`|
|<span data-ttu-id="ad683-122">Код операции</span><span class="sxs-lookup"><span data-stu-id="ad683-122">Opcode</span></span>|`Create`|
|<span data-ttu-id="ad683-123">Задача</span><span class="sxs-lookup"><span data-stu-id="ad683-123">Task</span></span>|`CommandStart`|
|<span data-ttu-id="ad683-124">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="ad683-124">Keyword</span></span>|`Runspace`|

## <a name="enabling-script-block-logging"></a><span data-ttu-id="ad683-125">Включение ведения журнала блоков сценариев</span><span class="sxs-lookup"><span data-stu-id="ad683-125">Enabling Script Block Logging</span></span>

<span data-ttu-id="ad683-126">При включении ведения журнала блока сценариев PowerShell записывает содержимое всех блоков сценариев, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="ad683-126">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="ad683-127">После включения все новые сеансы PowerShell регистрируют эти сведения.</span><span class="sxs-lookup"><span data-stu-id="ad683-127">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="ad683-128">Рекомендуется включить ведение журнала защищенных событий, как описано ниже, при использовании журнала блокировки сценариев для любых операций, кроме целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="ad683-128">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="ad683-129">Ведение журнала блока скрипта можно включить с помощью групповая политика или параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="ad683-129">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="ad683-130">Использование групповой политики</span><span class="sxs-lookup"><span data-stu-id="ad683-130">Using Group Policy</span></span>

<span data-ttu-id="ad683-131">Чтобы включить автоматическую транскрипцию, включите эту `Turn on PowerShell Script Block
Logging` функцию в групповая политика с помощью `Administrative Templates -> Windows
Components -> Windows PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="ad683-131">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="ad683-132">Использование реестра</span><span class="sxs-lookup"><span data-stu-id="ad683-132">Using the Registry</span></span>

<span data-ttu-id="ad683-133">Выполните следующую функцию:</span><span class="sxs-lookup"><span data-stu-id="ad683-133">Run the following function:</span></span>

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a><span data-ttu-id="ad683-134">Ведение журнала защищенных событий</span><span class="sxs-lookup"><span data-stu-id="ad683-134">Protected Event Logging</span></span>

<span data-ttu-id="ad683-135">Увеличение уровня ведения журналов в системе повышает вероятность того, что содержимое журнала может содержать конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="ad683-135">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="ad683-136">Например, если включено ведение журнала сценариев, то учетные данные или другие конфиденциальные данные, используемые сценарием, могут быть записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="ad683-136">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="ad683-137">При компрометации компьютера, на котором зарегистрированы конфиденциальные данные, журналы могут предоставить злоумышленнику информацию, необходимую для расширения их доступности.</span><span class="sxs-lookup"><span data-stu-id="ad683-137">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="ad683-138">Для защиты этих сведений в Windows 10 появился журнал защищенных событий.</span><span class="sxs-lookup"><span data-stu-id="ad683-138">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="ad683-139">Защищенное ведение журнала событий позволяет участвующим приложениям шифровать конфиденциальные данные, записанные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="ad683-139">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="ad683-140">Позже вы сможете расшифровать и обработать эти журналы на более безопасном и централизованном сборщике журналов.</span><span class="sxs-lookup"><span data-stu-id="ad683-140">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="ad683-141">Содержимое журнала событий защищено с помощью стандартного синтаксиса сообщений (CMS) IETF.</span><span class="sxs-lookup"><span data-stu-id="ad683-141">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="ad683-142">CMS использует шифрование с открытым ключом.</span><span class="sxs-lookup"><span data-stu-id="ad683-142">CMS uses public key cryptography.</span></span> <span data-ttu-id="ad683-143">Ключи, используемые для шифрования содержимого и расшифровки содержимого, хранятся отдельно.</span><span class="sxs-lookup"><span data-stu-id="ad683-143">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="ad683-144">Открытый ключ может быть общим и не конфиденциальным.</span><span class="sxs-lookup"><span data-stu-id="ad683-144">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="ad683-145">Любое содержимое, зашифрованное с помощью этого открытого ключа, может быть расшифровано только закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="ad683-145">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="ad683-146">Дополнительные сведения о шифровании с открытым ключом см. в статье о [шифровании с открытым ключом Википедии](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="ad683-146">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="ad683-147">Чтобы включить политику защищенного ведения журнала событий, разверните открытый ключ для всех компьютеров, которые содержат данные журнала событий для защиты.</span><span class="sxs-lookup"><span data-stu-id="ad683-147">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="ad683-148">Соответствующий закрытый ключ используется для последующей обработки журналов событий в более безопасном расположении, например в центральном сборщике журналов событий или [SIEM][] агрегаторе.</span><span class="sxs-lookup"><span data-stu-id="ad683-148">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="ad683-149">Вы можете настроить SIEM в Azure.</span><span class="sxs-lookup"><span data-stu-id="ad683-149">You can set up SIEM in Azure.</span></span> <span data-ttu-id="ad683-150">Дополнительные сведения см. в разделе [Универсальная интеграция SIEM](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="ad683-150">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="ad683-151">Включение ведения журнала защищенных событий с помощью групповая политика</span><span class="sxs-lookup"><span data-stu-id="ad683-151">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="ad683-152">Чтобы включить ведение журнала защищенных событий, включите `Enable Protected Event Logging` функцию в групповая политика с помощью `Administrative Templates -> Windows Components
-> Event Logging` .</span><span class="sxs-lookup"><span data-stu-id="ad683-152">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="ad683-153">Для этого параметра требуется сертификат шифрования, который можно указать в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="ad683-153">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="ad683-154">Содержимое сертификата X. 509 в кодировке Base-64 (например, предложено `Export` параметром в диспетчере сертификатов).</span><span class="sxs-lookup"><span data-stu-id="ad683-154">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="ad683-155">Отпечаток сертификата, который можно найти в хранилище сертификатов локального компьютера (может быть развернут инфраструктурой PKI).</span><span class="sxs-lookup"><span data-stu-id="ad683-155">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="ad683-156">Полный путь к сертификату (может быть локальным или удаленным общим ресурсом).</span><span class="sxs-lookup"><span data-stu-id="ad683-156">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="ad683-157">Путь к каталогу, содержащему сертификат или сертификаты (может быть локальным или удаленным общим ресурсом).</span><span class="sxs-lookup"><span data-stu-id="ad683-157">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="ad683-158">Имя субъекта сертификата, который можно найти в хранилище сертификатов локального компьютера (может быть развернуто инфраструктурой PKI).</span><span class="sxs-lookup"><span data-stu-id="ad683-158">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="ad683-159">Итоговый сертификат должен иметь `Document Encryption` в качестве расширенного использования ключа ( `1.3.6.1.4.1.311.80.1` ), а `Data Encipherment` также значение или `Key
Encipherment` Использование ключей.</span><span class="sxs-lookup"><span data-stu-id="ad683-159">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="ad683-160">Закрытый ключ не должен быть развернут на компьютерах, регистрируемых в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="ad683-160">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="ad683-161">Он должен храниться в безопасном месте, где вы расшифровываете сообщения.</span><span class="sxs-lookup"><span data-stu-id="ad683-161">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="ad683-162">Расшифровка сообщений журнала защищенных событий</span><span class="sxs-lookup"><span data-stu-id="ad683-162">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="ad683-163">Следующий сценарий будет получен и расшифрован, предполагая, что у вас есть закрытый ключ:</span><span class="sxs-lookup"><span data-stu-id="ad683-163">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="ad683-164">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ad683-164">See also</span></span>

[<span data-ttu-id="ad683-165">PowerShell — Синяя команда</span><span class="sxs-lookup"><span data-stu-id="ad683-165">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="ad683-166">Универсальная интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="ad683-166">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management

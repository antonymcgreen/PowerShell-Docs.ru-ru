---
description: PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов в журнале событий Windows.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_windows?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging — Windows
ms.openlocfilehash: b36c45e0e8192a292dab88615cdd23f877068774
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354785"
---
# <a name="about-logging-windows"></a><span data-ttu-id="28fb6-104">Сведения о окнах ведения журнала</span><span class="sxs-lookup"><span data-stu-id="28fb6-104">About Logging Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="28fb6-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="28fb6-105">Short description</span></span>
<span data-ttu-id="28fb6-106">PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="28fb6-106">PowerShell logs internal operations from the engine, providers, and cmdlets to the Windows event log.</span></span>

## <a name="long-description"></a><span data-ttu-id="28fb6-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="28fb6-107">Long description</span></span>

<span data-ttu-id="28fb6-108">PowerShell регистрирует сведения об операциях PowerShell, таких как запуск и остановка подсистемы и поставщиков, а также выполнение команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28fb6-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="28fb6-109">В Windows PowerShell версии 3,0, 4,0, 5,0 и 5,1 включены командлеты **EventLog** для журналов событий Windows.</span><span class="sxs-lookup"><span data-stu-id="28fb6-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="28fb6-110">В этих версиях для вывода списка типов командлетов **EventLog** : `Get-Command -Noun EventLog` .</span><span class="sxs-lookup"><span data-stu-id="28fb6-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="28fb6-111">Дополнительные сведения см. в документации по командлетам и about_EventLogs для вашей версии Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28fb6-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="28fb6-112">Просмотр записей журнала событий PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="28fb6-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="28fb6-113">Журналы PowerShell можно просмотреть с помощью Просмотр событий Windows.</span><span class="sxs-lookup"><span data-stu-id="28fb6-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="28fb6-114">Журнал событий находится в группе Журналы приложений и служб и называется `PowerShellCore` .</span><span class="sxs-lookup"><span data-stu-id="28fb6-114">The event log is located in the Application and Services Logs group and is named `PowerShellCore`.</span></span> <span data-ttu-id="28fb6-115">Связанным поставщиком ETW `GUID` является `{f90714a8-5509-434a-bf6d-b1624c8a19a2}` .</span><span class="sxs-lookup"><span data-stu-id="28fb6-115">The associated ETW provider `GUID` is `{f90714a8-5509-434a-bf6d-b1624c8a19a2}`.</span></span>

<span data-ttu-id="28fb6-116">Если включено ведение журнала блокировки сценариев, PowerShell регистрирует в журнале следующие события `PowerShellCore/Operational` :</span><span class="sxs-lookup"><span data-stu-id="28fb6-116">When Script Block Logging is enabled, PowerShell logs the following events to the `PowerShellCore/Operational` log:</span></span>

|  <span data-ttu-id="28fb6-117">Поле</span><span class="sxs-lookup"><span data-stu-id="28fb6-117">Field</span></span>  |       <span data-ttu-id="28fb6-118">Значение</span><span class="sxs-lookup"><span data-stu-id="28fb6-118">Value</span></span>       |
| ------- | ----------------- |
| <span data-ttu-id="28fb6-119">EventId</span><span class="sxs-lookup"><span data-stu-id="28fb6-119">EventId</span></span> | `4104` / `0x1008` |
| <span data-ttu-id="28fb6-120">Channel</span><span class="sxs-lookup"><span data-stu-id="28fb6-120">Channel</span></span> | `Operational`     |
| <span data-ttu-id="28fb6-121">Level</span><span class="sxs-lookup"><span data-stu-id="28fb6-121">Level</span></span>   | `Verbose`         |
| <span data-ttu-id="28fb6-122">Код операции</span><span class="sxs-lookup"><span data-stu-id="28fb6-122">Opcode</span></span>  | `Create`          |
| <span data-ttu-id="28fb6-123">Задача</span><span class="sxs-lookup"><span data-stu-id="28fb6-123">Task</span></span>    | `CommandStart`    |
| <span data-ttu-id="28fb6-124">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="28fb6-124">Keyword</span></span> | `Runspace`        |

### <a name="registering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="28fb6-125">Регистрация поставщика событий PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="28fb6-125">Registering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="28fb6-126">В отличие от Linux или macOS, Windows требует регистрации поставщика событий, прежде чем события могут быть записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-126">Unlike Linux or macOS, Windows requires the event provider to be registered before events can be written to the event log.</span></span> <span data-ttu-id="28fb6-127">Чтобы включить поставщик событий PowerShell, выполните следующую команду в командной строке PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="28fb6-127">To enable the PowerShell event provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1
```

### <a name="unregistering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="28fb6-128">Отмена регистрации поставщика событий PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="28fb6-128">Unregistering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="28fb6-129">Регистрация поставщика событий помещает блокировку в двоичную библиотеку, используемую для расшифровки событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-129">Registering the event provider places a lock in the binary library used to decode events.</span></span> <span data-ttu-id="28fb6-130">Чтобы обновить эту библиотеку, необходимо отменить регистрацию поставщика, чтобы освободить эту блокировку.</span><span class="sxs-lookup"><span data-stu-id="28fb6-130">To update this library, the provider must be unregistered to release this lock.</span></span>

<span data-ttu-id="28fb6-131">Чтобы отменить регистрацию поставщика PowerShell, выполните следующую команду в командной строке PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="28fb6-131">To unregister the PowerShell provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1 -Unregister
```

<span data-ttu-id="28fb6-132">После обновления PowerShell выполните команду, `$PSHOME\RegisterManifest.ps1` чтобы зарегистрировать обновленный поставщик событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-132">After updating PowerShell, run `$PSHOME\RegisterManifest.ps1` to register the updated event provider.</span></span>

## <a name="enabling-script-block-logging"></a><span data-ttu-id="28fb6-133">Включение ведения журнала блоков сценариев</span><span class="sxs-lookup"><span data-stu-id="28fb6-133">Enabling Script Block Logging</span></span>

<span data-ttu-id="28fb6-134">При включении ведения журнала блока сценариев PowerShell записывает содержимое всех блоков сценариев, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="28fb6-134">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="28fb6-135">После включения все новые сеансы PowerShell регистрируют эти сведения.</span><span class="sxs-lookup"><span data-stu-id="28fb6-135">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="28fb6-136">Рекомендуется включить ведение журнала защищенных событий, как описано ниже, при использовании журнала блокировки сценариев для любых операций, кроме целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="28fb6-136">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="28fb6-137">Ведение журнала блока скрипта можно включить с помощью групповая политика или параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="28fb6-137">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="28fb6-138">Использование групповой политики</span><span class="sxs-lookup"><span data-stu-id="28fb6-138">Using Group Policy</span></span>

<span data-ttu-id="28fb6-139">Чтобы включить автоматическую транскрипцию, включите эту `Turn on PowerShell Script Block
Logging` функцию в групповая политика с помощью `Administrative Templates -> Windows
Components -> Windows PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="28fb6-139">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="28fb6-140">Использование реестра</span><span class="sxs-lookup"><span data-stu-id="28fb6-140">Using the Registry</span></span>

<span data-ttu-id="28fb6-141">Выполните следующую функцию:</span><span class="sxs-lookup"><span data-stu-id="28fb6-141">Run the following function:</span></span>

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

## <a name="protected-event-logging"></a><span data-ttu-id="28fb6-142">Ведение журнала защищенных событий</span><span class="sxs-lookup"><span data-stu-id="28fb6-142">Protected Event Logging</span></span>

<span data-ttu-id="28fb6-143">Увеличение уровня ведения журналов в системе повышает вероятность того, что содержимое журнала может содержать конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="28fb6-143">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="28fb6-144">Например, если включено ведение журнала сценариев, то учетные данные или другие конфиденциальные данные, используемые сценарием, могут быть записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-144">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="28fb6-145">При компрометации компьютера, на котором зарегистрированы конфиденциальные данные, журналы могут предоставить злоумышленнику информацию, необходимую для расширения их доступности.</span><span class="sxs-lookup"><span data-stu-id="28fb6-145">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="28fb6-146">Для защиты этих сведений в Windows 10 появился журнал защищенных событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-146">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="28fb6-147">Защищенное ведение журнала событий позволяет участвующим приложениям шифровать конфиденциальные данные, записанные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-147">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="28fb6-148">Позже вы сможете расшифровать и обработать эти журналы на более безопасном и централизованном сборщике журналов.</span><span class="sxs-lookup"><span data-stu-id="28fb6-148">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="28fb6-149">Содержимое журнала событий защищено с помощью стандартного синтаксиса сообщений (CMS) IETF.</span><span class="sxs-lookup"><span data-stu-id="28fb6-149">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="28fb6-150">CMS использует шифрование с открытым ключом.</span><span class="sxs-lookup"><span data-stu-id="28fb6-150">CMS uses public key cryptography.</span></span> <span data-ttu-id="28fb6-151">Ключи, используемые для шифрования содержимого и расшифровки содержимого, хранятся отдельно.</span><span class="sxs-lookup"><span data-stu-id="28fb6-151">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="28fb6-152">Открытый ключ может быть общим и не конфиденциальным.</span><span class="sxs-lookup"><span data-stu-id="28fb6-152">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="28fb6-153">Любое содержимое, зашифрованное с помощью этого открытого ключа, может быть расшифровано только закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="28fb6-153">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="28fb6-154">Дополнительные сведения о шифровании с открытым ключом см. в статье о [шифровании с открытым ключом Википедии](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="28fb6-154">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="28fb6-155">Чтобы включить политику защищенного ведения журнала событий, разверните открытый ключ для всех компьютеров, которые содержат данные журнала событий для защиты.</span><span class="sxs-lookup"><span data-stu-id="28fb6-155">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="28fb6-156">Соответствующий закрытый ключ используется для последующей обработки журналов событий в более безопасном расположении, например в центральном сборщике журналов событий или [SIEM][] агрегаторе.</span><span class="sxs-lookup"><span data-stu-id="28fb6-156">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="28fb6-157">Вы можете настроить SIEM в Azure.</span><span class="sxs-lookup"><span data-stu-id="28fb6-157">You can set up SIEM in Azure.</span></span> <span data-ttu-id="28fb6-158">Дополнительные сведения см. в разделе [Универсальная интеграция SIEM](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="28fb6-158">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="28fb6-159">Включение ведения журнала защищенных событий с помощью групповая политика</span><span class="sxs-lookup"><span data-stu-id="28fb6-159">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="28fb6-160">Чтобы включить ведение журнала защищенных событий, включите `Enable Protected Event Logging` функцию в групповая политика с помощью `Administrative Templates -> Windows Components
-> Event Logging` .</span><span class="sxs-lookup"><span data-stu-id="28fb6-160">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="28fb6-161">Для этого параметра требуется сертификат шифрования, который можно указать в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="28fb6-161">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="28fb6-162">Содержимое сертификата X. 509 в кодировке Base-64 (например, предложено `Export` параметром в диспетчере сертификатов).</span><span class="sxs-lookup"><span data-stu-id="28fb6-162">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="28fb6-163">Отпечаток сертификата, который можно найти в хранилище сертификатов локального компьютера (может быть развернут инфраструктурой PKI).</span><span class="sxs-lookup"><span data-stu-id="28fb6-163">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="28fb6-164">Полный путь к сертификату (может быть локальным или удаленным общим ресурсом).</span><span class="sxs-lookup"><span data-stu-id="28fb6-164">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="28fb6-165">Путь к каталогу, содержащему сертификат или сертификаты (может быть локальным или удаленным общим ресурсом).</span><span class="sxs-lookup"><span data-stu-id="28fb6-165">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="28fb6-166">Имя субъекта сертификата, который можно найти в хранилище сертификатов локального компьютера (может быть развернуто инфраструктурой PKI).</span><span class="sxs-lookup"><span data-stu-id="28fb6-166">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="28fb6-167">Итоговый сертификат должен иметь `Document Encryption` в качестве расширенного использования ключа ( `1.3.6.1.4.1.311.80.1` ), а `Data Encipherment` также значение или `Key
Encipherment` Использование ключей.</span><span class="sxs-lookup"><span data-stu-id="28fb6-167">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="28fb6-168">Закрытый ключ не должен быть развернут на компьютерах, регистрируемых в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="28fb6-168">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="28fb6-169">Он должен храниться в безопасном месте, где вы расшифровываете сообщения.</span><span class="sxs-lookup"><span data-stu-id="28fb6-169">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="28fb6-170">Расшифровка сообщений журнала защищенных событий</span><span class="sxs-lookup"><span data-stu-id="28fb6-170">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="28fb6-171">Следующий сценарий будет получен и расшифрован, предполагая, что у вас есть закрытый ключ:</span><span class="sxs-lookup"><span data-stu-id="28fb6-171">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="28fb6-172">См. также</span><span class="sxs-lookup"><span data-stu-id="28fb6-172">See also</span></span>

[<span data-ttu-id="28fb6-173">about_Logging_Non — Windows</span><span class="sxs-lookup"><span data-stu-id="28fb6-173">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="28fb6-174">PowerShell — Синяя команда</span><span class="sxs-lookup"><span data-stu-id="28fb6-174">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="28fb6-175">Универсальная интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="28fb6-175">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management

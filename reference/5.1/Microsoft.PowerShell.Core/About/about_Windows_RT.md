---
description: Описание ограничений Windows PowerShell 4,0 в Windows RT 8,1.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231882"
---
# <a name="about-windows-rt"></a><span data-ttu-id="f8e46-104">О Windows RT</span><span class="sxs-lookup"><span data-stu-id="f8e46-104">About Windows RT</span></span>

## <a name="short-description"></a><span data-ttu-id="f8e46-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f8e46-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f8e46-106">Описание ограничений Windows PowerShell 4,0 в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-106">Explains limitations of  Windows PowerShell 4.0 on Windows RT 8.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="f8e46-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f8e46-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f8e46-108">Операционная система Windows RT 8,1 устанавливается на компьютерах и устройствах (например, на Microsoft Surface 2, на которых установлена операционная система, входящая в состав компьютера), использующих процессоры Advanced RISC Computer (ARM).</span><span class="sxs-lookup"><span data-stu-id="f8e46-108">The Windows RT 8.1 operating system is installed on computers and devices (such as Microsoft Surface 2, on which it is the operating system that ships with the computer) that use Advanced RISC Machine (ARM) processors.</span></span>

<span data-ttu-id="f8e46-109">Windows PowerShell 4,0 входит в комплект Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-109">Windows PowerShell 4.0 is included in Windows RT 8.1.</span></span> <span data-ttu-id="f8e46-110">Все командлеты, поставщики и модули, а большинство скриптов, предназначенных для Windows PowerShell 2,0 и более поздних версий, выполняются в Windows RT 8,1 без изменений.</span><span class="sxs-lookup"><span data-stu-id="f8e46-110">All cmdlets, providers, and modules, and most scripts designed for Windows PowerShell 2.0 and later releases run on Windows RT 8.1 without changes.</span></span>

<span data-ttu-id="f8e46-111">Поскольку Windows RT 8,1 не включает все компоненты Windows, некоторые функции Windows PowerShell работают по-разному или не работают на устройствах под управлением Windows RT.</span><span class="sxs-lookup"><span data-stu-id="f8e46-111">Because Windows RT 8.1 does not include all Windows features, some Windows PowerShell features work differently or do not work on Windows RT-based devices.</span></span> <span data-ttu-id="f8e46-112">Различия описаны в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="f8e46-112">The following list explains the differences.</span></span>

- <span data-ttu-id="f8e46-113">Интегрированная среда сценариев Windows PowerShell не включена в и не может работать в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-113">Windows PowerShell ISE is not included in and cannot run on Windows RT 8.1.</span></span>
  <span data-ttu-id="f8e46-114">Интегрированная среда сценариев Windows PowerShell требует Windows Presentation Foundation, который не входит в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-114">Windows PowerShell ISE requires Windows Presentation Foundation, which is not included in Windows RT 8.1.</span></span>

- <span data-ttu-id="f8e46-115">Удаленное взаимодействие Windows PowerShell и служба WinRM по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="f8e46-115">Windows PowerShell remoting and the WinRM service are disabled by default.</span></span>
  <span data-ttu-id="f8e46-116">Чтобы включить удаленное взаимодействие, выполните командлет Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="f8e46-116">To enable remoting, run the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="f8e46-117">Кроме того, выполните командлет Set-Service, чтобы задать автоматический или автоматический режим запуска службы WinRM (отложенный запуск).</span><span class="sxs-lookup"><span data-stu-id="f8e46-117">Also, run the Set-Service cmdlet to set the startup type of the WinRM service to Automatic, or Automatic (Delayed Start).</span></span>

  <span data-ttu-id="f8e46-118">Хотя удаленное взаимодействие отключено, можно использовать удаленное взаимодействие Windows PowerShell для выполнения команд на других компьютерах, но другие компьютеры не могут выполнять команды на устройстве Windows RT.</span><span class="sxs-lookup"><span data-stu-id="f8e46-118">While remoting is disabled, you can use Windows PowerShell remoting to run commands on other computers, but other computers cannot run commands on the Windows RT device.</span></span> <span data-ttu-id="f8e46-119">Кроме того, неявное удаленное взаимодействие — это удаленное взаимодействие, встроенное в командлет или сценарий, которое не запрашивается явным образом с добавленными параметрами.</span><span class="sxs-lookup"><span data-stu-id="f8e46-119">Also, implicit remoting - that is, remoting that is built in to a cmdlet or script, and not explicitly requested with added parameters</span></span>
  - <span data-ttu-id="f8e46-120">не работает в Windows PowerShell, работающем в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-120">does not work in Windows PowerShell running on Windows RT 8.1.</span></span>

- <span data-ttu-id="f8e46-121">В Windows RT 8,1 не поддерживаются присоединенные к домену вычисления и проверка подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f8e46-121">Domain-joined computing and Kerberos authentication are not supported on Windows RT 8.1.</span></span> <span data-ttu-id="f8e46-122">Windows PowerShell нельзя использовать для добавления этих функций или управления ими.</span><span class="sxs-lookup"><span data-stu-id="f8e46-122">You cannot use Windows PowerShell to add or manage these features.</span></span>

- <span data-ttu-id="f8e46-123">Классы Microsoft .NET Framework, которые не поддерживаются в Windows RT 8,1, также не поддерживаются Windows PowerShell в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-123">Microsoft .NET Framework classes that are not supported on Windows RT 8.1 are also not supported by Windows PowerShell on Windows RT 8.1.</span></span>

- <span data-ttu-id="f8e46-124">Транзакции не включены в Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="f8e46-124">Transactions are not enabled on Windows RT 8.1.</span></span> <span data-ttu-id="f8e46-125">Командлеты транзакций, такие как Start-Transaction и параметры транзакции, такие как UseTransaction, не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="f8e46-125">Transaction cmdlets, such as Start-Transaction, and transaction parameters, such as UseTransaction, do not work properly.</span></span>

- <span data-ttu-id="f8e46-126">Все сеансы Windows PowerShell на устройствах Windows RT 8,1 используют языковой режим ConstrainedLanguage.</span><span class="sxs-lookup"><span data-stu-id="f8e46-126">All Windows PowerShell sessions on Windows RT 8.1 devices use the ConstrainedLanguage language mode.</span></span> <span data-ttu-id="f8e46-127">Языковой режим ConstrainedLanguage является вспомогательным для целостности кода пользовательского режима (УМЦИ).</span><span class="sxs-lookup"><span data-stu-id="f8e46-127">ConstrainedLanguage language mode is a companion to User Mode Code Integrity (UMCI).</span></span> <span data-ttu-id="f8e46-128">Он позволяет использовать все командлеты Windows и языковые элементы Windows PowerShell, но запрещает использование Windows PowerShell для обхода или нарушения защиты УМЦИ.</span><span class="sxs-lookup"><span data-stu-id="f8e46-128">It permits all Windows cmdlets and Windows PowerShell language elements, but restricts types to ensure that users cannot use Windows PowerShell to circumvent or violate the UMCI protections.</span></span>

<span data-ttu-id="f8e46-129">Дополнительные сведения о языковом режиме ConstrainedLanguage см. в разделе [about_Language_Modes](about_Language_Modes.md).</span><span class="sxs-lookup"><span data-stu-id="f8e46-129">For more information about ConstrainedLanguage language mode, see [about_Language_Modes](about_Language_Modes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8e46-130">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f8e46-130">SEE ALSO</span></span>

[<span data-ttu-id="f8e46-131">about_Language_Modes</span><span class="sxs-lookup"><span data-stu-id="f8e46-131">about_Language_Modes</span></span>](about_Language_Modes.md)

[<span data-ttu-id="f8e46-132">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f8e46-132">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="f8e46-133">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="f8e46-133">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

---
description: Описывает, как управлять транзакционными операциями в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: о транзакциях
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231905"
---
# <a name="about-transactions"></a><span data-ttu-id="9fb00-104">О транзакциях</span><span class="sxs-lookup"><span data-stu-id="9fb00-104">About Transactions</span></span>

## <a name="short-description"></a><span data-ttu-id="9fb00-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="9fb00-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9fb00-106">Описывает, как управлять транзакционными операциями в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fb00-106">Describes how to manage transacted operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9fb00-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="9fb00-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9fb00-108">Транзакции поддерживаются в PowerShell, начиная с PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="9fb00-108">Transactions are supported in PowerShell beginning in PowerShell 2.0.</span></span> <span data-ttu-id="9fb00-109">Эта функция позволяет запустить транзакцию, указать команды, которые являются частью транзакции, а также выполнить фиксацию или откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-109">This feature enables you to start a transaction, to indicate which commands are part of the transaction, and to commit or roll back a transaction.</span></span>

## <a name="about-transactions"></a><span data-ttu-id="9fb00-110">О ТРАНЗАКЦИЯХ</span><span class="sxs-lookup"><span data-stu-id="9fb00-110">ABOUT TRANSACTIONS</span></span>

<span data-ttu-id="9fb00-111">В PowerShell транзакция представляет собой набор из одной или нескольких команд, управляемых как логические устройства.</span><span class="sxs-lookup"><span data-stu-id="9fb00-111">In PowerShell, a transaction is a set of one or more commands that are managed as a logical unit.</span></span> <span data-ttu-id="9fb00-112">Транзакция может быть завершена ("фиксируется"), которая изменяет данные, затронутые транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-112">A transaction can be completed ("committed"), which changes data affected by the transaction.</span></span> <span data-ttu-id="9fb00-113">Или транзакция может быть полностью отменена («откат»), чтобы затронутые данные не изменялись транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-113">Or, a transaction can be completely undone ("rolled back") so that the affected data is not changed by the transaction.</span></span>

<span data-ttu-id="9fb00-114">Так как команды в транзакции управляются как единое целое, фиксируются либо все команды, либо выполняется откат всех команд.</span><span class="sxs-lookup"><span data-stu-id="9fb00-114">Because the commands in a transaction are managed as a unit, either all commands are committed, or all commands are rolled back.</span></span>

<span data-ttu-id="9fb00-115">Транзакции широко используются при обработке данных, что особенно важно в операциях базы данных и финансовых транзакциях.</span><span class="sxs-lookup"><span data-stu-id="9fb00-115">Transactions are widely used in data processing, most notably in database operations and for financial transactions.</span></span> <span data-ttu-id="9fb00-116">Транзакции чаще всего используются, когда наихудший сценарий для набора команд не так, что все они завершаются сбоем, но некоторые команды были выполнены успешно, в то время как другие завершаются сбоем, что может привести к повреждению, ложным или неинтерпретируемому состоянию, который трудно восстановить.</span><span class="sxs-lookup"><span data-stu-id="9fb00-116">Transactions are most often used when the worst-case scenario for a set of commands is not that they all fail, but that some commands succeed while others fail, leaving the system in a damaged, false, or uninterpretable state that is difficult to repair.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="9fb00-117">КОМАНДЛЕТЫ ТРАНЗАКЦИЙ</span><span class="sxs-lookup"><span data-stu-id="9fb00-117">TRANSACTION CMDLETS</span></span>

<span data-ttu-id="9fb00-118">PowerShell включает несколько командлетов, предназначенных для управления транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9fb00-118">PowerShell includes several cmdlets designed for managing transactions.</span></span>

- <span data-ttu-id="9fb00-119">Start-Transaction: запускает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-119">Start-Transaction: Starts a new transaction.</span></span>
- <span data-ttu-id="9fb00-120">Use-Transaction: добавляет в транзакцию команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="9fb00-120">Use-Transaction: Adds a command or expression to the transaction.</span></span> <span data-ttu-id="9fb00-121">Команда должна использовать объекты с поддержкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="9fb00-121">The command must use transaction-enabled objects.</span></span>
- <span data-ttu-id="9fb00-122">Отменить-Transaction: откатывает транзакцию, чтобы данные не изменялись транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-122">Undo-Transaction: Rolls back the transaction so that no data is changed by the transaction.</span></span>
- <span data-ttu-id="9fb00-123">Complete — Transaction: фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-123">Complete-Transaction: Commits the transaction.</span></span> <span data-ttu-id="9fb00-124">Изменились данные, затронутые транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-124">The data affected by the transaction is changed.</span></span>
- <span data-ttu-id="9fb00-125">Get-Transaction: получает сведения об активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-125">Get-Transaction: Gets information about the active transaction.</span></span>

<span data-ttu-id="9fb00-126">Для списка командлетов транзакций введите:</span><span class="sxs-lookup"><span data-stu-id="9fb00-126">For a list of transaction cmdlets, type:</span></span>

```powershell
get-command *transaction
```

<span data-ttu-id="9fb00-127">Для получения подробных сведений о командлетах введите:</span><span class="sxs-lookup"><span data-stu-id="9fb00-127">For detailed information about the cmdlets, type:</span></span>

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a><span data-ttu-id="9fb00-128">ЭЛЕМЕНТЫ С ПОДДЕРЖКОЙ ТРАНЗАКЦИЙ</span><span class="sxs-lookup"><span data-stu-id="9fb00-128">TRANSACTION-ENABLED ELEMENTS</span></span>

<span data-ttu-id="9fb00-129">Для участия в транзакции оба командлета и поставщик должны поддерживать транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-129">To participate in a transaction, both the cmdlet and the provider must support transactions.</span></span> <span data-ttu-id="9fb00-130">Эта функция встроена в объекты, затрагиваемые транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-130">This feature is built in to the objects that are affected by the transaction.</span></span>

<span data-ttu-id="9fb00-131">Поставщик реестра PowerShell поддерживает транзакции в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="9fb00-131">The PowerShell Registry provider supports transactions in Windows Vista.</span></span> <span data-ttu-id="9fb00-132">Объект TransactedString (Microsoft. PowerShell. Commands. Management. TransactedString) работает с любой операционной системой, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fb00-132">The TransactedString object (Microsoft.PowerShell.Commands.Management.TransactedString) works with any operating system that runs PowerShell.</span></span>

<span data-ttu-id="9fb00-133">Другие поставщики PowerShell могут поддерживать транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-133">Other PowerShell providers can support transactions.</span></span> <span data-ttu-id="9fb00-134">Чтобы найти в сеансе поставщики PowerShell, которые поддерживают транзакции, используйте следующую команду, чтобы найти значение Transactions в свойстве capabilities поставщиков:</span><span class="sxs-lookup"><span data-stu-id="9fb00-134">To find the PowerShell providers in your session that support transactions, use the following command to find the "Transactions" value in the Capabilities property of providers:</span></span>

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

<span data-ttu-id="9fb00-135">Дополнительные сведения о поставщике см. в справке поставщика.</span><span class="sxs-lookup"><span data-stu-id="9fb00-135">For more information about a provider, see the Help for the provider.</span></span> <span data-ttu-id="9fb00-136">Чтобы получить справку поставщика, введите:</span><span class="sxs-lookup"><span data-stu-id="9fb00-136">To get provider Help, type:</span></span>

```
get-help <provider-name>
```

<span data-ttu-id="9fb00-137">Например, чтобы получить справку для поставщика Registry, введите:</span><span class="sxs-lookup"><span data-stu-id="9fb00-137">For example, to get Help for the Registry provider, type:</span></span>

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a><span data-ttu-id="9fb00-138">ПАРАМЕТР USETRANSACTION</span><span class="sxs-lookup"><span data-stu-id="9fb00-138">THE USETRANSACTION PARAMETER</span></span>

<span data-ttu-id="9fb00-139">Командлеты, которые могут поддерживать транзакции, имеют параметр UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-139">Cmdlets that can support transactions have a UseTransaction parameter.</span></span> <span data-ttu-id="9fb00-140">Этот параметр включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-140">This parameter includes the command in the active transaction.</span></span> <span data-ttu-id="9fb00-141">Можно использовать полное имя параметра или его псевдоним "усеткс".</span><span class="sxs-lookup"><span data-stu-id="9fb00-141">You can use the full parameter name or its alias, "usetx".</span></span>

<span data-ttu-id="9fb00-142">Параметр может использоваться только в том случае, если сеанс содержит активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-142">The parameter can be used only when the session contains an active transaction.</span></span> <span data-ttu-id="9fb00-143">При вводе команды с параметром UseTransaction при отсутствии активной транзакции команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9fb00-143">If you enter a command with the UseTransaction parameter when there is no active transaction, the command fails.</span></span>

<span data-ttu-id="9fb00-144">Чтобы найти командлеты с параметром UseTransaction, введите:</span><span class="sxs-lookup"><span data-stu-id="9fb00-144">To find cmdlets with the UseTransaction parameter, type:</span></span>

```powershell
get-help * -parameter UseTransaction
```

<span data-ttu-id="9fb00-145">В PowerShell Core все командлеты, предназначенные для работы с поставщиками PowerShell, поддерживают транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-145">In PowerShell core, all of the cmdlets designed to work with PowerShell providers support transactions.</span></span> <span data-ttu-id="9fb00-146">В результате можно использовать командлеты поставщика для управления транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9fb00-146">As a result, you can use the provider cmdlets to manage transactions.</span></span>

<span data-ttu-id="9fb00-147">Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9fb00-147">For more information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

## <a name="the-transaction-object"></a><span data-ttu-id="9fb00-148">ОБЪЕКТ TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="9fb00-148">THE TRANSACTION OBJECT</span></span>

<span data-ttu-id="9fb00-149">Транзакции представлены в PowerShell объектом транзакции, System. Management. Automation. Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-149">Transactions are represented in PowerShell by a transaction object, System.Management.Automation.Transaction.</span></span>

<span data-ttu-id="9fb00-150">Ниже приводится описание свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="9fb00-150">The object has the following properties:</span></span>

- <span data-ttu-id="9fb00-151">RollbackPreference: содержит параметры отката, заданные для текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-151">RollbackPreference: Contains the rollback preference set for the current transaction.</span></span> <span data-ttu-id="9fb00-152">Можно задать параметр отката при использовании Start-Transaction для запуска транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-152">You can set the rollback preference when you use Start-Transaction to start the transaction.</span></span>

  <span data-ttu-id="9fb00-153">Параметр отката определяет условия, при которых транзакция автоматически откатывается.</span><span class="sxs-lookup"><span data-stu-id="9fb00-153">The rollback preference determines the conditions under which the transaction is rolled back automatically.</span></span> <span data-ttu-id="9fb00-154">Допустимые значения: Error, Терминатинжеррор и Never.</span><span class="sxs-lookup"><span data-stu-id="9fb00-154">Valid values are Error, TerminatingError, and Never.</span></span> <span data-ttu-id="9fb00-155">Значение по умолчанию — Error.</span><span class="sxs-lookup"><span data-stu-id="9fb00-155">The default value is Error.</span></span>

- <span data-ttu-id="9fb00-156">Состояние: содержит текущее состояние транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-156">Status: Contains the current status of the transaction.</span></span> <span data-ttu-id="9fb00-157">Допустимые значения: Active, COMMITTED и откат.</span><span class="sxs-lookup"><span data-stu-id="9fb00-157">Valid values are Active, Committed, and RolledBack.</span></span>

- <span data-ttu-id="9fb00-158">Субскриберкаунт: содержит число подписчиков на транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-158">SubscriberCount: Contains the number of subscribers to the transaction.</span></span> <span data-ttu-id="9fb00-159">Подписчик добавляется в транзакцию при запуске транзакции во время выполнения другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-159">A subscriber is added to a transaction when you start a transaction while another transaction is in progress.</span></span> <span data-ttu-id="9fb00-160">Число подписчиков уменьшается, когда подписчик фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-160">The subscriber count is decremented when a subscriber commits the transaction.</span></span>

## <a name="active-transactions"></a><span data-ttu-id="9fb00-161">АКТИВНЫЕ ТРАНЗАКЦИИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-161">ACTIVE TRANSACTIONS</span></span>

<span data-ttu-id="9fb00-162">В PowerShell в каждый момент времени активна только одна транзакция, и вы можете управлять только активной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-162">In PowerShell, only one transaction is active at a time, and you can manage only the active transaction.</span></span> <span data-ttu-id="9fb00-163">Одновременно может выполняться несколько транзакций в одном сеансе, но активна только самая последняя начальная транзакция.</span><span class="sxs-lookup"><span data-stu-id="9fb00-163">Multiple transactions can be in progress in the same session at the same time, but only the most-recently started transaction is active.</span></span>

<span data-ttu-id="9fb00-164">В результате при использовании командлетов Transaction нельзя указать конкретную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-164">As a result, you cannot specify a particular transaction when using the transaction cmdlets.</span></span> <span data-ttu-id="9fb00-165">Команды всегда применяются к активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-165">Commands always apply to the active transaction.</span></span>

<span data-ttu-id="9fb00-166">Это наиболее очевидно в работе командлета Get-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-166">This is most evident in the behavior of the Get-Transaction cmdlet.</span></span> <span data-ttu-id="9fb00-167">При вводе команды Get-Transaction Get-Transaction всегда получает только один объект транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-167">When you enter a Get-Transaction command, Get-Transaction always gets only one transaction object.</span></span> <span data-ttu-id="9fb00-168">Этот объект представляет собой объект, представляющий активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-168">This object is the object that represents the active transaction.</span></span>

<span data-ttu-id="9fb00-169">Для управления другой транзакцией необходимо сначала завершить активную транзакцию, заменив ее или выполнив ее откат.</span><span class="sxs-lookup"><span data-stu-id="9fb00-169">To manage a different transaction, you must first finish the active transaction, either by committing it or rolling it back.</span></span> <span data-ttu-id="9fb00-170">При этом предыдущая транзакция автоматически активизируется.</span><span class="sxs-lookup"><span data-stu-id="9fb00-170">When you do this, the previous transaction becomes active automatically.</span></span> <span data-ttu-id="9fb00-171">Транзакции становятся активными в порядке, в котором они запускаются, чтобы последняя начальная транзакция всегда была активной.</span><span class="sxs-lookup"><span data-stu-id="9fb00-171">Transactions become active in the reverse of order of which they are started, so that the most recently started transaction is always active.</span></span>

## <a name="subscribers-and-independent-transactions"></a><span data-ttu-id="9fb00-172">ПОДПИСЧИКИ И НЕЗАВИСИМЫЕ ТРАНЗАКЦИИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-172">SUBSCRIBERS AND INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="9fb00-173">Если вы запускаете транзакцию во время выполнения другой транзакции, по умолчанию PowerShell не запускает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-173">If you start a transaction while another transaction is in progress, by default, PowerShell does not start a new transaction.</span></span> <span data-ttu-id="9fb00-174">Вместо этого он добавляет "Подписчик" к текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-174">Instead, it adds a "subscriber" to the current transaction.</span></span>

<span data-ttu-id="9fb00-175">Если транзакция имеет несколько подписчиков, одна команда Undo-Transaction в любой точке выполняет откат всей транзакции для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="9fb00-175">When a transaction has multiple subscribers, a single Undo-Transaction command at any point rolls back the entire transaction for all subscribers.</span></span> <span data-ttu-id="9fb00-176">Однако для фиксации транзакции необходимо ввести команду Complete-Transaction для каждого подписчика.</span><span class="sxs-lookup"><span data-stu-id="9fb00-176">However, to commit the transaction, you must enter a Complete-Transaction command for every subscriber.</span></span>

<span data-ttu-id="9fb00-177">Чтобы узнать число подписчиков на транзакцию, проверьте свойство Субскриберкаунт объекта Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-177">To find the number of subscribers to a transaction, check the SubscriberCount property of the transaction object.</span></span> <span data-ttu-id="9fb00-178">Например, следующая команда использует командлет Get-Transaction для получения значения свойства Субскриберкаунт активной транзакции:</span><span class="sxs-lookup"><span data-stu-id="9fb00-178">For example, the following command uses the Get-Transaction cmdlet to get the value of the SubscriberCount property of the active transaction:</span></span>

```powershell
(Get-Transaction).SubscriberCount
```

<span data-ttu-id="9fb00-179">Добавление подписчика является поведением по умолчанию, так как большинство транзакций, запущенных во время выполнения другой транзакции, связаны с исходной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-179">Adding a subscriber is the default behavior because most transactions that are started while another transaction is in progress are related to the original transaction.</span></span> <span data-ttu-id="9fb00-180">В типичной модели скрипт, содержащий транзакцию, вызывает вспомогательный скрипт, который содержит собственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-180">In the typical model, a script that contains a transaction calls a helper script that contains its own transaction.</span></span> <span data-ttu-id="9fb00-181">Поскольку транзакции связаны, они должны быть откатываются или зафиксированы как единое целое.</span><span class="sxs-lookup"><span data-stu-id="9fb00-181">Because the transactions are related, they should be rolled back or committed as a unit.</span></span>

<span data-ttu-id="9fb00-182">Однако можно запустить транзакцию, которая не зависит от текущей транзакции, с помощью независимого параметра командлета Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-182">However, you can start a transaction that is independent of the current transaction by using the Independent parameter of the Start-Transaction cmdlet.</span></span>

<span data-ttu-id="9fb00-183">При запуске независимой транзакции Start-Transaction создает новый объект транзакции, а новая транзакция превращается в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-183">When you start an independent transaction, Start-Transaction creates a new transaction object, and the new transaction becomes the active transaction.</span></span>
<span data-ttu-id="9fb00-184">Независимая транзакция может быть зафиксирована или отменена без влияния на исходную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-184">The independent transaction can be committed or rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="9fb00-185">После завершения независимой транзакции (фиксация или откат) исходная транзакция снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="9fb00-185">When the independent transaction is finished (committed or rolled back), the original transaction becomes the active transaction again.</span></span>

## <a name="changing-data"></a><span data-ttu-id="9fb00-186">ИЗМЕНЕНИЕ ДАННЫХ</span><span class="sxs-lookup"><span data-stu-id="9fb00-186">CHANGING DATA</span></span>

<span data-ttu-id="9fb00-187">При использовании транзакций для изменения данных данные, затрагиваемые транзакцией, не изменяются, пока транзакция не будет зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="9fb00-187">When you use transactions to change data, the data that is affected by the transaction is not changed until you commit the transaction.</span></span> <span data-ttu-id="9fb00-188">Однако одни и те же данные могут быть изменены командами, не входящими в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-188">However, the same data can be changed by commands that are not part of the transaction.</span></span>

<span data-ttu-id="9fb00-189">Учитывайте это при использовании транзакций для управления общими данными.</span><span class="sxs-lookup"><span data-stu-id="9fb00-189">Keep this in mind when you are using transactions to manage shared data.</span></span>
<span data-ttu-id="9fb00-190">Как правило, базы данных имеют механизмы, которые блокируют данные во время работы, предотвращая их изменение другими пользователями, а также другими командами, сценариями и функциями.</span><span class="sxs-lookup"><span data-stu-id="9fb00-190">Typically, databases have mechanisms that lock the data while you are working on it, preventing other users, and other commands, scripts, and functions, from changing it.</span></span>

<span data-ttu-id="9fb00-191">Однако блокировка является компонентом базы данных.</span><span class="sxs-lookup"><span data-stu-id="9fb00-191">However, the lock is a feature of the database.</span></span> <span data-ttu-id="9fb00-192">Он не связан с транзакциями.</span><span class="sxs-lookup"><span data-stu-id="9fb00-192">It is not related to transactions.</span></span> <span data-ttu-id="9fb00-193">При работе в файловой системе с поддержкой транзакций или другом хранилище данных можно изменить данные во время выполнения транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-193">If you are working in a transaction-enabled file system or other data store, the data can be changed while the transaction is in progress.</span></span>

## <a name="examples"></a><span data-ttu-id="9fb00-194">Примеры</span><span class="sxs-lookup"><span data-stu-id="9fb00-194">EXAMPLES</span></span>

<span data-ttu-id="9fb00-195">В примерах этого раздела используется поставщик реестра PowerShell, и предполагается, что вы знакомы с ним.</span><span class="sxs-lookup"><span data-stu-id="9fb00-195">The examples in this section use the PowerShell Registry provider and assume that you are familiar with it.</span></span> <span data-ttu-id="9fb00-196">Для получения сведений о поставщике реестра введите «Get-Help Registry».</span><span class="sxs-lookup"><span data-stu-id="9fb00-196">For information about the Registry provider, type "get-help registry".</span></span>

### <a name="example-1-committing-a-transaction"></a><span data-ttu-id="9fb00-197">ПРИМЕР 1. ФИКСАЦИЯ ТРАНЗАКЦИИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-197">EXAMPLE 1: COMMITTING A TRANSACTION</span></span>

<span data-ttu-id="9fb00-198">Чтобы создать транзакцию, используйте командлет Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-198">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="9fb00-199">Следующая команда запускает транзакцию с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-199">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-200">Чтобы включить команды в транзакцию, используйте параметр UseTransaction командлета.</span><span class="sxs-lookup"><span data-stu-id="9fb00-200">To include commands in the transaction, use the UseTransaction parameter of the cmdlet.</span></span> <span data-ttu-id="9fb00-201">По умолчанию команды не включаются в транзакцию,</span><span class="sxs-lookup"><span data-stu-id="9fb00-201">By default, commands are not included in the transaction,</span></span>

<span data-ttu-id="9fb00-202">Например, следующая команда, которая задает текущее расположение в программном ключе диска HKCU:, не включается в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-202">For example, the following command, which sets the current location in the Software key of the HKCU: drive, is not included in the transaction.</span></span>

```powershell
cd hkcu:\Software
```

<span data-ttu-id="9fb00-203">Следующая команда, создающая ключ MyCompany, использует параметр UseTransaction командлета New-Item для включения команды в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-203">The following command, which creates the MyCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="9fb00-204">Команда возвращает объект, представляющий новый ключ, но поскольку команда является частью транзакции, реестр еще не изменен.</span><span class="sxs-lookup"><span data-stu-id="9fb00-204">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

<span data-ttu-id="9fb00-205">Чтобы зафиксировать транзакцию, используйте командлет Complete-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-205">To commit the transaction, use the Complete-Transaction cmdlet.</span></span> <span data-ttu-id="9fb00-206">Так как он всегда влияет на активную транзакцию, нельзя указать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-206">Because it always affects the active transaction, you cannot specify the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-207">В результате ключ MyCompany добавляется в реестр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-207">As a result, the MyCompany key is added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a><span data-ttu-id="9fb00-208">ПРИМЕР 2. ОТКАТ ТРАНЗАКЦИИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-208">EXAMPLE 2: ROLLING BACK A TRANSACTION</span></span>

<span data-ttu-id="9fb00-209">Чтобы создать транзакцию, используйте командлет Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-209">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="9fb00-210">Следующая команда запускает транзакцию с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-210">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-211">Следующая команда, создающая ключ Мйосеркомпани, использует параметр UseTransaction командлета New-Item для включения команды в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-211">The following command, which creates the MyOtherCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -UseTransaction
```

<span data-ttu-id="9fb00-212">Команда возвращает объект, представляющий новый ключ, но поскольку команда является частью транзакции, реестр еще не изменен.</span><span class="sxs-lookup"><span data-stu-id="9fb00-212">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

<span data-ttu-id="9fb00-213">Для отката транзакции используйте командлет Undo-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-213">To roll back the transaction, use the Undo-Transaction cmdlet.</span></span> <span data-ttu-id="9fb00-214">Так как он всегда влияет на активную транзакцию, транзакция не указывается.</span><span class="sxs-lookup"><span data-stu-id="9fb00-214">Because it always affects the active transaction, you do not specify the transaction.</span></span>

```powershell
Undo-transaction
```

<span data-ttu-id="9fb00-215">В результате ключ Мйосеркомпани не добавляется в реестр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-215">The result is that the MyOtherCompany key is not added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a><span data-ttu-id="9fb00-216">ПРИМЕР 3. ПРЕДВАРИТЕЛЬНЫЙ ПРОСМОТР ТРАНЗАКЦИИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-216">EXAMPLE 3: PREVIEWING A TRANSACTION</span></span>

<span data-ttu-id="9fb00-217">Как правило, команды, используемые в данных изменения транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-217">Typically, the commands used in a transaction change data.</span></span> <span data-ttu-id="9fb00-218">Однако команды, получающие данные, полезны и в транзакции, так как они получают данные внутри транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-218">However, the commands that get data are useful in a transaction, too, because they get data inside of the transaction.</span></span> <span data-ttu-id="9fb00-219">Это обеспечивает предварительный просмотр изменений, которые могут привести к сбою транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-219">This provides a preview of the changes that committing the transaction would cause.</span></span>

<span data-ttu-id="9fb00-220">В следующем примере показано, как использовать команду Get-ChildItem (псевдоним — Dir) для предварительного просмотра изменений в транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-220">The following example shows how to use the Get-ChildItem command (the alias is "dir") to preview the changes in a transaction.</span></span>

<span data-ttu-id="9fb00-221">Следующая команда запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-221">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-222">Следующая команда использует командлет New-ItemProperty, чтобы добавить запись реестра MyKey в ключ MyCompany.</span><span class="sxs-lookup"><span data-stu-id="9fb00-222">The following command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="9fb00-223">Команда использует параметр UseTransaction для включения команды в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-223">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

<span data-ttu-id="9fb00-224">Команда возвращает объект, представляющий новую запись реестра, но запись реестра не изменяется.</span><span class="sxs-lookup"><span data-stu-id="9fb00-224">The command returns an object representing the new registry entry, but the registry entry is not changed.</span></span>

```
MyKey
-----
123
```

<span data-ttu-id="9fb00-225">Чтобы получить элементы, которые в данный момент находятся в реестре, используйте команду Get-ChildItem (DIR) без параметра UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-225">To get the items that are currently in the registry, use a Get-ChildItem command ("dir") without the UseTransaction parameter.</span></span> <span data-ttu-id="9fb00-226">Следующая команда возвращает элементы, которые начинаются с "M".</span><span class="sxs-lookup"><span data-stu-id="9fb00-226">The following command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="9fb00-227">Результат показывает, что в ключ MyCompany еще не было добавлено ни одной записи.</span><span class="sxs-lookup"><span data-stu-id="9fb00-227">The result shows that no entries have yet been added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

<span data-ttu-id="9fb00-228">Чтобы просмотреть результат фиксации транзакции, введите команду Get-ChildItem ("Dir") с параметром UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-228">To preview the effect of committing the transaction, enter a Get-ChildItem ("dir") command with the UseTransaction parameter.</span></span> <span data-ttu-id="9fb00-229">Эта команда содержит представление данных в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-229">This command has a view of the data from within the transaction.</span></span>

```powershell
dir m* -useTransaction
```

<span data-ttu-id="9fb00-230">Результат показывает, что если транзакция зафиксирована, в ключ MyCompany будет добавлена запись MyKey.</span><span class="sxs-lookup"><span data-stu-id="9fb00-230">The result shows that, if the transaction is committed, the MyKey entry will be added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a><span data-ttu-id="9fb00-231">ПРИМЕР 4. ОБЪЕДИНЕНИЕ ТРАНЗАКЦИОННЫХ И НЕТРАНЗАКЦИОННЫХ КОМАНД</span><span class="sxs-lookup"><span data-stu-id="9fb00-231">EXAMPLE 4: COMBINING TRANSACTED AND NON-TRANSACTED COMMANDS</span></span>

<span data-ttu-id="9fb00-232">Во время транзакции можно вводить нетранзакционные команды.</span><span class="sxs-lookup"><span data-stu-id="9fb00-232">You can enter non-transacted commands during a transaction.</span></span> <span data-ttu-id="9fb00-233">Нетранзакционные команды влияют на данные немедленно, но они не влияют на транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-233">The non-transacted commands affect the data immediately, but they do not affect the transaction.</span></span>
<span data-ttu-id="9fb00-234">Следующая команда запускает транзакцию в разделе реестра HKCU: \ Software.</span><span class="sxs-lookup"><span data-stu-id="9fb00-234">The following command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-235">Следующие три команды используют командлет New-Item для добавления разделов в реестр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-235">The next three commands use the New-Item cmdlet to add keys to the registry.</span></span>
<span data-ttu-id="9fb00-236">Первая и третья команды используют параметр UseTransaction для включения команд в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-236">The first and third commands use the UseTransaction parameter to include the commands in the transaction.</span></span> <span data-ttu-id="9fb00-237">Вторая команда пропускает параметр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-237">The second command omits the parameter.</span></span> <span data-ttu-id="9fb00-238">Так как Вторая команда не включена в транзакцию, она вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="9fb00-238">Because the second command is not included in the transaction, it is effective immediately.</span></span>

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

<span data-ttu-id="9fb00-239">Чтобы просмотреть текущее состояние реестра, используйте команду Get-ChildItem (DIR) без параметра UseTransaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-239">To view the current state of the registry, use a Get-ChildItem ("dir") command without the UseTransaction parameter.</span></span> <span data-ttu-id="9fb00-240">Эта команда возвращает элементы, которые начинаются с "M".</span><span class="sxs-lookup"><span data-stu-id="9fb00-240">This command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="9fb00-241">Результат показывает, что ключ MyCompany2 добавляется в реестр, но ключи MyCompany1 и MyCompany3, которые являются частью транзакции, не добавляются.</span><span class="sxs-lookup"><span data-stu-id="9fb00-241">The result shows that the MyCompany2 key is added to the registry, but the MyCompany1 and MyCompany3 keys, which are part of the transaction, are not added.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

<span data-ttu-id="9fb00-242">Следующая команда фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-242">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-243">Теперь ключи, добавленные как часть транзакции, отображаются в реестре.</span><span class="sxs-lookup"><span data-stu-id="9fb00-243">Now, the keys that were added as part of the transaction appear in the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a><span data-ttu-id="9fb00-244">ПРИМЕР 5. ИСПОЛЬЗОВАНИЕ АВТОМАТИЧЕСКОГО ОТКАТА</span><span class="sxs-lookup"><span data-stu-id="9fb00-244">EXAMPLE 5: USING AUTOMATIC ROLLBACK</span></span>

<span data-ttu-id="9fb00-245">Если команда в транзакции создает ошибку какого-либо типа, то транзакция автоматически откатывается.</span><span class="sxs-lookup"><span data-stu-id="9fb00-245">When a command in a transaction generates an error of any kind, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="9fb00-246">Это поведение по умолчанию предназначено для скриптов, выполняющих транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-246">This default behavior is designed for scripts that run transactions.</span></span> <span data-ttu-id="9fb00-247">Обычно сценарии хорошо тестируются и включают логику обработки ошибок, поэтому ошибки не ожидаются и должны завершать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-247">Scripts are typically well tested and include error-handling logic, so errors are not expected and should terminate the transaction.</span></span>

<span data-ttu-id="9fb00-248">Первая команда запускает транзакцию в разделе реестра HKCU: \ Software.</span><span class="sxs-lookup"><span data-stu-id="9fb00-248">The first command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-249">Следующая команда добавляет ключ MyCompany в реестр с помощью командлета New-Item.</span><span class="sxs-lookup"><span data-stu-id="9fb00-249">The following command uses the New-Item cmdlet to add the MyCompany key to the registry.</span></span> <span data-ttu-id="9fb00-250">Команда использует параметр UseTransaction (псевдоним — "усеткс") для включения команды в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-250">The command uses the UseTransaction parameter (the alias is "usetx") to include the command in the transaction.</span></span>

```powershell
New-Item MyCompany -UseTX
```

<span data-ttu-id="9fb00-251">Так как ключ MyCompany уже существует в реестре, команда завершается ошибкой и выполняется откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-251">Because the MyCompany key already exists in the registry, the command fails, and the transaction is rolled back.</span></span>

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="9fb00-252">Команда Get-Transaction подтверждает, что транзакция была отменена и Субскриберкаунт имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="9fb00-252">A Get-Transaction command confirms that the transaction has been rolled back and that the SubscriberCount is 0.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a><span data-ttu-id="9fb00-253">ПРИМЕР 6. ИЗМЕНЕНИЕ НАСТРОЕК ОТКАТА</span><span class="sxs-lookup"><span data-stu-id="9fb00-253">EXAMPLE 6: CHANGING THE ROLLBACK PREFERENCE</span></span>

<span data-ttu-id="9fb00-254">Если требуется, чтобы транзакция была более отказоустойчивой, можно использовать параметр RollbackPreference Start-Transaction для изменения предпочтения.</span><span class="sxs-lookup"><span data-stu-id="9fb00-254">If you want the transaction to be more error tolerant, you can use the RollbackPreference parameter of Start-Transaction to change the preference.</span></span>

<span data-ttu-id="9fb00-255">Следующая команда запускает транзакцию с предпочтением отката "никогда".</span><span class="sxs-lookup"><span data-stu-id="9fb00-255">The following command starts a transaction with a rollback preference of "Never".</span></span>

```powershell
start-transaction -rollbackpreference Never
```

<span data-ttu-id="9fb00-256">В этом случае, если выполнение команды завершается неудачно, транзакция не будет автоматически отменена.</span><span class="sxs-lookup"><span data-stu-id="9fb00-256">In this case, when the command fails, the transaction is not automatically rolled back.</span></span>

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="9fb00-257">Так как транзакция все еще активна, можно повторно отправить команду в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-257">Because the transaction is still active, you can resubmit the command as part of the transaction.</span></span>

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a><span data-ttu-id="9fb00-258">ПРИМЕР 7. ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТА USE-TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="9fb00-258">EXAMPLE 7: USING THE USE-TRANSACTION CMDLET</span></span>

<span data-ttu-id="9fb00-259">Командлет Use-Transaction позволяет выполнять прямые сценарии для объектов платформы Microsoft .NET Framework с поддержкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="9fb00-259">The Use-Transaction cmdlet enables you to do direct scripting against transaction-enabled Microsoft .NET Framework objects.</span></span> <span data-ttu-id="9fb00-260">Use-Transaction принимает блок скрипта, который может содержать только команды и выражения, использующие объекты .NET Framework с поддержкой транзакций, например экземпляры класса Microsoft. PowerShell. Commands. Management. TransactedString.</span><span class="sxs-lookup"><span data-stu-id="9fb00-260">Use-Transaction takes a script block that can only contain commands and expressions that use transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="9fb00-261">Следующая команда запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-261">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-262">Следующая команда New-Object создает экземпляр класса TransactedString и сохраняет его в переменной $t.</span><span class="sxs-lookup"><span data-stu-id="9fb00-262">The following New-Object command creates an instance of the TransactedString class and saves it in the $t variable.</span></span>

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

<span data-ttu-id="9fb00-263">Следующая команда использует метод Append объекта TransactedString для добавления текста в строку.</span><span class="sxs-lookup"><span data-stu-id="9fb00-263">The following command uses the Append method of the TransactedString object to add text to the string.</span></span> <span data-ttu-id="9fb00-264">Так как команда не является частью транзакции, изменение вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="9fb00-264">Because the command is not part of the transaction, the change is effective immediately.</span></span>

```powershell
$t.append("Windows")
```

<span data-ttu-id="9fb00-265">Следующая команда использует один и тот же метод Append для добавления текста, но добавляет текст как часть транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-265">The following command uses the same Append method to add text, but it adds the text as part of the transaction.</span></span> <span data-ttu-id="9fb00-266">Команда заключается в фигурные скобки и задается в качестве значения параметра ScriptBlock командлета Use-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-266">The command is enclosed in braces, and it is set as the value of the ScriptBlock parameter of Use-Transaction.</span></span> <span data-ttu-id="9fb00-267">Параметр UseTransaction (Усеткс) является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9fb00-267">The UseTransaction parameter (UseTx) is required.</span></span>

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

<span data-ttu-id="9fb00-268">Чтобы просмотреть текущее содержимое транзакционной строки в $t, используйте метод ToString объекта TransactedString.</span><span class="sxs-lookup"><span data-stu-id="9fb00-268">To see the current content of the transacted string in $t, use the ToString method of the TransactedString object.</span></span>

```powershell
$t.tostring()
```

<span data-ttu-id="9fb00-269">Выходные данные показывают, что действуют только изменения, не относящиеся к транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-269">The output shows that only the non-transacted changes are effective.</span></span>

```output
Windows
```

<span data-ttu-id="9fb00-270">Чтобы просмотреть текущее содержимое транзакционной строки в $t в рамках транзакции, внедрите выражение в команду Use-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-270">To see the current content of the transacted string in $t from within the transaction, embed the expression in a Use-Transaction command.</span></span>

```powershell
use-transaction {$s.tostring()} -usetx
```

<span data-ttu-id="9fb00-271">В выходных данных отображается представление транзакций.</span><span class="sxs-lookup"><span data-stu-id="9fb00-271">The output shows the transaction view.</span></span>

```output
PowerShell
```

<span data-ttu-id="9fb00-272">Следующая команда фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-272">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-273">Чтобы просмотреть последнюю строку:</span><span class="sxs-lookup"><span data-stu-id="9fb00-273">To see the final string:</span></span>

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a><span data-ttu-id="9fb00-274">ПРИМЕР 8. УПРАВЛЕНИЕ ТРАНЗАКЦИЯМИ С НЕСКОЛЬКИМИ ПОДПИСЧИКАМИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-274">EXAMPLE 8: MANAGING MULTI-SUBSCRIBER TRANSACTIONS</span></span>

<span data-ttu-id="9fb00-275">При запуске транзакции во время выполнения другой транзакции PowerShell по умолчанию не создает вторую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-275">When you start a transaction while another transaction is in progress, PowerShell does not create a second transaction by default.</span></span> <span data-ttu-id="9fb00-276">Вместо этого он добавляет подписчика в текущую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-276">Instead, it adds a subscriber to the current transaction.</span></span>

<span data-ttu-id="9fb00-277">В этом примере показано, как просматривать транзакцию с несколькими подписчиками и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="9fb00-277">This example shows how to view and manage a multi-subscriber transaction.</span></span>

<span data-ttu-id="9fb00-278">Начните с запуска транзакции в разделе HKCU: \ программный ключ.</span><span class="sxs-lookup"><span data-stu-id="9fb00-278">Begin by starting a transaction in the HKCU:\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-279">Следующая команда использует команду Get-Transaction для получения активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-279">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="9fb00-280">В результате отображается объект, представляющий активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-280">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="9fb00-281">Следующая команда добавляет ключ MyCompany в реестр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-281">The following command adds the MyCompany key to the registry.</span></span> <span data-ttu-id="9fb00-282">Команда использует параметр UseTransaction для включения команды в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-282">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="9fb00-283">Следующая команда запускает транзакцию с помощью команды Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-283">The following command uses the Start-Transaction command to start a transaction.</span></span> <span data-ttu-id="9fb00-284">Хотя эта команда введена в командной строке, этот сценарий, скорее всего, будет выполняться при выполнении скрипта, содержащего транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-284">Although this command is typed at the command prompt, this scenario is more likely to happen when you run a script that contains a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-285">Команда Get-Transaction показывает, что число подписчиков в объекте транзакции увеличивается.</span><span class="sxs-lookup"><span data-stu-id="9fb00-285">A Get-Transaction command shows that the subscriber count on the transaction object is incremented.</span></span> <span data-ttu-id="9fb00-286">Теперь значение равно 2.</span><span class="sxs-lookup"><span data-stu-id="9fb00-286">The value is now 2.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="9fb00-287">Следующая команда использует командлет New-ItemProperty, чтобы добавить запись реестра MyKey в ключ MyCompany.</span><span class="sxs-lookup"><span data-stu-id="9fb00-287">The next command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="9fb00-288">Он использует параметр UseTransaction для включения команды в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-288">It uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

<span data-ttu-id="9fb00-289">Ключ MyCompany не существует в реестре, но эта команда выполняется, так как две команды являются частью одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-289">The MyCompany key does not exist in the registry, but this command succeeds because the two commands are part of the same transaction.</span></span>

<span data-ttu-id="9fb00-290">Следующая команда фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-290">The following command commits the transaction.</span></span> <span data-ttu-id="9fb00-291">При откате транзакции будет выполнен откат транзакции для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="9fb00-291">If it rolled back the transaction, the transaction would be rolled back for all the subscribers.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-292">Команда Get-Transaction показывает, что число подписчиков в объекте транзакции равно 1, но значение Status по-прежнему активно (не зафиксировано).</span><span class="sxs-lookup"><span data-stu-id="9fb00-292">A Get-Transaction command shows that the subscriber count on the transaction object is 1, but the value of Status is still Active (not Committed).</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="9fb00-293">Чтобы завершить фиксацию транзакции, введите вторую команду завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-293">To finish committing the transaction, enter a second Complete- Transaction command.</span></span> <span data-ttu-id="9fb00-294">Чтобы зафиксировать транзакцию с несколькими подписчиками, необходимо ввести одну команду Complete-Transaction для каждой команды Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-294">To commit a multi-subscriber transaction, you must enter one Complete-Transaction command for each Start-Transaction command.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-295">Другая команда Get-Transaction показывает, что транзакция была зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="9fb00-295">Another Get-Transaction command shows that the transaction has been committed.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a><span data-ttu-id="9fb00-296">ПРИМЕР 9. УПРАВЛЕНИЕ НЕЗАВИСИМЫМИ ТРАНЗАКЦИЯМИ</span><span class="sxs-lookup"><span data-stu-id="9fb00-296">EXAMPLE 9: MANAGING INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="9fb00-297">При запуске транзакции во время выполнения другой транзакции можно использовать независимый параметр Start-Transaction, чтобы создать новую транзакцию независимо от исходной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-297">When you start a transaction while another transaction is in progress, you can use the Independent parameter of Start-Transaction to make the new transaction independent of the original transaction.</span></span>

<span data-ttu-id="9fb00-298">После этого Start-Transaction создает новый объект Transaction и делает новую транзакцию активной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-298">When you do, Start-Transaction creates a new transaction object and makes the new transaction the active transaction.</span></span>

<span data-ttu-id="9fb00-299">Начните с запуска транзакции в ключе HKCU: \\ Software.</span><span class="sxs-lookup"><span data-stu-id="9fb00-299">Begin by starting a transaction in the HKCU:\\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="9fb00-300">Следующая команда использует команду Get-Transaction для получения активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-300">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="9fb00-301">В результате отображается объект, представляющий активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-301">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="9fb00-302">Следующая команда добавляет раздел реестра MyCompany в состав транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-302">The following command adds the MyCompany registry key as part of the transaction.</span></span> <span data-ttu-id="9fb00-303">Для включения команды в активную транзакцию используется параметр UseTransaction (Усеткс).</span><span class="sxs-lookup"><span data-stu-id="9fb00-303">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -use
```

<span data-ttu-id="9fb00-304">Следующая команда запускает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-304">The following command starts a new transaction.</span></span> <span data-ttu-id="9fb00-305">Команда использует независимый параметр, чтобы указать, что эта транзакция не является подписчиком активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-305">The command uses the Independent parameter to indicate that this transaction is not a subscriber to the active transaction.</span></span>

```powershell
start-transaction -independent
```

<span data-ttu-id="9fb00-306">При создании независимой транзакции новая транзакция (самая последняя созданная) превращается в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-306">When you create an independent transaction, the new (most-recently created) transaction becomes the active transaction.</span></span> <span data-ttu-id="9fb00-307">Для получения активной транзакции можно использовать команду Get-Transaction.</span><span class="sxs-lookup"><span data-stu-id="9fb00-307">You can use a Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="9fb00-308">Обратите внимание, что Субскриберкаунт транзакции — 1, что означает, что нет других подписчиков и что транзакция является новой.</span><span class="sxs-lookup"><span data-stu-id="9fb00-308">Note that the SubscriberCount of the transaction is 1, indicating that there are no other subscribers and that the transaction is new.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="9fb00-309">Новая транзакция должна быть завершена (зафиксирована или отменена), прежде чем можно будет управлять исходной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-309">The new transaction must be finished (either committed or rolled back) before you can manage the original transaction.</span></span>

<span data-ttu-id="9fb00-310">Следующая команда добавляет ключ Мйосеркомпани в реестр.</span><span class="sxs-lookup"><span data-stu-id="9fb00-310">The following command adds the MyOtherCompany key to the registry.</span></span> <span data-ttu-id="9fb00-311">Для включения команды в активную транзакцию используется параметр UseTransaction (Усеткс).</span><span class="sxs-lookup"><span data-stu-id="9fb00-311">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -usetx
```

<span data-ttu-id="9fb00-312">Теперь выполните откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="9fb00-312">Now, roll back the transaction.</span></span> <span data-ttu-id="9fb00-313">Если имеется одна транзакция с двумя подписчиками, откат транзакции приведет к откату всей транзакции для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="9fb00-313">If there were a single transaction with two subscribers, rolling back the transaction would roll back the entire transaction for all the subscribers.</span></span>

<span data-ttu-id="9fb00-314">Однако, поскольку эти транзакции независимы, откат самой последней транзакции отменяет изменения в реестре и делает исходную транзакцию активной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="9fb00-314">However, because these transactions are independent, rolling back the newest transaction cancels the registry changes and makes the original transaction the active transaction.</span></span>

```powershell
undo-transaction
```

<span data-ttu-id="9fb00-315">Команда Get-Transaction подтверждает, что исходная транзакция по-прежнему активна в сеансе.</span><span class="sxs-lookup"><span data-stu-id="9fb00-315">A Get-Transaction command confirms that the original transaction is still active in the session.</span></span>

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="9fb00-316">Следующая команда фиксирует активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9fb00-316">The following command commits the active transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="9fb00-317">Команда Get-ChildItem показывает, что реестр был изменен.</span><span class="sxs-lookup"><span data-stu-id="9fb00-317">A Get-ChildItem command shows that the registry has been changed.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a><span data-ttu-id="9fb00-318">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="9fb00-318">SEE ALSO</span></span>

[<span data-ttu-id="9fb00-319">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="9fb00-319">Start-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Start-Transaction)

[<span data-ttu-id="9fb00-320">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="9fb00-320">Get-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Get-Transaction)

[<span data-ttu-id="9fb00-321">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="9fb00-321">Complete-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[<span data-ttu-id="9fb00-322">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="9fb00-322">Undo-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[<span data-ttu-id="9fb00-323">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="9fb00-323">Use-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Use-Transaction)

[<span data-ttu-id="9fb00-324">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="9fb00-324">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[<span data-ttu-id="9fb00-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9fb00-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[<span data-ttu-id="9fb00-326">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9fb00-326">about_Providers</span></span>](about_Providers.md)

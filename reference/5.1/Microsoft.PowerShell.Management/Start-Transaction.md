---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227861"
---
# <span data-ttu-id="d00dd-103">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="d00dd-103">Start-Transaction</span></span>

## <span data-ttu-id="d00dd-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d00dd-104">SYNOPSIS</span></span>
<span data-ttu-id="d00dd-105">Запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-105">Starts a transaction.</span></span>

## <span data-ttu-id="d00dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d00dd-106">SYNTAX</span></span>

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d00dd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d00dd-107">DESCRIPTION</span></span>
<span data-ttu-id="d00dd-108">Командлет **Start-Transaction** запускает транзакцию, которая представляет собой последовательность команд, управляемых как единое целое.</span><span class="sxs-lookup"><span data-stu-id="d00dd-108">The **Start-Transaction** cmdlet starts a transaction, which is a series of commands that are managed as a unit.</span></span>
<span data-ttu-id="d00dd-109">Транзакция может быть выполнена или зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="d00dd-109">A transaction can be completed, or committed.</span></span>
<span data-ttu-id="d00dd-110">Кроме того, его можно полностью отменить или откатить, чтобы любые данные, измененные транзакцией, восстанавливались в исходное состояние.</span><span class="sxs-lookup"><span data-stu-id="d00dd-110">Alternatively, it can be completely undone, or rolled back, so that any data changed by the transaction is restored to its original state.</span></span>
<span data-ttu-id="d00dd-111">Так как команды транзакции управляются как единое целое, фиксируются или откатываются все команды.</span><span class="sxs-lookup"><span data-stu-id="d00dd-111">Because the commands in a transaction are managed as a unit, either all commands are committed or all commands are rolled back.</span></span>

<span data-ttu-id="d00dd-112">По умолчанию, если любая команда в транзакции создает ошибку, автоматически выполняется откат транзакций.</span><span class="sxs-lookup"><span data-stu-id="d00dd-112">By default, if any command in the transaction generates an error, transactions are rolled back automatically.</span></span>
<span data-ttu-id="d00dd-113">Для изменения этого поведения можно использовать параметр *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-113">You can use the *RollbackPreference* parameter to change this behavior.</span></span>

<span data-ttu-id="d00dd-114">Командлеты, используемые в транзакции, должны поддерживать такую возможность.</span><span class="sxs-lookup"><span data-stu-id="d00dd-114">The cmdlets used in a transaction must be designed to support transactions.</span></span>
<span data-ttu-id="d00dd-115">Командлеты, которые поддерживают транзакции, имеют параметр *UseTransaction* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-115">Cmdlets that support transactions have a *UseTransaction* parameter.</span></span>
<span data-ttu-id="d00dd-116">Для выполнения транзакций в поставщике поставщик должен поддерживать транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-116">To perform transactions in a provider, the provider must support transactions.</span></span>
<span data-ttu-id="d00dd-117">Поставщик реестра Windows PowerShell в Windows Vista и более поздних версиях операционной системы Windows поддерживает транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-117">The Windows PowerShell Registry provider in Windows Vista and later versions of the Windows operating system supports transactions.</span></span>
<span data-ttu-id="d00dd-118">Можно также использовать класс **Microsoft. PowerShell. Commands. Management. TransactedString** для включения выражений в транзакции в любой версии системы Windows, которая поддерживает Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d00dd-118">You can also use the **Microsoft.PowerShell.Commands.Management.TransactedString** class to include expressions in transactions on any version of the Windows system that supports Windows PowerShell.</span></span>
<span data-ttu-id="d00dd-119">Другие поставщики Windows PowerShell также могут поддерживать транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-119">Other Windows PowerShell providers can also support transactions.</span></span>

<span data-ttu-id="d00dd-120">Одновременно может быть активна только одна транзакция.</span><span class="sxs-lookup"><span data-stu-id="d00dd-120">Only one transaction can be active at a time.</span></span>
<span data-ttu-id="d00dd-121">При запуске новой, независимой транзакции во время выполнения транзакции новая транзакция становится активной транзакцией, и перед внесением изменений в исходную транзакцию необходимо зафиксировать или откатить новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-121">If you start a new, independent transaction while a transaction is in progress, the new transaction becomes the active transaction, and you must commit or roll back the new transaction before you make any changes to the original transaction.</span></span>

<span data-ttu-id="d00dd-122">Командлет **Start-Transaction** — это один из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d00dd-122">**Start-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="d00dd-123">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="d00dd-123">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="d00dd-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="d00dd-124">EXAMPLES</span></span>

### <span data-ttu-id="d00dd-125">Пример 1. Запуск и откат транзакции</span><span class="sxs-lookup"><span data-stu-id="d00dd-125">Example 1: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

<span data-ttu-id="d00dd-126">Эти команды запускают, а затем откатывают транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-126">These commands start and then roll back a transaction.</span></span>
<span data-ttu-id="d00dd-127">Так как транзакция откатывается, изменения в реестр не вносятся.</span><span class="sxs-lookup"><span data-stu-id="d00dd-127">Because the transaction is rolled back, no changes are made to the registry.</span></span>

### <span data-ttu-id="d00dd-128">Пример 2. Запуск и завершение транзакции</span><span class="sxs-lookup"><span data-stu-id="d00dd-128">Example 2: Start and complete a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="d00dd-129">Эти команды запускают, а затем завершают транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-129">These commands start and then complete a transaction.</span></span>
<span data-ttu-id="d00dd-130">В реестр не вносятся изменения, пока не будет использована команда **Complete-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="d00dd-130">No changes are made to the registry until the **Complete-Transaction** command is used.</span></span>

### <span data-ttu-id="d00dd-131">Пример 3. Использование различных настроек отката</span><span class="sxs-lookup"><span data-stu-id="d00dd-131">Example 3: Use different rollback preferences</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

<span data-ttu-id="d00dd-132">В этом примере демонстрируется результат изменения значения параметра *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-132">This example demonstrates the effect of changing the *RollbackPreference* parameter value.</span></span>

<span data-ttu-id="d00dd-133">В первом наборе команд **Start-Transaction** не использует *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-133">In the first set of commands, **Start-Transaction** does not use *RollbackPreference* .</span></span>
<span data-ttu-id="d00dd-134">В результате используется значение по умолчанию (Error).</span><span class="sxs-lookup"><span data-stu-id="d00dd-134">As a result, the default value (Error) is used.</span></span>
<span data-ttu-id="d00dd-135">При возникновении ошибки в команде транзакции, то есть указанный путь не существует, транзакция автоматически откатывается.</span><span class="sxs-lookup"><span data-stu-id="d00dd-135">When an error occurs in a transaction command, that is, the specified path does not exist, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="d00dd-136">Во втором наборе команд **Start-Transaction** использует *RollbackPreference* со значением Never.</span><span class="sxs-lookup"><span data-stu-id="d00dd-136">In the second set of commands, **Start-Transaction** uses *RollbackPreference* with a value of Never.</span></span>
<span data-ttu-id="d00dd-137">Поэтому, когда в команде транзакции происходит ошибка, транзакция остается активной и ее можно успешно завершить.</span><span class="sxs-lookup"><span data-stu-id="d00dd-137">As a result, when an error occurs in a transaction command, the transaction is still active and can be completed successfully.</span></span>

<span data-ttu-id="d00dd-138">Так как большинство транзакций должно выполняться без ошибок, обычно рекомендуется использовать значение по умолчанию *RollbackPreference* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-138">Because most transactions must be performed without error, the default value of *RollbackPreference* is typically preferred.</span></span>

### <span data-ttu-id="d00dd-139">Пример 4. Использование этого командлета во время выполнения транзакции</span><span class="sxs-lookup"><span data-stu-id="d00dd-139">Example 4: Use this cmdlet while a transaction is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="d00dd-140">В этом примере показан результат использования команды **Start-Transaction** во время выполнения транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-140">This example shows the effect of using **Start-Transaction** while a transaction is in progress.</span></span>
<span data-ttu-id="d00dd-141">Он во многом похож на присоединение к выполняющейся транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-141">The effect is much like joining the transaction in progress.</span></span>

<span data-ttu-id="d00dd-142">Хотя это упрощенная команда, этот сценарий часто возникает, когда транзакция включает в себя выполнение скрипта, включающего полную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-142">Although this is a simplified command, this scenario frequently occurs when the transaction involves running a script that includes a complete transaction.</span></span>

<span data-ttu-id="d00dd-143">Первая команда **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-143">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="d00dd-144">Первая команда **New-Item** является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-144">The first **New-Item** command is part of the transaction.</span></span>

<span data-ttu-id="d00dd-145">Вторая команда **Start-Transaction** добавляет нового подписчика в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-145">The second **Start-Transaction** command adds a new subscriber to the transaction.</span></span>
<span data-ttu-id="d00dd-146">Команда **Get-Transaction** теперь возвращает транзакцию с числом подписчиков, равным 2.</span><span class="sxs-lookup"><span data-stu-id="d00dd-146">The **Get-Transaction** command now returns a transaction with a subscriber count of 2.</span></span>
<span data-ttu-id="d00dd-147">Вторая команда **New-Item** является частью той же транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-147">The second **New-Item** command is part of the same transaction.</span></span>

<span data-ttu-id="d00dd-148">В реестр не вносятся изменения, пока не завершится вся транзакция.</span><span class="sxs-lookup"><span data-stu-id="d00dd-148">No changes are made to the registry until the whole transaction is completed.</span></span>
<span data-ttu-id="d00dd-149">Чтобы завершить транзакцию, необходимо ввести две команды **полных транзакций** — по одной для каждого подписчика.</span><span class="sxs-lookup"><span data-stu-id="d00dd-149">To complete the transaction, you must enter two **Complete-Transaction** commands, one for each subscriber.</span></span>
<span data-ttu-id="d00dd-150">Если вы намерены откатить транзакцию в любой момент, для обоих подписчиков будет выполнен откат всей транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-150">If you were to roll back the transaction at any point, all the transaction would be rolled back for both subscribers.</span></span>

### <span data-ttu-id="d00dd-151">Пример 5. Запуск независимой транзакции во время ее выполнения</span><span class="sxs-lookup"><span data-stu-id="d00dd-151">Example 5: Start an independent transaction while one is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="d00dd-152">В этом примере показан результат использования *независимого* параметра командлета **Start-Transaction** для запуска транзакции во время выполнения другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-152">This example shows the effect of using the *Independent* parameter of **Start-Transaction** to start a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="d00dd-153">В этом случае новая транзакция откатывается, не затрагивая исходной транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-153">In this case, the new transaction is rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="d00dd-154">Хотя транзакции логически не зависят друг от друга, одновременно может быть активна только одна транзакция, поэтому более позднюю транзакцию нужно откатить или зафиксировать, прежде чем возобновлять работу с исходной.</span><span class="sxs-lookup"><span data-stu-id="d00dd-154">Although the transactions are logically independent, because only one transaction can be active at a time, you must roll back or commit the newest transaction before resuming work on the original transaction.</span></span>

<span data-ttu-id="d00dd-155">Первый набор команд запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-155">The first set of commands starts a transaction.</span></span>
<span data-ttu-id="d00dd-156">Команда **New-Item** является частью первой транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-156">The **New-Item** command is part of the first transaction.</span></span>

<span data-ttu-id="d00dd-157">Во втором наборе команд Команда **Start-Transaction** использует *независимый* параметр.</span><span class="sxs-lookup"><span data-stu-id="d00dd-157">In the second set of commands, the **Start-Transaction** command uses the *Independent* parameter.</span></span>
<span data-ttu-id="d00dd-158">Приведенная ниже команда **Get-Transaction** показывает объект транзакции для активной транзакции, которая является самой новой.</span><span class="sxs-lookup"><span data-stu-id="d00dd-158">The **Get-Transaction** command that follows shows the transaction object for the active transaction, which is the newest one.</span></span>
<span data-ttu-id="d00dd-159">Число подписчиков равно 1, что указывает, что транзакции не связаны.</span><span class="sxs-lookup"><span data-stu-id="d00dd-159">The subscriber count is equal to 1, that shows that the transactions are unrelated.</span></span>

<span data-ttu-id="d00dd-160">При откате активной транзакции с помощью команды **отмены транзакции** исходная транзакция снова становится активной.</span><span class="sxs-lookup"><span data-stu-id="d00dd-160">When the active transaction is rolled back by using an **Undo-Transaction** command, the original transaction becomes active again.</span></span>

<span data-ttu-id="d00dd-161">Команда **New-ItemProperty** , которая является частью исходной транзакции, завершается без ошибок, а исходная транзакция может быть выполнена с помощью команды **Complete-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="d00dd-161">The **New-ItemProperty** command, which is part of the original transaction, finishes without error, and the original transaction can be completed by using the **Complete-Transaction** command.</span></span>
<span data-ttu-id="d00dd-162">В результате реестр изменяется.</span><span class="sxs-lookup"><span data-stu-id="d00dd-162">As a result, the registry is changed.</span></span>

### <span data-ttu-id="d00dd-163">Пример 6. выполнение команд, не входящих в транзакцию</span><span class="sxs-lookup"><span data-stu-id="d00dd-163">Example 6: Run commands that are not part of a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

<span data-ttu-id="d00dd-164">Этот пример демонстрирует, что команды, переданные во время выполнения транзакции, могут включаться в транзакцию или не включаться.</span><span class="sxs-lookup"><span data-stu-id="d00dd-164">This example demonstrates that commands that are submitted while a transaction is in progress can be included in the transaction or not included.</span></span>
<span data-ttu-id="d00dd-165">Только команды, использующие параметр *UseTransaction* , являются частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-165">Only commands that use the *UseTransaction* parameter are part of the transaction.</span></span>

<span data-ttu-id="d00dd-166">В первой и третьей командах **нового элемента** используется параметр *UseTransaction* .</span><span class="sxs-lookup"><span data-stu-id="d00dd-166">The first and third **New-Item** commands use the *UseTransaction* parameter.</span></span>
<span data-ttu-id="d00dd-167">Эти команды входят в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-167">These commands are part of the transaction.</span></span>
<span data-ttu-id="d00dd-168">Так как Вторая команда **New-Item** не использует параметр *UseTransaction* , она не является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-168">Because the second **New-Item** command does not use the *UseTransaction* parameter, it is not part of the transaction.</span></span>

<span data-ttu-id="d00dd-169">Первая команда dir отображает результат.</span><span class="sxs-lookup"><span data-stu-id="d00dd-169">The first dir command shows the effect.</span></span>
<span data-ttu-id="d00dd-170">Вторая команда **New-Item** выполняется немедленно, но первая и третья команды **нового элемента** не вступают в силу до тех пор, пока не будет выполнена фиксация транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-170">The second **New-Item** command is completed immediately, but the first and third **New-Item** commands are not effective until the transaction is committed.</span></span>

<span data-ttu-id="d00dd-171">Команда **Complete-Transaction** фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-171">The **Complete-Transaction** command commits the transaction.</span></span>
<span data-ttu-id="d00dd-172">В результате вторая команда dir показывает, что все новые элементы добавляются в реестр.</span><span class="sxs-lookup"><span data-stu-id="d00dd-172">As a result, the second dir command shows that all of the new items are added to the registry.</span></span>

### <span data-ttu-id="d00dd-173">Пример 7. откат транзакции, которая не завершается в указанное время</span><span class="sxs-lookup"><span data-stu-id="d00dd-173">Example 7: Roll back a transaction that does not finish in a specified time</span></span>

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

<span data-ttu-id="d00dd-174">Эта команда использует параметр *timeout* командлета **Start-Transaction** для запуска транзакции, которая должна быть выполнена в течение двух минут.</span><span class="sxs-lookup"><span data-stu-id="d00dd-174">This command uses the *Timeout* parameter of **Start-Transaction** to start a transaction that must be completed within two minutes.</span></span>
<span data-ttu-id="d00dd-175">Если транзакция не завершена по истечении времени ожидания, она автоматически откатывается.</span><span class="sxs-lookup"><span data-stu-id="d00dd-175">If the transaction is not finished when the time-out expires, it is rolled back automatically.</span></span>

<span data-ttu-id="d00dd-176">По истечении времени ожидания вы не получаете уведомления, но свойство **Status** объекта Transaction имеет значение откат и команды, использующие параметр *UseTransaction* , завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d00dd-176">When the time-out expires, you are not notified, but the **Status** property of the transaction object is set to RolledBack and commands that use the *UseTransaction* parameter fail.</span></span>

## <span data-ttu-id="d00dd-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d00dd-177">PARAMETERS</span></span>

### <span data-ttu-id="d00dd-178">Не зависит от</span><span class="sxs-lookup"><span data-stu-id="d00dd-178">-Independent</span></span>
<span data-ttu-id="d00dd-179">Указывает, что этот командлет запускает транзакцию, которая не зависит от выполняемых транзакций.</span><span class="sxs-lookup"><span data-stu-id="d00dd-179">Indicates that this cmdlet starts a transaction that is independent of any transactions in progress.</span></span>
<span data-ttu-id="d00dd-180">По умолчанию, если используется **Start-Transaction** во время выполнения другой транзакции, в выполняемую транзакцию добавляется новый подписчик.</span><span class="sxs-lookup"><span data-stu-id="d00dd-180">By default, if you use **Start-Transaction** while another transaction is in progress, a new subscriber is added to the transaction in progress.</span></span>
<span data-ttu-id="d00dd-181">Этот параметр действует только в том случае, если в рамках сеанса уже выполняется транзакция.</span><span class="sxs-lookup"><span data-stu-id="d00dd-181">This parameter has an effect only when a transaction is already in progress in the session.</span></span>

<span data-ttu-id="d00dd-182">По умолчанию, если при выполнении транзакции используется **Start-Transaction** , существующий объект транзакции повторно используется и число подписчиков увеличивается.</span><span class="sxs-lookup"><span data-stu-id="d00dd-182">By default, if you use **Start-Transaction** while a transaction is in progress, the existing transaction object is reused and the subscriber count is incremented.</span></span>
<span data-ttu-id="d00dd-183">Результат во многом похож на присоединение к исходной транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-183">The effect is much like joining the original transaction.</span></span>
<span data-ttu-id="d00dd-184">Команда Undo-Transaction выполняет откат всей транзакции.</span><span class="sxs-lookup"><span data-stu-id="d00dd-184">An Undo-Transaction command rolls back the whole the transaction.</span></span>
<span data-ttu-id="d00dd-185">Чтобы завершить транзакцию, необходимо выполнить команду Complete-Transaction для каждого подписчика.</span><span class="sxs-lookup"><span data-stu-id="d00dd-185">To complete the transaction, you must enter a Complete-Transaction command for each subscriber.</span></span>
<span data-ttu-id="d00dd-186">Так как обычно одновременно выполняющиеся транзакции связаны, значения по умолчанию в большинстве случаев достаточно.</span><span class="sxs-lookup"><span data-stu-id="d00dd-186">Because most transactions that are in progress at the same time are related, the default is sufficient for most uses.</span></span>

<span data-ttu-id="d00dd-187">Если указан *независимый* параметр, этот командлет создает новую транзакцию, которая может быть завершена или отменена без влияния на исходную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d00dd-187">If you specify the *Independent* parameter, this cmdlet creates a new transaction that can be completed or undone without affecting the original transaction.</span></span>
<span data-ttu-id="d00dd-188">Однако, поскольку одновременно может быть активна только одна транзакция, новую транзакцию необходимо завершить или откатить, прежде чем возобновлять работу с исходной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="d00dd-188">However, because only one transaction can be active at a time, you must complete or roll back the new transaction before resuming work on the original transaction.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d00dd-189">-RollbackPreference</span><span class="sxs-lookup"><span data-stu-id="d00dd-189">-RollbackPreference</span></span>
<span data-ttu-id="d00dd-190">Указывает условия, при которых транзакция автоматически откатывается.</span><span class="sxs-lookup"><span data-stu-id="d00dd-190">Specifies the conditions under which a transaction is automatically rolled back.</span></span>
<span data-ttu-id="d00dd-191">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="d00dd-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d00dd-192">Ошибка.</span><span class="sxs-lookup"><span data-stu-id="d00dd-192">Error.</span></span>
<span data-ttu-id="d00dd-193">транзакция откатывается автоматически, если происходит устранимая или неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d00dd-193">The transaction is rolled back automatically if a terminating or non-terminating error occurs.</span></span>
- <span data-ttu-id="d00dd-194">Терминатинжеррор.</span><span class="sxs-lookup"><span data-stu-id="d00dd-194">TerminatingError.</span></span>
<span data-ttu-id="d00dd-195">транзакция откатывается автоматически, если происходит неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d00dd-195">The transaction is rolled back automatically if a terminating error occurs.</span></span>
- <span data-ttu-id="d00dd-196">Никогда.</span><span class="sxs-lookup"><span data-stu-id="d00dd-196">Never.</span></span>
<span data-ttu-id="d00dd-197">транзакция никогда не откатывается автоматически.</span><span class="sxs-lookup"><span data-stu-id="d00dd-197">The transaction is never rolled back automatically.</span></span>

<span data-ttu-id="d00dd-198">Значение по умолчанию — Error.</span><span class="sxs-lookup"><span data-stu-id="d00dd-198">The default value is Error.</span></span>

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d00dd-199">-Timeout</span><span class="sxs-lookup"><span data-stu-id="d00dd-199">-Timeout</span></span>
<span data-ttu-id="d00dd-200">Указывает максимальный период времени в минутах, в течение которого транзакция может быть активна.</span><span class="sxs-lookup"><span data-stu-id="d00dd-200">Specifies the maximum time, in minutes, that the transaction is active.</span></span>
<span data-ttu-id="d00dd-201">По истечении времени ожидания транзакция откатывается автоматически.</span><span class="sxs-lookup"><span data-stu-id="d00dd-201">When the time-out expires, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="d00dd-202">По умолчанию для транзакций, запускаемых из командной строки, время ожидания не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="d00dd-202">By default, there is no time-out for transactions that are started at the command line.</span></span>
<span data-ttu-id="d00dd-203">Если транзакции запускаются с помощью сценария, время ожидания по умолчанию — 30 минут.</span><span class="sxs-lookup"><span data-stu-id="d00dd-203">When transactions are started by a script, the default time-out is 30 minutes.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d00dd-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d00dd-204">-Confirm</span></span>
<span data-ttu-id="d00dd-205">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d00dd-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d00dd-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d00dd-206">-WhatIf</span></span>
<span data-ttu-id="d00dd-207">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d00dd-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d00dd-208">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d00dd-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d00dd-209">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d00dd-209">CommonParameters</span></span>
<span data-ttu-id="d00dd-210">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d00dd-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d00dd-211">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d00dd-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d00dd-212">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d00dd-212">INPUTS</span></span>

### <span data-ttu-id="d00dd-213">Нет</span><span class="sxs-lookup"><span data-stu-id="d00dd-213">None</span></span>
<span data-ttu-id="d00dd-214">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="d00dd-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d00dd-215">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d00dd-215">OUTPUTS</span></span>

### <span data-ttu-id="d00dd-216">Нет</span><span class="sxs-lookup"><span data-stu-id="d00dd-216">None</span></span>
<span data-ttu-id="d00dd-217">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d00dd-217">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d00dd-218">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d00dd-218">NOTES</span></span>

## <span data-ttu-id="d00dd-219">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d00dd-219">RELATED LINKS</span></span>

[<span data-ttu-id="d00dd-220">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="d00dd-220">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="d00dd-221">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="d00dd-221">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="d00dd-222">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="d00dd-222">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="d00dd-223">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="d00dd-223">Use-Transaction</span></span>](Use-Transaction.md)

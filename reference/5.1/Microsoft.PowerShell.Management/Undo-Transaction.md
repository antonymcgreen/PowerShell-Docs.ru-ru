---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227834"
---
# <span data-ttu-id="513bc-103">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="513bc-103">Undo-Transaction</span></span>

## <span data-ttu-id="513bc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="513bc-104">SYNOPSIS</span></span>
<span data-ttu-id="513bc-105">Откатывает активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-105">Rolls back the active transaction.</span></span>

## <span data-ttu-id="513bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="513bc-106">SYNTAX</span></span>

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="513bc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="513bc-107">DESCRIPTION</span></span>
<span data-ttu-id="513bc-108">Командлет **Undo-Transaction** выполняет откат активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-108">The **Undo-Transaction** cmdlet rolls back the active transaction.</span></span>
<span data-ttu-id="513bc-109">При откате транзакции изменения, внесенные командами в транзакции, отбрасываются, а данные восстанавливаются в исходную форму.</span><span class="sxs-lookup"><span data-stu-id="513bc-109">When you roll back a transaction, the changes that were made by the commands in the transaction are discarded and the data is restored to its original form.</span></span>

<span data-ttu-id="513bc-110">Если транзакция включает несколько подписчиков, команда **Undo-Transaction** выполняет откат всей транзакции для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="513bc-110">If the transaction includes multiple subscribers, an **Undo-Transaction** command rolls back the whole transaction for all subscribers.</span></span>

<span data-ttu-id="513bc-111">По умолчанию откат транзакций выполняется автоматически в случае создания ошибки любой из команд в транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-111">By default, transactions are rolled back automatically if any command in the transaction generates an error.</span></span>
<span data-ttu-id="513bc-112">Однако транзакции могут быть запущены с другим приоритетом отката, и этот командлет можно использовать для отката активной транзакции в любое время.</span><span class="sxs-lookup"><span data-stu-id="513bc-112">However, transactions can be started by using a different rollback preference and you can use this cmdlet to roll back the active transaction at any time.</span></span>

<span data-ttu-id="513bc-113">Командлет **Undo-Transaction** является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="513bc-113">The **Undo-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="513bc-114">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="513bc-114">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="513bc-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="513bc-115">EXAMPLES</span></span>

### <span data-ttu-id="513bc-116">Пример 1. откат текущей транзакции</span><span class="sxs-lookup"><span data-stu-id="513bc-116">Example 1: Roll back the current transaction</span></span>

```
PS C:\> Undo-Transaction
```

<span data-ttu-id="513bc-117">Эта команда выполняет откат текущей активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-117">This command rolls back the current, active, transaction.</span></span>

### <span data-ttu-id="513bc-118">Пример 2. Запуск и откат транзакции</span><span class="sxs-lookup"><span data-stu-id="513bc-118">Example 2: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

<span data-ttu-id="513bc-119">В этом примере запускается транзакция, а затем выполняется ее откат.</span><span class="sxs-lookup"><span data-stu-id="513bc-119">This example starts a transaction and then rolls it back.</span></span>
<span data-ttu-id="513bc-120">В результате изменения не вносятся в реестр.</span><span class="sxs-lookup"><span data-stu-id="513bc-120">As a result, no changes are made to the registry.</span></span>

### <span data-ttu-id="513bc-121">Пример 3. откат транзакции для всех подписчиков</span><span class="sxs-lookup"><span data-stu-id="513bc-121">Example 3: Roll back a transaction for all subscribers</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

<span data-ttu-id="513bc-122">В этом примере показано, что когда любой подписчик откатывает транзакцию, выполняется откат всей транзакции для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="513bc-122">This example demonstrates that when any subscriber rolls back a transaction, the whole transaction is rolled back for all subscribers.</span></span>

<span data-ttu-id="513bc-123">Первая команда изменяет расположение на раздел реестра HKCU:\Software.</span><span class="sxs-lookup"><span data-stu-id="513bc-123">The first command changes the location to the HKCU:\Software registry key.</span></span>

<span data-ttu-id="513bc-124">Вторая команда запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-124">The second command starts a transaction.</span></span>

<span data-ttu-id="513bc-125">Третья команда использует командлет New-Item для создания нового раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="513bc-125">The third command uses the New-Item cmdlet to create a new registry key.</span></span>
<span data-ttu-id="513bc-126">Команда использует параметр *UseTransaction* для включения изменения в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-126">The command uses the *UseTransaction* parameter to include the change in the transaction.</span></span>

<span data-ttu-id="513bc-127">Четвертая команда использует командлет Get-Transaction для получения активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-127">The fourth command uses the Get-Transaction cmdlet to get the active transaction.</span></span>
<span data-ttu-id="513bc-128">Обратите внимание, что состояние — Active, а число подписчиков — 1.</span><span class="sxs-lookup"><span data-stu-id="513bc-128">Notice that the status is Active and the subscriber count is 1.</span></span>

<span data-ttu-id="513bc-129">Пятая команда использует команду Start-Transaction еще раз.</span><span class="sxs-lookup"><span data-stu-id="513bc-129">The fifth command uses the Start-Transaction command again.</span></span>
<span data-ttu-id="513bc-130">Как правило, запуск транзакции во время выполнения другой транзакции происходит, когда скрипт, используемый основной транзакцией, содержит собственную полную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-130">Typically, starting a transaction while another transaction is in progress occurs when a script that is used by the main transaction includes its own complete transaction.</span></span>
<span data-ttu-id="513bc-131">Этот пример выполняется в интерактивном режиме, чтобы его можно было изучить поэтапно.</span><span class="sxs-lookup"><span data-stu-id="513bc-131">This example is performed interactively so that you can examine it in stages.</span></span>
<span data-ttu-id="513bc-132">При выполнении команды **Start-Transaction** во время выполнения другой транзакции команды присоединяются к существующей транзакции в качестве нового подписчика, а число подписчиков увеличивается.</span><span class="sxs-lookup"><span data-stu-id="513bc-132">When you run a **Start-Transaction** command while another transaction is in progress, the commands join the existing transaction as a new subscriber and the subscriber count is incremented.</span></span>

<span data-ttu-id="513bc-133">Шестая команда использует командлет **Get-Transaction** для получения активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-133">The sixth command uses the **Get-Transaction** cmdlet to get the active transaction.</span></span>
<span data-ttu-id="513bc-134">Обратите внимание, что число подписчиков теперь 2.</span><span class="sxs-lookup"><span data-stu-id="513bc-134">Notice that the subscriber count is now 2.</span></span>

<span data-ttu-id="513bc-135">Седьмая команда использует для отката транзакции операцию **отмены-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="513bc-135">The seventh command uses **Undo-Transaction** to roll back the transaction.</span></span>
<span data-ttu-id="513bc-136">Этот командлет не возвращает никакие объекты.</span><span class="sxs-lookup"><span data-stu-id="513bc-136">This command does not return any objects.</span></span>

<span data-ttu-id="513bc-137">Последняя команда — это команда **Get-Transaction** , которая получает активный объект или, в данном случае, последнюю активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-137">The final command is a **Get-Transaction** command that gets the active, or in this case, the most recently active, transaction.</span></span>
<span data-ttu-id="513bc-138">Результаты показывают, что откат транзакции выполнен и число подписчиков равно 0, то есть, откат транзакции был выполнен для всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="513bc-138">The results show that the transaction is rolled back, and that the subscriber count is 0, showing that the transaction was rolled back for all subscribers.</span></span>

## <span data-ttu-id="513bc-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="513bc-139">PARAMETERS</span></span>

### <span data-ttu-id="513bc-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="513bc-140">-Confirm</span></span>
<span data-ttu-id="513bc-141">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="513bc-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="513bc-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="513bc-142">-WhatIf</span></span>
<span data-ttu-id="513bc-143">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="513bc-143">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="513bc-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="513bc-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="513bc-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="513bc-145">CommonParameters</span></span>
<span data-ttu-id="513bc-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="513bc-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="513bc-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="513bc-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="513bc-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="513bc-148">INPUTS</span></span>

### <span data-ttu-id="513bc-149">Нет</span><span class="sxs-lookup"><span data-stu-id="513bc-149">None</span></span>
<span data-ttu-id="513bc-150">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="513bc-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="513bc-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="513bc-151">OUTPUTS</span></span>

### <span data-ttu-id="513bc-152">Нет</span><span class="sxs-lookup"><span data-stu-id="513bc-152">None</span></span>
<span data-ttu-id="513bc-153">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="513bc-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="513bc-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="513bc-154">NOTES</span></span>

* <span data-ttu-id="513bc-155">Нельзя выполнить откат транзакции, которая была зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="513bc-155">You cannot roll back a transaction that has been committed.</span></span>

  <span data-ttu-id="513bc-156">Нельзя выполнить откат транзакции, которая не является активной.</span><span class="sxs-lookup"><span data-stu-id="513bc-156">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="513bc-157">Для отката другой, независимой транзакции необходимо сначала выполнить фиксацию или откат активной транзакции.</span><span class="sxs-lookup"><span data-stu-id="513bc-157">To roll back a different, independent transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="513bc-158">Откат транзакции завершает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-158">Rolling back the transaction ends the transaction.</span></span>
<span data-ttu-id="513bc-159">Чтобы использовать транзакцию снова, необходимо запустить новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="513bc-159">To use a transaction again, you must start a new transaction.</span></span>

## <span data-ttu-id="513bc-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="513bc-160">RELATED LINKS</span></span>

[<span data-ttu-id="513bc-161">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="513bc-161">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="513bc-162">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="513bc-162">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="513bc-163">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="513bc-163">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="513bc-164">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="513bc-164">Use-Transaction</span></span>](Use-Transaction.md)

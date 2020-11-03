---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228442"
---
# <span data-ttu-id="b0112-103">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="b0112-103">Complete-Transaction</span></span>

## <span data-ttu-id="b0112-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b0112-104">SYNOPSIS</span></span>
<span data-ttu-id="b0112-105">Фиксирует активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-105">Commits the active transaction.</span></span>

## <span data-ttu-id="b0112-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0112-106">SYNTAX</span></span>

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b0112-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0112-107">DESCRIPTION</span></span>
<span data-ttu-id="b0112-108">Командлет **Complete-Transaction** фиксирует активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-108">The **Complete-Transaction** cmdlet commits an active transaction.</span></span>
<span data-ttu-id="b0112-109">При фиксации активной транзакции ее команды завершаются, а данные, которые затрагиваются ими, изменяются.</span><span class="sxs-lookup"><span data-stu-id="b0112-109">When you commit a transaction, the commands in the transaction are finalized and the data affected by the commands is changed.</span></span>

<span data-ttu-id="b0112-110">Если транзакция содержит несколько подписчиков, для фиксации транзакции необходимо ввести одну команду **завершения транзакции** для каждой команды Start-Transaction.</span><span class="sxs-lookup"><span data-stu-id="b0112-110">If the transaction includes multiple subscribers, to commit the transaction, you must enter one **Complete-Transaction** command for every Start-Transaction command.</span></span>

<span data-ttu-id="b0112-111">Командлет **Complete-Transaction** является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0112-111">The **Complete-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="b0112-112">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="b0112-112">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="b0112-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b0112-113">EXAMPLES</span></span>

### <span data-ttu-id="b0112-114">Пример 1. Фиксация транзакции</span><span class="sxs-lookup"><span data-stu-id="b0112-114">Example 1: Commit a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

<span data-ttu-id="b0112-115">В этом примере показано, что происходит при использовании командлета **Complete-Transaction** для фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="b0112-115">This example shows what happens when you use the **Complete-Transaction** cmdlet to commit a transaction.</span></span>

<span data-ttu-id="b0112-116">Команда **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-116">The **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="b0112-117">Команда New-Item использует параметр *UseTransaction* для включения команды в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-117">The New-Item command uses the *UseTransaction* parameter to include the command in the transaction.</span></span>

<span data-ttu-id="b0112-118">Первая команда dir (Get-ChildItem) показывает, что новый элемент еще не добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="b0112-118">The first dir (Get-ChildItem) command shows that the new item has not yet been added to the registry.</span></span>

<span data-ttu-id="b0112-119">Команда **Complete-Transaction** фиксирует транзакцию, что делает изменение в реестре эффективным.</span><span class="sxs-lookup"><span data-stu-id="b0112-119">The **Complete-Transaction** command commits the transaction, which makes the registry change effective.</span></span>
<span data-ttu-id="b0112-120">В результате вторая команда dir показывает, что реестр изменился.</span><span class="sxs-lookup"><span data-stu-id="b0112-120">As a result, the second dir command shows that the registry is changed.</span></span>

### <span data-ttu-id="b0112-121">Пример 2. Фиксация транзакции, имеющей более одного подписчика</span><span class="sxs-lookup"><span data-stu-id="b0112-121">Example 2: Commit a transaction that has more than one subscriber</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="b0112-122">В этом примере показано, как использовать **полную транзакцию** для фиксации транзакции, имеющей более одного подписчика.</span><span class="sxs-lookup"><span data-stu-id="b0112-122">This example shows how to use **Complete-Transaction** to commit a transaction that has more than one subscriber.</span></span>

<span data-ttu-id="b0112-123">Чтобы зафиксировать транзакцию с несколькими подписчиками, необходимо ввести одну команду **завершения транзакции** для каждой команды **Start-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="b0112-123">To commit a multi-subscriber transaction, you must enter one **Complete-Transaction** command for every **Start-Transaction** command.</span></span>
<span data-ttu-id="b0112-124">Данные изменяются только после отправки последней команды **завершения транзакции** .</span><span class="sxs-lookup"><span data-stu-id="b0112-124">The data is changed only when the final **Complete-Transaction** command is submitted.</span></span>

<span data-ttu-id="b0112-125">Для демонстрации в этом примере показана последовательность команд, введенных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b0112-125">For demonstration purposes, this example shows a series of commands entered at the command line.</span></span>
<span data-ttu-id="b0112-126">На практике транзакции чаще выполняются в рамках сценариев, причем дополнительная транзакция выполняется функцией или вспомогательным сценарием, вызываемым основным сценарием.</span><span class="sxs-lookup"><span data-stu-id="b0112-126">In practice, transactions are likely to be run in scripts, with the secondary transaction being run by a function or helper script that is called by the main script.</span></span>

<span data-ttu-id="b0112-127">В этом примере команда **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-127">In this example, a **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="b0112-128">Команда **New-Item** с параметром *UseTransaction* добавляет ключ MyCompany в ключ программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b0112-128">A **New-Item** command with the *UseTransaction* parameter adds the MyCompany key to the Software key.</span></span>
<span data-ttu-id="b0112-129">Хотя командлет **New-Item** возвращает ключевой объект, данные в реестре еще не изменялись.</span><span class="sxs-lookup"><span data-stu-id="b0112-129">Although the **New-Item** cmdlet returns a key object, the data in the registry is not yet changed.</span></span>

<span data-ttu-id="b0112-130">Вторая команда **Start-Transaction** добавляет второй подписчик в существующую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-130">A second **Start-Transaction** command adds a second subscriber to the existing transaction.</span></span>
<span data-ttu-id="b0112-131">Командлет **Get-Transaction** подтверждает, что число подписчиков равно 2.</span><span class="sxs-lookup"><span data-stu-id="b0112-131">The **Get-Transaction** cmdlet confirms that the subscriber count is 2.</span></span>
<span data-ttu-id="b0112-132">Команда New-ItemProperty с параметром *UseTransaction* добавляет запись реестра в новый ключ MyCompany.</span><span class="sxs-lookup"><span data-stu-id="b0112-132">A New-ItemProperty command with the *UseTransaction* parameter adds a registry entry to the new MyCompany key.</span></span>
<span data-ttu-id="b0112-133">И в этом случае команда возвращает значение, но реестр не изменен.</span><span class="sxs-lookup"><span data-stu-id="b0112-133">Again, the command returns a value, but the registry is not changed.</span></span>

<span data-ttu-id="b0112-134">Первая команда **Complete-Transaction** сокращает число подписчиков на 1.</span><span class="sxs-lookup"><span data-stu-id="b0112-134">The first **Complete-Transaction** command reduces the subscriber count by 1.</span></span>
<span data-ttu-id="b0112-135">Это подтверждается командой **Get-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="b0112-135">This is confirmed by a **Get-Transaction** command.</span></span>
<span data-ttu-id="b0112-136">Однако данные не изменяются, как свидетельствует команда dir m \* ( **Get-ChildItem** ).</span><span class="sxs-lookup"><span data-stu-id="b0112-136">However, no data is changed, as evidenced by a dir m\* ( **Get-ChildItem** ) command.</span></span>

<span data-ttu-id="b0112-137">Вторая команда **Complete-Transaction** фиксирует всю транзакцию и изменяет данные в реестре.</span><span class="sxs-lookup"><span data-stu-id="b0112-137">The second **Complete-Transaction** command commits the entire transaction and changes the data in the registry.</span></span>
<span data-ttu-id="b0112-138">Это подтверждается второй командой dir m \*, которая показывает изменения.</span><span class="sxs-lookup"><span data-stu-id="b0112-138">This is confirmed by a second dir m\* command, which shows the changes.</span></span>

### <span data-ttu-id="b0112-139">Пример 3. выполнение транзакции, которая не изменяет данные</span><span class="sxs-lookup"><span data-stu-id="b0112-139">Example 3: Perform a transaction that does not change any data</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="b0112-140">В этом примере показано значение с помощью Get- \* Commands и других команд, которые не изменяют данные в транзакции.</span><span class="sxs-lookup"><span data-stu-id="b0112-140">This example shows the value of using Get-\* commands, and other commands that do not change data, in a transaction.</span></span>
<span data-ttu-id="b0112-141">Если \* в транзакции используется команда Get-Command, она получает объекты, которые являются частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="b0112-141">When a Get-\* command is used in a transaction, it gets the objects that are part of the transaction.</span></span>
<span data-ttu-id="b0112-142">Это позволяет предварительно просматривать изменения в транзакции перед их фиксацией.</span><span class="sxs-lookup"><span data-stu-id="b0112-142">This allows you to preview the changes in the transaction before the changes are committed.</span></span>

<span data-ttu-id="b0112-143">В этом примере запускается транзакция.</span><span class="sxs-lookup"><span data-stu-id="b0112-143">In this example, a transaction is started.</span></span>
<span data-ttu-id="b0112-144">Команда New-Item с параметром *UseTransaction* добавляет новый раздел в реестр как часть транзакции.</span><span class="sxs-lookup"><span data-stu-id="b0112-144">A New-Item command with the *UseTransaction* parameter adds a new key to the registry as part of the transaction.</span></span>

<span data-ttu-id="b0112-145">Поскольку новый раздел реестра не добавляется в реестр до тех пор, пока не будет запущена команда **Complete-Transaction** , в простой команде dir ( **Get-ChildItem** ) будет показан реестр без нового ключа.</span><span class="sxs-lookup"><span data-stu-id="b0112-145">Because the new registry key is not added to the registry until the **Complete-Transaction** command is run, a simple dir ( **Get-ChildItem** ) command shows the registry without the new key.</span></span>

<span data-ttu-id="b0112-146">Однако при добавлении параметра *UseTransaction* в команду dir команда становится частью транзакции и получает элементы в транзакции, даже если они еще не добавлены в данные.</span><span class="sxs-lookup"><span data-stu-id="b0112-146">However, when you add the *UseTransaction* parameter to the dir command, the command becomes part of the transaction, and it gets the items in the transaction even if they are not yet added to the data.</span></span>

## <span data-ttu-id="b0112-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0112-147">PARAMETERS</span></span>

### <span data-ttu-id="b0112-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b0112-148">-Confirm</span></span>
<span data-ttu-id="b0112-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b0112-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b0112-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b0112-150">-WhatIf</span></span>
<span data-ttu-id="b0112-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b0112-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b0112-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b0112-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b0112-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b0112-153">CommonParameters</span></span>
<span data-ttu-id="b0112-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0112-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0112-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b0112-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0112-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b0112-156">INPUTS</span></span>

### <span data-ttu-id="b0112-157">Нет</span><span class="sxs-lookup"><span data-stu-id="b0112-157">None</span></span>
<span data-ttu-id="b0112-158">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="b0112-158">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b0112-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b0112-159">OUTPUTS</span></span>

### <span data-ttu-id="b0112-160">Нет</span><span class="sxs-lookup"><span data-stu-id="b0112-160">None</span></span>
<span data-ttu-id="b0112-161">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b0112-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b0112-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b0112-162">NOTES</span></span>

* <span data-ttu-id="b0112-163">Зафиксированную транзакцию нельзя откатить, а транзакцию, для которой выполнен откат, — зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="b0112-163">You cannot roll back a transaction that has been committed, or commit a transaction that has been rolled back.</span></span>

  <span data-ttu-id="b0112-164">Нельзя выполнить откат транзакции, которая не является активной.</span><span class="sxs-lookup"><span data-stu-id="b0112-164">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="b0112-165">Чтобы откатить другую транзакцию, сначала нужно зафиксировать или откатить активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b0112-165">To roll back a different transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="b0112-166">По умолчанию, если какая-либо часть транзакции не может быть зафиксирована, например, если команда транзакции завершается ошибкой, откатывается вся транзакция.</span><span class="sxs-lookup"><span data-stu-id="b0112-166">By default, if any part of a transaction cannot be committed, such as when a command in the transaction results in an error, the entire transaction is rolled back.</span></span>

*

## <span data-ttu-id="b0112-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b0112-167">RELATED LINKS</span></span>

[<span data-ttu-id="b0112-168">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="b0112-168">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="b0112-169">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="b0112-169">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="b0112-170">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="b0112-170">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="b0112-171">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="b0112-171">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="b0112-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b0112-172">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="b0112-173">New-Item</span><span class="sxs-lookup"><span data-stu-id="b0112-173">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="b0112-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b0112-174">New-ItemProperty</span></span>](New-ItemProperty.md)

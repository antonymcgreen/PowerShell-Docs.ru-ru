---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209025"
---
# <span data-ttu-id="cba12-103">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-103">Get-Transaction</span></span>

## <span data-ttu-id="cba12-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cba12-104">SYNOPSIS</span></span>
<span data-ttu-id="cba12-105">Получает текущую (активную) транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-105">Gets the current (active) transaction.</span></span>

## <span data-ttu-id="cba12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cba12-106">SYNTAX</span></span>

```
Get-Transaction [<CommonParameters>]
```

## <span data-ttu-id="cba12-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cba12-107">DESCRIPTION</span></span>
<span data-ttu-id="cba12-108">Командлет **Get-Transaction** возвращает объект, представляющий текущую транзакцию в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cba12-108">The **Get-Transaction** cmdlet gets an object that represents the current transaction in the session.</span></span>

<span data-ttu-id="cba12-109">Он никогда не возвращает более одного объекта, так как одновременно активна только одна транзакция.</span><span class="sxs-lookup"><span data-stu-id="cba12-109">This cmdlet never returns more than one object, because only one transaction is active at a time.</span></span>
<span data-ttu-id="cba12-110">При запуске одной или нескольких независимых транзакций (с помощью независимого параметра Start-Transaction) активная транзакция становится активной и это транзакция, возвращаемая командлетом **Get-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="cba12-110">If you start one or more independent transactions (by using the Independent parameter of Start-Transaction), the most recently started transaction is active, and that is the transaction that **Get-Transaction** returns.</span></span>

<span data-ttu-id="cba12-111">При откате или фиксации всех активных транзакций этот командлет показывает транзакцию, которая была недавно активна в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cba12-111">When all active transactions have either been rolled back or committed, this cmdlet shows the transaction that was most recently active in the session.</span></span>

<span data-ttu-id="cba12-112">Этот командлет является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cba12-112">This cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="cba12-113">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="cba12-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="cba12-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="cba12-114">EXAMPLES</span></span>

### <span data-ttu-id="cba12-115">Пример 1. Получение текущей транзакции</span><span class="sxs-lookup"><span data-stu-id="cba12-115">Example 1: Get the current transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="cba12-116">Командлет Get-Transaction применяется для получения текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-116">This command uses the Get-Transaction cmdlet to get the current transaction.</span></span>

### <span data-ttu-id="cba12-117">Пример 2. Отображение свойств и методов объекта Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-117">Example 2: Show the properties and methods of the transaction object</span></span>

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

<span data-ttu-id="cba12-118">Эта команда использует командлет Get-Member для отображения свойств и методов объекта транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-118">This command uses the Get-Member cmdlet to show the properties and methods of the transaction object.</span></span>

### <span data-ttu-id="cba12-119">Пример 3. Отображение значений свойств для выполненной отката транзакции</span><span class="sxs-lookup"><span data-stu-id="cba12-119">Example 3: Show the property values of a rolled back transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

<span data-ttu-id="cba12-120">Эта команда показывает значения свойств объекта транзакции, для которой был выполнен откат.</span><span class="sxs-lookup"><span data-stu-id="cba12-120">This command shows the property values of a transaction object for a transaction that has been rolled back.</span></span>

### <span data-ttu-id="cba12-121">Пример 4. Отображение значений свойств зафиксированной транзакции</span><span class="sxs-lookup"><span data-stu-id="cba12-121">Example 4: Show the property values of a committed transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="cba12-122">Эта команда показывает значения свойств объекта транзакции, которая была зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="cba12-122">This command shows the property values of a transaction object for a transaction that has been committed.</span></span>

### <span data-ttu-id="cba12-123">Пример 5. запуск транзакции во время выполнения другого</span><span class="sxs-lookup"><span data-stu-id="cba12-123">Example 5: Start a transaction while another is in progress</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="cba12-124">В этом примере показано, как запуск транзакции влияет на объект транзакции во время выполнения другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-124">This example shows the effect on the transaction object of starting a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="cba12-125">Как правило, это происходит, когда скрипт, выполняющий транзакцию, включает в себя функцию или вызывает скрипт, который содержит другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-125">Typically, this happens when a script that runs a transaction includes a function or calls a script that contains another complete transaction.</span></span>

<span data-ttu-id="cba12-126">Если вторая команда **Start-Transaction** не содержит *независимый* параметр, командлет **Start-Transaction** не создает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-126">Unless the second **Start-Transaction** command includes the *Independent* parameter, **Start-Transaction** does not create a new transaction.</span></span>
<span data-ttu-id="cba12-127">Вместо этого командлет добавляет второго подписчика к исходной транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-127">Instead, it adds a second subscriber to the original transaction.</span></span>

<span data-ttu-id="cba12-128">Первая команда **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-128">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="cba12-129">Команда New-Item с параметром *UseTransaction* является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-129">A New-Item command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="cba12-130">Вторая команда **Start-Transaction** добавляет подписчика в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-130">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="cba12-131">Следующая команда New-Item также является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-131">The next New-Item command is also part of the transaction.</span></span>

<span data-ttu-id="cba12-132">Первая команда **Get-Transaction** показывает транзакцию с несколькими подписчиками.</span><span class="sxs-lookup"><span data-stu-id="cba12-132">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="cba12-133">Обратите внимание, что число подписчиков — 2.</span><span class="sxs-lookup"><span data-stu-id="cba12-133">Notice that the subscriber count is 2.</span></span>

<span data-ttu-id="cba12-134">Первая команда Complete-Transaction не фиксируют транзакцию, но оно уменьшает число подписчиков до 1.</span><span class="sxs-lookup"><span data-stu-id="cba12-134">The first Complete-Transaction command does not commit the transaction, but it reduces the subscriber count to 1.</span></span>

<span data-ttu-id="cba12-135">Вторая команда **Complete-Transaction** фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-135">The second **Complete-Transaction** command commits the transaction.</span></span>

### <span data-ttu-id="cba12-136">Пример 6. Запуск независимой транзакции во время выполнения другого</span><span class="sxs-lookup"><span data-stu-id="cba12-136">Example 6: Start an independent transaction while another is in progress</span></span>

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

<span data-ttu-id="cba12-137">В этом примере показано, как запуск независимой транзакции влияет на объект транзакции во время выполнения другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-137">This example shows the effect on the transaction object of starting an independent transaction while another transaction is in progress.</span></span>

<span data-ttu-id="cba12-138">Первая команда **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-138">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="cba12-139">Команда **нового элемента** с параметром *UseTransaction* является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-139">A **New-Item** command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="cba12-140">Вторая команда **Start-Transaction** добавляет подписчика в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-140">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="cba12-141">Следующая команда **New-Item** также является частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="cba12-141">The next **New-Item** command is also part of the transaction.</span></span>

<span data-ttu-id="cba12-142">Первая команда **Get-Transaction** показывает транзакцию с несколькими подписчиками.</span><span class="sxs-lookup"><span data-stu-id="cba12-142">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="cba12-143">Обратите внимание, что число подписчиков — 2.</span><span class="sxs-lookup"><span data-stu-id="cba12-143">Note that the subscriber count is 2.</span></span>

<span data-ttu-id="cba12-144">Команда **Complete-Transaction** сокращает число подписчиков до 1, но не фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-144">The **Complete-Transaction** command reduces the subscriber count to 1, but it does not commit the transaction.</span></span>

<span data-ttu-id="cba12-145">Вторая команда **Complete-Transaction** фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-145">The second **Complete-Transaction** command commits the transaction.</span></span>

## <span data-ttu-id="cba12-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cba12-146">PARAMETERS</span></span>

### <span data-ttu-id="cba12-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cba12-147">CommonParameters</span></span>
<span data-ttu-id="cba12-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cba12-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cba12-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cba12-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cba12-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cba12-150">INPUTS</span></span>

### <span data-ttu-id="cba12-151">Нет</span><span class="sxs-lookup"><span data-stu-id="cba12-151">None</span></span>
<span data-ttu-id="cba12-152">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="cba12-152">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="cba12-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cba12-153">OUTPUTS</span></span>

### <span data-ttu-id="cba12-154">System. Management. Automation. Пстрансактион</span><span class="sxs-lookup"><span data-stu-id="cba12-154">System.Management.Automation.PSTransaction</span></span>
<span data-ttu-id="cba12-155">Этот командлет возвращает объект, представляющий текущую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cba12-155">This cmdlet returns an object that represents the current transaction.</span></span>

## <span data-ttu-id="cba12-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cba12-156">NOTES</span></span>

## <span data-ttu-id="cba12-157">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cba12-157">RELATED LINKS</span></span>

[<span data-ttu-id="cba12-158">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-158">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="cba12-159">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-159">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="cba12-160">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-160">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="cba12-161">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="cba12-161">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="cba12-162">New-Item</span><span class="sxs-lookup"><span data-stu-id="cba12-162">New-Item</span></span>](New-Item.md)

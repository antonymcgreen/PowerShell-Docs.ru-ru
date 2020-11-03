---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227842"
---
# <span data-ttu-id="fd1d3-103">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-103">Use-Transaction</span></span>

## <span data-ttu-id="fd1d3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fd1d3-104">SYNOPSIS</span></span>
<span data-ttu-id="fd1d3-105">Добавляет блок сценариев в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-105">Adds the script block to the active transaction.</span></span>

## <span data-ttu-id="fd1d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd1d3-106">SYNTAX</span></span>

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="fd1d3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd1d3-107">DESCRIPTION</span></span>
<span data-ttu-id="fd1d3-108">Командлет **Use-Transaction** добавляет блок скрипта в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-108">The **Use-Transaction** cmdlet adds a script block to an active transaction.</span></span>
<span data-ttu-id="fd1d3-109">Это позволяет выполнять транзакции скриптов с помощью объектов Microsoft .NET Framework с поддержкой транзакций.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-109">This enables you to do transacted scripting by using transaction-enabled Microsoft .NET Framework objects.</span></span>
<span data-ttu-id="fd1d3-110">Этот блок сценариев может содержать только объекты Microsoft .NET Framework с поддержкой транзакций, например экземпляры класса Microsoft.PowerShell.Commands.Management.TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-110">The script block can contain only transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="fd1d3-111">Параметр *UseTransaction* , необязательный для большинства командлетов, является обязательным при использовании этого командлета.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-111">The *UseTransaction* parameter, which is optional for most cmdlets, is required when you use this cmdlet.</span></span>

<span data-ttu-id="fd1d3-112">**Use-Transaction**  — один из набора командлетов, которые поддерживают компонент транзакций в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-112">**Use-Transaction** is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="fd1d3-113">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="fd1d3-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="fd1d3-114">EXAMPLES</span></span>

### <span data-ttu-id="fd1d3-115">Пример 1. Выполнение скрипта с использованием объекта, поддерживающего транзакции</span><span class="sxs-lookup"><span data-stu-id="fd1d3-115">Example 1: Script by using a transaction-enabled object</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

<span data-ttu-id="fd1d3-116">В этом примере показано, как использовать командлет **Use-Transaction** , чтобы выполнить скрипт для поддерживающего транзакции объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-116">This example shows how to use **Use-Transaction** to script against a transaction-enabled .NET Framework object.</span></span>
<span data-ttu-id="fd1d3-117">В этом случае объект является объектом **TransactedString** .</span><span class="sxs-lookup"><span data-stu-id="fd1d3-117">In this case, the object is a **TransactedString** object.</span></span>

<span data-ttu-id="fd1d3-118">Первая команда использует командлет Start-Transaction для запуска транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-118">The first command uses the Start-Transaction cmdlet to start a transaction.</span></span>

<span data-ttu-id="fd1d3-119">Вторая команда использует команду New-Object для создания объекта **TransactedString** .</span><span class="sxs-lookup"><span data-stu-id="fd1d3-119">The second command uses the New-Object command to create a **TransactedString** object.</span></span>
<span data-ttu-id="fd1d3-120">Она хранит объект в переменной $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-120">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="fd1d3-121">Третья и четвертая команды используют метод **append** объекта **TransactedString** для добавления текста к значению $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-121">The third and fourth commands both use the **Append** method of the **TransactedString** object to add text to the value of $TransactedString.</span></span>
<span data-ttu-id="fd1d3-122">Одна команда входит в транзакцию,</span><span class="sxs-lookup"><span data-stu-id="fd1d3-122">One command is part of the transaction.</span></span>
<span data-ttu-id="fd1d3-123">а вторая — нет.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-123">The other command is not.</span></span>

<span data-ttu-id="fd1d3-124">Третья команда использует метод **append** строки транзакции для добавления Hello к значению $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-124">The third command uses the **Append** method of the transacted string to add Hello to the value of $TransactedString.</span></span>
<span data-ttu-id="fd1d3-125">Так как команда не является частью транзакции, изменение вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-125">Because the command is not part of the transaction, the change is applied immediately.</span></span>

<span data-ttu-id="fd1d3-126">Четвертая команда с помощью командлета **Use-Transaction** добавляет текст к строке в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-126">The fourth command uses **Use-Transaction** to add text to the string in the transaction.</span></span>
<span data-ttu-id="fd1d3-127">Команда использует метод **append** для добавления ", мира" к значению $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-127">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>
<span data-ttu-id="fd1d3-128">Команда заключается в фигурные скобки ( {} ), чтобы сделать ее блоком сценария.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-128">The command is enclosed in braces ( {} ) to make it a script block.</span></span>
<span data-ttu-id="fd1d3-129">В этой команде требуется параметр *UseTransaction* .</span><span class="sxs-lookup"><span data-stu-id="fd1d3-129">The *UseTransaction* parameter is required in this command.</span></span>

<span data-ttu-id="fd1d3-130">Пятая и шестая команды используют метод **ToString** объекта **TransactedString** для вывода значения **TransactedString** в виде строки.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-130">The fifth and sixth commands use the **ToString** method of the **TransactedString** object to display the value of the **TransactedString** as a string.</span></span>
<span data-ttu-id="fd1d3-131">И снова одна команда входит в транзакцию,</span><span class="sxs-lookup"><span data-stu-id="fd1d3-131">Again, one command is part of the transaction.</span></span>
<span data-ttu-id="fd1d3-132">а вторая — нет.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-132">The other transaction is not.</span></span>

<span data-ttu-id="fd1d3-133">Пятая команда использует метод **ToString** для вывода текущего значения переменной $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-133">The fifth command uses the **ToString** method to display the current value of the $TransactedString variable.</span></span>
<span data-ttu-id="fd1d3-134">Так как она не является частью транзакции, то отображает только текущее состояние строки.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-134">Because it is not part of the transaction, it displays only the current state of the string.</span></span>

<span data-ttu-id="fd1d3-135">Шестая команда использует командлет **Use-Transaction** для запуска той же команды внутри транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-135">The sixth command uses **Use-Transaction** to run the same command in the transaction.</span></span>
<span data-ttu-id="fd1d3-136">Так как команда не является частью, она отображает текущее значение строки внутри транзакции, так же, как предварительную версию изменений транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-136">Because the command is part of the transaction, it displays the current value of the string in the transaction, much like a preview of the transaction changes.</span></span>

<span data-ttu-id="fd1d3-137">Седьмая команда использует командлет Complete-Transaction для отправки транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-137">The seventh command uses the Complete-Transaction cmdlet to commit the transaction.</span></span>

<span data-ttu-id="fd1d3-138">Последняя команда использует метод **ToString** для вывода результирующего значения переменной в виде строки.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-138">The final command uses the **ToString** method to display the resulting value of the variable as a string.</span></span>

### <span data-ttu-id="fd1d3-139">Пример 2. Откат транзакции</span><span class="sxs-lookup"><span data-stu-id="fd1d3-139">Example 2: Roll back a transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

<span data-ttu-id="fd1d3-140">В этом примере показан результат отката транзакции, включающей команды **Use-Transaction** .</span><span class="sxs-lookup"><span data-stu-id="fd1d3-140">This example shows the effect of rolling back a transaction that includes **Use-Transaction** commands.</span></span>
<span data-ttu-id="fd1d3-141">Как и все команды в транзакции при ее откате, изменения транзакций удаляются, и данные остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-141">Like all commands in a transaction, when the transaction is rolled back, the transacted changes are discarded and the data is unchanged.</span></span>

<span data-ttu-id="fd1d3-142">Первая команда с помощью командлета **Start-Transaction** запускает транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-142">The first command uses **Start-Transaction** to start a transaction.</span></span>

<span data-ttu-id="fd1d3-143">Вторая команда с помощью командлета **New-Object** создает объект **TransactedString** .</span><span class="sxs-lookup"><span data-stu-id="fd1d3-143">The second command uses **New-Object** to create a **TransactedString** object.</span></span>
<span data-ttu-id="fd1d3-144">Она хранит объект в переменной $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-144">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="fd1d3-145">Третья команда, не входящая в транзакцию, использует метод **append** для добавления "Hello" к значению $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-145">The third command, which is not part of the transaction, uses the **Append** method to add "Hello" to the value of $TransactedString.</span></span>

<span data-ttu-id="fd1d3-146">Четвертая команда использует командлет **Use-Transaction** для запуска другой команды, использующей метод **Append** , внутри транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-146">The fourth command uses **Use-Transaction** to run another command that uses the **Append** method in the transaction.</span></span>
<span data-ttu-id="fd1d3-147">Команда использует метод **append** для добавления ", мира" к значению $TransactedString.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-147">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>

<span data-ttu-id="fd1d3-148">Пятая команда использует командлет Undo-Transaction для отката транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-148">The fifth command uses the Undo-Transaction cmdlet to roll back the transaction.</span></span>
<span data-ttu-id="fd1d3-149">В результате все команды, выполненные в рамках транзакции, отменяются.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-149">As a result, all commands performed in the transaction are reversed.</span></span>

<span data-ttu-id="fd1d3-150">Последняя команда использует метод **ToString** для вывода результирующего значения $TransactedString в виде строки.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-150">The final command uses the **ToString** method to display the resulting value of $TransactedString as a string.</span></span>
<span data-ttu-id="fd1d3-151">Из результатов видно, что к объекту применены только изменения, внесенные за рамками транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-151">The results show that only the changes that were made outside the transaction were applied to the object.</span></span>

## <span data-ttu-id="fd1d3-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd1d3-152">PARAMETERS</span></span>

### <span data-ttu-id="fd1d3-153">-TransactedScript</span><span class="sxs-lookup"><span data-stu-id="fd1d3-153">-TransactedScript</span></span>
<span data-ttu-id="fd1d3-154">Указывает блок сценариев, выполняемых в транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-154">Specifies the script block that is run in the transaction.</span></span>
<span data-ttu-id="fd1d3-155">Введите любой допустимый блок сценариев, заключенный в фигурные скобки( { } ).</span><span class="sxs-lookup"><span data-stu-id="fd1d3-155">Enter any valid script block enclosed in braces ( { } ).</span></span>
<span data-ttu-id="fd1d3-156">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-156">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd1d3-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-157">-UseTransaction</span></span>
<span data-ttu-id="fd1d3-158">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="fd1d3-159">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="fd1d3-160">Дополнительные сведения см. в разделе about_transactions.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-160">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd1d3-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fd1d3-161">CommonParameters</span></span>
<span data-ttu-id="fd1d3-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd1d3-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd1d3-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd1d3-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fd1d3-164">INPUTS</span></span>

### <span data-ttu-id="fd1d3-165">Нет</span><span class="sxs-lookup"><span data-stu-id="fd1d3-165">None</span></span>
<span data-ttu-id="fd1d3-166">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fd1d3-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fd1d3-167">OUTPUTS</span></span>

### <span data-ttu-id="fd1d3-168">PSObject</span><span class="sxs-lookup"><span data-stu-id="fd1d3-168">PSObject</span></span>
<span data-ttu-id="fd1d3-169">Этот командлет возвращает результат транзакции.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-169">This cmdlet returns the result of the transaction.</span></span>

## <span data-ttu-id="fd1d3-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fd1d3-170">NOTES</span></span>

* <span data-ttu-id="fd1d3-171">Параметр *UseTransaction* включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-171">The *UseTransaction* parameter includes the command in the active transaction.</span></span> <span data-ttu-id="fd1d3-172">Поскольку командлет **Use-Transaction** всегда используется в транзакциях, этот параметр необходим, чтобы команда **Use-Transaction** действовала.</span><span class="sxs-lookup"><span data-stu-id="fd1d3-172">Because the **Use-Transaction** cmdlet is always used in transactions, this parameter is required to make any **Use-Transaction** command effective.</span></span>

*

## <span data-ttu-id="fd1d3-173">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fd1d3-173">RELATED LINKS</span></span>

[<span data-ttu-id="fd1d3-174">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-174">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="fd1d3-175">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-175">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="fd1d3-176">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-176">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="fd1d3-177">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="fd1d3-177">Undo-Transaction</span></span>](Undo-Transaction.md)

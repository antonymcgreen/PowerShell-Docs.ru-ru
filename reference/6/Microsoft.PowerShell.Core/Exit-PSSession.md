---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession;
ms.openlocfilehash: 4e0b79cae4af290c64f579217a3731aaac401d6d
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209105"
---
# <span data-ttu-id="ca0a1-103">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="ca0a1-103">Exit-PSSession</span></span>

## <span data-ttu-id="ca0a1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ca0a1-104">SYNOPSIS</span></span>
<span data-ttu-id="ca0a1-105">Завершает интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="ca0a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca0a1-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="ca0a1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca0a1-107">DESCRIPTION</span></span>

<span data-ttu-id="ca0a1-108">Командлет **Exit-PSSession** завершает интерактивные сеансы, запущенные с помощью командлета Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-108">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="ca0a1-109">Можно также использовать ключевое слово **Exit** для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-109">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="ca0a1-110">Результат такой же, как и при использовании **Exit-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="ca0a1-110">The effect is the same as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="ca0a1-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="ca0a1-111">EXAMPLES</span></span>

### <span data-ttu-id="ca0a1-112">Пример 1. Запуск и завершение интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="ca0a1-112">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="ca0a1-113">Эти команды создают и затем завершают интерактивный сеанс с удаленным компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="ca0a1-114">Пример 2. Запуск и завершение интерактивного сеанса с помощью объекта PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="ca0a1-115">Эти команды запускают и останавливают интерактивный сеанс с компьютером Server01, использующим сеанс PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="ca0a1-115">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session ( **PSSession** ).</span></span>

<span data-ttu-id="ca0a1-116">Поскольку интерактивный сеанс запущен с помощью сеанса PowerShell, сеанс **PSSession** по-прежнему доступен по окончании интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-116">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="ca0a1-117">Если используется параметр *ComputerName* , команда **Enter-PSSession** создает временный сеанс, который закрывается по завершении интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-117">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="ca0a1-118">Первая команда использует командлет New-PSSession для создания **сеанса PSSession** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-118">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="ca0a1-119">Команда сохраняет **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-119">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="ca0a1-120">Вторая команда использует **Enter-PSSession** для запуска интерактивного сеанса с использованием сеанса **PSSession** в $s.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-120">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="ca0a1-121">Третья команда использует **Exit-PSSession** для прекращения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-121">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="ca0a1-122">Последняя команда отображает **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-122">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="ca0a1-123">Свойство **State** показывает, что **сеанс PSSession** по-прежнему открыт и доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="ca0a1-124">Пример 3. Использование ключевого слова Exit для завершения сеанса</span><span class="sxs-lookup"><span data-stu-id="ca0a1-124">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="ca0a1-125">В этом примере используется ключевое слово **Exit** для завершения интерактивного сеанса, запущенного с помощью команды **Enter-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="ca0a1-125">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession** .</span></span>
<span data-ttu-id="ca0a1-126">Ключевое слово **Exit** имеет тот же результат, что и при использовании **Exit-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="ca0a1-126">The **Exit** keyword has the same effect as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="ca0a1-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca0a1-127">PARAMETERS</span></span>

### <span data-ttu-id="ca0a1-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ca0a1-128">CommonParameters</span></span>

<span data-ttu-id="ca0a1-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca0a1-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca0a1-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca0a1-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ca0a1-131">INPUTS</span></span>

### <span data-ttu-id="ca0a1-132">Нет</span><span class="sxs-lookup"><span data-stu-id="ca0a1-132">None</span></span>

<span data-ttu-id="ca0a1-133">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ca0a1-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ca0a1-134">OUTPUTS</span></span>

### <span data-ttu-id="ca0a1-135">Нет</span><span class="sxs-lookup"><span data-stu-id="ca0a1-135">None</span></span>

<span data-ttu-id="ca0a1-136">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="ca0a1-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ca0a1-137">NOTES</span></span>

* <span data-ttu-id="ca0a1-138">Этот командлет принимает только общие параметры.</span><span class="sxs-lookup"><span data-stu-id="ca0a1-138">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="ca0a1-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ca0a1-139">RELATED LINKS</span></span>

[<span data-ttu-id="ca0a1-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="ca0a1-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="ca0a1-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="ca0a1-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="ca0a1-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ca0a1-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="ca0a1-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="ca0a1-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="ca0a1-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="ca0a1-147">Remove-PSSession</span></span>](Remove-PSSession.md)

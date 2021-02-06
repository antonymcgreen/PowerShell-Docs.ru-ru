---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession;
ms.openlocfilehash: b76f7dc87105318285c930b6cd2ae4ae10c2b0e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600178"
---
# <span data-ttu-id="4b697-102">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="4b697-102">Exit-PSSession</span></span>

## <span data-ttu-id="4b697-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b697-103">SYNOPSIS</span></span>
<span data-ttu-id="4b697-104">Завершает интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="4b697-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="4b697-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b697-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="4b697-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b697-106">DESCRIPTION</span></span>

<span data-ttu-id="4b697-107">Командлет **Exit-PSSession** завершает интерактивные сеансы, запущенные с помощью командлета Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="4b697-107">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="4b697-108">Можно также использовать ключевое слово **Exit** для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="4b697-108">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="4b697-109">Результат такой же, как и при использовании **Exit-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4b697-109">The effect is the same as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="4b697-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b697-110">EXAMPLES</span></span>

### <span data-ttu-id="4b697-111">Пример 1. Запуск и завершение интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="4b697-111">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="4b697-112">Эти команды создают и затем завершают интерактивный сеанс с удаленным компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="4b697-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="4b697-113">Пример 2. Запуск и завершение интерактивного сеанса с помощью объекта PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="4b697-114">Эти команды запускают и останавливают интерактивный сеанс с компьютером Server01, использующим сеанс PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="4b697-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="4b697-115">Поскольку интерактивный сеанс запущен с помощью сеанса PowerShell, сеанс **PSSession** по-прежнему доступен по окончании интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="4b697-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="4b697-116">Если используется параметр *ComputerName* , команда **Enter-PSSession** создает временный сеанс, который закрывается по завершении интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="4b697-116">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="4b697-117">Первая команда использует командлет New-PSSession для создания **сеанса PSSession** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="4b697-117">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="4b697-118">Команда сохраняет **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="4b697-118">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="4b697-119">Вторая команда использует **Enter-PSSession** для запуска интерактивного сеанса с использованием сеанса **PSSession** в $s.</span><span class="sxs-lookup"><span data-stu-id="4b697-119">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="4b697-120">Третья команда использует **Exit-PSSession** для прекращения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="4b697-120">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="4b697-121">Последняя команда отображает **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="4b697-121">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="4b697-122">Свойство **State** показывает, что **сеанс PSSession** по-прежнему открыт и доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="4b697-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="4b697-123">Пример 3. Использование ключевого слова Exit для завершения сеанса</span><span class="sxs-lookup"><span data-stu-id="4b697-123">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="4b697-124">В этом примере используется ключевое слово **Exit** для завершения интерактивного сеанса, запущенного с помощью команды **Enter-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4b697-124">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession**.</span></span>
<span data-ttu-id="4b697-125">Ключевое слово **Exit** имеет тот же результат, что и при использовании **Exit-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4b697-125">The **Exit** keyword has the same effect as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="4b697-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b697-126">PARAMETERS</span></span>

### <span data-ttu-id="4b697-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b697-127">CommonParameters</span></span>

<span data-ttu-id="4b697-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b697-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b697-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b697-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b697-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b697-130">INPUTS</span></span>

### <span data-ttu-id="4b697-131">None</span><span class="sxs-lookup"><span data-stu-id="4b697-131">None</span></span>

<span data-ttu-id="4b697-132">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="4b697-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="4b697-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b697-133">OUTPUTS</span></span>

### <span data-ttu-id="4b697-134">None</span><span class="sxs-lookup"><span data-stu-id="4b697-134">None</span></span>

<span data-ttu-id="4b697-135">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4b697-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4b697-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b697-136">NOTES</span></span>

* <span data-ttu-id="4b697-137">Этот командлет принимает только общие параметры.</span><span class="sxs-lookup"><span data-stu-id="4b697-137">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="4b697-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b697-138">RELATED LINKS</span></span>

[<span data-ttu-id="4b697-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="4b697-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="4b697-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="4b697-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="4b697-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4b697-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="4b697-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="4b697-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="4b697-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b697-146">Remove-PSSession</span></span>](Remove-PSSession.md)


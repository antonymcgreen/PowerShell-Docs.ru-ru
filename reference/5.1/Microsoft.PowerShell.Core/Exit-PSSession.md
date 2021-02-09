---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession;
ms.openlocfilehash: 1e0c8413a37a9b8877b6af9089ac311459ada20d
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975113"
---
# <span data-ttu-id="46317-103">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="46317-103">Exit-PSSession</span></span>

## <span data-ttu-id="46317-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="46317-104">Synopsis</span></span>
<span data-ttu-id="46317-105">Завершает интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="46317-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="46317-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="46317-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="46317-107">Описание</span><span class="sxs-lookup"><span data-stu-id="46317-107">Description</span></span>

<span data-ttu-id="46317-108">`Exit-PSSession`Командлет завершает интерактивные сеансы, запущенные с помощью `Enter-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="46317-108">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="46317-109">Можно также использовать `exit` ключевое слово для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="46317-109">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="46317-110">Результат такой же, как и при использовании `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="46317-110">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="46317-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="46317-111">Examples</span></span>

### <span data-ttu-id="46317-112">Пример 1. Запуск и завершение интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="46317-112">Example 1: Start and stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS C:\>
```

<span data-ttu-id="46317-113">Эти команды создают и затем завершают интерактивный сеанс с удаленным компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="46317-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="46317-114">Пример 2. Запуск и завершение интерактивного сеанса с помощью объекта PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="46317-115">Эти команды запускают и останавливают интерактивный сеанс с компьютером Server01, использующим сеанс Windows PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="46317-115">These commands start and stop an interactive session with the Server01 computer that uses a Windows PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="46317-116">Поскольку интерактивный сеанс запущен с помощью сеанса Windows PowerShell, сеанс **PSSession** по-прежнему доступен по окончании интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="46317-116">Because the interactive session was started by using a Windows PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="46317-117">Если используется параметр _ComputerName_ , `Enter-PSSession` создает временный сеанс, который закрывается по окончании интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="46317-117">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="46317-118">Первая команда использует `New-PSSession` командлет для создания **сеанса PSSession** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="46317-118">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="46317-119">Команда сохраняет **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="46317-119">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="46317-120">Вторая команда использует `Enter-PSSession` для запуска интерактивного сеанса с использованием **PSSession** в `$s` .</span><span class="sxs-lookup"><span data-stu-id="46317-120">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="46317-121">Третья команда использует `Exit-PSSession` для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="46317-121">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="46317-122">Последняя команда отображает **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="46317-122">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="46317-123">Свойство **State** показывает, что **сеанс PSSession** по-прежнему открыт и доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="46317-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="46317-124">Пример 3. Использование ключевого слова Exit для завершения сеанса</span><span class="sxs-lookup"><span data-stu-id="46317-124">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS C:\>
```

<span data-ttu-id="46317-125">В этом примере используется `exit` ключевое слово для завершения интерактивного сеанса, запущенного с помощью `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="46317-125">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="46317-126">`exit`Ключевое слово имеет тот же результат, что и при использовании `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="46317-126">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="46317-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="46317-127">Parameters</span></span>

### <span data-ttu-id="46317-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="46317-128">CommonParameters</span></span>

<span data-ttu-id="46317-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="46317-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="46317-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="46317-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="46317-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="46317-131">Inputs</span></span>

### <span data-ttu-id="46317-132">None</span><span class="sxs-lookup"><span data-stu-id="46317-132">None</span></span>

<span data-ttu-id="46317-133">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="46317-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="46317-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="46317-134">Outputs</span></span>

### <span data-ttu-id="46317-135">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="46317-135">None</span></span>

<span data-ttu-id="46317-136">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="46317-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="46317-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="46317-137">Notes</span></span>

<span data-ttu-id="46317-138">Этот командлет принимает только общие параметры.</span><span class="sxs-lookup"><span data-stu-id="46317-138">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="46317-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="46317-139">RELATED LINKS</span></span>

[<span data-ttu-id="46317-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="46317-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="46317-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="46317-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="46317-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="46317-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="46317-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="46317-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="46317-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="46317-147">Remove-PSSession</span></span>](Remove-PSSession.md)

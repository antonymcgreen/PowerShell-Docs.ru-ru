---
description: Объясняет доступность и назначение выходных потоков в PowerShell.
keywords: PowerShell, командлет
Locale: en-US
ms.date: 10/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_output_streams?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Output_Streams
ms.openlocfilehash: 2f63c468f6b0d82559fca354a8ce5c1343eb2084
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232826"
---
# <a name="about-output-streams"></a><span data-ttu-id="a1c3c-104">О выходных потоках</span><span class="sxs-lookup"><span data-stu-id="a1c3c-104">About output streams</span></span>

## <a name="short-description"></a><span data-ttu-id="a1c3c-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="a1c3c-105">Short description</span></span>
<span data-ttu-id="a1c3c-106">Объясняет доступность и назначение выходных потоков в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-106">Explains the availability and purpose of output streams in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a1c3c-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a1c3c-107">Long description</span></span>

<span data-ttu-id="a1c3c-108">PowerShell предоставляет несколько выходных потоков.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-108">PowerShell provides multiple output streams.</span></span> <span data-ttu-id="a1c3c-109">Потоки предоставляют каналы для различных типов сообщений.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-109">The streams provide channels for different types of messages.</span></span> <span data-ttu-id="a1c3c-110">Вы можете записывать данные в эти потоки с помощью связанного командлета или перенаправления.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-110">You can write to these streams using the associated cmdlet or redirection.</span></span> <span data-ttu-id="a1c3c-111">Дополнительные сведения см. в разделе [about_Redirection](about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="a1c3c-111">For more information, see [about_Redirection](about_Redirection.md).</span></span>

<span data-ttu-id="a1c3c-112">PowerShell поддерживает следующие выходные потоки.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-112">PowerShell supports the following output streams.</span></span>

| <span data-ttu-id="a1c3c-113">Вышестоящий #</span><span class="sxs-lookup"><span data-stu-id="a1c3c-113">Stream #</span></span> |      <span data-ttu-id="a1c3c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a1c3c-114">Description</span></span>       | <span data-ttu-id="a1c3c-115">Введено в</span><span class="sxs-lookup"><span data-stu-id="a1c3c-115">Introduced in</span></span>  |    <span data-ttu-id="a1c3c-116">Записать командлет</span><span class="sxs-lookup"><span data-stu-id="a1c3c-116">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="a1c3c-117">1</span><span class="sxs-lookup"><span data-stu-id="a1c3c-117">1</span></span>        | <span data-ttu-id="a1c3c-118">**Успешно выполненный** поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-118">**Success** stream</span></span>     | <span data-ttu-id="a1c3c-119">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-119">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="a1c3c-120">2</span><span class="sxs-lookup"><span data-stu-id="a1c3c-120">2</span></span>        | <span data-ttu-id="a1c3c-121">Поток **ошибок**</span><span class="sxs-lookup"><span data-stu-id="a1c3c-121">**Error** stream</span></span>       | <span data-ttu-id="a1c3c-122">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-122">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="a1c3c-123">3</span><span class="sxs-lookup"><span data-stu-id="a1c3c-123">3</span></span>        | <span data-ttu-id="a1c3c-124">Поток **предупреждений**</span><span class="sxs-lookup"><span data-stu-id="a1c3c-124">**Warning** stream</span></span>     | <span data-ttu-id="a1c3c-125">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-125">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="a1c3c-126">4</span><span class="sxs-lookup"><span data-stu-id="a1c3c-126">4</span></span>        | <span data-ttu-id="a1c3c-127">**Подробный** поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-127">**Verbose** stream</span></span>     | <span data-ttu-id="a1c3c-128">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-128">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="a1c3c-129">5</span><span class="sxs-lookup"><span data-stu-id="a1c3c-129">5</span></span>        | <span data-ttu-id="a1c3c-130">**Отладка** потока</span><span class="sxs-lookup"><span data-stu-id="a1c3c-130">**Debug** stream</span></span>       | <span data-ttu-id="a1c3c-131">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-131">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="a1c3c-132">6</span><span class="sxs-lookup"><span data-stu-id="a1c3c-132">6</span></span>        | <span data-ttu-id="a1c3c-133">**Информационный** поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-133">**Information** stream</span></span> | <span data-ttu-id="a1c3c-134">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-134">PowerShell 5.0</span></span> | `Write-Information` |
| <span data-ttu-id="a1c3c-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a1c3c-135">n/a</span></span>      | <span data-ttu-id="a1c3c-136">Поток **хода выполнения**</span><span class="sxs-lookup"><span data-stu-id="a1c3c-136">**Progress** stream</span></span>    | <span data-ttu-id="a1c3c-137">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a1c3c-137">PowerShell 3.0</span></span> | `Write-Progress`    |

> [!NOTE]
> <span data-ttu-id="a1c3c-138">Поток **хода выполнения** не поддерживает перенаправление.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-138">The **Progress** stream does not support redirection.</span></span>

## <a name="success-stream"></a><span data-ttu-id="a1c3c-139">Успешно выполненный поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-139">Success stream</span></span>

<span data-ttu-id="a1c3c-140">Поток **Success** — это поток по умолчанию для обычных, успешных результатов.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-140">The **Success** stream is the default stream for normal, successful results.</span></span>
<span data-ttu-id="a1c3c-141">Используйте `Write-Output` командлет для явного записи объектов в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-141">Use the `Write-Output` cmdlet to explicitly write objects to this stream.</span></span> <span data-ttu-id="a1c3c-142">Этот поток используется для передачи объектов через конвейер PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-142">This stream is used for passing objects through the PowerShell pipeline.</span></span> <span data-ttu-id="a1c3c-143">Поток **успешного выполнения** подключается к потоку **stdout** для собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-143">The **Success** stream is connected to the **stdout** stream for native applications.</span></span>

## <a name="error-stream"></a><span data-ttu-id="a1c3c-144">Поток ошибок</span><span class="sxs-lookup"><span data-stu-id="a1c3c-144">Error stream</span></span>

<span data-ttu-id="a1c3c-145">Поток **ошибок** является потоком по умолчанию для результатов ошибок.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-145">The **Error** stream is the default stream for error results.</span></span> <span data-ttu-id="a1c3c-146">Используйте `Write-Error` командлет для явной записи в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-146">Use the `Write-Error` cmdlet to explicitly write to this stream.</span></span> <span data-ttu-id="a1c3c-147">Поток **ошибок** подключен к потоку **stderr** для собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-147">The **Error** stream is connected to the **stderr** stream for native applications.</span></span> <span data-ttu-id="a1c3c-148">В большинстве случаев эти ошибки могут завершить конвейер выполнения.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-148">Under most conditions, these errors can terminate the execution pipeline.</span></span> <span data-ttu-id="a1c3c-149">Ошибки, записанные в этот поток, также добавляются в `$Error` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-149">Errors written to this stream are also added the the `$Error` automatic variable.</span></span> <span data-ttu-id="a1c3c-150">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a1c3c-150">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

## <a name="warning-stream"></a><span data-ttu-id="a1c3c-151">Поток предупреждений</span><span class="sxs-lookup"><span data-stu-id="a1c3c-151">Warning stream</span></span>

<span data-ttu-id="a1c3c-152">Поток **предупреждений** предназначен для состояний ошибки, которые менее серьезны, чем ошибки, записанные в поток **ошибок** .</span><span class="sxs-lookup"><span data-stu-id="a1c3c-152">The **Warning** stream is intended for error conditions that are less severe than errors written to the **Error** stream.</span></span> <span data-ttu-id="a1c3c-153">В нормальных условиях эти предупреждения не завершают выполнение.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-153">Under normal conditions, these warnings do not terminate execution.</span></span> <span data-ttu-id="a1c3c-154">Предупреждения не записываются в `$Error` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-154">Warnings are not written to the `$Error` automatic variable.</span></span> <span data-ttu-id="a1c3c-155">Используйте `Write-Warning` командлет для явной записи в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-155">Use the `Write-Warning` cmdlet to explicitly write to this stream.</span></span>

## <a name="verbose-stream"></a><span data-ttu-id="a1c3c-156">Подробный поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-156">Verbose stream</span></span>

<span data-ttu-id="a1c3c-157">**Подробный** поток предназначен для сообщений, помогающих пользователям устранять неполадки в работе команды в интерактивном режиме или сценарии.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-157">The **Verbose** stream is intended for messages that help users troubleshoot commands as they are run interactively or from a script.</span></span> <span data-ttu-id="a1c3c-158">Используйте `Write-Verbose` командлет для явного записи сообщений в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-158">Use the `Write-Verbose` cmdlet to explicitly write messages to this stream.</span></span> <span data-ttu-id="a1c3c-159">Многие командлеты предоставляют подробные выходные данные, которые полезны для понимания внутренних операций командлета.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-159">Many cmdlets provide verbose output that is useful for understanding the internal workings of the cmdlet.</span></span> <span data-ttu-id="a1c3c-160">Подробные сообщения выводятся только при использовании `-Verbose` общего параметра.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-160">The verbose messages are output only when you use the `-Verbose` common parameter.</span></span> <span data-ttu-id="a1c3c-161">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a1c3c-161">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="debug-stream"></a><span data-ttu-id="a1c3c-162">Поток отладки</span><span class="sxs-lookup"><span data-stu-id="a1c3c-162">Debug stream</span></span>

<span data-ttu-id="a1c3c-163">Поток **отладки** используется для сообщений, которые помогают скриптам понять причину сбоя в коде.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-163">The **Debug** stream is used for messages that help scripters understand why their code is failing.</span></span> <span data-ttu-id="a1c3c-164">Используйте `Write-Debug` командлет для явной записи в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-164">Use the `Write-Debug` cmdlet to explicitly write to this stream.</span></span> <span data-ttu-id="a1c3c-165">Сообщения отладки выводятся только при использовании `-Debug` общего параметра.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-165">The debug messages are output only when you use the `-Debug` common parameter.</span></span> <span data-ttu-id="a1c3c-166">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a1c3c-166">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="a1c3c-167">Отладочные сообщения предназначены для разработчиков скриптов и командлетов, чем конечные пользователи.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-167">Debug messages are intended for script and cmdlet developers more than end users.</span></span> <span data-ttu-id="a1c3c-168">Эти отладочные сообщения могут содержать внутренние сведения, необходимые для глубокого устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-168">These debug messages can contain internal details necessary for deep troubleshooting.</span></span>

## <a name="information-stream"></a><span data-ttu-id="a1c3c-169">Информационный поток</span><span class="sxs-lookup"><span data-stu-id="a1c3c-169">Information stream</span></span>

<span data-ttu-id="a1c3c-170">**Информационный** поток предназначен для предоставления сообщения, помогающего пользователю понять, что делает сценарий.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-170">The **Information** stream is intended to provide message that help a user understand what a script is doing.</span></span> <span data-ttu-id="a1c3c-171">Он также может использоваться разработчиками в качестве дополнительного потока, используемого для передачи информации с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-171">It can also be used by developers as an additional stream used to pass information through PowerShell.</span></span> <span data-ttu-id="a1c3c-172">Разработчик может пометить потоковые данные и иметь определенную обработку для этого потока.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-172">The developer can tag stream data and have specific handling for that stream.</span></span> <span data-ttu-id="a1c3c-173">Используйте `Write-Information` командлет для явной записи в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-173">Use the `Write-Information` cmdlet to explicitly write to this stream.</span></span>

## <a name="progress-stream"></a><span data-ttu-id="a1c3c-174">Поток хода выполнения</span><span class="sxs-lookup"><span data-stu-id="a1c3c-174">Progress stream</span></span>

<span data-ttu-id="a1c3c-175">Поток **хода выполнения** используется для сообщений, которые сообщают о ходе выполнения команд и скриптов дольше.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-175">The **Progress** stream is used for messages that communicate progress in longer running commands and scripts.</span></span> <span data-ttu-id="a1c3c-176">Используйте `Write-Progress` командлет для явного записи сообщений в этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-176">Use the `Write-Progress` cmdlet to explicitly write messages to this stream.</span></span> <span data-ttu-id="a1c3c-177">Поток **хода выполнения** не поддерживает перенаправление.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-177">The **Progress** stream does not support redirection.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1c3c-178">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a1c3c-178">See also</span></span>

- [<span data-ttu-id="a1c3c-179">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a1c3c-179">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="a1c3c-180">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="a1c3c-180">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="a1c3c-181">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a1c3c-181">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="a1c3c-182">Write-Information</span><span class="sxs-lookup"><span data-stu-id="a1c3c-182">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="a1c3c-183">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a1c3c-183">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="a1c3c-184">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a1c3c-184">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="a1c3c-185">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a1c3c-185">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="a1c3c-186">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a1c3c-186">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="a1c3c-187">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a1c3c-187">about_CommonParameters</span></span>](about_CommonParameters.md)
- [<span data-ttu-id="a1c3c-188">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a1c3c-188">about_Redirection</span></span>](about_Redirection.md)
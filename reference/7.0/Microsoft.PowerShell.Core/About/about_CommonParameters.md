---
description: Описывает параметры, которые можно использовать с любым командлетом.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 949fabca6052a75d2cc4f8cf71e0a88b170a3b36
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231825"
---
# <a name="about-commonparameters"></a><span data-ttu-id="b7e43-104">О Общиепараметры</span><span class="sxs-lookup"><span data-stu-id="b7e43-104">About CommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="b7e43-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b7e43-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b7e43-106">Описывает параметры, которые можно использовать с любым командлетом.</span><span class="sxs-lookup"><span data-stu-id="b7e43-106">Describes the parameters that can be used with any cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="b7e43-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b7e43-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b7e43-108">Общие параметры — это набор параметров командлета, которые можно использовать с любым командлетом.</span><span class="sxs-lookup"><span data-stu-id="b7e43-108">The common parameters are a set of cmdlet parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="b7e43-109">Они реализуются с помощью PowerShell, а не разработчика командлетов и автоматически доступны любому командлету.</span><span class="sxs-lookup"><span data-stu-id="b7e43-109">They're implemented by PowerShell, not by the cmdlet developer, and they're automatically available to any cmdlet.</span></span>

<span data-ttu-id="b7e43-110">Общие параметры можно использовать с любыми командлетами, но они могут не влиять на все командлеты.</span><span class="sxs-lookup"><span data-stu-id="b7e43-110">You can use the common parameters with any cmdlet, but they might not have an effect on all cmdlets.</span></span> <span data-ttu-id="b7e43-111">Например, если командлет не создает подробные выходные данные, использование параметра **verbose** Common не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b7e43-111">For example, if a cmdlet doesn't generate any verbose output, using the **Verbose** common parameter has no effect.</span></span>

<span data-ttu-id="b7e43-112">Общие параметры также доступны для расширенных функций, использующих атрибут **CmdletBinding** или **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-112">The common parameters are also available on advanced functions that use the **CmdletBinding** attribute or the **Parameter** attribute.</span></span>

<span data-ttu-id="b7e43-113">Несколько общих параметров переопределяют системные значения по умолчанию или настройки, заданные с помощью переменных предпочтений PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7e43-113">Several common parameters override system defaults or preferences that you set by using the PowerShell preference variables.</span></span> <span data-ttu-id="b7e43-114">В отличие от привилегированных переменных, общие параметры влияют только на те команды, в которых они используются.</span><span class="sxs-lookup"><span data-stu-id="b7e43-114">Unlike the preference variables, the common parameters affect only the commands in which they're used.</span></span>

<span data-ttu-id="b7e43-115">Дополнительные сведения см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b7e43-115">For more information, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

<span data-ttu-id="b7e43-116">В следующем списке отображаются общие параметры.</span><span class="sxs-lookup"><span data-stu-id="b7e43-116">The following list displays the common parameters.</span></span> <span data-ttu-id="b7e43-117">Их псевдонимы перечислены в скобках.</span><span class="sxs-lookup"><span data-stu-id="b7e43-117">Their aliases are listed in parentheses.</span></span>

- <span data-ttu-id="b7e43-118">**Debug** (db)</span><span class="sxs-lookup"><span data-stu-id="b7e43-118">**Debug** (db)</span></span>
- <span data-ttu-id="b7e43-119">**ErrorAction** (EA)</span><span class="sxs-lookup"><span data-stu-id="b7e43-119">**ErrorAction** (ea)</span></span>
- <span data-ttu-id="b7e43-120">**ErrorVariable** (EV)</span><span class="sxs-lookup"><span data-stu-id="b7e43-120">**ErrorVariable** (ev)</span></span>
- <span data-ttu-id="b7e43-121">**InformationAction** (инфа)</span><span class="sxs-lookup"><span data-stu-id="b7e43-121">**InformationAction** (infa)</span></span>
- <span data-ttu-id="b7e43-122">**InformationVariable** (IV)</span><span class="sxs-lookup"><span data-stu-id="b7e43-122">**InformationVariable** (iv)</span></span>
- <span data-ttu-id="b7e43-123">**Переменная** (OV)</span><span class="sxs-lookup"><span data-stu-id="b7e43-123">**OutVariable** (ov)</span></span>
- <span data-ttu-id="b7e43-124">**Буфер** (OB)</span><span class="sxs-lookup"><span data-stu-id="b7e43-124">**OutBuffer** (ob)</span></span>
- <span data-ttu-id="b7e43-125">**PipelineVariable** (ПС)</span><span class="sxs-lookup"><span data-stu-id="b7e43-125">**PipelineVariable** (pv)</span></span>
- <span data-ttu-id="b7e43-126">**Verbose** (VB)</span><span class="sxs-lookup"><span data-stu-id="b7e43-126">**Verbose** (vb)</span></span>
- <span data-ttu-id="b7e43-127">**WarningAction** (штат Вашингтон)</span><span class="sxs-lookup"><span data-stu-id="b7e43-127">**WarningAction** (wa)</span></span>
- <span data-ttu-id="b7e43-128">**WarningVariable** (WV)</span><span class="sxs-lookup"><span data-stu-id="b7e43-128">**WarningVariable** (wv)</span></span>

<span data-ttu-id="b7e43-129">Параметры **действия** — это значения типа **действие** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-129">The **Action** parameters are **ActionPreference** type values.</span></span>
<span data-ttu-id="b7e43-130">**Действие** — это перечисление со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="b7e43-130">**ActionPreference** is an enumeration with the following values:</span></span>

| <span data-ttu-id="b7e43-131">name</span><span class="sxs-lookup"><span data-stu-id="b7e43-131">Name</span></span>             | <span data-ttu-id="b7e43-132">Значение</span><span class="sxs-lookup"><span data-stu-id="b7e43-132">Value</span></span> |
|------------------|-------|
| <span data-ttu-id="b7e43-133">Приостановить</span><span class="sxs-lookup"><span data-stu-id="b7e43-133">Suspend</span></span>          | <span data-ttu-id="b7e43-134">5</span><span class="sxs-lookup"><span data-stu-id="b7e43-134">5</span></span>     |
| <span data-ttu-id="b7e43-135">Игнорировать</span><span class="sxs-lookup"><span data-stu-id="b7e43-135">Ignore</span></span>           | <span data-ttu-id="b7e43-136">4</span><span class="sxs-lookup"><span data-stu-id="b7e43-136">4</span></span>     |
| <span data-ttu-id="b7e43-137">Inquire</span><span class="sxs-lookup"><span data-stu-id="b7e43-137">Inquire</span></span>          | <span data-ttu-id="b7e43-138">3</span><span class="sxs-lookup"><span data-stu-id="b7e43-138">3</span></span>     |
| <span data-ttu-id="b7e43-139">Продолжить</span><span class="sxs-lookup"><span data-stu-id="b7e43-139">Continue</span></span>         | <span data-ttu-id="b7e43-140">2</span><span class="sxs-lookup"><span data-stu-id="b7e43-140">2</span></span>     |
| <span data-ttu-id="b7e43-141">Стоп</span><span class="sxs-lookup"><span data-stu-id="b7e43-141">Stop</span></span>             | <span data-ttu-id="b7e43-142">1</span><span class="sxs-lookup"><span data-stu-id="b7e43-142">1</span></span>     |
| <span data-ttu-id="b7e43-143">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="b7e43-143">SilentlyContinue</span></span> | <span data-ttu-id="b7e43-144">0</span><span class="sxs-lookup"><span data-stu-id="b7e43-144">0</span></span>     |

<span data-ttu-id="b7e43-145">Можно использовать имя или значение с параметром.</span><span class="sxs-lookup"><span data-stu-id="b7e43-145">You may use the name or the value with the parameter.</span></span>

<span data-ttu-id="b7e43-146">Помимо общих параметров, многие командлеты предлагают параметры устранения рисков.</span><span class="sxs-lookup"><span data-stu-id="b7e43-146">In addition to the common parameters, many cmdlets offer risk mitigation parameters.</span></span> <span data-ttu-id="b7e43-147">Командлеты, которые подразумевают риск для системы или для пользовательских данных, обычно предлагают эти параметры.</span><span class="sxs-lookup"><span data-stu-id="b7e43-147">Cmdlets that involve risk to the system or to user data usually offer these parameters.</span></span>

<span data-ttu-id="b7e43-148">Параметры устранения рисков:</span><span class="sxs-lookup"><span data-stu-id="b7e43-148">The risk mitigation parameters are:</span></span>

- <span data-ttu-id="b7e43-149">**WhatIf** (Wi-in)</span><span class="sxs-lookup"><span data-stu-id="b7e43-149">**WhatIf** (wi)</span></span>
- <span data-ttu-id="b7e43-150">**Подтверждение** (CF)</span><span class="sxs-lookup"><span data-stu-id="b7e43-150">**Confirm** (cf)</span></span>

### <a name="common-parameter-descriptions"></a><span data-ttu-id="b7e43-151">ОБЩИЕ ОПИСАНИЯ ПАРАМЕТРОВ</span><span class="sxs-lookup"><span data-stu-id="b7e43-151">COMMON PARAMETER DESCRIPTIONS</span></span>

#### <a name="debug"></a><span data-ttu-id="b7e43-152">Отладка</span><span class="sxs-lookup"><span data-stu-id="b7e43-152">Debug</span></span>

<span data-ttu-id="b7e43-153">Отображает сведения на уровне программиста об операции, выполняемой командой.</span><span class="sxs-lookup"><span data-stu-id="b7e43-153">Displays programmer-level detail about the operation done by the command.</span></span> <span data-ttu-id="b7e43-154">Этот параметр работает только в том случае, если команда создает сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="b7e43-154">This parameter works only when the command generates a debugging message.</span></span> <span data-ttu-id="b7e43-155">Например, этот параметр работает, если команда содержит `Write-Debug` командлет.</span><span class="sxs-lookup"><span data-stu-id="b7e43-155">For example, this parameter works when a command contains the `Write-Debug` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-156">По умолчанию сообщения отладки не отображаются, так как значение `$DebugPreference` переменной — **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-156">By default, debugging messages aren't displayed because the value of the `$DebugPreference` variable is **SilentlyContinue** .</span></span>

<span data-ttu-id="b7e43-157">В интерактивном режиме параметр **Debug** переопределяет значение `$DebugPreference` переменной для текущей команды, устанавливая для параметра значение "запрос" `$DebugPreference` . **Inquire**</span><span class="sxs-lookup"><span data-stu-id="b7e43-157">In interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Inquire** .</span></span>

<span data-ttu-id="b7e43-158">В неинтерактивном режиме параметр **Debug** переопределяет значение `$DebugPreference` переменной для текущей команды, устанавливая `$DebugPreference` для значение **Continue** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-158">In non-interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Continue** .</span></span>

<span data-ttu-id="b7e43-159">`-Debug:$true` имеет тот же результат, что и `-Debug` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-159">`-Debug:$true` has the same effect as `-Debug`.</span></span> <span data-ttu-id="b7e43-160">Используйте, `-Debug:$false` чтобы подавлять отображение отладочных сообщений `$DebugPreference` , если не **SilentlyContinue** , что является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7e43-160">Use `-Debug:$false` to suppress the display of debugging messages when `$DebugPreference` isn't **SilentlyContinue** , which is the default.</span></span>

#### <a name="erroraction"></a><span data-ttu-id="b7e43-161">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="b7e43-161">ErrorAction</span></span>

<span data-ttu-id="b7e43-162">Определяет реакцию командлета на неустранимую ошибку команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-162">Determines how the cmdlet responds to a non-terminating error from the command.</span></span>
<span data-ttu-id="b7e43-163">Этот параметр работает только в том случае, если команда создает неустранимую ошибку, например из `Write-Error` командлета.</span><span class="sxs-lookup"><span data-stu-id="b7e43-163">This parameter works only when the command generates a non-terminating error, such as those from the `Write-Error` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-164">Параметр **ErrorAction** переопределяет значение `$ErrorActionPreference` переменной для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-164">The **ErrorAction** parameter overrides the value of the `$ErrorActionPreference` variable for the current command.</span></span> <span data-ttu-id="b7e43-165">Так как значение переменной по умолчанию `$ErrorActionPreference` **продолжится** , отображаются сообщения об ошибках и выполнение продолжается, если не используется параметр **ErrorAction** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-165">Because the default value of the `$ErrorActionPreference` variable is **Continue** , error messages are displayed and execution continues unless you use the **ErrorAction** parameter.</span></span>

<span data-ttu-id="b7e43-166">Параметр **ErrorAction** не влияет на завершающие ошибки (такие как отсутствующие данные, недопустимые параметры или недостаточные разрешения), препятствующие успешному выполнению команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-166">The **ErrorAction** parameter has no effect on terminating errors (such as missing data, parameters that aren't valid, or insufficient permissions) that prevent a command from completing successfully.</span></span>

<span data-ttu-id="b7e43-167">`-ErrorAction:Continue` Отобразите сообщение об ошибке и продолжит выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-167">`-ErrorAction:Continue` display the error message and continues executing the command.</span></span> <span data-ttu-id="b7e43-168">Значение по умолчанию — `Continue`.</span><span class="sxs-lookup"><span data-stu-id="b7e43-168">`Continue` is the default.</span></span>

<span data-ttu-id="b7e43-169">`-ErrorAction:Ignore` Подавляет сообщение об ошибке и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-169">`-ErrorAction:Ignore` suppresses the error message and continues executing the command.</span></span> <span data-ttu-id="b7e43-170">В отличие от **SilentlyContinue** , **Ignore** не добавляет сообщение об ошибке в `$Error` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="b7e43-170">Unlike **SilentlyContinue** , **Ignore** doesn't add the error message to the `$Error` automatic variable.</span></span> <span data-ttu-id="b7e43-171">Значение **Ignore** введено в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b7e43-171">The **Ignore** value is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="b7e43-172">`-ErrorAction:Inquire` Отображает сообщение об ошибке и запрашивает подтверждение перед продолжением выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7e43-172">`-ErrorAction:Inquire` displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="b7e43-173">Это значение используется редко.</span><span class="sxs-lookup"><span data-stu-id="b7e43-173">This value is rarely used.</span></span>

<span data-ttu-id="b7e43-174">`-ErrorAction:SilentlyContinue` Подавляет сообщение об ошибке и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-174">`-ErrorAction:SilentlyContinue` suppresses the error message and continues executing the command.</span></span>

<span data-ttu-id="b7e43-175">`-ErrorAction:Stop` Отображает сообщение об ошибке и останавливает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-175">`-ErrorAction:Stop` displays the error message and stops executing the command.</span></span>

<span data-ttu-id="b7e43-176">`-ErrorAction:Suspend` доступно только для рабочих процессов, которые не поддерживаются в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b7e43-176">`-ErrorAction:Suspend` is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-177">Параметр **ErrorAction** переопределяет, но не заменяет значение `$ErrorAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="b7e43-177">The **ErrorAction** parameter overrides, but does not replace the value of the `$ErrorAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="errorvariable"></a><span data-ttu-id="b7e43-178">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="b7e43-178">ErrorVariable</span></span>

<span data-ttu-id="b7e43-179">**ErrorVariable** хранит сообщения об ошибках команды в указанной переменной и в `$Error` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-179">**ErrorVariable** stores error messages about the command in the specified variable and in the `$Error` automatic variable.</span></span> <span data-ttu-id="b7e43-180">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="b7e43-180">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md)</span></span>

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-181">По умолчанию новые сообщения об ошибках переписывают сообщения об ошибках, которые уже хранятся в переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-181">By default, new error messages overwrite error messages that are already stored in the variable.</span></span> <span data-ttu-id="b7e43-182">Чтобы добавить сообщение об ошибке в содержимое переменной, введите знак плюс ( `+` ) перед именем переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-182">To append the error message to the variable content, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="b7e43-183">Например, следующая команда создает `$a` переменную, а затем сохраняет в ней ошибки:</span><span class="sxs-lookup"><span data-stu-id="b7e43-183">For example, the following command creates the `$a` variable and then stores any errors in it:</span></span>

```powershell
Get-Process -Id 6 -ErrorVariable a
```

<span data-ttu-id="b7e43-184">Следующая команда добавляет любые сообщения об ошибках в `$a` переменную:</span><span class="sxs-lookup"><span data-stu-id="b7e43-184">The following command adds any error messages to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

<span data-ttu-id="b7e43-185">Следующая команда отображает содержимое `$a` :</span><span class="sxs-lookup"><span data-stu-id="b7e43-185">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="b7e43-186">Этот параметр можно использовать для создания переменной, которая содержит только сообщения об ошибках из конкретных команд и не влияет на поведение `$Error` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-186">You can use this parameter to create a variable that contains only error messages from specific commands and does not affect the behavior of the `$Error` automatic variable.</span></span> <span data-ttu-id="b7e43-187">`$Error`Автоматическая переменная содержит сообщения об ошибках всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b7e43-187">The `$Error` automatic variable contains error messages from all the commands in the session.</span></span> <span data-ttu-id="b7e43-188">Можно использовать нотацию массива, например `$a[0]` или, `$error[1,2]` для обращения к конкретным ошибкам, хранящимся в переменных.</span><span class="sxs-lookup"><span data-stu-id="b7e43-188">You can use array notation, such as `$a[0]` or `$error[1,2]` to refer to specific errors stored in the variables.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-189">Пользовательская переменная ошибки содержит все ошибки, сформированные командой, включая ошибки вызовов вложенных функций или скриптов.</span><span class="sxs-lookup"><span data-stu-id="b7e43-189">The custom error variable contains all errors generated by the command, including errors from calls to nested functions or scripts.</span></span>

#### <a name="informationaction"></a><span data-ttu-id="b7e43-190">InformationAction</span><span class="sxs-lookup"><span data-stu-id="b7e43-190">InformationAction</span></span>

<span data-ttu-id="b7e43-191">Представлено в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b7e43-191">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="b7e43-192">В команде или сценарии, в которой они используются, общий параметр **InformationAction** переопределяет значение `$InformationPreference` привилегированной переменной, которая по умолчанию имеет значение **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-192">Within the command or script in which it's used, the **InformationAction** common parameter overrides the value of the `$InformationPreference` preference variable, which by default is set to **SilentlyContinue** .</span></span> <span data-ttu-id="b7e43-193">При использовании `Write-Information` в скрипте с **InformationAction** `Write-Information` значения отображаются в зависимости от значения параметра **InformationAction** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-193">When you use `Write-Information` in a script with **InformationAction** , `Write-Information` values are shown depending on the value of the **InformationAction** parameter.</span></span> <span data-ttu-id="b7e43-194">Дополнительные сведения о `$InformationPreference` см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b7e43-194">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-195">`-InformationAction:Stop` Останавливает команду или скрипт при возникновении `Write-Information` команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-195">`-InformationAction:Stop` stops a command or script at an occurrence of the `Write-Information` command.</span></span>

<span data-ttu-id="b7e43-196">`-InformationAction:Ignore` подавляет информационное сообщение и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-196">`-InformationAction:Ignore` suppresses the informational message and continues running the command.</span></span> <span data-ttu-id="b7e43-197">В отличие от **SilentlyContinue** , **Ignore** полностью забыл информационное сообщение. оно не добавляет информационное сообщение в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="b7e43-197">Unlike **SilentlyContinue** , **Ignore** completely forgets the informational message; it doesn't add the informational message to the information stream.</span></span>

<span data-ttu-id="b7e43-198">`-InformationAction:Inquire` отображает информационное сообщение, указанное в `Write-Information` команде, а затем спрашивает, нужно ли продолжить.</span><span class="sxs-lookup"><span data-stu-id="b7e43-198">`-InformationAction:Inquire` displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>

<span data-ttu-id="b7e43-199">`-InformationAction:Continue` отображает информационное сообщение и продолжит выполнение.</span><span class="sxs-lookup"><span data-stu-id="b7e43-199">`-InformationAction:Continue` displays the informational message, and continues running.</span></span>

<span data-ttu-id="b7e43-200">`-InformationAction:Suspend` не поддерживается в PowerShell Core, так как он доступен только для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b7e43-200">`-InformationAction:Suspend` isn't supported on PowerShell Core as it is only available for workflows.</span></span>

<span data-ttu-id="b7e43-201">`-InformationAction:SilentlyContinue` не действует, так как информационное сообщение не отображается (по умолчанию), и сценарий продолжается без прерывания.</span><span class="sxs-lookup"><span data-stu-id="b7e43-201">`-InformationAction:SilentlyContinue` no effect as the informational message aren't (Default) displayed, and the script continues without interruption.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-202">Параметр **InformationAction** переопределяет, но не заменяет значение `$InformationAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="b7e43-202">The **InformationAction** parameter overrides, but does not replace the value of the `$InformationAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="informationvariable"></a><span data-ttu-id="b7e43-203">InformationVariable</span><span class="sxs-lookup"><span data-stu-id="b7e43-203">InformationVariable</span></span>

<span data-ttu-id="b7e43-204">Представлено в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b7e43-204">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="b7e43-205">В команде или сценарии, в которой они используются, общий параметр **InformationVariable** сохраняет в переменной строку, указанную путем добавления `Write-Information` команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-205">Within the command or script in which it's used, the **InformationVariable** common parameter stores in a variable a string that you specify by adding the `Write-Information` command.</span></span> <span data-ttu-id="b7e43-206">`Write-Information` значения отображаются в зависимости от значения общего параметра **InformationAction** . Если не добавить общий параметр **InformationAction** , `Write-Information` строки будут показаны в зависимости от значения `$InformationPreference` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-206">`Write-Information` values are shown depending on the value of the **InformationAction** common parameter; if you don't add the **InformationAction** common parameter, `Write-Information` strings are shown depending on the value of the `$InformationPreference` preference variable.</span></span> <span data-ttu-id="b7e43-207">Дополнительные сведения о `$InformationPreference` см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b7e43-207">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-208">Информационная переменная содержит все информационные сообщения, созданные командой, включая информационные сообщения от вызовов вложенных функций или скриптов.</span><span class="sxs-lookup"><span data-stu-id="b7e43-208">The information variable contains all information messages generated by the command, including information messages from calls to nested functions or scripts.</span></span>

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a><span data-ttu-id="b7e43-209">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="b7e43-209">OutBuffer</span></span>

<span data-ttu-id="b7e43-210">Определяет количество объектов, которые должны накапливаться в буфере перед отправкой объектов через конвейер.</span><span class="sxs-lookup"><span data-stu-id="b7e43-210">Determines the number of objects to accumulate in a buffer before any objects are sent through the pipeline.</span></span> <span data-ttu-id="b7e43-211">Если опустить этот параметр, то объекты будут отправляться по мере их создания.</span><span class="sxs-lookup"><span data-stu-id="b7e43-211">If you omit this parameter, objects are sent as they're generated.</span></span>

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-212">Этот параметр управления ресурсами предназначен для опытных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7e43-212">This resource management parameter is designed for advanced users.</span></span> <span data-ttu-id="b7e43-213">При использовании этого параметра PowerShell отправляет данные в следующий командлет в пакетах `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-213">When you use this parameter, PowerShell sends data to the next cmdlet in batches of `OutBuffer + 1`.</span></span>

<span data-ttu-id="b7e43-214">В следующем примере в качестве альтернативы отображаются `ForEach-Object` блоки Process, использующие `Write-Host` командлет.</span><span class="sxs-lookup"><span data-stu-id="b7e43-214">The following example alternates displays between to `ForEach-Object` process blocks that use the `Write-Host` cmdlet.</span></span> <span data-ttu-id="b7e43-215">Отображаемые варианты в пакетах — 2 или `OutBuffer + 1` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-215">The display alternates in batches of 2 or `OutBuffer + 1`.</span></span>

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a><span data-ttu-id="b7e43-216">OutVariable</span><span class="sxs-lookup"><span data-stu-id="b7e43-216">OutVariable</span></span>

<span data-ttu-id="b7e43-217">Сохраняет выходные объекты из команды в указанной переменной в дополнение к отправке выходных данных в конвейере.</span><span class="sxs-lookup"><span data-stu-id="b7e43-217">Stores output objects from the command in the specified variable in addition to sending the output along the pipeline.</span></span>

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-218">Чтобы добавить выходные данные в переменную, вместо того, чтобы заменять выходные данные, которые могут быть уже сохранены, введите знак плюса ( `+` ) перед именем переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-218">To add the output to the variable, instead of replacing any output that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="b7e43-219">Например, следующая команда создает `$out` переменную и сохраняет в ней объект Process:</span><span class="sxs-lookup"><span data-stu-id="b7e43-219">For example, the following command creates the `$out` variable and stores the process object in it:</span></span>

```powershell
Get-Process PowerShell -OutVariable out
```

<span data-ttu-id="b7e43-220">Следующая команда добавляет объект Process в `$out` переменную:</span><span class="sxs-lookup"><span data-stu-id="b7e43-220">The following command adds the process object to the `$out` variable:</span></span>

```powershell
Get-Process iexplore -OutVariable +out
```

<span data-ttu-id="b7e43-221">Следующая команда отображает содержимое `$out` переменной:</span><span class="sxs-lookup"><span data-stu-id="b7e43-221">The following command displays the contents of the `$out` variable:</span></span>

```powershell
$out
```

> [!NOTE]
> <span data-ttu-id="b7e43-222">Переменная, созданная параметром **переменной** , имеет значение `[System.Collections.ArrayList]` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-222">The variable created by the **OutVariable** parameter is a `[System.Collections.ArrayList]`.</span></span>

#### <a name="pipelinevariable"></a><span data-ttu-id="b7e43-223">PipelineVariable</span><span class="sxs-lookup"><span data-stu-id="b7e43-223">PipelineVariable</span></span>

<span data-ttu-id="b7e43-224">**PipelineVariable** сохраняет значение текущего конвейера как переменную для любой именованной команды в том виде, в каком она проходит через конвейер.</span><span class="sxs-lookup"><span data-stu-id="b7e43-224">**PipelineVariable** stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.</span></span>

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-225">Допустимые значения — строки, такие же, как и для имен переменных.</span><span class="sxs-lookup"><span data-stu-id="b7e43-225">Valid values are strings, the same as for any variable names.</span></span>

<span data-ttu-id="b7e43-226">Ниже приведен пример того, как работает **PipelineVariable** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-226">The following is an example of how **PipelineVariable** works.</span></span> <span data-ttu-id="b7e43-227">В этом примере параметр **PipelineVariable** добавляется в `Foreach-Object` команду для сохранения результатов выполнения команды в переменных.</span><span class="sxs-lookup"><span data-stu-id="b7e43-227">In this example, the **PipelineVariable** parameter is added to a `Foreach-Object` command to store the results of the command in variables.</span></span> <span data-ttu-id="b7e43-228">Диапазон чисел от 1 до 10 передается в первую `Foreach-Object` команду, результаты которых хранятся в переменной с именем **Left** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-228">A range of numbers, 1 to 10, are piped into the first `Foreach-Object` command, the results of which are stored in a variable named **Left** .</span></span>

<span data-ttu-id="b7e43-229">Результаты первой `Foreach-Object` команды передаются во вторую `Foreach-Object` команду, которая фильтрует объекты, возвращаемые первой `Foreach-Object` командой.</span><span class="sxs-lookup"><span data-stu-id="b7e43-229">The results of the first `Foreach-Object` command are piped into a second `Foreach-Object` command, which filters the objects returned by the first `Foreach-Object` command.</span></span> <span data-ttu-id="b7e43-230">Результаты второй команды хранятся в переменной с именем **right** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-230">The results of the second command are stored in a variable named **Right** .</span></span>

<span data-ttu-id="b7e43-231">В третьей `Foreach-Object` команде результаты первых двух `Foreach-Object` команд, представленных переменными **слева** и **справа** , обрабатываются с помощью оператора умножения.</span><span class="sxs-lookup"><span data-stu-id="b7e43-231">In the third `Foreach-Object` command, the results of the first two `Foreach-Object` piped commands, represented by the variables **Left** and **Right** , are processed by using a multiplication operator.</span></span> <span data-ttu-id="b7e43-232">Команда указывает, что необходимо умножить объекты, хранящиеся в **левой** и **правой** переменных, и указать, что результаты должны отображаться как «левый диапазон член \* правый диапазон Member = продукт».</span><span class="sxs-lookup"><span data-stu-id="b7e43-232">The command instructs objects stored in the **Left** and **Right** variables to be multiplied, and specifies that the results should be displayed as "Left range member \* Right range member = product".</span></span>

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a><span data-ttu-id="b7e43-233">Подробный</span><span class="sxs-lookup"><span data-stu-id="b7e43-233">Verbose</span></span>

<span data-ttu-id="b7e43-234">Отображает подробные сведения об операции, выполненной командой.</span><span class="sxs-lookup"><span data-stu-id="b7e43-234">Displays detailed information about the operation done by the command.</span></span> <span data-ttu-id="b7e43-235">Эти сведения похожи на сведения в трассировке или в журнале транзакций.</span><span class="sxs-lookup"><span data-stu-id="b7e43-235">This information resembles the information in a trace or in a transaction log.</span></span> <span data-ttu-id="b7e43-236">Этот параметр работает, только если команда создает подробное сообщение.</span><span class="sxs-lookup"><span data-stu-id="b7e43-236">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="b7e43-237">Например, этот параметр работает, если команда содержит `Write-Verbose` командлет.</span><span class="sxs-lookup"><span data-stu-id="b7e43-237">For example, this parameter works when a command contains the `Write-Verbose` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-238">Параметр **verbose** переопределяет значение `$VerbosePreference` переменной для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-238">The **Verbose** parameter overrides the value of the `$VerbosePreference` variable for the current command.</span></span> <span data-ttu-id="b7e43-239">Так как значение переменной по умолчанию `$VerbosePreference` — **SilentlyContinue** , подробные сообщения не отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7e43-239">Because the default value of the `$VerbosePreference` variable is **SilentlyContinue** , verbose messages aren't displayed by default.</span></span>

<span data-ttu-id="b7e43-240">`-Verbose:$true` имеет тот же результат, что и `-Verbose`</span><span class="sxs-lookup"><span data-stu-id="b7e43-240">`-Verbose:$true` has the same effect as `-Verbose`</span></span>

<span data-ttu-id="b7e43-241">`-Verbose:$false` подавляет отображение подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b7e43-241">`-Verbose:$false` suppresses the display of verbose messages.</span></span> <span data-ttu-id="b7e43-242">Используйте этот параметр, если значение `$VerbosePreference` не **SilentlyContinue** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7e43-242">Use this parameter when the value of `$VerbosePreference` isn't **SilentlyContinue** (the default).</span></span>

#### <a name="warningaction"></a><span data-ttu-id="b7e43-243">WarningAction</span><span class="sxs-lookup"><span data-stu-id="b7e43-243">WarningAction</span></span>

<span data-ttu-id="b7e43-244">Определяет реакцию командлета на предупреждение от команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-244">Determines how the cmdlet responds to a warning from the command.</span></span> <span data-ttu-id="b7e43-245">Значение **Continue** является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7e43-245">**Continue** is the default value.</span></span> <span data-ttu-id="b7e43-246">Этот параметр работает, только если команда создает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="b7e43-246">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="b7e43-247">Например, этот параметр работает, если команда содержит `Write-Warning` командлет.</span><span class="sxs-lookup"><span data-stu-id="b7e43-247">For example, this parameter works when a command contains the `Write-Warning` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-248">Параметр **WarningAction** переопределяет значение `$WarningPreference` переменной для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-248">The **WarningAction** parameter overrides the value of the `$WarningPreference` variable for the current command.</span></span> <span data-ttu-id="b7e43-249">Так как значение переменной по умолчанию `$WarningPreference` — **Continue** , отображаются предупреждения и выполнение продолжается, если не используется параметр **WarningAction** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-249">Because the default value of the `$WarningPreference` variable is **Continue** , warnings are displayed and execution continues unless you use the **WarningAction** parameter.</span></span>

<span data-ttu-id="b7e43-250">`-WarningAction:Continue` Отображает предупреждающие сообщения и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-250">`-WarningAction:Continue` displays the warning messages and continues executing the command.</span></span> <span data-ttu-id="b7e43-251">Значение по умолчанию — `Continue`.</span><span class="sxs-lookup"><span data-stu-id="b7e43-251">`Continue` is the default.</span></span>

<span data-ttu-id="b7e43-252">`-WarningAction:Inquire` отображает предупреждающее сообщение и запрашивает подтверждение перед продолжением выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7e43-252">`-WarningAction:Inquire` displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="b7e43-253">Это значение используется редко.</span><span class="sxs-lookup"><span data-stu-id="b7e43-253">This value is rarely used.</span></span>

<span data-ttu-id="b7e43-254">`-WarningAction:SilentlyContinue` подавляет предупреждающее сообщение и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-254">`-WarningAction:SilentlyContinue` suppresses the warning message and continues executing the command.</span></span>

<span data-ttu-id="b7e43-255">`-WarningAction:Stop` отображает предупреждающее сообщение и прекращает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-255">`-WarningAction:Stop` displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-256">Параметр **WarningAction** переопределяет, но не заменяет значение `$WarningAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="b7e43-256">The **WarningAction** parameter overrides, but does not replace the value of the `$WarningAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="warningvariable"></a><span data-ttu-id="b7e43-257">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="b7e43-257">WarningVariable</span></span>

<span data-ttu-id="b7e43-258">Хранит предупреждения о команде в указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-258">Stores warnings about the command in the specified variable.</span></span>

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-259">Все созданные предупреждения сохраняются в переменной, даже если они не отображаются для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7e43-259">All generated warnings are saved in the variable even if the warnings aren't displayed to the user.</span></span>

<span data-ttu-id="b7e43-260">Чтобы добавить предупреждения в содержимое переменной, вместо того, чтобы заменять все предупреждения, которые могут быть уже сохранены, введите знак плюс ( `+` ) перед именем переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-260">To append the warnings to the variable content, instead of replacing any warnings that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="b7e43-261">Например, следующая команда создает `$a` переменную, а затем сохраняет в ней все предупреждения:</span><span class="sxs-lookup"><span data-stu-id="b7e43-261">For example, the following command creates the `$a` variable and then stores any warnings in it:</span></span>

```powershell
Get-Process -Id 6 -WarningVariable a
```

<span data-ttu-id="b7e43-262">Следующая команда добавляет все предупреждения в `$a` переменную:</span><span class="sxs-lookup"><span data-stu-id="b7e43-262">The following command adds any warnings to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -WarningVariable +a
```

<span data-ttu-id="b7e43-263">Следующая команда отображает содержимое `$a` :</span><span class="sxs-lookup"><span data-stu-id="b7e43-263">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="b7e43-264">Этот параметр можно использовать для создания переменной, содержащей только предупреждения из конкретных команд.</span><span class="sxs-lookup"><span data-stu-id="b7e43-264">You can use this parameter to create a variable that contains only warnings from specific commands.</span></span> <span data-ttu-id="b7e43-265">Можно использовать нотацию массива, например `$a[0]` или, `$warning[1,2]` для ссылки на конкретные предупреждения, хранящиеся в переменной.</span><span class="sxs-lookup"><span data-stu-id="b7e43-265">You can use array notation, such as `$a[0]` or `$warning[1,2]` to refer to specific warnings stored in the variable.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e43-266">Переменная предупреждения содержит все предупреждения, созданные командой, включая предупреждения о вызовах вложенных функций или скриптов.</span><span class="sxs-lookup"><span data-stu-id="b7e43-266">The warning variable contains all warnings generated by the command, including warnings from calls to nested functions or scripts.</span></span>

### <a name="risk-management-parameter-descriptions"></a><span data-ttu-id="b7e43-267">Описания параметров управления рисками</span><span class="sxs-lookup"><span data-stu-id="b7e43-267">Risk Management Parameter Descriptions</span></span>

#### <a name="whatif"></a><span data-ttu-id="b7e43-268">WhatIf</span><span class="sxs-lookup"><span data-stu-id="b7e43-268">WhatIf</span></span>

<span data-ttu-id="b7e43-269">Отображает сообщение, описывающее результат выполнения команды, а не выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-269">Displays a message that describes the effect of the command, instead of executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-270">Параметр **WhatIf** переопределяет значение `$WhatIfPreference` переменной для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-270">The **WhatIf** parameter overrides the value of the `$WhatIfPreference` variable for the current command.</span></span> <span data-ttu-id="b7e43-271">Так как значение переменной по умолчанию `$WhatIfPreference` равно 0 (отключено), поведение **WhatIf** не выполняется без параметра **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-271">Because the default value of the `$WhatIfPreference` variable is 0 (disabled), **WhatIf** behavior isn't done without the **WhatIf** parameter.</span></span> <span data-ttu-id="b7e43-272">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="b7e43-272">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="b7e43-273">`-WhatIf:$true` имеет тот же результат, что и `-WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-273">`-WhatIf:$true` has the same effect as `-WhatIf`.</span></span>

<span data-ttu-id="b7e43-274">`-WhatIf:$false` подавляет автоматическое поведение WhatIf, которое возникает, когда значение `$WhatIfPreference` переменной равно 1.</span><span class="sxs-lookup"><span data-stu-id="b7e43-274">`-WhatIf:$false` suppresses the automatic WhatIf behavior that results when the value of the `$WhatIfPreference` variable is 1.</span></span>

<span data-ttu-id="b7e43-275">Например, следующая команда использует `-WhatIf` параметр в `Remove-Item` команде:</span><span class="sxs-lookup"><span data-stu-id="b7e43-275">For example, the following command uses the `-WhatIf` parameter in a `Remove-Item` command:</span></span>

```powershell
Remove-Item Date.csv -WhatIf
```

<span data-ttu-id="b7e43-276">Вместо удаления элемента в PowerShell перечислены выполняемые операции и элементы, которые были бы затронуты.</span><span class="sxs-lookup"><span data-stu-id="b7e43-276">Instead of removing the item, PowerShell lists the operations it would do and the items that would be affected.</span></span> <span data-ttu-id="b7e43-277">Эта команда создает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="b7e43-277">This command produces the following output:</span></span>

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a><span data-ttu-id="b7e43-278">Подтвердить</span><span class="sxs-lookup"><span data-stu-id="b7e43-278">Confirm</span></span>

<span data-ttu-id="b7e43-279">Выводит приглашение для подтверждения перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-279">Prompts you for confirmation before executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="b7e43-280">Параметр **Confirm** переопределяет значение `$ConfirmPreference` переменной для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-280">The **Confirm** parameter overrides the value of the `$ConfirmPreference` variable for the current command.</span></span> <span data-ttu-id="b7e43-281">Значение по умолчанию — true.</span><span class="sxs-lookup"><span data-stu-id="b7e43-281">The default value is true.</span></span> <span data-ttu-id="b7e43-282">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="b7e43-282">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="b7e43-283">`-Confirm:$true` имеет тот же результат, что и `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="b7e43-283">`-Confirm:$true` has the same effect as `-Confirm`.</span></span>

<span data-ttu-id="b7e43-284">`-Confirm:$false` подавляет автоматическое подтверждение, которое происходит, если значение `$ConfirmPreference` меньше или равно предполагаемому риску командлета.</span><span class="sxs-lookup"><span data-stu-id="b7e43-284">`-Confirm:$false` suppresses automatic confirmation, which occurs when the value of `$ConfirmPreference` is less than or equal to the estimated risk of the cmdlet.</span></span>

<span data-ttu-id="b7e43-285">Например, следующая команда использует параметр **Confirm** с `Remove-Item` командой.</span><span class="sxs-lookup"><span data-stu-id="b7e43-285">For example, the following command uses the **Confirm** parameter with a `Remove-Item` command.</span></span> <span data-ttu-id="b7e43-286">Перед удалением элемента в PowerShell будут перечислены выполняемые операции и элементы, которые будут затронуты, и запрашивается утверждение.</span><span class="sxs-lookup"><span data-stu-id="b7e43-286">Before removing the item, PowerShell lists the operations it would do and the items that would be affected, and asks for approval.</span></span>

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="b7e43-287">Ниже приведены параметры подтверждения ответа.</span><span class="sxs-lookup"><span data-stu-id="b7e43-287">The Confirm response options are as follows:</span></span>

|<span data-ttu-id="b7e43-288">Ответ</span><span class="sxs-lookup"><span data-stu-id="b7e43-288">Response</span></span>       |<span data-ttu-id="b7e43-289">Результат</span><span class="sxs-lookup"><span data-stu-id="b7e43-289">Result</span></span>                                                     |
|---------------|-----------------------------------------------------------|
|<span data-ttu-id="b7e43-290">Да (Y)</span><span class="sxs-lookup"><span data-stu-id="b7e43-290">Yes (Y)</span></span>        |<span data-ttu-id="b7e43-291">Выполните действие.</span><span class="sxs-lookup"><span data-stu-id="b7e43-291">Perform the action.</span></span>                                        |
|<span data-ttu-id="b7e43-292">Да для всех (A)</span><span class="sxs-lookup"><span data-stu-id="b7e43-292">Yes to All (A)</span></span> |<span data-ttu-id="b7e43-293">Выполнение всех действий и подавление последующих запросов на подтверждение</span><span class="sxs-lookup"><span data-stu-id="b7e43-293">Perform all actions and suppress subsequent Confirm queries</span></span>|
|               |<span data-ttu-id="b7e43-294">для этой команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-294">for this command.</span></span>                                          |
|<span data-ttu-id="b7e43-295">Нет (N):</span><span class="sxs-lookup"><span data-stu-id="b7e43-295">No (N):</span></span>        |<span data-ttu-id="b7e43-296">Не выполняйте действие.</span><span class="sxs-lookup"><span data-stu-id="b7e43-296">Do not perform the action.</span></span>                                 |
|<span data-ttu-id="b7e43-297">Нет для всех (L):</span><span class="sxs-lookup"><span data-stu-id="b7e43-297">No to All (L):</span></span> |<span data-ttu-id="b7e43-298">Не выполнять никаких действий и подавлять последующие подтверждения</span><span class="sxs-lookup"><span data-stu-id="b7e43-298">Do not perform any actions and suppress subsequent Confirm</span></span> |
|               |<span data-ttu-id="b7e43-299">запросы для этой команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-299">queries for this command.</span></span>                                  |
|<span data-ttu-id="b7e43-300">Приостановка:</span><span class="sxs-lookup"><span data-stu-id="b7e43-300">Suspend (S):</span></span>   |<span data-ttu-id="b7e43-301">Приостановите команду и создайте временный сеанс.</span><span class="sxs-lookup"><span data-stu-id="b7e43-301">Pause the command and create a temporary session.</span></span>          |
|<span data-ttu-id="b7e43-302">Справка (?)</span><span class="sxs-lookup"><span data-stu-id="b7e43-302">Help (?)</span></span>       |<span data-ttu-id="b7e43-303">Отображает справку по этим параметрам.</span><span class="sxs-lookup"><span data-stu-id="b7e43-303">Display help for these options.</span></span>                            |

<span data-ttu-id="b7e43-304">Параметр **Suspend** помещает команду в удержание и создает временный вложенный сеанс, в котором можно работать, пока вы не будете готовы выбрать параметр **подтверждения** .</span><span class="sxs-lookup"><span data-stu-id="b7e43-304">The **Suspend** option places the command on hold and creates a temporary nested session in which you can work until you're ready to choose a **Confirm** option.</span></span> <span data-ttu-id="b7e43-305">Командная строка для вложенного сеанса имеет две дополнительные символы (>>), указывающие, что это дочерняя операция исходной родительской команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-305">The command prompt for the nested session has two extra carets (>>) to indicate that it's a child operation of the original parent command.</span></span> <span data-ttu-id="b7e43-306">Во вложенном сеансе можно выполнять команды и скрипты.</span><span class="sxs-lookup"><span data-stu-id="b7e43-306">You can run commands and scripts in the nested session.</span></span> <span data-ttu-id="b7e43-307">Чтобы завершить вложенный сеанс и вернуться к параметрам подтверждения исходной команды, введите "Exit".</span><span class="sxs-lookup"><span data-stu-id="b7e43-307">To end the nested session and return to the Confirm options for the original command, type "exit".</span></span>

<span data-ttu-id="b7e43-308">В следующем примере параметры **приостановки** используются для временной остановки команды, в то время как пользователь проверяет справку для параметра команды.</span><span class="sxs-lookup"><span data-stu-id="b7e43-308">In the following example, the **Suspend** option (S) is used to halt a command temporarily while the user checks the help for a command parameter.</span></span> <span data-ttu-id="b7e43-309">После получения необходимой информации пользователь вводит "Exit" для завершения вложенного запроса, а затем выбирает ответ "Да" (y) для подтверждения запроса.</span><span class="sxs-lookup"><span data-stu-id="b7e43-309">After obtaining the needed information, the user types "exit" to end the nested prompt and then selects the Yes (y) response to the Confirm query.</span></span>

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a><span data-ttu-id="b7e43-310">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="b7e43-310">KEYWORDS</span></span>

<span data-ttu-id="b7e43-311">about_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="b7e43-311">about_Common_Parameters</span></span>

## <a name="see-also"></a><span data-ttu-id="b7e43-312">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="b7e43-312">SEE ALSO</span></span>

[<span data-ttu-id="b7e43-313">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b7e43-313">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="b7e43-314">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="b7e43-314">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)

[<span data-ttu-id="b7e43-315">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="b7e43-315">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)

[<span data-ttu-id="b7e43-316">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="b7e43-316">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)

[<span data-ttu-id="b7e43-317">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="b7e43-317">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)

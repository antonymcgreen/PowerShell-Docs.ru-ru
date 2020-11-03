---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: d04fb0bb75906d18fecce17e4ceb581fe667eceb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226822"
---
# <span data-ttu-id="eb2e2-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="eb2e2-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="eb2e2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eb2e2-104">SYNOPSIS</span></span>
<span data-ttu-id="eb2e2-105">Задает политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="eb2e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eb2e2-106">SYNTAX</span></span>

### <span data-ttu-id="eb2e2-107">Все</span><span class="sxs-lookup"><span data-stu-id="eb2e2-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="eb2e2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eb2e2-108">DESCRIPTION</span></span>

<span data-ttu-id="eb2e2-109">`Set-ExecutionPolicy`Командлет изменяет политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="eb2e2-110">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="eb2e2-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="eb2e2-111">Начиная с PowerShell 6,0 для компьютеров, отличных от Windows, политика выполнения по умолчанию не **ограничена** и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-111">Beginning in PowerShell 6.0 for non-Windows computers, the default execution policy is **Unrestricted** and can't be changed.</span></span> <span data-ttu-id="eb2e2-112">`Set-ExecutionPolicy`Командлет доступен, но PowerShell отображает сообщение консоли, которое не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-112">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span>

<span data-ttu-id="eb2e2-113">Политика выполнения является частью стратегии безопасности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-113">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="eb2e2-114">Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-114">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="eb2e2-115">И, если перед запуском скрипты должны иметь цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-115">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="eb2e2-116">`Set-ExecutionPolicy`По умолчанию командлет имеет область **LocalMachine** , которая влияет на всех, кто использует этот компьютер.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-116">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="eb2e2-117">Чтобы изменить политику выполнения для **LocalMachine** , запустите PowerShell с **запуском от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-117">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator**.</span></span>

<span data-ttu-id="eb2e2-118">Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-118">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="eb2e2-119">Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-119">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="eb2e2-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="eb2e2-120">EXAMPLES</span></span>

### <span data-ttu-id="eb2e2-121">Пример 1. Настройка политики выполнения</span><span class="sxs-lookup"><span data-stu-id="eb2e2-121">Example 1: Set an execution policy</span></span>

<span data-ttu-id="eb2e2-122">В этом примере показано, как задать политику выполнения для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-122">This example shows how to set the execution policy for the local computer.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="eb2e2-123">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-123">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="eb2e2-124">Параметр **Scope** задает значение области по умолчанию — **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-124">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="eb2e2-125">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-125">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="eb2e2-126">Пример 2. Настройка политики выполнения, конфликтующей с групповая политика</span><span class="sxs-lookup"><span data-stu-id="eb2e2-126">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="eb2e2-127">Эта команда пытается установить **ограничение** для политики выполнения в области **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-127">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted**.</span></span>
<span data-ttu-id="eb2e2-128">**Хранилище LocalMachine** является более узким, но не является действующей политикой, так как она конфликтует с групповая политика.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-128">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="eb2e2-129">Политика **ограниченного** доступа записывается в куст реестра **HKEY_LOCAL_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-129">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE**.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

<span data-ttu-id="eb2e2-130">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **ограничения** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-130">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="eb2e2-131">Параметр **Scope** задает значение области по умолчанию — **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-131">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span>
<span data-ttu-id="eb2e2-132">`Get-ChildItem`Командлет использует параметр **path** с поставщиком **HKLM** для указания расположения реестра.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-132">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="eb2e2-133">Пример 3. Применение политики выполнения с удаленного компьютера к локальному компьютеру</span><span class="sxs-lookup"><span data-stu-id="eb2e2-133">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="eb2e2-134">Эта команда получает объект политики выполнения с удаленного компьютера и устанавливает политику на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-134">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="eb2e2-135">`Get-ExecutionPolicy` отправляет объект **Microsoft.PowerShell.Exeкутионполици** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-135">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="eb2e2-136">`Set-ExecutionPolicy` принимает входные данные конвейера и не требует параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-136">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="eb2e2-137">`Invoke-Command`Командлет выполняется на локальном компьютере и отправляет **ScriptBlock** на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-137">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="eb2e2-138">Параметр **ComputerName** указывает удаленный компьютер **Server01**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-138">The **ComputerName** parameter specifies the remote computer, **Server01**.</span></span> <span data-ttu-id="eb2e2-139">Параметр **ScriptBlock** выполняется `Get-ExecutionPolicy` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-139">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="eb2e2-140">`Get-ExecutionPolicy`Объект отправляется по конвейеру в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-140">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="eb2e2-141">`Set-ExecutionPolicy` применяет политику выполнения к области по умолчанию локального компьютера, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-141">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine**.</span></span>

### <span data-ttu-id="eb2e2-142">Пример 4. Задание области для политики выполнения</span><span class="sxs-lookup"><span data-stu-id="eb2e2-142">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="eb2e2-143">В этом примере показано, как задать политику выполнения для указанной области, **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-143">This example shows how to set an execution policy for a specified scope, **CurrentUser**.</span></span> <span data-ttu-id="eb2e2-144">Область **CurrentUser** влияет только на пользователя, который устанавливает эту область.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-144">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="eb2e2-145">`Set-ExecutionPolicy`Задает политику **AllSigned** с помощью параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-145">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="eb2e2-146">Параметр **Scope** указывает **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-146">The **Scope** parameter specifies the **CurrentUser**.</span></span> <span data-ttu-id="eb2e2-147">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-147">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="eb2e2-148">Действующая политика выполнения для пользователя преобразуется в **AllSigned**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-148">The effective execution policy for the user becomes **AllSigned**.</span></span>

### <span data-ttu-id="eb2e2-149">Пример 5. Удаление политики выполнения для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="eb2e2-149">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="eb2e2-150">В этом примере показано, как использовать **неопределенную** политику выполнения для удаления политики выполнения для указанной области.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-150">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

<span data-ttu-id="eb2e2-151">`Set-ExecutionPolicy` использует параметр **ExecutionPolicy** для указания **неопределенной** политики.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-151">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="eb2e2-152">Параметр **Scope** указывает **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-152">The **Scope** parameter specifies the **CurrentUser**.</span></span> <span data-ttu-id="eb2e2-153">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-153">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="eb2e2-154">Пример 6. Настройка политики выполнения для текущего сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb2e2-154">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="eb2e2-155">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-155">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="eb2e2-156">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` и удаляется при закрытии сеанса.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-156">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="eb2e2-157">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-157">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="eb2e2-158">Параметр **Scope** задает **процесс** value.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-158">The **Scope** parameter specifies the value **Process**.</span></span> <span data-ttu-id="eb2e2-159">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-159">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="eb2e2-160">Пример 7. Разблокировка скрипта для его запуска без изменения политики выполнения</span><span class="sxs-lookup"><span data-stu-id="eb2e2-160">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="eb2e2-161">В этом примере показано, как политика выполнения **RemoteSigned** не позволяет выполнять неподписанные сценарии.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-161">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="eb2e2-162">**Перед** использованием командлета рекомендуется прочитать код скрипта и проверить его безопасность `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-162">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="eb2e2-163">`Unblock-File`Командлет разблокирует скрипты для их запуска, но не изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-163">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

<span data-ttu-id="eb2e2-164">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-164">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="eb2e2-165">Политика задается для области по умолчанию, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-165">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="eb2e2-166">`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-166">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="eb2e2-167">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-167">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="eb2e2-168">Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-168">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="eb2e2-169">В этом примере код скрипта был проверен и проверен как надежный для выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-169">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="eb2e2-170">`Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-170">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="eb2e2-171">Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-171">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="eb2e2-172">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-172">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="eb2e2-173">Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-173">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="eb2e2-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eb2e2-174">PARAMETERS</span></span>

### <span data-ttu-id="eb2e2-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eb2e2-175">-Confirm</span></span>

<span data-ttu-id="eb2e2-176">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-176">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="eb2e2-177">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="eb2e2-177">-ExecutionPolicy</span></span>

<span data-ttu-id="eb2e2-178">Задает политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-178">Specifies the execution policy.</span></span> <span data-ttu-id="eb2e2-179">Если групповых политик нет, а для каждой политики выполнения каждой области задано значение **undefine** , то **ограничения** становятся действующей политикой для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-179">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="eb2e2-180">Допустимы следующие значения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-180">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="eb2e2-181">**AllSigned**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-181">**AllSigned**.</span></span> <span data-ttu-id="eb2e2-182">Требует, чтобы все сценарии и файлы конфигурации подписаны доверенным издателем, включая сценарии, написанные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-182">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="eb2e2-183">**Обход**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-183">**Bypass**.</span></span> <span data-ttu-id="eb2e2-184">ничего не блокируется, и никакие предупреждения и запросы не появляются.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-184">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="eb2e2-185">**Default**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-185">**Default**.</span></span> <span data-ttu-id="eb2e2-186">Задает политику выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-186">Sets the default execution policy.</span></span> <span data-ttu-id="eb2e2-187">**Ограничено** для клиентов Windows или **RemoteSigned** для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-187">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="eb2e2-188">**RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-188">**RemoteSigned**.</span></span> <span data-ttu-id="eb2e2-189">Требует, чтобы все скрипты и файлы конфигурации, скачанные из Интернета, были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-189">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="eb2e2-190">Политика выполнения по умолчанию для компьютеров Windows Server.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-190">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="eb2e2-191">**Ограничено**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-191">**Restricted**.</span></span> <span data-ttu-id="eb2e2-192">Не загружает файлы конфигурации или не выполняет сценарии.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-192">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="eb2e2-193">Политика выполнения по умолчанию клиентские компьютеры Windows.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-193">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="eb2e2-194">Не **определено**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-194">**Undefined**.</span></span> <span data-ttu-id="eb2e2-195">Для области не задана политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-195">No execution policy is set for the scope.</span></span> <span data-ttu-id="eb2e2-196">Удаляет назначенную политику выполнения из области, которая не задается групповая политика.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-196">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="eb2e2-197">Если политика выполнения во всех областях не **определена** , действующая политика выполнения **ограничена**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-197">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted**.</span></span>
- <span data-ttu-id="eb2e2-198">Без **ограничений**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-198">**Unrestricted**.</span></span> <span data-ttu-id="eb2e2-199">Начиная с PowerShell 6,0 это политика выполнения по умолчанию для компьютеров, отличных от Windows, и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-199">Beginning in PowerShell 6.0, this is the default execution policy for non-Windows computers and can't be changed.</span></span> <span data-ttu-id="eb2e2-200">загружает все файлы конфигурации и выполняет все скрипты.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-200">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="eb2e2-201">При запуске неподписанного скрипта, скачанного из Интернета, перед запуском появится запрос на разрешение.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-201">If you run an unsigned script that was downloaded from the internet, you're prompted for permission before it runs.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="eb2e2-202">-Force</span><span class="sxs-lookup"><span data-stu-id="eb2e2-202">-Force</span></span>

<span data-ttu-id="eb2e2-203">Подавляет все запросы подтверждения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-203">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="eb2e2-204">Будьте внимательны с этим параметром, чтобы избежать непредвиденных результатов.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-204">Use caution with this parameter to avoid unexpected results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb2e2-205">-Scope</span><span class="sxs-lookup"><span data-stu-id="eb2e2-205">-Scope</span></span>

<span data-ttu-id="eb2e2-206">Указывает область, на которую влияет политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-206">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="eb2e2-207">Областью по умолчанию является **хранилище LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-207">The default scope is **LocalMachine**.</span></span>

<span data-ttu-id="eb2e2-208">Действующая политика выполнения определяется порядком приоритета следующим образом.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-208">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="eb2e2-209">**Мачинеполици**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-209">**MachinePolicy**.</span></span> <span data-ttu-id="eb2e2-210">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-210">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="eb2e2-211">**UserPolicy**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-211">**UserPolicy**.</span></span> <span data-ttu-id="eb2e2-212">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-212">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="eb2e2-213">**Процесс**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-213">**Process**.</span></span> <span data-ttu-id="eb2e2-214">Влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-214">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="eb2e2-215">**CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-215">**CurrentUser**.</span></span> <span data-ttu-id="eb2e2-216">Влияет только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-216">Affects only the current user.</span></span>
- <span data-ttu-id="eb2e2-217">**Хранилище LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-217">**LocalMachine**.</span></span> <span data-ttu-id="eb2e2-218">Область по умолчанию, влияющая на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-218">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="eb2e2-219">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-219">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="eb2e2-220">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-220">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="eb2e2-221">При закрытии сеанса PowerShell переменная и значение удаляются.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-221">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="eb2e2-222">Политики выполнения для области **CurrentUser** записываются в куст реестра **HKEY_LOCAL_USER**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-222">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER**.</span></span>

<span data-ttu-id="eb2e2-223">Политики выполнения для области **LocalMachine** записываются в куст реестра **HKEY_LOCAL_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-223">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE**.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eb2e2-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eb2e2-224">-WhatIf</span></span>

<span data-ttu-id="eb2e2-225">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="eb2e2-226">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-226">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="eb2e2-227">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="eb2e2-227">CommonParameters</span></span>

<span data-ttu-id="eb2e2-228">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-228">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eb2e2-229">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eb2e2-229">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eb2e2-230">Входные данные</span><span class="sxs-lookup"><span data-stu-id="eb2e2-230">INPUTS</span></span>

### <span data-ttu-id="eb2e2-231">Microsoft.PowerShell.ExeКутионполици, System. String</span><span class="sxs-lookup"><span data-stu-id="eb2e2-231">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="eb2e2-232">Объект политики выполнения или строку, содержащую имя политики выполнения, можно передать в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="eb2e2-232">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="eb2e2-233">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="eb2e2-233">OUTPUTS</span></span>

### <span data-ttu-id="eb2e2-234">Нет</span><span class="sxs-lookup"><span data-stu-id="eb2e2-234">None</span></span>

<span data-ttu-id="eb2e2-235">`Set-ExecutionPolicy` не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-235">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="eb2e2-236">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="eb2e2-236">NOTES</span></span>

<span data-ttu-id="eb2e2-237">`Set-ExecutionPolicy` не изменяет области **мачинеполици** и **UserPolicy** , так как они задаются групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-237">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="eb2e2-238">`Set-ExecutionPolicy` не переопределяет групповая политика, даже если предпочтение пользователя является более узким, чем политика.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-238">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="eb2e2-239">Если групповая политика **включить выполнение скрипта** для компьютера или пользователя, параметры пользователя сохраняются, но не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-239">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="eb2e2-240">PowerShell выводит сообщение с объяснением конфликта.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-240">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="eb2e2-241">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="eb2e2-241">RELATED LINKS</span></span>

[<span data-ttu-id="eb2e2-242">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="eb2e2-242">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="eb2e2-243">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="eb2e2-243">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="eb2e2-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="eb2e2-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="eb2e2-245">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="eb2e2-245">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="eb2e2-246">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="eb2e2-246">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="eb2e2-247">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="eb2e2-247">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="eb2e2-248">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="eb2e2-248">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="eb2e2-249">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="eb2e2-249">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="eb2e2-250">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="eb2e2-250">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)


---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: 313ff4f2d3fc89263cdf4d0ede860ef8e538a2ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227766"
---
# <span data-ttu-id="77a21-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="77a21-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="77a21-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="77a21-104">SYNOPSIS</span></span>
<span data-ttu-id="77a21-105">Задает политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="77a21-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="77a21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77a21-106">SYNTAX</span></span>

### <span data-ttu-id="77a21-107">Все</span><span class="sxs-lookup"><span data-stu-id="77a21-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="77a21-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77a21-108">DESCRIPTION</span></span>

<span data-ttu-id="77a21-109">`Set-ExecutionPolicy`Командлет изменяет политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="77a21-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="77a21-110">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="77a21-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="77a21-111">Политика выполнения является частью стратегии безопасности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a21-111">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="77a21-112">Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="77a21-112">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="77a21-113">И, если перед запуском скрипты должны иметь цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="77a21-113">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="77a21-114">`Set-ExecutionPolicy`По умолчанию командлет имеет область **LocalMachine** , которая влияет на всех, кто использует этот компьютер.</span><span class="sxs-lookup"><span data-stu-id="77a21-114">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="77a21-115">Чтобы изменить политику выполнения для **LocalMachine** , запустите PowerShell с **запуском от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="77a21-115">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="77a21-116">Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="77a21-116">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="77a21-117">Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.</span><span class="sxs-lookup"><span data-stu-id="77a21-117">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="77a21-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="77a21-118">EXAMPLES</span></span>

### <span data-ttu-id="77a21-119">Пример 1. Настройка политики выполнения</span><span class="sxs-lookup"><span data-stu-id="77a21-119">Example 1: Set an execution policy</span></span>

<span data-ttu-id="77a21-120">В этом примере показано, как задать политику выполнения для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="77a21-120">This example shows how to set the execution policy for the local computer.</span></span>

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

<span data-ttu-id="77a21-121">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-121">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="77a21-122">Параметр **Scope** задает значение области по умолчанию — **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-122">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="77a21-123">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="77a21-123">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="77a21-124">Пример 2. Настройка политики выполнения, конфликтующей с групповая политика</span><span class="sxs-lookup"><span data-stu-id="77a21-124">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="77a21-125">Эта команда пытается установить **ограничение** для политики выполнения в области **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-125">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="77a21-126">**Хранилище LocalMachine** является более узким, но не является действующей политикой, так как она конфликтует с групповая политика.</span><span class="sxs-lookup"><span data-stu-id="77a21-126">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="77a21-127">Политика **ограниченного** доступа записывается в куст реестра **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="77a21-127">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

<span data-ttu-id="77a21-128">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **ограничения** .</span><span class="sxs-lookup"><span data-stu-id="77a21-128">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="77a21-129">Параметр **Scope** задает значение области по умолчанию — **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-129">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="77a21-130">`Get-ChildItem`Командлет использует параметр **path** с поставщиком **HKLM** для указания расположения реестра.</span><span class="sxs-lookup"><span data-stu-id="77a21-130">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="77a21-131">Пример 3. Применение политики выполнения с удаленного компьютера к локальному компьютеру</span><span class="sxs-lookup"><span data-stu-id="77a21-131">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="77a21-132">Эта команда получает объект политики выполнения с удаленного компьютера и устанавливает политику на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77a21-132">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="77a21-133">`Get-ExecutionPolicy` отправляет объект **Microsoft.PowerShell.Exeкутионполици** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="77a21-133">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="77a21-134">`Set-ExecutionPolicy` принимает входные данные конвейера и не требует параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="77a21-134">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="77a21-135">`Invoke-Command`Командлет выполняется на локальном компьютере и отправляет **ScriptBlock** на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="77a21-135">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="77a21-136">Параметр **ComputerName** указывает удаленный компьютер **Server01** .</span><span class="sxs-lookup"><span data-stu-id="77a21-136">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="77a21-137">Параметр **ScriptBlock** выполняется `Get-ExecutionPolicy` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77a21-137">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="77a21-138">`Get-ExecutionPolicy`Объект отправляется по конвейеру в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="77a21-138">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="77a21-139">`Set-ExecutionPolicy` применяет политику выполнения к области по умолчанию локального компьютера, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-139">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="77a21-140">Пример 4. Задание области для политики выполнения</span><span class="sxs-lookup"><span data-stu-id="77a21-140">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="77a21-141">В этом примере показано, как задать политику выполнения для указанной области, **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="77a21-141">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="77a21-142">Область **CurrentUser** влияет только на пользователя, который устанавливает эту область.</span><span class="sxs-lookup"><span data-stu-id="77a21-142">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

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

<span data-ttu-id="77a21-143">`Set-ExecutionPolicy`Задает политику **AllSigned** с помощью параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="77a21-143">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="77a21-144">Параметр **Scope** указывает **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="77a21-144">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="77a21-145">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="77a21-145">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="77a21-146">Действующая политика выполнения для пользователя преобразуется в **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-146">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="77a21-147">Пример 5. Удаление политики выполнения для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="77a21-147">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="77a21-148">В этом примере показано, как использовать **неопределенную** политику выполнения для удаления политики выполнения для указанной области.</span><span class="sxs-lookup"><span data-stu-id="77a21-148">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

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

<span data-ttu-id="77a21-149">`Set-ExecutionPolicy` использует параметр **ExecutionPolicy** для указания **неопределенной** политики.</span><span class="sxs-lookup"><span data-stu-id="77a21-149">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="77a21-150">Параметр **Scope** указывает **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="77a21-150">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="77a21-151">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="77a21-151">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="77a21-152">Пример 6. Настройка политики выполнения для текущего сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="77a21-152">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="77a21-153">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a21-153">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="77a21-154">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` и удаляется при закрытии сеанса.</span><span class="sxs-lookup"><span data-stu-id="77a21-154">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

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

<span data-ttu-id="77a21-155">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-155">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="77a21-156">Параметр **Scope** задает **процесс** value.</span><span class="sxs-lookup"><span data-stu-id="77a21-156">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="77a21-157">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="77a21-157">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="77a21-158">Пример 7. Разблокировка скрипта для его запуска без изменения политики выполнения</span><span class="sxs-lookup"><span data-stu-id="77a21-158">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="77a21-159">В этом примере показано, как политика выполнения **RemoteSigned** не позволяет выполнять неподписанные сценарии.</span><span class="sxs-lookup"><span data-stu-id="77a21-159">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="77a21-160">**Перед** использованием командлета рекомендуется прочитать код скрипта и проверить его безопасность `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="77a21-160">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="77a21-161">`Unblock-File`Командлет разблокирует скрипты для их запуска, но не изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-161">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="77a21-162">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-162">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="77a21-163">Политика задается для области по умолчанию, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-163">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="77a21-164">`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a21-164">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="77a21-165">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="77a21-165">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="77a21-166">Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="77a21-166">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="77a21-167">В этом примере код скрипта был проверен и проверен как надежный для выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-167">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="77a21-168">`Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.</span><span class="sxs-lookup"><span data-stu-id="77a21-168">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="77a21-169">Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-169">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="77a21-170">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="77a21-170">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="77a21-171">Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.</span><span class="sxs-lookup"><span data-stu-id="77a21-171">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="77a21-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77a21-172">PARAMETERS</span></span>

### <span data-ttu-id="77a21-173">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="77a21-173">-ExecutionPolicy</span></span>

<span data-ttu-id="77a21-174">Задает политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-174">Specifies the execution policy.</span></span> <span data-ttu-id="77a21-175">Если групповых политик нет, а для каждой политики выполнения каждой области задано значение **undefine** , то **ограничения** становятся действующей политикой для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="77a21-175">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="77a21-176">Допустимы следующие значения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-176">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="77a21-177">**AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-177">**AllSigned** .</span></span> <span data-ttu-id="77a21-178">Требует, чтобы все сценарии и файлы конфигурации подписаны доверенным издателем, включая сценарии, написанные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77a21-178">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="77a21-179">**Обход** .</span><span class="sxs-lookup"><span data-stu-id="77a21-179">**Bypass** .</span></span> <span data-ttu-id="77a21-180">ничего не блокируется, и никакие предупреждения и запросы не появляются.</span><span class="sxs-lookup"><span data-stu-id="77a21-180">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="77a21-181">**Default** .</span><span class="sxs-lookup"><span data-stu-id="77a21-181">**Default** .</span></span> <span data-ttu-id="77a21-182">Задает политику выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77a21-182">Sets the default execution policy.</span></span> <span data-ttu-id="77a21-183">**Ограничено** для клиентов Windows или **RemoteSigned** для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="77a21-183">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="77a21-184">**RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="77a21-184">**RemoteSigned** .</span></span> <span data-ttu-id="77a21-185">Требует, чтобы все скрипты и файлы конфигурации, скачанные из Интернета, были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="77a21-185">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="77a21-186">Политика выполнения по умолчанию для компьютеров Windows Server.</span><span class="sxs-lookup"><span data-stu-id="77a21-186">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="77a21-187">**Ограничено** .</span><span class="sxs-lookup"><span data-stu-id="77a21-187">**Restricted** .</span></span> <span data-ttu-id="77a21-188">Не загружает файлы конфигурации или не выполняет сценарии.</span><span class="sxs-lookup"><span data-stu-id="77a21-188">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="77a21-189">Политика выполнения по умолчанию клиентские компьютеры Windows.</span><span class="sxs-lookup"><span data-stu-id="77a21-189">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="77a21-190">Не **определено** .</span><span class="sxs-lookup"><span data-stu-id="77a21-190">**Undefined** .</span></span> <span data-ttu-id="77a21-191">Для области не задана политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-191">No execution policy is set for the scope.</span></span> <span data-ttu-id="77a21-192">Удаляет назначенную политику выполнения из области, которая не задается групповая политика.</span><span class="sxs-lookup"><span data-stu-id="77a21-192">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="77a21-193">Если политика выполнения во всех областях не **определена** , действующая политика выполнения **ограничена** .</span><span class="sxs-lookup"><span data-stu-id="77a21-193">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="77a21-194">Без **ограничений** .</span><span class="sxs-lookup"><span data-stu-id="77a21-194">**Unrestricted** .</span></span> <span data-ttu-id="77a21-195">загружает все файлы конфигурации и выполняет все скрипты.</span><span class="sxs-lookup"><span data-stu-id="77a21-195">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="77a21-196">Перед запуском неподписанного скрипта, загруженного из Интернета, программа просит ввести разрешение.</span><span class="sxs-lookup"><span data-stu-id="77a21-196">If you run an unsigned script that was downloaded from the Internet, you are prompted for permission before it runs.</span></span>

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

### <span data-ttu-id="77a21-197">-Force</span><span class="sxs-lookup"><span data-stu-id="77a21-197">-Force</span></span>

<span data-ttu-id="77a21-198">Подавляет все запросы подтверждения.</span><span class="sxs-lookup"><span data-stu-id="77a21-198">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="77a21-199">Будьте внимательны с этим параметром, чтобы избежать непредвиденных результатов.</span><span class="sxs-lookup"><span data-stu-id="77a21-199">Use caution with this parameter to avoid unexpected results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77a21-200">-Scope</span><span class="sxs-lookup"><span data-stu-id="77a21-200">-Scope</span></span>

<span data-ttu-id="77a21-201">Указывает область, на которую влияет политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="77a21-201">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="77a21-202">Областью по умолчанию является **хранилище LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-202">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="77a21-203">Действующая политика выполнения определяется порядком приоритета следующим образом.</span><span class="sxs-lookup"><span data-stu-id="77a21-203">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="77a21-204">**Мачинеполици** .</span><span class="sxs-lookup"><span data-stu-id="77a21-204">**MachinePolicy** .</span></span> <span data-ttu-id="77a21-205">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="77a21-205">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="77a21-206">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="77a21-206">**UserPolicy** .</span></span> <span data-ttu-id="77a21-207">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="77a21-207">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="77a21-208">**Процесс** .</span><span class="sxs-lookup"><span data-stu-id="77a21-208">**Process** .</span></span> <span data-ttu-id="77a21-209">Влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a21-209">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="77a21-210">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="77a21-210">**CurrentUser** .</span></span> <span data-ttu-id="77a21-211">Влияет только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="77a21-211">Affects only the current user.</span></span>
- <span data-ttu-id="77a21-212">**Хранилище LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="77a21-212">**LocalMachine** .</span></span> <span data-ttu-id="77a21-213">Область по умолчанию, влияющая на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="77a21-213">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="77a21-214">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a21-214">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="77a21-215">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре.</span><span class="sxs-lookup"><span data-stu-id="77a21-215">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="77a21-216">При закрытии сеанса PowerShell переменная и значение удаляются.</span><span class="sxs-lookup"><span data-stu-id="77a21-216">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="77a21-217">Политики выполнения для области **CurrentUser** записываются в куст реестра **HKEY_LOCAL_USER** .</span><span class="sxs-lookup"><span data-stu-id="77a21-217">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="77a21-218">Политики выполнения для области **LocalMachine** записываются в куст реестра **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="77a21-218">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

### <span data-ttu-id="77a21-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77a21-219">-Confirm</span></span>

<span data-ttu-id="77a21-220">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="77a21-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77a21-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77a21-221">-WhatIf</span></span>

<span data-ttu-id="77a21-222">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="77a21-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="77a21-223">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="77a21-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="77a21-224">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="77a21-224">CommonParameters</span></span>

<span data-ttu-id="77a21-225">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="77a21-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77a21-226">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="77a21-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77a21-227">Входные данные</span><span class="sxs-lookup"><span data-stu-id="77a21-227">INPUTS</span></span>

### <span data-ttu-id="77a21-228">Microsoft.PowerShell.ExeКутионполици, System. String</span><span class="sxs-lookup"><span data-stu-id="77a21-228">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="77a21-229">Объект политики выполнения или строку, содержащую имя политики выполнения, можно передать в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="77a21-229">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="77a21-230">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="77a21-230">OUTPUTS</span></span>

### <span data-ttu-id="77a21-231">Нет</span><span class="sxs-lookup"><span data-stu-id="77a21-231">None</span></span>

<span data-ttu-id="77a21-232">`Set-ExecutionPolicy` не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="77a21-232">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="77a21-233">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="77a21-233">NOTES</span></span>

<span data-ttu-id="77a21-234">`Set-ExecutionPolicy` не изменяет области **мачинеполици** и **UserPolicy** , так как они задаются групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="77a21-234">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="77a21-235">`Set-ExecutionPolicy` не переопределяет групповая политика, даже если предпочтение пользователя является более узким, чем политика.</span><span class="sxs-lookup"><span data-stu-id="77a21-235">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="77a21-236">Если групповая политика **включить выполнение скрипта** для компьютера или пользователя, параметры пользователя сохраняются, но не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="77a21-236">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="77a21-237">PowerShell выводит сообщение с объяснением конфликта.</span><span class="sxs-lookup"><span data-stu-id="77a21-237">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="77a21-238">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="77a21-238">RELATED LINKS</span></span>

[<span data-ttu-id="77a21-239">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="77a21-239">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="77a21-240">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="77a21-240">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="77a21-241">about_Providers</span><span class="sxs-lookup"><span data-stu-id="77a21-241">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="77a21-242">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="77a21-242">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="77a21-243">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="77a21-243">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="77a21-244">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="77a21-244">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="77a21-245">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="77a21-245">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="77a21-246">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="77a21-246">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="77a21-247">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="77a21-247">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)

---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: 4c45267113ff7b8a870d5a05bf3e4ab922f7e9c6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604654"
---
# <span data-ttu-id="1a2ec-102">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="1a2ec-102">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="1a2ec-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1a2ec-103">SYNOPSIS</span></span>
<span data-ttu-id="1a2ec-104">Задает политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-104">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="1a2ec-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a2ec-105">SYNTAX</span></span>

### <span data-ttu-id="1a2ec-106">Все</span><span class="sxs-lookup"><span data-stu-id="1a2ec-106">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1a2ec-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a2ec-107">DESCRIPTION</span></span>

<span data-ttu-id="1a2ec-108">`Set-ExecutionPolicy`Командлет изменяет политики выполнения PowerShell для компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-108">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="1a2ec-109">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="1a2ec-109">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="1a2ec-110">Начиная с PowerShell 6,0 для компьютеров, отличных от Windows, политика выполнения по умолчанию не **ограничена** и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-110">Beginning in PowerShell 6.0 for non-Windows computers, the default execution policy is **Unrestricted** and can't be changed.</span></span> <span data-ttu-id="1a2ec-111">`Set-ExecutionPolicy`Командлет доступен, но PowerShell отображает сообщение консоли, которое не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-111">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span>

<span data-ttu-id="1a2ec-112">Политика выполнения является частью стратегии безопасности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-112">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="1a2ec-113">Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-113">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="1a2ec-114">И, если перед запуском скрипты должны иметь цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-114">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="1a2ec-115">`Set-ExecutionPolicy`По умолчанию командлет имеет область **LocalMachine**, которая влияет на всех, кто использует этот компьютер.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-115">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine**, which affects everyone who uses the computer.</span></span> <span data-ttu-id="1a2ec-116">Чтобы изменить политику выполнения для **LocalMachine**, запустите PowerShell с **запуском от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-116">To change the execution policy for **LocalMachine**, start PowerShell with **Run as Administrator**.</span></span>

<span data-ttu-id="1a2ec-117">Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-117">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="1a2ec-118">Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-118">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="1a2ec-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="1a2ec-119">EXAMPLES</span></span>

### <span data-ttu-id="1a2ec-120">Пример 1. Настройка политики выполнения</span><span class="sxs-lookup"><span data-stu-id="1a2ec-120">Example 1: Set an execution policy</span></span>

<span data-ttu-id="1a2ec-121">В этом примере показано, как задать политику выполнения для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-121">This example shows how to set the execution policy for the local computer.</span></span>

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

<span data-ttu-id="1a2ec-122">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-122">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="1a2ec-123">Параметр **Scope** задает значение области по умолчанию — **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-123">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="1a2ec-124">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-124">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="1a2ec-125">Пример 2. Настройка политики выполнения, конфликтующей с групповая политика</span><span class="sxs-lookup"><span data-stu-id="1a2ec-125">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="1a2ec-126">Эта команда пытается установить **ограничение** для политики выполнения в области **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-126">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted**.</span></span>
<span data-ttu-id="1a2ec-127">**Хранилище LocalMachine** является более узким, но не является действующей политикой, так как она конфликтует с групповая политика.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-127">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="1a2ec-128">Политика **ограниченного** доступа записывается в куст реестра **HKEY_LOCAL_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-128">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE**.</span></span>

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

<span data-ttu-id="1a2ec-129">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **ограничения** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-129">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="1a2ec-130">Параметр **Scope** задает значение области по умолчанию — **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-130">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span>
<span data-ttu-id="1a2ec-131">`Get-ChildItem`Командлет использует параметр **path** с поставщиком **HKLM** для указания расположения реестра.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-131">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="1a2ec-132">Пример 3. Применение политики выполнения с удаленного компьютера к локальному компьютеру</span><span class="sxs-lookup"><span data-stu-id="1a2ec-132">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="1a2ec-133">Эта команда получает объект политики выполнения с удаленного компьютера и устанавливает политику на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-133">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="1a2ec-134">`Get-ExecutionPolicy` отправляет объект **Microsoft.PowerShell.Exeкутионполици** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-134">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="1a2ec-135">`Set-ExecutionPolicy` принимает входные данные конвейера и не требует параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-135">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="1a2ec-136">`Invoke-Command`Командлет выполняется на локальном компьютере и отправляет **ScriptBlock** на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-136">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="1a2ec-137">Параметр **ComputerName** указывает удаленный компьютер **Server01**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-137">The **ComputerName** parameter specifies the remote computer, **Server01**.</span></span> <span data-ttu-id="1a2ec-138">Параметр **ScriptBlock** выполняется `Get-ExecutionPolicy` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-138">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="1a2ec-139">`Get-ExecutionPolicy`Объект отправляется по конвейеру в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-139">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="1a2ec-140">`Set-ExecutionPolicy` применяет политику выполнения к области по умолчанию локального компьютера, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-140">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine**.</span></span>

### <span data-ttu-id="1a2ec-141">Пример 4. Задание области для политики выполнения</span><span class="sxs-lookup"><span data-stu-id="1a2ec-141">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="1a2ec-142">В этом примере показано, как задать политику выполнения для указанной области, **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-142">This example shows how to set an execution policy for a specified scope, **CurrentUser**.</span></span> <span data-ttu-id="1a2ec-143">Область **CurrentUser** влияет только на пользователя, который устанавливает эту область.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-143">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

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

<span data-ttu-id="1a2ec-144">`Set-ExecutionPolicy`Задает политику **AllSigned** с помощью параметра **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-144">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="1a2ec-145">Параметр **Scope** указывает **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-145">The **Scope** parameter specifies the **CurrentUser**.</span></span> <span data-ttu-id="1a2ec-146">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-146">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="1a2ec-147">Действующая политика выполнения для пользователя преобразуется в **AllSigned**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-147">The effective execution policy for the user becomes **AllSigned**.</span></span>

### <span data-ttu-id="1a2ec-148">Пример 5. Удаление политики выполнения для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="1a2ec-148">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="1a2ec-149">В этом примере показано, как использовать **неопределенную** политику выполнения для удаления политики выполнения для указанной области.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-149">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

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

<span data-ttu-id="1a2ec-150">`Set-ExecutionPolicy` использует параметр **ExecutionPolicy** для указания **неопределенной** политики.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-150">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="1a2ec-151">Параметр **Scope** указывает **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-151">The **Scope** parameter specifies the **CurrentUser**.</span></span> <span data-ttu-id="1a2ec-152">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-152">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="1a2ec-153">Пример 6. Настройка политики выполнения для текущего сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a2ec-153">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="1a2ec-154">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-154">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="1a2ec-155">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` и удаляется при закрытии сеанса.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-155">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

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

<span data-ttu-id="1a2ec-156">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-156">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="1a2ec-157">Параметр **Scope** задает **процесс** value.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-157">The **Scope** parameter specifies the value **Process**.</span></span> <span data-ttu-id="1a2ec-158">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-158">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="1a2ec-159">Пример 7. Разблокировка скрипта для его запуска без изменения политики выполнения</span><span class="sxs-lookup"><span data-stu-id="1a2ec-159">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="1a2ec-160">В этом примере показано, как политика выполнения **RemoteSigned** не позволяет выполнять неподписанные сценарии.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-160">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="1a2ec-161">**Перед** использованием командлета рекомендуется прочитать код скрипта и проверить его безопасность `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-161">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="1a2ec-162">`Unblock-File`Командлет разблокирует скрипты для их запуска, но не изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-162">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="1a2ec-163">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-163">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="1a2ec-164">Политика задается для области по умолчанию, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-164">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="1a2ec-165">`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-165">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="1a2ec-166">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-166">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="1a2ec-167">Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-167">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="1a2ec-168">В этом примере код скрипта был проверен и проверен как надежный для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-168">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="1a2ec-169">`Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-169">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="1a2ec-170">Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-170">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="1a2ec-171">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-171">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="1a2ec-172">Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-172">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="1a2ec-173">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a2ec-173">PARAMETERS</span></span>

### <span data-ttu-id="1a2ec-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1a2ec-174">-Confirm</span></span>

<span data-ttu-id="1a2ec-175">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-175">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1a2ec-176">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="1a2ec-176">-ExecutionPolicy</span></span>

<span data-ttu-id="1a2ec-177">Задает политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-177">Specifies the execution policy.</span></span> <span data-ttu-id="1a2ec-178">Если групповых политик нет, а для каждой политики выполнения каждой области задано значение **undefine**, то **ограничения** становятся действующей политикой для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-178">If there are no Group Policies and each scope's execution policy is set to **Undefined**, then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="1a2ec-179">Допустимы следующие значения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-179">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="1a2ec-180">**AllSigned**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-180">**AllSigned**.</span></span> <span data-ttu-id="1a2ec-181">Требует, чтобы все сценарии и файлы конфигурации подписаны доверенным издателем, включая сценарии, написанные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-181">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="1a2ec-182">**Обход**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-182">**Bypass**.</span></span> <span data-ttu-id="1a2ec-183">ничего не блокируется, и никакие предупреждения и запросы не появляются.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-183">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="1a2ec-184">**Default**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-184">**Default**.</span></span> <span data-ttu-id="1a2ec-185">Задает политику выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-185">Sets the default execution policy.</span></span> <span data-ttu-id="1a2ec-186">**Ограничено** для клиентов Windows или **RemoteSigned** для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-186">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="1a2ec-187">**RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-187">**RemoteSigned**.</span></span> <span data-ttu-id="1a2ec-188">Требует, чтобы все скрипты и файлы конфигурации, скачанные из Интернета, были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-188">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="1a2ec-189">Политика выполнения по умолчанию для компьютеров Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-189">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="1a2ec-190">**Ограничено**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-190">**Restricted**.</span></span> <span data-ttu-id="1a2ec-191">Не загружает файлы конфигурации или не выполняет сценарии.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-191">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="1a2ec-192">Политика выполнения по умолчанию клиентские компьютеры Windows.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-192">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="1a2ec-193">Не **определено**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-193">**Undefined**.</span></span> <span data-ttu-id="1a2ec-194">Для области не задана политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-194">No execution policy is set for the scope.</span></span> <span data-ttu-id="1a2ec-195">Удаляет назначенную политику выполнения из области, которая не задается групповая политика.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-195">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="1a2ec-196">Если политика выполнения во всех областях не **определена**, действующая политика выполнения **ограничена**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-196">If the execution policy in all scopes is **Undefined**, the effective execution policy is **Restricted**.</span></span>
- <span data-ttu-id="1a2ec-197">Без **ограничений**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-197">**Unrestricted**.</span></span> <span data-ttu-id="1a2ec-198">Начиная с PowerShell 6,0 это политика выполнения по умолчанию для компьютеров, отличных от Windows, и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-198">Beginning in PowerShell 6.0, this is the default execution policy for non-Windows computers and can't be changed.</span></span> <span data-ttu-id="1a2ec-199">загружает все файлы конфигурации и выполняет все скрипты.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-199">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="1a2ec-200">При запуске неподписанного скрипта, скачанного из Интернета, перед запуском появится запрос на разрешение.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-200">If you run an unsigned script that was downloaded from the internet, you're prompted for permission before it runs.</span></span>

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

### <span data-ttu-id="1a2ec-201">-Force</span><span class="sxs-lookup"><span data-stu-id="1a2ec-201">-Force</span></span>

<span data-ttu-id="1a2ec-202">Подавляет все запросы подтверждения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-202">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="1a2ec-203">Будьте внимательны с этим параметром, чтобы избежать непредвиденных результатов.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-203">Use caution with this parameter to avoid unexpected results.</span></span>

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

### <span data-ttu-id="1a2ec-204">-Scope</span><span class="sxs-lookup"><span data-stu-id="1a2ec-204">-Scope</span></span>

<span data-ttu-id="1a2ec-205">Указывает область, на которую влияет политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-205">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="1a2ec-206">Областью по умолчанию является **хранилище LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-206">The default scope is **LocalMachine**.</span></span>

<span data-ttu-id="1a2ec-207">Действующая политика выполнения определяется порядком приоритета следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-207">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="1a2ec-208">**Мачинеполици**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-208">**MachinePolicy**.</span></span> <span data-ttu-id="1a2ec-209">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-209">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="1a2ec-210">**UserPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-210">**UserPolicy**.</span></span> <span data-ttu-id="1a2ec-211">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-211">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="1a2ec-212">**Процесс**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-212">**Process**.</span></span> <span data-ttu-id="1a2ec-213">Влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-213">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="1a2ec-214">**CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-214">**CurrentUser**.</span></span> <span data-ttu-id="1a2ec-215">Влияет только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-215">Affects only the current user.</span></span>
- <span data-ttu-id="1a2ec-216">**Хранилище LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-216">**LocalMachine**.</span></span> <span data-ttu-id="1a2ec-217">Область по умолчанию, влияющая на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-217">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="1a2ec-218">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-218">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="1a2ec-219">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-219">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="1a2ec-220">При закрытии сеанса PowerShell переменная и значение удаляются.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-220">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="1a2ec-221">Политики выполнения для области **CurrentUser** записываются в куст реестра **HKEY_LOCAL_USER**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-221">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER**.</span></span>

<span data-ttu-id="1a2ec-222">Политики выполнения для области **LocalMachine** записываются в куст реестра **HKEY_LOCAL_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-222">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE**.</span></span>

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

### <span data-ttu-id="1a2ec-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1a2ec-223">-WhatIf</span></span>

<span data-ttu-id="1a2ec-224">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1a2ec-225">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-225">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1a2ec-226">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1a2ec-226">CommonParameters</span></span>

<span data-ttu-id="1a2ec-227">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a2ec-228">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a2ec-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a2ec-229">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1a2ec-229">INPUTS</span></span>

### <span data-ttu-id="1a2ec-230">Microsoft.PowerShell.ExeКутионполици, System. String</span><span class="sxs-lookup"><span data-stu-id="1a2ec-230">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="1a2ec-231">Объект политики выполнения или строку, содержащую имя политики выполнения, можно передать в `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="1a2ec-231">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="1a2ec-232">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1a2ec-232">OUTPUTS</span></span>

### <span data-ttu-id="1a2ec-233">None</span><span class="sxs-lookup"><span data-stu-id="1a2ec-233">None</span></span>

<span data-ttu-id="1a2ec-234">`Set-ExecutionPolicy` не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-234">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="1a2ec-235">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1a2ec-235">NOTES</span></span>

<span data-ttu-id="1a2ec-236">`Set-ExecutionPolicy` не изменяет области **мачинеполици** и **UserPolicy** , так как они задаются групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-236">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="1a2ec-237">`Set-ExecutionPolicy` не переопределяет групповая политика, даже если предпочтение пользователя является более узким, чем политика.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-237">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="1a2ec-238">Если групповая политика **включить выполнение скрипта** для компьютера или пользователя, параметры пользователя сохраняются, но не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-238">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="1a2ec-239">PowerShell выводит сообщение с объяснением конфликта.</span><span class="sxs-lookup"><span data-stu-id="1a2ec-239">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="1a2ec-240">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1a2ec-240">RELATED LINKS</span></span>

[<span data-ttu-id="1a2ec-241">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="1a2ec-241">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="1a2ec-242">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="1a2ec-242">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="1a2ec-243">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1a2ec-243">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="1a2ec-244">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="1a2ec-244">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="1a2ec-245">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1a2ec-245">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="1a2ec-246">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="1a2ec-246">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="1a2ec-247">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="1a2ec-247">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="1a2ec-248">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="1a2ec-248">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="1a2ec-249">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="1a2ec-249">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)


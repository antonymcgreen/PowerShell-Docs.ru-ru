---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d33961d9c0b1980d84d35a33c45d965e84231914
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229413"
---
# <span data-ttu-id="3c6a0-103">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="3c6a0-103">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="3c6a0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3c6a0-104">SYNOPSIS</span></span>
<span data-ttu-id="3c6a0-105">Получает политики выполнения для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-105">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="3c6a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c6a0-106">SYNTAX</span></span>

### <span data-ttu-id="3c6a0-107">Все</span><span class="sxs-lookup"><span data-stu-id="3c6a0-107">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="3c6a0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c6a0-108">DESCRIPTION</span></span>

<span data-ttu-id="3c6a0-109">Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-109">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="3c6a0-110">Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-110">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="3c6a0-111">Действующая политика выполнения определяется политиками выполнения, которые задаются `Set-ExecutionPolicy` параметрами и групповая политика.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-111">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="3c6a0-112">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-112">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="3c6a0-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c6a0-113">EXAMPLES</span></span>

### <span data-ttu-id="3c6a0-114">Пример 1. получение всех политик выполнения</span><span class="sxs-lookup"><span data-stu-id="3c6a0-114">Example 1: Get all execution policies</span></span>

<span data-ttu-id="3c6a0-115">Эта команда отображает политики выполнения для каждой области в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-115">This command displays the execution policies for each scope in the order of precedence.</span></span>

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

<span data-ttu-id="3c6a0-116">`Get-ExecutionPolicy`Командлет использует параметр **List** для вывода политики выполнения каждой области.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-116">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="3c6a0-117">Пример 2. Настройка политики выполнения</span><span class="sxs-lookup"><span data-stu-id="3c6a0-117">Example 2: Set an execution policy</span></span>

<span data-ttu-id="3c6a0-118">В этом примере показано, как задать политику выполнения для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-118">This example shows how to set an execution policy for the local computer.</span></span>

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="3c6a0-119">`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-119">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="3c6a0-120">Параметр **Scope** задает значение области по умолчанию — **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-120">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="3c6a0-121">Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-121">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="3c6a0-122">Пример 3. получение действующей политики выполнения</span><span class="sxs-lookup"><span data-stu-id="3c6a0-122">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="3c6a0-123">В этом примере показано, как отобразить действующую политику выполнения для сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-123">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

<span data-ttu-id="3c6a0-124">`Get-ExecutionPolicy`Командлет использует параметр **List** для вывода политики выполнения каждой области.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-124">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="3c6a0-125">`Get-ExecutionPolicy`Командлет выполняется без параметра для вывода действующей политики выполнения **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-125">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned** .</span></span>

### <span data-ttu-id="3c6a0-126">Пример 4. Разблокировка скрипта для его запуска без изменения политики выполнения</span><span class="sxs-lookup"><span data-stu-id="3c6a0-126">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="3c6a0-127">В этом примере показано, как политика выполнения **RemoteSigned** не позволяет выполнять неподписанные сценарии.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-127">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="3c6a0-128">**Перед** использованием командлета рекомендуется прочитать код скрипта и проверить его безопасность `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-128">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="3c6a0-129">`Unblock-File`Командлет разблокирует скрипты для их запуска, но не изменяет политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-129">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="3c6a0-130">`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-130">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="3c6a0-131">Политика задается для области по умолчанию, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-131">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="3c6a0-132">`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-132">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="3c6a0-133">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-133">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="3c6a0-134">Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-134">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="3c6a0-135">В этом примере код скрипта был проверен и проверен как надежный для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-135">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="3c6a0-136">`Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-136">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="3c6a0-137">Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-137">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="3c6a0-138">Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-138">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="3c6a0-139">Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-139">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="3c6a0-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c6a0-140">PARAMETERS</span></span>

### <span data-ttu-id="3c6a0-141">-List</span><span class="sxs-lookup"><span data-stu-id="3c6a0-141">-List</span></span>

<span data-ttu-id="3c6a0-142">Получает все значения политики выполнения для сеанса, перечисленные в порядке приоритетности,</span><span class="sxs-lookup"><span data-stu-id="3c6a0-142">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="3c6a0-143">По умолчанию `Get-ExecutionPolicy` получает только действующую политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-143">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="3c6a0-144">-Scope</span><span class="sxs-lookup"><span data-stu-id="3c6a0-144">-Scope</span></span>

<span data-ttu-id="3c6a0-145">Указывает область, на которую влияет политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-145">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="3c6a0-146">Действующая политика выполнения определяется порядком приоритета следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-146">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="3c6a0-147">**Мачинеполици** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-147">**MachinePolicy** .</span></span> <span data-ttu-id="3c6a0-148">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-148">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="3c6a0-149">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-149">**UserPolicy** .</span></span> <span data-ttu-id="3c6a0-150">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-150">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="3c6a0-151">**Процесс** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-151">**Process** .</span></span> <span data-ttu-id="3c6a0-152">Влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-152">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="3c6a0-153">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-153">**CurrentUser** .</span></span> <span data-ttu-id="3c6a0-154">Влияет только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-154">Affects only the current user.</span></span>
- <span data-ttu-id="3c6a0-155">**Хранилище LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-155">**LocalMachine** .</span></span> <span data-ttu-id="3c6a0-156">Область по умолчанию, влияющая на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-156">Default scope that affects all users of the computer.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3c6a0-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3c6a0-157">CommonParameters</span></span>

<span data-ttu-id="3c6a0-158">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c6a0-159">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c6a0-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c6a0-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3c6a0-160">INPUTS</span></span>

### <span data-ttu-id="3c6a0-161">Нет</span><span class="sxs-lookup"><span data-stu-id="3c6a0-161">None</span></span>

<span data-ttu-id="3c6a0-162">`Get-ExecutionPolicy` не принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-162">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="3c6a0-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3c6a0-163">OUTPUTS</span></span>

### <span data-ttu-id="3c6a0-164">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="3c6a0-164">Microsoft.PowerShell.ExecutionPolicy</span></span>

## <span data-ttu-id="3c6a0-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3c6a0-165">NOTES</span></span>

<span data-ttu-id="3c6a0-166">Политика выполнения является частью стратегии безопасности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="3c6a0-167">Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="3c6a0-168">И, если перед запуском скрипты должны иметь цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="3c6a0-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3c6a0-169">RELATED LINKS</span></span>

[<span data-ttu-id="3c6a0-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="3c6a0-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="3c6a0-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="3c6a0-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="3c6a0-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="3c6a0-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="3c6a0-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="3c6a0-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="3c6a0-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="3c6a0-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)


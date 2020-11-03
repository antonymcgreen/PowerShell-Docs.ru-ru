---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227837"
---
# <span data-ttu-id="2005a-103">Test-ComputerSecureChannel</span><span class="sxs-lookup"><span data-stu-id="2005a-103">Test-ComputerSecureChannel</span></span>

## <span data-ttu-id="2005a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2005a-104">SYNOPSIS</span></span>
<span data-ttu-id="2005a-105">Тестирует и восстанавливает безопасный канал между локальным компьютером и его доменом.</span><span class="sxs-lookup"><span data-stu-id="2005a-105">Tests and repairs the secure channel between the local computer and its domain.</span></span>

## <span data-ttu-id="2005a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2005a-106">SYNTAX</span></span>

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2005a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2005a-107">DESCRIPTION</span></span>
<span data-ttu-id="2005a-108">Командлет **Test-ComputerSecureChannel** проверяет, правильно ли работает канал между локальным компьютером и его доменом. Для этого он проверяет состояние отношений доверия.</span><span class="sxs-lookup"><span data-stu-id="2005a-108">The **Test-ComputerSecureChannel** cmdlet verifies that the channel between the local computer and its domain is working correctly by checking the status of its trust relationships.</span></span>
<span data-ttu-id="2005a-109">В случае сбоя подключения можно использовать параметр *Repair* , чтобы попытаться восстановить его.</span><span class="sxs-lookup"><span data-stu-id="2005a-109">If a connection fails, you can use the *Repair* parameter to try to restore it.</span></span>

<span data-ttu-id="2005a-110">Командлет **Test-ComputerSecureChannel** возвращает значение $True, если канал работает правильно, и $False в противном случае.</span><span class="sxs-lookup"><span data-stu-id="2005a-110">**Test-ComputerSecureChannel** returns $True if the channel is working correctly and $False if it is not.</span></span>
<span data-ttu-id="2005a-111">Это позволяет использовать его в условных операторах в функциях и сценариях.</span><span class="sxs-lookup"><span data-stu-id="2005a-111">This result lets you use the cmdlet in conditional statements in functions and scripts.</span></span>
<span data-ttu-id="2005a-112">Чтобы получить более подробные результаты теста, используйте параметр *verbose* .</span><span class="sxs-lookup"><span data-stu-id="2005a-112">To get more detailed test results, use the *Verbose* parameter.</span></span>

<span data-ttu-id="2005a-113">Этот командлет работает во многом так же, как программа NetDom.exe.</span><span class="sxs-lookup"><span data-stu-id="2005a-113">This cmdlet works much like NetDom.exe.</span></span>
<span data-ttu-id="2005a-114">Как NetDom, так и **Test-ComputerSecureChannel** используют службу **Netlogon** для выполнения действий.</span><span class="sxs-lookup"><span data-stu-id="2005a-114">Both NetDom and **Test-ComputerSecureChannel** use the **NetLogon** service to perform the actions.</span></span>

## <span data-ttu-id="2005a-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="2005a-115">EXAMPLES</span></span>

### <span data-ttu-id="2005a-116">Пример 1. Тестирование канала между локальным компьютером и его доменом</span><span class="sxs-lookup"><span data-stu-id="2005a-116">Example 1: Test a channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel
True
```

<span data-ttu-id="2005a-117">Эта команда проверяет канал между локальным компьютером и доменом, в который он входит.</span><span class="sxs-lookup"><span data-stu-id="2005a-117">This command tests the channel between the local computer and the domain to which it is joined.</span></span>

### <span data-ttu-id="2005a-118">Пример 2. Тестирование канала между локальным компьютером и контроллером домена</span><span class="sxs-lookup"><span data-stu-id="2005a-118">Example 2: Test a channel between the local computer and a domain controller</span></span>

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

<span data-ttu-id="2005a-119">Эта команда задает предпочтительный контроллер домена для проверки.</span><span class="sxs-lookup"><span data-stu-id="2005a-119">This command specifies a preferred domain controller for the test.</span></span>

### <span data-ttu-id="2005a-120">Пример 3. Тестирование канала между локальным компьютером и его доменом</span><span class="sxs-lookup"><span data-stu-id="2005a-120">Example 3: Reset the channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

<span data-ttu-id="2005a-121">Эта команда переустанавливает канал между локальным компьютером и его доменом.</span><span class="sxs-lookup"><span data-stu-id="2005a-121">This command resets the channel between the local computer and its domain.</span></span>

### <span data-ttu-id="2005a-122">Пример 4. Отображение подробных сведений о тесте</span><span class="sxs-lookup"><span data-stu-id="2005a-122">Example 4: Display detailed information about the test</span></span>

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

<span data-ttu-id="2005a-123">Эта команда использует параметр *verbose* Common для запроса подробных сообщений об операции.</span><span class="sxs-lookup"><span data-stu-id="2005a-123">This command uses the *Verbose* common parameter to request detailed messages about the operation.</span></span>
<span data-ttu-id="2005a-124">Сведения о параметре *Verbose* см. в разделе about_CommonParameters.</span><span class="sxs-lookup"><span data-stu-id="2005a-124">For more information about *Verbose* , see about_CommonParameters.</span></span>

### <span data-ttu-id="2005a-125">Пример 5. Проверка подключения, перед тем как выполнить скрипт</span><span class="sxs-lookup"><span data-stu-id="2005a-125">Example 5: Test a connection before you run a script</span></span>

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

<span data-ttu-id="2005a-126">В этом примере показано, как использовать командлет **Test-ComputerSecureChannel** для проверки подключения перед выполнением скрипта, которому оно требуется.</span><span class="sxs-lookup"><span data-stu-id="2005a-126">This example shows how to use **Test-ComputerSecureChannel** to test a connection before you run a script that requires the connection.</span></span>

<span data-ttu-id="2005a-127">В первой команде используется командлет Set-Alias с целью создания псевдонима для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="2005a-127">The first command uses the Set-Alias cmdlet to create an alias for the cmdlet name.</span></span>
<span data-ttu-id="2005a-128">Это позволяет сэкономить место и избежать ошибок при вводе.</span><span class="sxs-lookup"><span data-stu-id="2005a-128">This saves space and prevents typing errors.</span></span>

<span data-ttu-id="2005a-129">Оператор **If** проверяет значение, возвращенное командлетом **Test-ComputerSecureChannel** , перед выполнением скрипта.</span><span class="sxs-lookup"><span data-stu-id="2005a-129">The **If** statement checks the value that **Test-ComputerSecureChannel** returns before it runs a script.</span></span>

## <span data-ttu-id="2005a-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2005a-130">PARAMETERS</span></span>

### <span data-ttu-id="2005a-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="2005a-131">-Credential</span></span>
<span data-ttu-id="2005a-132">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="2005a-132">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="2005a-133">Введите имя пользователя, например User01, Domain01\User01, либо укажите объект **PSCredential** , например возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="2005a-133">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one that the Get-Credential cmdlet returns.</span></span>
<span data-ttu-id="2005a-134">По умолчанию командлет использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2005a-134">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="2005a-135">Параметр *Credential* предназначен для использования в командах, которые используют параметр *Repair* для восстановления канала между компьютером и доменом.</span><span class="sxs-lookup"><span data-stu-id="2005a-135">The *Credential* parameter is designed for use in commands that use the *Repair* parameter to repair the channel between the computer and the domain.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2005a-136">-Repair</span><span class="sxs-lookup"><span data-stu-id="2005a-136">-Repair</span></span>
<span data-ttu-id="2005a-137">Указывает, что этот командлет удаляет и повторно создает канал, установленный службой NetLogon.</span><span class="sxs-lookup"><span data-stu-id="2005a-137">Indicates that this cmdlet removes and then rebuilds the channel established by the NetLogon service.</span></span>
<span data-ttu-id="2005a-138">Используйте этот параметр, чтобы попытаться восстановить подключение, которое не прошло проверку.</span><span class="sxs-lookup"><span data-stu-id="2005a-138">Use this parameter to try to restore a connection that has failed the test.</span></span>

<span data-ttu-id="2005a-139">Для использования этого параметра текущий пользователь должен быть участником группы "Администраторы" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2005a-139">To use this parameter, the current user must be a member of the Administrators group on the local computer.</span></span>

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

### <span data-ttu-id="2005a-140">-Server</span><span class="sxs-lookup"><span data-stu-id="2005a-140">-Server</span></span>
<span data-ttu-id="2005a-141">Указывает контроллер домена для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="2005a-141">Specifies the domain controller to run the command.</span></span>
<span data-ttu-id="2005a-142">Если этот параметр не указан, командлет выбирает контроллер домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2005a-142">If this parameter is not specified, this cmdlet selects a default domain controller for the operation.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2005a-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2005a-143">-Confirm</span></span>
<span data-ttu-id="2005a-144">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2005a-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2005a-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2005a-145">-WhatIf</span></span>
<span data-ttu-id="2005a-146">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2005a-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2005a-147">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2005a-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2005a-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2005a-148">CommonParameters</span></span>
<span data-ttu-id="2005a-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2005a-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2005a-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2005a-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2005a-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2005a-151">INPUTS</span></span>

### <span data-ttu-id="2005a-152">Нет</span><span class="sxs-lookup"><span data-stu-id="2005a-152">None</span></span>
<span data-ttu-id="2005a-153">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="2005a-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2005a-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2005a-154">OUTPUTS</span></span>

### <span data-ttu-id="2005a-155">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="2005a-155">System.Boolean</span></span>
<span data-ttu-id="2005a-156">Этот командлет возвращает значение $True, если подключение работает правильно, и значение $False в противном случае.</span><span class="sxs-lookup"><span data-stu-id="2005a-156">This cmdlet returns $True if the connection is working correctly and $False if it is not.</span></span>

## <span data-ttu-id="2005a-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2005a-157">NOTES</span></span>

* <span data-ttu-id="2005a-158">Чтобы выполнить команду **Test-ComputerSecureChannel** в Windows Vista и более поздних версиях операционной системы Windows, откройте среду Windows PowerShell, используя параметр "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="2005a-158">To run a **Test-ComputerSecureChannel** command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="2005a-159">Командлет **Test-ComputerSecureChannel** реализован с помощью функции **I_NetLogonControl2** , которая контролирует различные аспекты службы Netlogon.</span><span class="sxs-lookup"><span data-stu-id="2005a-159">**Test-ComputerSecureChannel** is implemented by using the **I_NetLogonControl2** function, which controls various aspects of the Netlogon service.</span></span>

## <span data-ttu-id="2005a-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2005a-160">RELATED LINKS</span></span>

[<span data-ttu-id="2005a-161">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="2005a-161">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="2005a-162">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="2005a-162">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="2005a-163">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="2005a-163">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="2005a-164">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="2005a-164">Stop-Computer</span></span>](Stop-Computer.md)

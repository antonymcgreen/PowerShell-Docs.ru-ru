---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388354"
---
# <span data-ttu-id="6aa72-103">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-103">Add-Computer</span></span>

## <span data-ttu-id="6aa72-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6aa72-104">SYNOPSIS</span></span>
<span data-ttu-id="6aa72-105">Добавляет локальный компьютер в домен или рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="6aa72-105">Add the local computer to a domain or workgroup.</span></span>

## <span data-ttu-id="6aa72-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6aa72-106">SYNTAX</span></span>

### <span data-ttu-id="6aa72-107">Домен (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6aa72-107">Domain (Default)</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6aa72-108">Рабочая группа</span><span class="sxs-lookup"><span data-stu-id="6aa72-108">Workgroup</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="6aa72-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6aa72-109">DESCRIPTION</span></span>

<span data-ttu-id="6aa72-110">`Add-Computer`Командлет добавляет локальный или удаленный компьютер в домен или рабочую группу или перемещает их из одного домена в другой.</span><span class="sxs-lookup"><span data-stu-id="6aa72-110">The `Add-Computer` cmdlet adds the local computer or remote computers to a domain or workgroup, or moves them from one domain to another.</span></span> <span data-ttu-id="6aa72-111">Он также создает учетную запись домена при добавлении компьютера в домен без учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6aa72-111">It also creates a domain account if the computer is added to the domain without an account.</span></span>

<span data-ttu-id="6aa72-112">Параметры этого командлета можно использовать для указания контроллера домена и подразделения или выполнения незащищенного присоединения.</span><span class="sxs-lookup"><span data-stu-id="6aa72-112">You can use the parameters of this cmdlet to specify an organizational unit (OU) and domain controller or to perform an unsecure join.</span></span>

<span data-ttu-id="6aa72-113">Чтобы получить результаты выполнения команды, используйте параметры **Verbose** и **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-113">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span>

## <span data-ttu-id="6aa72-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="6aa72-114">EXAMPLES</span></span>

### <span data-ttu-id="6aa72-115">Пример 1. Добавление локального компьютера в домен и перезагрузка компьютера</span><span class="sxs-lookup"><span data-stu-id="6aa72-115">Example 1: Add a local computer to a domain then restart the computer</span></span>

```powershell
Add-Computer -DomainName Domain01 -Restart
```

<span data-ttu-id="6aa72-116">Эта команда добавляет локальный компьютер в домен Domain01, а затем перезагружает компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="6aa72-116">This command adds the local computer to the Domain01 domain and then restarts the computer to make the change effective.</span></span>

### <span data-ttu-id="6aa72-117">Пример 2. Добавление локального компьютера в рабочую группу</span><span class="sxs-lookup"><span data-stu-id="6aa72-117">Example 2: Add a local computer to a workgroup</span></span>

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

<span data-ttu-id="6aa72-118">Эта команда добавляет локальный компьютер в рабочую группу Workgroup-A.</span><span class="sxs-lookup"><span data-stu-id="6aa72-118">This command adds the local computer to the Workgroup-A workgroup.</span></span>

### <span data-ttu-id="6aa72-119">Пример 3. Добавление локального компьютера в домен</span><span class="sxs-lookup"><span data-stu-id="6aa72-119">Example 3: Add a local computer to a domain</span></span>

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

<span data-ttu-id="6aa72-120">Эта команда добавляет локальный компьютер в домен Domain01, используя контроллер домена Domain01\DC01.</span><span class="sxs-lookup"><span data-stu-id="6aa72-120">This command adds the local computer to the Domain01 domain by using the Domain01\DC01 domain controller.</span></span>

<span data-ttu-id="6aa72-121">Команда использует параметры **PassThru** и **Verbose** для получения подробных сведений о результатах выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="6aa72-121">The command uses the **PassThru** and **Verbose** parameters to get detailed information about the results of the command.</span></span>

### <span data-ttu-id="6aa72-122">Пример 4. Добавление локального компьютера в домен с помощью параметра Аупас</span><span class="sxs-lookup"><span data-stu-id="6aa72-122">Example 4: Add a local computer to a domain using the OUPath parameter</span></span>

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

<span data-ttu-id="6aa72-123">Эта команда добавляет локальный компьютер в домен Domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-123">This command adds the local computer to the Domain02 domain.</span></span>
<span data-ttu-id="6aa72-124">Она использует параметр OUPath, чтобы указать подразделение для новых учетных записей.</span><span class="sxs-lookup"><span data-stu-id="6aa72-124">It uses the OUPath parameter to specify the organizational unit for the new accounts.</span></span>

### <span data-ttu-id="6aa72-125">Пример 5. Добавление локального компьютера в домен с использованием учетных данных</span><span class="sxs-lookup"><span data-stu-id="6aa72-125">Example 5: Add a local computer to a domain using credentials</span></span>

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

<span data-ttu-id="6aa72-126">Эта команда добавляет компьютер Server01 в домен Domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-126">This command adds the Server01 computer to the Domain02 domain.</span></span> <span data-ttu-id="6aa72-127">Она использует параметр **LocalCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на подключение к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="6aa72-127">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the Server01 computer.</span></span> <span data-ttu-id="6aa72-128">Она использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на присоединение компьютеров к домену.</span><span class="sxs-lookup"><span data-stu-id="6aa72-128">It uses the **Credential** parameter to specify a user account that has permission to join computers to the domain.</span></span> <span data-ttu-id="6aa72-129">Она использует параметр **Restart** , чтобы перезагрузить компьютер после выполнения операции присоединения, и параметр **Force** для отключения запросов подтверждения пользователем.</span><span class="sxs-lookup"><span data-stu-id="6aa72-129">It uses the **Restart** parameter to restart the computer after the join operation completes and the **Force** parameter to suppress user confirmation messages.</span></span>

### <span data-ttu-id="6aa72-130">Пример 6. Перемещение группы компьютеров в новый домен</span><span class="sxs-lookup"><span data-stu-id="6aa72-130">Example 6: Move a group of computers to a new domain</span></span>

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="6aa72-131">Эта команда перемещает компьютеры Server01 и Server02 и локальный компьютер из Domain01 в Domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-131">This command moves the Server01 and Server02 computers, and the local computer, from Domain01 to Domain02.</span></span>

<span data-ttu-id="6aa72-132">Она использует параметр **LocalCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на подключение к трем задействованным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="6aa72-132">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the three affected computers.</span></span> <span data-ttu-id="6aa72-133">Она использует параметр **UnjoinDomainCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на исключение компьютеров из домена Domain01, и параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на присоединение компьютеров к домену Domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-133">It uses the **UnjoinDomainCredential** parameter to specify a user account that has permission to unjoin the computers from the Domain01 domain and the **Credential** parameter to specify a user account that has permission to join the computers to the Domain02 domain.</span></span> <span data-ttu-id="6aa72-134">Она использует параметр **Restart** для перезагрузки всех трех компьютеров после завершения перемещения.</span><span class="sxs-lookup"><span data-stu-id="6aa72-134">It uses the **Restart** parameter to restart all three computers after the move is complete.</span></span>

### <span data-ttu-id="6aa72-135">Пример 7. Перемещение компьютера в новый домен и изменение имени компьютера</span><span class="sxs-lookup"><span data-stu-id="6aa72-135">Example 7: Move a computer to a new domain and change the name of the computer</span></span>

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="6aa72-136">Эта команда перемещает компьютер Server01 в домен Domain02 и изменяет имя компьютера на Server044.</span><span class="sxs-lookup"><span data-stu-id="6aa72-136">This command moves the Server01 computer to the Domain02 and changes the machine name to Server044.</span></span>

<span data-ttu-id="6aa72-137">Команда использует учетные данные текущего пользователя для подключения к компьютеру Server01 и исключению его из текущего домена.</span><span class="sxs-lookup"><span data-stu-id="6aa72-137">The command uses the credential of the current user to connect to the Server01 computer and unjoin it from its current domain.</span></span> <span data-ttu-id="6aa72-138">Параметр **Credential** используется для указания учетной записи пользователя, имеющей разрешение на присоединение компьютера к домену домен domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-138">It uses the **Credential** parameter to specify a user account that has permission to join the computer to the Domain02 domain.</span></span>

### <span data-ttu-id="6aa72-139">Пример 8. Добавление компьютеров, перечисленных в файле, в новый домен</span><span class="sxs-lookup"><span data-stu-id="6aa72-139">Example 8: Add computers listed in a file to a new domain</span></span>

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

<span data-ttu-id="6aa72-140">Эта команда добавляет компьютеры, перечисленные в файле Servers.txt, в домен Domain02.</span><span class="sxs-lookup"><span data-stu-id="6aa72-140">This command adds the computers that are listed in the Servers.txt file to the Domain02 domain.</span></span> <span data-ttu-id="6aa72-141">Она использует параметр **Options** для указания параметра **Win9xUpgrade**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-141">It uses the **Options** parameter to specify the **Win9xUpgrade** option.</span></span> <span data-ttu-id="6aa72-142">Параметр **Restart** перезапускает все добавленные компьютеры после выполнения операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="6aa72-142">The **Restart** parameter restarts all of the newly added computers after the join operation completes.</span></span>

### <span data-ttu-id="6aa72-143">Пример 9. Добавление компьютера в домен с использованием стандартных учетных данных компьютера</span><span class="sxs-lookup"><span data-stu-id="6aa72-143">Example 9: Add a computer to a domain using predefined computer credentials</span></span>

<span data-ttu-id="6aa72-144">Эта первая команда должна запускаться администратором с компьютера, который уже присоединен к домену `Domain03` .</span><span class="sxs-lookup"><span data-stu-id="6aa72-144">This first command should be run by an administrator from a computer that is already joined to domain `Domain03`:</span></span>

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

<span data-ttu-id="6aa72-145">Это сочетание команд создает новую учетную запись компьютера с предопределенным именем и временным паролем присоединения в домене, используя существующий компьютер, присоединенный к домену.</span><span class="sxs-lookup"><span data-stu-id="6aa72-145">This combination of commands creates a new computer account with a predefined name and temporary join password in a domain using an existing domain-joined computer.</span></span> <span data-ttu-id="6aa72-146">Затем по отдельности компьютер с предопределенным именем присоединяется к домену, используя только имя компьютера и временный пароль присоединение.</span><span class="sxs-lookup"><span data-stu-id="6aa72-146">Then separately, a computer with the predefined name joins the domain using only the computer name and the temporary join password.</span></span>
<span data-ttu-id="6aa72-147">Предопределенный пароль используется только для поддержки операции JOIN и заменяется как часть обычных процедур учетной записи компьютера после того, как компьютер завершает соединение.</span><span class="sxs-lookup"><span data-stu-id="6aa72-147">The predefined password is only used to support the join operation and is replaced as part of normal computer account procedures after the computer completes the join.</span></span>

## <span data-ttu-id="6aa72-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6aa72-148">PARAMETERS</span></span>

### <span data-ttu-id="6aa72-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6aa72-149">-ComputerName</span></span>

<span data-ttu-id="6aa72-150">Указывает компьютеры для добавления в домен или рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="6aa72-150">Specifies the computers to add to a domain or workgroup.</span></span>
<span data-ttu-id="6aa72-151">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6aa72-151">The default is the local computer.</span></span>

<span data-ttu-id="6aa72-152">Введите имя NetBIOS, IP-адрес или полное доменное имя каждого удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6aa72-152">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of each of the remote computers.</span></span> <span data-ttu-id="6aa72-153">Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или localhost.</span><span class="sxs-lookup"><span data-stu-id="6aa72-153">To specify the local computer, type the computer name, a dot (`.`), or "localhost".</span></span>

<span data-ttu-id="6aa72-154">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6aa72-154">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="6aa72-155">Параметр **ComputerName** можно использовать, `Add-Computer` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="6aa72-155">You can use the **ComputerName** parameter of `Add-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="6aa72-156">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-156">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="6aa72-157">-Credential</span></span>

<span data-ttu-id="6aa72-158">Указывает учетную запись пользователя, имеющую разрешение на присоединение компьютеров к новому домену.</span><span class="sxs-lookup"><span data-stu-id="6aa72-158">Specifies a user account that has permission to join the computers to a new domain.</span></span>
<span data-ttu-id="6aa72-159">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6aa72-159">The default is the current user.</span></span>

<span data-ttu-id="6aa72-160">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="6aa72-160">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="6aa72-161">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="6aa72-161">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="6aa72-162">Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютера из текущего домена, используйте параметр **UnjoinDomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-162">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span> <span data-ttu-id="6aa72-163">Чтобы указать учетную запись, имеющую разрешение на подключение к удаленному компьютеру, используйте параметр **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-163">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-164">-DomainName</span><span class="sxs-lookup"><span data-stu-id="6aa72-164">-DomainName</span></span>

<span data-ttu-id="6aa72-165">Указывает домен, в который добавляются компьютеры.</span><span class="sxs-lookup"><span data-stu-id="6aa72-165">Specifies the domain to which the computers are added.</span></span> <span data-ttu-id="6aa72-166">Этот параметр является обязательным при добавлении компьютеров в домен.</span><span class="sxs-lookup"><span data-stu-id="6aa72-166">This parameter is required when adding the computers to a domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-167">-Force</span><span class="sxs-lookup"><span data-stu-id="6aa72-167">-Force</span></span>

<span data-ttu-id="6aa72-168">Отключает запрос подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="6aa72-168">Suppresses the user confirmation prompt.</span></span> <span data-ttu-id="6aa72-169">Без этого параметра `Add-Computer` требует подтверждения добавления каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="6aa72-169">Without this parameter, `Add-Computer` requires you to confirm the addition of each computer.</span></span>

<span data-ttu-id="6aa72-170">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-170">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="6aa72-171">-Локалкредентиал</span><span class="sxs-lookup"><span data-stu-id="6aa72-171">-LocalCredential</span></span>

<span data-ttu-id="6aa72-172">Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютерам, указанным в параметре **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-172">Specifies a user account that has permission to connect to the computers that are specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="6aa72-173">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6aa72-173">The default is the current user.</span></span>

<span data-ttu-id="6aa72-174">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="6aa72-174">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="6aa72-175">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="6aa72-175">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="6aa72-176">Чтобы указать учетную запись пользователя, имеющую разрешение на добавление компьютеров в новый домен, используйте параметр **Credential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-176">To specify a user account that has permission to add the computers to a new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="6aa72-177">Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущего домена, используйте параметр **UnjoinDomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-177">To specify a user account that has permission to remove the computers from their current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="6aa72-178">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-179">-NewName</span><span class="sxs-lookup"><span data-stu-id="6aa72-179">-NewName</span></span>

<span data-ttu-id="6aa72-180">Указывает новое имя для компьютера в новом домене.</span><span class="sxs-lookup"><span data-stu-id="6aa72-180">Specifies a new name for the computer in the new domain.</span></span> <span data-ttu-id="6aa72-181">Этот параметр допустим только при добавлении или перемещении одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6aa72-181">This parameter is valid only when one computer is being added or moved.</span></span>

<span data-ttu-id="6aa72-182">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-182">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-183">-Параметры</span><span class="sxs-lookup"><span data-stu-id="6aa72-183">-Options</span></span>

<span data-ttu-id="6aa72-184">Указывает дополнительные параметры для операции присоединение к **Add-Computer** .</span><span class="sxs-lookup"><span data-stu-id="6aa72-184">Specifies advanced options for the **Add-Computer** join operation.</span></span> <span data-ttu-id="6aa72-185">Введите одно или несколько значений в строку с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="6aa72-185">Enter one or more values in a comma-separated string.</span></span>

<span data-ttu-id="6aa72-186">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6aa72-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6aa72-187">**Аккаунткреате** : создает учетную запись домена.</span><span class="sxs-lookup"><span data-stu-id="6aa72-187">**AccountCreate** : Creates a domain account.</span></span> <span data-ttu-id="6aa72-188">Командлет **Add-Computer** автоматически создает учетную запись домена при добавлении компьютера в домен.</span><span class="sxs-lookup"><span data-stu-id="6aa72-188">The **Add-Computer** cmdlet automatically creates a domain account when it adds a computer to a domain.</span></span> <span data-ttu-id="6aa72-189">Этот параметр включен для полноты.</span><span class="sxs-lookup"><span data-stu-id="6aa72-189">This option is included for completeness.</span></span>

- <span data-ttu-id="6aa72-190">**Win9XUpgrade** : указывает, что операция JOIN является частью обновления операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="6aa72-190">**Win9XUpgrade** : Indicates that the join operation is part of a Windows operating system upgrade.</span></span>

- <span data-ttu-id="6aa72-191">**Унсекуреджоин** : Выполняет небезопасное соединение.</span><span class="sxs-lookup"><span data-stu-id="6aa72-191">**UnsecuredJoin** : Performs an unsecured join.</span></span> <span data-ttu-id="6aa72-192">Чтобы запросить небезопасное соединение, используйте параметр *незащищенный* или этот параметр.</span><span class="sxs-lookup"><span data-stu-id="6aa72-192">To request an unsecured join, use the *Unsecure* parameter or this option.</span></span> <span data-ttu-id="6aa72-193">Если вы хотите передать пароль компьютера, этот параметр следует использовать в сочетании с `PasswordPass` параметром.</span><span class="sxs-lookup"><span data-stu-id="6aa72-193">If you want to pass a machine password, then you must use this option in combination with `PasswordPass` option.</span></span>

- <span data-ttu-id="6aa72-194">**Пассвордпасс** : задает для пароля компьютера значение параметра *Credential* (домаинкредентиал) после выполнения небезопасного объединения.</span><span class="sxs-lookup"><span data-stu-id="6aa72-194">**PasswordPass** : Sets the machine password to the value of the *Credential* (DomainCredential) parameter after performing an unsecured join.</span></span> <span data-ttu-id="6aa72-195">Этот параметр также указывает, что значение параметра *Credential* (DomainCredential) является паролем компьютера, а не пользователя.</span><span class="sxs-lookup"><span data-stu-id="6aa72-195">This option also indicates that the value of the *Credential* (DomainCredential) parameter is a machine password, not a user password.</span></span> <span data-ttu-id="6aa72-196">Этот параметр допустим только в том случае, если `UnsecuredJoin` указан параметр.</span><span class="sxs-lookup"><span data-stu-id="6aa72-196">This option is valid only when the `UnsecuredJoin` option is specified.</span></span> <span data-ttu-id="6aa72-197">При использовании этого параметра учетные данные, предоставленные для `-Credential` параметра, *должны* иметь значение NULL username.</span><span class="sxs-lookup"><span data-stu-id="6aa72-197">When using this option, the credential provided to the `-Credential` parameter *must* have a null username.</span></span>

- <span data-ttu-id="6aa72-198">**Жоинвисневнаме** : переименовывает имя компьютера в новом домене на имя, заданное параметром *newname* .</span><span class="sxs-lookup"><span data-stu-id="6aa72-198">**JoinWithNewName** : Renames the computer name in the new domain to the name specified by the *NewName* parameter.</span></span> <span data-ttu-id="6aa72-199">При использовании параметра *NewName* этот параметр задается автоматически.</span><span class="sxs-lookup"><span data-stu-id="6aa72-199">When you use the *NewName* parameter, this option is set automatically.</span></span> <span data-ttu-id="6aa72-200">Этот параметр предназначен для использования с командлетом Rename-Computer.</span><span class="sxs-lookup"><span data-stu-id="6aa72-200">This option is designed to be used with the Rename-Computer cmdlet.</span></span> <span data-ttu-id="6aa72-201">Если вы используете командлет **Rename-Computer** для переименования компьютера, но не перезапускайте компьютер для внесения изменений, можно использовать этот параметр, чтобы присоединить компьютер к домену с новым именем.</span><span class="sxs-lookup"><span data-stu-id="6aa72-201">If you use the **Rename-Computer** cmdlet to rename the computer, but do not restart the computer to make the change effective, you can use this parameter to join the computer to a domain with its new name.</span></span>

- <span data-ttu-id="6aa72-202">**Жоинреадонли** : использует существующую учетную запись компьютера для приподключения компьютера к контроллеру домена только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6aa72-202">**JoinReadOnly** : Uses an existing machine account to join the computer to a read-only domain controller.</span></span> <span data-ttu-id="6aa72-203">Учетная запись компьютера должна быть добавлена в список разрешенных для политики репликации паролей, а пароль учетной записи должен быть реплицирован на контроллер домена только для чтения до выполнения операции JOIN.</span><span class="sxs-lookup"><span data-stu-id="6aa72-203">The machine account must be added to the allowed list for password replication policy and the account password must be replicated to the read-only domain controller prior to the join operation.</span></span>

- <span data-ttu-id="6aa72-204">**Инсталлинвоке** : задает флаги Create (0x2) и Delete (0x4) параметра **фжоиноптионс** метода **жоиндомаинорворкграуп** .</span><span class="sxs-lookup"><span data-stu-id="6aa72-204">**InstallInvoke** : Sets the create (0x2) and delete (0x4) flags of the **FJoinOptions** parameter of the **JoinDomainOrWorkgroup** method.</span></span> <span data-ttu-id="6aa72-205">Дополнительные сведения о методе **жоиндомаинорворкграуп** см. в разделе [метод жоиндомаинорворкграуп класса Win32_ComputerSystem](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span><span class="sxs-lookup"><span data-stu-id="6aa72-205">For more information about the **JoinDomainOrWorkgroup** method, see [JoinDomainOrWorkgroup method of the Win32_ComputerSystem class](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span></span>
  <span data-ttu-id="6aa72-206">Дополнительные сведения об этих параметрах см. в разделе [функция нетжоиндомаин](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span><span class="sxs-lookup"><span data-stu-id="6aa72-206">For more information about these options, see [NetJoinDomain function](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span></span>

<span data-ttu-id="6aa72-207">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-208">-Аупас</span><span class="sxs-lookup"><span data-stu-id="6aa72-208">-OUPath</span></span>

<span data-ttu-id="6aa72-209">Указывает подразделение для учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="6aa72-209">Specifies an organizational unit (OU) for the domain account.</span></span> <span data-ttu-id="6aa72-210">Введите полное различающееся имя подразделения в кавычках.</span><span class="sxs-lookup"><span data-stu-id="6aa72-210">Enter the full distinguished name of the OU in quotation marks.</span></span> <span data-ttu-id="6aa72-211">Значение по умолчанию — подразделение по умолчанию для объектов компьютеров в домене.</span><span class="sxs-lookup"><span data-stu-id="6aa72-211">The default value is the default OU for machine objects in the domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-212">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6aa72-212">-PassThru</span></span>

<span data-ttu-id="6aa72-213">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="6aa72-213">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="6aa72-214">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="6aa72-214">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="6aa72-215">-Restart</span><span class="sxs-lookup"><span data-stu-id="6aa72-215">-Restart</span></span>

<span data-ttu-id="6aa72-216">Перезапускает компьютеры, которые были добавлены в домен или рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="6aa72-216">Restarts the computers that were added to the domain or workgroup.</span></span> <span data-ttu-id="6aa72-217">Чтобы изменения вступили в силу, часто требуется перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="6aa72-217">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="6aa72-218">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-218">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="6aa72-219">-Server</span><span class="sxs-lookup"><span data-stu-id="6aa72-219">-Server</span></span>

<span data-ttu-id="6aa72-220">Задает имя контроллера домена, который добавляет компьютер в домен.</span><span class="sxs-lookup"><span data-stu-id="6aa72-220">Specifies the name of a domain controller that adds the computer to the domain.</span></span> <span data-ttu-id="6aa72-221">Введите имя в формате "ИмяДомена\ИмяКомпьютера".</span><span class="sxs-lookup"><span data-stu-id="6aa72-221">Enter the name in DomainName\ComputerName format.</span></span> <span data-ttu-id="6aa72-222">По умолчанию контроллер домена не указан.</span><span class="sxs-lookup"><span data-stu-id="6aa72-222">By default, no domain controller is specified.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-223">-Унжоиндомаинкредентиал</span><span class="sxs-lookup"><span data-stu-id="6aa72-223">-UnjoinDomainCredential</span></span>

<span data-ttu-id="6aa72-224">Указывает учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущих доменов.</span><span class="sxs-lookup"><span data-stu-id="6aa72-224">Specifies a user account that has permission to remove the computers from their current domains.</span></span> <span data-ttu-id="6aa72-225">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6aa72-225">The default is the current user.</span></span>

<span data-ttu-id="6aa72-226">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="6aa72-226">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="6aa72-227">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="6aa72-227">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="6aa72-228">Используйте этот параметр при перемещении компьютеров в другой домен.</span><span class="sxs-lookup"><span data-stu-id="6aa72-228">Use this parameter when you are moving computers to a different domain.</span></span> <span data-ttu-id="6aa72-229">Чтобы указать учетную запись, имеющую разрешение на присоединение к новому домену, используйте параметр **Credential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-229">To specify a user account that has permission to join the new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="6aa72-230">Чтобы указать учетную запись, имеющую разрешение на подключение к удаленному компьютеру, используйте параметр **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="6aa72-230">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="6aa72-231">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aa72-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-232">— Небезопасный</span><span class="sxs-lookup"><span data-stu-id="6aa72-232">-Unsecure</span></span>

<span data-ttu-id="6aa72-233">Выполняет незащищенное присоединение к указанному домену.</span><span class="sxs-lookup"><span data-stu-id="6aa72-233">Performs an unsecure join to the specified domain.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-234">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="6aa72-234">-WorkgroupName</span></span>

<span data-ttu-id="6aa72-235">Указывает имя рабочей группы, в которую добавляются компьютеры.</span><span class="sxs-lookup"><span data-stu-id="6aa72-235">Specifies the name of a workgroup to which the computers are added.</span></span> <span data-ttu-id="6aa72-236">Значение по умолчанию — WORKGROUP.</span><span class="sxs-lookup"><span data-stu-id="6aa72-236">The default value is "WORKGROUP".</span></span>

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aa72-237">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6aa72-237">-Confirm</span></span>

<span data-ttu-id="6aa72-238">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6aa72-238">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6aa72-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6aa72-239">-WhatIf</span></span>

<span data-ttu-id="6aa72-240">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6aa72-240">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6aa72-241">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6aa72-241">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6aa72-242">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6aa72-242">CommonParameters</span></span>

<span data-ttu-id="6aa72-243">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6aa72-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6aa72-244">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6aa72-244">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6aa72-245">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6aa72-245">INPUTS</span></span>

### <span data-ttu-id="6aa72-246">System.String</span><span class="sxs-lookup"><span data-stu-id="6aa72-246">System.String</span></span>

<span data-ttu-id="6aa72-247">В командлет можно передать имена компьютеров и новые имена `Add-Computer` .</span><span class="sxs-lookup"><span data-stu-id="6aa72-247">You can pipe computer names and new names to the `Add-Computer` Cmdlet.</span></span>

## <span data-ttu-id="6aa72-248">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6aa72-248">OUTPUTS</span></span>

### <span data-ttu-id="6aa72-249">Microsoft. PowerShell. Commands. Компутерчанжеинфо</span><span class="sxs-lookup"><span data-stu-id="6aa72-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="6aa72-250">При использовании параметра **PassThru** `Add-Computer` возвращает объект **компутерчанжеинфо** .</span><span class="sxs-lookup"><span data-stu-id="6aa72-250">When you use the **PassThru** parameter, `Add-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="6aa72-251">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6aa72-251">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6aa72-252">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6aa72-252">NOTES</span></span>

- <span data-ttu-id="6aa72-253">В Windows PowerShell 2,0 параметр **сервера** `Add-Computer` завершается ошибкой даже при наличии сервера.</span><span class="sxs-lookup"><span data-stu-id="6aa72-253">In Windows PowerShell 2.0, the **Server** parameter of `Add-Computer` fails even when the server is present.</span></span> <span data-ttu-id="6aa72-254">В Windows PowerShell 3.0 реализация параметра **Server** изменилась. Теперь он работает надежно.</span><span class="sxs-lookup"><span data-stu-id="6aa72-254">In Windows PowerShell 3.0, the implementation of the **Server** parameter is changed so that it works reliably.</span></span>

## <span data-ttu-id="6aa72-255">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6aa72-255">RELATED LINKS</span></span>

[<span data-ttu-id="6aa72-256">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-256">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="6aa72-257">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-257">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="6aa72-258">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-258">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="6aa72-259">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-259">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="6aa72-260">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-260">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="6aa72-261">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="6aa72-261">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="6aa72-262">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="6aa72-262">Test-Connection</span></span>](Test-Connection.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: ce9e19140cb0bb8fd9172fa7ca7929fb696f9c65
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229881"
---
# <span data-ttu-id="0bcd0-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="0bcd0-103">Restart-Computer</span></span>

## <span data-ttu-id="0bcd0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0bcd0-104">SYNOPSIS</span></span>
<span data-ttu-id="0bcd0-105">Перезапускает операционную систему на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="0bcd0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bcd0-106">SYNTAX</span></span>

### <span data-ttu-id="0bcd0-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0bcd0-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0bcd0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bcd0-108">DESCRIPTION</span></span>

<span data-ttu-id="0bcd0-109">`Restart-Computer`Командлет перезапускает операционную систему на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-109">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="0bcd0-110">Параметры можно использовать `Restart-Computer` для запуска операций перезапуска, для указания уровней проверки подлинности и альтернативных учетных данных, для ограничения операций, выполняемых одновременно, и для принудительной перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-110">You can use the parameters of `Restart-Computer` to run the restart operations, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="0bcd0-111">Начиная с Windows PowerShell 3,0, перед выполнением следующей команды можно дождаться завершения перезапуска.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-111">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="0bcd0-112">Укажите время ожидания и интервал запроса, а также дождитесь доступности определенных служб на перезагруженном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-112">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="0bcd0-113">Эта функция делает ее практичной для использования `Restart-Computer` в скриптах и функциях.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-113">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

## <span data-ttu-id="0bcd0-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="0bcd0-114">EXAMPLES</span></span>

### <span data-ttu-id="0bcd0-115">Пример 1. перезапуск локального компьютера</span><span class="sxs-lookup"><span data-stu-id="0bcd0-115">Example 1: Restart the local computer</span></span>

<span data-ttu-id="0bcd0-116">`Restart-Computer` перезапускает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-116">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="0bcd0-117">Пример 2. перезапуск нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="0bcd0-117">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="0bcd0-118">`Restart-Computer` может перезапустить удаленный и локальный компьютеры.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-118">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="0bcd0-119">Параметр **ComputerName** принимает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-119">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="0bcd0-120">Пример 3. Получение имен компьютеров из текстового файла</span><span class="sxs-lookup"><span data-stu-id="0bcd0-120">Example 3: Get computer names from a text file</span></span>

<span data-ttu-id="0bcd0-121">`Restart-Computer` Возвращает список имен компьютеров из текстового файла и перезапускает компьютеры.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-121">`Restart-Computer` gets a list of computer names from a text file and restarts the computers.</span></span> <span data-ttu-id="0bcd0-122">Параметр **ComputerName** не указан.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-122">The **ComputerName** parameter isn't specified.</span></span> <span data-ttu-id="0bcd0-123">Но поскольку это первый параметр размещения, он принимает имена компьютеров из текстового файла, которые отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-123">But because it's the first position parameter, it accepts the computer names from the text file that are sent down the pipeline.</span></span>

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

<span data-ttu-id="0bcd0-124">`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-124">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="0bcd0-125">Имена компьютеров отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-125">The computer names are sent down the pipeline.</span></span> <span data-ttu-id="0bcd0-126">`Restart-Computer` перезапускает каждый компьютер.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-126">`Restart-Computer` restarts each computer.</span></span>

### <span data-ttu-id="0bcd0-127">Пример 4. принудительный перезапуск компьютеров, перечисленных в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="0bcd0-127">Example 4: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="0bcd0-128">В этом примере выполняется принудительная перезагрузка компьютеров, перечисленных в `Domain01.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-128">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="0bcd0-129">Имена компьютеров из текстового файла хранятся в переменной.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-129">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="0bcd0-130">Параметр **Force** принудительно вызывает немедленную перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-130">The **Force** parameter forces an immediate restart.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

<span data-ttu-id="0bcd0-131">`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-131">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="0bcd0-132">Имена компьютеров хранятся в переменной `$Names` .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-132">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="0bcd0-133">`Get-Credential` запрашивает имя пользователя и пароль и сохраняет значения в переменной `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-133">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="0bcd0-134">`Restart-Computer` использует параметры **ComputerName** и **Credential** с их переменными.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-134">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="0bcd0-135">Параметр **Force** приводит к немедленному перезапуску каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-135">The **Force** parameter causes an immediate restart of each computer.</span></span>

### <span data-ttu-id="0bcd0-136">Пример 6. перезапуск удаленного компьютера и ожидание PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bcd0-136">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="0bcd0-137">`Restart-Computer` перезапускает удаленный компьютер, после чего ждет до 5 минут (300 секунд), чтобы PowerShell был доступен на перезагруженном компьютере, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-137">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="0bcd0-138">`Restart-Computer` использует параметр **ComputerName** для указания **Server01**.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-138">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="0bcd0-139">Параметр **Wait** ожидает завершения перезапуска.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-139">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="0bcd0-140">**Для** указывает, что PowerShell может выполнять команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-140">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="0bcd0-141">Параметр **timeout** задает время ожидания в пять минут.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-141">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="0bcd0-142">Параметр **delay** запрашивает удаленный компьютер каждые две секунды, чтобы определить, перезапущен ли он.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-142">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="0bcd0-143">Пример 7. перезагрузка компьютера с помощью Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="0bcd0-143">Example 7: Restart a computer by using WsmanAuthentication</span></span>

<span data-ttu-id="0bcd0-144">`Restart-Computer` перезапускает удаленный компьютер с помощью механизма **всманаусентикатион** .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-144">`Restart-Computer` restarts the remote computer using the **WsmanAuthentication** mechanism.</span></span>
<span data-ttu-id="0bcd0-145">Проверка подлинности Kerberos определяет, имеет ли текущий пользователь разрешение на перезапуск удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-145">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span> <span data-ttu-id="0bcd0-146">Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-146">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

<span data-ttu-id="0bcd0-147">`Restart-Computer` использует параметр **ComputerName** для указания удаленного компьютера **Server01**.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-147">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="0bcd0-148">Параметр **всманаусентикатион** указывает метод проверки подлинности **Kerberos**.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-148">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="0bcd0-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bcd0-149">PARAMETERS</span></span>

### <span data-ttu-id="0bcd0-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0bcd0-150">-ComputerName</span></span>

<span data-ttu-id="0bcd0-151">Указывает одно имя компьютера или разделенный запятыми массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-151">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="0bcd0-152">`Restart-Computer` принимает объекты **ComputerName** из конвейера или переменных.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-152">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="0bcd0-153">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="0bcd0-154">Чтобы указать локальный компьютер, введите имя компьютера, точку `.` или localhost.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-154">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="0bcd0-155">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-155">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="0bcd0-156">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-156">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="0bcd0-157">Если параметр **ComputerName** не указан, `Restart-Computer` перезапускает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-157">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="0bcd0-158">-Credential</span></span>

<span data-ttu-id="0bcd0-159">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-159">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="0bcd0-160">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-160">The default is the current user.</span></span>

<span data-ttu-id="0bcd0-161">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-161">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0bcd0-162">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-162">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0bcd0-163">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0bcd0-164">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-165">-Delay</span><span class="sxs-lookup"><span data-stu-id="0bcd0-165">-Delay</span></span>

<span data-ttu-id="0bcd0-166">Указывает частоту запросов в секундах.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-166">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="0bcd0-167">PowerShell запрашивает службу, указанную **параметром, чтобы** определить, доступна ли служба после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-167">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="0bcd0-168">Этот параметр допустим только вместе с параметрами **ожидания** и **для** параметров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-168">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="0bcd0-169">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-169">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="0bcd0-170">Если параметр **delay** не указан, `Restart-Computer` использует 5-секундную задержку.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-170">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-171">— Для</span><span class="sxs-lookup"><span data-stu-id="0bcd0-171">-For</span></span>

<span data-ttu-id="0bcd0-172">Задает поведение PowerShell при ожидании доступности указанной службы или компонента после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-172">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="0bcd0-173">Этот параметр допустим только с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-173">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="0bcd0-174">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0bcd0-174">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0bcd0-175">**По умолчанию** : ожидает перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-175">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="0bcd0-176">**PowerShell** : может выполнять команды в удаленном сеансе PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-176">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="0bcd0-177">**WMI** : получает ответ на запрос Win32_ComputerSystem компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-177">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="0bcd0-178">**WinRM** : может установить удаленный сеанс для компьютера с помощью WS-Management.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-178">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="0bcd0-179">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-180">-Force</span><span class="sxs-lookup"><span data-stu-id="0bcd0-180">-Force</span></span>

<span data-ttu-id="0bcd0-181">Вызывает немедленную перезагрузку компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-181">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-182">-Timeout</span><span class="sxs-lookup"><span data-stu-id="0bcd0-182">-Timeout</span></span>

<span data-ttu-id="0bcd0-183">Указывает время ожидания в секундах.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-183">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="0bcd0-184">По истечении времени ожидания `Restart-Computer` возвращает в командную строку, даже если компьютеры не перезапускаются.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-184">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="0bcd0-185">Параметр **timeout** допустим только с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-185">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="0bcd0-186">**Время ожидания** переопределяет неопределенный период ожидания в параметре **ожидания** .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-186">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="0bcd0-187">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-187">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-188">-Wait</span><span class="sxs-lookup"><span data-stu-id="0bcd0-188">-Wait</span></span>

<span data-ttu-id="0bcd0-189">`Restart-Computer` подавляет командную строку PowerShell и блокирует конвейер до перезапуска компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-189">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="0bcd0-190">Этот параметр можно использовать в скрипте для перезагрузки компьютеров и продолжения обработки после завершения перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-190">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="0bcd0-191">Параметр **Wait** ожидает неограниченное время ожидания перезапуска компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-191">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="0bcd0-192">Можно использовать **время ожидания** для настройки времени, а параметры **для** и **задержки** ожидают, когда определенные службы станут доступны на перезагруженных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-192">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="0bcd0-193">Параметр **Wait** недопустим при перезапуске локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-193">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="0bcd0-194">Если значение параметра **ComputerName** содержит имена удаленных компьютеров и локального компьютера, `Restart-Computer` создает неустранимую ошибку для **ожидания** на локальном компьютере, но ожидает перезапуска удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-194">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="0bcd0-195">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-195">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0bcd0-196">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="0bcd0-196">-WsmanAuthentication</span></span>

<span data-ttu-id="0bcd0-197">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-197">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="0bcd0-198">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-198">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="0bcd0-199">Допустимые значения для этого параметра: " **базовый** ", " **CredSSP** ", " **по умолчанию** ", " **дайджест** ", **Kerberos** и " **согласование** ".</span><span class="sxs-lookup"><span data-stu-id="0bcd0-199">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="0bcd0-200">Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-200">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="0bcd0-201">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-201">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0bcd0-202">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0bcd0-203">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bcd0-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0bcd0-204">-Confirm</span></span>

<span data-ttu-id="0bcd0-205">Запрашивает подтверждение перед запуском `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-205">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="0bcd0-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0bcd0-206">-WhatIf</span></span>

<span data-ttu-id="0bcd0-207">Показывает, что произойдет при `Restart-Computer` выполнении.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-207">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="0bcd0-208">`Restart-Computer`Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-208">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0bcd0-209">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0bcd0-209">CommonParameters</span></span>

<span data-ttu-id="0bcd0-210">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bcd0-211">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bcd0-212">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0bcd0-212">INPUTS</span></span>

### <span data-ttu-id="0bcd0-213">System.String</span><span class="sxs-lookup"><span data-stu-id="0bcd0-213">System.String</span></span>

<span data-ttu-id="0bcd0-214">`Restart-Computer` принимает имена компьютеров из конвейера или переменных.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-214">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

## <span data-ttu-id="0bcd0-215">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0bcd0-215">OUTPUTS</span></span>

### <span data-ttu-id="0bcd0-216">Нет</span><span class="sxs-lookup"><span data-stu-id="0bcd0-216">None</span></span>

<span data-ttu-id="0bcd0-217">`Restart-Computer` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-217">`Restart-Computer` doesn't generate any output.</span></span>

## <span data-ttu-id="0bcd0-218">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0bcd0-218">NOTES</span></span>

- <span data-ttu-id="0bcd0-219">`Restart-Computer` работает только на компьютерах под управлением Windows и требует от WinRM и инструментария WMI для завершения работы системы, включая локальную систему.</span><span class="sxs-lookup"><span data-stu-id="0bcd0-219">`Restart-Computer` only works on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="0bcd0-220">`Restart-Computer` использует [метод Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) класса [WIN32_OPERATINGSYSTEM](/windows/desktop/CIMWin32Prov/win32-operatingsystem) инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="0bcd0-220">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span> <span data-ttu-id="0bcd0-221">Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .</span><span class="sxs-lookup"><span data-stu-id="0bcd0-221">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="0bcd0-222">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0bcd0-222">RELATED LINKS</span></span>

[<span data-ttu-id="0bcd0-223">О служба удаленного управления Windows</span><span class="sxs-lookup"><span data-stu-id="0bcd0-223">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="0bcd0-224">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="0bcd0-224">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="0bcd0-225">Протокол WS-Management</span><span class="sxs-lookup"><span data-stu-id="0bcd0-225">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)

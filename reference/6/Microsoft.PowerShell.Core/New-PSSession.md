---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 90bd1d539bb6bc071df6bfcf326adc57e24fff8f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229882"
---
# <span data-ttu-id="3425d-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-103">New-PSSession</span></span>

## <span data-ttu-id="3425d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3425d-104">SYNOPSIS</span></span>
<span data-ttu-id="3425d-105">Создает постоянное подключение к локальному или удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="3425d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3425d-106">SYNTAX</span></span>

### <span data-ttu-id="3425d-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3425d-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-108">VMId</span><span class="sxs-lookup"><span data-stu-id="3425d-108">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-109">URI</span><span class="sxs-lookup"><span data-stu-id="3425d-109">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-110">VMName</span><span class="sxs-lookup"><span data-stu-id="3425d-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-111">Сеанс</span><span class="sxs-lookup"><span data-stu-id="3425d-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="3425d-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-113">сшхост</span><span class="sxs-lookup"><span data-stu-id="3425d-113">SSHHost</span></span>

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="3425d-114">сшхоссашпарам</span><span class="sxs-lookup"><span data-stu-id="3425d-114">SSHHostHashParam</span></span>

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## <span data-ttu-id="3425d-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3425d-115">DESCRIPTION</span></span>

<span data-ttu-id="3425d-116">`New-PSSession`Командлет создает сеанс PowerShell ( **PSSession** ) на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-116">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="3425d-117">При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-117">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="3425d-118">Используйте **PSSession** для выполнения нескольких команд, совместно использующих данные, таких как функция или значение переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-118">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="3425d-119">Для выполнения команд в **PSSession** используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="3425d-119">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="3425d-120">Чтобы использовать **PSSession** для взаимодействия непосредственно с удаленным компьютером, используйте `Enter-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="3425d-120">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="3425d-121">Дополнительные сведения см. в разделе [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-121">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="3425d-122">Команды можно выполнять на удаленном компьютере без создания **сеанса PSSession** с помощью параметров **ComputerName** параметра `Enter-PSSession` или `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="3425d-122">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="3425d-123">При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется для команды и затем закрывается.</span><span class="sxs-lookup"><span data-stu-id="3425d-123">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

<span data-ttu-id="3425d-124">Начиная с PowerShell 6,0 можно использовать Secure Shell (SSH) для установления подключения к и создания сеанса на удаленном компьютере, если SSH доступен на локальном компьютере, а удаленный компьютер настроен с помощью конечной точки SSH PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3425d-124">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and create a session on a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="3425d-125">Преимуществом удаленного сеанса PowerShell на основе SSH является то, что он может работать на нескольких платформах (Windows, Linux, macOS).</span><span class="sxs-lookup"><span data-stu-id="3425d-125">The benefit of an SSH based PowerShell remote session is that it can work across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="3425d-126">Для сеансов на основе SSH используется параметр **HostName** или **сшконнектион** , заданный для указания удаленного компьютера и соответствующих сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="3425d-126">For SSH based sessions you use the **HostName** or **SSHConnection** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="3425d-127">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="3425d-127">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="3425d-128">При использовании удаленного взаимодействия WSMan из клиента Linux или macOS с конечной точкой HTTPS, в которой сертификат сервера не является доверенным (например, самозаверяющий сертификат).</span><span class="sxs-lookup"><span data-stu-id="3425d-128">When using WSMan remoting from a Linux or macOS client with a HTTPS endpoint where the server certificate is not trusted (e.g., a self-signed certificate).</span></span> <span data-ttu-id="3425d-129">`PSSessionOption` `-SkipCACheck` Для успешного установления соединения необходимо указать, который включает и `-SkipCNCheck` .</span><span class="sxs-lookup"><span data-stu-id="3425d-129">You must provide a `PSSessionOption` that includes `-SkipCACheck` and `-SkipCNCheck` to successfully establish the connection.</span></span> <span data-ttu-id="3425d-130">Сделайте это, только если вы в среде, где можно указать сертификат сервера и сетевое подключение к целевой системе.</span><span class="sxs-lookup"><span data-stu-id="3425d-130">Only do this if you are in an environment where you can be certain of the server certificate and the network connection to the target system.</span></span>

## <span data-ttu-id="3425d-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="3425d-131">EXAMPLES</span></span>

### <span data-ttu-id="3425d-132">Пример 1. Создание сеанса на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="3425d-132">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="3425d-133">Эта команда создает новый **сеанс PSSession** на локальном компьютере и сохраняет **сеанс PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-133">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="3425d-134">Теперь этот **сеанс PSSession** можно использовать для выполнения команд на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-134">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="3425d-135">Пример 2. Создание сеанса на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="3425d-135">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="3425d-136">Эта команда создает новый **сеанс PSSession** на компьютере Server01 и сохраняет его в `$Server01` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-136">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="3425d-137">При создании нескольких объектов **PSSession** назначьте их переменным с полезными именами.</span><span class="sxs-lookup"><span data-stu-id="3425d-137">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="3425d-138">Это позволит управлять объектами **PSSession** в последующих командах.</span><span class="sxs-lookup"><span data-stu-id="3425d-138">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="3425d-139">Пример 3. Создание сеансов на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="3425d-139">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="3425d-140">Эта команда создает три объекта **PSSession** — по одному на каждом из компьютеров, указанных параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="3425d-140">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="3425d-141">Команда использует оператор присваивания (=) для назначения новых объектов **PSSession** переменным: `$s1` , `$s2` , `$s3` .</span><span class="sxs-lookup"><span data-stu-id="3425d-141">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="3425d-142">Он назначает Server01 **PSSession** `$s1` , Server02 **PSSession** `$s2` —, а Server03 **PSSession** — `$s3` .</span><span class="sxs-lookup"><span data-stu-id="3425d-142">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="3425d-143">При назначении нескольких объектов ряду переменных PowerShell каждый объект назначается переменной в ряде, соответственно.</span><span class="sxs-lookup"><span data-stu-id="3425d-143">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="3425d-144">Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-144">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="3425d-145">Если переменных больше, чем объектов, оставшиеся переменные остаются пустыми (null).</span><span class="sxs-lookup"><span data-stu-id="3425d-145">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="3425d-146">Пример 4. Создание сеанса с указанным портом</span><span class="sxs-lookup"><span data-stu-id="3425d-146">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="3425d-147">Эта команда создает новый **сеанс PSSession** на компьютере Server01, который подключается к порту сервера 8081 и использует протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="3425d-147">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="3425d-148">Новый сеанс **PSSession** использует альтернативную конфигурацию сеанса с именем E12.</span><span class="sxs-lookup"><span data-stu-id="3425d-148">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="3425d-149">Прежде чем задать порт, необходимо настроить прослушиватель службы удаленного управления Windows для прослушивания порта 8081 на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-149">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="3425d-150">Дополнительные сведения см. в описании параметра **Port**.</span><span class="sxs-lookup"><span data-stu-id="3425d-150">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="3425d-151">Пример 5. Создание сеанса на основе существующего сеанса</span><span class="sxs-lookup"><span data-stu-id="3425d-151">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="3425d-152">Эта команда создает **сеанс PSSession** с теми же свойствами, что и у существующего **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-152">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="3425d-153">Этот формат команды можно использовать, когда ресурсы существующего **сеанса PSSession** исчерпаны, а для разгрузки какого-либо запроса требуется новый **сеанс PSSession** .</span><span class="sxs-lookup"><span data-stu-id="3425d-153">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="3425d-154">Команда использует параметр **Session** объекта, `New-PSSession` чтобы указать **сеанс PSSession** , сохраненный в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-154">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="3425d-155">Она использует для выполнения команды учетные данные пользователя Domain1\Admin01.</span><span class="sxs-lookup"><span data-stu-id="3425d-155">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="3425d-156">Пример 6. Создание сеанса с глобальной областью в другом домене</span><span class="sxs-lookup"><span data-stu-id="3425d-156">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="3425d-157">В этом примере показано, как создать **сеанс PSSession** с глобальной областью на компьютере в другом домене.</span><span class="sxs-lookup"><span data-stu-id="3425d-157">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="3425d-158">По умолчанию объекты **PSSession** , созданные в командной строке, создаются с помощью локальной области, а объекты **PSSession** , созданные в скрипте, имеют область скриптов.</span><span class="sxs-lookup"><span data-stu-id="3425d-158">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="3425d-159">Чтобы создать **сеанс PSSession** с глобальной областью, создайте новый **сеанс PSSession** , а затем сохраните **PSSession** в переменной, приведенной к глобальной области.</span><span class="sxs-lookup"><span data-stu-id="3425d-159">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="3425d-160">В этом случае `$s` переменная приводится к глобальной области видимости.</span><span class="sxs-lookup"><span data-stu-id="3425d-160">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="3425d-161">Команда использует параметр **ComputerName** , чтобы указать удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3425d-161">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="3425d-162">Так как компьютер находится в домене, отличном от домена с учетной записью пользователя, полное имя компьютера указывается вместе с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-162">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="3425d-163">Пример 7. Создание сеансов для многих компьютеров</span><span class="sxs-lookup"><span data-stu-id="3425d-163">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="3425d-164">Эта команда создает **сеанс PSSession** на каждом из 200 компьютеров, перечисленных в файле Servers.txt и сохраняет полученный **сеанс PSSession** в `$rs` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-164">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="3425d-165">Объекты **PSSession** имеют ограничение регулирования в 50.</span><span class="sxs-lookup"><span data-stu-id="3425d-165">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="3425d-166">Этот формат команды можно использовать, если имена компьютеров хранятся в базе данных, электронной таблице, текстовом файле или другом формате, преобразуемом в текст.</span><span class="sxs-lookup"><span data-stu-id="3425d-166">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="3425d-167">Пример 8. Создание сеанса с помощью URI</span><span class="sxs-lookup"><span data-stu-id="3425d-167">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="3425d-168">Эта команда создает **сеанс PSSession** на компьютере Server01 и сохраняет его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-168">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="3425d-169">Он использует параметр **URI** , чтобы указать транспортный протокол, удаленный компьютер, порт и конфигурацию дополнительного сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-169">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="3425d-170">Он также использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на создание сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-170">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="3425d-171">Пример 9. Запуск фонового задания в наборе сеансов</span><span class="sxs-lookup"><span data-stu-id="3425d-171">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="3425d-172">Эти команды создают набор объектов **PSSession** , а затем запускают фоновое задание в каждом из объектов **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="3425d-172">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="3425d-173">Первая команда создает новый **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="3425d-173">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="3425d-174">Он использует `New-PSSession` командлет для создания **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-174">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="3425d-175">Значение параметра **ComputerName** — это команда, использующая `Get-Content` командлет для получения списка имен компьютеров с Servers.txtным файлом.</span><span class="sxs-lookup"><span data-stu-id="3425d-175">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="3425d-176">Команда использует параметр **Credential** для создания объектов **PSSession** , имеющих разрешение администратора домена, и использует параметр **ThrottleLimit** , чтобы ограничить команду 16 одновременными подключениями.</span><span class="sxs-lookup"><span data-stu-id="3425d-176">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="3425d-177">Команда сохраняет объекты **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-177">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="3425d-178">Вторая команда использует параметр **AsJob** `Invoke-Command` командлета для запуска фонового задания, которое выполняет `Get-Process PowerShell` команду в каждом из объектов **PSSession** в `$s` .</span><span class="sxs-lookup"><span data-stu-id="3425d-178">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="3425d-179">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-179">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="3425d-180">Пример 10. Создание сеанса для компьютера с помощью универсального кода ресурса (URI)</span><span class="sxs-lookup"><span data-stu-id="3425d-180">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="3425d-181">Эта команда создает объекты **PSSession** , которые подключаются к компьютеру, указанному с помощью универсального кода ресурса (URI), а не имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="3425d-181">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="3425d-182">Пример 11. Создание параметра сеанса</span><span class="sxs-lookup"><span data-stu-id="3425d-182">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="3425d-183">В этом примере показано, как создать объект параметров сеанса и использовать параметр **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="3425d-183">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="3425d-184">Первая команда использует `New-PSSessionOption` командлет для создания параметра сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-184">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="3425d-185">Он сохраняет полученный объект **SessionOption** в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-185">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="3425d-186">Вторая команда использует параметр в новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="3425d-186">The second command uses the option in a new session.</span></span> <span data-ttu-id="3425d-187">Команда использует `New-PSSession` командлет для создания нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-187">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="3425d-188">Значением параметра SessionOption является объект **SessionOption** в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="3425d-188">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

### <span data-ttu-id="3425d-189">Пример 12. Создание сеанса с помощью SSH</span><span class="sxs-lookup"><span data-stu-id="3425d-189">Example 12: Create a session using SSH</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="3425d-190">В этом примере показано, как создать новый **сеанс PSSession** с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-190">This example shows how to create a new **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="3425d-191">Если на удаленном компьютере настроен протокол SSH для запроса паролей, вы получите запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="3425d-191">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span> <span data-ttu-id="3425d-192">В противном случае необходимо будет использовать проверку подлинности пользователя на основе ключа SSH.</span><span class="sxs-lookup"><span data-stu-id="3425d-192">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="3425d-193">Пример 13. Создание сеанса с помощью SSH и указание ключа проверки подлинности порта и пользователя</span><span class="sxs-lookup"><span data-stu-id="3425d-193">Example 13: Create a session using SSH and specify the port and user authentication key</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="3425d-194">В этом примере показано, как создать **сеанс PSSession** с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-194">This example shows how to create a **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="3425d-195">Он использует параметр **Port** для указания используемого порта и параметр **KeyFilePath** для указания ключа RSA, используемого для идентификации пользователя на удаленном компьютере и проверки его подлинности.</span><span class="sxs-lookup"><span data-stu-id="3425d-195">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to identify and authenticate the user on the remote computer.</span></span>

### <span data-ttu-id="3425d-196">Пример 14. Создание нескольких сеансов с помощью SSH</span><span class="sxs-lookup"><span data-stu-id="3425d-196">Example 14: Create multiple sessions using SSH</span></span>

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

<span data-ttu-id="3425d-197">В этом примере показано, как создать несколько сеансов с помощью Secure Shell (SSH) и набора параметров **сшконнектион** .</span><span class="sxs-lookup"><span data-stu-id="3425d-197">This example shows how to create multiple sessions using Secure Shell (SSH) and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="3425d-198">Параметр **сшконнектион** принимает массив хэш-таблиц, содержащих сведения о соединении для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-198">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each session.</span></span> <span data-ttu-id="3425d-199">Обратите внимание, что этот пример требует, чтобы на целевых удаленных компьютерах был настроен SSH для поддержки проверки подлинности пользователей на основе ключей.</span><span class="sxs-lookup"><span data-stu-id="3425d-199">Note that this example requires that the target remote computers have SSH configured to support key based user authentication.</span></span>

## <span data-ttu-id="3425d-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3425d-200">PARAMETERS</span></span>

### <span data-ttu-id="3425d-201">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="3425d-201">-AllowRedirection</span></span>

<span data-ttu-id="3425d-202">Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="3425d-202">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="3425d-203">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="3425d-203">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="3425d-204">По умолчанию PowerShell не перенаправляет соединения, но этот параметр можно использовать, чтобы разрешить ему перенаправить подключение.</span><span class="sxs-lookup"><span data-stu-id="3425d-204">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="3425d-205">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="3425d-205">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="3425d-206">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** переменной предпочтений **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="3425d-206">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="3425d-207">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="3425d-207">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-208">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="3425d-208">-ApplicationName</span></span>

<span data-ttu-id="3425d-209">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="3425d-209">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="3425d-210">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI**.</span><span class="sxs-lookup"><span data-stu-id="3425d-210">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="3425d-211">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-211">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="3425d-212">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="3425d-212">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="3425d-213">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="3425d-213">This value is appropriate for most uses.</span></span> <span data-ttu-id="3425d-214">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-214">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="3425d-215">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="3425d-215">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="3425d-216">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-216">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-217">-Authentication</span><span class="sxs-lookup"><span data-stu-id="3425d-217">-Authentication</span></span>

<span data-ttu-id="3425d-218">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-218">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="3425d-219">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3425d-219">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3425d-220">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="3425d-220">Default</span></span>
- <span data-ttu-id="3425d-221">Базовый</span><span class="sxs-lookup"><span data-stu-id="3425d-221">Basic</span></span>
- <span data-ttu-id="3425d-222">CredSSP</span><span class="sxs-lookup"><span data-stu-id="3425d-222">Credssp</span></span>
- <span data-ttu-id="3425d-223">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="3425d-223">Digest</span></span>
- <span data-ttu-id="3425d-224">Kerberos</span><span class="sxs-lookup"><span data-stu-id="3425d-224">Kerberos</span></span>
- <span data-ttu-id="3425d-225">Согласование</span><span class="sxs-lookup"><span data-stu-id="3425d-225">Negotiate</span></span>
- <span data-ttu-id="3425d-226">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="3425d-226">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="3425d-227">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="3425d-227">The default value is Default.</span></span>

<span data-ttu-id="3425d-228">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="3425d-228">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="3425d-229">Проверка подлинности с помощью поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="3425d-229">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="3425d-230">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="3425d-230">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="3425d-231">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="3425d-231">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-232">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="3425d-232">-CertificateThumbprint</span></span>

<span data-ttu-id="3425d-233">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="3425d-233">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="3425d-234">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="3425d-234">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="3425d-235">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="3425d-235">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="3425d-236">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="3425d-236">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="3425d-237">Чтобы получить сертификат, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="3425d-237">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-238">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3425d-238">-ComputerName</span></span>

<span data-ttu-id="3425d-239">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-239">Specifies an array of names of computers.</span></span> <span data-ttu-id="3425d-240">Этот командлет создает постоянное подключение ( **PSSession** ) к указанному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-240">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="3425d-241">Если ввести несколько имен компьютеров, `New-PSSession` создает несколько объектов **PSSession** , по одному для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3425d-241">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="3425d-242">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3425d-242">The default is the local computer.</span></span>

<span data-ttu-id="3425d-243">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-243">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="3425d-244">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="3425d-244">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="3425d-245">Если компьютер находится в другом домене, отличном от домена пользователя, полное доменное имя является обязательным.</span><span class="sxs-lookup"><span data-stu-id="3425d-245">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="3425d-246">Также можно передать имя компьютера в кавычках в `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3425d-246">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="3425d-247">Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="3425d-247">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="3425d-248">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-248">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="3425d-249">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-249">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="3425d-250">Чтобы включить локальный компьютер в значение параметра **ComputerName** , запустите Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3425d-250">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-251">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="3425d-251">-ConfigurationName</span></span>

<span data-ttu-id="3425d-252">Указывает конфигурацию сеанса, используемую для нового **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-252">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="3425d-253">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-253">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="3425d-254">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="3425d-254">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="3425d-255">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-255">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="3425d-256">Если указанной конфигурации сеанса нет на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3425d-256">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="3425d-257">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-257">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="3425d-258">Если эта привилегированная переменная не определена, значением по умолчанию является Microsoft.PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3425d-258">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="3425d-259">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-259">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-260">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="3425d-260">-ConnectionUri</span></span>

<span data-ttu-id="3425d-261">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-261">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="3425d-262">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="3425d-262">The URI must be fully qualified.</span></span> <span data-ttu-id="3425d-263">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="3425d-263">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="3425d-264">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3425d-264">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="3425d-265">Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI**.</span><span class="sxs-lookup"><span data-stu-id="3425d-265">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="3425d-266">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3425d-266">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="3425d-267">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3425d-267">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="3425d-268">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3425d-268">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="3425d-269">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="3425d-269">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-270">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="3425d-270">-ContainerId</span></span>

<span data-ttu-id="3425d-271">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-271">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="3425d-272">Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-272">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="3425d-273">Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-273">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="3425d-274">Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="3425d-274">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-275">-Credential</span><span class="sxs-lookup"><span data-stu-id="3425d-275">-Credential</span></span>

<span data-ttu-id="3425d-276">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="3425d-276">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="3425d-277">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="3425d-277">The default is the current user.</span></span>

<span data-ttu-id="3425d-278">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="3425d-278">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3425d-279">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="3425d-279">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="3425d-280">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="3425d-280">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="3425d-281">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="3425d-281">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-282">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="3425d-282">-EnableNetworkAccess</span></span>

<span data-ttu-id="3425d-283">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="3425d-283">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="3425d-284">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-284">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="3425d-285">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="3425d-285">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="3425d-286">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-286">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="3425d-287">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot (.), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3425d-287">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="3425d-288">По умолчанию этот командлет создает сеансы замыкания на себя с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3425d-288">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="3425d-289">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="3425d-289">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="3425d-290">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3425d-290">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="3425d-291">Кроме того, можно включить удаленный доступ в сеансе замыкания на себя, используя значение CredSSP параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.</span><span class="sxs-lookup"><span data-stu-id="3425d-291">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="3425d-292">Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью параметра **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="3425d-292">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="3425d-293">Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3425d-293">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="3425d-294">Для получения дополнительной информации см. `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="3425d-294">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="3425d-295">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-295">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-296">-HostName</span><span class="sxs-lookup"><span data-stu-id="3425d-296">-HostName</span></span>

<span data-ttu-id="3425d-297">Указывает массив имен компьютеров для подключения на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-297">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="3425d-298">Это похоже на параметр ComputerName, за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.</span><span class="sxs-lookup"><span data-stu-id="3425d-298">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="3425d-299">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-299">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-300">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="3425d-300">-KeyFilePath</span></span>

<span data-ttu-id="3425d-301">Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-301">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="3425d-302">SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля.</span><span class="sxs-lookup"><span data-stu-id="3425d-302">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="3425d-303">Если на удаленном компьютере настроена проверка подлинности с помощью ключа, этот параметр можно использовать для предоставления ключа, определяющего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-303">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="3425d-304">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-304">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-305">-Name</span><span class="sxs-lookup"><span data-stu-id="3425d-305">-Name</span></span>

<span data-ttu-id="3425d-306">Указывает понятное имя для **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-306">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="3425d-307">Имя можно использовать для ссылки на **PSSession** при использовании других командлетов, таких как `Get-PSSession` и `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3425d-307">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="3425d-308">Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-308">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-309">-Port</span><span class="sxs-lookup"><span data-stu-id="3425d-309">-Port</span></span>

<span data-ttu-id="3425d-310">Задает сетевой порт на удаленном компьютере, используемый для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="3425d-310">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="3425d-311">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="3425d-311">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="3425d-312">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3425d-312">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="3425d-313">Прежде чем использовать другой порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта.</span><span class="sxs-lookup"><span data-stu-id="3425d-313">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="3425d-314">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="3425d-314">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="3425d-315">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="3425d-315">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="3425d-316">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="3425d-316">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="3425d-317">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3425d-317">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-318">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="3425d-318">-RunAsAdministrator</span></span>

<span data-ttu-id="3425d-319">Указывает, что **сеанс PSSession** запускается от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3425d-319">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-320">-Session</span><span class="sxs-lookup"><span data-stu-id="3425d-320">-Session</span></span>

<span data-ttu-id="3425d-321">Указывает массив объектов **PSSession** , который используется этим командлетом в качестве модели для нового **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-321">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="3425d-322">Этот параметр создает новые объекты **PSSession** , имеющие те же свойства, что и указанные объекты **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="3425d-322">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="3425d-323">Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` `Get-PSSession` команда или.</span><span class="sxs-lookup"><span data-stu-id="3425d-323">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="3425d-324">Итоговые объекты **PSSession** имеют те же имя компьютера, имя приложения, URI подключения, порт, имя конфигурации, предел регулирования и SSL (SSL) в качестве исходных значений, но имеют разные отображаемые имя, идентификатор и идентификатор экземпляра (GUID).</span><span class="sxs-lookup"><span data-stu-id="3425d-324">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-325">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="3425d-325">-SessionOption</span></span>

<span data-ttu-id="3425d-326">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-326">Specifies advanced options for the session.</span></span> <span data-ttu-id="3425d-327">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-327">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="3425d-328">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="3425d-328">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="3425d-329">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-329">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="3425d-330">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-330">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="3425d-331">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-331">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="3425d-332">Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="3425d-332">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="3425d-333">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-333">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="3425d-334">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-334">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-335">-Сшконнектион</span><span class="sxs-lookup"><span data-stu-id="3425d-335">-SSHConnection</span></span>

<span data-ttu-id="3425d-336">Этот параметр принимает массив хэш-таблиц, где каждая таблица Hashtable содержит один или несколько параметров соединения, необходимых для установления подключения Secure Shell (имя узла, порт, имя пользователя, KeyFilePath).</span><span class="sxs-lookup"><span data-stu-id="3425d-336">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath).</span></span>

<span data-ttu-id="3425d-337">Параметры соединения Hashtable аналогичны параметрам, заданным для набора параметров **HostName** .</span><span class="sxs-lookup"><span data-stu-id="3425d-337">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>

<span data-ttu-id="3425d-338">Параметр **сшконнектион** полезен для создания нескольких сеансов, в которых каждому сеансу требуются разные сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="3425d-338">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="3425d-339">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-339">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-340">-Сштранспорт</span><span class="sxs-lookup"><span data-stu-id="3425d-340">-SSHTransport</span></span>

<span data-ttu-id="3425d-341">Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-341">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="3425d-342">По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-342">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="3425d-343">Этот параметр заставляет PowerShell использовать набор параметров HostName для установления удаленного подключения на основе SSH.</span><span class="sxs-lookup"><span data-stu-id="3425d-343">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="3425d-344">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-344">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-345">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="3425d-345">-ThrottleLimit</span></span>

<span data-ttu-id="3425d-346">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="3425d-346">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="3425d-347">Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="3425d-347">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="3425d-348">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-348">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-349">-UserName</span><span class="sxs-lookup"><span data-stu-id="3425d-349">-UserName</span></span>

<span data-ttu-id="3425d-350">Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-350">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="3425d-351">Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-351">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="3425d-352">Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-352">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="3425d-353">Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра KeyFilePath. при этом запрос на ввод пароля не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="3425d-353">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="3425d-354">Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр KeyFilePath не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-354">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="3425d-355">Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.</span><span class="sxs-lookup"><span data-stu-id="3425d-355">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="3425d-356">Этот параметр не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="3425d-356">This is not a required parameter.</span></span> <span data-ttu-id="3425d-357">Если параметр UserName не указан, то для соединения используется текущее имя пользователя для входа.</span><span class="sxs-lookup"><span data-stu-id="3425d-357">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="3425d-358">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-358">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-359">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="3425d-359">-UseSSL</span></span>

<span data-ttu-id="3425d-360">Указывает, что этот командлет использует протокол SSL для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="3425d-360">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="3425d-361">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="3425d-361">By default, SSL is not used.</span></span>

<span data-ttu-id="3425d-362">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="3425d-362">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="3425d-363">Параметр **UseSSL** обеспечивает дополнительную защиту, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="3425d-363">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="3425d-364">Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3425d-364">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-365">— VMId</span><span class="sxs-lookup"><span data-stu-id="3425d-365">-VMId</span></span>

<span data-ttu-id="3425d-366">Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="3425d-366">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="3425d-367">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="3425d-367">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="3425d-368">Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3425d-368">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-369">-VMName</span><span class="sxs-lookup"><span data-stu-id="3425d-369">-VMName</span></span>

<span data-ttu-id="3425d-370">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="3425d-370">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="3425d-371">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="3425d-371">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="3425d-372">Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.</span><span class="sxs-lookup"><span data-stu-id="3425d-372">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-373">-HostName</span><span class="sxs-lookup"><span data-stu-id="3425d-373">-HostName</span></span>

<span data-ttu-id="3425d-374">Указывает массив имен компьютеров для подключения на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-374">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="3425d-375">Это похоже на параметр ComputerName, за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.</span><span class="sxs-lookup"><span data-stu-id="3425d-375">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>
<span data-ttu-id="3425d-376">Этот параметр поддерживает указание имени пользователя и/или порта в качестве части значения параметра имени узла с помощью формы `user@hostname:port` .</span><span class="sxs-lookup"><span data-stu-id="3425d-376">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span>
<span data-ttu-id="3425d-377">Имя пользователя и (или) порт, указанный как часть имени узла, имеет приоритет над `-UserName` параметрами и `-Port` , если они заданы.</span><span class="sxs-lookup"><span data-stu-id="3425d-377">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span>
<span data-ttu-id="3425d-378">Это позволяет передавать этому параметру несколько имен компьютеров, где некоторые имеют определенные имена пользователей и (или) порты, а другие используют имя пользователя и (или) порт `-UserName` из `-Port` параметров и.</span><span class="sxs-lookup"><span data-stu-id="3425d-378">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="3425d-379">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-379">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: HostName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-380">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="3425d-380">-KeyFilePath</span></span>

<span data-ttu-id="3425d-381">Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-381">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="3425d-382">SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля.</span><span class="sxs-lookup"><span data-stu-id="3425d-382">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="3425d-383">Если на удаленном компьютере настроена проверка подлинности с помощью ключа, этот параметр можно использовать для предоставления ключа, определяющего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-383">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="3425d-384">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-384">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-385">-Сштранспорт</span><span class="sxs-lookup"><span data-stu-id="3425d-385">-SSHTransport</span></span>

<span data-ttu-id="3425d-386">Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-386">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="3425d-387">По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3425d-387">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="3425d-388">Этот параметр заставляет PowerShell использовать набор параметров HostName для установления удаленного подключения на основе SSH.</span><span class="sxs-lookup"><span data-stu-id="3425d-388">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="3425d-389">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-389">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-390">-UserName</span><span class="sxs-lookup"><span data-stu-id="3425d-390">-UserName</span></span>

<span data-ttu-id="3425d-391">Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-391">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="3425d-392">Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3425d-392">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="3425d-393">Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-393">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="3425d-394">Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра KeyFilePath. при этом запрос на ввод пароля не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="3425d-394">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="3425d-395">Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр KeyFilePath не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-395">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="3425d-396">Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.</span><span class="sxs-lookup"><span data-stu-id="3425d-396">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="3425d-397">Этот параметр не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="3425d-397">This is not a required parameter.</span></span> <span data-ttu-id="3425d-398">Если параметр UserName не указан, то для соединения используется текущее имя пользователя для входа.</span><span class="sxs-lookup"><span data-stu-id="3425d-398">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="3425d-399">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-399">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-400">-Сшконнектион</span><span class="sxs-lookup"><span data-stu-id="3425d-400">-SSHConnection</span></span>

<span data-ttu-id="3425d-401">Этот параметр принимает массив хэш-таблиц, где каждая таблица Hashtable содержит один или несколько параметров соединения, необходимых для установления подключения Secure Shell (имя узла, порт, имя пользователя, KeyFilePath, подсистема).</span><span class="sxs-lookup"><span data-stu-id="3425d-401">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath, Subsystem).</span></span>

<span data-ttu-id="3425d-402">Параметры соединения Hashtable аналогичны параметрам, заданным для набора параметров **HostName** .</span><span class="sxs-lookup"><span data-stu-id="3425d-402">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>
<span data-ttu-id="3425d-403">Обратите внимание, что порядок ключей в хэш-таблице приводит к тому, что имя пользователя и порт используются для соединения, в котором используется последнее указанное значение.</span><span class="sxs-lookup"><span data-stu-id="3425d-403">Note that the order of the keys in the hashtable result in user name and port being used for the connection where the last one specified is used.</span></span>  <span data-ttu-id="3425d-404">Например, если используется `@{UserName="first";HostName="second@host"}` , `second` будет использоваться имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3425d-404">For example, if you use `@{UserName="first";HostName="second@host"}`, then the user name `second` will be used.</span></span>  <span data-ttu-id="3425d-405">Однако если используется `@{HostName="second@host:22";Port=23}` , будет использоваться порт 23.</span><span class="sxs-lookup"><span data-stu-id="3425d-405">However, if you use `@{HostName="second@host:22";Port=23}`, then port 23 will be used.</span></span>

<span data-ttu-id="3425d-406">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-406">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="3425d-407">Параметр **сшконнектион** полезен для создания нескольких сеансов, в которых каждому сеансу требуются разные сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="3425d-407">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

```yaml
Type: hashtable
Parameter Sets: SSHConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-408">-Подсистема</span><span class="sxs-lookup"><span data-stu-id="3425d-408">-Subsystem</span></span>

<span data-ttu-id="3425d-409">Указывает подсистему SSH, используемую для нового **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="3425d-409">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="3425d-410">Указывает подсистему для использования в целевом объекте, как определено в sshd_config.</span><span class="sxs-lookup"><span data-stu-id="3425d-410">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="3425d-411">Подсистема запускает определенную версию PowerShell с предопределенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="3425d-411">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="3425d-412">Если указанная подсистема не существует на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3425d-412">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="3425d-413">Если этот параметр не используется, по умолчанию используется подсистема PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3425d-413">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3425d-414">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3425d-414">CommonParameters</span></span>

<span data-ttu-id="3425d-415">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3425d-415">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3425d-416">Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3425d-416">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3425d-417">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3425d-417">INPUTS</span></span>

### <span data-ttu-id="3425d-418">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-418">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="3425d-419">В этот командлет можно передать строку, URI или объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="3425d-419">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="3425d-420">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3425d-420">OUTPUTS</span></span>

### <span data-ttu-id="3425d-421">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-421">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="3425d-422">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3425d-422">NOTES</span></span>

- <span data-ttu-id="3425d-423">Этот командлет использует инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3425d-423">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="3425d-424">Для использования этого командлета локальный компьютер и все удаленные компьютеры должны быть настроены для удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3425d-424">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="3425d-425">Дополнительные сведения см. в разделе [about_Remote_Requirements](About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3425d-425">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="3425d-426">Чтобы создать **сеанс PSSession** на локальном компьютере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3425d-426">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="3425d-427">По завершении работы с **PSSession** используйте `Remove-PSSession` командлет, чтобы удалить **сеанс PSSession** и освободить его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="3425d-427">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>
- <span data-ttu-id="3425d-428">Наборы параметров **HostName** и **сшконнектион** были добавлены начиная с PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3425d-428">The **HostName** and **SSHConnection** parameter sets were included starting with PowerShell 6.0.</span></span>
  <span data-ttu-id="3425d-429">Они были добавлены для обеспечения удаленного взаимодействия PowerShell на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="3425d-429">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="3425d-430">SSH и PowerShell поддерживаются на нескольких платформах (Windows, Linux, macOS) и удаленное взаимодействие PowerShell будет работать на этих платформах, где установлены и настроены PowerShell и SSH.</span><span class="sxs-lookup"><span data-stu-id="3425d-430">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="3425d-431">Это отдельно от предыдущего удаленного взаимодействия только в Windows, основанного на WinRM, и многие функции и ограничения WinRM не применяются.</span><span class="sxs-lookup"><span data-stu-id="3425d-431">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="3425d-432">Например, квоты на основе WinRM, параметры сеанса, конфигурация пользовательской конечной точки и функции отключения и повторного подключения сейчас не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3425d-432">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="3425d-433">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="3425d-433">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="3425d-434">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3425d-434">RELATED LINKS</span></span>

[<span data-ttu-id="3425d-435">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-435">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="3425d-436">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-436">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="3425d-437">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-437">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="3425d-438">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="3425d-438">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="3425d-439">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-439">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="3425d-440">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3425d-440">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="3425d-441">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-441">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="3425d-442">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="3425d-442">Remove-PSSession</span></span>](Remove-PSSession.md)

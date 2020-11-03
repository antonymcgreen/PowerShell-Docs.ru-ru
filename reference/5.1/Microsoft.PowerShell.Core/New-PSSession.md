---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 1835d0bd4294161f83728a63e8da8fc64c2bf9e0
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229761"
---
# <span data-ttu-id="5b475-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-103">New-PSSession</span></span>

## <span data-ttu-id="5b475-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5b475-104">SYNOPSIS</span></span>
<span data-ttu-id="5b475-105">Создает постоянное подключение к локальному или удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5b475-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="5b475-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b475-106">SYNTAX</span></span>

### <span data-ttu-id="5b475-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5b475-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="5b475-108">URI</span><span class="sxs-lookup"><span data-stu-id="5b475-108">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="5b475-109">VMId</span><span class="sxs-lookup"><span data-stu-id="5b475-109">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="5b475-110">VMName</span><span class="sxs-lookup"><span data-stu-id="5b475-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="5b475-111">Сеанс</span><span class="sxs-lookup"><span data-stu-id="5b475-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="5b475-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="5b475-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="5b475-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b475-113">DESCRIPTION</span></span>

<span data-ttu-id="5b475-114">`New-PSSession`Командлет создает сеанс PowerShell ( **PSSession** ) на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-114">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="5b475-115">При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5b475-115">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="5b475-116">Используйте **PSSession** для выполнения нескольких команд, совместно использующих данные, таких как функция или значение переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-116">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="5b475-117">Для выполнения команд в **PSSession** используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="5b475-117">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="5b475-118">Чтобы использовать **PSSession** для взаимодействия непосредственно с удаленным компьютером, используйте `Enter-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="5b475-118">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="5b475-119">Дополнительные сведения см. в разделе [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-119">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="5b475-120">Команды можно выполнять на удаленном компьютере без создания **сеанса PSSession** с помощью параметров **ComputerName** параметра `Enter-PSSession` или `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="5b475-120">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="5b475-121">При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется для команды и затем закрывается.</span><span class="sxs-lookup"><span data-stu-id="5b475-121">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

## <span data-ttu-id="5b475-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="5b475-122">EXAMPLES</span></span>

### <span data-ttu-id="5b475-123">Пример 1. Создание сеанса на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="5b475-123">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="5b475-124">Эта команда создает новый **сеанс PSSession** на локальном компьютере и сохраняет **сеанс PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-124">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="5b475-125">Теперь этот **сеанс PSSession** можно использовать для выполнения команд на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-125">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="5b475-126">Пример 2. Создание сеанса на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="5b475-126">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="5b475-127">Эта команда создает новый **сеанс PSSession** на компьютере Server01 и сохраняет его в `$Server01` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-127">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="5b475-128">При создании нескольких объектов **PSSession** назначьте их переменным с полезными именами.</span><span class="sxs-lookup"><span data-stu-id="5b475-128">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="5b475-129">Это позволит управлять объектами **PSSession** в последующих командах.</span><span class="sxs-lookup"><span data-stu-id="5b475-129">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="5b475-130">Пример 3. Создание сеансов на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="5b475-130">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="5b475-131">Эта команда создает три объекта **PSSession** — по одному на каждом из компьютеров, указанных параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5b475-131">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="5b475-132">Команда использует оператор присваивания (=) для назначения новых объектов **PSSession** переменным: `$s1` , `$s2` , `$s3` .</span><span class="sxs-lookup"><span data-stu-id="5b475-132">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="5b475-133">Он назначает Server01 **PSSession** `$s1` , Server02 **PSSession** `$s2` —, а Server03 **PSSession** — `$s3` .</span><span class="sxs-lookup"><span data-stu-id="5b475-133">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="5b475-134">При назначении нескольких объектов ряду переменных PowerShell каждый объект назначается переменной в ряде, соответственно.</span><span class="sxs-lookup"><span data-stu-id="5b475-134">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="5b475-135">Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-135">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="5b475-136">Если переменных больше, чем объектов, оставшиеся переменные остаются пустыми (null).</span><span class="sxs-lookup"><span data-stu-id="5b475-136">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="5b475-137">Пример 4. Создание сеанса с указанным портом</span><span class="sxs-lookup"><span data-stu-id="5b475-137">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="5b475-138">Эта команда создает новый **сеанс PSSession** на компьютере Server01, который подключается к порту сервера 8081 и использует протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="5b475-138">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="5b475-139">Новый сеанс **PSSession** использует альтернативную конфигурацию сеанса с именем E12.</span><span class="sxs-lookup"><span data-stu-id="5b475-139">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="5b475-140">Прежде чем задать порт, необходимо настроить прослушиватель службы удаленного управления Windows для прослушивания порта 8081 на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-140">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="5b475-141">Дополнительные сведения см. в описании параметра **Port**.</span><span class="sxs-lookup"><span data-stu-id="5b475-141">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="5b475-142">Пример 5. Создание сеанса на основе существующего сеанса</span><span class="sxs-lookup"><span data-stu-id="5b475-142">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="5b475-143">Эта команда создает **сеанс PSSession** с теми же свойствами, что и у существующего **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="5b475-143">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="5b475-144">Этот формат команды можно использовать, когда ресурсы существующего **сеанса PSSession** исчерпаны, а для разгрузки какого-либо запроса требуется новый **сеанс PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5b475-144">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="5b475-145">Команда использует параметр **Session** объекта, `New-PSSession` чтобы указать **сеанс PSSession** , сохраненный в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-145">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="5b475-146">Она использует для выполнения команды учетные данные пользователя Domain1\Admin01.</span><span class="sxs-lookup"><span data-stu-id="5b475-146">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="5b475-147">Пример 6. Создание сеанса с глобальной областью в другом домене</span><span class="sxs-lookup"><span data-stu-id="5b475-147">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="5b475-148">В этом примере показано, как создать **сеанс PSSession** с глобальной областью на компьютере в другом домене.</span><span class="sxs-lookup"><span data-stu-id="5b475-148">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="5b475-149">По умолчанию объекты **PSSession** , созданные в командной строке, создаются с помощью локальной области, а объекты **PSSession** , созданные в скрипте, имеют область скриптов.</span><span class="sxs-lookup"><span data-stu-id="5b475-149">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="5b475-150">Чтобы создать **сеанс PSSession** с глобальной областью, создайте новый **сеанс PSSession** , а затем сохраните **PSSession** в переменной, приведенной к глобальной области.</span><span class="sxs-lookup"><span data-stu-id="5b475-150">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="5b475-151">В этом случае `$s` переменная приводится к глобальной области видимости.</span><span class="sxs-lookup"><span data-stu-id="5b475-151">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="5b475-152">Команда использует параметр **ComputerName** , чтобы указать удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="5b475-152">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="5b475-153">Так как компьютер находится в домене, отличном от домена с учетной записью пользователя, полное имя компьютера указывается вместе с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="5b475-153">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="5b475-154">Пример 7. Создание сеансов для многих компьютеров</span><span class="sxs-lookup"><span data-stu-id="5b475-154">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="5b475-155">Эта команда создает **сеанс PSSession** на каждом из 200 компьютеров, перечисленных в файле Servers.txt и сохраняет полученный **сеанс PSSession** в `$rs` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-155">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="5b475-156">Объекты **PSSession** имеют ограничение регулирования в 50.</span><span class="sxs-lookup"><span data-stu-id="5b475-156">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="5b475-157">Этот формат команды можно использовать, если имена компьютеров хранятся в базе данных, электронной таблице, текстовом файле или другом формате, преобразуемом в текст.</span><span class="sxs-lookup"><span data-stu-id="5b475-157">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="5b475-158">Пример 8. Создание сеанса с помощью URI</span><span class="sxs-lookup"><span data-stu-id="5b475-158">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="5b475-159">Эта команда создает **сеанс PSSession** на компьютере Server01 и сохраняет его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-159">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="5b475-160">Он использует параметр **URI** , чтобы указать транспортный протокол, удаленный компьютер, порт и конфигурацию дополнительного сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-160">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="5b475-161">Он также использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на создание сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-161">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="5b475-162">Пример 9. Запуск фонового задания в наборе сеансов</span><span class="sxs-lookup"><span data-stu-id="5b475-162">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="5b475-163">Эти команды создают набор объектов **PSSession** , а затем запускают фоновое задание в каждом из объектов **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5b475-163">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="5b475-164">Первая команда создает новый **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="5b475-164">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="5b475-165">Он использует `New-PSSession` командлет для создания **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="5b475-165">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="5b475-166">Значение параметра **ComputerName** — это команда, использующая `Get-Content` командлет для получения списка имен компьютеров с Servers.txtным файлом.</span><span class="sxs-lookup"><span data-stu-id="5b475-166">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="5b475-167">Команда использует параметр **Credential** для создания объектов **PSSession** , имеющих разрешение администратора домена, и использует параметр **ThrottleLimit** , чтобы ограничить команду 16 одновременными подключениями.</span><span class="sxs-lookup"><span data-stu-id="5b475-167">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="5b475-168">Команда сохраняет объекты **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-168">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="5b475-169">Вторая команда использует параметр **AsJob** `Invoke-Command` командлета для запуска фонового задания, которое выполняет `Get-Process PowerShell` команду в каждом из объектов **PSSession** в `$s` .</span><span class="sxs-lookup"><span data-stu-id="5b475-169">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="5b475-170">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-170">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="5b475-171">Пример 10. Создание сеанса для компьютера с помощью универсального кода ресурса (URI)</span><span class="sxs-lookup"><span data-stu-id="5b475-171">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="5b475-172">Эта команда создает объекты **PSSession** , которые подключаются к компьютеру, указанному с помощью универсального кода ресурса (URI), а не имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="5b475-172">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="5b475-173">Пример 11. Создание параметра сеанса</span><span class="sxs-lookup"><span data-stu-id="5b475-173">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="5b475-174">В этом примере показано, как создать объект параметров сеанса и использовать параметр **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="5b475-174">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="5b475-175">Первая команда использует `New-PSSessionOption` командлет для создания параметра сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-175">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="5b475-176">Он сохраняет полученный объект **SessionOption** в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-176">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="5b475-177">Вторая команда использует параметр в новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="5b475-177">The second command uses the option in a new session.</span></span> <span data-ttu-id="5b475-178">Команда использует `New-PSSession` командлет для создания нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-178">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="5b475-179">Значением параметра SessionOption является объект **SessionOption** в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="5b475-179">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

## <span data-ttu-id="5b475-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b475-180">PARAMETERS</span></span>

### <span data-ttu-id="5b475-181">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="5b475-181">-AllowRedirection</span></span>

<span data-ttu-id="5b475-182">Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="5b475-182">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="5b475-183">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="5b475-183">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="5b475-184">По умолчанию PowerShell не перенаправляет соединения, но этот параметр можно использовать, чтобы разрешить ему перенаправить подключение.</span><span class="sxs-lookup"><span data-stu-id="5b475-184">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="5b475-185">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="5b475-185">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="5b475-186">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** переменной предпочтений **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="5b475-186">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="5b475-187">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="5b475-187">The default value is 5.</span></span>

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

### <span data-ttu-id="5b475-188">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="5b475-188">-ApplicationName</span></span>

<span data-ttu-id="5b475-189">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="5b475-189">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="5b475-190">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI**.</span><span class="sxs-lookup"><span data-stu-id="5b475-190">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="5b475-191">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-191">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="5b475-192">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="5b475-192">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="5b475-193">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="5b475-193">This value is appropriate for most uses.</span></span> <span data-ttu-id="5b475-194">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-194">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="5b475-195">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="5b475-195">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="5b475-196">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-196">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="5b475-197">-Authentication</span><span class="sxs-lookup"><span data-stu-id="5b475-197">-Authentication</span></span>

<span data-ttu-id="5b475-198">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="5b475-198">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="5b475-199">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5b475-199">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5b475-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="5b475-200">Default</span></span>
- <span data-ttu-id="5b475-201">Базовый</span><span class="sxs-lookup"><span data-stu-id="5b475-201">Basic</span></span>
- <span data-ttu-id="5b475-202">CredSSP</span><span class="sxs-lookup"><span data-stu-id="5b475-202">Credssp</span></span>
- <span data-ttu-id="5b475-203">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="5b475-203">Digest</span></span>
- <span data-ttu-id="5b475-204">Kerberos</span><span class="sxs-lookup"><span data-stu-id="5b475-204">Kerberos</span></span>
- <span data-ttu-id="5b475-205">Согласование</span><span class="sxs-lookup"><span data-stu-id="5b475-205">Negotiate</span></span>
- <span data-ttu-id="5b475-206">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="5b475-206">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="5b475-207">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="5b475-207">The default value is Default.</span></span>

<span data-ttu-id="5b475-208">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="5b475-208">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="5b475-209">Проверка подлинности с помощью поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="5b475-209">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="5b475-210">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="5b475-210">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="5b475-211">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="5b475-211">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="5b475-212">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="5b475-212">-CertificateThumbprint</span></span>

<span data-ttu-id="5b475-213">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="5b475-213">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="5b475-214">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="5b475-214">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="5b475-215">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="5b475-215">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="5b475-216">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="5b475-216">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5b475-217">Чтобы получить сертификат, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="5b475-217">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="5b475-218">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5b475-218">-ComputerName</span></span>

<span data-ttu-id="5b475-219">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-219">Specifies an array of names of computers.</span></span> <span data-ttu-id="5b475-220">Этот командлет создает постоянное подключение ( **PSSession** ) к указанному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5b475-220">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="5b475-221">Если ввести несколько имен компьютеров, `New-PSSession` создает несколько объектов **PSSession** , по одному для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="5b475-221">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="5b475-222">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="5b475-222">The default is the local computer.</span></span>

<span data-ttu-id="5b475-223">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-223">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="5b475-224">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="5b475-224">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="5b475-225">Если компьютер находится в другом домене, отличном от домена пользователя, полное доменное имя является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5b475-225">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="5b475-226">Также можно передать имя компьютера в кавычках в `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="5b475-226">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="5b475-227">Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="5b475-227">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="5b475-228">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-228">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="5b475-229">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-229">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="5b475-230">Чтобы включить локальный компьютер в значение параметра **ComputerName** , запустите Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5b475-230">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

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

### <span data-ttu-id="5b475-231">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5b475-231">-ConfigurationName</span></span>

<span data-ttu-id="5b475-232">Указывает конфигурацию сеанса, используемую для нового **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="5b475-232">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="5b475-233">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-233">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="5b475-234">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="5b475-234">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="5b475-235">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-235">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="5b475-236">Если указанной конфигурации сеанса нет на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5b475-236">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="5b475-237">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-237">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="5b475-238">Если эта привилегированная переменная не определена, значением по умолчанию является Microsoft.PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b475-238">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="5b475-239">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-239">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="5b475-240">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="5b475-240">-ConnectionUri</span></span>

<span data-ttu-id="5b475-241">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-241">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="5b475-242">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="5b475-242">The URI must be fully qualified.</span></span> <span data-ttu-id="5b475-243">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="5b475-243">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="5b475-244">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b475-244">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="5b475-245">Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI**.</span><span class="sxs-lookup"><span data-stu-id="5b475-245">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="5b475-246">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b475-246">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="5b475-247">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b475-247">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="5b475-248">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b475-248">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="5b475-249">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="5b475-249">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="5b475-250">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="5b475-250">-ContainerId</span></span>

<span data-ttu-id="5b475-251">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-251">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="5b475-252">Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-252">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="5b475-253">Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-253">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="5b475-254">Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="5b475-254">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

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

### <span data-ttu-id="5b475-255">-Credential</span><span class="sxs-lookup"><span data-stu-id="5b475-255">-Credential</span></span>

<span data-ttu-id="5b475-256">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="5b475-256">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="5b475-257">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="5b475-257">The default is the current user.</span></span>

<span data-ttu-id="5b475-258">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="5b475-258">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="5b475-259">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="5b475-259">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="5b475-260">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="5b475-260">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="5b475-261">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="5b475-261">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="5b475-262">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="5b475-262">-EnableNetworkAccess</span></span>

<span data-ttu-id="5b475-263">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="5b475-263">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="5b475-264">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-264">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="5b475-265">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="5b475-265">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="5b475-266">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b475-266">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="5b475-267">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot (.), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="5b475-267">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="5b475-268">По умолчанию этот командлет создает сеансы замыкания на себя с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5b475-268">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="5b475-269">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="5b475-269">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="5b475-270">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="5b475-270">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="5b475-271">Кроме того, можно включить удаленный доступ в сеансе замыкания на себя, используя значение CredSSP параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.</span><span class="sxs-lookup"><span data-stu-id="5b475-271">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="5b475-272">Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью параметра **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="5b475-272">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="5b475-273">Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5b475-273">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="5b475-274">Для получения дополнительной информации см. `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="5b475-274">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="5b475-275">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5b475-275">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b475-276">-Name</span><span class="sxs-lookup"><span data-stu-id="5b475-276">-Name</span></span>

<span data-ttu-id="5b475-277">Указывает понятное имя для **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="5b475-277">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="5b475-278">Имя можно использовать для ссылки на **PSSession** при использовании других командлетов, таких как `Get-PSSession` и `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="5b475-278">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="5b475-279">Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-279">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="5b475-280">-Port</span><span class="sxs-lookup"><span data-stu-id="5b475-280">-Port</span></span>

<span data-ttu-id="5b475-281">Задает сетевой порт на удаленном компьютере, используемый для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="5b475-281">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="5b475-282">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="5b475-282">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="5b475-283">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b475-283">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="5b475-284">Прежде чем использовать другой порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта.</span><span class="sxs-lookup"><span data-stu-id="5b475-284">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="5b475-285">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5b475-285">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="5b475-286">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="5b475-286">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="5b475-287">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="5b475-287">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="5b475-288">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5b475-288">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b475-289">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="5b475-289">-RunAsAdministrator</span></span>

<span data-ttu-id="5b475-290">Указывает, что **сеанс PSSession** запускается от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5b475-290">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="5b475-291">-Session</span><span class="sxs-lookup"><span data-stu-id="5b475-291">-Session</span></span>

<span data-ttu-id="5b475-292">Указывает массив объектов **PSSession** , который используется этим командлетом в качестве модели для нового **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="5b475-292">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="5b475-293">Этот параметр создает новые объекты **PSSession** , имеющие те же свойства, что и указанные объекты **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5b475-293">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="5b475-294">Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` `Get-PSSession` команда или.</span><span class="sxs-lookup"><span data-stu-id="5b475-294">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="5b475-295">Итоговые объекты **PSSession** имеют те же имя компьютера, имя приложения, URI подключения, порт, имя конфигурации, предел регулирования и SSL (SSL) в качестве исходных значений, но имеют разные отображаемые имя, идентификатор и идентификатор экземпляра (GUID).</span><span class="sxs-lookup"><span data-stu-id="5b475-295">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

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

### <span data-ttu-id="5b475-296">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="5b475-296">-SessionOption</span></span>

<span data-ttu-id="5b475-297">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-297">Specifies advanced options for the session.</span></span> <span data-ttu-id="5b475-298">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-298">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="5b475-299">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="5b475-299">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="5b475-300">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-300">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="5b475-301">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-301">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="5b475-302">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-302">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="5b475-303">Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="5b475-303">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="5b475-304">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-304">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="5b475-305">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-305">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="5b475-306">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="5b475-306">-ThrottleLimit</span></span>

<span data-ttu-id="5b475-307">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="5b475-307">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="5b475-308">Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="5b475-308">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="5b475-309">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5b475-309">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b475-310">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="5b475-310">-UseSSL</span></span>

<span data-ttu-id="5b475-311">Указывает, что этот командлет использует протокол SSL для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="5b475-311">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="5b475-312">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="5b475-312">By default, SSL is not used.</span></span>

<span data-ttu-id="5b475-313">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="5b475-313">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="5b475-314">Параметр **UseSSL** обеспечивает дополнительную защиту, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="5b475-314">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="5b475-315">Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5b475-315">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="5b475-316">— VMId</span><span class="sxs-lookup"><span data-stu-id="5b475-316">-VMId</span></span>

<span data-ttu-id="5b475-317">Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="5b475-317">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="5b475-318">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="5b475-318">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="5b475-319">Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b475-319">To see the virtual machines that are available to you, use the following command:</span></span>

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

### <span data-ttu-id="5b475-320">-VMName</span><span class="sxs-lookup"><span data-stu-id="5b475-320">-VMName</span></span>

<span data-ttu-id="5b475-321">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="5b475-321">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="5b475-322">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="5b475-322">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="5b475-323">Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.</span><span class="sxs-lookup"><span data-stu-id="5b475-323">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

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

### <span data-ttu-id="5b475-324">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5b475-324">CommonParameters</span></span>

<span data-ttu-id="5b475-325">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b475-325">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b475-326">Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5b475-326">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5b475-327">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5b475-327">INPUTS</span></span>

### <span data-ttu-id="5b475-328">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-328">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="5b475-329">В этот командлет можно передать строку, URI или объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="5b475-329">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="5b475-330">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5b475-330">OUTPUTS</span></span>

### <span data-ttu-id="5b475-331">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-331">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="5b475-332">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5b475-332">NOTES</span></span>

- <span data-ttu-id="5b475-333">Этот командлет использует инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b475-333">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="5b475-334">Для использования этого командлета локальный компьютер и все удаленные компьютеры должны быть настроены для удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b475-334">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="5b475-335">Дополнительные сведения см. в разделе [about_Remote_Requirements](About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b475-335">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="5b475-336">Чтобы создать **сеанс PSSession** на локальном компьютере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5b475-336">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="5b475-337">По завершении работы с **PSSession** используйте `Remove-PSSession` командлет, чтобы удалить **сеанс PSSession** и освободить его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="5b475-337">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>

## <span data-ttu-id="5b475-338">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5b475-338">RELATED LINKS</span></span>

[<span data-ttu-id="5b475-339">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-339">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="5b475-340">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-340">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="5b475-341">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-341">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="5b475-342">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="5b475-342">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="5b475-343">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-343">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="5b475-344">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5b475-344">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="5b475-345">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-345">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="5b475-346">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="5b475-346">Remove-PSSession</span></span>](Remove-PSSession.md)

---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: d07942797bad3666a263e017fa8372e672936041
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605543"
---
# <span data-ttu-id="a0ef3-102">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="a0ef3-102">New-PSSessionOption</span></span>

## <span data-ttu-id="a0ef3-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a0ef3-103">SYNOPSIS</span></span>
<span data-ttu-id="a0ef3-104">Создает объект, содержащий дополнительные параметры для сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-104">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="a0ef3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0ef3-105">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="a0ef3-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0ef3-106">DESCRIPTION</span></span>

<span data-ttu-id="a0ef3-107">`New-PSSessionOption`Командлет создает объект, содержащий дополнительные параметры для управляемого пользователем сеанса (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-107">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session (**PSSession**).</span></span> <span data-ttu-id="a0ef3-108">Объект можно использовать в качестве значения параметра **SessionOption** командлетов, которые создают **сеанс PSSession**, например `New-PSSession` , `Enter-PSSession` и `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-108">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession**, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="a0ef3-109">Без параметров `New-PSSessionOption` создает объект, содержащий значения по умолчанию для всех параметров.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-109">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="a0ef3-110">Поскольку все свойства доступны для изменения, вы можете использовать итоговый объект в качестве шаблона и создавать стандартные объекты параметров для своей организации.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-110">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="a0ef3-111">Объект параметра сеанса также можно сохранить в `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-111">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="a0ef3-112">Значения этой переменной устанавливают новые значения по умолчанию для параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-112">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="a0ef3-113">Они действительны, если для сеанса не задано никаких параметров, и имеют приоритет над параметрами, заданными в конфигурации сеанса, однако их можно переопределить, указав параметры сеанса или объект параметров сеанса в командлете, создающем сеанс.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-113">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="a0ef3-114">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-114">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="a0ef3-115">При использовании объекта параметров сеанса в командлете, создающем сеанс, значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в привилегированной переменной $PSSessionOption и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-115">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="a0ef3-116">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-116">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="a0ef3-117">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="a0ef3-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="a0ef3-118">EXAMPLES</span></span>

### <span data-ttu-id="a0ef3-119">Пример 1. Создание параметра сеанса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a0ef3-119">Example 1: Create a default session option</span></span>

<span data-ttu-id="a0ef3-120">Эта команда создает объект параметра сеанса со всеми значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-120">This command creates a session option object that has all of the default values.</span></span>

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### <span data-ttu-id="a0ef3-121">Пример 2. Настройка сеанса с помощью объекта параметров сеанса</span><span class="sxs-lookup"><span data-stu-id="a0ef3-121">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="a0ef3-122">В этом примере показано, как использовать объект параметров сеанса для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-122">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="a0ef3-123">Первая команда создает новый объект параметра сеанса и сохраняет его в значении `$pso` переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-123">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="a0ef3-124">Вторая команда использует `New-PSSession` командлет для создания сеанса на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-124">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="a0ef3-125">Команда использует объект параметра сеанса в значении `$pso` переменной в качестве значения параметра **SessionOption** команды.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-125">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="a0ef3-126">Пример 3. Запуск интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="a0ef3-126">Example 3: Start an interactive session</span></span>

<span data-ttu-id="a0ef3-127">Эта команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-127">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="a0ef3-128">Значение параметра **SessionOption** — это `New-PSSessionOption` команда, которая имеет параметры WITH **ENCRYPTION** и **Compression** .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-128">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="a0ef3-129">`New-PSSessionOption`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед `Enter-PSSession` командой.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-129">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="a0ef3-130">Пример 4. изменение объекта параметров сеанса</span><span class="sxs-lookup"><span data-stu-id="a0ef3-130">Example 4: Modify a session option object</span></span>

<span data-ttu-id="a0ef3-131">В этом примере показано, как можно изменить объект параметра сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-131">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="a0ef3-132">Все свойства имеют значения для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-132">All properties have read/write values.</span></span>

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

<span data-ttu-id="a0ef3-133">Используйте этот метод для создания стандартного объекта сеанса в своей организации, а затем настраивайте отдельные его версии для определенных целей.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-133">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="a0ef3-134">Пример 5. Создание привилегированной переменной</span><span class="sxs-lookup"><span data-stu-id="a0ef3-134">Example 5: Create a preference variable</span></span>

<span data-ttu-id="a0ef3-135">Эта команда создает `$PSSessionOption` переменную предпочтений.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-135">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="a0ef3-136">Когда `$PSSessionOption` в сеансе происходит переменная предпочтений, она устанавливает значения по умолчанию для параметров в сеансах, созданных с помощью `New-PSSession` `Enter-PSSession` командлетов, и `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-136">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="a0ef3-137">Чтобы сделать `$PSSessionOption` переменную доступной во всех сеансах, добавьте ее в сеанс PowerShell и в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-137">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="a0ef3-138">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-138">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="a0ef3-139">Дополнительные сведения о профилях см. в разделе [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-139">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="a0ef3-140">Пример 6. соблюдение требований к конфигурации удаленного сеанса</span><span class="sxs-lookup"><span data-stu-id="a0ef3-140">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="a0ef3-141">В этом примере показано, как использовать объект **SessionOption** для удовлетворения требований, предъявляемых к конфигурации удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-141">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="a0ef3-142">Первая команда использует `New-PSSessionOption` командлет для создания объекта параметра сеанса со свойством **SkipCNCheck** .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-142">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="a0ef3-143">Команда сохраняет результирующий объект сеанса в `$skipCN` переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-143">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="a0ef3-144">Вторая команда использует `New-PSSession` командлет для создания нового сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-144">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="a0ef3-145">`$skipCN`Переменная Check используется в значении параметра **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-145">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="a0ef3-146">Так как компьютер идентифицируется по его IP-адресу, значение параметра **ComputerName** не соответствует ни одному из общих имен в сертификате, используемом для SSL (SSL).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-146">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="a0ef3-147">По этой причине параметр **SkipCNCheck** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-147">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="a0ef3-148">Пример 7. предоставление доступа к аргументам в удаленном сеансе</span><span class="sxs-lookup"><span data-stu-id="a0ef3-148">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="a0ef3-149">В этом примере показано, как использовать параметр **аппликатионаргументс** `New-PSSessionOption` командлета, чтобы сделать дополнительные данные доступными для удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-149">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

<span data-ttu-id="a0ef3-150">Первая команда создает хэш-таблицу с двумя ключами, **группой** и **использованием**.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-150">The first command creates a hash table with two keys, **Team** and **Use**.</span></span> <span data-ttu-id="a0ef3-151">Команда сохраняет хэш-таблицу в `$team` переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-151">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="a0ef3-152">Дополнительные сведения о хэш-таблицах см. [здесь](about/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-152">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="a0ef3-153">Затем `New-PSSessionOption` командлет, использующий параметр **аппликатионаргументс** , создает объект параметра сеанса, сохраненный в `$team` переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-153">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="a0ef3-154">При `New-PSSessionOption` создании объекта параметра сеанса он автоматически преобразует хэш-таблицу в значение параметра **аппликатионаргументс** в словарь примитива, чтобы данные могли быть надежно переданы в удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-154">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="a0ef3-155">`New-PSSession`Командлет запускает сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-155">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="a0ef3-156">Для включения параметров в переменную используется параметр **SessionOption** `$teamOption` .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-156">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="a0ef3-157">`Invoke-Command`Командлет показывает, что данные в `$team` переменной доступны командам в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-157">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="a0ef3-158">Данные отображаются в свойстве **аппликатионаргументс** `$PSSenderInfo` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-158">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="a0ef3-159">В последнем `Invoke-Command` показывается, как можно использовать данные.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-159">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="a0ef3-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0ef3-160">PARAMETERS</span></span>

### <span data-ttu-id="a0ef3-161">-Аппликатионаргументс</span><span class="sxs-lookup"><span data-stu-id="a0ef3-161">-ApplicationArguments</span></span>

<span data-ttu-id="a0ef3-162">Указывает словарь примитивов, отправляемый в удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-162">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="a0ef3-163">Команды и скрипты в удаленном сеансе, включая сценарии запуска в конфигурации сеанса, могут найти этот словарь в свойстве **аппликатионаргументс** `$PSSenderInfo` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-163">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="a0ef3-164">Этот параметр можно использовать для отправки данных в удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-164">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="a0ef3-165">Дополнительные сведения см. в разделе [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)и [about_Automatic_Variables](about/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-165">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-166">-Канцелтимеаут</span><span class="sxs-lookup"><span data-stu-id="a0ef3-166">-CancelTimeout</span></span>

<span data-ttu-id="a0ef3-167">Определяет, сколько времени PowerShell ожидает завершения операции отмены (CTRL + C), прежде чем ее завершить.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-167">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="a0ef3-168">Введите значение в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-168">Enter a value in milliseconds.</span></span>

<span data-ttu-id="a0ef3-169">Значение по умолчанию — 60 000 (одна минута).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-169">The default value is 60000 (one minute).</span></span> <span data-ttu-id="a0ef3-170">Значение 0 (ноль) означает отсутствие времени ожидания; команда будет продолжать выполняться неопределенно долго.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-170">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-171">-Culture</span><span class="sxs-lookup"><span data-stu-id="a0ef3-171">-Culture</span></span>

<span data-ttu-id="a0ef3-172">Указывает язык и региональные параметры, используемые для сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-172">Specifies the culture to use for the session.</span></span> <span data-ttu-id="a0ef3-173">Введите имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате (например `ja-JP` ,), переменную, которая содержит объект **CultureInfo** , или команду, которая получает объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-173">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="a0ef3-174">Значение по умолчанию — `$Null` , а язык и региональные параметры, заданные в операционной системе, используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-174">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-175">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="a0ef3-175">-IdleTimeout</span></span>

<span data-ttu-id="a0ef3-176">Определяет, как долго сеанс остается открытым, если удаленный компьютер не получает никаких сообщений от локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-176">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="a0ef3-177">Сюда входит сигнал пульса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-177">This includes the heartbeat signal.</span></span> <span data-ttu-id="a0ef3-178">По истечении этого времени сеанс закрывается.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-178">When the interval expires, the session closes.</span></span>

<span data-ttu-id="a0ef3-179">Значение времени ожидания простоя имеет значительную важность, если планируется отключение и повторное подключение к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-179">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="a0ef3-180">Повторно подключиться можно только в том случае, если не истекло время ожидания сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-180">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="a0ef3-181">Введите значение в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-181">Enter a value in milliseconds.</span></span> <span data-ttu-id="a0ef3-182">Минимальное значение — 60000 (1 минута).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-182">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="a0ef3-183">Максимальное значение задано свойством **MaxIdleTimeoutms** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-183">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="a0ef3-184">Значение по умолчанию-1 не задает время ожидания простоя.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-184">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="a0ef3-185">В сеансе используется время ожидания простоя, заданное в параметрах сеанса, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-185">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="a0ef3-186">Если значение не задано (-1), то в сеансе используется значение свойства **идлетимеаутмс** конфигурации сеанса или значение времени ожидания оболочки WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), в зависимости от того, какой из них является самым коротким.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-186">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="a0ef3-187">Если заданное в параметрах сеанса время ожидания простоя превышает значение свойства **MaxIdleTimeoutMs** в конфигурации сеанса, команда создания сеанса завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-187">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="a0ef3-188">Значение **идлетимеаутмс** для конфигурации сеанса **Microsoft. PowerShell** по умолчанию составляет 7200000 мс (2 часа).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-188">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="a0ef3-189">Его значение **максидлетимеаутмс** составляет 2147483647 миллисекунд ( \> 24 дня).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-189">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="a0ef3-190">Значение по умолчанию времени ожидания простоя оболочки WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) составляет 7200000 миллисекунд (2 часа).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-190">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="a0ef3-191">Значение времени ожидания простоя сеанса также может быть изменено при отключении от сеанса или при повторном подключении к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-191">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="a0ef3-192">Дополнительные сведения см. в разделах `Disconnect-PSSession` и `Connect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-192">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="a0ef3-193">В Windows PowerShell 2.0 значение по умолчанию для параметра **IdleTimeout** равно 240 000 (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-193">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-194">-Инклудепортинспн</span><span class="sxs-lookup"><span data-stu-id="a0ef3-194">-IncludePortInSPN</span></span>

<span data-ttu-id="a0ef3-195">Включает номер порта в имени участника-службы (SPN), используемый для проверки подлинности Kerberos, например `HTTP://<ComputerName>:5985` .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-195">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="a0ef3-196">Этот параметр позволяет клиенту, который использует имя субъекта-службы, отличное от значения по умолчанию, выполнять аутентификацию для удаленного компьютера, который использует аутентификацию Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-196">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="a0ef3-197">Параметр предназначен для организаций, где несколько служб, поддерживающих аутентификацию Kerberos, выполняются с использованием разных учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-197">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="a0ef3-198">Например, приложение IIS, которое разрешает проверку подлинности Kerberos, может потребовать регистрации имени субъекта-службы по умолчанию для учетной записи пользователя, которая отличается от учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-198">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="a0ef3-199">В таких случаях удаленное взаимодействие PowerShell не может использовать Kerberos для проверки подлинности, так как для этого требуется имя участника-службы, зарегистрированное в учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-199">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="a0ef3-200">Чтобы устранить эту проблему, администраторы могут создавать разные имена участников-служб, например с помощью **Setspn.exe**, которые зарегистрированы для разных учетных записей пользователей, и могут различать их путем включения номера порта в имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-200">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe**, that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="a0ef3-201">Дополнительные сведения см. в разделе [Обзор SetSPN](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-201">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="a0ef3-202">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a0ef3-203">-Максконнектионретрикаунт</span><span class="sxs-lookup"><span data-stu-id="a0ef3-203">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="a0ef3-204">Указывает, сколько раз PowerShell пытается установить подключение к целевому компьютеру, если текущая попытка не удалась из-за проблем с сетью.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-204">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="a0ef3-205">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-205">The default value is 5.</span></span>

<span data-ttu-id="a0ef3-206">Этот параметр был добавлен для PowerShell версии 5,0.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-206">This parameter was added for PowerShell version 5.0.</span></span>

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

### <span data-ttu-id="a0ef3-207">-Максимумрецеиведдатасизеперкомманд</span><span class="sxs-lookup"><span data-stu-id="a0ef3-207">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="a0ef3-208">Указывает максимальное число байтов, которые может получить локальный компьютер с удаленного компьютера в рамках одной команды.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-208">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="a0ef3-209">Введите значение в байтах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-209">Enter a value in bytes.</span></span> <span data-ttu-id="a0ef3-210">По умолчанию ограничения размера данных отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-210">By default, there is no data size limit.</span></span>

<span data-ttu-id="a0ef3-211">Этот параметр предназначен для защиты ресурсов на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-211">This option is designed to protect the resources on the client computer.</span></span>

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

### <span data-ttu-id="a0ef3-212">-Максимумрецеиведобжектсизе</span><span class="sxs-lookup"><span data-stu-id="a0ef3-212">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="a0ef3-213">Указывает максимальный размер объекта, который может получить локальный компьютер с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-213">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="a0ef3-214">Этот параметр предназначен для защиты ресурсов на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-214">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="a0ef3-215">Введите значение в байтах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-215">Enter a value in bytes.</span></span>

<span data-ttu-id="a0ef3-216">Если пропустить этот параметр в Windows PowerShell 2.0, ограничение на размер объекта не действует.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-216">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="a0ef3-217">Начиная с Windows PowerShell 3.0, при отсутствии этого параметра применяется значение по умолчанию — 200 МБ.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-217">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-218">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="a0ef3-218">-MaximumRedirection</span></span>

<span data-ttu-id="a0ef3-219">Определяет, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-219">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="a0ef3-220">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-220">The default value is 5.</span></span> <span data-ttu-id="a0ef3-221">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-221">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="a0ef3-222">Этот параметр используется в сеансе только в том случае, если параметр **AllowRedirection** используется в команде, которая создает сеанс.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-222">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-223">-Уплотнение</span><span class="sxs-lookup"><span data-stu-id="a0ef3-223">-NoCompression</span></span>

<span data-ttu-id="a0ef3-224">Отключает сжатие пакетов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-224">Turns off packet compression in the session.</span></span> <span data-ttu-id="a0ef3-225">Сжатие требует большего числа рабочих циклов процессора, но ускоряет передачу.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-225">Compression uses more processor cycles, but it makes transmission faster.</span></span>

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

### <span data-ttu-id="a0ef3-226">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="a0ef3-226">-NoEncryption</span></span>

<span data-ttu-id="a0ef3-227">Отключает шифрование данных.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-227">Turns off data encryption.</span></span>

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

### <span data-ttu-id="a0ef3-228">-Номачинепрофиле</span><span class="sxs-lookup"><span data-stu-id="a0ef3-228">-NoMachineProfile</span></span>

<span data-ttu-id="a0ef3-229">Запрещает загрузку профиля пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-229">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="a0ef3-230">В результате сеанс может создаваться быстрее, но в нем будут недоступны параметры реестра для конкретного пользователя, элементы, такие как переменные среды, и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-230">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

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

### <span data-ttu-id="a0ef3-231">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="a0ef3-231">-OpenTimeout</span></span>

<span data-ttu-id="a0ef3-232">Определяет время ожидания клиентского компьютера при установлении соединения сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-232">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="a0ef3-233">По истечении периода команда для установления соединения завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-233">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="a0ef3-234">Введите значение в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-234">Enter a value in milliseconds.</span></span>

<span data-ttu-id="a0ef3-235">Значение по умолчанию — 180 000 (3 минуты).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-235">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="a0ef3-236">Значение 0 (ноль) означает отсутствие времени ожидания; команда будет продолжать выполняться неопределенно долго.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-236">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-237">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="a0ef3-237">-OperationTimeout</span></span>

<span data-ttu-id="a0ef3-238">Определяет максимальное время выполнения любой операции в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-238">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="a0ef3-239">По истечении периода операция завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-239">When the interval expires, the operation fails.</span></span> <span data-ttu-id="a0ef3-240">Введите значение в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-240">Enter a value in milliseconds.</span></span>

<span data-ttu-id="a0ef3-241">Значение по умолчанию — 180 000 (3 минуты).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-241">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="a0ef3-242">Значение 0 (ноль) означает отсутствие времени ожидания; операция будет продолжать выполняться неопределенно долго.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-242">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-243">-Аутпутбуфферингмоде</span><span class="sxs-lookup"><span data-stu-id="a0ef3-243">-OutputBufferingMode</span></span>

<span data-ttu-id="a0ef3-244">Определяет порядок управления выходным потоком команды в отключенных сеансах при заполнении .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-244">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="a0ef3-245">Если в сеансе или его конфигурации не задан режим буферизации выходных данных, используется значение по умолчанию **Block**.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-245">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block**.</span></span> <span data-ttu-id="a0ef3-246">Пользователи также могут изменять режим буферизации выходных данных при отключении сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-246">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="a0ef3-247">Если этот параметр не задан, значение параметра **аутпутбуфферингмоде** объекта параметра Session не равно None.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-247">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="a0ef3-248">Значение **Block** или **Drop** переопределяет параметр режим буферизации выходных данных, заданный в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-248">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="a0ef3-249">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a0ef3-249">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a0ef3-250">Блокировка.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-250">Block.</span></span> <span data-ttu-id="a0ef3-251">при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-251">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="a0ef3-252">Drop.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-252">Drop.</span></span> <span data-ttu-id="a0ef3-253">при заполнении выходного буфера выполнение команды продолжается.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-253">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="a0ef3-254">Новые выходные данные сохраняются вместо наиболее старых.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-254">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="a0ef3-255">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-255">None.</span></span> <span data-ttu-id="a0ef3-256">порядок действий в случае переполнения выходного буфера не установлен.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-256">No output buffering mode is specified.</span></span>

<span data-ttu-id="a0ef3-257">Дополнительные сведения о параметре транспорта режим буферизации вывода см. в разделе `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-257">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="a0ef3-258">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-259">-Проксякцесстипе</span><span class="sxs-lookup"><span data-stu-id="a0ef3-259">-ProxyAccessType</span></span>

<span data-ttu-id="a0ef3-260">Определяет, какой механизм используется для разрешения имени узла.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-260">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="a0ef3-261">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a0ef3-261">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a0ef3-262">иеконфиг</span><span class="sxs-lookup"><span data-stu-id="a0ef3-262">IEConfig</span></span>
- <span data-ttu-id="a0ef3-263">винхттпконфиг</span><span class="sxs-lookup"><span data-stu-id="a0ef3-263">WinHttpConfig</span></span>
- <span data-ttu-id="a0ef3-264">AutoDetect</span><span class="sxs-lookup"><span data-stu-id="a0ef3-264">AutoDetect</span></span>
- <span data-ttu-id="a0ef3-265">нопроксисервер</span><span class="sxs-lookup"><span data-stu-id="a0ef3-265">NoProxyServer</span></span>
- <span data-ttu-id="a0ef3-266">None</span><span class="sxs-lookup"><span data-stu-id="a0ef3-266">None</span></span>

<span data-ttu-id="a0ef3-267">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-267">The default value is None.</span></span>

<span data-ttu-id="a0ef3-268">Сведения о значениях этого параметра см. в разделе [Проксякцесстипе enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-268">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span></span>

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-269">-Проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="a0ef3-269">-ProxyAuthentication</span></span>

<span data-ttu-id="a0ef3-270">Задает метод аутентификации, используемый для разрешения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-270">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="a0ef3-271">Допустимые значения для этого параметра: **Basic**, **Digest** и **Negotiate**.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-271">The acceptable values for this parameter are: **Basic**, **Digest**, and **Negotiate**.</span></span> <span data-ttu-id="a0ef3-272">Значение по умолчанию — **Negotiate**.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-272">The default value is **Negotiate**.</span></span>

<span data-ttu-id="a0ef3-273">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-273">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-274">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="a0ef3-274">-ProxyCredential</span></span>

<span data-ttu-id="a0ef3-275">Задает учетные данные, используемые для аутентификации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-275">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="a0ef3-276">Введите переменную, содержащую объект **PSCredential** , или команду, которая получает объект **PSCredential** , например `Get-Credential` команду.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-276">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="a0ef3-277">Если этот параметр не установлен, учетные данные не заданы.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-277">If this option is not set, no credentials are specified.</span></span>

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

### <span data-ttu-id="a0ef3-278">-Скипкачекк</span><span class="sxs-lookup"><span data-stu-id="a0ef3-278">-SkipCACheck</span></span>

<span data-ttu-id="a0ef3-279">Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-279">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="a0ef3-280">Используйте этот параметр только в том случае, если имеются другие основания считать удаленный компьютер доверенным, например, если он входит в состав физически защищенной и изолированной сети либо указан в качестве доверенного узла в конфигурации службы удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-280">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="a0ef3-281">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="a0ef3-281">-SkipCNCheck</span></span>

<span data-ttu-id="a0ef3-282">Указывает, что общее имя сертификата (CN) сервера не обязательно должен совпадать с именем узла сервера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-282">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="a0ef3-283">Этот параметр используется только для удаленных операций, использующих протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-283">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="a0ef3-284">Используйте этот параметр только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-284">Use this option only for trusted computers.</span></span>

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

### <span data-ttu-id="a0ef3-285">-Скипревокатиончекк</span><span class="sxs-lookup"><span data-stu-id="a0ef3-285">-SkipRevocationCheck</span></span>

<span data-ttu-id="a0ef3-286">Не проверяет состояние отзыва сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-286">Does not validate the revocation status of the server certificate.</span></span>

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

### <span data-ttu-id="a0ef3-287">-UICulture</span><span class="sxs-lookup"><span data-stu-id="a0ef3-287">-UICulture</span></span>

<span data-ttu-id="a0ef3-288">Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-288">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="a0ef3-289">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a0ef3-289">Valid values include:</span></span>

- <span data-ttu-id="a0ef3-290">Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="a0ef3-290">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="a0ef3-291">Переменная, содержащая объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="a0ef3-291">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="a0ef3-292">Команда, которая получает объект **CultureInfo** , например `Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="a0ef3-292">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="a0ef3-293">Значение по умолчанию — `$null` , а язык и региональные параметры пользовательского интерфейса, заданные в операционной системе при создании сеанса, используются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-293">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0ef3-294">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="a0ef3-294">-UseUTF16</span></span>

<span data-ttu-id="a0ef3-295">Указывает, что этот командлет кодирует запрос в формате UTF16, а не в формате UTF8.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-295">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="a0ef3-296">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a0ef3-296">CommonParameters</span></span>

<span data-ttu-id="a0ef3-297">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0ef3-298">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0ef3-299">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a0ef3-299">INPUTS</span></span>

### <span data-ttu-id="a0ef3-300">None</span><span class="sxs-lookup"><span data-stu-id="a0ef3-300">None</span></span>

<span data-ttu-id="a0ef3-301">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-301">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a0ef3-302">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a0ef3-302">OUTPUTS</span></span>

### <span data-ttu-id="a0ef3-303">System. Management. Automation. Remoting. PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="a0ef3-303">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="a0ef3-304">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a0ef3-304">NOTES</span></span>

<span data-ttu-id="a0ef3-305">Если параметр **SessionOption** не используется в команде для создания **PSSession**, параметры сеанса определяются значениями свойств `$PSSessionOption` привилегированной переменной, если они заданы.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-305">If the **SessionOption** parameter is not used in a command to create a **PSSession**, the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="a0ef3-306">Дополнительные сведения о `$PSSessionOption` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef3-306">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="a0ef3-307">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="a0ef3-308">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="a0ef3-309">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a0ef3-309">RELATED LINKS</span></span>

[<span data-ttu-id="a0ef3-310">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a0ef3-310">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="a0ef3-311">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a0ef3-311">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a0ef3-312">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a0ef3-312">New-PSSession</span></span>](New-PSSession.md)

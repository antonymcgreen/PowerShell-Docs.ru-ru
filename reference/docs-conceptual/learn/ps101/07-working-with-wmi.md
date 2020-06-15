---
title: Использование инструментария WMI
description: PowerShell поставляется с командлетами для работы с инструментарием WMI с момента выпуска.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 243685efa1f976ddb46a0d0efc4ed0635844606d
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438295"
---
# <a name="chapter-7---working-with-wmi"></a><span data-ttu-id="76965-103">Глава 7. Использование инструментария WMI</span><span class="sxs-lookup"><span data-stu-id="76965-103">Chapter 7 - Working with WMI</span></span>

## <a name="wmi-and-cim"></a><span data-ttu-id="76965-104">Инструментарий WMI и CIM</span><span class="sxs-lookup"><span data-stu-id="76965-104">WMI and CIM</span></span>

<span data-ttu-id="76965-105">По умолчанию PowerShell поставляется с командлетами для использования вместе с другими технологиями, такими как инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="76965-105">PowerShell ships by default with cmdlets for working with other technologies such as Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="76965-106">Существует несколько собственных командлетов WMI, которые используются в PowerShell без необходимости установки дополнительного программного обеспечения или модулей.</span><span class="sxs-lookup"><span data-stu-id="76965-106">There are several native WMI cmdlets that exist in PowerShell without having to install any additional software or modules.</span></span>

<span data-ttu-id="76965-107">PowerShell поставляется с командлетами для работы с инструментарием WMI с момента выпуска.</span><span class="sxs-lookup"><span data-stu-id="76965-107">PowerShell has had cmdlets for working with WMI since the beginning.</span></span> <span data-ttu-id="76965-108">`Get-Command` можно использовать для определения командлетов WMI, существующих в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76965-108">`Get-Command` can be used to determine what WMI cmdlets exist in PowerShell.</span></span> <span data-ttu-id="76965-109">Приведенные ниже результаты получены на моем компьютере с Windows 10 в лабораторной среде под управлением PowerShell версии 5.1.</span><span class="sxs-lookup"><span data-stu-id="76965-109">The following results are from my Windows 10 lab environment computer that is running PowerShell version 5.1.</span></span> <span data-ttu-id="76965-110">Ваши результаты могут отличаться в зависимости от используемой версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76965-110">Your results may differ depending on what PowerShell version you're running.</span></span>

```powershell
Get-Command -Noun WMI*
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-WmiObject                                      3.1.0.0    Microsof...
Cmdlet          Invoke-WmiMethod                                   3.1.0.0    Microsof...
Cmdlet          Register-WmiEvent                                  3.1.0.0    Microsof...
Cmdlet          Remove-WmiObject                                   3.1.0.0    Microsof...
Cmdlet          Set-WmiInstance                                    3.1.0.0    Microsof...
```

<span data-ttu-id="76965-111">Командлеты модели CIM появились в PowerShell версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="76965-111">Common Information Model (CIM) cmdlets were introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="76965-112">Командлеты CIM разработаны так, чтобы их можно было использовать на компьютерах под управлением Windows и других ОС.</span><span class="sxs-lookup"><span data-stu-id="76965-112">The CIM cmdlets are designed so they can be used on both Windows and non-Windows machines.</span></span> <span data-ttu-id="76965-113">Командлеты WMI являются устаревшими, поэтому вместо них рекомендуется использовать командлеты CIM.</span><span class="sxs-lookup"><span data-stu-id="76965-113">The WMI cmdlets are deprecated so my recommendation is to use the CIM cmdlets instead of the older WMI ones.</span></span>

<span data-ttu-id="76965-114">Все командлеты CIM содержатся в модуле.</span><span class="sxs-lookup"><span data-stu-id="76965-114">The CIM cmdlets are all contained within a module.</span></span> <span data-ttu-id="76965-115">Чтобы получить список командлетов CIM, используйте `Get-Command` вместе с параметром **Module**, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="76965-115">To obtain a list of the CIM cmdlets, use `Get-Command` with the **Module** parameter as shown in the following example.</span></span>

```powershell
Get-Command -Module CimCmdlets
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Export-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Get-CimAssociatedInstance                          1.0.0.0    CimCmdlets
Cmdlet          Get-CimClass                                       1.0.0.0    CimCmdlets
Cmdlet          Get-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Get-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          Import-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Invoke-CimMethod                                   1.0.0.0    CimCmdlets
Cmdlet          New-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          New-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          New-CimSessionOption                               1.0.0.0    CimCmdlets
Cmdlet          Register-CimIndicationEvent                        1.0.0.0    CimCmdlets
Cmdlet          Remove-CimInstance                                 1.0.0.0    CimCmdlets
Cmdlet          Remove-CimSession                                  1.0.0.0    CimCmdlets
Cmdlet          Set-CimInstance                                    1.0.0.0    CimCmdlets
```

<span data-ttu-id="76965-116">Как и раньше, командлеты CIM позволяют вам работать с WMI, поэтому не путайтесь, если кто-то пытается выполнить запрос WMI с помощью командлетов CIM PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76965-116">The CIM cmdlets still allow you to work with WMI so don't be confused when someone makes the statement "When I query WMI with the PowerShell CIM cmdlets..."</span></span>

<span data-ttu-id="76965-117">Как я уже говорил, WMI — это отдельная технология в PowerShell, поэтому вы просто используете командлеты CIM для доступа к WMI.</span><span class="sxs-lookup"><span data-stu-id="76965-117">As I previously mentioned, WMI is a separate technology from PowerShell and you're just using the CIM cmdlets for accessing WMI.</span></span> <span data-ttu-id="76965-118">Вы можете найти прежний сценарий VBScript, в котором используется язык запросов WMI (WQL), позволяющий выполнить запрос WMI, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="76965-118">You may find an old VBScript that uses WMI Query Language (WQL) to query WMI such as in the following example.</span></span>

```vb
strComputer = "."
Set objWMIService = GetObject("winmgmts:" _
    & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\cimv2")

Set colBIOS = objWMIService.ExecQuery _
    ("Select * from Win32_BIOS")

For each objBIOS in colBIOS
    Wscript.Echo "Manufacturer: " & objBIOS.Manufacturer
    Wscript.Echo "Name: " & objBIOS.Name
    Wscript.Echo "Serial Number: " & objBIOS.SerialNumber
    Wscript.Echo "SMBIOS Version: " & objBIOS.SMBIOSBIOSVersion
    Wscript.Echo "Version: " & objBIOS.Version
Next
```

<span data-ttu-id="76965-119">Вы можете взять WQL-запрос из сценария VBScript и использовать его с командлетом `Get-CimInstance` без изменений.</span><span class="sxs-lookup"><span data-stu-id="76965-119">You can take the WQL query from that VBScript and use it with the `Get-CimInstance` cmdlet without any modifications.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_BIOS'
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="76965-120">Это не тот способ, который я стандартно использую для запроса WMI с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76965-120">That's not how I typically query WMI with PowerShell.</span></span> <span data-ttu-id="76965-121">Но он действительно работает, позволяя легко перенести существующие сценарии VBScript в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76965-121">But it does work and allows you to easily migrate existing VBScripts to PowerShell.</span></span> <span data-ttu-id="76965-122">При внесении скрипта из одной строки для запроса WMI я использую следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="76965-122">When I start out writing a one-liner to query WMI, I use the following syntax.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="76965-123">Если нужно указать только серийный номер, я могу передать выходные данные в `Select-Object` и указать только свойство **SerialNumber**.</span><span class="sxs-lookup"><span data-stu-id="76965-123">If I only want the serial number, I can pipe the output to `Select-Object` and specify only the **SerialNumber** property.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS | Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="76965-124">По умолчанию существуют несколько свойств, извлекающихся в фоновом режиме, который никогда не используется.</span><span class="sxs-lookup"><span data-stu-id="76965-124">By default, there are several properties that are retrieved behind the scenes that are never used.</span></span>
<span data-ttu-id="76965-125">Это действие не важно, если запрос инструментария WMI выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76965-125">It may not matter much when querying WMI on the local computer.</span></span> <span data-ttu-id="76965-126">Но когда вы приступаете к выполнению запросов с удаленных компьютеров, оно позволяет не только увеличить время обработки для возврата информации, но и получить по сети дополнительные ненужные данные.</span><span class="sxs-lookup"><span data-stu-id="76965-126">But once you start querying remote computers, it's not only additional processing time to return that information, but also additional unnecessary information to have to pull across the network.</span></span> <span data-ttu-id="76965-127">`Get-CimInstance` содержит параметр **Property**, который ограничивает извлекаемые данные.</span><span class="sxs-lookup"><span data-stu-id="76965-127">`Get-CimInstance` has a **Property** parameter that limits the information that's retrieved.</span></span> <span data-ttu-id="76965-128">Это действие позволяет выполнять запрос к инструментарию WMI более эффективно.</span><span class="sxs-lookup"><span data-stu-id="76965-128">This makes the query to WMI more efficient.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="76965-129">Предыдущие результаты вернули объект.</span><span class="sxs-lookup"><span data-stu-id="76965-129">The previous results returned an object.</span></span> <span data-ttu-id="76965-130">Для возврата простой строки используйте параметр **ExpandProperty**.</span><span class="sxs-lookup"><span data-stu-id="76965-130">To return a simple string, use the **ExpandProperty** parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -ExpandProperty SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="76965-131">Также для этого вы можете использовать пунктирный стиль синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="76965-131">You could also use the dotted style of syntax to return a simple string.</span></span> <span data-ttu-id="76965-132">Это избавляет от необходимости передавать простую строку в `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="76965-132">This eliminates the need to pipe to `Select-Object`.</span></span>

```powershell
(Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber).SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

## <a name="query-remote-computers-with-the-cim-cmdlets"></a><span data-ttu-id="76965-133">Запрос с удаленных компьютеров с помощью командлетов CIM</span><span class="sxs-lookup"><span data-stu-id="76965-133">Query Remote Computers with the CIM cmdlets</span></span>

<span data-ttu-id="76965-134">Я использую PowerShell от имени локального администратора, который является пользователем домена.</span><span class="sxs-lookup"><span data-stu-id="76965-134">I'm still running PowerShell as a local admin who is a domain user.</span></span> <span data-ttu-id="76965-135">При попытке запросить данные с удаленного компьютера с помощью командлета `Get-CimInstance` появляется сообщение об ошибке с отказом в доступе.</span><span class="sxs-lookup"><span data-stu-id="76965-135">When I try to query information from a remote computer using the `Get-CimInstance` cmdlet, I receive an access denied error message.</span></span>

```powershell
Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
```

```Output
Get-CimInstance : Access is denied.
At line:1 char:1
+ Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
+ ``````````````````````````````````````````````````````~~
    + CategoryInfo          : PermissionDenied: (root\cimv2:Win32_BIOS:String) [Get-CimI
   nstance], CimException
    + FullyQualifiedErrorId : HRESULT 0x80070005,Microsoft.Management.Infrastructure.Cim
   Cmdlets.GetCimInstanceCommand
    + PSComputerName        : dc01
```

<span data-ttu-id="76965-136">Когда речь идет о PowerShell, многие люди сталкиваются с проблемами безопасности, но дело в том, что вы имеете точно такие же разрешения в PowerShell, как и в графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="76965-136">Many people have security concerns when it comes to PowerShell, but the truth is you have exactly the same permissions in PowerShell as you do in the GUI.</span></span> <span data-ttu-id="76965-137">Ни больше ни меньше.</span><span class="sxs-lookup"><span data-stu-id="76965-137">No more and no less.</span></span> <span data-ttu-id="76965-138">Из предыдущего примера видно, что пользователь, запускающий PowerShell, не имеет прав на выполнение запроса WMI с сервера DC01.</span><span class="sxs-lookup"><span data-stu-id="76965-138">The problem in the previous example is that the user running PowerShell doesn't have rights to query WMI information from the DC01 server.</span></span> <span data-ttu-id="76965-139">Я могу повторно запустить PowerShell от имени администратора домена, так как `Get-CimInstance` не содержит параметр **Credential**.</span><span class="sxs-lookup"><span data-stu-id="76965-139">I could relaunch PowerShell as a domain administrator since `Get-CimInstance` doesn't have a **Credential** parameter.</span></span> <span data-ttu-id="76965-140">Но это не совсем удобно, так как потом любая открытая в PowerShell программа будет запускаться с правами администратора домена. С точки зрения безопасности это действие может быть рискованным в зависимости от ситуации.</span><span class="sxs-lookup"><span data-stu-id="76965-140">But, trust me, that isn't a good idea because then anything that I run from PowerShell would be running as a domain admin. That could be dangerous from a security standpoint depending on the situation.</span></span>

<span data-ttu-id="76965-141">Используя принцип предоставления наименьших прав, я буду повышать уровень прав учетной записи администратора домена для каждой команды с помощью параметра **Credential**, если команда будет содержать такой же параметр.</span><span class="sxs-lookup"><span data-stu-id="76965-141">Using the principle of least privilege, I elevate to my domain admin account on a per command basis using the **Credential** parameter, if a command has one.</span></span> <span data-ttu-id="76965-142">`Get-CimInstance` не содержит параметр **Credential**, поэтому решение для этого сценария заключается в том, чтобы сначала создать параметр **CimSession**.</span><span class="sxs-lookup"><span data-stu-id="76965-142">`Get-CimInstance` doesn't have a **Credential** parameter so the solution in this scenario is to create a **CimSession** first.</span></span> <span data-ttu-id="76965-143">Затем я использую параметр **CimSession** для запроса WMI на удаленном компьютере вместо имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="76965-143">Then I use the **CimSession** instead of a computer name to query WMI on the remote computer.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName dc01 -Credential (Get-Credential)
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="76965-144">Сеанс CIM сохранился в переменной с именем `$CimSession`.</span><span class="sxs-lookup"><span data-stu-id="76965-144">The CIM session was stored in a variable named `$CimSession`.</span></span> <span data-ttu-id="76965-145">Заметьте, что командлет `Get-Credential` я указываю также в круглых скобках, которые позволяют выполнить его первым, предлагая мне ввести альтернативные учетные данные перед созданием нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="76965-145">Notice that I also specified the `Get-Credential` cmdlet in parentheses so that it executes first, prompting me for alternate credentials, before creating the new session.</span></span> <span data-ttu-id="76965-146">Позже при рассмотрении этой главы я покажу вам более эффективный способ указывать альтернативные учетные данные, а пока важно усвоить основной принцип, чтобы потом уметь разбираться с более сложными понятиями.</span><span class="sxs-lookup"><span data-stu-id="76965-146">I'll show you another more efficient way to specify alternate credentials later in this chapter, but it's important to understand this basic concept before making it more complicated.</span></span>

<span data-ttu-id="76965-147">Сеанс CIM, созданный в предыдущем примере, теперь можно использовать с командлетом `Get-CimInstance` для запроса информации BIOS из инструментария WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76965-147">The CIM session created in the previous example can now be used with the `Get-CimInstance` cmdlet to query the BIOS information from WMI on the remote computer.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01
```

<span data-ttu-id="76965-148">Использование сеансов CIM вместо ввода имени компьютера дает несколько дополнительных преимуществ.</span><span class="sxs-lookup"><span data-stu-id="76965-148">There are several additional benefits to using CIM sessions instead of just specifying a computer name.</span></span> <span data-ttu-id="76965-149">При выполнении нескольких запросов к одному и тому же компьютеру использовать сеанс CIM более эффективно, чем вводить имя компьютера для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="76965-149">When running multiple queries to the same computer, using a CIM session is more efficient than using the computer name for each query.</span></span> <span data-ttu-id="76965-150">При создании сеанса CIM соединение настраивается только один раз.</span><span class="sxs-lookup"><span data-stu-id="76965-150">Creating a CIM session only sets up the connection once.</span></span>
<span data-ttu-id="76965-151">Затем несколько запросов используют этот же сеанс для получения информации.</span><span class="sxs-lookup"><span data-stu-id="76965-151">Then, multiple queries use that same session to retrieve information.</span></span> <span data-ttu-id="76965-152">При использовании имени компьютера необходимы командлеты для установки и разрыва соединения с каждым отдельным запросом.</span><span class="sxs-lookup"><span data-stu-id="76965-152">Using the computer name requires the cmdlets to set up and tear down the connection with each individual query.</span></span>

<span data-ttu-id="76965-153">Командлет `Get-CimInstance` по умолчанию использует протокол WSMan, то есть для подключения к удаленному компьютеру необходимо иметь PowerShell версии 3.0 или выше.</span><span class="sxs-lookup"><span data-stu-id="76965-153">The `Get-CimInstance` cmdlet uses the WSMan protocol by default, which means the remote computer needs PowerShell version 3.0 or higher to connect.</span></span> <span data-ttu-id="76965-154">По сути, важна не версия PowerShell, а версия стека.</span><span class="sxs-lookup"><span data-stu-id="76965-154">It's actually not the PowerShell version that matters, it's the stack version.</span></span> <span data-ttu-id="76965-155">Версию стека можно определить с помощью командлета `Test-WSMan`.</span><span class="sxs-lookup"><span data-stu-id="76965-155">The stack version can be determined using the `Test-WSMan` cmdlet.</span></span>
<span data-ttu-id="76965-156">Стек должен быть версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="76965-156">It needs to be version 3.0.</span></span> <span data-ttu-id="76965-157">Эту версию можно найти с помощью PowerShell версии 3.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="76965-157">That's the version you'll find with PowerShell version 3.0 and higher.</span></span>

```powershell
Test-WSMan -ComputerName dc01
```

```Output
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd
ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd
ProductVendor   : Microsoft Corporation
ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 3.0
```

<span data-ttu-id="76965-158">Прежние командлеты WMI используют протокол DCOM, совместимый с более старыми версиями Windows.</span><span class="sxs-lookup"><span data-stu-id="76965-158">The older WMI cmdlets use the DCOM protocol, which is compatible with older versions of Windows.</span></span> <span data-ttu-id="76965-159">Но в новых версиях Windows протокол DCOM обычно блокируется брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="76965-159">But DCOM is typically blocked by the firewall on newer versions of Windows.</span></span> <span data-ttu-id="76965-160">Командлет `New-CimSessionOption` позволяет создать подключение протокола DCOM для использования вместе с `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="76965-160">The `New-CimSessionOption` cmdlet allows you to create a DCOM protocol connection for use with `New-CimSession`.</span></span> <span data-ttu-id="76965-161">Это позволяет использовать командлет `Get-CimInstance` для взаимодействия с такими же старыми версиями Windows, как и у Windows Server 2000.</span><span class="sxs-lookup"><span data-stu-id="76965-161">This allows the `Get-CimInstance` cmdlet to be used to communicate with versions of Windows as old as Windows Server 2000.</span></span> <span data-ttu-id="76965-162">Кроме того, это значит, что установка PowerShell не требуется на удаленном компьютере при использовании командлета `Get-CimInstance` с параметром CimSession, который настроен для использования протокола DCOM.</span><span class="sxs-lookup"><span data-stu-id="76965-162">This also means that PowerShell is not required on the remote computer when using the `Get-CimInstance` cmdlet with a CimSession that's configured to use the DCOM protocol.</span></span>

<span data-ttu-id="76965-163">Создайте параметр протокола DCOM с помощью командлета `New-CimSessionOption` и сохраните его в переменной.</span><span class="sxs-lookup"><span data-stu-id="76965-163">Create the DCOM protocol option using the `New-CimSessionOption` cmdlet and store it in a variable.</span></span>

```powershell
$DCOM = New-CimSessionOption -Protocol Dcom
```

<span data-ttu-id="76965-164">Для удобства вы можете сохранить в переменной свои учетные данные администратора домена или учетные данные с повышенными правами, чтобы постоянно не вводить их для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="76965-164">For efficiency, you can store your domain administrator or elevated credentials in a variable so you don't have to constantly enter them for each command.</span></span>

```powershell
$Cred = Get-Credential
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="76965-165">Я использую сервер SQL03 по управлением Windows Server 2008 (без R2).</span><span class="sxs-lookup"><span data-stu-id="76965-165">I have a server named SQL03 that runs Windows Server 2008 (non-R2).</span></span> <span data-ttu-id="76965-166">Это новейшая операционная система Windows Server, на которой средство PowerShell по умолчанию не установлено.</span><span class="sxs-lookup"><span data-stu-id="76965-166">It's the newest Windows Server operating system that doesn't have PowerShell installed by default.</span></span>

<span data-ttu-id="76965-167">Создайте параметр **CimSession** на сервере SQL03, используя протокол DCOM.</span><span class="sxs-lookup"><span data-stu-id="76965-167">Create a **CimSession** to SQL03 using the DCOM protocol.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName sql03 -SessionOption $DCOM -Credential $Cred
```

<span data-ttu-id="76965-168">Заметьте, что в предыдущем примере я указал в этот раз переменную с именем `$Cred` в качестве значения параметра **Credential**, а не вводил ее вручную.</span><span class="sxs-lookup"><span data-stu-id="76965-168">Notice in the previous command, this time I specified the variable named `$Cred` as the value for the **Credential** parameter instead of having to enter them manually again.</span></span>

<span data-ttu-id="76965-169">Выходные данные запроса одинаковые, независимо от используемого базового протокола.</span><span class="sxs-lookup"><span data-stu-id="76965-169">The output of the query is the same regardless of the underlying protocol being used.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="76965-170">Командлет `Get-CimSession` используется для просмотра подключенных в данный момент параметров **CimSession**, а также используемых ими протоколов.</span><span class="sxs-lookup"><span data-stu-id="76965-170">The `Get-CimSession` cmdlet is used to see what **CimSessions** are currently connected and what protocols they're using.</span></span>

```powershell
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : 80742787-e38e-41b1-a7d7-fa1369cf1402
ComputerName : dc01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : 8fcabd81-43cf-4682-bd53-ccce1e24aecb
ComputerName : sql03
Protocol     : DCOM
```

<span data-ttu-id="76965-171">Получите и сохраните оба ранее созданных параметра **CimSession** в переменной с именем `$CimSession`.</span><span class="sxs-lookup"><span data-stu-id="76965-171">Retrieve and store both of the previously created **CimSessions** in a variable named `$CimSession`.</span></span>

```powershell
$CimSession = Get-CimSession
```

<span data-ttu-id="76965-172">Отправьте запрос с обоих компьютеров с помощью одной команды, при этом на первом должен использоваться протокол WSMan, а на втором — DCOM.</span><span class="sxs-lookup"><span data-stu-id="76965-172">Query both of the computers with one command, one using the WSMan protocol and the other one with DCOM.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01

SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="76965-173">Я написал несколько статей в блогах о командлетах WMI и CIM.</span><span class="sxs-lookup"><span data-stu-id="76965-173">I've written numerous blog articles about the WMI and CIM cmdlets.</span></span> <span data-ttu-id="76965-174">В одной из самых полезных статей описывается созданная мной функция, которая позволяет автоматически определить нужный протокол WSMan или DCOM, а также настроить сеанс CIM, не указывая протокол вручную.</span><span class="sxs-lookup"><span data-stu-id="76965-174">One of the most useful ones is about a function that I created to automatically determine if WSMan or DCOM should be used and set up the CIM session automatically without having to figure out which one manually.</span></span> <span data-ttu-id="76965-175">Эта статья называется [PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom][] (Использование функции PowerShell для создания параметров CimSession на удаленных компьютерах с помощью отката и DCOM).</span><span class="sxs-lookup"><span data-stu-id="76965-175">That blog article is titled [PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom][].</span></span>

<span data-ttu-id="76965-176">Завершив работу с сеансами CIM, удалите их с помощью командлета `Remove-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="76965-176">When you're finished with the CIM sessions, you should remove them with the `Remove-CimSession` cmdlet.</span></span> <span data-ttu-id="76965-177">Чтобы удалить все сеансы CIM, передайте `Get-CimSession` в `Remove-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="76965-177">To remove all CIM sessions, simply pipe `Get-CimSession` to `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

## <a name="summary"></a><span data-ttu-id="76965-178">Сводка</span><span class="sxs-lookup"><span data-stu-id="76965-178">Summary</span></span>

<span data-ttu-id="76965-179">В этой главе вы узнали об использовании PowerShell для работы с инструментарием WMI на локальном и на удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="76965-179">In this chapter, you've learned about using PowerShell to work with WMI on both local and remote computers.</span></span> <span data-ttu-id="76965-180">Кроме того, вы узнали о том, как использовать командлеты CIM для работы с удаленными компьютерами с помощью протокола WSMan или DCOM.</span><span class="sxs-lookup"><span data-stu-id="76965-180">You've also learned how to use the CIM cmdlets to work with remote computers with both the WSMan or DCOM protocol.</span></span>

## <a name="review"></a><span data-ttu-id="76965-181">Просмотр</span><span class="sxs-lookup"><span data-stu-id="76965-181">Review</span></span>

1. <span data-ttu-id="76965-182">Чем отличаются командлеты WMI и CIM?</span><span class="sxs-lookup"><span data-stu-id="76965-182">What is the difference in the WMI and CIM cmdlets?</span></span>
1. <span data-ttu-id="76965-183">В каком протоколе командлет `Get-CimInstance` используется по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="76965-183">By default, what protocol does the `Get-CimInstance` cmdlet use?</span></span>
1. <span data-ttu-id="76965-184">В чем преимущества использования сеанса CIM перед вводом имени компьютера с помощью `Get-CimInstance`?</span><span class="sxs-lookup"><span data-stu-id="76965-184">What are some of the benefits of using a CIM session instead of specifying a computer name with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="76965-185">Как указать отличный от используемого по умолчанию альтернативный протокол вместе с `Get-CimInstance`?</span><span class="sxs-lookup"><span data-stu-id="76965-185">How do you specify an alternate protocol other than the default one for use with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="76965-186">Как закрыть или удалить сеансы CIM?</span><span class="sxs-lookup"><span data-stu-id="76965-186">How do you close or remove CIM sessions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="76965-187">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="76965-187">Recommended Reading</span></span>

- <span data-ttu-id="76965-188">[about_WMI][]</span><span class="sxs-lookup"><span data-stu-id="76965-188">[about_WMI][]</span></span>
- <span data-ttu-id="76965-189">[about_WMI_Cmdlets][]</span><span class="sxs-lookup"><span data-stu-id="76965-189">[about_WMI_Cmdlets][]</span></span>
- <span data-ttu-id="76965-190">[about_WQL][]</span><span class="sxs-lookup"><span data-stu-id="76965-190">[about_WQL][]</span></span>
- <span data-ttu-id="76965-191">[Модуль CimCmdlets][]</span><span class="sxs-lookup"><span data-stu-id="76965-191">[CimCmdlets Module][]</span></span>
- <span data-ttu-id="76965-192">[Видео: Использование командлетов CIM и сеансов CIM][]</span><span class="sxs-lookup"><span data-stu-id="76965-192">[Video: Using CIM Cmdlets and CIM Sessions][]</span></span>

<!-- link references -->
[about_WMI]: /powershell/module/microsoft.powershell.core/about/about_wmi
[about_WMI_Cmdlets]: /powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets
[about_WQL]: /powershell/module/microsoft.powershell.core/about/about_wql
[Модуль CimCmdlets]: /powershell/module/cimcmdlets/
[CimCmdlets Module]: /powershell/module/cimcmdlets/
[Видео: Использование командлетов CIM и сеансов CIM]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[Video: Using CIM Cmdlets and CIM Sessions]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/ (Использование функции PowerShell для создания параметров CimSession на удаленных компьютерах с помощью отката и DCOM).

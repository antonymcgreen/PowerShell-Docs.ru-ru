---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Установка пакета SDK для Windows PowerShell
ms.assetid: c3636b45-61aa-4720-85f0-58312c4fc8f9
ms.openlocfilehash: fa876bac0c1afac24f93d11dd2e7ecfb1165cf5f
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893544"
---
# <a name="installing-the-windows-powershell-sdk"></a><span data-ttu-id="88a12-103">Установка пакета SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88a12-103">Installing the Windows PowerShell SDK</span></span>

<span data-ttu-id="88a12-104">В следующей статье описывается, как установить пакет PowerShell SDK на разные версии Windows.</span><span class="sxs-lookup"><span data-stu-id="88a12-104">The following topic describes how to install the PowerShell SDK on different versions of Windows.</span></span>

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a><span data-ttu-id="88a12-105">Установка пакета SDK для Windows PowerShell 3.0 в Windows 8 и Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="88a12-105">Installing Windows PowerShell 3.0 SDK for Windows 8 and Windows Server 2012</span></span>

<span data-ttu-id="88a12-106">Windows PowerShell 3.0 устанавливается автоматически вместе с Windows 8 и Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="88a12-106">Windows PowerShell 3.0 is automatically installed with Windows 8 and Windows Server 2012.</span></span>
<span data-ttu-id="88a12-107">Вы также можете скачать и установить ссылочные сборки для Windows PowerShell 3.0 в составе Windows 8 SDK.</span><span class="sxs-lookup"><span data-stu-id="88a12-107">In addition, you can download and install the reference assemblies for Windows PowerShell 3.0 as part of the Windows 8 SDK.</span></span>
<span data-ttu-id="88a12-108">Эти сборки позволяют написать командлеты, поставщики и ведущие программы для Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="88a12-108">These assemblies allow you to write cmdlets, providers, and host programs for Windows PowerShell 3.0.</span></span>
<span data-ttu-id="88a12-109">При установке Windows SDK для Windows 8 сборки Windows PowerShell автоматически устанавливаются в папку базовой сборки, в `\Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`.</span><span class="sxs-lookup"><span data-stu-id="88a12-109">When you install the Windows SDK for Windows 8, the Windows PowerShell assemblies are automatically installed in the reference assembly folder, in `\Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`.</span></span>
<span data-ttu-id="88a12-110">Дополнительные сведения см. в статье [Веб-сайт скачивания пакета SDK для Windows 8](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive).</span><span class="sxs-lookup"><span data-stu-id="88a12-110">For more information, see the [Windows 8 SDK download site](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive).</span></span>
<span data-ttu-id="88a12-111">Примеры кода Windows PowerShell также доступны в Центре разработки.</span><span class="sxs-lookup"><span data-stu-id="88a12-111">Windows PowerShell code samples are also available on the Development Center.</span></span>
<span data-ttu-id="88a12-112">Дополнительные сведения см. на странице примеров кода классических приложений на [сайте центра разработки](https://code.msdn.microsoft.com:443/windowsdesktop/).</span><span class="sxs-lookup"><span data-stu-id="88a12-112">For more information, see the Desktop code sample page on the [Dev center site](https://code.msdn.microsoft.com:443/windowsdesktop/).</span></span>

<span data-ttu-id="88a12-113">Кроме того, Windows PowerShell 3.0 обратно совместим с Windows PowerShell 2.0 SDK, в который входит ряд примеров кода.</span><span class="sxs-lookup"><span data-stu-id="88a12-113">In addition, Windows PowerShell 3.0 is backwards-compatible with the Windows PowerShell 2.0 SDK, which includes a number of code samples.</span></span>
<span data-ttu-id="88a12-114">Дополнительные сведения о том, как скачать Windows PowerShell 2.0 SDK, см. ниже.</span><span class="sxs-lookup"><span data-stu-id="88a12-114">For more information on how to download the Windows PowerShell 2.0 SDK, see below.</span></span>
<span data-ttu-id="88a12-115">(Обратите внимание, что, хотя примеры кода 2.0 совместимы с Windows 8 и Windows PowerShell 3.0, невозможно установить Windows PowerShell 2.0 на платформу Windows 8.)</span><span class="sxs-lookup"><span data-stu-id="88a12-115">(Note that while the 2.0 code samples are compatible with Windows 8 and Windows PowerShell 3.0, you cannot install Windows PowerShell 2.0 on a Windows 8 platform.)</span></span>

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a><span data-ttu-id="88a12-116">Установка пакета SDK для Windows PowerShell 3.0 в Windows 7 и Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="88a12-116">Installing Windows PowerShell 3.0 SDK for Windows 7 and Windows Server 2008 R2</span></span>

<span data-ttu-id="88a12-117">Вместе с Windows 7 и Windows Server 2008 R2 автоматически устанавливается PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="88a12-117">Windows 7 and Windows Server 2008 R2 automatically have PowerShell 2.0 installed.</span></span>
<span data-ttu-id="88a12-118">Вы также можете установить PowerShell 3.0 в этих системах.</span><span class="sxs-lookup"><span data-stu-id="88a12-118">In addition, you can install PowerShell 3.0 on these systems.</span></span>
<span data-ttu-id="88a12-119">(Дополнительные сведения см. в статье [Установка Windows PowerShell](Installing-Windows-PowerShell.md).)</span><span class="sxs-lookup"><span data-stu-id="88a12-119">(For more information, see [Installing Windows PowerShell](Installing-Windows-PowerShell.md).).</span></span>
<span data-ttu-id="88a12-120">Как описано выше, вы также можете установить Windows 8 SDK на Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="88a12-120">As described above, you can also install the Windows 8 SDK on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a><span data-ttu-id="88a12-121">Установка пакета SDK для Windows PowerShell 2.0 в Windows 7, Windows Vista, Windows XP, Windows Server 2003 и Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="88a12-121">Installing Windows PowerShell 2.0 SDK for Windows 7, Vista, XP, Server 2003, and Server 2008</span></span>

<span data-ttu-id="88a12-122">Установка пакета SDK для Windows PowerShell 2.0 предоставляет эталонные сборки, необходимые для написания командлетов, поставщиков и ведущих приложений, а также пример кода C#, который можно использовать в качестве начальной точки при написании кода.</span><span class="sxs-lookup"><span data-stu-id="88a12-122">The Windows PowerShell 2.0 SDK provides the reference assemblies needed to write cmdlets, providers, and hosting applications, and it provides C# sample code that can be used as the starting point when you begin writing code.</span></span>

<span data-ttu-id="88a12-123">Инструкции по установке этого пакета SDK см. в статье [Пакет SDK для Windows PowerShell 2.0](http://www.microsoft.com/en-us/download/details.aspx?id=2560).</span><span class="sxs-lookup"><span data-stu-id="88a12-123">To install this SDK, see [Windows PowerShell 2.0 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=2560).</span></span>

## <a name="reference-assemblies"></a><span data-ttu-id="88a12-124">Эталонные сборки</span><span class="sxs-lookup"><span data-stu-id="88a12-124">Reference assemblies</span></span>

<span data-ttu-id="88a12-125">Эталонные сборки по умолчанию устанавливаются в следующий каталог: `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0`.</span><span class="sxs-lookup"><span data-stu-id="88a12-125">Reference assemblies are installed in the following location by default: `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0`.</span></span>

> [!NOTE] 
> <span data-ttu-id="88a12-126">Код, который компилируется с использованием сборок Windows PowerShell 2.0, нельзя загрузить в установках Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="88a12-126">Code that is compiled against the Windows PowerShell 2.0 assemblies cannot be loaded into Windows PowerShell 1.0 installations.</span></span>
> <span data-ttu-id="88a12-127">Но код, который компилируется в сборках Windows PowerShell 1.0, можно загрузить в установках Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="88a12-127">However, code that is compiled against the Windows PowerShell 1.0 assemblies can be loaded into Windows PowerShell 2.0 installations.</span></span>

## <a name="samples"></a><span data-ttu-id="88a12-128">примеры</span><span class="sxs-lookup"><span data-stu-id="88a12-128">Samples</span></span>

<span data-ttu-id="88a12-129">Примеры кода по умолчанию устанавливаются в следующий каталог: `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="88a12-129">Code samples are installed in the following location by default: `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.</span></span>

<span data-ttu-id="88a12-130">В следующих разделах приводится краткое описание каждого примера.</span><span class="sxs-lookup"><span data-stu-id="88a12-130">The following sections provide a brief description of what each sample does.</span></span>

## <a name="cmdlet-samples"></a><span data-ttu-id="88a12-131">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="88a12-131">Cmdlet samples</span></span>

### <a name="getprocesssample01"></a><span data-ttu-id="88a12-132">GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="88a12-132">GetProcessSample01</span></span>

<span data-ttu-id="88a12-133">Показывает, как написать простой командлет, который будет получать все процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="88a12-133">Shows how to write a simple cmdlet that gets all the processes on the local computer.</span></span>

### <a name="getprocesssample02"></a><span data-ttu-id="88a12-134">GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="88a12-134">GetProcessSample02</span></span>

<span data-ttu-id="88a12-135">Показывает, как добавить в командлет параметры.</span><span class="sxs-lookup"><span data-stu-id="88a12-135">Shows how to add parameters to the cmdlet.</span></span>
<span data-ttu-id="88a12-136">Командлет принимает одно или несколько имен процессов и возвращает соответствующие процессы.</span><span class="sxs-lookup"><span data-stu-id="88a12-136">The cmdlet takes one or more process names and returns the matching processes.</span></span>

### <a name="getprocesssample03"></a><span data-ttu-id="88a12-137">GetProcessSample03</span><span class="sxs-lookup"><span data-stu-id="88a12-137">GetProcessSample03</span></span>

<span data-ttu-id="88a12-138">Показывает, как добавить параметры, которые будут принимать входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="88a12-138">Shows how to add parameters that accept input from the pipeline.</span></span>

### <a name="getprocesssample04"></a><span data-ttu-id="88a12-139">GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="88a12-139">GetProcessSample04</span></span>

<span data-ttu-id="88a12-140">Показывает, как обрабатывать устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="88a12-140">Shows how to handle nonterminating errors.</span></span>

### <a name="getprocesssample05"></a><span data-ttu-id="88a12-141">GetProcessSample05</span><span class="sxs-lookup"><span data-stu-id="88a12-141">GetProcessSample05</span></span>

<span data-ttu-id="88a12-142">Показывает, как вывести на экран список указанных процессов.</span><span class="sxs-lookup"><span data-stu-id="88a12-142">Shows how to display a list of specified processes.</span></span>

### <a name="selectobject"></a><span data-ttu-id="88a12-143">SelectObject</span><span class="sxs-lookup"><span data-stu-id="88a12-143">SelectObject</span></span>

<span data-ttu-id="88a12-144">Показывает, как написать фильтр, позволяющий отобрать только определенные объекты.</span><span class="sxs-lookup"><span data-stu-id="88a12-144">Shows how to write a filter to select only certain objects.</span></span>

### <a name="selectstring"></a><span data-ttu-id="88a12-145">SelectString</span><span class="sxs-lookup"><span data-stu-id="88a12-145">SelectString</span></span>

<span data-ttu-id="88a12-146">Показывает, как искать в файлах заданные последовательности.</span><span class="sxs-lookup"><span data-stu-id="88a12-146">Shows how to search files for specified patterns.</span></span>

### <a name="stopprocesssample01"></a><span data-ttu-id="88a12-147">StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="88a12-147">StopProcessSample01</span></span>

<span data-ttu-id="88a12-148">Показывает, как реализовать параметр *PassThru* и запрашивать мнение пользователя, вызывая методы [ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess) и [ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span><span class="sxs-lookup"><span data-stu-id="88a12-148">Shows how to implement a *PassThru* parameter, and how to request user feedback by calls to the [ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess) and [ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue) methods.</span></span>
<span data-ttu-id="88a12-149">Если пользователь хочет заставить командлет вернуть объект, он указывает параметр *PassThru*.</span><span class="sxs-lookup"><span data-stu-id="88a12-149">Users specify the *PassThru* parameter when they want to force the cmdlet to return an object,</span></span>

### <a name="stopprocesssample02"></a><span data-ttu-id="88a12-150">StopProcessSample02</span><span class="sxs-lookup"><span data-stu-id="88a12-150">StopProcessSample02</span></span>

<span data-ttu-id="88a12-151">Показывает, как остановить определенный процесс.</span><span class="sxs-lookup"><span data-stu-id="88a12-151">Shows how to stop a specific process.</span></span>

### <a name="stopprocesssample03"></a><span data-ttu-id="88a12-152">StopProcessSample03</span><span class="sxs-lookup"><span data-stu-id="88a12-152">StopProcessSample03</span></span>

<span data-ttu-id="88a12-153">Показывает, как объявлять псевдонимы для параметров и включать поддержку подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="88a12-153">Shows how to declare aliases for parameters and how to support wildcards.</span></span>

### <a name="stopprocesssample04"></a><span data-ttu-id="88a12-154">StopProcessSample04</span><span class="sxs-lookup"><span data-stu-id="88a12-154">StopProcessSample04</span></span>

<span data-ttu-id="88a12-155">Показывает, как объявлять набор параметров (объект, принимаемый командлетом как входные данные) и указывать, какой набор параметров должен использоваться по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88a12-155">Shows how to declare parameter sets, the object that the cmdlet takes as input, and how to specify the default parameter set to use.</span></span>

## <a name="remoting-samples"></a><span data-ttu-id="88a12-156">Примеры удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="88a12-156">Remoting samples</span></span>

### <a name="remoterunspace01"></a><span data-ttu-id="88a12-157">RemoteRunspace01</span><span class="sxs-lookup"><span data-stu-id="88a12-157">RemoteRunspace01</span></span>

<span data-ttu-id="88a12-158">Показывает, как создавать удаленное пространство выполнения, используемое для установления удаленного подключения.</span><span class="sxs-lookup"><span data-stu-id="88a12-158">Shows how to create a remote runspace that is used to establish a remote connection.</span></span>

### <a name="remoterunspacepool01"></a><span data-ttu-id="88a12-159">RemoteRunspacePool01</span><span class="sxs-lookup"><span data-stu-id="88a12-159">RemoteRunspacePool01</span></span>

<span data-ttu-id="88a12-160">Показывает, как формировать пул удаленных пространств выполнения и с его помощью выполнять сразу несколько команд одновременно.</span><span class="sxs-lookup"><span data-stu-id="88a12-160">Shows how to construct a remote runspace pool and how to run multiple commands concurrently by using this pool.</span></span>

### <a name="serialization01"></a><span data-ttu-id="88a12-161">Serialization01</span><span class="sxs-lookup"><span data-stu-id="88a12-161">Serialization01</span></span>

<span data-ttu-id="88a12-162">Показывает, как проанализировать существующий класс .NET и сделать так, чтобы информация из определенных открытых свойств этого класса сохранялась в процессе сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="88a12-162">Shows how to look at an existing .NET class and make sure that information from selected public properties of this class is preserved across serialization/deserialization.</span></span>

### <a name="serialization02"></a><span data-ttu-id="88a12-163">Serialization02</span><span class="sxs-lookup"><span data-stu-id="88a12-163">Serialization02</span></span>

<span data-ttu-id="88a12-164">Показывает, как проанализировать существующий класс .NET и сделать так, чтобы информация из экземпляра этого класса сохранялась в процессе сериализации и десериализации на случай, если информация будет недоступна в открытых свойствах класса.</span><span class="sxs-lookup"><span data-stu-id="88a12-164">Shows how to look at an existing .NET class and make sure that information from instance of this class is preserved across serialization/deserialization when the information is not available in public properties of the class.</span></span>

### <a name="serialization03"></a><span data-ttu-id="88a12-165">Serialization03</span><span class="sxs-lookup"><span data-stu-id="88a12-165">Serialization03</span></span>

<span data-ttu-id="88a12-166">Показывает, как проанализировать существующий класс .NET и сделать так, чтобы экземпляры этого класса и классов, производных от него, десериализовывались (восстанавливались) в рабочие объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="88a12-166">Shows how to look at an existing .NET class and make sure that instances of this class and of derived classes are deserialized (rehydrated) into live .NET objects.</span></span>

## <a name="event-samples"></a><span data-ttu-id="88a12-167">Примеры событий</span><span class="sxs-lookup"><span data-stu-id="88a12-167">Event samples</span></span>

### <a name="event01"></a><span data-ttu-id="88a12-168">Event01</span><span class="sxs-lookup"><span data-stu-id="88a12-168">Event01</span></span>

<span data-ttu-id="88a12-169">Показывает, как создать командлет для регистрации событий, наследуя от ObjectEventRegistrationBase.</span><span class="sxs-lookup"><span data-stu-id="88a12-169">Shows how to create a cmdlet for event registration by deriving from ObjectEventRegistrationBase.</span></span>

### <a name="event02"></a><span data-ttu-id="88a12-170">Event02</span><span class="sxs-lookup"><span data-stu-id="88a12-170">Event02</span></span>

<span data-ttu-id="88a12-171">Показывает, как получать уведомления о событиях Windows PowerShell, возникающих на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="88a12-171">Shows how to shows how to receive notifications of Windows PowerShell events that are generated on remote computers.</span></span>
<span data-ttu-id="88a12-172">Использует событие PSEventReceived, предоставляемое классом [Runspace](/dotnet/api/system.management.automation.runspaces.runspace).</span><span class="sxs-lookup"><span data-stu-id="88a12-172">It uses the PSEventReceived event exposed through the [Runspace](/dotnet/api/system.management.automation.runspaces.runspace) class.</span></span>

## <a name="hosting-application-samples"></a><span data-ttu-id="88a12-173">Примеры размещения приложений</span><span class="sxs-lookup"><span data-stu-id="88a12-173">Hosting application samples</span></span>

### <a name="runspace01"></a><span data-ttu-id="88a12-174">Runspace01</span><span class="sxs-lookup"><span data-stu-id="88a12-174">Runspace01</span></span>

<span data-ttu-id="88a12-175">Показывает, как использовать класс [PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлета [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span><span class="sxs-lookup"><span data-stu-id="88a12-175">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span>
<span data-ttu-id="88a12-176">Командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает объекты [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) для каждого процесса, запущенного на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="88a12-176">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer.</span></span>

### <a name="runspace02"></a><span data-ttu-id="88a12-177">Runspace02</span><span class="sxs-lookup"><span data-stu-id="88a12-177">Runspace02</span></span>

<span data-ttu-id="88a12-178">Показывает, как использовать класс [PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object).</span><span class="sxs-lookup"><span data-stu-id="88a12-178">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span>
<span data-ttu-id="88a12-179">Командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает объекты [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) для каждого процесса, запущенного на локальном компьютере, а командлет `Sort-Object` сортирует объекты на основании свойства [Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx).</span><span class="sxs-lookup"><span data-stu-id="88a12-179">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) property.</span></span>
<span data-ttu-id="88a12-180">Результаты выполнения этих команд можно отобразить с помощью элемента управления [DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx).</span><span class="sxs-lookup"><span data-stu-id="88a12-180">The results of these commands is displayed by using a [DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) control.</span></span>

### <a name="runspace03"></a><span data-ttu-id="88a12-181">Runspace03</span><span class="sxs-lookup"><span data-stu-id="88a12-181">Runspace03</span></span>

<span data-ttu-id="88a12-182">Показывает, как использовать класс [PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения скрипта и как обрабатывать устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="88a12-182">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span>
<span data-ttu-id="88a12-183">Скрипт получает список имен процессов, а затем извлекает эти процессы.</span><span class="sxs-lookup"><span data-stu-id="88a12-183">The script receives a list of process names and then retrieves those processes.</span></span>
<span data-ttu-id="88a12-184">Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="88a12-184">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

### <a name="runspace04"></a><span data-ttu-id="88a12-185">Runspace04</span><span class="sxs-lookup"><span data-stu-id="88a12-185">Runspace04</span></span>

<span data-ttu-id="88a12-186">Показывает, как использовать класс [PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд и фиксации неустранимых ошибок, возникающих при их выполнении.</span><span class="sxs-lookup"><span data-stu-id="88a12-186">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span>
<span data-ttu-id="88a12-187">Выполняются две команды, и последняя получает недопустимый аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="88a12-187">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span>
<span data-ttu-id="88a12-188">В результате объекты не возвращаются и создается неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="88a12-188">As a result, no objects are returned and a terminating error is thrown.</span></span>

### <a name="runspace05"></a><span data-ttu-id="88a12-189">Runspace05</span><span class="sxs-lookup"><span data-stu-id="88a12-189">Runspace05</span></span>

<span data-ttu-id="88a12-190">Показывает, как добавить оснастку в объект [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate), чтобы командлет оснастки был доступен при открытии пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="88a12-190">Shows how to add a snap-in to an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span>
<span data-ttu-id="88a12-191">Оснастка предоставляет командлет Get-Proc (см. [GetProcessSample01](https://technet.microsoft.com/library/ff602028.aspx)), который запускается синхронно с помощью объекта [PowerShell](/dotnet/api/system.management.automation.powershell).</span><span class="sxs-lookup"><span data-stu-id="88a12-191">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](https://technet.microsoft.com/library/ff602028.aspx)) that is run synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace06"></a><span data-ttu-id="88a12-192">Runspace06</span><span class="sxs-lookup"><span data-stu-id="88a12-192">Runspace06</span></span>

<span data-ttu-id="88a12-193">Показывает, как добавить модуль в объект [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate), чтобы модуль загружался при открытии пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="88a12-193">Shows how to add a module to an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object so that the module is loaded when the runspace is opened.</span></span>
<span data-ttu-id="88a12-194">Модуль предоставляет командлет Get-Proc (см. [GetProcessSample02](https://technet.microsoft.com/library/ff602027.aspx)), который запускается синхронно с помощью объекта [PowerShell](/dotnet/api/system.management.automation.powershell).</span><span class="sxs-lookup"><span data-stu-id="88a12-194">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](https://technet.microsoft.com/library/ff602027.aspx)) that is run synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace07"></a><span data-ttu-id="88a12-195">Runspace07</span><span class="sxs-lookup"><span data-stu-id="88a12-195">Runspace07</span></span>

<span data-ttu-id="88a12-196">Показывает, как создать пространство выполнения и использовать его для синхронного запуска двух командлетов с помощью объекта [PowerShell](/dotnet/api/system.management.automation.powershell).</span><span class="sxs-lookup"><span data-stu-id="88a12-196">Shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace08"></a><span data-ttu-id="88a12-197">Runspace08</span><span class="sxs-lookup"><span data-stu-id="88a12-197">Runspace08</span></span>

<span data-ttu-id="88a12-198">Показывает, как добавить команды и аргументы в конвейер объекта [PowerShell](/dotnet/api/system.management.automation.powershell) и запустить команды синхронно.</span><span class="sxs-lookup"><span data-stu-id="88a12-198">Shows how to add commands and arguments to the pipeline of a [PowerShell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

### <a name="runspace09"></a><span data-ttu-id="88a12-199">Runspace09</span><span class="sxs-lookup"><span data-stu-id="88a12-199">Runspace09</span></span>

<span data-ttu-id="88a12-200">Показывает, как добавить скрипт в конвейер объекта [PowerShell](/dotnet/api/system.management.automation.powershell) и запустить скрипт асинхронно.</span><span class="sxs-lookup"><span data-stu-id="88a12-200">Shows how to add a script to the pipeline of a [PowerShell](/dotnet/api/system.management.automation.powershell) object and how to run the script asynchronously.</span></span>
<span data-ttu-id="88a12-201">События используются для обработки выходных данных скрипта.</span><span class="sxs-lookup"><span data-stu-id="88a12-201">Events are used to handle the output of the script.</span></span>

### <a name="runspace10"></a><span data-ttu-id="88a12-202">Runspace10</span><span class="sxs-lookup"><span data-stu-id="88a12-202">Runspace10</span></span>

<span data-ttu-id="88a12-203">Показывает, как создать начальное состояние сеанса по умолчанию, добавить командлет в [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate), создать пространство выполнения с использованием начального состояния сеанса и выполнить команду с помощью объекта [PowerShell](/dotnet/api/system.management.automation.powershell).</span><span class="sxs-lookup"><span data-stu-id="88a12-203">Shows how to create a default initial session state, how to add a cmdlet to the [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate), how to create a runspace that uses the initial session state, and how to run the command by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace11"></a><span data-ttu-id="88a12-204">Runspace11</span><span class="sxs-lookup"><span data-stu-id="88a12-204">Runspace11</span></span>

<span data-ttu-id="88a12-205">Показывает, как использовать класс [ProxyCommand](/dotnet/api/system.management.automation.proxycommand) для создания прокси-команды, которая вызывает существующий командлет, но ограничивает набор доступных параметров.</span><span class="sxs-lookup"><span data-stu-id="88a12-205">Shows how to use the [ProxyCommand](/dotnet/api/system.management.automation.proxycommand) class to create a proxy command that calls an existing cmdlet, but restricts the set of available parameters.</span></span>
<span data-ttu-id="88a12-206">Прокси-команда затем добавляется в начальное состояние сеанса, который используется для создания ограниченного пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="88a12-206">The proxy command is then added to an initial session state that is used to create a constrained runspace.</span></span>
<span data-ttu-id="88a12-207">Это означает, что пользователь может получить доступ к функциям командлета только с помощью прокси-команды.</span><span class="sxs-lookup"><span data-stu-id="88a12-207">This means that the user can access the functionality of the cmdlet only through the proxy command.</span></span>

### <a name="powershell01"></a><span data-ttu-id="88a12-208">PowerShell01</span><span class="sxs-lookup"><span data-stu-id="88a12-208">PowerShell01</span></span>

<span data-ttu-id="88a12-209">Показывает, как создать ограниченное пространство выполнения с помощью объекта [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate).</span><span class="sxs-lookup"><span data-stu-id="88a12-209">Shows how to create a constrained runspace using an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object.</span></span>

### <a name="powershell02"></a><span data-ttu-id="88a12-210">PowerShell02</span><span class="sxs-lookup"><span data-stu-id="88a12-210">PowerShell02</span></span>

<span data-ttu-id="88a12-211">Показывает, как использовать пул пространств выполнения для одновременного выполнения нескольких команд.</span><span class="sxs-lookup"><span data-stu-id="88a12-211">Shows how to use a runspace pool to run multiple commands concurrently.</span></span>

## <a name="host-samples"></a><span data-ttu-id="88a12-212">Примеры узлов</span><span class="sxs-lookup"><span data-stu-id="88a12-212">Host samples</span></span>

### <a name="host01"></a><span data-ttu-id="88a12-213">Host01</span><span class="sxs-lookup"><span data-stu-id="88a12-213">Host01</span></span>

<span data-ttu-id="88a12-214">Показывает, как реализовать ведущее приложение, которое использует пользовательский узел.</span><span class="sxs-lookup"><span data-stu-id="88a12-214">Shows how to implement a host application that uses a custom host.</span></span>
<span data-ttu-id="88a12-215">В этом примере создается пространство выполнения, которое использует пользовательский узел, а затем с помощью API [T:System.Management.Automation.PowerShell](/dotnet/api/system.management.automation.powershell) запускается скрипт, вызывающий команду "exit".</span><span class="sxs-lookup"><span data-stu-id="88a12-215">In this sample a runspace is created that uses the custom host, and then the [PowerShell](/dotnet/api/system.management.automation.powershell) API is used to run a script that calls "exit".</span></span>
<span data-ttu-id="88a12-216">Затем ведущее приложение анализирует выходные данные скрипта и выводит на экран результаты.</span><span class="sxs-lookup"><span data-stu-id="88a12-216">The host application then looks at the output of the script and prints out the results.</span></span>

### <a name="host02"></a><span data-ttu-id="88a12-217">Host02</span><span class="sxs-lookup"><span data-stu-id="88a12-217">Host02</span></span>

<span data-ttu-id="88a12-218">Показывает, как написать ведущее приложение, использующее среду выполнения Windows PowerShell наряду с реализацией пользовательского узла.</span><span class="sxs-lookup"><span data-stu-id="88a12-218">Shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span>
<span data-ttu-id="88a12-219">Ведущее приложение задает в качестве региональных параметров немецкий язык, запускает командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и отображает результаты в том виде, в котором они отобразились бы при использовании pwrsh.exe, а затем выводит на экран текущие дату и время на немецком языке.</span><span class="sxs-lookup"><span data-stu-id="88a12-219">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them by using pwrsh.exe, and then prints out the current data and time in German.</span></span>

### <a name="host03"></a><span data-ttu-id="88a12-220">Host03</span><span class="sxs-lookup"><span data-stu-id="88a12-220">Host03</span></span>

<span data-ttu-id="88a12-221">Показывает, как выполнить сборку интерактивного консольного ведущего приложения, которое считывает команды из командной строки, выполняет их, а затем отображает результаты в консоли.</span><span class="sxs-lookup"><span data-stu-id="88a12-221">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

### <a name="host04"></a><span data-ttu-id="88a12-222">Host04</span><span class="sxs-lookup"><span data-stu-id="88a12-222">Host04</span></span>

<span data-ttu-id="88a12-223">Показывает, как выполнить сборку интерактивного консольного ведущего приложения, которое считывает команды из командной строки, выполняет их, а затем отображает результаты в консоли.</span><span class="sxs-lookup"><span data-stu-id="88a12-223">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="88a12-224">Это приложение также поддерживает отображение запросов, позволяющих пользователю выбрать несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="88a12-224">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

### <a name="host05"></a><span data-ttu-id="88a12-225">Host05</span><span class="sxs-lookup"><span data-stu-id="88a12-225">Host05</span></span>

<span data-ttu-id="88a12-226">Показывает, как выполнить сборку интерактивного консольного ведущего приложения, которое считывает команды из командной строки, выполняет их, а затем отображает результаты в консоли.</span><span class="sxs-lookup"><span data-stu-id="88a12-226">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="88a12-227">Это ведущее приложение также поддерживает вызовы удаленных компьютеров с помощью командлетов [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) и [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession).</span><span class="sxs-lookup"><span data-stu-id="88a12-227">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets.</span></span>

### <a name="host06"></a><span data-ttu-id="88a12-228">Host06</span><span class="sxs-lookup"><span data-stu-id="88a12-228">Host06</span></span>

<span data-ttu-id="88a12-229">Показывает, как выполнить сборку интерактивного консольного ведущего приложения, которое считывает команды из командной строки, выполняет их, а затем отображает результаты в консоли.</span><span class="sxs-lookup"><span data-stu-id="88a12-229">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="88a12-230">Кроме того, в этом примере используются интерфейсы API создателя токенов для указания цвета текста, вводимого пользователем.</span><span class="sxs-lookup"><span data-stu-id="88a12-230">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="provider-samples"></a><span data-ttu-id="88a12-231">Примеры поставщиков</span><span class="sxs-lookup"><span data-stu-id="88a12-231">Provider samples</span></span>

### <a name="accessdbprovidersample01"></a><span data-ttu-id="88a12-232">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="88a12-232">AccessDBProviderSample01</span></span>

<span data-ttu-id="88a12-233">Показывает, как объявить класс поставщика, производный от класса [CmdletProvider](/dotnet/api/system.management.automation.provider.cmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-233">Shows how to declare a provider class that derives directly from the [CmdletProvider](/dotnet/api/system.management.automation.provider.cmdletprovider) class.</span></span>
<span data-ttu-id="88a12-234">Он приводится здесь только для полноты картины.</span><span class="sxs-lookup"><span data-stu-id="88a12-234">It is included here only for completeness.</span></span>

### <a name="accessdbprovidersample02"></a><span data-ttu-id="88a12-235">AccessDBProviderSample02</span><span class="sxs-lookup"><span data-stu-id="88a12-235">AccessDBProviderSample02</span></span>

<span data-ttu-id="88a12-236">Показывает, как перезаписать методы [NewDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.newdrive) и [RemoveDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.removedrive) таким образом, чтобы они поддерживали вызовы командлетов `New-PSDrive` и `Remove-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="88a12-236">Shows how to overwrite the [NewDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.newdrive) and [RemoveDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.removedrive) methods to support calls to the `New-PSDrive` and `Remove-PSDrive` cmdlets.</span></span>
<span data-ttu-id="88a12-237">Класс поставщика в этом примере является производным от класса [DriveCmdletProvider](/dotnet/api/system.management.automation.provider.drivecmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-237">The provider class in this sample derives from the [DriveCmdletProvider](/dotnet/api/system.management.automation.provider.drivecmdletprovider) class.</span></span>

### <a name="accessdbprovidersample03"></a><span data-ttu-id="88a12-238">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="88a12-238">AccessDBProviderSample03</span></span>

<span data-ttu-id="88a12-239">Показывает, как перезаписать методы [GetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.getitem) и [SetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.setitem) таким образом, чтобы они поддерживали вызовы командлетов `Get-Item` и `Set-Item`.</span><span class="sxs-lookup"><span data-stu-id="88a12-239">Shows how to overwrite the [GetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.getitem) and [SetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.setitem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span>
<span data-ttu-id="88a12-240">Класс поставщика в этом примере является производным от класса [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-240">The provider class in this sample derives from the [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample04"></a><span data-ttu-id="88a12-241">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="88a12-241">AccessDBProviderSample04</span></span>

<span data-ttu-id="88a12-242">Показывает, как перезаписать методы контейнера таким образом, чтобы они поддерживали вызовы командлетов `Copy-Item`, `Get-ChildItem`, `New-Item` и `Remove-Item`.</span><span class="sxs-lookup"><span data-stu-id="88a12-242">Shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span>
<span data-ttu-id="88a12-243">Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами.</span><span class="sxs-lookup"><span data-stu-id="88a12-243">These methods should be implemented when the data store contains items that are containers.</span></span>
<span data-ttu-id="88a12-244">Контейнер — это группа дочерних элементов в составе общего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="88a12-244">A container is a group of child items under a common parent item.</span></span>
<span data-ttu-id="88a12-245">Класс поставщика в этом примере является производным от класса [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-245">The provider class in this sample derives from the [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample05"></a><span data-ttu-id="88a12-246">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="88a12-246">AccessDBProviderSample05</span></span>

<span data-ttu-id="88a12-247">Показывает, как перезаписать методы контейнера таким образом, чтобы они поддерживали вызовы командлетов `Move-Item` и `Join-Path`.</span><span class="sxs-lookup"><span data-stu-id="88a12-247">Shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span>
<span data-ttu-id="88a12-248">Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="88a12-248">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span>
<span data-ttu-id="88a12-249">Класс поставщика в этом примере является производным от класса [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-249">The provider class in this sample derives from the [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample06"></a><span data-ttu-id="88a12-250">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="88a12-250">AccessDBProviderSample06</span></span>

<span data-ttu-id="88a12-251">Показывает, как перезаписать методы содержимого таким образом, чтобы они поддерживали вызовы командлетов `Clear-Content`, `Get-Content` и `Set-Content`.</span><span class="sxs-lookup"><span data-stu-id="88a12-251">Shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span>
<span data-ttu-id="88a12-252">Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="88a12-252">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span>
<span data-ttu-id="88a12-253">Класс поставщика в этом примере является производным от класса [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) и реализует интерфейс [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider).</span><span class="sxs-lookup"><span data-stu-id="88a12-253">The provider class in this sample derives from the [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) class, and it implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>
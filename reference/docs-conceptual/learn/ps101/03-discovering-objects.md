---
title: Обнаружение объектов, свойств и методов
description: Чтобы понимать и использовать объекты, свойства и методы, не нужно быть разработчиком.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 5ab972755afeba0d94bf6c2debaf84ec84cd9244
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438075"
---
# <a name="chapter-3---discovering-objects-properties-and-methods"></a><span data-ttu-id="17864-103">Глава 3. Обнаружение объектов, свойств и методов</span><span class="sxs-lookup"><span data-stu-id="17864-103">Chapter 3 - Discovering objects, properties, and methods</span></span>

<span data-ttu-id="17864-104">Мое знакомство с компьютерами началось с Commodore 64, но первым современным компьютером был клон IBM на базе 286, с частотой 12 МГц, 1 МБ памяти, жестким диском объемом 40 МБ, одним дисководом 5,25 дюйма, монитором CGA и ОС Microsoft DOS 3.3.</span><span class="sxs-lookup"><span data-stu-id="17864-104">My first introduction to computers was a Commodore 64, but my first modern computer was a 286 12-Mhz IBM clone with 1 megabyte of memory, a 40-megabyte hard drive, and one 5-1/4 inch floppy disk drive with a CGA monitor running Microsoft DOS 3.3.</span></span>

<span data-ttu-id="17864-105">Многие ИТ-специалисты, да и я тоже, не понаслышке знают о командной строке, но, когда дело касается объектов, свойств и методов, они впадают в ступор и говорят: "Я не разработчик".</span><span class="sxs-lookup"><span data-stu-id="17864-105">Many IT Pros, like myself, are no stranger to the command line, but when the subject of objects, properties, and methods comes up, they get the deer in the headlights look and say, "I'm not a developer."</span></span> <span data-ttu-id="17864-106">И знаете что?</span><span class="sxs-lookup"><span data-stu-id="17864-106">Guess what?</span></span> <span data-ttu-id="17864-107">Для работы с PowerShell совершенно не обязательно быть разработчиком.</span><span class="sxs-lookup"><span data-stu-id="17864-107">You don't have to be a developer to be successful with PowerShell.</span></span> <span data-ttu-id="17864-108">Не углубляйтесь в терминологию.</span><span class="sxs-lookup"><span data-stu-id="17864-108">Don't get bogged down in the terminology.</span></span> <span data-ttu-id="17864-109">Сначала что-то может показаться непонятным и бессмысленным, но, когда вы немного попрактикуетесь, наступит миг озарения.</span><span class="sxs-lookup"><span data-stu-id="17864-109">Not everything may make sense initially, but after a little hands-on experience you'll start to have those "light bulb" moments.</span></span> <span data-ttu-id="17864-110">"Ну, конечно!</span><span class="sxs-lookup"><span data-stu-id="17864-110">"Aha!</span></span> <span data-ttu-id="17864-111">Так вот о чем шла речь в книге!"</span><span class="sxs-lookup"><span data-stu-id="17864-111">So that's what the book was talking about."</span></span>

<span data-ttu-id="17864-112">Обязательно попробуйте выполнить примеры на своем компьютере, чтобы получить некий практический опыт.</span><span class="sxs-lookup"><span data-stu-id="17864-112">Be sure to try the examples on your computer to gain some of that hands-on experience.</span></span>

## <a name="requirements"></a><span data-ttu-id="17864-113">Требования</span><span class="sxs-lookup"><span data-stu-id="17864-113">Requirements</span></span>

<span data-ttu-id="17864-114">В некоторых примерах, приведенных в этой главе, требуется модуль Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17864-114">The Active Directory PowerShell module is required by some of the examples shown in this chapter.</span></span>
<span data-ttu-id="17864-115">Модуль входит в состав средств удаленного администрирования сервера (RSAT) для Windows.</span><span class="sxs-lookup"><span data-stu-id="17864-115">The module is part of the Remote Server Administration Tools (RSAT) for Windows.</span></span> <span data-ttu-id="17864-116">В сборке Windows 1809 (или более поздней версии) средства RSAT установлены в качестве компонента Windows.</span><span class="sxs-lookup"><span data-stu-id="17864-116">For the 1809 (or higher) build of Windows, the RSAT tools are installed as a Windows feature.</span></span>

- <span data-ttu-id="17864-117">Сведения об установке средств RSAT см. в разделе [Модули управления Windows][].</span><span class="sxs-lookup"><span data-stu-id="17864-117">For information about installing the RSAT tools, see [Windows Management modules][].</span></span>
- <span data-ttu-id="17864-118">При работе с более ранними версиями Windows см. статью [RSAT для Windows][].</span><span class="sxs-lookup"><span data-stu-id="17864-118">For older versions of Windows, see [RSAT for Windows][].</span></span>

## <a name="get-member"></a><span data-ttu-id="17864-119">Get-Member</span><span class="sxs-lookup"><span data-stu-id="17864-119">Get-Member</span></span>

<span data-ttu-id="17864-120">`Get-Member` помогает определить доступные для команд объекты, свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="17864-120">`Get-Member` helps you discover what objects, properties, and methods are available for commands.</span></span>
<span data-ttu-id="17864-121">Все команды, создающие объектно-ориентированные выходные данные, могут быть переданы в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-121">Any command that produces object-based output can be piped to `Get-Member`.</span></span> <span data-ttu-id="17864-122">Свойство — это характеристика элемента.</span><span class="sxs-lookup"><span data-stu-id="17864-122">A property is a characteristic about an item.</span></span> <span data-ttu-id="17864-123">У водительского удостоверения есть свойство, называемое цветом глаз, а самыми распространенными значениями для этого свойства являются цвета: синий и карий.</span><span class="sxs-lookup"><span data-stu-id="17864-123">Your drivers license has a property called eye color and the most common values for that property are blue and brown.</span></span> <span data-ttu-id="17864-124">Метод — это действие, которое может быть выполнено с элементом.</span><span class="sxs-lookup"><span data-stu-id="17864-124">A method is an action that can be taken on an item.</span></span> <span data-ttu-id="17864-125">В примере с водительским удостоверением одним из методов является "Лишить", так как управление автомобильного транспорта может лишить вас удостоверения.</span><span class="sxs-lookup"><span data-stu-id="17864-125">In staying with the drivers license example, one of the methods is "Revoke" because the department of motor vehicles can revoke your drivers license.</span></span>

### <a name="properties"></a><span data-ttu-id="17864-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="17864-126">Properties</span></span>

<span data-ttu-id="17864-127">В следующем примере будут получены сведения о службе времени Windows, работающей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17864-127">In the following example, I'll retrieve information about the Windows Time service running on my computer.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="17864-128">**Status**, **Name** и **DisplayName** — это примеры свойств, как показано в предыдущем наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="17864-128">**Status**, **Name**, and **DisplayName** are examples of properties as shown in the previous set of results.</span></span> <span data-ttu-id="17864-129">Свойство **Status** имеет значение `Running`, свойство **Name** имеет значение `w32time`, а свойство **DisplayName** имеет значение `Windows Time`.</span><span class="sxs-lookup"><span data-stu-id="17864-129">The value for the **Status** property is `Running`, the value for the **Name** property is `w32time`, and the value for **DisplayName** is `Windows Time`.</span></span>

<span data-ttu-id="17864-130">Теперь эта же команда будет передана в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-130">Now I'll pipe that same command to `Get-Member`:</span></span>

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="17864-131">В первой строке результатов в предыдущем примере содержится часть очень важных сведений.</span><span class="sxs-lookup"><span data-stu-id="17864-131">The first line of the results in the previous example contains one piece of very important information.</span></span> <span data-ttu-id="17864-132">**TypeName** сообщает, какой тип объекта был возвращен.</span><span class="sxs-lookup"><span data-stu-id="17864-132">**TypeName** tells you what type of object was returned.</span></span> <span data-ttu-id="17864-133">В этом примере был возвращен объект **System.ServiceProcess.ServiceController**.</span><span class="sxs-lookup"><span data-stu-id="17864-133">In this example, a **System.ServiceProcess.ServiceController** object was returned.</span></span> <span data-ttu-id="17864-134">Он часто сокращается до части свойства **TypeName**, идущей сразу после последней точки. В этом примере — **ServiceController**.</span><span class="sxs-lookup"><span data-stu-id="17864-134">This is often abbreviated as the portion of the **TypeName** just after the last period; **ServiceController** in this example.</span></span>

<span data-ttu-id="17864-135">После того как будет известен тип объекта, создаваемый командой, эти сведения можно использовать для поиска команд, которые принимают этот тип объекта в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="17864-135">Once you know what type of object a command produces, you can use this information to find commands that accept that type of object as input.</span></span>

```powershell
Get-Command -ParameterType ServiceController
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
```

<span data-ttu-id="17864-136">У всех этих команд есть параметр, принимающий тип объекта **ServiceController** по конвейеру, входным данным параметра или обоим условиям.</span><span class="sxs-lookup"><span data-stu-id="17864-136">All of those commands have a parameter that accepts a **ServiceController** object type by pipeline, parameter input, or both.</span></span>

<span data-ttu-id="17864-137">Обратите внимание, что доступны и дополнительные свойства, а не только те, которые отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17864-137">Notice that there are more properties than are displayed by default.</span></span> <span data-ttu-id="17864-138">Хотя эти дополнительные свойства не отображаются по умолчанию, их можно выбрать из конвейера путем передачи команды в командлет `Select-Object` и использования параметра **Property**.</span><span class="sxs-lookup"><span data-stu-id="17864-138">Although these additional properties aren't displayed by default, they can be selected from the pipeline by piping the command to the `Select-Object` cmdlet and using the **Property** parameter.</span></span> <span data-ttu-id="17864-139">В следующем примере все свойства выбираются путем передачи результатов `Get-Service` в `Select-Object` и указания подстановочного знака `*` в качестве значения параметра **Property**.</span><span class="sxs-lookup"><span data-stu-id="17864-139">The following example selects all of the properties by piping the results of `Get-Service` to `Select-Object` and specifying the `*` wildcard character as the value for the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

<span data-ttu-id="17864-140">Можно также выбрать конкретные свойства, указав список с разделителями-запятыми в качестве значения параметра **Property**.</span><span class="sxs-lookup"><span data-stu-id="17864-140">Specific properties can also be selected using a comma-separated list for the value of the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, Name, DisplayName, ServiceType
```

```Output
 Status Name    DisplayName        ServiceType
 ------ ----    -----------        -----------
Running w32time Windows Time Win32ShareProcess
```

<span data-ttu-id="17864-141">По умолчанию четыре свойства возвращаются в таблице, а пять или более — в списке.</span><span class="sxs-lookup"><span data-stu-id="17864-141">By default, four properties are returned in a table and five or more are returned in a list.</span></span> <span data-ttu-id="17864-142">Для переопределения количества свойств, отображаемых по умолчанию в таблице, некоторые команды используют пользовательское форматирование.</span><span class="sxs-lookup"><span data-stu-id="17864-142">Some commands use custom formatting to override how many properties are displayed by default in a table.</span></span>
<span data-ttu-id="17864-143">Существует несколько командлетов `Format-*`, которые можно использовать для переопределения этих значений по умолчанию вручную.</span><span class="sxs-lookup"><span data-stu-id="17864-143">There are several `Format-*` cmdlets that can be used to manually override these defaults.</span></span> <span data-ttu-id="17864-144">Самыми распространенными являются `Format-Table` и `Format-List`. Они будут рассматриваться в следующей главе.</span><span class="sxs-lookup"><span data-stu-id="17864-144">The most common ones are `Format-Table` and `Format-List`, both of which will be covered in an upcoming chapter.</span></span>

<span data-ttu-id="17864-145">При указании имен свойств с помощью `Select-Object` можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17864-145">Wildcard characters can be used when specifying the property names with `Select-Object`.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```powershell
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

<span data-ttu-id="17864-146">В предыдущем примере параметру **Property** было задано значение `Can*` для возврата всех свойств, начинающихся с `Can`.</span><span class="sxs-lookup"><span data-stu-id="17864-146">In the previous example, `Can*` was used as one of the values for the **Property** parameter to return all the properties that start with `Can`.</span></span> <span data-ttu-id="17864-147">К ним относятся **CanPauseAndContinue**, **CanShutdown** и **CanStop**.</span><span class="sxs-lookup"><span data-stu-id="17864-147">These include **CanPauseAndContinue**, **CanShutdown**, and **CanStop**.</span></span>

### <a name="methods"></a><span data-ttu-id="17864-148">Методы</span><span class="sxs-lookup"><span data-stu-id="17864-148">Methods</span></span>

<span data-ttu-id="17864-149">Метод — это действие, которое может быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="17864-149">Methods are an action that can be taken.</span></span> <span data-ttu-id="17864-150">Параметр **MemberType** позволяет сузить результаты `Get-Member` так, чтобы отображались только методы для `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="17864-150">Use the **MemberType** parameter to narrow down the results of `Get-Member` to only show the methods for `Get-Service`.</span></span>

```powershell
Get-Service -Name w32time | Get-Member -MemberType Method
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType Definition
----                      ---------- ----------
Close                     Method     void Close()
Continue                  Method     void Continue()
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type ...
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Equals                    Method     bool Equals(System.Object obj)
ExecuteCommand            Method     void ExecuteCommand(int command)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Pause                     Method     void Pause()
Refresh                   Method     void Refresh()
Start                     Method     void Start(), void Start(string[] args)
Stop                      Method     void Stop()
WaitForStatus             Method     void WaitForStatus(System.ServiceProcess.ServiceC...
```

<span data-ttu-id="17864-151">Как видите, методов довольно много.</span><span class="sxs-lookup"><span data-stu-id="17864-151">As you can see, there are many methods.</span></span> <span data-ttu-id="17864-152">Метод **Stop** можно использовать для остановки службы Windows.</span><span class="sxs-lookup"><span data-stu-id="17864-152">The **Stop** method can be used to stop a Windows service.</span></span>

```powershell
(Get-Service -Name w32time).Stop()
```

<span data-ttu-id="17864-153">Теперь убедитесь, что служба времени Windows действительно остановлена.</span><span class="sxs-lookup"><span data-stu-id="17864-153">Now to verify the Windows time service has indeed been stopped.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  w32time            Windows Time
```

<span data-ttu-id="17864-154">Я сам редко использую методы, но о них нужно знать.</span><span class="sxs-lookup"><span data-stu-id="17864-154">I rarely find myself using methods, but they're something you need to be aware of.</span></span> <span data-ttu-id="17864-155">Может возникнуть ситуация, когда вам встретится команда `Get-*`, не имеющая соответствующей команды для изменения этого элемента.</span><span class="sxs-lookup"><span data-stu-id="17864-155">There are times that you'll come across a `Get-*` command without a corresponding command to modify that item.</span></span>
<span data-ttu-id="17864-156">Зачастую выполнить действие для изменения элемента можно с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="17864-156">Often, a method can be used to perform an action that modifies it.</span></span> <span data-ttu-id="17864-157">Хорошим примером является командлет `Get-SqlAgentJob` в модуле PowerShell для SqlServer.</span><span class="sxs-lookup"><span data-stu-id="17864-157">The `Get-SqlAgentJob` cmdlet in the SqlServer PowerShell module is a good example of this.</span></span> <span data-ttu-id="17864-158">Модуль устанавливается в составе [SQL Server Management Studio (SSMS)][SMSS].</span><span class="sxs-lookup"><span data-stu-id="17864-158">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="17864-159">Соответствующий командлет `Set-*` отсутствует, но для выполнения той же задачи можно использовать метод.</span><span class="sxs-lookup"><span data-stu-id="17864-159">No corresponding `Set-*` cmdlet exists, but a method can be used to complete the same task.</span></span>

<span data-ttu-id="17864-160">Еще одна причина, по которой следует знать о методах, заключается в том, что многие новички считают, что команды `Get-*` не способны вызывать разрушительные изменения.</span><span class="sxs-lookup"><span data-stu-id="17864-160">Another reason to be aware of methods is that many beginners assume destructive changes can't be made with `Get-*` commands.</span></span> <span data-ttu-id="17864-161">Однако при неправильном применении эти команды на самом деле могут приводить к серьезным проблемам.</span><span class="sxs-lookup"><span data-stu-id="17864-161">But they indeed can cause serious problems if used inappropriately.</span></span>

<span data-ttu-id="17864-162">Оптимальным вариантом для выполнения действия будет использование командлета (если таковой существует).</span><span class="sxs-lookup"><span data-stu-id="17864-162">A better option is to use a cmdlet to perform the action if one exists.</span></span> <span data-ttu-id="17864-163">Запустите службу времени Windows, на этот раз с помощью командлета для запуска служб.</span><span class="sxs-lookup"><span data-stu-id="17864-163">Go ahead and start the Windows Time service, except this time use the cmdlet for starting services.</span></span>

```powershell
Get-Service -Name w32time | Start-Service -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="17864-164">По умолчанию `Start-Service` не возвращает никаких результатов, как и метод запуска `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="17864-164">By default, `Start-Service` doesn't return any results just like the start method of `Get-Service`.</span></span>
<span data-ttu-id="17864-165">Но одно из преимуществ использования командлета в том, что он несколько раз предлагает дополнительные функции, недоступные в методе.</span><span class="sxs-lookup"><span data-stu-id="17864-165">But one of the benefits of using a cmdlet is that many times the cmdlet offers additional functionality that isn't available with a method.</span></span> <span data-ttu-id="17864-166">В предыдущем примере использовался параметр **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="17864-166">In the previous example, the **PassThru** parameter was used.</span></span> <span data-ttu-id="17864-167">В результате командлет, который обычно не создает выходные данные, генерирует их.</span><span class="sxs-lookup"><span data-stu-id="17864-167">This causes a cmdlet that doesn't normally produce output, to produce output.</span></span>

<span data-ttu-id="17864-168">Будьте внимательны, делая предположения о выходных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="17864-168">Be careful with assumptions about the output of a cmdlet.</span></span> <span data-ttu-id="17864-169">Мы все знаем, что происходит, когда что-то предполагается.</span><span class="sxs-lookup"><span data-stu-id="17864-169">We all know what happens when you assume things.</span></span> <span data-ttu-id="17864-170">Я получу информацию о процессе PowerShell, выполняемом на компьютере Windows 10 с лабораторной средой.</span><span class="sxs-lookup"><span data-stu-id="17864-170">I'll retrieve information about the PowerShell process running on my Windows 10 lab environment computer.</span></span>

```powershell
Get-Process -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    922      48   107984     140552       2.84   9020   1 powershell

```

<span data-ttu-id="17864-171">Теперь эта же команда будет передана в Get-Member.</span><span class="sxs-lookup"><span data-stu-id="17864-171">Now I'll pipe that same command to Get-Member:</span></span>

```powershell
Get-Process -Name PowerShell | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
```

<span data-ttu-id="17864-172">Обратите внимание, что доступны дополнительные свойства, а не только те, которые отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17864-172">Notice that there are more properties listed than are displayed by default.</span></span> <span data-ttu-id="17864-173">Некоторые отображаемые свойства по умолчанию не отображаются как свойства при просмотре результатов `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-173">A number of the default properties displayed don't show up as properties when viewing the results of `Get-Member`.</span></span> <span data-ttu-id="17864-174">Это связано с тем, что многие из показанных значений, такие как `NPM(K)`, `PM(K)`, `WS(K)` и `CPU(s)`, являются вычисляемыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="17864-174">This is because many of the displayed values, such as `NPM(K)`, `PM(K)`, `WS(K)`, and `CPU(s)`, are calculated properties.</span></span> <span data-ttu-id="17864-175">Чтобы определить фактические имена свойств, необходимо передать команду в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-175">To determine the actual property names, the command must be piped to `Get-Member`.</span></span>

<span data-ttu-id="17864-176">Если команда не создает выходные данные, она не может быть передана в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-176">If a command does not produce output, it can't be piped to `Get-Member`.</span></span> <span data-ttu-id="17864-177">Так как команда `Start-Service` по умолчанию не выводит никаких выходных данных, при попытке передать ее в `Get-Member` возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="17864-177">Since `Start-Service` doesn't produce any output by default, it generates an error when you try to pipe it to `Get-Member`.</span></span>

```powershell
Start-Service -Name w32time | Get-Member
```

```Output
Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:31
+ Start-Service -Name w32time | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMembe
   rCommand
```

<span data-ttu-id="17864-178">Параметр **PassThru** можно указать с помощью командлета `Start-Service`, чтобы создать выходные данные, которые затем передаются в `Get-Member` без ошибок.</span><span class="sxs-lookup"><span data-stu-id="17864-178">The **PassThru** parameter can be specified with the `Start-Service` cmdlet make it produce output, which is then piped to `Get-Member` without error.</span></span>

```powershell
Start-Service -Name w32time -PassThru | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="17864-179">Для передачи в `Get-Member` команда должна создавать выходные данные на основе объекта.</span><span class="sxs-lookup"><span data-stu-id="17864-179">To be piped to `Get-Member`, a command must produce object-based output.</span></span>

```powershell
Get-Service -Name w32time | Out-Host | Get-Member
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time

Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:40
+ Get-Service -Name w32time | Out-Host | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMemberCommand
```

<span data-ttu-id="17864-180">`Out-Host` выполняет запись непосредственно на узел PowerShell, но не создает для конвейера выходные данные на основе объекта.</span><span class="sxs-lookup"><span data-stu-id="17864-180">`Out-Host` writes directly to the PowerShell host, but it doesn't produce object-based output for the pipeline.</span></span> <span data-ttu-id="17864-181">Поэтому ее нельзя передать в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-181">So it can't be piped to `Get-Member`.</span></span>

## <a name="active-directory"></a><span data-ttu-id="17864-182">Active Directory</span><span class="sxs-lookup"><span data-stu-id="17864-182">Active Directory</span></span>

> [!NOTE]
> <span data-ttu-id="17864-183">Для выполнения действий в этом разделе необходимы средства удаленного администрирования сервера, приведенные в разделе требований этой главы.</span><span class="sxs-lookup"><span data-stu-id="17864-183">The Remote Server Administration Tools listed in the requirements section of this chapter are required to complete this section.</span></span> <span data-ttu-id="17864-184">Кроме того, как отмечалось во введении к этой книге, компьютер Windows 10 с лабораторной средой должен входить в домен лабораторной среды.</span><span class="sxs-lookup"><span data-stu-id="17864-184">Also, as mentioned in the introduction to this book, your Windows 10 lab environment computer must be a member of the lab environment domain.</span></span>

<span data-ttu-id="17864-185">Используйте `Get-Command` с параметром **Module**, чтобы определить, какие команды были добавлены в состав модуля PowerShell для ActiveDirectory при установке средств удаленного администрирования сервера.</span><span class="sxs-lookup"><span data-stu-id="17864-185">Use `Get-Command` with the **Module** parameter to determine what commands were added as part of the ActiveDirectory PowerShell module when the remote server administration tools were installed.</span></span>

```powershell
Get-Command -Module ActiveDirectory
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-ADCentralAccessPolicyMember                    1.0.0.0    ActiveDi...
Cmdlet          Add-ADComputerServiceAccount                       1.0.0.0    ActiveDi...
Cmdlet          Add-ADDomainControllerPasswordReplicationPolicy    1.0.0.0    ActiveDi...
Cmdlet          Add-ADFineGrainedPasswordPolicySubject             1.0.0.0    ActiveDi...
Cmdlet          Add-ADGroupMember                                  1.0.0.0    ActiveDi...
Cmdlet          Add-ADPrincipalGroupMembership                     1.0.0.0    ActiveDi...
Cmdlet          Add-ADResourcePropertyListMember                   1.0.0.0    ActiveDi...
Cmdlet          Clear-ADAccountExpiration                          1.0.0.0    ActiveDi...
Cmdlet          Clear-ADClaimTransformLink                         1.0.0.0    ActiveDi...
Cmdlet          Disable-ADAccount                                  1.0.0.0    ActiveDi...
...
```

<span data-ttu-id="17864-186">В модуль PowerShell для ActiveDirectory было добавлено всего 147 команд.</span><span class="sxs-lookup"><span data-stu-id="17864-186">A total of 147 commands were added as part of the ActiveDirectory PowerShell module.</span></span> <span data-ttu-id="17864-187">Некоторые команды по умолчанию возвращают только часть доступных свойств.</span><span class="sxs-lookup"><span data-stu-id="17864-187">Some commands of these commands only return a portion of the available properties by default.</span></span>

<span data-ttu-id="17864-188">Вы заметили что-то необычное в именах команд в этом модуле?</span><span class="sxs-lookup"><span data-stu-id="17864-188">Did you notice anything different about the names of the commands in this module?</span></span> <span data-ttu-id="17864-189">В именной части команд есть префикс AD.</span><span class="sxs-lookup"><span data-stu-id="17864-189">The noun portion of the commands has an AD prefix.</span></span> <span data-ttu-id="17864-190">Это распространенное явление для команд в большинстве модулей.</span><span class="sxs-lookup"><span data-stu-id="17864-190">This is common to see on the commands of most modules.</span></span> <span data-ttu-id="17864-191">Префикс предназначен для предотвращения конфликтов имен.</span><span class="sxs-lookup"><span data-stu-id="17864-191">The prefix is designed to help prevent naming conflicts.</span></span>

```powershell
Get-ADUser -Identity mike | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name              MemberType            Definition
----              ----------            ----------
Contains          Method                bool Contains(string propertyName)
Equals            Method                bool Equals(System.Object obj)
GetEnumerator     Method                System.Collections.IDictionaryEnumerator GetEn...
GetHashCode       Method                int GetHashCode()
GetType           Method                type GetType()
ToString          Method                string ToString()
Item              ParameterizedProperty Microsoft.ActiveDirectory.Management.ADPropert...
DistinguishedName Property              System.String DistinguishedName {get;set;}
Enabled           Property              System.Boolean Enabled {get;set;}
GivenName         Property              System.String GivenName {get;set;}
Name              Property              System.String Name {get;}
ObjectClass       Property              System.String ObjectClass {get;set;}
ObjectGUID        Property              System.Nullable`1[[System.Guid, mscorlib, Vers...
SamAccountName    Property              System.String SamAccountName {get;set;}
SID               Property              System.Security.Principal.SecurityIdentifier S...
Surname           Property              System.String Surname {get;set;}
UserPrincipalName Property              System.String UserPrincipalName {get;set;}
```

<span data-ttu-id="17864-192">Даже если вы лишь смутно знакомы с Active Directory, вам, вероятно, известно, что учетная запись пользователя имеет больше свойств, чем показано в этом примере.</span><span class="sxs-lookup"><span data-stu-id="17864-192">Even if you're only vaguely familiar with Active Directory, you're probably aware that a user account has more properties than are shown in this example.</span></span>

<span data-ttu-id="17864-193">У командлета `Get-ADUser` есть параметр **Properties**, который используется для указания дополнительных возвращаемых свойств (не заданных по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="17864-193">The `Get-ADUser` cmdlet has a **Properties** parameter that is used to specify the additional (non-default) properties you want to return.</span></span> <span data-ttu-id="17864-194">Если указать подстановочный знак `*`, будут возвращены все свойства.</span><span class="sxs-lookup"><span data-stu-id="17864-194">Specifying the `*` wildcard character returns all of them.</span></span>

```powershell
Get-ADUser -Identity mike -Properties * | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name                                 MemberType            Definition
----                                 ----------            ----------
Contains                             Method                bool Contains(string proper...
Equals                               Method                bool Equals(System.Object obj)
GetEnumerator                        Method                System.Collections.IDiction...
GetHashCode                          Method                int GetHashCode()
GetType                              Method                type GetType()
ToString                             Method                string ToString()
Item                                 ParameterizedProperty Microsoft.ActiveDirectory.M...
AccountExpirationDate                Property              System.DateTime AccountExpi...
accountExpires                       Property              System.Int64 accountExpires...
AccountLockoutTime                   Property              System.DateTime AccountLock...
AccountNotDelegated                  Property              System.Boolean AccountNotDe...
AllowReversiblePasswordEncryption    Property              System.Boolean AllowReversi...
AuthenticationPolicy                 Property              Microsoft.ActiveDirectory.M...
AuthenticationPolicySilo             Property              Microsoft.ActiveDirectory.M...
BadLogonCount                        Property              System.Int32 BadLogonCount ...
badPasswordTime                      Property              System.Int64 badPasswordTim...
badPwdCount                          Property              System.Int32 badPwdCount {g...
CannotChangePassword                 Property              System.Boolean CannotChange...
CanonicalName                        Property              System.String CanonicalName...
Certificates                         Property              Microsoft.ActiveDirectory.M...
City                                 Property              System.String City {get;set;}
CN                                   Property              System.String CN {get;}
codePage                             Property              System.Int32 codePage {get;...
Company                              Property              System.String Company {get;...
CompoundIdentitySupported            Property              Microsoft.ActiveDirectory.M...
Country                              Property              System.String Country {get;...
countryCode                          Property              System.Int32 countryCode {g...
Created                              Property              System.DateTime Created {get;}
createTimeStamp                      Property              System.DateTime createTimeS...
Deleted                              Property              System.Boolean Deleted {get;}
Department                           Property              System.String Department {g...
Description                          Property              System.String Description {...
DisplayName                          Property              System.String DisplayName {...
DistinguishedName                    Property              System.String Distinguished...
Division                             Property              System.String Division {get...
DoesNotRequirePreAuth                Property              System.Boolean DoesNotRequi...
dSCorePropagationData                Property              Microsoft.ActiveDirectory.M...
EmailAddress                         Property              System.String EmailAddress ...
EmployeeID                           Property              System.String EmployeeID {g...
EmployeeNumber                       Property              System.String EmployeeNumbe...
Enabled                              Property              System.Boolean Enabled {get...
Fax                                  Property              System.String Fax {get;set;}
GivenName                            Property              System.String GivenName {ge...
HomeDirectory                        Property              System.String HomeDirectory...
HomedirRequired                      Property              System.Boolean HomedirRequi...
HomeDrive                            Property              System.String HomeDrive {ge...
HomePage                             Property              System.String HomePage {get...
HomePhone                            Property              System.String HomePhone {ge...
Initials                             Property              System.String Initials {get...
instanceType                         Property              System.Int32 instanceType {...
isDeleted                            Property              System.Boolean isDeleted {g...
KerberosEncryptionType               Property              Microsoft.ActiveDirectory.M...
LastBadPasswordAttempt               Property              System.DateTime LastBadPass...
LastKnownParent                      Property              System.String LastKnownPare...
lastLogoff                           Property              System.Int64 lastLogoff {ge...
lastLogon                            Property              System.Int64 lastLogon {get...
LastLogonDate                        Property              System.DateTime LastLogonDa...
lastLogonTimestamp                   Property              System.Int64 lastLogonTimes...
LockedOut                            Property              System.Boolean LockedOut {g...
logonCount                           Property              System.Int32 logonCount {ge...
LogonWorkstations                    Property              System.String LogonWorkstat...
Manager                              Property              System.String Manager {get;...
MemberOf                             Property              Microsoft.ActiveDirectory.M...
MNSLogonAccount                      Property              System.Boolean MNSLogonAcco...
MobilePhone                          Property              System.String MobilePhone {...
Modified                             Property              System.DateTime Modified {g...
modifyTimeStamp                      Property              System.DateTime modifyTimeS...
msDS-User-Account-Control-Computed   Property              System.Int32 msDS-User-Acco...
Name                                 Property              System.String Name {get;}
nTSecurityDescriptor                 Property              System.DirectoryServices.Ac...
ObjectCategory                       Property              System.String ObjectCategor...
ObjectClass                          Property              System.String ObjectClass {...
ObjectGUID                           Property              System.Nullable`1[[System.G...
objectSid                            Property              System.Security.Principal.S...
Office                               Property              System.String Office {get;s...
OfficePhone                          Property              System.String OfficePhone {...
Organization                         Property              System.String Organization ...
OtherName                            Property              System.String OtherName {ge...
PasswordExpired                      Property              System.Boolean PasswordExpi...
PasswordLastSet                      Property              System.DateTime PasswordLas...
PasswordNeverExpires                 Property              System.Boolean PasswordNeve...
PasswordNotRequired                  Property              System.Boolean PasswordNotR...
POBox                                Property              System.String POBox {get;set;}
PostalCode                           Property              System.String PostalCode {g...
PrimaryGroup                         Property              System.String PrimaryGroup ...
primaryGroupID                       Property              System.Int32 primaryGroupID...
PrincipalsAllowedToDelegateToAccount Property              Microsoft.ActiveDirectory.M...
ProfilePath                          Property              System.String ProfilePath {...
ProtectedFromAccidentalDeletion      Property              System.Boolean ProtectedFro...
pwdAnswer                            Property              System.String pwdAnswer {ge...
pwdLastSet                           Property              System.Int64 pwdLastSet {ge...
pwdQuestion                          Property              System.String pwdQuestion {...
SamAccountName                       Property              System.String SamAccountNam...
sAMAccountType                       Property              System.Int32 sAMAccountType...
ScriptPath                           Property              System.String ScriptPath {g...
sDRightsEffective                    Property              System.Int32 sDRightsEffect...
ServicePrincipalNames                Property              Microsoft.ActiveDirectory.M...
SID                                  Property              System.Security.Principal.S...
SIDHistory                           Property              Microsoft.ActiveDirectory.M...
SmartcardLogonRequired               Property              System.Boolean SmartcardLog...
sn                                   Property              System.String sn {get;set;}
State                                Property              System.String State {get;set;}
StreetAddress                        Property              System.String StreetAddress...
Surname                              Property              System.String Surname {get;...
Title                                Property              System.String Title {get;set;}
TrustedForDelegation                 Property              System.Boolean TrustedForDe...
TrustedToAuthForDelegation           Property              System.Boolean TrustedToAut...
UseDESKeyOnly                        Property              System.Boolean UseDESKeyOnl...
userAccountControl                   Property              System.Int32 userAccountCon...
userCertificate                      Property              Microsoft.ActiveDirectory.M...
UserPrincipalName                    Property              System.String UserPrincipal...
uSNChanged                           Property              System.Int64 uSNChanged {get;}
uSNCreated                           Property              System.Int64 uSNCreated {get;}
whenChanged                          Property              System.DateTime whenChanged...
whenCreated                          Property              System.DateTime whenCreated...
```

<span data-ttu-id="17864-195">Теперь это выглядит примерно так.</span><span class="sxs-lookup"><span data-stu-id="17864-195">Now that looks more like it.</span></span>

<span data-ttu-id="17864-196">Можете ли вы представить себе причину, по которой свойства учетной записи пользователя Active Directory будут настолько ограничены по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="17864-196">Can you think of a reason why the properties of an Active Directory user account would be so limited by default?</span></span> <span data-ttu-id="17864-197">Представьте, что возвращены все свойства для каждой учетной записи пользователя в производственной среде Active Directory.</span><span class="sxs-lookup"><span data-stu-id="17864-197">Imagine if you returned every property for every user account in your production Active Directory environment.</span></span> <span data-ttu-id="17864-198">Подумайте о снижении производительности не только самих контроллеров домена, но и сети.</span><span class="sxs-lookup"><span data-stu-id="17864-198">Think of the performance degradation that you could cause, not only to the domain controllers themselves, but also to your network.</span></span> <span data-ttu-id="17864-199">Маловероятно, что вам потребуются все свойства.</span><span class="sxs-lookup"><span data-stu-id="17864-199">It's doubtful that you'll actually need every property anyway.</span></span> <span data-ttu-id="17864-200">Возврат всех свойств для одной учетной записи пользователя вполне допустим, когда вы пытаетесь определить, какие свойства существуют.</span><span class="sxs-lookup"><span data-stu-id="17864-200">Returning all of the properties for a single user account is perfectly acceptable when you're trying to determine what properties exist.</span></span>

<span data-ttu-id="17864-201">Нередко при создании прототипов команды запускаются несколько раз.</span><span class="sxs-lookup"><span data-stu-id="17864-201">It's not uncommon to run a command many times when prototyping it.</span></span> <span data-ttu-id="17864-202">Если вам нужно выполнить огромный запрос, сделайте это один раз и сохраните результаты в переменную.</span><span class="sxs-lookup"><span data-stu-id="17864-202">If you're going to perform some huge query, query it once and store the results in a variable.</span></span> <span data-ttu-id="17864-203">Затем вы сможете работать с содержимым переменной, а не запускать ресурсоемкий запрос многократно.</span><span class="sxs-lookup"><span data-stu-id="17864-203">Then work with the contents of the variable instead of repeatedly using some expensive query.</span></span>

```powershell
$Users = Get-ADUser -Identity mike -Properties *
```

<span data-ttu-id="17864-204">Используйте содержимое переменной `$Users`, а не выполняйте предыдущую команду несколько раз.</span><span class="sxs-lookup"><span data-stu-id="17864-204">Use the contents of the `$Users` variable instead of running the previous command numerous times.</span></span>
<span data-ttu-id="17864-205">Помните, что содержимое переменной не обновляется при внесении изменений для этого пользователя в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="17864-205">Keep in mind that the contents of the variable aren't updated when changes are made to that user in Active Directory.</span></span>

<span data-ttu-id="17864-206">Чтобы определить доступные свойства, переменную `$Users` можно передать в `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="17864-206">You could pipe the `$Users` variable to `Get-Member` to discover the available properties.</span></span>

```powershell
$Users | Get-Member
```

<span data-ttu-id="17864-207">Затем выберите отдельные свойства, передав `$Users` в `Select-Object`. При этом запрос в Active Directory отправляется не более одного раза.</span><span class="sxs-lookup"><span data-stu-id="17864-207">Then select the individual properties by piping `$Users` to `Select-Object`, all without ever having to query Active Directory more than one time.</span></span>

```powershell
$Users | Select-Object -Property Name, LastLogonDate, LastBadPasswordAttempt
```

<span data-ttu-id="17864-208">Чтобы запросить Active Directory несколько раз, воспользуйтесь параметром **Properties** для указания необходимых свойств, не являющихся заданными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17864-208">If you are going to query Active Directory more than once, use the **Properties** parameter to specify any non-default properties you want.</span></span>

```powershell
Get-ADUser -Identity mike -Properties LastLogonDate, LastBadPasswordAttempt
```

```Output
DistinguishedName      : CN=Mike F. Robbins,OU=Sales,DC=mikefrobbins,DC=com
Enabled                : True
GivenName              : Mike
LastBadPasswordAttempt : 2/4/2017 10:46:15 AM
LastLogonDate          : 2/18/2017 12:45:14 AM
Name                   : Mike F. Robbins
ObjectClass            : user
ObjectGUID             : a82a8c58-1332-4a57-a6e2-68e0c750ea56
SamAccountName         : mike
SID                    : S-1-5-21-2989741381-570885089-3319121794-1108
Surname                : Robbins
UserPrincipalName      : miker@mikefrobbins.com
```

## <a name="summary"></a><span data-ttu-id="17864-209">Сводка</span><span class="sxs-lookup"><span data-stu-id="17864-209">Summary</span></span>

<span data-ttu-id="17864-210">В этой главе вы узнали, как определить тип объекта, выводимый командой, как определить доступные для команды свойства и методы, а также то, как работать с командами, которые ограничивают свойства, возвращаемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17864-210">In this chapter, you've learned how to determine what type of object a command produces, how to determine what properties and methods are available for a command, and how to work with commands that limit the properties that are returned by default.</span></span>

## <a name="review"></a><span data-ttu-id="17864-211">Просмотр</span><span class="sxs-lookup"><span data-stu-id="17864-211">Review</span></span>

1. <span data-ttu-id="17864-212">Какой тип объекта создает командлет `Get-Process`?</span><span class="sxs-lookup"><span data-stu-id="17864-212">What type of object does the `Get-Process` cmdlet produce?</span></span>
1. <span data-ttu-id="17864-213">Как определить доступные для команды свойства?</span><span class="sxs-lookup"><span data-stu-id="17864-213">How do you determine what the available properties are for a command?</span></span>
1. <span data-ttu-id="17864-214">Если есть команда для получения объекта, но не для его задания, что следует проверить?</span><span class="sxs-lookup"><span data-stu-id="17864-214">If a command exists for getting something but not for setting the same thing, what should you check for?</span></span>
1. <span data-ttu-id="17864-215">Как сделать так, чтобы определенные команды, которые не создают выходные данные по умолчанию, выводили результаты?</span><span class="sxs-lookup"><span data-stu-id="17864-215">How can certain commands that don't produce output by default be made to produce output?</span></span>
1. <span data-ttu-id="17864-216">Если вы собираетесь работать с результатами команды, которая выводит огромное количество выходных данных, что следует принять во внимание?</span><span class="sxs-lookup"><span data-stu-id="17864-216">If you're going to be working with the results of a command that produces an enormous amount of output, what should you consider doing?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="17864-217">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="17864-217">Recommended Reading</span></span>

- <span data-ttu-id="17864-218">[Get-Member][]</span><span class="sxs-lookup"><span data-stu-id="17864-218">[Get-Member][]</span></span>
- <span data-ttu-id="17864-219">[Просмотр структуры объектов (Get-Member)][]</span><span class="sxs-lookup"><span data-stu-id="17864-219">[Viewing Object Structure (Get-Member)][]</span></span>
- <span data-ttu-id="17864-220">[about_Objects][]</span><span class="sxs-lookup"><span data-stu-id="17864-220">[about_Objects][]</span></span>
- <span data-ttu-id="17864-221">[about_Properties][]</span><span class="sxs-lookup"><span data-stu-id="17864-221">[about_Properties][]</span></span>
- <span data-ttu-id="17864-222">[about_Methods][]</span><span class="sxs-lookup"><span data-stu-id="17864-222">[about_Methods][]</span></span>
- <span data-ttu-id="17864-223">[No PowerShell Cmdlet to Start or Stop Something? Don’t Forget to Check for Methods on the Get Cmdlets][use-methods] (Нет командлета для запуска или остановки службы? Вспомните о методах для командлетов Get)</span><span class="sxs-lookup"><span data-stu-id="17864-223">[No PowerShell Cmdlet to Start or Stop Something? Don’t Forget to Check for Methods on the Get Cmdlets][use-methods]</span></span>

<!-- link references -->
[RSAT для Windows]: https://support.microsoft.com/help/2693643
[RSAT for Windows]: https://support.microsoft.com/help/2693643
[Модули управления Windows]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Windows Management modules]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Get-Member]: /powershell/module/microsoft.powershell.utility/get-member
[Просмотр структуры объектов (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[Viewing Object Structure (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[about_Objects]: /powershell/module/microsoft.powershell.core/about/about_objects
[about_Properties]: /powershell/module/microsoft.powershell.core/about/about_properties
[about_Methods]: /powershell/module/microsoft.powershell.core/about/about_methods
[use-methods]: https://mikefrobbins.com/2016/12/15/no-powershell-cmdlet-to-start-or-stop-something-dont-forget-to-check-for-methods-on-the-get-cmdlets/
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms

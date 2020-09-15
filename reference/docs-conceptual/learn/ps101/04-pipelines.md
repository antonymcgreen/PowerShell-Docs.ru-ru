---
title: Однострочные элементы кода и конвейеры
description: Однострочный элемент кода PowerShell — это один непрерывный конвейер, содержащий несколько команд, который позволяет выполнять одну задачу.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: b8fd45e5e5dc408754ebac015757ef4241428978
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633351"
---
# <a name="chapter-4---one-liners-and-the-pipeline"></a>Глава 4. Однострочные элементы кода и конвейеры

На начальном этапе изучения PowerShell, если мне не удавалось выполнить задачу с помощью PowerShell, я возвращался к графическому интерфейсу. Со временем я создал собственные техники написания сценариев, функций и модулей. Не пытайтесь углубляться в изучение сложных примеров, которые можно увидеть в Интернете. Сразу экспертами PowerShell не становятся. Все мы когда-то были начинающими пользователями.

Тем из вас, кто еще использует графический интерфейс для администрирования, я советую установить средства управления на рабочей станции администратора и управлять серверами удаленно. В этом случае не важно, работает ли на сервере графический интерфейс пользователя или установка основных серверных компонентов операционной системы.
Это поможет вам подготовиться к удаленному управлению серверами с помощью PowerShell.

Как говорилось и в предыдущих главах, обязательно следуйте инструкциям на компьютере с Windows 10 в лабораторной среде.

## <a name="one-liners"></a>Однострочные элементы кода

Однострочный элемент кода PowerShell — это один непрерывный конвейер, а не обязательно команда, которая приведена на одной физической строке. Не все команды, приведенные на одной физической строке, являются однострочным элементом кода.

Несмотря на то что следующая команда приведена на нескольких физических строках, она считается однострочным элементом кода PowerShell, потому что является одним непрерывным конвейером. Ее можно было записать на одной физической строке, но я выбрал разрыв строки рядом с вертикальной чертой. Вертикальная черта — один из символов, в котором допускается использовать естественный разрыв строки в PowerShell.

```powershell
Get-Service |
  Where-Object CanPauseAndContinue -eq $true |
    Select-Object -Property *
```

```Output
Name                : LanmanWorkstation
RequiredServices    : {NSI, MRxSmb20, Bowser}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Workstation
DependentServices   : {SessionEnv, Netlogon, Browser}
MachineName         : .
ServiceName         : LanmanWorkstation
ServicesDependedOn  : {NSI, MRxSmb20, Bowser}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : Netlogon
RequiredServices    : {LanmanWorkstation}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Netlogon
DependentServices   : {}
MachineName         : .
ServiceName         : Netlogon
ServicesDependedOn  : {LanmanWorkstation}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : vmicheartbeat
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Heartbeat Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicheartbeat
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmickvpexchange
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Data Exchange Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmickvpexchange
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicrdv
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Remote Desktop Virtualization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicrdv
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicshutdown
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Guest Shutdown Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicshutdown
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmictimesync
RequiredServices    : {VmGid}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Time Synchronization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmictimesync
ServicesDependedOn  : {VmGid}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicvss
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Volume Shadow Copy Requestor
DependentServices   : {}
MachineName         : .
ServiceName         : vmicvss
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : Winmgmt
RequiredServices    : {RPCSS}
CanPauseAndContinue : True
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Management Instrumentation
DependentServices   : {wscsvc, NcaSvc, iphlpsvc}
MachineName         : .
ServiceName         : Winmgmt
ServicesDependedOn  : {RPCSS}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :
```

Естественные разрывы строк могут встречаться в часто используемых символах, включая запятую (`,`) и открывающие квадратные скобки (`[`), фигурные скобки (`{`) и круглые скобки (`(`). К другим, менее распространенным символам, относятся точка с запятой (`;`), знак равенства (`=`), а также открывающие одинарные и двойные кавычки (`'`, `"`).

Использование обратной галочки (`` ` ``) или знака ударения в качестве символа продолжения строки является спорным. Я советую стараться не использовать эти символы, если это вообще возможно. Часто мне встречаются команды PowerShell, написанные с помощью обратной галочки, сразу за естественным символом разрыва строки.
Она там абсолютна не нужна.

```powershell
Get-Service -Name w32time |
>> Select-Object -Property *
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

Команды, показанные в предыдущих двух примерах, стабильно работают в консоли PowerShell. Но если вы запустите их в области консоли интегрированной среды сценариев PowerShell, они создадут ошибку. В области консоли интегрированной среды сценариев PowerShell не предполагается, что остальная часть команды будет включена на следующей строке, как в консоли PowerShell. Чтобы избежать этой проблемы в области консоли интегрированной среды сценариев PowerShell, используйте сочетание клавиш <kbd>Shift</kbd>+<kbd>ВВОД</kbd> вместо только клавиши <kbd>ВВОД</kbd>, когда продолжаете писать команду в другой строке.

Следующий пример не является однострочным элементом кода PowerShell, так как он не является одним непрерывным конвейером. Это две отдельные команды в одной строке, разделенные точкой с запятой.

```powershell
$Service = 'w32time'; Get-Service -Name $Service
```

```powershell
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Во многих языках программирования и сценариев необходимо использовать точку с запятой в конце каждой строки. Хотя их можно использовать таким образом в PowerShell, мы не советуем это делать, потому что эти символы не нужны.

## <a name="filtering-left"></a>Фильтрация по левому краю

Результаты команд, приведенные в этой главе, отфильтрованы по подмножеству. Например, `Get-Service` использовался с параметром **Name** для фильтрации списка служб, которые были возвращены только службе времени Windows.

В конвейере всегда нужно как можно раньше отфильтровать результаты по параметрам поиска. Это выполняется с помощью параметров в первой команде или той, которая расположена в крайнем левом углу.
Иногда этот способ называется _фильтрация слева_.

В следующем примере используется параметр **Name** `Get-Service` для немедленной фильтрации результатов только в службе времени Windows.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Нередко встречаются примеры, в которых команда передается `Where-Object` для выполнения фильтрации.

```powershell
Get-Service | Where-Object Name -eq w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  W32Time            Windows Time
```

В первом примере фильтрация выполняется в источнике и результаты возвращаются только для службы времени Windows.
Во втором примере возвращаются все службы, а затем они передаются другой команде для выполнения фильтрации. Хотя это может быть не так важно в следующем примере, но представьте, что вы запрашиваете список пользователей Active Directory. Вы точно хотите вернуть данные для нескольких тысяч учетных записей пользователей из Active Directory только для передачи их в другую команду, которая фильтрует учетные записи в небольшом подмножестве? Я советую всегда выполнять фильтрацию по левому краю, даже если это кажется неважным. Вы привыкнете использовать этот способ и будете выполнять фильтрацию по левому краю автоматически, когда это действительно важно.

Однажды мне кто-то сказал, что порядок, в котором указываются команды, не имеет значения. Это далеко от истины. Порядок, в котором указываются команды, действительно важен при выполнении фильтрации. Например, рассмотрим ситуацию, при котором вы используете `Select-Object`, чтобы выбрать только несколько свойств, и `Where-Object` для фильтрации по свойствам, которые не будут находиться в выделенном фрагменте. В этом сценарии фильтрация должна выполняться первой, иначе свойство не будет существовать в конвейере при попытке выполнить фильтрацию.

```powershell
Get-Service |
Select-Object -Property DisplayName, Running, Status |
Where-Object CanPauseAndContinue
```

Команда в предыдущем примере не возвращает результаты, так как свойство **CanStopAndContinue** не существует при передаче результатов из `Select-Object` в `Where-Object`. Именно это свойство было "не выбрано". По сути, оно было отфильтровано. Обратная последовательность `Select-Object` и `Where-Object` выдает нужные результаты.

```powershell
Get-Service |
Where-Object CanPauseAndContinue |
Select-Object -Property DisplayName, Status
```

```Output
DisplayName                                    Status
-----------                                    ------
Workstation                                    Running
Netlogon                                       Running
Hyper-V Heartbeat Service                      Running
Hyper-V Data Exchange Service                  Running
Hyper-V Remote Desktop Virtualization Service  Running
Hyper-V Guest Shutdown Service                 Running
Hyper-V Time Synchronization Service           Running
Hyper-V Volume Shadow Copy Requestor           Running
Windows Management Instrumentation             Running
```

## <a name="the-pipeline"></a>Конвейер

Как вы уже видели во многих примерах, показанных до настоящего момента в этом пособии, выходные данные одной команды можно несколько раз использовать в качестве входных данных для другой команды. В главе 3 `Get-Member` использовался для определения типа объекта, который создает команда. Кроме того, в этой же главе показано использование параметра **ParameterType** для `Get-Command`, которое позволяет определить команды, принявшие этот тип входных данных, хотя это необязательно выполняется входными данными конвейера.

В зависимости от того, насколько полезна команда, она может включать раздел **INPUTS** и **OUTPUTS**.

```powershell
help Stop-Service -Full
```

```Output
...
INPUTS
    System.ServiceProcess.ServiceController, System.String
        You can pipe a service object or a string that contains the name of a service
        to this cmdlet.

OUTPUTS
    None, System.ServiceProcess.ServiceController
        This cmdlet generates a System.ServiceProcess.ServiceController object that
        represents the service, if you use the PassThru parameter. Otherwise, this
        cmdlet does not generate any output.
...
```

В предыдущих результатах отображается только соответствующий раздел справки. Как вы видите, в разделе **INPUTS** указано, что объект **ServiceController** или **String** может передаваться командлету `Stop-Service`. Объект не сообщает, какие параметры принимают этот тип входных данных. Проще всего определить эти данные при просмотре разных параметров в полной версии справки для командлета `Stop-Service`.

```powershell
help Stop-Service -Full
```

```powershell
...
-DisplayName <String[]>
    Specifies the display names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false

-InputObject <ServiceController[]>
    Specifies ServiceController objects that represent the services to stop. Enter a
    variable that contains the objects, or type a command or expression that gets the
    objects.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByValue)
    Accept wildcard characters?  false

-Name <String[]>
    Specifies the service names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  false
...
```

Еще раз замечу, что в предыдущем наборе результатов я показал только соответствующую часть справки. Обратите внимание, что параметр **DisplayName** не принимает входные данные конвейера, параметр **InputObject** принимает входные данные конвейера **по значению** для объектов **ServiceController**, а параметр **Name** принимает входные данные конвейера **по значению** для объектов **строки**. Кроме того, он принимает входные данные конвейера **по имени свойства**.

Если параметр принимает входные данные конвейера как по имени свойства, так и по значению, он всегда пытается сначала принять их **по значению**. Если параметру не удается принять данные **по значению**, он пытается принять их **по имени свойства**. Вариант **по значению** не совсем точный. Я предпочитаю называть его **по типу**. Это означает, что, если вы передаете результаты команды, которая создает тип объекта **ServiceController** для `Stop-Service`, он привязывает эти входные данные к параметру **InputObject**. Но если вы передаете результаты команды, которая создает выходные данные **String** в `Stop-Service`, объект привязывает их к параметру **Name**. Если вы передаете результаты команды, которая не создает объект **ServiceController** или **String** для `Stop-Service`, но при этом создает выходные данные, содержащие свойство с именем **Name**, объект привязывает свойство **Name** из выходных данных к параметру **Name** для `Stop-Service`.

Определите, какой тип выходных данных создает команда `Get-Service`.

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController
```

`Get-Service` создает тип объекта ServiceController.

Как вы уже видели в справке, параметр **InputObject** для `Stop-Service` принимает объекты **ServiceController** через конвейер **по значению** (по типу). Это означает, что, когда результаты командлета `Get-Service` передаются в `Stop-Service`, они привязываются к параметру **InputObject** для `Stop-Service`.

```powershell
Get-Service -Name w32time | Stop-Service
```

Теперь можно попробовать ввести строку. Передайте `w32time` в `Get-Member`, только чтобы подтвердить, что это строка.

```powershell
'w32time' | Get-Member
```

```Output
   TypeName: System.String
```

Как уже было показано в справке, передача строки в `Stop-Service` привязывает ее **по значению** к параметру **Name** для `Stop-Service`. Проверьте это, передав `w32time` в `Stop-Service`.

```powershell
'w32time' | Stop-Service
```

Заметьте, что в предыдущем примере я использовал одинарные кавычки вокруг строки `w32time`. В PowerShell вы должны всегда использовать одинарные кавычки вместо двойных, если только содержимое строки в кавычках не содержит переменную, которая должна быть расширена до фактического значения. С помощью одинарных кавычек средству PowerShell не нужно анализировать содержимое, содержащееся в кавычках, поэтому ваш код будет выполняться быстрее.

Создайте пользовательский объект для проверки входных данных конвейера по имени свойства для параметра **Name** в `Stop-Service`.

```powershell
$CustomObject = [pscustomobject]@{
 Name = 'w32time'
 }
```

Содержимое переменной **CustomObject** является типом объекта **PSCustomObject** и содержит свойство с именем **Name**.

```powershell
$CustomObject | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty string Name=w32time
```

Если бы вы должны были заключить переменную `$CustomObject` в кавычки, вам бы пришлось использовать двойные кавычки.
В противном случае при использовании одинарных кавычек строковый литерал `$CustomObject` передается в `Get-Member` вместо значения, содержащегося в переменной.

Хотя передача содержимого `$CustomObject` в командлет `Stop-Service` привязывается к параметру **Name**, на этот раз он привязывается **по имени свойства**, а не **по значению**, так как содержимое `$CustomObject` является объектом, содержащим свойство с именем **Name**.

В этом примере я создаю другой пользовательский объект, используя другое имя свойства, например **Service**.

```powershell
$CustomObject = [pscustomobject]@{
  Service = 'w32time'
}
```

При попытке передать `$CustomObject` в `Stop-Service` создается ошибка, так как она не создает объект **ServiceController** или **String** и не содержит свойства с именем **Name**.

```powershell
$CustomObject | Stop-Service
```

```Output
Stop-Service : Cannot find any service with service name '@{Service=w32time}'.
At line:1 char:17
+ $CustomObject | Stop-Service
+
    + CategoryInfo          : ObjectNotFound: (@{Service=w32time}:String) [Stop-Service]
   , ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.S
   topServiceCommand
```

Если выходные данные одной команды не выводятся с входными параметрами конвейера для другой команды, `Select-Object` можно использовать для переименования свойства таким образом, чтобы свойства были заданы правильно.

```powershell
$CustomObject |
  Select-Object -Property @{name='Name';expression={$_.Service}} |
    Stop-Service
```

В этом примере `Select-Object` использовался для переименования свойства **Service** в свойство с именем **Name**.

Синтаксис этого примера может сначала показаться немного сложным. Единственное, что я понял: вы никогда не узнаете о синтаксисе, копируя и вставляя код. Потратьте время и несколько раз подряд введите код вручную. Потом это станет для вас привычным действием. Наличие нескольких мониторов — большое преимущество, так как вы можете отобразить пример кода на одном экране и вводить его на другом.

Иногда вам придется использовать параметр, который не принимает входные данные конвейера. В следующем примере показано использование выходных данных одной команды в качестве входных данных для другой. Сначала сохраните отображаемое имя для нескольких служб Windows в текстовый файл.

```powershell
'Background Intelligent Transfer Service', 'Windows Time' |
Out-File -FilePath $env:TEMP\services.txt
```

Вы можете выполнить команду, которая предоставляет необходимые выходные данные в круглых скобках в качестве значения параметра команды, требующей входные данные.

```powershell
Stop-Service -DisplayName (Get-Content -Path $env:TEMP\services.txt)
```

Это напоминает порядок операций в алгебре для тех, кто помнит, как это выглядит. Команда в круглых скобках всегда выполняется до внешней части команды.

## <a name="powershellget"></a>PowerShellGet

PowerShellGet — это модуль PowerShell, который содержит команды для обнаружения, установки, публикации и обновления модулей PowerShell (и других артефактов) в репозиторий NuGet или из него. PowerShellGet поставляется с PowerShell версии 5.0 и выше. Он доступен в виде отдельного скачиваемого файла для PowerShell версии 3.0 и более поздних версий.

Корпорация Майкрософт размещает в Интернете репозиторий NuGet, который называется [Коллекция PowerShell][]. Хотя этот репозиторий размещается Майкрософт, большинство модулей, которые в нем содержатся, пишутся не корпорацией. Любой код, полученный из коллекции PowerShell, необходимо тщательно проверить в изолированной тестовой среде, прежде чем считать его подходящим для использования в рабочей среде.

Многим компаниям понадобится разместить собственный внутренний репозиторий NuGet, где они могут публиковать только внутренние модули, а также модули, загруженные ими из других источников, после того как они проверят, что эти модули не являются вредоносными.

Используйте командлет `Find-Module`, входящий в состав модуля PowerShellGet, чтобы найти модуль в коллекции PowerShell, который я написал, с именем MrToolkit.

```powershell
Find-Module -Name MrToolkit
```

```Output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with
NuGet-based repositories. The NuGet provider must be available in 'C:\Program
Files\PackageManagement\ProviderAssemblies' or
'C:\Users\MrAdmin\AppData\Local\PackageManagement\ProviderAssemblies'. You can also
install the NuGet provider by running 'Install-PackageProvider -Name NuGet
-MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the
NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1        MrToolkit                           PSGallery            Misc PowerShell Tools
```

При первом использовании одной из команд из модуля PowerShellGet вам будет предложено установить поставщик NuGet.

Чтобы установить модуль MrToolkit, передайте предыдущую команду в `Install-Module`.

```powershell
Find-Module -Name MrToolkit | Install-Module
```

```Output
Untrusted repository
You are installing the modules from an untrusted repository. If you trust this
repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet.
Are you sure you want to install the modules from
'https://www.powershellgallery.com/api/v2/'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): y
```

Так как коллекция PowerShell является недоверенным репозиторием, она предложит вам подтвердить установку модуля.

## <a name="finding-pipeline-input-the-easy-way"></a>Простой способ поиска входных данных конвейера

Модуль MrToolkit содержит функцию с именем `Get-MrPipelineInput`. С помощью этого командлета можно легко определить, какие параметры команды принимают входные данные конвейера, какой тип объекта они принимают, принимают ли они входные данные конвейера **по значению** или **по имени свойства**.

```powershell
Get-MrPipelineInput -Name Stop-Service
```

```Output
ParameterName ParameterType                             ValueFromPipeline ValueFromPipelineByPropertyName
------------- -------------                             ----------------- ---------------
InputObject   System.ServiceProcess.ServiceController[]              True           False
Name          System.String[]                                        True            True
```

Как видите, одни и те же данные, которые мы раньше определяли путем фильтрации справки, можно легко определять с помощью этой функции.

## <a name="summary"></a>Сводка

В этой главе вы узнали об однострочных элементах кода PowerShell. Вы узнали, что количество физических строк, на которых приводится команда, не связано с однострочным элементом кода PowerShell. Кроме того, вы получили представление о фильтрации по левому краю, конвейере и модуле PowerShellGet.

## <a name="review"></a>Просмотр

1. Что такое однострочный элемент кода PowerShell?
1. В каких нескольких символах допускаются естественные разрывы строк в PowerShell?
1. Зачем выполнять фильтрацию по левому краю?
1. С помощью каких двух способов команда PowerShell может принимать входные данные конвейера?
1. Почему не следует доверять командам, найденным в коллекции PowerShell?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [about_Pipelines][]
- [about_Command_Syntax][]
- [about_Parameters][]
- [PowerShellGet: ПРОСТОЙ, НО ВАЖНЫЙ способ обнаружения, установки и обновления модулей PowerShell][psget]

<!-- link references-->
[about_Pipelines]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[about_Parameters]: /powershell/module/microsoft.powershell.core/about/about_parameters
[psget]: https://mikefrobbins.com/2015/04/23/powershellget-the-big-easy-way-to-discover-install-and-update-powershell-modules/
[Коллекция PowerShell]: https://www.powershellgallery.com/

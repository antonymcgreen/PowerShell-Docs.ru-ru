---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Get теста Set
ms.openlocfilehash: e46710954679bf20f4536c6efbcbd4dafd9e629e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402576"
---
# <a name="get-test-set"></a><span data-ttu-id="912c4-103">Get теста Set</span><span class="sxs-lookup"><span data-stu-id="912c4-103">Get-Test-Set</span></span>

><span data-ttu-id="912c4-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="912c4-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

![Получение, тестирования и настройка](/media/get-test-set.png)

<span data-ttu-id="912c4-106">Desired State Configuration PowerShell построена **получить**, **теста**, и **задать** процесса.</span><span class="sxs-lookup"><span data-stu-id="912c4-106">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="912c4-107">DSC [ресурсы](resources.md) каждый содержит методы для выполнения каждой из этих операций.</span><span class="sxs-lookup"><span data-stu-id="912c4-107">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span> <span data-ttu-id="912c4-108">В [конфигурации](../configurations/configurations.md), определить блоки ресурсов для заполнения в ключах, которые становятся параметрами для ресурса **получить**, **теста**, и **задать** методы.</span><span class="sxs-lookup"><span data-stu-id="912c4-108">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="912c4-109">Далее представлен синтаксис для **службы** блоке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="912c4-109">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="912c4-110">**Службы** ресурсов настраивает службы Windows.</span><span class="sxs-lookup"><span data-stu-id="912c4-110">The **Service** resource configures Windows services.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="912c4-111">**Получить**, **теста**, и **задать** методы **службы** ресурс будет иметь параметр блоки, которые принимают эти значения.</span><span class="sxs-lookup"><span data-stu-id="912c4-111">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

```powershell
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [System.String]
        $Name,

        [System.String]
        [ValidateSet("Automatic", "Manual", "Disabled")]
        $StartupType,

        [System.String]
        [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
        $BuiltInAccount,

        [System.Management.Automation.PSCredential]
        [ValidateNotNull()]
        $Credential,

        [System.String]
        [ValidateSet("Running", "Stopped")]
        $State="Running",

        [System.String]
        [ValidateNotNullOrEmpty()]
        $DisplayName,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Description,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Path,

        [System.String[]]
        [ValidateNotNullOrEmpty()]
        $Dependencies,

        [System.String]
        [ValidateSet("Present", "Absent")]
        $Ensure="Present"
    )
```

> [!NOTE]
> <span data-ttu-id="912c4-112">Язык и метод, используемый для определения ресурса определяет как **получить**, **теста**, и **задать** методы будут определены.</span><span class="sxs-lookup"><span data-stu-id="912c4-112">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="912c4-113">Так как **службы** ресурсов имеет только один обязательный ключ (`Name`), **службы** блок ресурсов может быть сложнее, чем это:</span><span class="sxs-lookup"><span data-stu-id="912c4-113">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

<span data-ttu-id="912c4-114">При компиляции конфигурации выше, значения, указываемые для ключа хранятся в файле «.mof», который создается.</span><span class="sxs-lookup"><span data-stu-id="912c4-114">When you compile the Configuration above, the values you specify for a key are stored in the ".mof" file that is generated.</span></span> <span data-ttu-id="912c4-115">Дополнительные сведения см. в разделе [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="912c4-115">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

<span data-ttu-id="912c4-116">При применении [локального диспетчера конфигураций](../managing-nodes/metaConfig.md) будет считать значение «Spooler» из файла «.mof» и передать его в `-Name` параметр **получить**, **теста**, и **задать** методы для экземпляра «MyService» **службы** ресурсов.</span><span class="sxs-lookup"><span data-stu-id="912c4-116">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) will read the value "Spooler" from the ".mof" file, and pass it to the `-Name` parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="912c4-117">Get</span><span class="sxs-lookup"><span data-stu-id="912c4-117">Get</span></span>

<span data-ttu-id="912c4-118">**Получить** ресурса, получает состояние ресурса в конфигурации на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="912c4-118">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="912c4-119">Это состояние возвращается в виде [хэш-таблицу](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="912c4-119">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span> <span data-ttu-id="912c4-120">Ключи **hashtable** будет настраиваемые значения, то есть параметры, ресурс принимает.</span><span class="sxs-lookup"><span data-stu-id="912c4-120">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="912c4-121">**Получить** метод сопоставляется непосредственно с [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) командлета.</span><span class="sxs-lookup"><span data-stu-id="912c4-121">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="912c4-122">При вызове `Get-DSCConfiguration`, запуски LCM **получить** метод каждого ресурса в настоящее время применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="912c4-122">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="912c4-123">LCM использует значения ключей, сохраненной в файле «.mof» в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="912c4-123">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="912c4-124">Это пример выходных данных из **службы** ресурс, который настраивает службу «Spooler».</span><span class="sxs-lookup"><span data-stu-id="912c4-124">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won’t be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

<span data-ttu-id="912c4-125">Выходные данные показывают текущее значение свойства, можно настроить путем **службы** ресурсов.</span><span class="sxs-lookup"><span data-stu-id="912c4-125">The output shows the current value properties configurable by the **Service** resource.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a><span data-ttu-id="912c4-126">Тест</span><span class="sxs-lookup"><span data-stu-id="912c4-126">Test</span></span>

<span data-ttu-id="912c4-127">**Теста** ресурса определяет, является ли целевой узел в настоящее время соответствуют ресурса *требуемое состояние*.</span><span class="sxs-lookup"><span data-stu-id="912c4-127">The **Test** method of a resource determines if the target node is currently compliant with the resource's *desired state*.</span></span> <span data-ttu-id="912c4-128">**Теста** возвращает `$True` или `$False` только для того, чтобы указать, является ли узел совместимым.</span><span class="sxs-lookup"><span data-stu-id="912c4-128">The **Test** method returns `$True` or `$False` only to indicate whether the Node is compliant.</span></span>
<span data-ttu-id="912c4-129">При вызове [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), LCM вызывает **теста** метод каждого ресурса в настоящее время применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="912c4-129">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="912c4-130">LCM использует значения ключей, сохраненной в файле «.mof» в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="912c4-130">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="912c4-131">Если результат любого отдельного ресурса **теста** — `$False`, `Test-DSCConfiguration` возвращает `$False` , указывающее, что узел не является совместимым.</span><span class="sxs-lookup"><span data-stu-id="912c4-131">If the result of any individual resource's **Test** is `$False`, `Test-DSCConfiguration` returns `$False` indicating that the Node is not compliant.</span></span> <span data-ttu-id="912c4-132">Если все ресурсов **теста** методы возвращают `$True`, `Test-DSCConfiguration` возвращает `$True` для указания, что узел соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="912c4-132">If all resource's **Test** methods return `$True`, `Test-DSCConfiguration` returns `$True` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="912c4-133">Начиная с PowerShell 5.0 `-Detailed` был добавлен параметр.</span><span class="sxs-lookup"><span data-stu-id="912c4-133">Beginning in PowerShell 5.0, the `-Detailed` parameter was added.</span></span> <span data-ttu-id="912c4-134">Указание `-Detailed` вызывает `Test-DSCConfiguration` возвращает объект, содержащий коллекцию результатов для соответствующих и несоответствующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="912c4-134">Specifying `-Detailed` causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="912c4-135">Дополнительные сведения см. в разделе [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span><span class="sxs-lookup"><span data-stu-id="912c4-135">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="912c4-136">Установить</span><span class="sxs-lookup"><span data-stu-id="912c4-136">Set</span></span>

<span data-ttu-id="912c4-137">**Задать** ресурса предпринимает попытку принудительного узел, чтобы обеспечить соответствие с ресурса *требуемое состояние*.</span><span class="sxs-lookup"><span data-stu-id="912c4-137">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="912c4-138">**Задать** метод должен быть **идемпотентными**, означающее, что **задать** возможно многократное выполнение и всегда получать один и тот же результат без ошибок.</span><span class="sxs-lookup"><span data-stu-id="912c4-138">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span>  <span data-ttu-id="912c4-139">При запуске [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), циклы LCM через каждый ресурс в данный момент применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="912c4-139">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="912c4-140">LCM получает ключевые значения для текущего экземпляра ресурсов из файла «.mof» и использует их в качестве параметров для **теста** метод.</span><span class="sxs-lookup"><span data-stu-id="912c4-140">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="912c4-141">Если **теста** возвращает `$True`, узел является совместимым с текущего ресурса и **задать** метод пропускается.</span><span class="sxs-lookup"><span data-stu-id="912c4-141">If the **Test** method returns `$True`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="912c4-142">Если **теста** возвращает `$False`, узел является несоответствующим.</span><span class="sxs-lookup"><span data-stu-id="912c4-142">If the **Test** returns `$False`, the Node is non-compliant.</span></span>  <span data-ttu-id="912c4-143">LCM передает ресурса значения ключа экземпляра в качестве параметров ресурса **задать** метод, восстановление узла на соответствие.</span><span class="sxs-lookup"><span data-stu-id="912c4-143">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="912c4-144">Путем указания `-Verbose` и `-Wait` параметров, можно отслеживать ход выполнения `Start-DSCConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="912c4-144">By specifying the `-Verbose` and `-Wait` parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="912c4-145">В этом примере узел уже совместимых.</span><span class="sxs-lookup"><span data-stu-id="912c4-145">In this example, the Node is already compliant.</span></span> <span data-ttu-id="912c4-146">`Verbose` Выходных данных указывает, что **задать** метод был пропущен.</span><span class="sxs-lookup"><span data-stu-id="912c4-146">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a><span data-ttu-id="912c4-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="912c4-147">See also</span></span>

- <span data-ttu-id="912c4-148">[Обзор DSC службы автоматизации Azure](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview).</span><span class="sxs-lookup"><span data-stu-id="912c4-148">[Azure Automation DSC Overview](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)</span></span>
- [<span data-ttu-id="912c4-149">Настройка опрашивающего SMB-сервера</span><span class="sxs-lookup"><span data-stu-id="912c4-149">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="912c4-150">Настройка опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="912c4-150">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)

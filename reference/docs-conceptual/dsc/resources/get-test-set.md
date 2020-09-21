---
ms.date: 07/08/2020
keywords: dsc,powershell,конфигурация,установка
title: Методы Get, Test, Set
ms.openlocfilehash: f7b7e947a85832365a783e40c25a25bfaa9fff8d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771521"
---
# <a name="get-test-set"></a><span data-ttu-id="6f8bc-103">Методы Get, Test, Set</span><span class="sxs-lookup"><span data-stu-id="6f8bc-103">Get-Test-Set</span></span>

><span data-ttu-id="6f8bc-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6f8bc-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6f8bc-105">Настройка требуемого состояния (DSC) PowerShell основана на процессе **получения**, **тестирования** и **настройки**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-105">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="6f8bc-106">Во всех [ресурсах](resources.md) DSC содержатся методы выполнения каждой из этих операций.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-106">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span>
<span data-ttu-id="6f8bc-107">В [конфигурации](../configurations/configurations.md) необходимо определить блоки ресурсов, чтобы заполнить ключи, которые становятся параметрами для методов ресурса **Get**, **Test** и **Set**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-107">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="6f8bc-108">Далее представлен синтаксис для блока ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-108">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="6f8bc-109">Ресурс **Service** настраивает службы Windows.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-109">The **Service** resource configures Windows services.</span></span>

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

<span data-ttu-id="6f8bc-110">Методы **Get**, **Test** и **Set** ресурса **Service** будут содержать блоки параметров, которые принимают эти значения.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-110">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

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
> <span data-ttu-id="6f8bc-111">Язык и метод, используемые для определения ресурса, указывают, как методы **Get**, **Test** и **Set** будут заданы.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-111">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="6f8bc-112">Так как у ресурса **Service** есть только один обязательный ключ (`Name`), блок ресурса **Service** может содержать всего пару строк:</span><span class="sxs-lookup"><span data-stu-id="6f8bc-112">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

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

<span data-ttu-id="6f8bc-113">Если скомпилировать вышеуказанную конфигурацию, значения, указанные для ключа, сохранятся в сгенерированном файле `.mof`.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-113">When you compile the Configuration above, the values you specify for a key are stored in the `.mof` file that is generated.</span></span> <span data-ttu-id="6f8bc-114">Дополнительные сведения о [MOF-файле](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="6f8bc-114">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

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

<span data-ttu-id="6f8bc-115">При использовании этого кода [локальный диспетчер конфигураций](../managing-nodes/metaConfig.md) (LCM) считывает из файла `.mof` значение Spooler и передает его в параметр **Name** методов **Get**, **Test** и **Set** для экземпляра MyService ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-115">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the `.mof` file, and pass it to the **Name** parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="6f8bc-116">Получить</span><span class="sxs-lookup"><span data-stu-id="6f8bc-116">Get</span></span>

<span data-ttu-id="6f8bc-117">Метод ресурса **Get** извлекает состояние ресурса, настроенное на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-117">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="6f8bc-118">Это состояние возвращается в виде [хэш-таблицы](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="6f8bc-118">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>
<span data-ttu-id="6f8bc-119">Ключами **хэш-таблицы** будут настраиваемые значения или параметры, принимаемые ресурсом.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-119">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="6f8bc-120">Метод **Get** отображается непосредственно в командлете [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="6f8bc-120">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="6f8bc-121">При вызове командлета `Get-DSCConfiguration` LCM запускает метод **Get** для каждого ресурса в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-121">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="6f8bc-122">LCM использует значения ключей, хранящиеся в файле `.mof`, в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-122">The LCM uses the key values stored in the `.mof` file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="6f8bc-123">Ниже приведен пример выходных данных для ресурса **Service**, который настраивает службу Spooler.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-123">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

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
                       this service, you won't be able to print or see your printers.
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

<span data-ttu-id="6f8bc-124">В выходных данных содержатся текущие свойства значений, настраиваемые ресурсом **Service**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-124">The output shows the current value properties configurable by the **Service** resource.</span></span>

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

## <a name="test"></a><span data-ttu-id="6f8bc-125">Тест</span><span class="sxs-lookup"><span data-stu-id="6f8bc-125">Test</span></span>

<span data-ttu-id="6f8bc-126">Метод ресурса **Test** определяет, соответствует ли сейчас целевой узел _требуемому состоянию_ ресурса.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-126">The **Test** method of a resource determines if the target node is currently compliant with the resource's _desired state_.</span></span> <span data-ttu-id="6f8bc-127">Метод **Test** возвращает значение `$true` или `$false` только, чтобы указать, соответствует ли узел.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-127">The **Test** method returns `$true` or `$false` only to indicate whether the Node is compliant.</span></span> <span data-ttu-id="6f8bc-128">При вызове командлета [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) LCM вызывает метод **Test** для каждого ресурса в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-128">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="6f8bc-129">LCM использует значения ключей, хранящиеся в MOF-файле, в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-129">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="6f8bc-130">Если в результате применения какого-либо отдельного метода **Test** ресурса возвращается значение `$false`, командлет `Test-DSCConfiguration` возвращает значение `$false`, указывая, что узел не соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-130">If the result of any individual resource's **Test** is `$false`, `Test-DSCConfiguration` returns `$false` indicating that the Node is not compliant.</span></span> <span data-ttu-id="6f8bc-131">Если все методы **Test** ресурса возвращают значение `$true`, `Test-DSCConfiguration` возвращает значение `$true`, чтобы указать, что узел соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-131">If all resource's **Test** methods return `$true`, `Test-DSCConfiguration` returns `$true` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="6f8bc-132">Начиная с PowerShell 5.0, был добавлен параметр **Detailed**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-132">Beginning in PowerShell 5.0, the **Detailed** parameter was added.</span></span> <span data-ttu-id="6f8bc-133">Если указать параметр **Detailed**, это приведет к тому, что командлет `Test-DSCConfiguration` вернет объект, содержащий коллекции результатов для совместимых и несовместимых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-133">Specifying **Detailed** causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="6f8bc-134">Дополнительные сведения о [командлете Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="6f8bc-134">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="6f8bc-135">Присвойте параметру</span><span class="sxs-lookup"><span data-stu-id="6f8bc-135">Set</span></span>

<span data-ttu-id="6f8bc-136">Метод **Set** ресурса пытается сделать узел совместимым с *требуемым состоянием* ресурса.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-136">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="6f8bc-137">Метод **Set** должен быть **идемпотентным**. Это означает, что при любом запуске **Set** всегда будет получен один и тот же результат без ошибок.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-137">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span> <span data-ttu-id="6f8bc-138">При запуске командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) LCM циклически перебирает каждый ресурс в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-138">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="6f8bc-139">LCM извлекает значения ключей текущего экземпляра ресурса из MOF-файла и использует их как параметры метода **Test**.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-139">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="6f8bc-140">Если метод **Test** возвращает значение `$true`, узел соответствует текущему ресурсу, а метод **Set** не вызывается.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-140">If the **Test** method returns `$true`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="6f8bc-141">Если **Test** возвращает значение `$false`, значит, узел не соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-141">If the **Test** returns `$false`, the Node is non-compliant.</span></span> <span data-ttu-id="6f8bc-142">LCM передает значения ключей экземпляра ресурса в качестве параметров методу **Set** ресурса, восстанавливая соответствие узла.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-142">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="6f8bc-143">Указав параметры **Verbose** и **Wait**, можно наблюдать за ходом выполнения командлета `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-143">By specifying the **Verbose** and **Wait** parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="6f8bc-144">В этом примере узел уже соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-144">In this example, the Node is already compliant.</span></span> <span data-ttu-id="6f8bc-145">Параметр `Verbose` в выходных данных указывает, что метод **Set** не вызывался.</span><span class="sxs-lookup"><span data-stu-id="6f8bc-145">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6f8bc-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6f8bc-146">See also</span></span>

- <span data-ttu-id="6f8bc-147">[Обзор DSC службы автоматизации Azure](/azure/automation/automation-dsc-overview).</span><span class="sxs-lookup"><span data-stu-id="6f8bc-147">[Azure Automation DSC Overview](/azure/automation/automation-dsc-overview)</span></span>
- [<span data-ttu-id="6f8bc-148">Настройка опрашивающего SMB-сервера</span><span class="sxs-lookup"><span data-stu-id="6f8bc-148">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="6f8bc-149">Настройка опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="6f8bc-149">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)

---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Методы Get, Test, Set
ms.openlocfilehash: bf409f71c07c434fbc7389789e16575868d21b42
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278429"
---
# <a name="get-test-set"></a><span data-ttu-id="b4180-103">Методы Get, Test, Set</span><span class="sxs-lookup"><span data-stu-id="b4180-103">Get-Test-Set</span></span>

><span data-ttu-id="b4180-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b4180-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

![Получение, тестирования и настройка](media/get-test-set/get-test-set.png)

<span data-ttu-id="b4180-106">Настройка требуемого состояния (DSC) PowerShell основана на процессе **получения**, **тестирования** и **настройки**.</span><span class="sxs-lookup"><span data-stu-id="b4180-106">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="b4180-107">Во всех [ресурсах](resources.md) DSC содержатся методы выполнения каждой из этих операций.</span><span class="sxs-lookup"><span data-stu-id="b4180-107">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span> <span data-ttu-id="b4180-108">В [конфигурации](../configurations/configurations.md) необходимо определить блоки ресурсов, чтобы заполнить ключи, которые становятся параметрами для методов ресурса **Get**, **Test** и **Set**.</span><span class="sxs-lookup"><span data-stu-id="b4180-108">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="b4180-109">Далее представлен синтаксис для блока ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="b4180-109">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="b4180-110">Ресурс **Service** настраивает службы Windows.</span><span class="sxs-lookup"><span data-stu-id="b4180-110">The **Service** resource configures Windows services.</span></span>

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

<span data-ttu-id="b4180-111">Методы **Get**, **Test** и **Set** ресурса **Service** будут содержать блоки параметров, которые принимают эти значения.</span><span class="sxs-lookup"><span data-stu-id="b4180-111">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

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
> <span data-ttu-id="b4180-112">Язык и метод, используемые для определения ресурса, указывают, как методы **Get**, **Test** и **Set** будут заданы.</span><span class="sxs-lookup"><span data-stu-id="b4180-112">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="b4180-113">Так как у ресурса **Service** есть только один обязательный ключ (`Name`), блок ресурса **Service** может содержать всего пару строк:</span><span class="sxs-lookup"><span data-stu-id="b4180-113">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

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

<span data-ttu-id="b4180-114">Если скомпилировать вышеуказанную конфигурацию, значения, указанные для ключа, сохранятся в сгенерированном MOF-файле.</span><span class="sxs-lookup"><span data-stu-id="b4180-114">When you compile the Configuration above, the values you specify for a key are stored in the ".mof" file that is generated.</span></span> <span data-ttu-id="b4180-115">Дополнительные сведения о [MOF-файле](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="b4180-115">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

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

<span data-ttu-id="b4180-116">При использовании этого кода [локальный диспетчер конфигураций](../managing-nodes/metaConfig.md) (LCM) считывает из MOF-файла значение "Spooler" и передает его в параметр `-Name` методов **Get**, **Test** и **Set** для экземпляра "MyService" ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="b4180-116">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the ".mof" file, and pass it to the `-Name` parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="b4180-117">Получить</span><span class="sxs-lookup"><span data-stu-id="b4180-117">Get</span></span>

<span data-ttu-id="b4180-118">Метод ресурса **Get** извлекает состояние ресурса, настроенное на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="b4180-118">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="b4180-119">Это состояние возвращается в виде [хэш-таблицы](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="b4180-119">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span> <span data-ttu-id="b4180-120">Ключами **хэш-таблицы** будут настраиваемые значения или параметры, принимаемые ресурсом.</span><span class="sxs-lookup"><span data-stu-id="b4180-120">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="b4180-121">Метод **Get** отображается непосредственно в командлете [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="b4180-121">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="b4180-122">При вызове командлета `Get-DSCConfiguration` LCM запускает метод **Get** для каждого ресурса в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4180-122">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="b4180-123">LCM использует значения ключей, хранящиеся в MOF-файле, в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="b4180-123">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="b4180-124">Ниже приведен пример выходных данных для ресурса **Service**, который настраивает службу Spooler.</span><span class="sxs-lookup"><span data-stu-id="b4180-124">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

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

<span data-ttu-id="b4180-125">В выходных данных содержатся текущие свойства значений, настраиваемые ресурсом **Service**.</span><span class="sxs-lookup"><span data-stu-id="b4180-125">The output shows the current value properties configurable by the **Service** resource.</span></span>

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

## <a name="test"></a><span data-ttu-id="b4180-126">Тест</span><span class="sxs-lookup"><span data-stu-id="b4180-126">Test</span></span>

<span data-ttu-id="b4180-127">Метод ресурса **Test** определяет, соответствует ли сейчас целевой узел *требуемому состоянию* ресурса.</span><span class="sxs-lookup"><span data-stu-id="b4180-127">The **Test** method of a resource determines if the target node is currently compliant with the resource's *desired state*.</span></span> <span data-ttu-id="b4180-128">Метод **Test** возвращает значение `$True` или `$False` только, чтобы указать, соответствует ли узел.</span><span class="sxs-lookup"><span data-stu-id="b4180-128">The **Test** method returns `$True` or `$False` only to indicate whether the Node is compliant.</span></span>
<span data-ttu-id="b4180-129">При вызове командлета [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) LCM вызывает метод **Test** для каждого ресурса в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4180-129">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="b4180-130">LCM использует значения ключей, хранящиеся в MOF-файле, в качестве параметров для каждого соответствующего экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="b4180-130">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="b4180-131">Если в результате применения какого-либо отдельного метода **Test** ресурса возвращается значение `$False`, командлет `Test-DSCConfiguration` возвращает значение `$False`, указывая, что узел не соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b4180-131">If the result of any individual resource's **Test** is `$False`, `Test-DSCConfiguration` returns `$False` indicating that the Node is not compliant.</span></span> <span data-ttu-id="b4180-132">Если все методы **Test** ресурса возвращают значение `$True`, `Test-DSCConfiguration` возвращает значение `$True`, чтобы указать, что узел соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b4180-132">If all resource's **Test** methods return `$True`, `Test-DSCConfiguration` returns `$True` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="b4180-133">Начиная с PowerShell 5.0 добавлен параметр `-Detailed`.</span><span class="sxs-lookup"><span data-stu-id="b4180-133">Beginning in PowerShell 5.0, the `-Detailed` parameter was added.</span></span> <span data-ttu-id="b4180-134">Если указать параметр `-Detailed`, это приведет к тому, что командлет `Test-DSCConfiguration` вернет объект, содержащий коллекции результатов для совместимых и несовместимых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4180-134">Specifying `-Detailed` causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="b4180-135">Дополнительные сведения о [командлете Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b4180-135">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="b4180-136">Присвойте параметру</span><span class="sxs-lookup"><span data-stu-id="b4180-136">Set</span></span>

<span data-ttu-id="b4180-137">Метод **Set** ресурса пытается сделать узел совместимым с *требуемым состоянием* ресурса.</span><span class="sxs-lookup"><span data-stu-id="b4180-137">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="b4180-138">Метод **Set** должен быть **идемпотентным**. Это означает, что при любом запуске **Set** всегда будет получен один и тот же результат без ошибок.</span><span class="sxs-lookup"><span data-stu-id="b4180-138">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span>  <span data-ttu-id="b4180-139">При запуске командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) LCM циклически перебирает каждый ресурс в текущей применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4180-139">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="b4180-140">LCM извлекает значения ключей текущего экземпляра ресурса из MOF-файла и использует их как параметры метода **Test**.</span><span class="sxs-lookup"><span data-stu-id="b4180-140">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="b4180-141">Если метод **Test** возвращает значение `$True`, узел соответствует текущему ресурсу, а метод **Set** не вызывается.</span><span class="sxs-lookup"><span data-stu-id="b4180-141">If the **Test** method returns `$True`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="b4180-142">Если **Test** возвращает значение `$False`, значит, узел не соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b4180-142">If the **Test** returns `$False`, the Node is non-compliant.</span></span>  <span data-ttu-id="b4180-143">LCM передает значения ключей экземпляра ресурса в качестве параметров методу **Set** ресурса, восстанавливая соответствие узла.</span><span class="sxs-lookup"><span data-stu-id="b4180-143">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="b4180-144">Указав параметры `-Verbose` и `-Wait`, можно наблюдать за ходом выполнения командлета `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="b4180-144">By specifying the `-Verbose` and `-Wait` parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="b4180-145">В этом примере узел уже соответствует текущему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b4180-145">In this example, the Node is already compliant.</span></span> <span data-ttu-id="b4180-146">Параметр `Verbose` в выходных данных указывает, что метод **Set** не вызывался.</span><span class="sxs-lookup"><span data-stu-id="b4180-146">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b4180-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4180-147">See also</span></span>

- <span data-ttu-id="b4180-148">[Обзор DSC службы автоматизации Azure](https://docs.microsoft.com/azure/automation/automation-dsc-overview).</span><span class="sxs-lookup"><span data-stu-id="b4180-148">[Azure Automation DSC Overview](https://docs.microsoft.com/azure/automation/automation-dsc-overview)</span></span>
- [<span data-ttu-id="b4180-149">Настройка опрашивающего SMB-сервера</span><span class="sxs-lookup"><span data-stu-id="b4180-149">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="b4180-150">Настройка опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="b4180-150">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)

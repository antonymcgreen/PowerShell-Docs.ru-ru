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
# <a name="get-test-set"></a>Get теста Set

>Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

![Получение, тестирования и настройка](/media/get-test-set.png)

Desired State Configuration PowerShell построена **получить**, **теста**, и **задать** процесса. DSC [ресурсы](resources.md) каждый содержит методы для выполнения каждой из этих операций. В [конфигурации](../configurations/configurations.md), определить блоки ресурсов для заполнения в ключах, которые становятся параметрами для ресурса **получить**, **теста**, и **задать** методы.

Далее представлен синтаксис для **службы** блоке ресурсов. **Службы** ресурсов настраивает службы Windows.

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

**Получить**, **теста**, и **задать** методы **службы** ресурс будет иметь параметр блоки, которые принимают эти значения.

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
> Язык и метод, используемый для определения ресурса определяет как **получить**, **теста**, и **задать** методы будут определены.

Так как **службы** ресурсов имеет только один обязательный ключ (`Name`), **службы** блок ресурсов может быть сложнее, чем это:

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

При компиляции конфигурации выше, значения, указываемые для ключа хранятся в файле «.mof», который создается. Дополнительные сведения см. в разделе [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).

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

При применении [локального диспетчера конфигураций](../managing-nodes/metaConfig.md) будет считать значение «Spooler» из файла «.mof» и передать его в `-Name` параметр **получить**, **теста**, и **задать** методы для экземпляра «MyService» **службы** ресурсов.

## <a name="get"></a>Get

**Получить** ресурса, получает состояние ресурса в конфигурации на целевом узле. Это состояние возвращается в виде [хэш-таблицу](/powershell/module/microsoft.powershell.core/about/about_hash_tables). Ключи **hashtable** будет настраиваемые значения, то есть параметры, ресурс принимает.

**Получить** метод сопоставляется непосредственно с [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) командлета. При вызове `Get-DSCConfiguration`, запуски LCM **получить** метод каждого ресурса в настоящее время применяемой конфигурации. LCM использует значения ключей, сохраненной в файле «.mof» в качестве параметров для каждого соответствующего экземпляра ресурса.

Это пример выходных данных из **службы** ресурс, который настраивает службу «Spooler».

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

Выходные данные показывают текущее значение свойства, можно настроить путем **службы** ресурсов.

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

## <a name="test"></a>Тест

**Теста** ресурса определяет, является ли целевой узел в настоящее время соответствуют ресурса *требуемое состояние*. **Теста** возвращает `$True` или `$False` только для того, чтобы указать, является ли узел совместимым.
При вызове [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), LCM вызывает **теста** метод каждого ресурса в настоящее время применяемой конфигурации. LCM использует значения ключей, сохраненной в файле «.mof» в качестве параметров для каждого соответствующего экземпляра ресурса.

Если результат любого отдельного ресурса **теста** — `$False`, `Test-DSCConfiguration` возвращает `$False` , указывающее, что узел не является совместимым. Если все ресурсов **теста** методы возвращают `$True`, `Test-DSCConfiguration` возвращает `$True` для указания, что узел соответствует требованиям.

```powershell
Test-DSCConfiguration
```

```output
True
```

Начиная с PowerShell 5.0 `-Detailed` был добавлен параметр. Указание `-Detailed` вызывает `Test-DSCConfiguration` возвращает объект, содержащий коллекцию результатов для соответствующих и несоответствующих ресурсов.

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

Дополнительные сведения см. в разделе [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)

## <a name="set"></a>Установить

**Задать** ресурса предпринимает попытку принудительного узел, чтобы обеспечить соответствие с ресурса *требуемое состояние*. **Задать** метод должен быть **идемпотентными**, означающее, что **задать** возможно многократное выполнение и всегда получать один и тот же результат без ошибок.  При запуске [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), циклы LCM через каждый ресурс в данный момент применяемой конфигурации. LCM получает ключевые значения для текущего экземпляра ресурсов из файла «.mof» и использует их в качестве параметров для **теста** метод. Если **теста** возвращает `$True`, узел является совместимым с текущего ресурса и **задать** метод пропускается. Если **теста** возвращает `$False`, узел является несоответствующим.  LCM передает ресурса значения ключа экземпляра в качестве параметров ресурса **задать** метод, восстановление узла на соответствие.

Путем указания `-Verbose` и `-Wait` параметров, можно отслеживать ход выполнения `Start-DSCConfiguration` командлета. В этом примере узел уже совместимых. `Verbose` Выходных данных указывает, что **задать** метод был пропущен.

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

## <a name="see-also"></a>См. также:

- [Обзор DSC службы автоматизации Azure](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview).
- [Настройка опрашивающего SMB-сервера](../pull-server/pullServerSMB.md)
- [Настройка опрашивающего клиента](../pull-server/pullClientConfigID.md)

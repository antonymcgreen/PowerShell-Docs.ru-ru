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
# <a name="get-test-set"></a>Методы Get, Test, Set

>Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

![Получение, тестирования и настройка](media/get-test-set/get-test-set.png)

Настройка требуемого состояния (DSC) PowerShell основана на процессе **получения**, **тестирования** и **настройки**. Во всех [ресурсах](resources.md) DSC содержатся методы выполнения каждой из этих операций. В [конфигурации](../configurations/configurations.md) необходимо определить блоки ресурсов, чтобы заполнить ключи, которые становятся параметрами для методов ресурса **Get**, **Test** и **Set**.

Далее представлен синтаксис для блока ресурса **Service**. Ресурс **Service** настраивает службы Windows.

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

Методы **Get**, **Test** и **Set** ресурса **Service** будут содержать блоки параметров, которые принимают эти значения.

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
> Язык и метод, используемые для определения ресурса, указывают, как методы **Get**, **Test** и **Set** будут заданы.

Так как у ресурса **Service** есть только один обязательный ключ (`Name`), блок ресурса **Service** может содержать всего пару строк:

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

Если скомпилировать вышеуказанную конфигурацию, значения, указанные для ключа, сохранятся в сгенерированном MOF-файле. Дополнительные сведения о [MOF-файле](/windows/desktop/wmisdk/managed-object-format--mof-).

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

При использовании этого кода [локальный диспетчер конфигураций](../managing-nodes/metaConfig.md) (LCM) считывает из MOF-файла значение "Spooler" и передает его в параметр `-Name` методов **Get**, **Test** и **Set** для экземпляра "MyService" ресурса **Service**.

## <a name="get"></a>Получить

Метод ресурса **Get** извлекает состояние ресурса, настроенное на целевом узле. Это состояние возвращается в виде [хэш-таблицы](/powershell/module/microsoft.powershell.core/about/about_hash_tables). Ключами **хэш-таблицы** будут настраиваемые значения или параметры, принимаемые ресурсом.

Метод **Get** отображается непосредственно в командлете [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration). При вызове командлета `Get-DSCConfiguration` LCM запускает метод **Get** для каждого ресурса в текущей применяемой конфигурации. LCM использует значения ключей, хранящиеся в MOF-файле, в качестве параметров для каждого соответствующего экземпляра ресурса.

Ниже приведен пример выходных данных для ресурса **Service**, который настраивает службу Spooler.

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

В выходных данных содержатся текущие свойства значений, настраиваемые ресурсом **Service**.

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

Метод ресурса **Test** определяет, соответствует ли сейчас целевой узел *требуемому состоянию* ресурса. Метод **Test** возвращает значение `$True` или `$False` только, чтобы указать, соответствует ли узел.
При вызове командлета [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) LCM вызывает метод **Test** для каждого ресурса в текущей применяемой конфигурации. LCM использует значения ключей, хранящиеся в MOF-файле, в качестве параметров для каждого соответствующего экземпляра ресурса.

Если в результате применения какого-либо отдельного метода **Test** ресурса возвращается значение `$False`, командлет `Test-DSCConfiguration` возвращает значение `$False`, указывая, что узел не соответствует текущему ресурсу. Если все методы **Test** ресурса возвращают значение `$True`, `Test-DSCConfiguration` возвращает значение `$True`, чтобы указать, что узел соответствует текущему ресурсу.

```powershell
Test-DSCConfiguration
```

```output
True
```

Начиная с PowerShell 5.0 добавлен параметр `-Detailed`. Если указать параметр `-Detailed`, это приведет к тому, что командлет `Test-DSCConfiguration` вернет объект, содержащий коллекции результатов для совместимых и несовместимых ресурсов.

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

Дополнительные сведения о [командлете Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).

## <a name="set"></a>Присвойте параметру

Метод **Set** ресурса пытается сделать узел совместимым с *требуемым состоянием* ресурса. Метод **Set** должен быть **идемпотентным**. Это означает, что при любом запуске **Set** всегда будет получен один и тот же результат без ошибок.  При запуске командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) LCM циклически перебирает каждый ресурс в текущей применяемой конфигурации. LCM извлекает значения ключей текущего экземпляра ресурса из MOF-файла и использует их как параметры метода **Test**. Если метод **Test** возвращает значение `$True`, узел соответствует текущему ресурсу, а метод **Set** не вызывается. Если **Test** возвращает значение `$False`, значит, узел не соответствует текущему ресурсу.  LCM передает значения ключей экземпляра ресурса в качестве параметров методу **Set** ресурса, восстанавливая соответствие узла.

Указав параметры `-Verbose` и `-Wait`, можно наблюдать за ходом выполнения командлета `Start-DSCConfiguration`. В этом примере узел уже соответствует текущему ресурсу. Параметр `Verbose` в выходных данных указывает, что метод **Set** не вызывался.

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

## <a name="see-also"></a>См. также раздел

- [Обзор DSC службы автоматизации Azure](https://docs.microsoft.com/azure/automation/automation-dsc-overview).
- [Настройка опрашивающего SMB-сервера](../pull-server/pullServerSMB.md)
- [Настройка опрашивающего клиента](../pull-server/pullClientConfigID.md)

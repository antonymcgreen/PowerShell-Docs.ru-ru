---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Применение, получение и тестирование конфигураций на узле
ms.openlocfilehash: 41f8d2d75d3dd9621de615e7999c2690cb8ce44a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402947"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a>Применение, получение и тестирование конфигураций на узле

В этом руководстве будет показано, как работать с конфигурациями на конечный узел. В этом руководстве разбивается на следующие действия:

## <a name="apply-a-configuration"></a>Применение конфигурации

Чтобы применить конфигурацию и управлять ею, нам нужно создать файл «.mof». Следующий код будет представлять простую конфигурацию, которая будет использоваться в этом руководстве.

```powershell
Configuration Sample
{
    # This will generate two .mof files, a localhost.mof, and a server02.mof
    Node localhost, server02
    {
        File SampleFile
        {
            DestinationPath = 'C:\Temp\temp.txt'
            Contents = 'This is a simple resource to show Configuration functionality on a Node.'
        }
    }
}

# The -OutputPath parameter is built into every Configuration automatically.
# The value of -OutputPath determines where the .mof file should be stored, once compiled.
Sample -OutputPath "C:\Temp\"
```

Компиляция эта конфигурация обеспечит два MOF-файлы.

```output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

Чтобы применить конфигурацию, используйте [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) командлета. `-Path` Параметр задает каталог, где находятся MOF-файлы. Если не `-Computername` указано, `Start-DSCConfiguration` попытается применяют их к имени компьютера, указанного по имени файла «.mof» (\<computername\>.mof). Укажите `-Verbose` для `Start-DSCConfiguration` Чтобы просмотреть более подробные выходные данные.

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

Если `-Wait` не указан, вы увидите одно задание создано. Создано задание будет содержать одну **ChildJob** для каждого файла «.mof» обрабатываемых `Start-DSCConfiguration`.

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

Если конфигурация занимает много времени и вы хотите остановить его, можно использовать [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) завершить приложения на локальном узле.

```powershell
Stop-DSCConfiguration -Force
```

После завершения процесса можно просмотреть состояние заданий через объект задания, возвращаемый [Get-Job](/powershell/module/microsoft.powershell.core/get-job).

```powershell
$job = Get-Job
$job.ChildJobs
```

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

Чтобы увидеть **Verbose** выходных данных, используйте следующие команды для просмотра **Verbose** поток для каждого **ChildJob**. Для получения дополнительных сведений о заданиях PowerShell см. в разделе [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-124525095-708259637-1543119021-1282804.
[SERVER01]: LCM:  [ Start  Set      ]
[SERVER01]: LCM:  [ Start  Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ Start  Test     ]  [[File]SampleFile]
[SERVER01]:                            [[File]SampleFile] The destination object was found and no action is required.
[SERVER01]: LCM:  [ End    Test     ]  [[File]SampleFile]  in 0.0370 seconds.
[SERVER01]: LCM:  [ Skip   Set      ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Set      ]
[SERVER01]: LCM:  [ End    Set      ]    in  0.2400 seconds.
Operation 'Invoke CimMethod' complete.
```

Начиная с PowerShell 5.0 `-UseExisting` был добавлен в `Start-DSCConfiguration`. Путем указания `-UseExisting`, в командлете использовать существующие применяемой конфигурации вместо указанной `-Path` параметра.

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a>Проверка конфигурации

Можно проверить в настоящее время применяются конфигурации с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration). `Test-DSCConfiguration` Возвращает `True` , является ли узел соответствует требованиям, и `False` Если это не так.

```powershell
Test-DSCConfiguration
```

Начиная с PowerShell 5.0 `-Detailed` был добавлен параметр, который возвращает объект с коллекциями для **ResourcesInDesiredState** и **ResourcesNotInDesiredState**

```powershell
Test-DSCConfiguration -Detailed
```

Начиная с PowerShell 5.0 можно проверить конфигурацию без его применения. `-ReferenceConfiguration` Параметр принимает путь к файлу «.mof» для проверки узла на соответствие. Не **задать** действий под узел. В PowerShell 4.0 существуют обходные пути, чтобы проверить конфигурацию без его применения, но они не рассматриваются здесь.

## <a name="get-configuration-values"></a>Получить значения конфигурации

[Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) командлет возвращает текущие значения для любых ресурсов, настроенных в настоящее время применяемой конфигурации.

```powershell
Get-DSCConfiguration
```

Выходные данные в нашем примере конфигурации будет выглядеть следующим образом, если успешно применены.

```output
ConfigurationName    : Sample
DependsOn            :
ModuleName           : PSDesiredStateConfiguration
ModuleVersion        :
PsDscRunAsCredential :
ResourceId           : [File]SampleFile
SourceInfo           :
Attributes           : {archive}
Checksum             :
Contents             :
CreatedDate          : 11/27/2018 7:16:06 AM
Credential           :
DestinationPath      : C:\Temp\temp.txt
Ensure               : present
Force                :
MatchSource          :
ModifiedDate         : 11/27/2018 7:16:06 AM
Recurse              :
Size                 : 75
SourcePath           :
SubItems             :
Type                 : file
PSComputerName       :
CimClassName         : MSFT_FileDirectoryConfiguration
```

## <a name="get-configuration-status"></a>Получение сведений о состоянии конфигурации

Начиная с PowerShell 5.0 [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) командлет позволяет просмотреть историю примененных конфигураций для узла. PowerShell DSC следит за последней конфигурации {{N}}, применяемые в **Push** или **на включение внесенных изменений** режим. Это включает какой-либо *согласованности* проверок, lcm ее выполняет. По умолчанию `Get-DSCConfigurationStatus` показано только последней записи журнала.

```powershell
Get-DSCConfigurationStatus
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

Используйте `-All` параметр, чтобы просмотреть весь журнал состояния конфигурации.

> [!NOTE]
> Для краткости производится усечение выходных данных.

```powershell
Get-DSCConfigurationStatus -All
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
Success    11/27/2018 7:16:06 AM     Initial         PUSH  False                1
Success    11/27/2018 7:04:53 AM     Initial         PUSH  False                1
Success    11/27/2018 7:03:45 AM     Consistency     PUSH  False                2
Success    11/27/2018 7:03:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:48:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:44 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:18:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:03:44 AM     Consistency     PUSH  False                2
```

## <a name="manage-configuration-documents"></a>Управление документами конфигурации

LCM управляет конфигурацией узла, работая с **документы конфигурации**. Эти MOF-файлы находятся в каталоге «C:\Windows\System32\Configuration».

Начиная с PowerShell 5.0 [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) позволяет удалить MOF-файлы для остановки проверки согласованности в будущем или удалить конфигурации, которая имеет ошибки при их применении. `-Stage` Параметр позволяет указать файл «.mof», который требуется удалить.

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> В PowerShell 4.0, по-прежнему можно удалить эти MOF-файлы непосредственно с помощью [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).

## <a name="publish-configurations"></a>Публикация конфигураций

Начиная с PowerShell 5.0 [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) был добавлен командлет. Этот командлет позволяет опубликовать файл «.mof» к удаленным компьютерам без его применения.

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a>См. также:

- [Получение, тестирование и настройка](../resources/get-test-set.md)

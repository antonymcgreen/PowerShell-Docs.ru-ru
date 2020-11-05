---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Применение, получение и тестирование конфигураций на узле
description: В этом руководстве будет показано, как работать с конфигурациями на целевом узле.
ms.openlocfilehash: 6bc9262bc0e2ce8eea7b85bd46ecc0c0a691276d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651023"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a>Применение, получение и тестирование конфигураций на узле

В этом руководстве будет показано, как работать с конфигурациями на целевом узле. Руководство разбито на описанные ниже этапы.

## <a name="apply-a-configuration"></a>Применение конфигурации

Чтобы применить конфигурацию и управлять ей, нам нужно сгенерировать MOF-файл. Следующий код представляет собой простую конфигурацию, которая будет использоваться в этом руководстве.

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

Компиляция этой конфигурации даст два MOF-файла.

```Output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

Чтобы применить конфигурацию, используйте командлет [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration). Параметр `-Path` указывает каталог, в котором находятся MOF-файлы. Если не указано `-Computername`, `Start-DSCConfiguration` попытается применить каждую конфигурацию к имени компьютера, указанному в имени MOF-файла (`<computername>.mof`). Укажите `-Verbose` для `Start-DSCConfiguration`, чтобы увидеть более подробные выходные данные.

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

Если `-Wait` не указано, вы увидите одно созданное задание. Созданное задание будет иметь по одному **ChildJob** для каждого MOF-файла, обработанного `Start-DSCConfiguration`.

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

Если конфигурация занимает много времени и вы хотите остановить ее, вы можете использовать [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration), чтобы остановить приложение на локальном узле.

```powershell
Stop-DSCConfiguration -Force
```

После завершения вы можете просматривать состояние заданий через объект задания, возвращаемый [Get-Job](/powershell/module/microsoft.powershell.core/get-job).

```powershell
$job = Get-Job
$job.ChildJobs
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

Чтобы просмотреть выходные данные **Подробных сведений** , используйте следующие команды для просмотра потока **Подробных сведений** для каждого **ChildJob**. Дополнительные сведения о заданиях PowerShell см. в разделе [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```Output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,
'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
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

Начиная с PowerShell 5.0, параметр `-UseExisting` был добавлен в `Start-DSCConfiguration`. Указывая `-UseExisting`, вы даете командлету указание использовать существующую примененную конфигурацию вместо конфигурации, указанной параметром `-Path`.

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a>Проверка конфигурации

Текущую конфигурацию можно проверить, используя [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).
`Test-DSCConfiguration` возвращает `True`, если узел соответствует, и `False`, если это не так.

```powershell
Test-DSCConfiguration
```

Начиная с PowerShell 5.0, был добавлен параметр `-Detailed`, который возвращает объект с коллекциями для **ResourcesInDesiredState** и **ResourcesNotInDesiredState**.

```powershell
Test-DSCConfiguration -Detailed
```

Начиная с PowerShell 5.0 конфигурацию можно проверить, не применяя эту команду. Параметр `-ReferenceConfiguration` принимает путь к MOF-файлу для проверки узла на соответствие. К узлу не применяется никакой **набор** действий. В PowerShell 4.0 есть обходные пути для проверки конфигурации без применения этой команды, но они здесь не рассматриваются.

## <a name="get-configuration-values"></a>Получение значений конфигурации

Командлет [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) возвращает текущие значения для всех настроенных ресурсов в текущей примененной конфигурации.

```powershell
Get-DSCConfiguration
```

В случае успешного применения выходные данные нашего примера конфигурации будут выглядеть таким образом.

```Output
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

## <a name="get-configuration-status"></a>Получение статуса конфигурации

Начиная с PowerShell 5.0, командлет [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) позволяет просматривать историю примененных к узлу конфигураций. PowerShell DSC отслеживает последние конфигурации (в количестве {{N}}), примененные в режиме **Push** или **Pull**. Это включает в себя любые проверки *согласованности* , выполненные LCM. По умолчанию `Get-DSCConfigurationStatus` показывает только последнюю запись истории.

```powershell
Get-DSCConfigurationStatus
```

```Output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

Используйте параметр `-All`, чтобы просмотреть всю историю состояния конфигурации.

> [!NOTE]
> Для краткости производится сокращение выходных данных.

```powershell
Get-DSCConfigurationStatus -All
```

```Output
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

LCM управляет конфигурацией узла, работая с **документами конфигурации**. Такие файлы ".mof" хранятся в каталоге `C:\Windows\System32\Configuration`.

Начиная с PowerShell 5.0, [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) позволяет вам удалять MOF-файлы, чтобы остановить будущие проверки согласованности или удалить конфигурацию, в которой возникают ошибки при применении. Параметр `-Stage` позволяет указать, какой MOF-файл вы хотите удалить.

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> В PowerShell 4.0 вы по-прежнему можете удалять эти MOF-файлы непосредственно, используя [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).

## <a name="publish-configurations"></a>Публикация конфигураций

Начиная с PowerShell 5.0, был добавлен командлет [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration). Этот командлет позволяет публиковать MOF-файлы на удаленных компьютерах без применения.

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a>См. также раздел

- [Получение, тестирования и настройка](../resources/get-test-set.md)

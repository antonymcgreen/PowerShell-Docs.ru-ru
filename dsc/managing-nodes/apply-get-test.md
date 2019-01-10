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
# <a name="apply-get-and-test-configurations-on-a-node"></a><span data-ttu-id="25842-103">Применение, получение и тестирование конфигураций на узле</span><span class="sxs-lookup"><span data-stu-id="25842-103">Apply, Get, and Test Configurations on a Node</span></span>

<span data-ttu-id="25842-104">В этом руководстве будет показано, как работать с конфигурациями на конечный узел.</span><span class="sxs-lookup"><span data-stu-id="25842-104">This guide will show you how to work with Configurations on a target Node.</span></span> <span data-ttu-id="25842-105">В этом руководстве разбивается на следующие действия:</span><span class="sxs-lookup"><span data-stu-id="25842-105">This guide is broken up into the following steps:</span></span>

## <a name="apply-a-configuration"></a><span data-ttu-id="25842-106">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="25842-106">Apply a Configuration</span></span>

<span data-ttu-id="25842-107">Чтобы применить конфигурацию и управлять ею, нам нужно создать файл «.mof».</span><span class="sxs-lookup"><span data-stu-id="25842-107">In order to apply and manage a Configuration, we need to generate a ".mof" file.</span></span> <span data-ttu-id="25842-108">Следующий код будет представлять простую конфигурацию, которая будет использоваться в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="25842-108">The following code will represent a simple Configuration that will be used throughout this guide.</span></span>

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

<span data-ttu-id="25842-109">Компиляция эта конфигурация обеспечит два MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="25842-109">Compiling this configuration will yield two ".mof" files.</span></span>

```output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

<span data-ttu-id="25842-110">Чтобы применить конфигурацию, используйте [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) командлета.</span><span class="sxs-lookup"><span data-stu-id="25842-110">To apply a Configuration, use the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="25842-111">`-Path` Параметр задает каталог, где находятся MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="25842-111">The `-Path` parameter specifies a directory where ".mof" files reside.</span></span> <span data-ttu-id="25842-112">Если не `-Computername` указано, `Start-DSCConfiguration` попытается применяют их к имени компьютера, указанного по имени файла «.mof» (\<computername\>.mof).</span><span class="sxs-lookup"><span data-stu-id="25842-112">If no `-Computername` is specified, `Start-DSCConfiguration` will attempt to apply each Configuration to the computer name specified by the name of the '.mof' file (\<computername\>.mof).</span></span> <span data-ttu-id="25842-113">Укажите `-Verbose` для `Start-DSCConfiguration` Чтобы просмотреть более подробные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="25842-113">Specify `-Verbose` to `Start-DSCConfiguration` to see more verbose output.</span></span>

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

<span data-ttu-id="25842-114">Если `-Wait` не указан, вы увидите одно задание создано.</span><span class="sxs-lookup"><span data-stu-id="25842-114">If `-Wait` is not specified, you see one job created.</span></span> <span data-ttu-id="25842-115">Создано задание будет содержать одну **ChildJob** для каждого файла «.mof» обрабатываемых `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="25842-115">The job created will have one **ChildJob** for each ".mof" file processed by `Start-DSCConfiguration`.</span></span>

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

<span data-ttu-id="25842-116">Если конфигурация занимает много времени и вы хотите остановить его, можно использовать [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) завершить приложения на локальном узле.</span><span class="sxs-lookup"><span data-stu-id="25842-116">If a Configuration is taking a long time and you want to stop it, you can use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) to stop application on the local Node.</span></span>

```powershell
Stop-DSCConfiguration -Force
```

<span data-ttu-id="25842-117">После завершения процесса можно просмотреть состояние заданий через объект задания, возвращаемый [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span><span class="sxs-lookup"><span data-stu-id="25842-117">Once complete, you can view the status of the jobs through the job object returned by [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span></span>

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

<span data-ttu-id="25842-118">Чтобы увидеть **Verbose** выходных данных, используйте следующие команды для просмотра **Verbose** поток для каждого **ChildJob**.</span><span class="sxs-lookup"><span data-stu-id="25842-118">To see the **Verbose** output, use the following commands to view the **Verbose** stream for each **ChildJob**.</span></span> <span data-ttu-id="25842-119">Для получения дополнительных сведений о заданиях PowerShell см. в разделе [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span><span class="sxs-lookup"><span data-stu-id="25842-119">For more about PowerShell jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>

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

<span data-ttu-id="25842-120">Начиная с PowerShell 5.0 `-UseExisting` был добавлен в `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="25842-120">Beginning in PowerShell 5.0, the `-UseExisting` parameter was added to `Start-DSCConfiguration`.</span></span> <span data-ttu-id="25842-121">Путем указания `-UseExisting`, в командлете использовать существующие применяемой конфигурации вместо указанной `-Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="25842-121">By specifying `-UseExisting`, you instruct the cmdlet to use the existing applied Configuration instead of one specified by the `-Path` parameter.</span></span>

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a><span data-ttu-id="25842-122">Проверка конфигурации</span><span class="sxs-lookup"><span data-stu-id="25842-122">Test a Configuration</span></span>

<span data-ttu-id="25842-123">Можно проверить в настоящее время применяются конфигурации с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="25842-123">You can test a currently applied Configuration using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span> <span data-ttu-id="25842-124">`Test-DSCConfiguration` Возвращает `True` , является ли узел соответствует требованиям, и `False` Если это не так.</span><span class="sxs-lookup"><span data-stu-id="25842-124">`Test-DSCConfiguration` will return `True` if the Node is compliant, and `False` if it is not.</span></span>

```powershell
Test-DSCConfiguration
```

<span data-ttu-id="25842-125">Начиная с PowerShell 5.0 `-Detailed` был добавлен параметр, который возвращает объект с коллекциями для **ResourcesInDesiredState** и **ResourcesNotInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="25842-125">Beginning in PowerShell 5.0, the `-Detailed` parameter was added which returns an object with collections for **ResourcesInDesiredState** and **ResourcesNotInDesiredState**</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

<span data-ttu-id="25842-126">Начиная с PowerShell 5.0 можно проверить конфигурацию без его применения.</span><span class="sxs-lookup"><span data-stu-id="25842-126">Beginning in PowerShell 5.0 you can test a Configuration without applying it.</span></span> <span data-ttu-id="25842-127">`-ReferenceConfiguration` Параметр принимает путь к файлу «.mof» для проверки узла на соответствие.</span><span class="sxs-lookup"><span data-stu-id="25842-127">The `-ReferenceConfiguration` parameter accepts the path of a ".mof" file to test the Node against.</span></span> <span data-ttu-id="25842-128">Не **задать** действий под узел.</span><span class="sxs-lookup"><span data-stu-id="25842-128">No **Set** actions are taken against the Node.</span></span> <span data-ttu-id="25842-129">В PowerShell 4.0 существуют обходные пути, чтобы проверить конфигурацию без его применения, но они не рассматриваются здесь.</span><span class="sxs-lookup"><span data-stu-id="25842-129">In PowerShell 4.0, there are workarounds to test a Configuration without applying it, but they are not discussed here.</span></span>

## <a name="get-configuration-values"></a><span data-ttu-id="25842-130">Получить значения конфигурации</span><span class="sxs-lookup"><span data-stu-id="25842-130">Get Configuration Values</span></span>

<span data-ttu-id="25842-131">[Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) командлет возвращает текущие значения для любых ресурсов, настроенных в настоящее время применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="25842-131">The [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet returns the current values for any configured resources in the currently applied Configuration.</span></span>

```powershell
Get-DSCConfiguration
```

<span data-ttu-id="25842-132">Выходные данные в нашем примере конфигурации будет выглядеть следующим образом, если успешно применены.</span><span class="sxs-lookup"><span data-stu-id="25842-132">Output from our sample Configuration would look like this if applied successfully.</span></span>

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

## <a name="get-configuration-status"></a><span data-ttu-id="25842-133">Получение сведений о состоянии конфигурации</span><span class="sxs-lookup"><span data-stu-id="25842-133">Get Configuration Status</span></span>

<span data-ttu-id="25842-134">Начиная с PowerShell 5.0 [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) командлет позволяет просмотреть историю примененных конфигураций для узла.</span><span class="sxs-lookup"><span data-stu-id="25842-134">Beginning in PowerShell 5.0 the [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet allows you to see the history of applied Configurations to the node.</span></span> <span data-ttu-id="25842-135">PowerShell DSC следит за последней конфигурации {{N}}, применяемые в **Push** или **на включение внесенных изменений** режим.</span><span class="sxs-lookup"><span data-stu-id="25842-135">PowerShell DSC keeps track of the last {{N}} Configurations applied in **Push** or **Pull** mode.</span></span> <span data-ttu-id="25842-136">Это включает какой-либо *согласованности* проверок, lcm ее выполняет.</span><span class="sxs-lookup"><span data-stu-id="25842-136">This includes any *consistency* checks executed by the LCM.</span></span> <span data-ttu-id="25842-137">По умолчанию `Get-DSCConfigurationStatus` показано только последней записи журнала.</span><span class="sxs-lookup"><span data-stu-id="25842-137">By default, `Get-DSCConfigurationStatus` shows you the last history entry only.</span></span>

```powershell
Get-DSCConfigurationStatus
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

<span data-ttu-id="25842-138">Используйте `-All` параметр, чтобы просмотреть весь журнал состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="25842-138">Use the `-All` parameter to see all Configuration Status history.</span></span>

> [!NOTE]
> <span data-ttu-id="25842-139">Для краткости производится усечение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="25842-139">Output is truncated for brevity.</span></span>

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

## <a name="manage-configuration-documents"></a><span data-ttu-id="25842-140">Управление документами конфигурации</span><span class="sxs-lookup"><span data-stu-id="25842-140">Manage Configuration Documents</span></span>

<span data-ttu-id="25842-141">LCM управляет конфигурацией узла, работая с **документы конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="25842-141">The LCM manages the Configuration of the Node by working with **Configuration Documents**.</span></span> <span data-ttu-id="25842-142">Эти MOF-файлы находятся в каталоге «C:\Windows\System32\Configuration».</span><span class="sxs-lookup"><span data-stu-id="25842-142">These ".mof" files reside in the "C:\Windows\System32\Configuration" directory.</span></span>

<span data-ttu-id="25842-143">Начиная с PowerShell 5.0 [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) позволяет удалить MOF-файлы для остановки проверки согласованности в будущем или удалить конфигурации, которая имеет ошибки при их применении.</span><span class="sxs-lookup"><span data-stu-id="25842-143">Beginning in PowerShell 5.0 the [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) allows you to remove the ".mof" files to stop future consistency checks or remove a Configuration that has errors when applied.</span></span> <span data-ttu-id="25842-144">`-Stage` Параметр позволяет указать файл «.mof», который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="25842-144">The `-Stage` parameter allows you to specify which ".mof" file you want to remove.</span></span>

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> <span data-ttu-id="25842-145">В PowerShell 4.0, по-прежнему можно удалить эти MOF-файлы непосредственно с помощью [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span><span class="sxs-lookup"><span data-stu-id="25842-145">In PowerShell 4.0, you can still remove these ".mof" files directly using [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span></span>

## <a name="publish-configurations"></a><span data-ttu-id="25842-146">Публикация конфигураций</span><span class="sxs-lookup"><span data-stu-id="25842-146">Publish Configurations</span></span>

<span data-ttu-id="25842-147">Начиная с PowerShell 5.0 [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) был добавлен командлет.</span><span class="sxs-lookup"><span data-stu-id="25842-147">Beginning in PowerShell 5.0, the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet was added.</span></span> <span data-ttu-id="25842-148">Этот командлет позволяет опубликовать файл «.mof» к удаленным компьютерам без его применения.</span><span class="sxs-lookup"><span data-stu-id="25842-148">This cmdlet allows you to publish a ".mof" file to remote computers, without applying it.</span></span>

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a><span data-ttu-id="25842-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="25842-149">See also</span></span>

- [<span data-ttu-id="25842-150">Получение, тестирование и настройка</span><span class="sxs-lookup"><span data-stu-id="25842-150">Get, Test, and Set</span></span>](../resources/get-test-set.md)

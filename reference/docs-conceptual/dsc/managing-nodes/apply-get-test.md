---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Применение, получение и тестирование конфигураций на узле
ms.openlocfilehash: 41f8d2d75d3dd9621de615e7999c2690cb8ce44a
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953841"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a><span data-ttu-id="56465-103">Применение, получение и тестирование конфигураций на узле</span><span class="sxs-lookup"><span data-stu-id="56465-103">Apply, Get, and Test Configurations on a Node</span></span>

<span data-ttu-id="56465-104">В этом руководстве будет показано, как работать с конфигурациями на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="56465-104">This guide will show you how to work with Configurations on a target Node.</span></span> <span data-ttu-id="56465-105">Руководство разбито на описанные ниже этапы.</span><span class="sxs-lookup"><span data-stu-id="56465-105">This guide is broken up into the following steps:</span></span>

## <a name="apply-a-configuration"></a><span data-ttu-id="56465-106">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="56465-106">Apply a Configuration</span></span>

<span data-ttu-id="56465-107">Чтобы применить конфигурацию и управлять ей, нам нужно сгенерировать MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="56465-107">In order to apply and manage a Configuration, we need to generate a ".mof" file.</span></span> <span data-ttu-id="56465-108">Следующий код представляет собой простую конфигурацию, которая будет использоваться в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="56465-108">The following code will represent a simple Configuration that will be used throughout this guide.</span></span>

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

<span data-ttu-id="56465-109">Компиляция этой конфигурации даст два MOF-файла.</span><span class="sxs-lookup"><span data-stu-id="56465-109">Compiling this configuration will yield two ".mof" files.</span></span>

```output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

<span data-ttu-id="56465-110">Чтобы применить конфигурацию, используйте командлет [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="56465-110">To apply a Configuration, use the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="56465-111">Параметр `-Path` указывает каталог, в котором находятся MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="56465-111">The `-Path` parameter specifies a directory where ".mof" files reside.</span></span> <span data-ttu-id="56465-112">Если не указано `-Computername`, `Start-DSCConfiguration` попытается применить каждую конфигурацию к имени компьютера, указанному в имени MOF-файла (\<имя_компьютера\>.mof).</span><span class="sxs-lookup"><span data-stu-id="56465-112">If no `-Computername` is specified, `Start-DSCConfiguration` will attempt to apply each Configuration to the computer name specified by the name of the '.mof' file (\<computername\>.mof).</span></span> <span data-ttu-id="56465-113">Укажите `-Verbose` для `Start-DSCConfiguration`, чтобы увидеть более подробные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="56465-113">Specify `-Verbose` to `Start-DSCConfiguration` to see more verbose output.</span></span>

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

<span data-ttu-id="56465-114">Если `-Wait` не указано, вы увидите одно созданное задание.</span><span class="sxs-lookup"><span data-stu-id="56465-114">If `-Wait` is not specified, you see one job created.</span></span> <span data-ttu-id="56465-115">Созданное задание будет иметь по одному **ChildJob** для каждого MOF-файла, обработанного `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="56465-115">The job created will have one **ChildJob** for each ".mof" file processed by `Start-DSCConfiguration`.</span></span>

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

<span data-ttu-id="56465-116">Если конфигурация занимает много времени и вы хотите остановить ее, вы можете использовать [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration), чтобы остановить приложение на локальном узле.</span><span class="sxs-lookup"><span data-stu-id="56465-116">If a Configuration is taking a long time and you want to stop it, you can use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) to stop application on the local Node.</span></span>

```powershell
Stop-DSCConfiguration -Force
```

<span data-ttu-id="56465-117">После завершения вы можете просматривать состояние заданий через объект задания, возвращаемый [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span><span class="sxs-lookup"><span data-stu-id="56465-117">Once complete, you can view the status of the jobs through the job object returned by [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span></span>

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

<span data-ttu-id="56465-118">Чтобы просмотреть выходные данные **Подробных сведений**, используйте следующие команды для просмотра потока **Подробных сведений** для каждого **ChildJob**.</span><span class="sxs-lookup"><span data-stu-id="56465-118">To see the **Verbose** output, use the following commands to view the **Verbose** stream for each **ChildJob**.</span></span> <span data-ttu-id="56465-119">Дополнительные сведения о заданиях PowerShell см. в разделе [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span><span class="sxs-lookup"><span data-stu-id="56465-119">For more about PowerShell jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>

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

<span data-ttu-id="56465-120">Начиная с PowerShell 5.0, параметр `-UseExisting` был добавлен в `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="56465-120">Beginning in PowerShell 5.0, the `-UseExisting` parameter was added to `Start-DSCConfiguration`.</span></span> <span data-ttu-id="56465-121">Указывая `-UseExisting`, вы даете командлету указание использовать существующую примененную конфигурацию вместо конфигурации, указанной параметром `-Path`.</span><span class="sxs-lookup"><span data-stu-id="56465-121">By specifying `-UseExisting`, you instruct the cmdlet to use the existing applied Configuration instead of one specified by the `-Path` parameter.</span></span>

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a><span data-ttu-id="56465-122">Проверка конфигурации</span><span class="sxs-lookup"><span data-stu-id="56465-122">Test a Configuration</span></span>

<span data-ttu-id="56465-123">Текущую конфигурацию можно проверить, используя [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="56465-123">You can test a currently applied Configuration using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span> <span data-ttu-id="56465-124">`Test-DSCConfiguration` возвращает `True`, если узел соответствует, и `False`, если это не так.</span><span class="sxs-lookup"><span data-stu-id="56465-124">`Test-DSCConfiguration` will return `True` if the Node is compliant, and `False` if it is not.</span></span>

```powershell
Test-DSCConfiguration
```

<span data-ttu-id="56465-125">Начиная с PowerShell 5.0, был добавлен параметр `-Detailed`, который возвращает объект с коллекциями для **ResourcesInDesiredState** и **ResourcesNotInDesiredState**.</span><span class="sxs-lookup"><span data-stu-id="56465-125">Beginning in PowerShell 5.0, the `-Detailed` parameter was added which returns an object with collections for **ResourcesInDesiredState** and **ResourcesNotInDesiredState**</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

<span data-ttu-id="56465-126">Начиная с PowerShell 5.0 конфигурацию можно проверить, не применяя эту команду.</span><span class="sxs-lookup"><span data-stu-id="56465-126">Beginning in PowerShell 5.0 you can test a Configuration without applying it.</span></span> <span data-ttu-id="56465-127">Параметр `-ReferenceConfiguration` принимает путь к MOF-файлу для проверки узла на соответствие.</span><span class="sxs-lookup"><span data-stu-id="56465-127">The `-ReferenceConfiguration` parameter accepts the path of a ".mof" file to test the Node against.</span></span> <span data-ttu-id="56465-128">К узлу не применяется никакой **набор** действий.</span><span class="sxs-lookup"><span data-stu-id="56465-128">No **Set** actions are taken against the Node.</span></span> <span data-ttu-id="56465-129">В PowerShell 4.0 есть обходные пути для проверки конфигурации без применения этой команды, но они здесь не рассматриваются.</span><span class="sxs-lookup"><span data-stu-id="56465-129">In PowerShell 4.0, there are workarounds to test a Configuration without applying it, but they are not discussed here.</span></span>

## <a name="get-configuration-values"></a><span data-ttu-id="56465-130">Получение значений конфигурации</span><span class="sxs-lookup"><span data-stu-id="56465-130">Get Configuration Values</span></span>

<span data-ttu-id="56465-131">Командлет [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) возвращает текущие значения для всех настроенных ресурсов в текущей примененной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56465-131">The [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet returns the current values for any configured resources in the currently applied Configuration.</span></span>

```powershell
Get-DSCConfiguration
```

<span data-ttu-id="56465-132">В случае успешного применения выходные данные нашего примера конфигурации будут выглядеть таким образом.</span><span class="sxs-lookup"><span data-stu-id="56465-132">Output from our sample Configuration would look like this if applied successfully.</span></span>

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

## <a name="get-configuration-status"></a><span data-ttu-id="56465-133">Получение статуса конфигурации</span><span class="sxs-lookup"><span data-stu-id="56465-133">Get Configuration Status</span></span>

<span data-ttu-id="56465-134">Начиная с PowerShell 5.0, командлет [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) позволяет просматривать историю примененных к узлу конфигураций.</span><span class="sxs-lookup"><span data-stu-id="56465-134">Beginning in PowerShell 5.0 the [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet allows you to see the history of applied Configurations to the node.</span></span> <span data-ttu-id="56465-135">PowerShell DSC отслеживает последние конфигурации (в количестве {{N}}), примененные в режиме **Push** или **Pull**.</span><span class="sxs-lookup"><span data-stu-id="56465-135">PowerShell DSC keeps track of the last {{N}} Configurations applied in **Push** or **Pull** mode.</span></span> <span data-ttu-id="56465-136">Это включает в себя любые проверки *согласованности*, выполненные LCM.</span><span class="sxs-lookup"><span data-stu-id="56465-136">This includes any *consistency* checks executed by the LCM.</span></span> <span data-ttu-id="56465-137">По умолчанию `Get-DSCConfigurationStatus` показывает только последнюю запись истории.</span><span class="sxs-lookup"><span data-stu-id="56465-137">By default, `Get-DSCConfigurationStatus` shows you the last history entry only.</span></span>

```powershell
Get-DSCConfigurationStatus
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

<span data-ttu-id="56465-138">Используйте параметр `-All`, чтобы просмотреть всю историю состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56465-138">Use the `-All` parameter to see all Configuration Status history.</span></span>

> [!NOTE]
> <span data-ttu-id="56465-139">Для краткости производится сокращение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="56465-139">Output is truncated for brevity.</span></span>

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

## <a name="manage-configuration-documents"></a><span data-ttu-id="56465-140">Управление документами конфигурации</span><span class="sxs-lookup"><span data-stu-id="56465-140">Manage Configuration Documents</span></span>

<span data-ttu-id="56465-141">LCM управляет конфигурацией узла, работая с **документами конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="56465-141">The LCM manages the Configuration of the Node by working with **Configuration Documents**.</span></span> <span data-ttu-id="56465-142">Эти MOF-файлы находятся в каталоге "C:\Windows\System32\Configuration".</span><span class="sxs-lookup"><span data-stu-id="56465-142">These ".mof" files reside in the "C:\Windows\System32\Configuration" directory.</span></span>

<span data-ttu-id="56465-143">Начиная с PowerShell 5.0, [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) позволяет вам удалять MOF-файлы, чтобы остановить будущие проверки согласованности или удалить конфигурацию, в которой возникают ошибки при применении.</span><span class="sxs-lookup"><span data-stu-id="56465-143">Beginning in PowerShell 5.0 the [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) allows you to remove the ".mof" files to stop future consistency checks or remove a Configuration that has errors when applied.</span></span> <span data-ttu-id="56465-144">Параметр `-Stage` позволяет указать, какой MOF-файл вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="56465-144">The `-Stage` parameter allows you to specify which ".mof" file you want to remove.</span></span>

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> <span data-ttu-id="56465-145">В PowerShell 4.0 вы по-прежнему можете удалять эти MOF-файлы непосредственно, используя [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span><span class="sxs-lookup"><span data-stu-id="56465-145">In PowerShell 4.0, you can still remove these ".mof" files directly using [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span></span>

## <a name="publish-configurations"></a><span data-ttu-id="56465-146">Публикация конфигураций</span><span class="sxs-lookup"><span data-stu-id="56465-146">Publish Configurations</span></span>

<span data-ttu-id="56465-147">Начиная с PowerShell 5.0, был добавлен командлет [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration).</span><span class="sxs-lookup"><span data-stu-id="56465-147">Beginning in PowerShell 5.0, the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet was added.</span></span> <span data-ttu-id="56465-148">Этот командлет позволяет публиковать MOF-файлы на удаленных компьютерах без применения.</span><span class="sxs-lookup"><span data-stu-id="56465-148">This cmdlet allows you to publish a ".mof" file to remote computers, without applying it.</span></span>

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a><span data-ttu-id="56465-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="56465-149">See also</span></span>

- [<span data-ttu-id="56465-150">Получение, тестирование и настройка</span><span class="sxs-lookup"><span data-stu-id="56465-150">Get, Test, and Set</span></span>](../resources/get-test-set.md)

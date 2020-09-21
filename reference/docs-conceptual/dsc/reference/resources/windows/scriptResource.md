---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Script в DSC
ms.openlocfilehash: 9b89981c17e87b3681c6416c7dee44a75c432ea1
ms.sourcegitcommit: eb6a7c01e6385809656ac828b9211683e0b1a6fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "89041135"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="7d8c2-103">Ресурс Script в DSC</span><span class="sxs-lookup"><span data-stu-id="7d8c2-103">DSC Script Resource</span></span>

> <span data-ttu-id="7d8c2-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="7d8c2-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="7d8c2-105">Ресурс `Script` в DSC Windows PowerShell предоставляет механизм запуска блоков сценариев на целевых узлах.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-105">The `Script` resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="7d8c2-106">Ресурс `Script` использует свойства `GetScript`
`SetScript` и `TestScript`, которые содержат блоки скрипта, определяемые вами для выполнения соответствующих операций DSC.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-106">The `Script` resource uses `GetScript`
`SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d8c2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d8c2-107">Syntax</span></span>

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="7d8c2-108">Блоки `GetScript`, `TestScript` и `SetScript` хранятся в виде строк.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-108">`GetScript` `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="7d8c2-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="7d8c2-109">Properties</span></span>

|  <span data-ttu-id="7d8c2-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="7d8c2-110">Property</span></span>  |                                          <span data-ttu-id="7d8c2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7d8c2-111">Description</span></span>                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7d8c2-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-112">GetScript</span></span>  | <span data-ttu-id="7d8c2-113">Блок скрипта, который возвращает текущее состояние узла.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-113">A script block that returns the current state of the Node.</span></span>                                    |
| <span data-ttu-id="7d8c2-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-114">SetScript</span></span>  | <span data-ttu-id="7d8c2-115">Блок скрипта, который DSC использует для обеспечения совместимости, если узел не находится в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
| <span data-ttu-id="7d8c2-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-116">TestScript</span></span> | <span data-ttu-id="7d8c2-117">Блок скрипта, который определяет, находится ли узел в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-117">A script block that determines if the Node is in the desired state.</span></span>                           |
| <span data-ttu-id="7d8c2-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="7d8c2-118">Credential</span></span> | <span data-ttu-id="7d8c2-119">Указывает учетные данные, используемые для запуска этого сценария, если они необходимы.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>        |

## <a name="common-properties"></a><span data-ttu-id="7d8c2-120">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="7d8c2-120">Common properties</span></span>

|       <span data-ttu-id="7d8c2-121">Свойство</span><span class="sxs-lookup"><span data-stu-id="7d8c2-121">Property</span></span>       |                                            <span data-ttu-id="7d8c2-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7d8c2-122">Description</span></span>                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7d8c2-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7d8c2-123">DependsOn</span></span>            | <span data-ttu-id="7d8c2-124">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> |
| <span data-ttu-id="7d8c2-125">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="7d8c2-125">PsDscRunAsCredential</span></span> | <span data-ttu-id="7d8c2-126">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-126">Sets the credential for running the entire resource as.</span></span>                                           |

> [!NOTE]
> <span data-ttu-id="7d8c2-127">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-127">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="7d8c2-128">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="7d8c2-128">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="7d8c2-129">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7d8c2-129">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="7d8c2-130">GetScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-130">GetScript</span></span>

<span data-ttu-id="7d8c2-131">DSC не использует выходные данные из `GetScript`. Командлет [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) выполняет `GetScript`, чтобы получить сведения о текущем состоянии узла.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-131">DSC does not use the output from `GetScript` The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="7d8c2-132">Не требуется возвращаемое значение из `GetScript`. Если вы указываете возвращаемое значение, используйте хэш-таблицу с ключом **Result** со строковым значением.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-132">A return value is not required from `GetScript` If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="7d8c2-133">TestScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-133">TestScript</span></span>

<span data-ttu-id="7d8c2-134">DSC выполняет `TestScript`, чтобы определить, необходим ли запуск `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-134">`TestScript` is executed by DSC to determine if `SetScript` should be run.</span></span> <span data-ttu-id="7d8c2-135">Если `TestScript` возвращает `$false`, DSC выполняет `SetScript`, чтобы вернуть узел в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-135">If `TestScript` returns `$false`, DSC executes `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="7d8c2-136">Этот блок скрипта должен возвращать логическое значение.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-136">It must return a boolean value.</span></span> <span data-ttu-id="7d8c2-137">Значение `$true` указывает, что узел совместим и `SetScript` запускать не нужно.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-137">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="7d8c2-138">Командлет [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) выполняет `TestScript`, чтобы получить сведения о совместимости узлов с ресурсами `Script`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-138">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes `TestScript` to retrieve the nodes compliance with the `Script` resources.</span></span> <span data-ttu-id="7d8c2-139">Но в этом случае `SetScript` не будет запущен независимо от того, какое значение возвращает блок `TestScript`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-139">However, in this case, `SetScript` does not run, no matter what `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="7d8c2-140">Все выходные данные `TestScript` являются частью его возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-140">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="7d8c2-141">PowerShell интерпретирует нескрытые выходные данные как ненулевое значение, поэтому `TestScript` вернет `$true` независимо от состояния узла.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-141">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="7d8c2-142">Это приводит к непредсказуемым результатам, ложноположительным значениям и сложностям при устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-142">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="7d8c2-143">SetScript</span><span class="sxs-lookup"><span data-stu-id="7d8c2-143">SetScript</span></span>

<span data-ttu-id="7d8c2-144">`SetScript` изменяет узел, задавая ему требуемое состояние.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-144">`SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="7d8c2-145">Он вызывается DSC, если блок `TestScript` возвращает значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-145">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="7d8c2-146">`SetScript` не имеет возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-146">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="7d8c2-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="7d8c2-147">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="7d8c2-148">Пример 1: написание примера текста с помощью ресурса Script</span><span class="sxs-lookup"><span data-stu-id="7d8c2-148">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="7d8c2-149">Этот пример проверяет наличие `C:\TempFolder\TestFile.txt` на каждом узле.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-149">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="7d8c2-150">Если такой файл не существует, он создается с помощью `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-150">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="7d8c2-151">`GetScript` возвращает содержимое файла, а его возвращаемое значение не используется.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-151">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="7d8c2-152">Пример 2. Сравнение сведений о версии с помощью ресурса Script</span><span class="sxs-lookup"><span data-stu-id="7d8c2-152">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="7d8c2-153">В этом примере из текстового файла на исходном компьютере извлекаются сведения о _соответствующей_ версии, которые сохраняются в переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-153">This example retrieves the _compliant_ version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="7d8c2-154">При создании MOF-файла узла DSC заменяет переменные `$using:version` в каждом блоке сценария значением переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-154">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="7d8c2-155">Во время выполнения сведения о _соответствующей_ версии сохраняются в текстовом файле на каждом узле. При последующих выполнениях эти сведения сравниваются и обновляются.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-155">During execution, the _compliant_ version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="7d8c2-156">Пример 3. Использование параметров в ресурсе Script</span><span class="sxs-lookup"><span data-stu-id="7d8c2-156">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="7d8c2-157">В этом примере осуществляется доступ к параметрам из ресурса Script с использованием области `using`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-157">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span>
<span data-ttu-id="7d8c2-158">Обратите внимание, что аналогичным образом можно получить доступ к **ConfigurationData**.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-158">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="7d8c2-159">Как и в примере 2, ожидается сохраненная версия в локальном файле на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-159">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="7d8c2-160">Можно настроить как локальный путь к файлу, так и версию, что позволяет отделить код от данных конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-160">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

<span data-ttu-id="7d8c2-161">Полученный MOF-файл включает переменные и их значения, доступ к которым осуществляется через область `using`.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-161">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="7d8c2-162">Они вставляются в каждый блок scriptblock, использующий переменные.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-162">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="7d8c2-163">Сценарии Test и Set были удалены для краткости:</span><span class="sxs-lookup"><span data-stu-id="7d8c2-163">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a><span data-ttu-id="7d8c2-164">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="7d8c2-164">Known Limitations</span></span>

- <span data-ttu-id="7d8c2-165">Учетные данные, передаваемые в рамках ресурса скрипта, не всегда являются надежными при использовании серверной модели извлечения или принудительной отправки.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-165">Credentials being passed within a script resource are not always reliable when using a pull or push server model.</span></span> <span data-ttu-id="7d8c2-166">В этом случае рекомендуется использовать полный ресурс, а не ресурс скрипта.</span><span class="sxs-lookup"><span data-stu-id="7d8c2-166">It is recommended to use a full resource rather than use a script resource in this case.</span></span>

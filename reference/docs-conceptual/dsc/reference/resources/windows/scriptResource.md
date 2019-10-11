---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Script в DSC
ms.openlocfilehash: e09e86011fa7dbb2a4d7f28b5032b4328b6f6ec2
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953071"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="ba17b-103">Ресурс Script в DSC</span><span class="sxs-lookup"><span data-stu-id="ba17b-103">DSC Script Resource</span></span>

> <span data-ttu-id="ba17b-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="ba17b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="ba17b-105">Ресурс **Script** в DSC Windows PowerShell предоставляет механизм запуска блоков сценариев на целевых узлах.</span><span class="sxs-lookup"><span data-stu-id="ba17b-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="ba17b-106">Ресурс **Script** имеет свойства **GetScript**, **SetScript** и **TestScript**, которые содержат блоки скриптов, определяемые вами для выполнения соответствующих операций DSC.</span><span class="sxs-lookup"><span data-stu-id="ba17b-106">The **Script** resource uses **GetScript**, **SetScript**, and **TestScript** properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba17b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba17b-107">Syntax</span></span>

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
> <span data-ttu-id="ba17b-108">Блоки **GetScript**, **TestScript** и **SetScript** хранятся в виде строк.</span><span class="sxs-lookup"><span data-stu-id="ba17b-108">**GetScript**, **TestScript**, and **SetScript** blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="ba17b-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="ba17b-109">Properties</span></span>

|<span data-ttu-id="ba17b-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="ba17b-110">Property</span></span> |<span data-ttu-id="ba17b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ba17b-111">Description</span></span> |
|---|---|
|<span data-ttu-id="ba17b-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-112">GetScript</span></span> |<span data-ttu-id="ba17b-113">Блок скрипта, который возвращает текущее состояние узла.</span><span class="sxs-lookup"><span data-stu-id="ba17b-113">A script block that returns the current state of the Node.</span></span> |
|<span data-ttu-id="ba17b-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-114">SetScript</span></span> |<span data-ttu-id="ba17b-115">Блок скрипта, который DSC использует для обеспечения совместимости, если узел не находится в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="ba17b-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
|<span data-ttu-id="ba17b-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-116">TestScript</span></span> |<span data-ttu-id="ba17b-117">Блок скрипта, который определяет, находится ли узел в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="ba17b-117">A script block that determines if the Node is in the desired state.</span></span> |
|<span data-ttu-id="ba17b-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="ba17b-118">Credential</span></span> |<span data-ttu-id="ba17b-119">Указывает учетные данные, используемые для запуска этого сценария, если они необходимы.</span><span class="sxs-lookup"><span data-stu-id="ba17b-119">Indicates the credentials to use for running this script, if credentials are required.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="ba17b-120">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="ba17b-120">Common properties</span></span>

|<span data-ttu-id="ba17b-121">Свойство</span><span class="sxs-lookup"><span data-stu-id="ba17b-121">Property</span></span> |<span data-ttu-id="ba17b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ba17b-122">Description</span></span> |
|---|---|
|<span data-ttu-id="ba17b-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ba17b-123">DependsOn</span></span> |<span data-ttu-id="ba17b-124">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ba17b-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ba17b-125">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="ba17b-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ba17b-126">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ba17b-126">PsDscRunAsCredential</span></span> |<span data-ttu-id="ba17b-127">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="ba17b-127">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="ba17b-128">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ba17b-128">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="ba17b-129">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="ba17b-129">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="ba17b-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ba17b-130">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="ba17b-131">GetScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-131">GetScript</span></span>

<span data-ttu-id="ba17b-132">DSC не использует выходные данные **GetScript**.</span><span class="sxs-lookup"><span data-stu-id="ba17b-132">DSC does not use the output from **GetScript**.</span></span> <span data-ttu-id="ba17b-133">Командлет [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) выполняет **GetScript**, чтобы получить сведения о текущем состоянии узла.</span><span class="sxs-lookup"><span data-stu-id="ba17b-133">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes **GetScript** to retrieve a node's current state.</span></span> <span data-ttu-id="ba17b-134">**GetScript** может не возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="ba17b-134">A return value is not required from **GetScript**.</span></span> <span data-ttu-id="ba17b-135">Если вы указываете возвращаемое значение, используйте хеш-таблицу с ключом **Result** со строковым значением.</span><span class="sxs-lookup"><span data-stu-id="ba17b-135">If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="ba17b-136">TestScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-136">TestScript</span></span>

<span data-ttu-id="ba17b-137">DSC выполняет **TestScript**, чтобы определить, необходим ли запуск **SetScript**.</span><span class="sxs-lookup"><span data-stu-id="ba17b-137">**TestScript** is executed by DSC to determine if **SetScript** should be run.</span></span> <span data-ttu-id="ba17b-138">Если **TestScript** возвращает `$false`, DSC выполняет **SetScript**, чтобы вернуть узел в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="ba17b-138">If **TestScript** returns `$false`, DSC executes **SetScript** to bring the node back to the desired state.</span></span> <span data-ttu-id="ba17b-139">Этот блок скрипта должен возвращать логическое значение.</span><span class="sxs-lookup"><span data-stu-id="ba17b-139">It must return a boolean value.</span></span> <span data-ttu-id="ba17b-140">Значение `$true` указывает, что узел совместим и **SetScript** запускать не нужно.</span><span class="sxs-lookup"><span data-stu-id="ba17b-140">A result of `$true` indicates that the node is compliant and **SetScript** should not executed.</span></span>

<span data-ttu-id="ba17b-141">Командлет [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) выполняет **TestScript**, чтобы получить сведения о совместимости узлов с ресурсами **Script**.</span><span class="sxs-lookup"><span data-stu-id="ba17b-141">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes **TestScript** to retrieve the nodes compliance with the **Script** resources.</span></span>
<span data-ttu-id="ba17b-142">Но в этом случае **SetScript** не будет запущен независимо от того, какое значение возвращает блок **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="ba17b-142">However, in this case, **SetScript** does not run, no matter what **TestScript** block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="ba17b-143">Все выходные данные **TestScript** являются частью его возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ba17b-143">All output from your **TestScript** is part of its return value.</span></span> <span data-ttu-id="ba17b-144">PowerShell интерпретирует нескрытые выходные данные как ненулевое значение, поэтому **TestScript** вернет `$true`, независимо от состояния узла.</span><span class="sxs-lookup"><span data-stu-id="ba17b-144">PowerShell interprets unsuppressed output as non-zero, which means that your **TestScript** will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="ba17b-145">Это приводит к непредсказуемым результатам, ложноположительным значениям и сложностям при устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="ba17b-145">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="ba17b-146">SetScript</span><span class="sxs-lookup"><span data-stu-id="ba17b-146">SetScript</span></span>

<span data-ttu-id="ba17b-147">**SetScript** изменяет узел, задавая ему требуемое состояние.</span><span class="sxs-lookup"><span data-stu-id="ba17b-147">**SetScript** modifies the node to enforce the desired state.</span></span> <span data-ttu-id="ba17b-148">Он вызывается DSC, если блок **TestScript** возвращает значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="ba17b-148">It is called by DSC if the **TestScript** script block returns `$false`.</span></span> <span data-ttu-id="ba17b-149">**SetScript** не имеет возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ba17b-149">The **SetScript** should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="ba17b-150">Примеры</span><span class="sxs-lookup"><span data-stu-id="ba17b-150">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="ba17b-151">Пример 1: написание примера текста с помощью ресурса Script</span><span class="sxs-lookup"><span data-stu-id="ba17b-151">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="ba17b-152">Этот пример проверяет наличие `C:\TempFolder\TestFile.txt` на каждом узле.</span><span class="sxs-lookup"><span data-stu-id="ba17b-152">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="ba17b-153">Если такой файл не существует, он создается с помощью `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="ba17b-153">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="ba17b-154">`GetScript` возвращает содержимое файла, а его возвращаемое значение не используется.</span><span class="sxs-lookup"><span data-stu-id="ba17b-154">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="ba17b-155">Пример 2. Сравнение сведений о версии с помощью ресурса Script</span><span class="sxs-lookup"><span data-stu-id="ba17b-155">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="ba17b-156">В этом примере из текстового файла на исходном компьютере извлекаются сведения о *соответствующей* версии, которые сохраняются в переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="ba17b-156">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="ba17b-157">При создании MOF-файла узла DSC заменяет переменные `$using:version` в каждом блоке сценария значением переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="ba17b-157">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="ba17b-158">Во время выполнения сведения о *соответствующей* версии сохраняются в текстовом файле на каждом узле. При последующих выполнениях эти сведения сравниваются и обновляются.</span><span class="sxs-lookup"><span data-stu-id="ba17b-158">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

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

                if( $state['Result'] -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
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
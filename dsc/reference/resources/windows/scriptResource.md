---
ms.date: 08/24/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Script в DSC
ms.openlocfilehash: ef84239820a44aab2a028f7f0fe17653a851b72e
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047756"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="71b6e-103">Ресурс Script в DSC</span><span class="sxs-lookup"><span data-stu-id="71b6e-103">DSC Script Resource</span></span>

> <span data-ttu-id="71b6e-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="71b6e-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="71b6e-105">Ресурс **Script** в DSC Windows PowerShell предоставляет механизм запуска блоков сценариев на целевых узлах.</span><span class="sxs-lookup"><span data-stu-id="71b6e-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="71b6e-106">Ресурс **Script** имеет свойства `GetScript`, `SetScript` и `TestScript`, которые содержат блоки скрипта, определяемые вами для выполнения соответствующих операций DSC.</span><span class="sxs-lookup"><span data-stu-id="71b6e-106">The **Script** resource uses `GetScript`, `SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="71b6e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71b6e-107">Syntax</span></span>

```
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

> [!NOTE]
> <span data-ttu-id="71b6e-108">Блоки `GetScript`, `TestScript` и `SetScript` хранятся в виде строк.</span><span class="sxs-lookup"><span data-stu-id="71b6e-108">The `GetScript`, `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="71b6e-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="71b6e-109">Properties</span></span>

|<span data-ttu-id="71b6e-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="71b6e-110">Property</span></span>|<span data-ttu-id="71b6e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="71b6e-111">Description</span></span>|
|--------|-----------|
|<span data-ttu-id="71b6e-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-112">GetScript</span></span>|<span data-ttu-id="71b6e-113">Блок скрипта, который возвращает текущее состояние узла.</span><span class="sxs-lookup"><span data-stu-id="71b6e-113">A script block that returns the current state of the Node.</span></span>|
|<span data-ttu-id="71b6e-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-114">SetScript</span></span>|<span data-ttu-id="71b6e-115">Блок скрипта, который DSC использует для обеспечения совместимости, если узел не находится в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="71b6e-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span>|
|<span data-ttu-id="71b6e-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-116">TestScript</span></span>|<span data-ttu-id="71b6e-117">Блок скрипта, который определяет, находится ли узел в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="71b6e-117">A script block that determines if the Node is in the desired state.</span></span>|
|<span data-ttu-id="71b6e-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="71b6e-118">Credential</span></span>| <span data-ttu-id="71b6e-119">Указывает учетные данные, используемые для запуска этого сценария, если они необходимы.</span><span class="sxs-lookup"><span data-stu-id="71b6e-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>|
|<span data-ttu-id="71b6e-120">DependsOn</span><span class="sxs-lookup"><span data-stu-id="71b6e-120">DependsOn</span></span>| <span data-ttu-id="71b6e-121">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="71b6e-121">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="71b6e-122">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-122">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>

### <a name="getscript"></a><span data-ttu-id="71b6e-123">GetScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-123">GetScript</span></span>

<span data-ttu-id="71b6e-124">DSC не использует выходные данные `GetScript`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-124">DSC does not use the output from `GetScript`.</span></span> <span data-ttu-id="71b6e-125">Командлет [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) выполняет `GetScript`, чтобы получить сведения о текущем состоянии узла.</span><span class="sxs-lookup"><span data-stu-id="71b6e-125">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes the `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="71b6e-126">`GetScript` может не возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="71b6e-126">A return value is not required from `GetScript`.</span></span> <span data-ttu-id="71b6e-127">Если вы указываете возвращаемое значение, используйте `hashtable` с ключом **Result** со значением `String`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-127">If you specify a return value, it must be a `hashtable` containing a **Result** key whose value is a `String`.</span></span>

### <a name="testscript"></a><span data-ttu-id="71b6e-128">TestScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-128">TestScript</span></span>

<span data-ttu-id="71b6e-129">`TestScript` выполняется DSC, чтобы определить, необходим ли запуск `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-129">The `TestScript` is executed by DSC to determine if the `SetScript` should be run.</span></span> <span data-ttu-id="71b6e-130">Если `TestScript` возвращает `$false`, DSC выполняет `SetScript`, чтобы вернуть узел в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="71b6e-130">If the `TestScript` returns `$false`, DSC executes the `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="71b6e-131">Этот блок скрипта должен возвращать значение `boolean`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-131">It must return a `boolean` value.</span></span> <span data-ttu-id="71b6e-132">Значение `$true` указывает, что узел совместим и `SetScript` запускать не нужно.</span><span class="sxs-lookup"><span data-stu-id="71b6e-132">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="71b6e-133">Командлет [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) выполняет `TestScript`, чтобы получить сведения о совместимости узлов с ресурсами **Script**.</span><span class="sxs-lookup"><span data-stu-id="71b6e-133">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes the `TestScript` to retrieve the nodes compliance with the  **Script** resources.</span></span> <span data-ttu-id="71b6e-134">Но в этом случае `SetScript` не будет запущен независимо от того, какое значение возвращает блок `TestScript`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-134">However, in this case, the `SetScript` does not run, no matter what the `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="71b6e-135">Все выходные данные `TestScript` являются частью его возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="71b6e-135">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="71b6e-136">PowerShell интерпретирует нескрытые выходные данные как ненулевое значение, поэтому `TestScript` вернет `$true` независимо от состояния узла.</span><span class="sxs-lookup"><span data-stu-id="71b6e-136">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span>
> <span data-ttu-id="71b6e-137">Это приводит к непредсказуемым результатам, ложноположительным значениям и сложностям при устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="71b6e-137">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

### <a name="setscript"></a><span data-ttu-id="71b6e-138">SetScript</span><span class="sxs-lookup"><span data-stu-id="71b6e-138">SetScript</span></span>

<span data-ttu-id="71b6e-139">`SetScript` изменяет узел, задавая ему требуемое состояние.</span><span class="sxs-lookup"><span data-stu-id="71b6e-139">The `SetScript` modifies the node to enfore the desired state.</span></span> <span data-ttu-id="71b6e-140">Он вызывается DSC, если блок `TestScript` возвращает значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-140">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="71b6e-141">`SetScript` не имеет возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="71b6e-141">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="71b6e-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="71b6e-142">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="71b6e-143">Пример 1: Запись образец текста, с помощью сценария ресурса</span><span class="sxs-lookup"><span data-stu-id="71b6e-143">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="71b6e-144">Этот пример проверяет наличие `C:\TempFolder\TestFile.txt` на каждом узле.</span><span class="sxs-lookup"><span data-stu-id="71b6e-144">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="71b6e-145">Если такой файл не существует, он создается с помощью `SetScript`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-145">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="71b6e-146">`GetScript` возвращает содержимое файла, а его возвращаемое значение не используется.</span><span class="sxs-lookup"><span data-stu-id="71b6e-146">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="71b6e-147">Пример 2. Сравнение сведений о версии, с помощью сценария ресурса</span><span class="sxs-lookup"><span data-stu-id="71b6e-147">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="71b6e-148">В этом примере из текстового файла на исходном компьютере извлекаются сведения о *соответствующей* версии, которые сохраняются в переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-148">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="71b6e-149">При создании MOF-файла узла DSC заменяет переменные `$using:version` в каждом блоке сценария значением переменной `$version`.</span><span class="sxs-lookup"><span data-stu-id="71b6e-149">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span> <span data-ttu-id="71b6e-150">Во время выполнения сведения о *соответствующей* версии сохраняются в текстовом файле на каждом узле. При последующих выполнениях эти сведения сравниваются и обновляются.</span><span class="sxs-lookup"><span data-stu-id="71b6e-150">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

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
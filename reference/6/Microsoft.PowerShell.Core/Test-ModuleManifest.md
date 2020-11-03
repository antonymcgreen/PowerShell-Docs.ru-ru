---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 03f32d798a9e7ec1e58cdeb4ddf5d30edccd2490
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229245"
---
# <span data-ttu-id="06f4f-103">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="06f4f-103">Test-ModuleManifest</span></span>

## <span data-ttu-id="06f4f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06f4f-104">SYNOPSIS</span></span>
<span data-ttu-id="06f4f-105">Проверяет, точно ли описывает файл манифеста модуля его содержимое.</span><span class="sxs-lookup"><span data-stu-id="06f4f-105">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="06f4f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06f4f-106">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="06f4f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06f4f-107">DESCRIPTION</span></span>

<span data-ttu-id="06f4f-108">Командлет **Test-ModuleManifest** проверяет, находятся ли файлы, перечисленные в файле манифеста модуля (. PSD1), в указанных путях.</span><span class="sxs-lookup"><span data-stu-id="06f4f-108">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="06f4f-109">Этот командлет помогает разработчикам модулей тестировать файлы манифестов.</span><span class="sxs-lookup"><span data-stu-id="06f4f-109">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="06f4f-110">Пользователи модулей также могут использовать этот командлет в сценариях и командах для обнаружения ошибок перед выполнением скриптов, зависящих от модуля.</span><span class="sxs-lookup"><span data-stu-id="06f4f-110">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="06f4f-111">Командлет **Test-ModuleManifest** возвращает объект, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="06f4f-111">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="06f4f-112">Это тот же тип объекта, который Get-Module возвращает.</span><span class="sxs-lookup"><span data-stu-id="06f4f-112">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="06f4f-113">Если какой-либо файл отсутствует в местоположении, указанном в манифесте, выдается ошибка для каждого отсутствующего файла.</span><span class="sxs-lookup"><span data-stu-id="06f4f-113">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="06f4f-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="06f4f-114">EXAMPLES</span></span>

### <span data-ttu-id="06f4f-115">Пример 1. Тестирование манифеста</span><span class="sxs-lookup"><span data-stu-id="06f4f-115">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="06f4f-116">Эта команда проверяет манифест модуля TestModule.psd1.</span><span class="sxs-lookup"><span data-stu-id="06f4f-116">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="06f4f-117">Пример 2. Тестирование манифеста с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="06f4f-117">Example 2: Test a manifest by using the pipeline</span></span>

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="06f4f-118">Эта команда использует конвейерный оператор (|) для отправки строки пути в **Test-ModuleManifest**.</span><span class="sxs-lookup"><span data-stu-id="06f4f-118">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="06f4f-119">В выходных данных команды видно, что тест закончился ошибкой, так как не найден файл TestTypes.ps1xml, указанный в манифесте.</span><span class="sxs-lookup"><span data-stu-id="06f4f-119">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="06f4f-120">Пример 3. Написание функции для тестирования манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="06f4f-120">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="06f4f-121">Эта функция похожа на **Test-ModuleManifest** , но возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="06f4f-121">This function is like **Test-ModuleManifest** , but it returns a Boolean value.</span></span>
<span data-ttu-id="06f4f-122">Функция возвращает $True, если манифест прошел проверку и $False иным образом.</span><span class="sxs-lookup"><span data-stu-id="06f4f-122">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="06f4f-123">Функция использует командлет Get-ChildItem Alias = dir для получения манифеста модуля, указанного $path переменной.</span><span class="sxs-lookup"><span data-stu-id="06f4f-123">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="06f4f-124">Команда использует конвейерный оператор (|) для передачи объекта File в **Test-ModuleManifest**.</span><span class="sxs-lookup"><span data-stu-id="06f4f-124">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="06f4f-125">Командлет **Test-ModuleManifest** использует общий параметр *ErrorAction* со значением SilentlyContinue, чтобы подавить отображение ошибок, формируемых командой.</span><span class="sxs-lookup"><span data-stu-id="06f4f-125">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="06f4f-126">Он также сохраняет объект **PSModuleInfo** , возвращаемый командлетом **Test-ModuleManifest** , в переменную $a.</span><span class="sxs-lookup"><span data-stu-id="06f4f-126">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="06f4f-127">Поэтому объект не отображается.</span><span class="sxs-lookup"><span data-stu-id="06f4f-127">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="06f4f-128">Затем в отдельной команде функция отображает значение $?</span><span class="sxs-lookup"><span data-stu-id="06f4f-128">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="06f4f-129">Автоматическая переменная.</span><span class="sxs-lookup"><span data-stu-id="06f4f-129">automatic variable.</span></span>
<span data-ttu-id="06f4f-130">Если предыдущая команда не создает ошибку, команда отображает $True и $False в противном случае.</span><span class="sxs-lookup"><span data-stu-id="06f4f-130">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="06f4f-131">Эту функцию можно использовать в условных инструкциях, например тех, которые могут предшествовать команде **Import-Module** , или команде, которая использует этот модуль.</span><span class="sxs-lookup"><span data-stu-id="06f4f-131">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="06f4f-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06f4f-132">PARAMETERS</span></span>

### <span data-ttu-id="06f4f-133">-Path</span><span class="sxs-lookup"><span data-stu-id="06f4f-133">-Path</span></span>

<span data-ttu-id="06f4f-134">Указывает путь и имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="06f4f-134">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="06f4f-135">Введите необязательный путь и имя файла манифеста модуля с расширением имени файла PSD1.</span><span class="sxs-lookup"><span data-stu-id="06f4f-135">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="06f4f-136">Местоположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="06f4f-136">The default location is the current directory.</span></span>
<span data-ttu-id="06f4f-137">Подстановочные знаки поддерживаются, но должны разрешаться в один файл манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="06f4f-137">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="06f4f-138">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="06f4f-138">This parameter is required.</span></span>
<span data-ttu-id="06f4f-139">Можно также передать путь в командлет **Test-ModuleManifest** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="06f4f-139">You can also pipe a path to **Test-ModuleManifest**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="06f4f-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="06f4f-140">CommonParameters</span></span>

<span data-ttu-id="06f4f-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06f4f-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06f4f-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06f4f-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06f4f-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="06f4f-143">INPUTS</span></span>

### <span data-ttu-id="06f4f-144">System.String</span><span class="sxs-lookup"><span data-stu-id="06f4f-144">System.String</span></span>

<span data-ttu-id="06f4f-145">Путь к манифесту модуля можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="06f4f-145">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="06f4f-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="06f4f-146">OUTPUTS</span></span>

### <span data-ttu-id="06f4f-147">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="06f4f-147">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="06f4f-148">Этот командлет возвращает объект **PSModuleInfo** , представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="06f4f-148">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="06f4f-149">Объект возвращается даже при наличии ошибок в манифесте.</span><span class="sxs-lookup"><span data-stu-id="06f4f-149">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="06f4f-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="06f4f-150">NOTES</span></span>

## <span data-ttu-id="06f4f-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="06f4f-151">RELATED LINKS</span></span>

[<span data-ttu-id="06f4f-152">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="06f4f-152">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="06f4f-153">Get-Module</span><span class="sxs-lookup"><span data-stu-id="06f4f-153">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="06f4f-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="06f4f-154">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="06f4f-155">New-Module</span><span class="sxs-lookup"><span data-stu-id="06f4f-155">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="06f4f-156">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="06f4f-156">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="06f4f-157">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="06f4f-157">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="06f4f-158">about_Modules</span><span class="sxs-lookup"><span data-stu-id="06f4f-158">about_Modules</span></span>](About/about_Modules.md)

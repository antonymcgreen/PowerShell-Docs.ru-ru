---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: c86a7253335b91011d2eb225bc53d1c5cc671aff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601089"
---
# <span data-ttu-id="dfcaa-102">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="dfcaa-102">Test-ModuleManifest</span></span>

## <span data-ttu-id="dfcaa-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dfcaa-103">SYNOPSIS</span></span>
<span data-ttu-id="dfcaa-104">Проверяет, точно ли описывает файл манифеста модуля его содержимое.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-104">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="dfcaa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dfcaa-105">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="dfcaa-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dfcaa-106">DESCRIPTION</span></span>

<span data-ttu-id="dfcaa-107">Командлет **Test-ModuleManifest** проверяет, находятся ли файлы, перечисленные в файле манифеста модуля (. PSD1), в указанных путях.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-107">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="dfcaa-108">Этот командлет помогает разработчикам модулей тестировать файлы манифестов.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-108">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="dfcaa-109">Пользователи модулей также могут использовать этот командлет в сценариях и командах для обнаружения ошибок перед выполнением скриптов, зависящих от модуля.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-109">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="dfcaa-110">Командлет **Test-ModuleManifest** возвращает объект, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-110">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="dfcaa-111">Это тот же тип объекта, который Get-Module возвращает.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-111">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="dfcaa-112">Если какой-либо файл отсутствует в местоположении, указанном в манифесте, выдается ошибка для каждого отсутствующего файла.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-112">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="dfcaa-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="dfcaa-113">EXAMPLES</span></span>

### <span data-ttu-id="dfcaa-114">Пример 1. Тестирование манифеста</span><span class="sxs-lookup"><span data-stu-id="dfcaa-114">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="dfcaa-115">Эта команда проверяет манифест модуля TestModule.psd1.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-115">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="dfcaa-116">Пример 2. Тестирование манифеста с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="dfcaa-116">Example 2: Test a manifest by using the pipeline</span></span>

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

<span data-ttu-id="dfcaa-117">Эта команда использует конвейерный оператор (|) для отправки строки пути в **Test-ModuleManifest**.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-117">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="dfcaa-118">В выходных данных команды видно, что тест закончился ошибкой, так как не найден файл TestTypes.ps1xml, указанный в манифесте.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-118">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="dfcaa-119">Пример 3. Написание функции для тестирования манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="dfcaa-119">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="dfcaa-120">Эта функция похожа на **Test-ModuleManifest**, но возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-120">This function is like **Test-ModuleManifest**, but it returns a Boolean value.</span></span>
<span data-ttu-id="dfcaa-121">Функция возвращает $True, если манифест прошел проверку и $False иным образом.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-121">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="dfcaa-122">Функция использует командлет Get-ChildItem Alias = dir для получения манифеста модуля, указанного $path переменной.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-122">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="dfcaa-123">Команда использует конвейерный оператор (|) для передачи объекта File в **Test-ModuleManifest**.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-123">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="dfcaa-124">Командлет **Test-ModuleManifest** использует общий параметр *ErrorAction* со значением SilentlyContinue, чтобы подавить отображение ошибок, формируемых командой.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-124">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="dfcaa-125">Он также сохраняет объект **PSModuleInfo** , возвращаемый командлетом **Test-ModuleManifest** , в переменную $a.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-125">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="dfcaa-126">Поэтому объект не отображается.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-126">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="dfcaa-127">Затем в отдельной команде функция отображает значение $?</span><span class="sxs-lookup"><span data-stu-id="dfcaa-127">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="dfcaa-128">Автоматическая переменная.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-128">automatic variable.</span></span>
<span data-ttu-id="dfcaa-129">Если предыдущая команда не создает ошибку, команда отображает $True и $False в противном случае.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-129">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="dfcaa-130">Эту функцию можно использовать в условных инструкциях, например тех, которые могут предшествовать команде **Import-Module** , или команде, которая использует этот модуль.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-130">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="dfcaa-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dfcaa-131">PARAMETERS</span></span>

### <span data-ttu-id="dfcaa-132">-Path</span><span class="sxs-lookup"><span data-stu-id="dfcaa-132">-Path</span></span>

<span data-ttu-id="dfcaa-133">Указывает путь и имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-133">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="dfcaa-134">Введите необязательный путь и имя файла манифеста модуля с расширением имени файла PSD1.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-134">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="dfcaa-135">Местоположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-135">The default location is the current directory.</span></span>
<span data-ttu-id="dfcaa-136">Подстановочные знаки поддерживаются, но должны разрешаться в один файл манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-136">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="dfcaa-137">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-137">This parameter is required.</span></span>
<span data-ttu-id="dfcaa-138">Можно также передать путь в командлет **Test-ModuleManifest** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-138">You can also pipe a path to **Test-ModuleManifest**.</span></span>

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

### <span data-ttu-id="dfcaa-139">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dfcaa-139">CommonParameters</span></span>

<span data-ttu-id="dfcaa-140">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dfcaa-141">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dfcaa-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dfcaa-142">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dfcaa-142">INPUTS</span></span>

### <span data-ttu-id="dfcaa-143">System.String</span><span class="sxs-lookup"><span data-stu-id="dfcaa-143">System.String</span></span>

<span data-ttu-id="dfcaa-144">Путь к манифесту модуля можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-144">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="dfcaa-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dfcaa-145">OUTPUTS</span></span>

### <span data-ttu-id="dfcaa-146">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="dfcaa-146">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="dfcaa-147">Этот командлет возвращает объект **PSModuleInfo** , представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-147">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="dfcaa-148">Объект возвращается даже при наличии ошибок в манифесте.</span><span class="sxs-lookup"><span data-stu-id="dfcaa-148">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="dfcaa-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dfcaa-149">NOTES</span></span>

## <span data-ttu-id="dfcaa-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dfcaa-150">RELATED LINKS</span></span>

[<span data-ttu-id="dfcaa-151">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="dfcaa-151">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="dfcaa-152">Get-Module</span><span class="sxs-lookup"><span data-stu-id="dfcaa-152">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="dfcaa-153">Import-Module</span><span class="sxs-lookup"><span data-stu-id="dfcaa-153">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="dfcaa-154">New-Module</span><span class="sxs-lookup"><span data-stu-id="dfcaa-154">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="dfcaa-155">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="dfcaa-155">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="dfcaa-156">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="dfcaa-156">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="dfcaa-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="dfcaa-157">about_Modules</span></span>](About/about_Modules.md)


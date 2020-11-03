---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 3dca5f922f31690bb78ccc610b4ed44b7423ca47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227093"
---
# <span data-ttu-id="63a7e-103">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="63a7e-103">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="63a7e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="63a7e-104">SYNOPSIS</span></span>
<span data-ttu-id="63a7e-105">Создает файл, который определяет набор возможностей, предоставляемых через конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-105">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="63a7e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63a7e-106">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="63a7e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="63a7e-107">DESCRIPTION</span></span>

<span data-ttu-id="63a7e-108">`New-PSRoleCapabilityFile`Командлет создает файл, который определяет набор возможностей пользователя, которые могут быть предоставлены через файлы конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-108">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="63a7e-109">Это включает определение того, какие командлеты, функции и скрипты доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="63a7e-109">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="63a7e-110">Файл возможностей — это текстовый файл, доступный для чтения и содержащий хэш-таблицу свойств и значений конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-110">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="63a7e-111">Файл имеет расширение pSrc и может использоваться более чем в одной конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-111">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="63a7e-112">Все параметры `New-PSRoleCapabilityFile` являются необязательными, за исключением параметра **path** , который указывает путь к файлу для файла.</span><span class="sxs-lookup"><span data-stu-id="63a7e-112">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="63a7e-113">Если параметр не включен при выполнении командлета, соответствующий ключ в файле конфигурации сеанса заносится в комментарий, за исключением тех случаев, где указано в описании параметра.</span><span class="sxs-lookup"><span data-stu-id="63a7e-113">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="63a7e-114">Например, если не включить параметр **ассемблиестолоад** , то этот раздел файла конфигурации сеанса будет добавлен в комментарий.</span><span class="sxs-lookup"><span data-stu-id="63a7e-114">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="63a7e-115">Чтобы использовать файл возможностей роли в конфигурации сеанса, сначала поместите файл во вложенную папку **RoleCapabilities** допустимой папки модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63a7e-115">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="63a7e-116">Затем сослаться на файл по имени в поле **RoleDefinitions** в файле конфигурации сеанса PowerShell (. pssc).</span><span class="sxs-lookup"><span data-stu-id="63a7e-116">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="63a7e-117">Этот командлет появился в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="63a7e-117">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="63a7e-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="63a7e-118">EXAMPLES</span></span>

### <span data-ttu-id="63a7e-119">Пример 1. Создание пустого файла возможностей роли</span><span class="sxs-lookup"><span data-stu-id="63a7e-119">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="63a7e-120">В этом примере создается новый файл возможностей роли, который использует значения по умолчанию (пустые).</span><span class="sxs-lookup"><span data-stu-id="63a7e-120">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="63a7e-121">Затем файл можно изменить в текстовом редакторе для изменения этих параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="63a7e-121">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="63a7e-122">Пример 2. Создание файла возможностей роли, позволяющего пользователям перезапускать службы и любой компьютер VDI</span><span class="sxs-lookup"><span data-stu-id="63a7e-122">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="63a7e-123">В этом примере создается пример файла возможностей роли, который позволяет пользователям перезапускать службы и компьютеры, соответствующие определенному шаблону имени.</span><span class="sxs-lookup"><span data-stu-id="63a7e-123">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="63a7e-124">Фильтрация имен определяется путем присвоения параметру **ValidatePattern** регулярного выражения `VDI\d+` .</span><span class="sxs-lookup"><span data-stu-id="63a7e-124">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## <span data-ttu-id="63a7e-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63a7e-125">PARAMETERS</span></span>

### <span data-ttu-id="63a7e-126">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="63a7e-126">-AliasDefinitions</span></span>

<span data-ttu-id="63a7e-127">Добавляет указанные псевдонимы в сеансы, которые используют файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-127">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-128">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="63a7e-128">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="63a7e-129">Название</span><span class="sxs-lookup"><span data-stu-id="63a7e-129">Name.</span></span> <span data-ttu-id="63a7e-130">Имя псевдонима.</span><span class="sxs-lookup"><span data-stu-id="63a7e-130">Name of the alias.</span></span> <span data-ttu-id="63a7e-131">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-131">This key is required.</span></span>
- <span data-ttu-id="63a7e-132">Значение.</span><span class="sxs-lookup"><span data-stu-id="63a7e-132">Value.</span></span> <span data-ttu-id="63a7e-133">Команда, которая представляет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="63a7e-133">The command that the alias represents.</span></span> <span data-ttu-id="63a7e-134">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-134">This key is required.</span></span>
- <span data-ttu-id="63a7e-135">Описание.</span><span class="sxs-lookup"><span data-stu-id="63a7e-135">Description.</span></span> <span data-ttu-id="63a7e-136">Текстовая строка с описанием псевдонима.</span><span class="sxs-lookup"><span data-stu-id="63a7e-136">A text string that describes the alias.</span></span> <span data-ttu-id="63a7e-137">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-137">This key is optional.</span></span>
- <span data-ttu-id="63a7e-138">Параметры.</span><span class="sxs-lookup"><span data-stu-id="63a7e-138">Options.</span></span> <span data-ttu-id="63a7e-139">Параметры псевдонима.</span><span class="sxs-lookup"><span data-stu-id="63a7e-139">Alias options.</span></span> <span data-ttu-id="63a7e-140">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-140">This key is optional.</span></span> <span data-ttu-id="63a7e-141">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="63a7e-141">The default value is None.</span></span> <span data-ttu-id="63a7e-142">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="63a7e-142">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="63a7e-143">Пример: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="63a7e-143">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-144">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="63a7e-144">-AssembliesToLoad</span></span>

<span data-ttu-id="63a7e-145">Указывает сборки, которые необходимо загрузить в сеансы, использующие файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-145">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-146">-Author</span><span class="sxs-lookup"><span data-stu-id="63a7e-146">-Author</span></span>

<span data-ttu-id="63a7e-147">Указывает пользователя, создавшего файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-147">Specifies the user that created the role capability file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-148">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="63a7e-148">-CompanyName</span></span>

<span data-ttu-id="63a7e-149">Идентифицирует компанию, которая создала файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-149">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="63a7e-150">Значение по умолчанию — Unknown.</span><span class="sxs-lookup"><span data-stu-id="63a7e-150">The default value is Unknown.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-151">-Copyright</span><span class="sxs-lookup"><span data-stu-id="63a7e-151">-Copyright</span></span>

<span data-ttu-id="63a7e-152">Указывает авторские права на файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-152">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="63a7e-153">Если опустить этот параметр, `New-PSRoleCapabilityFile` создает заявление об авторских правах с помощью значения параметра **Author** .</span><span class="sxs-lookup"><span data-stu-id="63a7e-153">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-154">-Description</span><span class="sxs-lookup"><span data-stu-id="63a7e-154">-Description</span></span>

<span data-ttu-id="63a7e-155">Задает описание для файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-155">Specifies a description for the role capability file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-156">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="63a7e-156">-EnvironmentVariables</span></span>

<span data-ttu-id="63a7e-157">Указывает переменные среды для сеансов, которые предоставляют этот файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-157">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="63a7e-158">Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.</span><span class="sxs-lookup"><span data-stu-id="63a7e-158">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="63a7e-159">Пример: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="63a7e-159">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-160">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="63a7e-160">-FormatsToProcess</span></span>

<span data-ttu-id="63a7e-161">Указывает файлы форматирования (. ps1xml), которые выполняются в сеансах, использующих файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="63a7e-161">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-162">Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.</span><span class="sxs-lookup"><span data-stu-id="63a7e-162">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-163">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="63a7e-163">-FunctionDefinitions</span></span>

<span data-ttu-id="63a7e-164">Добавляет указанные функции к сеансам, которые предоставляют возможность роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-164">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="63a7e-165">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="63a7e-165">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="63a7e-166">Название</span><span class="sxs-lookup"><span data-stu-id="63a7e-166">Name.</span></span> <span data-ttu-id="63a7e-167">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="63a7e-167">Name of the function.</span></span> <span data-ttu-id="63a7e-168">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-168">This key is required.</span></span>
- <span data-ttu-id="63a7e-169">ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="63a7e-169">ScriptBlock.</span></span> <span data-ttu-id="63a7e-170">Тело функции.</span><span class="sxs-lookup"><span data-stu-id="63a7e-170">Function body.</span></span> <span data-ttu-id="63a7e-171">Введите блок сценария.</span><span class="sxs-lookup"><span data-stu-id="63a7e-171">Enter a script block.</span></span> <span data-ttu-id="63a7e-172">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-172">This key is required.</span></span>
- <span data-ttu-id="63a7e-173">Параметры.</span><span class="sxs-lookup"><span data-stu-id="63a7e-173">Options.</span></span> <span data-ttu-id="63a7e-174">Параметры функции.</span><span class="sxs-lookup"><span data-stu-id="63a7e-174">Function options.</span></span> <span data-ttu-id="63a7e-175">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-175">This key is optional.</span></span> <span data-ttu-id="63a7e-176">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="63a7e-176">The default value is None.</span></span> <span data-ttu-id="63a7e-177">Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".</span><span class="sxs-lookup"><span data-stu-id="63a7e-177">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="63a7e-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="63a7e-178">For example:</span></span>

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-179">-Guid</span><span class="sxs-lookup"><span data-stu-id="63a7e-179">-Guid</span></span>

<span data-ttu-id="63a7e-180">Указывает уникальный идентификатор для файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-180">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="63a7e-181">Если опустить этот параметр, `New-PSRoleCapabilityFile` создает идентификатор GUID для файла.</span><span class="sxs-lookup"><span data-stu-id="63a7e-181">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="63a7e-182">Чтобы создать новый GUID в PowerShell, введите `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="63a7e-182">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-183">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="63a7e-183">-ModulesToImport</span></span>

<span data-ttu-id="63a7e-184">Указывает модули, которые автоматически импортируются в сеансы, использующие файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-184">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-185">По умолчанию все команды в списке модулей видимы.</span><span class="sxs-lookup"><span data-stu-id="63a7e-185">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="63a7e-186">При использовании с **VisibleCmdlets** или **VisibleFunctions** команды, видимые из указанных модулей, могут быть ограничены.</span><span class="sxs-lookup"><span data-stu-id="63a7e-186">When used with **VisibleCmdlets** or **VisibleFunctions** , the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="63a7e-187">Каждый модуль, используемый в значении этого параметра, может быть представлен строкой или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="63a7e-187">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="63a7e-188">Строка модуля состоит только из имени модуля.</span><span class="sxs-lookup"><span data-stu-id="63a7e-188">A module string consists only of the name of the module.</span></span> <span data-ttu-id="63a7e-189">Хэш-таблица модуля может включать разделы **ModuleName** , **ModuleVersion** и **GUID**.</span><span class="sxs-lookup"><span data-stu-id="63a7e-189">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="63a7e-190">Обязателен только раздел **ModuleName**.</span><span class="sxs-lookup"><span data-stu-id="63a7e-190">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="63a7e-191">Например, следующее значение состоит из строки и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="63a7e-191">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="63a7e-192">Допустимо любое сочетание строк и хэш-таблиц в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="63a7e-192">Any combination of strings and hash tables, in any order, is valid.</span></span>

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-193">-Path</span><span class="sxs-lookup"><span data-stu-id="63a7e-193">-Path</span></span>

<span data-ttu-id="63a7e-194">Указывает путь и имя файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-194">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="63a7e-195">Файл должен иметь `.psrc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="63a7e-195">The file must have a `.psrc` filename extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-196">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="63a7e-196">-ScriptsToProcess</span></span>

<span data-ttu-id="63a7e-197">Указывает скрипты, добавляемые в сеансы, в которых используется файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="63a7e-197">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-198">Введите путь и имена файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="63a7e-198">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="63a7e-199">Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="63a7e-199">The value of this parameter must be a full or absolute path of the script file names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-200">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="63a7e-200">-TypesToProcess</span></span>

<span data-ttu-id="63a7e-201">Указывает файлы типов (. ps1xml) для добавления в сеансы, в которых используется файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="63a7e-201">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-202">Введите имена файлов.</span><span class="sxs-lookup"><span data-stu-id="63a7e-202">Enter the type filenames.</span></span> <span data-ttu-id="63a7e-203">Значение этого параметра должно быть полным или абсолютным путем к типу filename.</span><span class="sxs-lookup"><span data-stu-id="63a7e-203">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-204">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="63a7e-204">-VariableDefinitions</span></span>

<span data-ttu-id="63a7e-205">Указывает переменные для добавления в сеансы, в которых используется файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="63a7e-205">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="63a7e-206">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="63a7e-206">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="63a7e-207">Название</span><span class="sxs-lookup"><span data-stu-id="63a7e-207">Name.</span></span> <span data-ttu-id="63a7e-208">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="63a7e-208">Name of the variable.</span></span> <span data-ttu-id="63a7e-209">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-209">This key is required.</span></span>
- <span data-ttu-id="63a7e-210">Значение.</span><span class="sxs-lookup"><span data-stu-id="63a7e-210">Value.</span></span> <span data-ttu-id="63a7e-211">Значение переменной.</span><span class="sxs-lookup"><span data-stu-id="63a7e-211">Variable value.</span></span> <span data-ttu-id="63a7e-212">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-212">This key is required.</span></span>
- <span data-ttu-id="63a7e-213">Параметры.</span><span class="sxs-lookup"><span data-stu-id="63a7e-213">Options.</span></span> <span data-ttu-id="63a7e-214">Параметры переменных.</span><span class="sxs-lookup"><span data-stu-id="63a7e-214">Variable options.</span></span> <span data-ttu-id="63a7e-215">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="63a7e-215">This key is optional.</span></span> <span data-ttu-id="63a7e-216">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="63a7e-216">The default value is None.</span></span> <span data-ttu-id="63a7e-217">Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".</span><span class="sxs-lookup"><span data-stu-id="63a7e-217">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="63a7e-218">Пример: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="63a7e-218">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-219">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="63a7e-219">-VisibleAliases</span></span>

<span data-ttu-id="63a7e-220">Ограничивает псевдонимы в сеансе псевдонимами, указанными в значении этого параметра, а также любыми псевдонимами, определенными в параметре **алиасдефинитион** .</span><span class="sxs-lookup"><span data-stu-id="63a7e-220">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="63a7e-221">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="63a7e-221">Wildcard characters are supported.</span></span>
<span data-ttu-id="63a7e-222">По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="63a7e-222">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="63a7e-223">Например, чтобы ограничить доступные псевдонимы GM и GCM, используйте следующий синтаксис: `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="63a7e-223">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="63a7e-224">Если любой **видимый** параметр включен в файл возможностей роли, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-224">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63a7e-225">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="63a7e-225">-VisibleCmdlets</span></span>

<span data-ttu-id="63a7e-226">Ограничивает командлеты в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="63a7e-226">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="63a7e-227">Поддерживаются подстановочные знаки и полные имена модулей.</span><span class="sxs-lookup"><span data-stu-id="63a7e-227">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="63a7e-228">По умолчанию все командлеты, экспортируемые модулями в сеансе, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="63a7e-228">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="63a7e-229">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="63a7e-229">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="63a7e-230">Если ни один из модулей в **ModulesToImport** не предоставляет командлет, `New-PSRoleCapabilityFile` пытается загрузить соответствующий модуль.</span><span class="sxs-lookup"><span data-stu-id="63a7e-230">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="63a7e-231">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-231">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63a7e-232">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="63a7e-232">-VisibleExternalCommands</span></span>

<span data-ttu-id="63a7e-233">Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="63a7e-233">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="63a7e-234">По умолчанию в этом сеансе нет видимых внешних команд.</span><span class="sxs-lookup"><span data-stu-id="63a7e-234">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="63a7e-235">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-235">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a7e-236">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="63a7e-236">-VisibleFunctions</span></span>

<span data-ttu-id="63a7e-237">Ограничивает функции в сеансе значениями, указанными в значении этого параметра, а также всеми функциями, определенными в параметре **функтиондефинитионс** .</span><span class="sxs-lookup"><span data-stu-id="63a7e-237">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="63a7e-238">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="63a7e-238">Wildcard characters are supported.</span></span>

<span data-ttu-id="63a7e-239">По умолчанию все функции, экспортируемые модулями в сеансе, видимы в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="63a7e-239">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="63a7e-240">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="63a7e-240">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="63a7e-241">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-241">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63a7e-242">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="63a7e-242">-VisibleProviders</span></span>

<span data-ttu-id="63a7e-243">Ограничивает поставщиков PowerShell в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="63a7e-243">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="63a7e-244">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="63a7e-244">Wildcard characters are supported.</span></span>

<span data-ttu-id="63a7e-245">По умолчанию все поставщики, экспортированные модулем в сеансе, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="63a7e-245">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="63a7e-246">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="63a7e-246">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="63a7e-247">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="63a7e-247">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63a7e-248">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="63a7e-248">CommonParameters</span></span>

<span data-ttu-id="63a7e-249">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="63a7e-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="63a7e-250">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="63a7e-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="63a7e-251">Входные данные</span><span class="sxs-lookup"><span data-stu-id="63a7e-251">INPUTS</span></span>

## <span data-ttu-id="63a7e-252">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="63a7e-252">OUTPUTS</span></span>

## <span data-ttu-id="63a7e-253">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="63a7e-253">NOTES</span></span>

## <span data-ttu-id="63a7e-254">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="63a7e-254">RELATED LINKS</span></span>

[<span data-ttu-id="63a7e-255">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="63a7e-255">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="63a7e-256">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="63a7e-256">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)

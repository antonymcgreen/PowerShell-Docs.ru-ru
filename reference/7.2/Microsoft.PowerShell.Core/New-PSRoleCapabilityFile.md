---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 3ef54618e065a5fca3d52415897b3042d6ba4c65
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599412"
---
# <span data-ttu-id="b27e9-102">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="b27e9-102">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="b27e9-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b27e9-103">SYNOPSIS</span></span>
<span data-ttu-id="b27e9-104">Создает файл, который определяет набор возможностей, предоставляемых через конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-104">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="b27e9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b27e9-105">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="b27e9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b27e9-106">DESCRIPTION</span></span>

<span data-ttu-id="b27e9-107">`New-PSRoleCapabilityFile`Командлет создает файл, который определяет набор возможностей пользователя, которые могут быть предоставлены через файлы конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-107">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="b27e9-108">Это включает определение того, какие командлеты, функции и скрипты доступны пользователям.</span><span class="sxs-lookup"><span data-stu-id="b27e9-108">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="b27e9-109">Файл возможностей — это текстовый файл, доступный для чтения и содержащий хэш-таблицу свойств и значений конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-109">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="b27e9-110">Файл имеет расширение pSrc и может использоваться более чем в одной конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-110">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="b27e9-111">Все параметры `New-PSRoleCapabilityFile` являются необязательными, за исключением параметра **path** , который указывает путь к файлу для файла.</span><span class="sxs-lookup"><span data-stu-id="b27e9-111">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="b27e9-112">Если параметр не включен при выполнении командлета, соответствующий ключ в файле конфигурации сеанса заносится в комментарий, за исключением тех случаев, где указано в описании параметра.</span><span class="sxs-lookup"><span data-stu-id="b27e9-112">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="b27e9-113">Например, если не включить параметр **ассемблиестолоад** , то этот раздел файла конфигурации сеанса будет добавлен в комментарий.</span><span class="sxs-lookup"><span data-stu-id="b27e9-113">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="b27e9-114">Чтобы использовать файл возможностей роли в конфигурации сеанса, сначала поместите файл во вложенную папку **RoleCapabilities** допустимой папки модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b27e9-114">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="b27e9-115">Затем сослаться на файл по имени в поле **RoleDefinitions** в файле конфигурации сеанса PowerShell (. pssc).</span><span class="sxs-lookup"><span data-stu-id="b27e9-115">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="b27e9-116">Этот командлет появился в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b27e9-116">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="b27e9-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="b27e9-117">EXAMPLES</span></span>

### <span data-ttu-id="b27e9-118">Пример 1. Создание пустого файла возможностей роли</span><span class="sxs-lookup"><span data-stu-id="b27e9-118">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="b27e9-119">В этом примере создается новый файл возможностей роли, который использует значения по умолчанию (пустые).</span><span class="sxs-lookup"><span data-stu-id="b27e9-119">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="b27e9-120">Затем файл можно изменить в текстовом редакторе для изменения этих параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b27e9-120">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="b27e9-121">Пример 2. Создание файла возможностей роли, позволяющего пользователям перезапускать службы и любой компьютер VDI</span><span class="sxs-lookup"><span data-stu-id="b27e9-121">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="b27e9-122">В этом примере создается пример файла возможностей роли, который позволяет пользователям перезапускать службы и компьютеры, соответствующие определенному шаблону имени.</span><span class="sxs-lookup"><span data-stu-id="b27e9-122">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="b27e9-123">Фильтрация имен определяется путем присвоения параметру **ValidatePattern** регулярного выражения `VDI\d+` .</span><span class="sxs-lookup"><span data-stu-id="b27e9-123">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

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

## <span data-ttu-id="b27e9-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b27e9-124">PARAMETERS</span></span>

### <span data-ttu-id="b27e9-125">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="b27e9-125">-AliasDefinitions</span></span>

<span data-ttu-id="b27e9-126">Добавляет указанные псевдонимы в сеансы, которые используют файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-126">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-127">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="b27e9-127">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="b27e9-128">Название</span><span class="sxs-lookup"><span data-stu-id="b27e9-128">Name.</span></span> <span data-ttu-id="b27e9-129">Имя псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b27e9-129">Name of the alias.</span></span> <span data-ttu-id="b27e9-130">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-130">This key is required.</span></span>
- <span data-ttu-id="b27e9-131">Значение.</span><span class="sxs-lookup"><span data-stu-id="b27e9-131">Value.</span></span> <span data-ttu-id="b27e9-132">Команда, которая представляет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b27e9-132">The command that the alias represents.</span></span> <span data-ttu-id="b27e9-133">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-133">This key is required.</span></span>
- <span data-ttu-id="b27e9-134">Описание.</span><span class="sxs-lookup"><span data-stu-id="b27e9-134">Description.</span></span> <span data-ttu-id="b27e9-135">Текстовая строка с описанием псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b27e9-135">A text string that describes the alias.</span></span> <span data-ttu-id="b27e9-136">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-136">This key is optional.</span></span>
- <span data-ttu-id="b27e9-137">Параметры.</span><span class="sxs-lookup"><span data-stu-id="b27e9-137">Options.</span></span> <span data-ttu-id="b27e9-138">Параметры псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b27e9-138">Alias options.</span></span> <span data-ttu-id="b27e9-139">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-139">This key is optional.</span></span> <span data-ttu-id="b27e9-140">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="b27e9-140">The default value is None.</span></span> <span data-ttu-id="b27e9-141">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="b27e9-141">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="b27e9-142">Пример: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="b27e9-142">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

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

### <span data-ttu-id="b27e9-143">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="b27e9-143">-AssembliesToLoad</span></span>

<span data-ttu-id="b27e9-144">Указывает сборки, которые необходимо загрузить в сеансы, использующие файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-144">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

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

### <span data-ttu-id="b27e9-145">-Author</span><span class="sxs-lookup"><span data-stu-id="b27e9-145">-Author</span></span>

<span data-ttu-id="b27e9-146">Указывает пользователя, создавшего файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-146">Specifies the user that created the role capability file.</span></span>

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

### <span data-ttu-id="b27e9-147">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="b27e9-147">-CompanyName</span></span>

<span data-ttu-id="b27e9-148">Идентифицирует компанию, которая создала файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-148">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="b27e9-149">Значение по умолчанию — Unknown.</span><span class="sxs-lookup"><span data-stu-id="b27e9-149">The default value is Unknown.</span></span>

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

### <span data-ttu-id="b27e9-150">-Copyright</span><span class="sxs-lookup"><span data-stu-id="b27e9-150">-Copyright</span></span>

<span data-ttu-id="b27e9-151">Указывает авторские права на файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-151">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="b27e9-152">Если опустить этот параметр, `New-PSRoleCapabilityFile` создает заявление об авторских правах с помощью значения параметра **Author** .</span><span class="sxs-lookup"><span data-stu-id="b27e9-152">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="b27e9-153">-Description</span><span class="sxs-lookup"><span data-stu-id="b27e9-153">-Description</span></span>

<span data-ttu-id="b27e9-154">Задает описание для файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-154">Specifies a description for the role capability file.</span></span>

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

### <span data-ttu-id="b27e9-155">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="b27e9-155">-EnvironmentVariables</span></span>

<span data-ttu-id="b27e9-156">Указывает переменные среды для сеансов, которые предоставляют этот файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-156">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="b27e9-157">Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.</span><span class="sxs-lookup"><span data-stu-id="b27e9-157">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="b27e9-158">Пример: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="b27e9-158">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

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

### <span data-ttu-id="b27e9-159">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="b27e9-159">-FormatsToProcess</span></span>

<span data-ttu-id="b27e9-160">Указывает файлы форматирования (. ps1xml), которые выполняются в сеансах, использующих файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="b27e9-160">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-161">Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.</span><span class="sxs-lookup"><span data-stu-id="b27e9-161">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="b27e9-162">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="b27e9-162">-FunctionDefinitions</span></span>

<span data-ttu-id="b27e9-163">Добавляет указанные функции к сеансам, которые предоставляют возможность роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-163">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="b27e9-164">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="b27e9-164">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="b27e9-165">Название</span><span class="sxs-lookup"><span data-stu-id="b27e9-165">Name.</span></span> <span data-ttu-id="b27e9-166">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="b27e9-166">Name of the function.</span></span> <span data-ttu-id="b27e9-167">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-167">This key is required.</span></span>
- <span data-ttu-id="b27e9-168">ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="b27e9-168">ScriptBlock.</span></span> <span data-ttu-id="b27e9-169">Тело функции.</span><span class="sxs-lookup"><span data-stu-id="b27e9-169">Function body.</span></span> <span data-ttu-id="b27e9-170">Введите блок сценария.</span><span class="sxs-lookup"><span data-stu-id="b27e9-170">Enter a script block.</span></span> <span data-ttu-id="b27e9-171">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-171">This key is required.</span></span>
- <span data-ttu-id="b27e9-172">Параметры.</span><span class="sxs-lookup"><span data-stu-id="b27e9-172">Options.</span></span> <span data-ttu-id="b27e9-173">Параметры функции.</span><span class="sxs-lookup"><span data-stu-id="b27e9-173">Function options.</span></span> <span data-ttu-id="b27e9-174">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-174">This key is optional.</span></span> <span data-ttu-id="b27e9-175">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="b27e9-175">The default value is None.</span></span> <span data-ttu-id="b27e9-176">Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".</span><span class="sxs-lookup"><span data-stu-id="b27e9-176">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="b27e9-177">Пример:</span><span class="sxs-lookup"><span data-stu-id="b27e9-177">For example:</span></span>

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

### <span data-ttu-id="b27e9-178">-Guid</span><span class="sxs-lookup"><span data-stu-id="b27e9-178">-Guid</span></span>

<span data-ttu-id="b27e9-179">Указывает уникальный идентификатор для файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-179">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="b27e9-180">Если опустить этот параметр, `New-PSRoleCapabilityFile` создает идентификатор GUID для файла.</span><span class="sxs-lookup"><span data-stu-id="b27e9-180">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="b27e9-181">Чтобы создать новый GUID в PowerShell, введите `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="b27e9-181">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

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

### <span data-ttu-id="b27e9-182">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="b27e9-182">-ModulesToImport</span></span>

<span data-ttu-id="b27e9-183">Указывает модули, которые автоматически импортируются в сеансы, использующие файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-183">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-184">По умолчанию все команды в списке модулей видимы.</span><span class="sxs-lookup"><span data-stu-id="b27e9-184">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="b27e9-185">При использовании с **VisibleCmdlets** или **VisibleFunctions** команды, видимые из указанных модулей, могут быть ограничены.</span><span class="sxs-lookup"><span data-stu-id="b27e9-185">When used with **VisibleCmdlets** or **VisibleFunctions**, the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="b27e9-186">Каждый модуль, используемый в значении этого параметра, может быть представлен строкой или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b27e9-186">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="b27e9-187">Строка модуля состоит только из имени модуля.</span><span class="sxs-lookup"><span data-stu-id="b27e9-187">A module string consists only of the name of the module.</span></span> <span data-ttu-id="b27e9-188">Хэш-таблица модуля может включать разделы **ModuleName**, **ModuleVersion** и **GUID**.</span><span class="sxs-lookup"><span data-stu-id="b27e9-188">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="b27e9-189">Обязателен только раздел **ModuleName**.</span><span class="sxs-lookup"><span data-stu-id="b27e9-189">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="b27e9-190">Например, следующее значение состоит из строки и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="b27e9-190">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="b27e9-191">Допустимо любое сочетание строк и хэш-таблиц в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="b27e9-191">Any combination of strings and hash tables, in any order, is valid.</span></span>

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

### <span data-ttu-id="b27e9-192">-Path</span><span class="sxs-lookup"><span data-stu-id="b27e9-192">-Path</span></span>

<span data-ttu-id="b27e9-193">Указывает путь и имя файла возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-193">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="b27e9-194">Файл должен иметь `.psrc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="b27e9-194">The file must have a `.psrc` filename extension.</span></span>

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

### <span data-ttu-id="b27e9-195">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="b27e9-195">-ScriptsToProcess</span></span>

<span data-ttu-id="b27e9-196">Указывает скрипты, добавляемые в сеансы, в которых используется файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="b27e9-196">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-197">Введите путь и имена файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="b27e9-197">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="b27e9-198">Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="b27e9-198">The value of this parameter must be a full or absolute path of the script file names.</span></span>

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

### <span data-ttu-id="b27e9-199">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="b27e9-199">-TypesToProcess</span></span>

<span data-ttu-id="b27e9-200">Указывает файлы типов (. ps1xml) для добавления в сеансы, в которых используется файл возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="b27e9-200">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-201">Введите имена файлов.</span><span class="sxs-lookup"><span data-stu-id="b27e9-201">Enter the type filenames.</span></span> <span data-ttu-id="b27e9-202">Значение этого параметра должно быть полным или абсолютным путем к типу filename.</span><span class="sxs-lookup"><span data-stu-id="b27e9-202">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

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

### <span data-ttu-id="b27e9-203">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="b27e9-203">-VariableDefinitions</span></span>

<span data-ttu-id="b27e9-204">Указывает переменные для добавления в сеансы, в которых используется файл возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="b27e9-204">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="b27e9-205">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="b27e9-205">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="b27e9-206">Название</span><span class="sxs-lookup"><span data-stu-id="b27e9-206">Name.</span></span> <span data-ttu-id="b27e9-207">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="b27e9-207">Name of the variable.</span></span> <span data-ttu-id="b27e9-208">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-208">This key is required.</span></span>
- <span data-ttu-id="b27e9-209">Значение.</span><span class="sxs-lookup"><span data-stu-id="b27e9-209">Value.</span></span> <span data-ttu-id="b27e9-210">Значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b27e9-210">Variable value.</span></span> <span data-ttu-id="b27e9-211">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-211">This key is required.</span></span>
- <span data-ttu-id="b27e9-212">Параметры.</span><span class="sxs-lookup"><span data-stu-id="b27e9-212">Options.</span></span> <span data-ttu-id="b27e9-213">Параметры переменных.</span><span class="sxs-lookup"><span data-stu-id="b27e9-213">Variable options.</span></span> <span data-ttu-id="b27e9-214">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="b27e9-214">This key is optional.</span></span> <span data-ttu-id="b27e9-215">По умолчанию используется None.</span><span class="sxs-lookup"><span data-stu-id="b27e9-215">The default value is None.</span></span> <span data-ttu-id="b27e9-216">Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".</span><span class="sxs-lookup"><span data-stu-id="b27e9-216">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="b27e9-217">Пример: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="b27e9-217">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

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

### <span data-ttu-id="b27e9-218">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="b27e9-218">-VisibleAliases</span></span>

<span data-ttu-id="b27e9-219">Ограничивает псевдонимы в сеансе псевдонимами, указанными в значении этого параметра, а также любыми псевдонимами, определенными в параметре **алиасдефинитион** .</span><span class="sxs-lookup"><span data-stu-id="b27e9-219">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="b27e9-220">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b27e9-220">Wildcard characters are supported.</span></span>
<span data-ttu-id="b27e9-221">По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b27e9-221">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="b27e9-222">Например, чтобы ограничить доступные псевдонимы GM и GCM, используйте следующий синтаксис: `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="b27e9-222">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="b27e9-223">Если любой **видимый** параметр включен в файл возможностей роли, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-223">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="b27e9-224">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="b27e9-224">-VisibleCmdlets</span></span>

<span data-ttu-id="b27e9-225">Ограничивает командлеты в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b27e9-225">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="b27e9-226">Поддерживаются подстановочные знаки и полные имена модулей.</span><span class="sxs-lookup"><span data-stu-id="b27e9-226">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="b27e9-227">По умолчанию все командлеты, экспортируемые модулями в сеансе, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b27e9-227">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="b27e9-228">Используйте параметры **SessionType** и **ModulesToImport**, чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b27e9-228">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="b27e9-229">Если ни один из модулей в **ModulesToImport** не предоставляет командлет, `New-PSRoleCapabilityFile` пытается загрузить соответствующий модуль.</span><span class="sxs-lookup"><span data-stu-id="b27e9-229">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="b27e9-230">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-230">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="b27e9-231">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="b27e9-231">-VisibleExternalCommands</span></span>

<span data-ttu-id="b27e9-232">Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b27e9-232">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="b27e9-233">По умолчанию в этом сеансе нет видимых внешних команд.</span><span class="sxs-lookup"><span data-stu-id="b27e9-233">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="b27e9-234">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-234">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="b27e9-235">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="b27e9-235">-VisibleFunctions</span></span>

<span data-ttu-id="b27e9-236">Ограничивает функции в сеансе значениями, указанными в значении этого параметра, а также всеми функциями, определенными в параметре **функтиондефинитионс** .</span><span class="sxs-lookup"><span data-stu-id="b27e9-236">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="b27e9-237">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b27e9-237">Wildcard characters are supported.</span></span>

<span data-ttu-id="b27e9-238">По умолчанию все функции, экспортируемые модулями в сеансе, видимы в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="b27e9-238">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="b27e9-239">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b27e9-239">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="b27e9-240">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-240">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="b27e9-241">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="b27e9-241">-VisibleProviders</span></span>

<span data-ttu-id="b27e9-242">Ограничивает поставщиков PowerShell в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b27e9-242">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="b27e9-243">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b27e9-243">Wildcard characters are supported.</span></span>

<span data-ttu-id="b27e9-244">По умолчанию все поставщики, экспортированные модулем в сеансе, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b27e9-244">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="b27e9-245">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b27e9-245">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="b27e9-246">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b27e9-246">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="b27e9-247">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b27e9-247">CommonParameters</span></span>

<span data-ttu-id="b27e9-248">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b27e9-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b27e9-249">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b27e9-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b27e9-250">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b27e9-250">INPUTS</span></span>

## <span data-ttu-id="b27e9-251">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b27e9-251">OUTPUTS</span></span>

## <span data-ttu-id="b27e9-252">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b27e9-252">NOTES</span></span>

## <span data-ttu-id="b27e9-253">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b27e9-253">RELATED LINKS</span></span>

[<span data-ttu-id="b27e9-254">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="b27e9-254">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="b27e9-255">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="b27e9-255">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)


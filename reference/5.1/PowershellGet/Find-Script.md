---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 21b8dc249c93ae68ad3e43f998ede5dfe7a82766
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227265"
---
# <span data-ttu-id="e6c44-103">Find-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-103">Find-Script</span></span>

## <span data-ttu-id="e6c44-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e6c44-104">SYNOPSIS</span></span>
<span data-ttu-id="e6c44-105">Поиск скрипта.</span><span class="sxs-lookup"><span data-stu-id="e6c44-105">Finds a script.</span></span>

## <span data-ttu-id="e6c44-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6c44-106">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="e6c44-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6c44-107">DESCRIPTION</span></span>

<span data-ttu-id="e6c44-108">Командлет **Find-Script** находит указанный скрипт в зарегистрированных репозиториях.</span><span class="sxs-lookup"><span data-stu-id="e6c44-108">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="e6c44-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="e6c44-109">EXAMPLES</span></span>

### <span data-ttu-id="e6c44-110">Пример 1. Поиск всех доступных скриптов</span><span class="sxs-lookup"><span data-stu-id="e6c44-110">Example 1: Find all available scripts</span></span>

```
PS C:\> Find-Script
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
2.5        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
2.5        Fabrikam-ServerScript               Script     LocalRepo1           Description for the Fabrikam-ServerScript script
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        Script-WithDependencies2            Script     LocalRepo1           Description for the Script-WithDependencies2 script
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
2.1        Test-Script1                        Script     LocalRepo1           Test-Script1 Script example
2.0        Test-Script2                        Script     LocalRepo1           Test-Script2 Script example
1.0        TestRunbook                         Script     LocalRepo1           Contoso Script example
```

<span data-ttu-id="e6c44-111">Эта команда находит все доступные скрипты.</span><span class="sxs-lookup"><span data-stu-id="e6c44-111">This command finds all available scripts.</span></span>

### <span data-ttu-id="e6c44-112">Пример 2. Поиск скрипта по имени</span><span class="sxs-lookup"><span data-stu-id="e6c44-112">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="e6c44-113">Эта команда находит сценарий с именем Start-Вфконтососервер.</span><span class="sxs-lookup"><span data-stu-id="e6c44-113">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="e6c44-114">Пример 3. Поиск скрипта по имени, требуемой версии и из указанного репозитория</span><span class="sxs-lookup"><span data-stu-id="e6c44-114">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="e6c44-115">Эта команда находит скрипт по имени и требуемой версии в репозитории LocalRepo01.</span><span class="sxs-lookup"><span data-stu-id="e6c44-115">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="e6c44-116">Пример 4. Поиск скрипта и форматирование выходных данных в виде списка</span><span class="sxs-lookup"><span data-stu-id="e6c44-116">Example 4: Find a script and format the output as a list</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo1" | Format-List * -Force
Name                       : Required-Script2
Version                    : 2.0
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/14/2015 2:37:01 PM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {, Tag1, Tag2, Tag-Required-Script2-2.0...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : C:\MyLocalRepo
Repository                 : LocalRepo01
PackageManagementProvider  : NuGet
```

<span data-ttu-id="e6c44-117">Эта команда находит Required-Script2 в репозитории LocalRepo1, а затем передает полученный объект **PSRepositoryItemInfo** в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="e6c44-117">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="e6c44-118">Пример 5. Поиск скрипта в указанном диапазоне версий</span><span class="sxs-lookup"><span data-stu-id="e6c44-118">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="e6c44-119">Эта команда находит все версии RequiredScript2 между версиями 2,1 и 2,5 в репозитории LocalRepo1.</span><span class="sxs-lookup"><span data-stu-id="e6c44-119">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="e6c44-120">Пример 6. Поиск всех версий сценария</span><span class="sxs-lookup"><span data-stu-id="e6c44-120">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="e6c44-121">Эта команда находит все версии Required-Script02.</span><span class="sxs-lookup"><span data-stu-id="e6c44-121">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="e6c44-122">Пример 7. Поиск скрипта и его зависимостей</span><span class="sxs-lookup"><span data-stu-id="e6c44-122">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="e6c44-123">Эта команда находит скрипт и его зависимости.</span><span class="sxs-lookup"><span data-stu-id="e6c44-123">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="e6c44-124">Пример 8. Поиск скриптов с указанным тегом</span><span class="sxs-lookup"><span data-stu-id="e6c44-124">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="e6c44-125">Эта команда находит скрипты с тегом Tag1 в репозитории LocalRepo1.</span><span class="sxs-lookup"><span data-stu-id="e6c44-125">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="e6c44-126">Пример 9. Поиск скриптов с указанным именем команды</span><span class="sxs-lookup"><span data-stu-id="e6c44-126">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="e6c44-127">Эта команда находит скрипт, содержащий указанное имя команды.</span><span class="sxs-lookup"><span data-stu-id="e6c44-127">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="e6c44-128">Пример 10. Поиск сценариев с рабочими процессами</span><span class="sxs-lookup"><span data-stu-id="e6c44-128">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="e6c44-129">Эта команда находит скрипты рабочего процесса в репозитории LocalRepo1.</span><span class="sxs-lookup"><span data-stu-id="e6c44-129">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="e6c44-130">Пример 11. Поиск сценариев с использованием подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="e6c44-130">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="e6c44-131">Эта команда использует подстановочный знак (\*) для поиска скриптов, начинающихся с обязательного скрипта.</span><span class="sxs-lookup"><span data-stu-id="e6c44-131">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="e6c44-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6c44-132">PARAMETERS</span></span>

### <span data-ttu-id="e6c44-133">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="e6c44-133">-AllowPrerelease</span></span>

<span data-ttu-id="e6c44-134">Включает в скрипты результатов, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="e6c44-134">Includes in the results scripts marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-135">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e6c44-135">-AllVersions</span></span>

<span data-ttu-id="e6c44-136">Указывает, что эта операция находит все версии скриптов.</span><span class="sxs-lookup"><span data-stu-id="e6c44-136">Indicates that this operation finds all script versions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-137">-Command</span><span class="sxs-lookup"><span data-stu-id="e6c44-137">-Command</span></span>

<span data-ttu-id="e6c44-138">Указывает массив команд для поиска в скриптах.</span><span class="sxs-lookup"><span data-stu-id="e6c44-138">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="e6c44-139">Команда может быть функцией или рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="e6c44-139">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="e6c44-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="e6c44-140">-Credential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="e6c44-141">-Filter</span></span>

<span data-ttu-id="e6c44-142">Находит скрипты на основе синтаксиса поиска, зависящего от поставщика PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="e6c44-142">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="e6c44-143">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="e6c44-143">-IncludeDependencies</span></span>

<span data-ttu-id="e6c44-144">Указывает, что эта операция получает все скрипты, зависящие от скрипта, указанного в параметре *Name* .</span><span class="sxs-lookup"><span data-stu-id="e6c44-144">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-145">— Включает</span><span class="sxs-lookup"><span data-stu-id="e6c44-145">-Includes</span></span>

<span data-ttu-id="e6c44-146">Указывает тип получаемого скрипта.</span><span class="sxs-lookup"><span data-stu-id="e6c44-146">Specifies type of script to get.</span></span>
<span data-ttu-id="e6c44-147">Допустимые значения для этого параметра: функция, Рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="e6c44-147">The acceptable values for this parameter are: Function, Workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Function, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e6c44-148">-MaximumVersion</span></span>

<span data-ttu-id="e6c44-149">Указывает максимальную или самую новую версию скрипта для поиска.</span><span class="sxs-lookup"><span data-stu-id="e6c44-149">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="e6c44-150">Параметры *MaximumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e6c44-150">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e6c44-151">-MinimumVersion</span></span>

<span data-ttu-id="e6c44-152">Указывает минимальную версию скрипта для поиска.</span><span class="sxs-lookup"><span data-stu-id="e6c44-152">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="e6c44-153">Параметры *MinimumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e6c44-153">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-154">-Name</span><span class="sxs-lookup"><span data-stu-id="e6c44-154">-Name</span></span>

<span data-ttu-id="e6c44-155">Задает массив имен скриптов для поиска.</span><span class="sxs-lookup"><span data-stu-id="e6c44-155">Specifies an array of names of scripts to find.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e6c44-156">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e6c44-156">-Proxy</span></span>

<span data-ttu-id="e6c44-157">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="e6c44-157">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-158">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e6c44-158">-ProxyCredential</span></span>

<span data-ttu-id="e6c44-159">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="e6c44-159">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-160">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="e6c44-160">-Repository</span></span>

<span data-ttu-id="e6c44-161">Указывает понятное имя репозитория, зарегистрированного с помощью команды Register-PSRepository.</span><span class="sxs-lookup"><span data-stu-id="e6c44-161">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="e6c44-162">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e6c44-162">-RequiredVersion</span></span>

<span data-ttu-id="e6c44-163">Указывает точный номер версии скрипта для поиска.</span><span class="sxs-lookup"><span data-stu-id="e6c44-163">Specifies the exact version number of the script to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e6c44-164">-Tag</span><span class="sxs-lookup"><span data-stu-id="e6c44-164">-Tag</span></span>

<span data-ttu-id="e6c44-165">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="e6c44-165">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="e6c44-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e6c44-166">CommonParameters</span></span>

<span data-ttu-id="e6c44-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6c44-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6c44-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6c44-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6c44-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e6c44-169">INPUTS</span></span>

## <span data-ttu-id="e6c44-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e6c44-170">OUTPUTS</span></span>

### <span data-ttu-id="e6c44-171">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="e6c44-171">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="e6c44-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e6c44-172">NOTES</span></span>

## <span data-ttu-id="e6c44-173">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e6c44-173">RELATED LINKS</span></span>

[<span data-ttu-id="e6c44-174">Install-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-174">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="e6c44-175">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-175">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="e6c44-176">Save-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-176">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="e6c44-177">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-177">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="e6c44-178">Update-Script</span><span class="sxs-lookup"><span data-stu-id="e6c44-178">Update-Script</span></span>](Update-Script.md)

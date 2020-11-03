---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/install-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Script
ms.openlocfilehash: ecae1ba3a3aea6628817bab2f09fc23e23162f03
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228657"
---
# <span data-ttu-id="eee50-103">Install-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-103">Install-Script</span></span>

## <span data-ttu-id="eee50-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eee50-104">SYNOPSIS</span></span>
<span data-ttu-id="eee50-105">Устанавливает скрипт.</span><span class="sxs-lookup"><span data-stu-id="eee50-105">Installs a script.</span></span>

## <span data-ttu-id="eee50-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eee50-106">SYNTAX</span></span>

### <span data-ttu-id="eee50-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="eee50-107">NameParameterSet (Default)</span></span>

```
Install-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Scope <String>] [-NoPathUpdate]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="eee50-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="eee50-108">InputObject</span></span>

```
Install-Script [-InputObject] <PSObject[]> [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="eee50-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eee50-109">DESCRIPTION</span></span>

<span data-ttu-id="eee50-110">`Install-Script`Командлет получает полезные данные скрипта из репозитория, проверяет, является ли полезная нагрузка допустимым сценарием PowerShell, и копирует файл скрипта в указанное расположение установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-110">The `Install-Script` cmdlet acquires a script payload from a repository, verifies that the payload is a valid PowerShell script, and copies the script file to a specified installation location.</span></span>

<span data-ttu-id="eee50-111">Репозитории по умолчанию `Install-Script` можно настроить с помощью `Register-PSRepository` `Set-PSRepository` `Unregister-PSRepository` командлетов,, и `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="eee50-111">The default repositories `Install-Script` operates against are configurable through the `Register-PSRepository`, `Set-PSRepository`, `Unregister-PSRepository`, and `Get-PSRepository` cmdlets.</span></span> <span data-ttu-id="eee50-112">При работе с несколькими репозиториями `Install-Script` устанавливает первый скрипт, соответствующий указанным условиям поиска ( **имя** , **MinimumVersion** или **MaximumVersion** ), из первого репозитория без каких-либо ошибок.</span><span class="sxs-lookup"><span data-stu-id="eee50-112">When operating against multiple repositories, `Install-Script` installs the first script that matches the specified search criteria ( **Name** , **MinimumVersion** , or **MaximumVersion** ) from the first repository without any error.</span></span>

## <span data-ttu-id="eee50-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="eee50-113">EXAMPLES</span></span>

### <span data-ttu-id="eee50-114">Пример 1. Поиск и установка сценария</span><span class="sxs-lookup"><span data-stu-id="eee50-114">Example 1: Find a script and install it</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2"
Version    Name                           Type       Repository           Description
-------    ----                           ----       ----------           -----------
2.5        Required-Script2               Script     local1               Description for the Required-Script2 script

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2" | Install-Script
PS C:\> Get-Command -Name "Required-Script2"
CommandType     Name                      Version    Source
-----------     ----                      -------    ------
ExternalScript  Required-Script2.ps1      2.0       C:\Users\pattif\Documents\WindowsPowerShell\Scripts\Required-Script2.ps1

PS C:\> Get-InstalledScript -Name "Required-Script2"
Version    Name                  Type     Repository           Description
-------    ----                  ----     ----------           -----------
2.5        Required-Script2      Script   local1               Description for the Required-Script2 script

PS C:\> Get-InstalledScript -Name "Required-Script2" | Format-List *
Name                       : Required-Script2
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:39 AM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script2-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Users\pattif\Documents\WindowsPowerShell\Scripts
```

<span data-ttu-id="eee50-115">Первая команда находит сценарий с именем `Required-Script2` из репозитория local1 и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="eee50-115">The first command finds the script named `Required-Script2` from the Local1 repository and displays the results.</span></span>

<span data-ttu-id="eee50-116">Вторая команда находит `Required-Script2` скрипт, а затем использует оператор конвейера, чтобы передать его `Install-Script` командлету для его установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-116">The second command finds the `Required-Script2` script, and then uses the pipeline operator to pass it to the `Install-Script` cmdlet to install it.</span></span>

<span data-ttu-id="eee50-117">Третья команда использует `Get-Command` командлет для получения `Required-Script2` , а затем отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="eee50-117">The third command uses the `Get-Command` cmdlet to get `Required-Script2`, and then displays the results.</span></span>

<span data-ttu-id="eee50-118">Четвертая команда использует `Get-InstalledScript` командлет для получения `Required-Script2` и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="eee50-118">The fourth command uses the `Get-InstalledScript` cmdlet to get `Required-Script2` and display the results.</span></span>

<span data-ttu-id="eee50-119">Пятая команда получает `Required-Script2` и использует оператор конвейера для передачи его в `Format-List` командлет для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="eee50-119">The fifth command gets `Required-Script2` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="eee50-120">Пример 2. Установка скрипта с областью AllUsers</span><span class="sxs-lookup"><span data-stu-id="eee50-120">Example 2: Install a script with AllUsers scope</span></span>

```
PS C:\> Install-Script -Repository "Local1" -Name "Required-Script3" -Scope "AllUsers"
PS C:\> Get-InstalledScript -Name "Required-Script3"
Version    Name                  Type       Repository    Description
-------    ----                  ----       ----------    -----------
2.5        Required-Script3      Script     local1        Description for the Required-Script3 script

PS C:\> Get-InstalledScript -Name "Required-Script3" | Format-List *
Name                       : Required-Script3
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script3 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:45 AM
LicenseUri                 : http://required-script3.com/license
ProjectUri                 : http://required-script3.com/
IconUri                    : http://required-script3.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script3-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script3 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts
```

<span data-ttu-id="eee50-121">Первая команда устанавливает скрипт с именем `Required-Script3` и назначает область ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="eee50-121">The first command installs the script named `Required-Script3` and assigns it AllUsers scope.</span></span>

<span data-ttu-id="eee50-122">Вторая команда получает установленный скрипт `Required-Script3` и отображает сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="eee50-122">The second command gets the installed script `Required-Script3` and displays information about it.</span></span>

<span data-ttu-id="eee50-123">Третья команда получает `Required-Script3` и использует оператор конвейера для передачи его в `Format-List` командлет для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="eee50-123">The third command gets `Required-Script3` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="eee50-124">Пример 3. Установка скрипта и его зависимостей</span><span class="sxs-lookup"><span data-stu-id="eee50-124">Example 3: Install a script and its dependencies</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Script-WithDependencies2" -IncludeDependencies
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Script-WithDependencies2"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script

PS C:\> Get-InstalledModule
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script*"
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Required-Script*"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
```

<span data-ttu-id="eee50-125">Первая команда находит скрипт с именем `Script-WithDependencies2` и его зависимостями в репозитории local1 и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="eee50-125">The first command finds the script named `Script-WithDependencies2` and its dependencies in the Local1 repository and displays the results.</span></span>

<span data-ttu-id="eee50-126">Вторая команда устанавливает `Script-WithDependencies2` .</span><span class="sxs-lookup"><span data-stu-id="eee50-126">The second command installs `Script-WithDependencies2`.</span></span>

<span data-ttu-id="eee50-127">Третья команда использует `Get-InstalledScript` командлет Script для получения установленных скриптов и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="eee50-127">The third command uses the `Get-InstalledScript` script cmdlet to get installed scripts and display the results.</span></span>

<span data-ttu-id="eee50-128">Четвертая команда использует `Get-InstalledModule` командлет для получения установленных модулей и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="eee50-128">The fourth command uses the `Get-InstalledModule` cmdlet to get installed modules and display the results.</span></span>

<span data-ttu-id="eee50-129">Пятая команда использует командлет, `Find-Script` чтобы найти скрипты, имена которых начинаются с `Required-Script` и отображают результаты.</span><span class="sxs-lookup"><span data-stu-id="eee50-129">The fifth command uses the `Find-Script` cmdlet to find scripts where the name begins with `Required-Script` and display the results.</span></span>

<span data-ttu-id="eee50-130">Шестая команда устанавливает скрипты, имена которых начинаются с `Required-Script` в репозитории local1.</span><span class="sxs-lookup"><span data-stu-id="eee50-130">The sixth command installs the scripts where the name begins with `Required-Script` in the Local1 repository.</span></span>

<span data-ttu-id="eee50-131">Последняя команда получает установленные скрипты и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="eee50-131">The final command gets installed scripts and displays the results.</span></span>

## <span data-ttu-id="eee50-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eee50-132">PARAMETERS</span></span>

### <span data-ttu-id="eee50-133">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="eee50-133">-AcceptLicense</span></span>

<span data-ttu-id="eee50-134">Автоматически принять лицензионное соглашение во время установки, если оно требуется для модуля.</span><span class="sxs-lookup"><span data-stu-id="eee50-134">Automatically accept the license agreement during installation if the module requires it.</span></span>

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

### <span data-ttu-id="eee50-135">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="eee50-135">-AllowPrerelease</span></span>

<span data-ttu-id="eee50-136">Позволяет установить сценарий, помеченный как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="eee50-136">Allows you to install a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eee50-137">-Confirm</span></span>

<span data-ttu-id="eee50-138">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="eee50-138">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="eee50-139">-Credential</span></span>

<span data-ttu-id="eee50-140">Указывает учетную запись пользователя, имеющую права на установку скрипта для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="eee50-140">Specifies a user account that has rights to install a script for a specified package provider or source.</span></span>

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

### <span data-ttu-id="eee50-141">-Force</span><span class="sxs-lookup"><span data-stu-id="eee50-141">-Force</span></span>

<span data-ttu-id="eee50-142">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="eee50-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="eee50-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="eee50-143">-InputObject</span></span>

<span data-ttu-id="eee50-144">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="eee50-144">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="eee50-145">-MaximumVersion</span></span>

<span data-ttu-id="eee50-146">Указывает максимальную версию отдельных сценариев для установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-146">Specifies the maximum version of a single scripts to install.</span></span> <span data-ttu-id="eee50-147">Этот параметр нельзя добавить, если вы пытаетесь установить несколько скриптов.</span><span class="sxs-lookup"><span data-stu-id="eee50-147">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="eee50-148">Параметры **MaximumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="eee50-148">The **MaximumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="eee50-149">-MinimumVersion</span></span>

<span data-ttu-id="eee50-150">Указывает минимальную версию отдельного скрипта для установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-150">Specifies the minimum version of a single script to install.</span></span> <span data-ttu-id="eee50-151">Этот параметр нельзя добавить, если вы пытаетесь установить несколько скриптов.</span><span class="sxs-lookup"><span data-stu-id="eee50-151">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="eee50-152">Параметры **MinimumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="eee50-152">The **MinimumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-153">-Name</span><span class="sxs-lookup"><span data-stu-id="eee50-153">-Name</span></span>

<span data-ttu-id="eee50-154">Указывает массив имен скриптов для установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-154">Specifies an array of names of scripts to install.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-155">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="eee50-155">-NoPathUpdate</span></span>

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

### <span data-ttu-id="eee50-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="eee50-156">-PassThru</span></span>

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

### <span data-ttu-id="eee50-157">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="eee50-157">-Proxy</span></span>

<span data-ttu-id="eee50-158">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="eee50-158">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="eee50-159">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="eee50-159">-ProxyCredential</span></span>

<span data-ttu-id="eee50-160">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="eee50-160">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="eee50-161">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="eee50-161">-Repository</span></span>

<span data-ttu-id="eee50-162">Указывает понятное имя репозитория, зарегистрированного с помощью `Register-PSRepository` командлета.</span><span class="sxs-lookup"><span data-stu-id="eee50-162">Specifies the friendly name of a repository that has been registered with the `Register-PSRepository` cmdlet.</span></span> <span data-ttu-id="eee50-163">По умолчанию все зарегистрированные репозитории.</span><span class="sxs-lookup"><span data-stu-id="eee50-163">The default is all registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="eee50-164">-RequiredVersion</span></span>

<span data-ttu-id="eee50-165">Указывает точный номер версии скрипта для установки.</span><span class="sxs-lookup"><span data-stu-id="eee50-165">Specifies the exact version number of the script to install.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-166">-Scope</span><span class="sxs-lookup"><span data-stu-id="eee50-166">-Scope</span></span>

<span data-ttu-id="eee50-167">Задает область установки скрипта.</span><span class="sxs-lookup"><span data-stu-id="eee50-167">Specifies the installation scope of the script.</span></span>
<span data-ttu-id="eee50-168">Допустимые значения: AllUsers и CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="eee50-168">Valid values are: AllUsers and CurrentUser.</span></span>

<span data-ttu-id="eee50-169">Область AllUsers позволяет устанавливать модули в расположении, доступном для всех пользователей компьютера, то есть `$env:ProgramFiles\WindowsPowerShell\Scripts` .</span><span class="sxs-lookup"><span data-stu-id="eee50-169">The AllUsers scope lets modules be installed in a location that is accessible to all users of the computer, that is, `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span></span>

<span data-ttu-id="eee50-170">Область CurrentUser позволяет устанавливать модули только в `$home\Documents\WindowsPowerShell\Scripts` , чтобы модуль был доступен только текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="eee50-170">The CurrentUser scope lets modules be installed only to `$home\Documents\WindowsPowerShell\Scripts`, so that the module is available only to the current user.</span></span>

<span data-ttu-id="eee50-171">Если **область** не определена, значение по умолчанию будет задаваться на основе текущего сеанса:</span><span class="sxs-lookup"><span data-stu-id="eee50-171">When no **Scope** is defined, the default will be set based on the current session:</span></span>

- <span data-ttu-id="eee50-172">Для сеанса PowerShell с повышенными привилегиями по умолчанию для **области** используется значение ALLUSERS;</span><span class="sxs-lookup"><span data-stu-id="eee50-172">For an elevated PowerShell session, **Scope** defaults to AllUsers;</span></span>
- <span data-ttu-id="eee50-173">Для сеансов PowerShell без повышенных привилегий в [PowerShellGet версий 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) и выше используется **область** CurrentUser;</span><span class="sxs-lookup"><span data-stu-id="eee50-173">For non-elevated PowerShell sessions in [PowerShellGet versions 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) and above, **Scope** is CurrentUser;</span></span>
- <span data-ttu-id="eee50-174">Для сеансов PowerShell без повышенных привилегий в версиях PowerShellGet 1.6.7 и более ранних версий **область** не определена и `Install-Module` завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="eee50-174">For non-elevated PowerShell sessions in PowerShellGet versions 1.6.7 and earlier, **Scope** is undefined, and `Install-Module` fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eee50-175">-WhatIf</span></span>

<span data-ttu-id="eee50-176">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="eee50-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="eee50-177">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="eee50-177">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eee50-178">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="eee50-178">CommonParameters</span></span>

<span data-ttu-id="eee50-179">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eee50-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eee50-180">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eee50-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eee50-181">Входные данные</span><span class="sxs-lookup"><span data-stu-id="eee50-181">INPUTS</span></span>

### <span data-ttu-id="eee50-182">System.String[]</span><span class="sxs-lookup"><span data-stu-id="eee50-182">System.String[]</span></span>

### <span data-ttu-id="eee50-183">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="eee50-183">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="eee50-184">System.String</span><span class="sxs-lookup"><span data-stu-id="eee50-184">System.String</span></span>

### <span data-ttu-id="eee50-185">System.Uri</span><span class="sxs-lookup"><span data-stu-id="eee50-185">System.Uri</span></span>

### <span data-ttu-id="eee50-186">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="eee50-186">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="eee50-187">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="eee50-187">OUTPUTS</span></span>

### <span data-ttu-id="eee50-188">System.Object</span><span class="sxs-lookup"><span data-stu-id="eee50-188">System.Object</span></span>

## <span data-ttu-id="eee50-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="eee50-189">NOTES</span></span>

## <span data-ttu-id="eee50-190">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="eee50-190">RELATED LINKS</span></span>

[<span data-ttu-id="eee50-191">Find-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-191">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="eee50-192">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-192">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="eee50-193">Save-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-193">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="eee50-194">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-194">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="eee50-195">Update-Script</span><span class="sxs-lookup"><span data-stu-id="eee50-195">Update-Script</span></span>](Update-Script.md)

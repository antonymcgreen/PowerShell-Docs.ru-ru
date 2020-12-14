---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 25da03724603b0000c46ae2da69d63cdf2f36cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891689"
---
# <span data-ttu-id="2382f-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="2382f-103">Update-Script</span></span>

## <span data-ttu-id="2382f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2382f-104">SYNOPSIS</span></span>
<span data-ttu-id="2382f-105">Обновляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="2382f-105">Updates a script.</span></span>

## <span data-ttu-id="2382f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2382f-106">SYNTAX</span></span>

### <span data-ttu-id="2382f-107">Все</span><span class="sxs-lookup"><span data-stu-id="2382f-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2382f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2382f-108">DESCRIPTION</span></span>

<span data-ttu-id="2382f-109">`Update-Script`Командлет обновляет скрипт, установленный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2382f-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="2382f-110">Обновленный скрипт загружается из того же репозитория, что и установленная версия.</span><span class="sxs-lookup"><span data-stu-id="2382f-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="2382f-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="2382f-111">EXAMPLES</span></span>

### <span data-ttu-id="2382f-112">Пример 1. обновление указанного скрипта</span><span class="sxs-lookup"><span data-stu-id="2382f-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="2382f-113">В этом примере обновляется установленный скрипт и отображается обновленная версия.</span><span class="sxs-lookup"><span data-stu-id="2382f-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="2382f-114">`Update-Script` использует параметр **Name** , чтобы указать скрипт для обновления.</span><span class="sxs-lookup"><span data-stu-id="2382f-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="2382f-115">Параметр **RequiredVersion** указывает версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="2382f-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="2382f-116">`Get-InstalledScript` Отображает обновленную версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="2382f-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="2382f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2382f-117">PARAMETERS</span></span>

### <span data-ttu-id="2382f-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="2382f-118">-AcceptLicense</span></span>

<span data-ttu-id="2382f-119">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="2382f-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="2382f-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="2382f-120">-AllowPrerelease</span></span>

<span data-ttu-id="2382f-121">Позволяет обновить скрипт с помощью нового скрипта, помеченного как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="2382f-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="2382f-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2382f-122">-Confirm</span></span>

<span data-ttu-id="2382f-123">Запрашивает подтверждение перед запуском `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="2382f-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="2382f-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="2382f-124">-Credential</span></span>

<span data-ttu-id="2382f-125">Указывает учетную запись пользователя, имеющую разрешение на обновление скрипта.</span><span class="sxs-lookup"><span data-stu-id="2382f-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="2382f-126">-Force</span><span class="sxs-lookup"><span data-stu-id="2382f-126">-Force</span></span>

<span data-ttu-id="2382f-127">Принудительное `Update-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="2382f-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2382f-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2382f-128">-MaximumVersion</span></span>

<span data-ttu-id="2382f-129">Указывает максимальную или самую новую версию скрипта для обновления.</span><span class="sxs-lookup"><span data-stu-id="2382f-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="2382f-130">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="2382f-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="2382f-131">-Name</span><span class="sxs-lookup"><span data-stu-id="2382f-131">-Name</span></span>

<span data-ttu-id="2382f-132">Задает одно имя скрипта или массив имен скриптов для обновления.</span><span class="sxs-lookup"><span data-stu-id="2382f-132">Specifies one script name or an array of script names to update.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2382f-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2382f-133">-PassThru</span></span>

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

### <span data-ttu-id="2382f-134">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="2382f-134">-Proxy</span></span>

<span data-ttu-id="2382f-135">Указывает прокси-сервер для запроса, а не прямое подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="2382f-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="2382f-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2382f-136">-ProxyCredential</span></span>

<span data-ttu-id="2382f-137">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="2382f-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="2382f-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2382f-138">-RequiredVersion</span></span>

<span data-ttu-id="2382f-139">Указывает точный номер версии скрипта для обновления.</span><span class="sxs-lookup"><span data-stu-id="2382f-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="2382f-140">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="2382f-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="2382f-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2382f-141">-WhatIf</span></span>

<span data-ttu-id="2382f-142">Показывает, что произойдет при `Update-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="2382f-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="2382f-143">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2382f-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2382f-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2382f-144">CommonParameters</span></span>

<span data-ttu-id="2382f-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2382f-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2382f-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2382f-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2382f-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2382f-147">INPUTS</span></span>

### <span data-ttu-id="2382f-148">System.String[]</span><span class="sxs-lookup"><span data-stu-id="2382f-148">System.String[]</span></span>

### <span data-ttu-id="2382f-149">System.String</span><span class="sxs-lookup"><span data-stu-id="2382f-149">System.String</span></span>

### <span data-ttu-id="2382f-150">System.Uri</span><span class="sxs-lookup"><span data-stu-id="2382f-150">System.Uri</span></span>

### <span data-ttu-id="2382f-151">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="2382f-151">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="2382f-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2382f-152">OUTPUTS</span></span>

### <span data-ttu-id="2382f-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="2382f-153">System.Object</span></span>

## <span data-ttu-id="2382f-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2382f-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2382f-155">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="2382f-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2382f-156">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="2382f-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2382f-157">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="2382f-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2382f-158">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2382f-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="2382f-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2382f-159">RELATED LINKS</span></span>

[<span data-ttu-id="2382f-160">Find-Script</span><span class="sxs-lookup"><span data-stu-id="2382f-160">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="2382f-161">Install-Script</span><span class="sxs-lookup"><span data-stu-id="2382f-161">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="2382f-162">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="2382f-162">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="2382f-163">Save-Script</span><span class="sxs-lookup"><span data-stu-id="2382f-163">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="2382f-164">Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="2382f-164">Uninstall-Script</span></span>](Uninstall-Script.md)


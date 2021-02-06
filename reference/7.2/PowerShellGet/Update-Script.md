---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 0fa537e463464fe055ea14aeab05cbb3ac5d1012
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599992"
---
# <span data-ttu-id="ee5c9-102">Update-Script</span><span class="sxs-lookup"><span data-stu-id="ee5c9-102">Update-Script</span></span>

## <span data-ttu-id="ee5c9-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ee5c9-103">SYNOPSIS</span></span>
<span data-ttu-id="ee5c9-104">Обновляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-104">Updates a script.</span></span>

## <span data-ttu-id="ee5c9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ee5c9-105">SYNTAX</span></span>

### <span data-ttu-id="ee5c9-106">Все</span><span class="sxs-lookup"><span data-stu-id="ee5c9-106">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ee5c9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ee5c9-107">DESCRIPTION</span></span>

<span data-ttu-id="ee5c9-108">`Update-Script`Командлет обновляет скрипт, установленный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-108">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="ee5c9-109">Обновленный скрипт загружается из того же репозитория, что и установленная версия.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-109">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="ee5c9-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ee5c9-110">EXAMPLES</span></span>

### <span data-ttu-id="ee5c9-111">Пример 1. обновление указанного скрипта</span><span class="sxs-lookup"><span data-stu-id="ee5c9-111">Example 1: Update the specified script</span></span>

<span data-ttu-id="ee5c9-112">В этом примере обновляется установленный скрипт и отображается обновленная версия.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-112">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="ee5c9-113">`Update-Script` использует параметр **Name** , чтобы указать скрипт для обновления.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-113">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="ee5c9-114">Параметр **RequiredVersion** указывает версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-114">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="ee5c9-115">`Get-InstalledScript` Отображает обновленную версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-115">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="ee5c9-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ee5c9-116">PARAMETERS</span></span>

### <span data-ttu-id="ee5c9-117">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ee5c9-117">-AcceptLicense</span></span>

<span data-ttu-id="ee5c9-118">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-118">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="ee5c9-119">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="ee5c9-119">-AllowPrerelease</span></span>

<span data-ttu-id="ee5c9-120">Позволяет обновить скрипт с помощью нового скрипта, помеченного как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-120">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="ee5c9-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ee5c9-121">-Confirm</span></span>

<span data-ttu-id="ee5c9-122">Запрашивает подтверждение перед запуском `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="ee5c9-122">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="ee5c9-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="ee5c9-123">-Credential</span></span>

<span data-ttu-id="ee5c9-124">Указывает учетную запись пользователя, имеющую разрешение на обновление скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-124">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="ee5c9-125">-Force</span><span class="sxs-lookup"><span data-stu-id="ee5c9-125">-Force</span></span>

<span data-ttu-id="ee5c9-126">Принудительное `Update-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-126">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ee5c9-127">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ee5c9-127">-MaximumVersion</span></span>

<span data-ttu-id="ee5c9-128">Указывает максимальную или самую новую версию скрипта для обновления.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-128">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="ee5c9-129">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-129">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ee5c9-130">-Name</span><span class="sxs-lookup"><span data-stu-id="ee5c9-130">-Name</span></span>

<span data-ttu-id="ee5c9-131">Задает одно имя скрипта или массив имен скриптов для обновления.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-131">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="ee5c9-132">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ee5c9-132">-PassThru</span></span>

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

### <span data-ttu-id="ee5c9-133">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="ee5c9-133">-Proxy</span></span>

<span data-ttu-id="ee5c9-134">Указывает прокси-сервер для запроса, а не прямое подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-134">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="ee5c9-135">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ee5c9-135">-ProxyCredential</span></span>

<span data-ttu-id="ee5c9-136">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="ee5c9-136">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="ee5c9-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ee5c9-137">-RequiredVersion</span></span>

<span data-ttu-id="ee5c9-138">Указывает точный номер версии скрипта для обновления.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-138">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="ee5c9-139">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-139">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="ee5c9-140">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ee5c9-140">-WhatIf</span></span>

<span data-ttu-id="ee5c9-141">Показывает, что произойдет при `Update-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-141">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="ee5c9-142">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-142">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ee5c9-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ee5c9-143">CommonParameters</span></span>

<span data-ttu-id="ee5c9-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ee5c9-145">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ee5c9-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ee5c9-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ee5c9-146">INPUTS</span></span>

### <span data-ttu-id="ee5c9-147">System.String[]</span><span class="sxs-lookup"><span data-stu-id="ee5c9-147">System.String[]</span></span>

### <span data-ttu-id="ee5c9-148">System.String</span><span class="sxs-lookup"><span data-stu-id="ee5c9-148">System.String</span></span>

### <span data-ttu-id="ee5c9-149">System.Uri</span><span class="sxs-lookup"><span data-stu-id="ee5c9-149">System.Uri</span></span>

### <span data-ttu-id="ee5c9-150">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="ee5c9-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="ee5c9-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ee5c9-151">OUTPUTS</span></span>

### <span data-ttu-id="ee5c9-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="ee5c9-152">System.Object</span></span>

## <span data-ttu-id="ee5c9-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ee5c9-153">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee5c9-154">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-154">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="ee5c9-155">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-155">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="ee5c9-156">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee5c9-156">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="ee5c9-157">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee5c9-157">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="ee5c9-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ee5c9-158">RELATED LINKS</span></span>

[<span data-ttu-id="ee5c9-159">Find-Script</span><span class="sxs-lookup"><span data-stu-id="ee5c9-159">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="ee5c9-160">Install-Script</span><span class="sxs-lookup"><span data-stu-id="ee5c9-160">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="ee5c9-161">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="ee5c9-161">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="ee5c9-162">Save-Script</span><span class="sxs-lookup"><span data-stu-id="ee5c9-162">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="ee5c9-163">Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="ee5c9-163">Uninstall-Script</span></span>](Uninstall-Script.md)

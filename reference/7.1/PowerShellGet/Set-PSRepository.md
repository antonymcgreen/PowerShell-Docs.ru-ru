---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 74eb0b105674c4e007cfade8d8a16799b5c366f2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892095"
---
# <span data-ttu-id="ebbe6-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ebbe6-103">Set-PSRepository</span></span>

## <span data-ttu-id="ebbe6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ebbe6-104">SYNOPSIS</span></span>
<span data-ttu-id="ebbe6-105">Задает значения для зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="ebbe6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ebbe6-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="ebbe6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ebbe6-107">DESCRIPTION</span></span>

<span data-ttu-id="ebbe6-108">`Set-PSRepository`Командлет задает значения для зарегистрированного репозитория модуля.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="ebbe6-109">Параметры постоянны для текущего пользователя и применяются ко всем версиям PowerShell, установленным для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="ebbe6-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ebbe6-110">EXAMPLES</span></span>

### <span data-ttu-id="ebbe6-111">Пример 1. Задание политики установки для репозитория</span><span class="sxs-lookup"><span data-stu-id="ebbe6-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="ebbe6-112">Эта команда задает **доверенную** политику установки для репозитория **минтерналсаурце** , чтобы не выводить запрос перед установкой модулей из этого источника.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted**, so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="ebbe6-113">Пример 2. Задание расположений источника и публикации для репозитория</span><span class="sxs-lookup"><span data-stu-id="ebbe6-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="ebbe6-114">Эта команда задает исходное расположение и расположение публикации для **минтерналсаурце** указанным URI.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="ebbe6-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ebbe6-115">PARAMETERS</span></span>

### <span data-ttu-id="ebbe6-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="ebbe6-116">-Credential</span></span>

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

### <span data-ttu-id="ebbe6-117">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="ebbe6-117">-InstallationPolicy</span></span>

<span data-ttu-id="ebbe6-118">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-118">Specifies the installation policy.</span></span> <span data-ttu-id="ebbe6-119">Допустимые значения: **доверие**, **без доверия**.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-119">Valid values are: **Trusted**, **Untrusted**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-120">-Name</span><span class="sxs-lookup"><span data-stu-id="ebbe6-120">-Name</span></span>

<span data-ttu-id="ebbe6-121">Указывает имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-121">Specifies the name of the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-122">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="ebbe6-122">-PackageManagementProvider</span></span>

<span data-ttu-id="ebbe6-123">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="ebbe6-124">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="ebbe6-124">-Proxy</span></span>

<span data-ttu-id="ebbe6-125">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="ebbe6-126">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ebbe6-126">-ProxyCredential</span></span>

<span data-ttu-id="ebbe6-127">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="ebbe6-128">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="ebbe6-128">-PublishLocation</span></span>

<span data-ttu-id="ebbe6-129">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="ebbe6-130">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="ebbe6-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-131">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="ebbe6-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="ebbe6-132">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-132">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-133">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="ebbe6-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="ebbe6-134">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-134">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-135">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="ebbe6-135">-SourceLocation</span></span>

<span data-ttu-id="ebbe6-136">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="ebbe6-137">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="ebbe6-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebbe6-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ebbe6-138">CommonParameters</span></span>

<span data-ttu-id="ebbe6-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ebbe6-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ebbe6-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ebbe6-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ebbe6-141">INPUTS</span></span>

### <span data-ttu-id="ebbe6-142">System.String</span><span class="sxs-lookup"><span data-stu-id="ebbe6-142">System.String</span></span>

### <span data-ttu-id="ebbe6-143">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="ebbe6-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="ebbe6-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="ebbe6-144">System.Uri</span></span>

## <span data-ttu-id="ebbe6-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ebbe6-145">OUTPUTS</span></span>

### <span data-ttu-id="ebbe6-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="ebbe6-146">System.Object</span></span>

## <span data-ttu-id="ebbe6-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ebbe6-147">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebbe6-148">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-148">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="ebbe6-149">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-149">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="ebbe6-150">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="ebbe6-150">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="ebbe6-151">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebbe6-151">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="ebbe6-152">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ebbe6-152">RELATED LINKS</span></span>

[<span data-ttu-id="ebbe6-153">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ebbe6-153">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="ebbe6-154">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ebbe6-154">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="ebbe6-155">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ebbe6-155">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

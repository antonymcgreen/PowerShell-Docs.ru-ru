---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: d6f3901ba389ff910dcc808d2e4296032617052c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600472"
---
# <span data-ttu-id="66fea-102">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="66fea-102">Set-PSRepository</span></span>

## <span data-ttu-id="66fea-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="66fea-103">SYNOPSIS</span></span>
<span data-ttu-id="66fea-104">Задает значения для зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="66fea-104">Sets values for a registered repository.</span></span>

## <span data-ttu-id="66fea-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66fea-105">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="66fea-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66fea-106">DESCRIPTION</span></span>

<span data-ttu-id="66fea-107">`Set-PSRepository`Командлет задает значения для зарегистрированного репозитория модуля.</span><span class="sxs-lookup"><span data-stu-id="66fea-107">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="66fea-108">Параметры постоянны для текущего пользователя и применяются ко всем версиям PowerShell, установленным для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="66fea-108">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="66fea-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="66fea-109">EXAMPLES</span></span>

### <span data-ttu-id="66fea-110">Пример 1. Задание политики установки для репозитория</span><span class="sxs-lookup"><span data-stu-id="66fea-110">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="66fea-111">Эта команда задает **доверенную** политику установки для репозитория **минтерналсаурце** , чтобы не выводить запрос перед установкой модулей из этого источника.</span><span class="sxs-lookup"><span data-stu-id="66fea-111">This command sets the installation policy for the **myInternalSource** repository to **Trusted**, so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="66fea-112">Пример 2. Задание расположений источника и публикации для репозитория</span><span class="sxs-lookup"><span data-stu-id="66fea-112">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="66fea-113">Эта команда задает исходное расположение и расположение публикации для **минтерналсаурце** указанным URI.</span><span class="sxs-lookup"><span data-stu-id="66fea-113">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="66fea-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66fea-114">PARAMETERS</span></span>

### <span data-ttu-id="66fea-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="66fea-115">-Credential</span></span>

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

### <span data-ttu-id="66fea-116">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="66fea-116">-InstallationPolicy</span></span>

<span data-ttu-id="66fea-117">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="66fea-117">Specifies the installation policy.</span></span> <span data-ttu-id="66fea-118">Допустимые значения: **доверие**, **без доверия**.</span><span class="sxs-lookup"><span data-stu-id="66fea-118">Valid values are: **Trusted**, **Untrusted**.</span></span>

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

### <span data-ttu-id="66fea-119">-Name</span><span class="sxs-lookup"><span data-stu-id="66fea-119">-Name</span></span>

<span data-ttu-id="66fea-120">Указывает имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="66fea-120">Specifies the name of the repository.</span></span>

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

### <span data-ttu-id="66fea-121">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="66fea-121">-PackageManagementProvider</span></span>

<span data-ttu-id="66fea-122">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="66fea-122">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="66fea-123">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="66fea-123">-Proxy</span></span>

<span data-ttu-id="66fea-124">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="66fea-124">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="66fea-125">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="66fea-125">-ProxyCredential</span></span>

<span data-ttu-id="66fea-126">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="66fea-126">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="66fea-127">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="66fea-127">-PublishLocation</span></span>

<span data-ttu-id="66fea-128">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="66fea-128">Specifies the URI of the publish location.</span></span> <span data-ttu-id="66fea-129">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="66fea-129">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="66fea-130">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="66fea-130">-ScriptPublishLocation</span></span>

<span data-ttu-id="66fea-131">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="66fea-131">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="66fea-132">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="66fea-132">-ScriptSourceLocation</span></span>

<span data-ttu-id="66fea-133">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="66fea-133">Specifies the script source location.</span></span>

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

### <span data-ttu-id="66fea-134">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="66fea-134">-SourceLocation</span></span>

<span data-ttu-id="66fea-135">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="66fea-135">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="66fea-136">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="66fea-136">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="66fea-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="66fea-137">CommonParameters</span></span>

<span data-ttu-id="66fea-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66fea-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66fea-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="66fea-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66fea-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="66fea-140">INPUTS</span></span>

### <span data-ttu-id="66fea-141">System.String</span><span class="sxs-lookup"><span data-stu-id="66fea-141">System.String</span></span>

### <span data-ttu-id="66fea-142">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="66fea-142">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="66fea-143">System.Uri</span><span class="sxs-lookup"><span data-stu-id="66fea-143">System.Uri</span></span>

## <span data-ttu-id="66fea-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="66fea-144">OUTPUTS</span></span>

### <span data-ttu-id="66fea-145">System.Object</span><span class="sxs-lookup"><span data-stu-id="66fea-145">System.Object</span></span>

## <span data-ttu-id="66fea-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="66fea-146">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66fea-147">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="66fea-147">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="66fea-148">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="66fea-148">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="66fea-149">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="66fea-149">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="66fea-150">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66fea-150">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="66fea-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="66fea-151">RELATED LINKS</span></span>

[<span data-ttu-id="66fea-152">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="66fea-152">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="66fea-153">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="66fea-153">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="66fea-154">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="66fea-154">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

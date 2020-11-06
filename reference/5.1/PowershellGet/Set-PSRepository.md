---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 0734bda0a3462e39f799570c853cffa3e267c5db
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228273"
---
# <span data-ttu-id="4788b-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4788b-103">Set-PSRepository</span></span>

## <span data-ttu-id="4788b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4788b-104">SYNOPSIS</span></span>
<span data-ttu-id="4788b-105">Задает значения для зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="4788b-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="4788b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4788b-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="4788b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4788b-107">DESCRIPTION</span></span>

<span data-ttu-id="4788b-108">`Set-PSRepository`Командлет задает значения для зарегистрированного репозитория модуля.</span><span class="sxs-lookup"><span data-stu-id="4788b-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="4788b-109">Параметры постоянны для текущего пользователя и применяются ко всем версиям PowerShell, установленным для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4788b-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="4788b-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="4788b-110">EXAMPLES</span></span>

### <span data-ttu-id="4788b-111">Пример 1. Задание политики установки для репозитория</span><span class="sxs-lookup"><span data-stu-id="4788b-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="4788b-112">Эта команда задает **доверенную** политику установки для репозитория **минтерналсаурце** , чтобы не выводить запрос перед установкой модулей из этого источника.</span><span class="sxs-lookup"><span data-stu-id="4788b-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="4788b-113">Пример 2. Задание расположений источника и публикации для репозитория</span><span class="sxs-lookup"><span data-stu-id="4788b-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="4788b-114">Эта команда задает исходное расположение и расположение публикации для **минтерналсаурце** указанным URI.</span><span class="sxs-lookup"><span data-stu-id="4788b-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="4788b-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4788b-115">PARAMETERS</span></span>

### <span data-ttu-id="4788b-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="4788b-116">-Credential</span></span>

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

### <span data-ttu-id="4788b-117">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="4788b-117">-InstallationPolicy</span></span>

<span data-ttu-id="4788b-118">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="4788b-118">Specifies the installation policy.</span></span> <span data-ttu-id="4788b-119">Допустимые значения: **доверие** , **без доверия** .</span><span class="sxs-lookup"><span data-stu-id="4788b-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

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

### <span data-ttu-id="4788b-120">-Name</span><span class="sxs-lookup"><span data-stu-id="4788b-120">-Name</span></span>

<span data-ttu-id="4788b-121">Указывает имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="4788b-121">Specifies the name of the repository.</span></span>

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

### <span data-ttu-id="4788b-122">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="4788b-122">-PackageManagementProvider</span></span>

<span data-ttu-id="4788b-123">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="4788b-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="4788b-124">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="4788b-124">-Proxy</span></span>

<span data-ttu-id="4788b-125">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="4788b-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="4788b-126">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="4788b-126">-ProxyCredential</span></span>

<span data-ttu-id="4788b-127">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="4788b-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="4788b-128">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="4788b-128">-PublishLocation</span></span>

<span data-ttu-id="4788b-129">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="4788b-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="4788b-130">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="4788b-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="4788b-131">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="4788b-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="4788b-132">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="4788b-132">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="4788b-133">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="4788b-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="4788b-134">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="4788b-134">Specifies the script source location.</span></span>

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

### <span data-ttu-id="4788b-135">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="4788b-135">-SourceLocation</span></span>

<span data-ttu-id="4788b-136">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="4788b-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="4788b-137">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="4788b-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="4788b-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4788b-138">CommonParameters</span></span>

<span data-ttu-id="4788b-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4788b-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4788b-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4788b-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4788b-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4788b-141">INPUTS</span></span>

### <span data-ttu-id="4788b-142">System.String</span><span class="sxs-lookup"><span data-stu-id="4788b-142">System.String</span></span>

### <span data-ttu-id="4788b-143">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="4788b-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="4788b-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="4788b-144">System.Uri</span></span>

## <span data-ttu-id="4788b-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4788b-145">OUTPUTS</span></span>

### <span data-ttu-id="4788b-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="4788b-146">System.Object</span></span>

## <span data-ttu-id="4788b-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4788b-147">NOTES</span></span>

## <span data-ttu-id="4788b-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4788b-148">RELATED LINKS</span></span>

[<span data-ttu-id="4788b-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4788b-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="4788b-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4788b-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="4788b-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4788b-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
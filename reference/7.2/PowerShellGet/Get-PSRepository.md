---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: 66f840d99b107da22b6771e6327ab68d33a1b368
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599812"
---
# <span data-ttu-id="1eb80-102">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="1eb80-102">Get-PSRepository</span></span>

## <span data-ttu-id="1eb80-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1eb80-103">SYNOPSIS</span></span>
<span data-ttu-id="1eb80-104">Возвращает репозитории PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1eb80-104">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="1eb80-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1eb80-105">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1eb80-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1eb80-106">DESCRIPTION</span></span>

<span data-ttu-id="1eb80-107">Командлет **Get-PSRepository** получает репозитории модуля PowerShell, которые зарегистрированы для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb80-107">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="1eb80-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="1eb80-108">EXAMPLES</span></span>

### <span data-ttu-id="1eb80-109">Пример 1. получение всех репозиториев модулей</span><span class="sxs-lookup"><span data-stu-id="1eb80-109">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="1eb80-110">Эта команда возвращает все репозитории модулей, зарегистрированные для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb80-110">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="1eb80-111">Пример 2. получение репозиториев модулей по имени</span><span class="sxs-lookup"><span data-stu-id="1eb80-111">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="1eb80-112">Эта команда возвращает все репозитории модулей, в именах которых содержится NuGet.</span><span class="sxs-lookup"><span data-stu-id="1eb80-112">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="1eb80-113">Пример 3. получение репозитория модуля и форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="1eb80-113">Example 3: Get a module repository and format the output</span></span>

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

<span data-ttu-id="1eb80-114">Эта команда получает репозиторий с именем Local01 и использует оператор конвейера для передачи этого объекта в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="1eb80-114">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="1eb80-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1eb80-115">PARAMETERS</span></span>

### <span data-ttu-id="1eb80-116">-Name</span><span class="sxs-lookup"><span data-stu-id="1eb80-116">-Name</span></span>

<span data-ttu-id="1eb80-117">Указывает имена репозиториев для получения.</span><span class="sxs-lookup"><span data-stu-id="1eb80-117">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="1eb80-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1eb80-118">CommonParameters</span></span>

<span data-ttu-id="1eb80-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1eb80-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1eb80-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1eb80-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1eb80-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1eb80-121">INPUTS</span></span>

### <span data-ttu-id="1eb80-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1eb80-122">System.String[]</span></span>

## <span data-ttu-id="1eb80-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1eb80-123">OUTPUTS</span></span>

### <span data-ttu-id="1eb80-124">System.Object</span><span class="sxs-lookup"><span data-stu-id="1eb80-124">System.Object</span></span>

## <span data-ttu-id="1eb80-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1eb80-125">NOTES</span></span>

## <span data-ttu-id="1eb80-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1eb80-126">RELATED LINKS</span></span>

[<span data-ttu-id="1eb80-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="1eb80-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="1eb80-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="1eb80-128">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="1eb80-129">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="1eb80-129">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)


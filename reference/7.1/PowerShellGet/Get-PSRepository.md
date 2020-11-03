---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: e24bb117b4d4277adc359c130789cf7ee03b1fd6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228513"
---
# <span data-ttu-id="f4ed2-103">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4ed2-103">Get-PSRepository</span></span>

## <span data-ttu-id="f4ed2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f4ed2-104">SYNOPSIS</span></span>
<span data-ttu-id="f4ed2-105">Возвращает репозитории PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-105">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="f4ed2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4ed2-106">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f4ed2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4ed2-107">DESCRIPTION</span></span>

<span data-ttu-id="f4ed2-108">Командлет **Get-PSRepository** получает репозитории модуля PowerShell, которые зарегистрированы для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-108">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="f4ed2-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="f4ed2-109">EXAMPLES</span></span>

### <span data-ttu-id="f4ed2-110">Пример 1. получение всех репозиториев модулей</span><span class="sxs-lookup"><span data-stu-id="f4ed2-110">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="f4ed2-111">Эта команда возвращает все репозитории модулей, зарегистрированные для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-111">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="f4ed2-112">Пример 2. получение репозиториев модулей по имени</span><span class="sxs-lookup"><span data-stu-id="f4ed2-112">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="f4ed2-113">Эта команда возвращает все репозитории модулей, в именах которых содержится NuGet.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-113">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="f4ed2-114">Пример 3. получение репозитория модуля и форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="f4ed2-114">Example 3: Get a module repository and format the output</span></span>

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

<span data-ttu-id="f4ed2-115">Эта команда получает репозиторий с именем Local01 и использует оператор конвейера для передачи этого объекта в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-115">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="f4ed2-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4ed2-116">PARAMETERS</span></span>

### <span data-ttu-id="f4ed2-117">-Name</span><span class="sxs-lookup"><span data-stu-id="f4ed2-117">-Name</span></span>

<span data-ttu-id="f4ed2-118">Указывает имена репозиториев для получения.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-118">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="f4ed2-119">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f4ed2-119">CommonParameters</span></span>

<span data-ttu-id="f4ed2-120">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4ed2-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4ed2-121">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4ed2-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4ed2-122">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f4ed2-122">INPUTS</span></span>

### <span data-ttu-id="f4ed2-123">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f4ed2-123">System.String[]</span></span>

## <span data-ttu-id="f4ed2-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f4ed2-124">OUTPUTS</span></span>

### <span data-ttu-id="f4ed2-125">System.Object</span><span class="sxs-lookup"><span data-stu-id="f4ed2-125">System.Object</span></span>

## <span data-ttu-id="f4ed2-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f4ed2-126">NOTES</span></span>

## <span data-ttu-id="f4ed2-127">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f4ed2-127">RELATED LINKS</span></span>

[<span data-ttu-id="f4ed2-128">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4ed2-128">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="f4ed2-129">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4ed2-129">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="f4ed2-130">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f4ed2-130">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)


---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0d98d7bbb26d5a50542f0e125e912ea6333714c1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228254"
---
# <span data-ttu-id="f495b-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f495b-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="f495b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f495b-104">SYNOPSIS</span></span>
<span data-ttu-id="f495b-105">Отмена регистрации репозитория.</span><span class="sxs-lookup"><span data-stu-id="f495b-105">Unregisters a repository.</span></span>

## <span data-ttu-id="f495b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f495b-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f495b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f495b-107">DESCRIPTION</span></span>

<span data-ttu-id="f495b-108">`Unregister-PSRepository`Командлет отменяет регистрацию репозитория для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f495b-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="f495b-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="f495b-109">EXAMPLES</span></span>

### <span data-ttu-id="f495b-110">Пример 1. Отмена регистрации репозитория</span><span class="sxs-lookup"><span data-stu-id="f495b-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="f495b-111">В этом примере отменяется регистрация репозитория с именем Минужетсаурце.</span><span class="sxs-lookup"><span data-stu-id="f495b-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="f495b-112">Пример 2. Отмена регистрации всех репозиториев</span><span class="sxs-lookup"><span data-stu-id="f495b-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="f495b-113">В этом примере используется `Get-PSRepository` для получения всех зарегистрированных репозиториев и используется оператор конвейера, чтобы передать их для `Unregister-PSRepository` отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="f495b-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="f495b-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f495b-114">PARAMETERS</span></span>

### <span data-ttu-id="f495b-115">-Name</span><span class="sxs-lookup"><span data-stu-id="f495b-115">-Name</span></span>

<span data-ttu-id="f495b-116">Указывает массив имен удаляемых репозиториев.</span><span class="sxs-lookup"><span data-stu-id="f495b-116">Specifies an array of names of the repositories to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f495b-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f495b-117">CommonParameters</span></span>

<span data-ttu-id="f495b-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f495b-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f495b-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f495b-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f495b-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f495b-120">INPUTS</span></span>

### <span data-ttu-id="f495b-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f495b-121">System.String[]</span></span>

## <span data-ttu-id="f495b-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f495b-122">OUTPUTS</span></span>

### <span data-ttu-id="f495b-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="f495b-123">System.Object</span></span>

## <span data-ttu-id="f495b-124">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f495b-124">NOTES</span></span>

## <span data-ttu-id="f495b-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f495b-125">RELATED LINKS</span></span>

[<span data-ttu-id="f495b-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f495b-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="f495b-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f495b-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="f495b-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f495b-128">Set-PSRepository</span></span>](Set-PSRepository.md)
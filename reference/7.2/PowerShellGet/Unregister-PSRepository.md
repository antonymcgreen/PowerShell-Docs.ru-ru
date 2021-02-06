---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 908a43506bfbff964cfbdd8eea270b1fa42c3e77
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602275"
---
# <span data-ttu-id="fa722-102">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="fa722-102">Unregister-PSRepository</span></span>

## <span data-ttu-id="fa722-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fa722-103">SYNOPSIS</span></span>
<span data-ttu-id="fa722-104">Отмена регистрации репозитория.</span><span class="sxs-lookup"><span data-stu-id="fa722-104">Unregisters a repository.</span></span>

## <span data-ttu-id="fa722-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa722-105">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="fa722-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa722-106">DESCRIPTION</span></span>

<span data-ttu-id="fa722-107">`Unregister-PSRepository`Командлет отменяет регистрацию репозитория для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa722-107">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="fa722-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa722-108">EXAMPLES</span></span>

### <span data-ttu-id="fa722-109">Пример 1. Отмена регистрации репозитория</span><span class="sxs-lookup"><span data-stu-id="fa722-109">Example 1: Unregister a repository</span></span>

<span data-ttu-id="fa722-110">В этом примере отменяется регистрация репозитория с именем Минужетсаурце.</span><span class="sxs-lookup"><span data-stu-id="fa722-110">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="fa722-111">Пример 2. Отмена регистрации всех репозиториев</span><span class="sxs-lookup"><span data-stu-id="fa722-111">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="fa722-112">В этом примере используется `Get-PSRepository` для получения всех зарегистрированных репозиториев и используется оператор конвейера, чтобы передать их для `Unregister-PSRepository` отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="fa722-112">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="fa722-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa722-113">PARAMETERS</span></span>

### <span data-ttu-id="fa722-114">-Name</span><span class="sxs-lookup"><span data-stu-id="fa722-114">-Name</span></span>

<span data-ttu-id="fa722-115">Указывает массив имен удаляемых репозиториев.</span><span class="sxs-lookup"><span data-stu-id="fa722-115">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="fa722-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fa722-116">CommonParameters</span></span>

<span data-ttu-id="fa722-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fa722-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa722-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fa722-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa722-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fa722-119">INPUTS</span></span>

### <span data-ttu-id="fa722-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="fa722-120">System.String[]</span></span>

## <span data-ttu-id="fa722-121">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fa722-121">OUTPUTS</span></span>

### <span data-ttu-id="fa722-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="fa722-122">System.Object</span></span>

## <span data-ttu-id="fa722-123">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fa722-123">NOTES</span></span>

## <span data-ttu-id="fa722-124">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fa722-124">RELATED LINKS</span></span>

[<span data-ttu-id="fa722-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="fa722-125">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="fa722-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="fa722-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="fa722-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="fa722-127">Set-PSRepository</span></span>](Set-PSRepository.md)

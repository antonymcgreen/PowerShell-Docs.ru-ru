---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2d91c36c6fd6d2e1281fdadf95c3b83e27c36f60
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229526"
---
# <span data-ttu-id="0d21f-102">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0d21f-102">Get-ExperimentalFeature</span></span>

## <span data-ttu-id="0d21f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0d21f-103">SYNOPSIS</span></span>
<span data-ttu-id="0d21f-104">Получает экспериментальные функции.</span><span class="sxs-lookup"><span data-stu-id="0d21f-104">Gets experimental features.</span></span>

## <span data-ttu-id="0d21f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d21f-105">SYNTAX</span></span>

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0d21f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d21f-106">DESCRIPTION</span></span>

<span data-ttu-id="0d21f-107">`Get-ExperimentalFeature`Командлет возвращает все экспериментальные функции, обнаруженные PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d21f-107">The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell.</span></span>
<span data-ttu-id="0d21f-108">Экспериментальные функции могут поступать из модулей или механизма PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d21f-108">Experimental features can come from modules or the PowerShell engine.</span></span> <span data-ttu-id="0d21f-109">Экспериментальные функции позволяют пользователям безопасно тестировать новые функции и предоставлять отзывы (обычно через GitHub), прежде чем проект считается завершенным, и любые изменения могут стать критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="0d21f-109">Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.</span></span>

## <span data-ttu-id="0d21f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="0d21f-110">EXAMPLES</span></span>

### <span data-ttu-id="0d21f-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="0d21f-111">Example 1</span></span>

<span data-ttu-id="0d21f-112">Возвращает список зарегистрированных в настоящее время экспериментальных функций и их текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="0d21f-112">Gets the list of currently registered experimental features and their current state.</span></span>

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## <span data-ttu-id="0d21f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d21f-113">PARAMETERS</span></span>

### <span data-ttu-id="0d21f-114">-Name</span><span class="sxs-lookup"><span data-stu-id="0d21f-114">-Name</span></span>

<span data-ttu-id="0d21f-115">Имя или имена конкретных экспериментальных функций, которые нужно вернуть.</span><span class="sxs-lookup"><span data-stu-id="0d21f-115">Name or names of specific experimental features to return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0d21f-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0d21f-116">CommonParameters</span></span>

<span data-ttu-id="0d21f-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d21f-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d21f-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d21f-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d21f-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0d21f-119">INPUTS</span></span>

### <span data-ttu-id="0d21f-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0d21f-120">System.String[]</span></span>

<span data-ttu-id="0d21f-121">Имя или имена экспериментальных функций, которые нужно вернуть.</span><span class="sxs-lookup"><span data-stu-id="0d21f-121">Name or names of experimental features to return.</span></span>

## <span data-ttu-id="0d21f-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0d21f-122">OUTPUTS</span></span>

### <span data-ttu-id="0d21f-123">експерименталфеатуре</span><span class="sxs-lookup"><span data-stu-id="0d21f-123">ExperimentalFeature</span></span>

<span data-ttu-id="0d21f-124">Возвращает экземпляры, соответствующие запрошенным именам, или все экспериментальные функции, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="0d21f-124">Returns instances that match the requested names or all experimental features if no name is specified.</span></span>

## <span data-ttu-id="0d21f-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0d21f-125">RELATED LINKS</span></span>

[<span data-ttu-id="0d21f-126">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0d21f-126">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="0d21f-127">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0d21f-127">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)


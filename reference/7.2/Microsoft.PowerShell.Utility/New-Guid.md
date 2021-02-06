---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: df7f9000cf66cebce83e3146cd5c95a7d1a78bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605288"
---
# <span data-ttu-id="4a88d-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="4a88d-102">New-Guid</span></span>

## <span data-ttu-id="4a88d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4a88d-103">SYNOPSIS</span></span>
<span data-ttu-id="4a88d-104">Создает глобальный уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="4a88d-104">Creates a GUID.</span></span>

## <span data-ttu-id="4a88d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a88d-105">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="4a88d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4a88d-106">DESCRIPTION</span></span>

<span data-ttu-id="4a88d-107">Командлет **New-Guid** создает случайный идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="4a88d-107">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="4a88d-108">Если в скрипте требуется уникальный идентификатор, при необходимости можно создать идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="4a88d-108">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="4a88d-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="4a88d-109">EXAMPLES</span></span>

### <span data-ttu-id="4a88d-110">Пример 1. Создание идентификатора GUID</span><span class="sxs-lookup"><span data-stu-id="4a88d-110">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="4a88d-111">Эта команда создает случайный идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="4a88d-111">This command creates a random GUID.</span></span>
<span data-ttu-id="4a88d-112">Выходные данные этого командлета можно хранить в переменных, а затем использовать их в другом месте в скрипте.</span><span class="sxs-lookup"><span data-stu-id="4a88d-112">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="4a88d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a88d-113">PARAMETERS</span></span>

### <span data-ttu-id="4a88d-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4a88d-114">CommonParameters</span></span>

<span data-ttu-id="4a88d-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4a88d-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a88d-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4a88d-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a88d-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4a88d-117">INPUTS</span></span>

## <span data-ttu-id="4a88d-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4a88d-118">OUTPUTS</span></span>

### <span data-ttu-id="4a88d-119">System.Guid</span><span class="sxs-lookup"><span data-stu-id="4a88d-119">System.Guid</span></span>

<span data-ttu-id="4a88d-120">Этот командлет возвращает идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="4a88d-120">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="4a88d-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4a88d-121">NOTES</span></span>

## <span data-ttu-id="4a88d-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4a88d-122">RELATED LINKS</span></span>


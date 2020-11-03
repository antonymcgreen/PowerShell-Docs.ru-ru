---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 80d30b5c3b33c3e4f8125db3a158166a00f7e816
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209153"
---
# <span data-ttu-id="91e7f-103">New-Guid</span><span class="sxs-lookup"><span data-stu-id="91e7f-103">New-Guid</span></span>

## <span data-ttu-id="91e7f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="91e7f-104">SYNOPSIS</span></span>
<span data-ttu-id="91e7f-105">Создает глобальный уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="91e7f-105">Creates a GUID.</span></span>

## <span data-ttu-id="91e7f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91e7f-106">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="91e7f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91e7f-107">DESCRIPTION</span></span>

<span data-ttu-id="91e7f-108">Командлет **New-Guid** создает случайный идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="91e7f-108">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="91e7f-109">Если в скрипте требуется уникальный идентификатор, при необходимости можно создать идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="91e7f-109">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="91e7f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="91e7f-110">EXAMPLES</span></span>

### <span data-ttu-id="91e7f-111">Пример 1. Создание идентификатора GUID</span><span class="sxs-lookup"><span data-stu-id="91e7f-111">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="91e7f-112">Эта команда создает случайный идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="91e7f-112">This command creates a random GUID.</span></span>
<span data-ttu-id="91e7f-113">Выходные данные этого командлета можно хранить в переменных, а затем использовать их в другом месте в скрипте.</span><span class="sxs-lookup"><span data-stu-id="91e7f-113">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="91e7f-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91e7f-114">PARAMETERS</span></span>

### <span data-ttu-id="91e7f-115">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="91e7f-115">CommonParameters</span></span>

<span data-ttu-id="91e7f-116">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91e7f-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91e7f-117">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91e7f-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91e7f-118">Входные данные</span><span class="sxs-lookup"><span data-stu-id="91e7f-118">INPUTS</span></span>

## <span data-ttu-id="91e7f-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="91e7f-119">OUTPUTS</span></span>

### <span data-ttu-id="91e7f-120">System.Guid</span><span class="sxs-lookup"><span data-stu-id="91e7f-120">System.Guid</span></span>

<span data-ttu-id="91e7f-121">Этот командлет возвращает идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="91e7f-121">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="91e7f-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="91e7f-122">NOTES</span></span>

## <span data-ttu-id="91e7f-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="91e7f-123">RELATED LINKS</span></span>

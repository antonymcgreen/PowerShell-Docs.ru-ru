---
title: Объявление атрибута Валидатеранже | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369133"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="8d20e-102">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="8d20e-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="8d20e-103">Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="8d20e-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="8d20e-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d20e-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="8d20e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d20e-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="8d20e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d20e-106">Parameters</span></span>

<span data-ttu-id="8d20e-107">требуется `MinRange` ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="8d20e-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="8d20e-108">Указывает минимальное допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="8d20e-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="8d20e-109">требуется `MaxRange` ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="8d20e-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="8d20e-110">Указывает максимально допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="8d20e-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d20e-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="8d20e-111">Remarks</span></span>

- <span data-ttu-id="8d20e-112">Среда выполнения Windows PowerShell создает ошибку создания, если значение параметра `MinRange` больше значения параметра `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="8d20e-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="8d20e-113">Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="8d20e-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="8d20e-114">Если значение аргумента меньше `MinRange` предела или превышает ограничение `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="8d20e-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="8d20e-115">Если аргумент имеет тип, отличный от типа `MinRange` и параметров `MaxRange`.</span><span class="sxs-lookup"><span data-stu-id="8d20e-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="8d20e-116">Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="8d20e-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d20e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d20e-117">See Also</span></span>

[<span data-ttu-id="8d20e-118">System. Management. Automation. Валидатеранжеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8d20e-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="8d20e-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d20e-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

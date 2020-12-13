---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateRange
description: Объявление атрибута ValidateRange
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660604"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="5a489-103">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="5a489-103">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="5a489-104">Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="5a489-104">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="5a489-105">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a489-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a489-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a489-106">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="5a489-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a489-107">Parameters</span></span>

<span data-ttu-id="5a489-108">`MinRange` Требуется ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="5a489-108">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="5a489-109">Указывает минимальное допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="5a489-109">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="5a489-110">`MaxRange` Требуется ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="5a489-110">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="5a489-111">Указывает максимально допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="5a489-111">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a489-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5a489-112">Remarks</span></span>

- <span data-ttu-id="5a489-113">Среда выполнения Windows PowerShell создает ошибку создания, если значение `MinRange` параметра больше значения `MaxRange` параметра.</span><span class="sxs-lookup"><span data-stu-id="5a489-113">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="5a489-114">Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="5a489-114">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="5a489-115">, Если значение аргумента меньше `MinRange` ограничения или превышает его `MaxRange` .</span><span class="sxs-lookup"><span data-stu-id="5a489-115">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="5a489-116">Если аргумент имеет тип, отличный от типа `MinRange` и `MaxRange` параметров.</span><span class="sxs-lookup"><span data-stu-id="5a489-116">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="5a489-117">Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="5a489-117">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a489-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a489-118">See Also</span></span>

[<span data-ttu-id="5a489-119">System. Management. Automation. Валидатеранжеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="5a489-119">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="5a489-120">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a489-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

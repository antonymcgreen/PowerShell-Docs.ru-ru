---
title: Объявление атрибута Валидатеранже | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787790"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="12daa-102">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="12daa-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="12daa-103">Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="12daa-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="12daa-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12daa-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="12daa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12daa-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="12daa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12daa-106">Parameters</span></span>

<span data-ttu-id="12daa-107">`MinRange`Требуется ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="12daa-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="12daa-108">Указывает минимальное допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="12daa-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="12daa-109">`MaxRange`Требуется ([System. Object](/dotnet/api/system.object)).</span><span class="sxs-lookup"><span data-stu-id="12daa-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="12daa-110">Указывает максимально допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="12daa-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="12daa-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="12daa-111">Remarks</span></span>

- <span data-ttu-id="12daa-112">Среда выполнения Windows PowerShell создает ошибку создания, если значение `MinRange` параметра больше значения `MaxRange` параметра.</span><span class="sxs-lookup"><span data-stu-id="12daa-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="12daa-113">Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="12daa-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="12daa-114">, Если значение аргумента меньше `MinRange` ограничения или превышает его `MaxRange` .</span><span class="sxs-lookup"><span data-stu-id="12daa-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="12daa-115">Если аргумент имеет тип, отличный от типа `MinRange` и `MaxRange` параметров.</span><span class="sxs-lookup"><span data-stu-id="12daa-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="12daa-116">Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="12daa-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="12daa-117">См. также</span><span class="sxs-lookup"><span data-stu-id="12daa-117">See Also</span></span>

[<span data-ttu-id="12daa-118">System. Management. Automation. Валидатеранжеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="12daa-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="12daa-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12daa-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

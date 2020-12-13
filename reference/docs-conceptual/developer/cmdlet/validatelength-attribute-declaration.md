---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateLength
description: Объявление атрибута ValidateLength
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646182"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="2a99e-103">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="2a99e-103">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="2a99e-104">Атрибут Валидателенгс указывает минимальное и максимальное число символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="2a99e-104">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="2a99e-105">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a99e-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a99e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a99e-106">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="2a99e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a99e-107">Parameters</span></span>

<span data-ttu-id="2a99e-108">`MinLength` ([System. Int32](/dotnet/api/System.Int32)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="2a99e-108">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="2a99e-109">Указывает минимальное допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="2a99e-109">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="2a99e-110">`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="2a99e-110">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="2a99e-111">Указывает максимально допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="2a99e-111">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a99e-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2a99e-112">Remarks</span></span>

- <span data-ttu-id="2a99e-113">Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять правила проверки входных данных](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="2a99e-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="2a99e-114">Если этот атрибут не используется, соответствующий аргумент параметра может иметь любую длину.</span><span class="sxs-lookup"><span data-stu-id="2a99e-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="2a99e-115">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="2a99e-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="2a99e-116">Если значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="2a99e-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="2a99e-117">Если `MaxLength` параметр атрибута имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="2a99e-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="2a99e-118">Если аргумент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="2a99e-118">When the argument is not a string.</span></span>

- <span data-ttu-id="2a99e-119">Атрибут Валидателенгс определяется классом [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .</span><span class="sxs-lookup"><span data-stu-id="2a99e-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a99e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a99e-120">See Also</span></span>

[<span data-ttu-id="2a99e-121">System. Management. Automation. Валидателенгсаттрибуте</span><span class="sxs-lookup"><span data-stu-id="2a99e-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="2a99e-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a99e-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

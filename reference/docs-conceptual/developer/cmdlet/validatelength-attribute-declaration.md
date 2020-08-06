---
title: Объявление атрибута Валидателенгс | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786311"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="900a0-102">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="900a0-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="900a0-103">Атрибут Валидателенгс указывает минимальное и максимальное число символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="900a0-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="900a0-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900a0-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="900a0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="900a0-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="900a0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="900a0-106">Parameters</span></span>

<span data-ttu-id="900a0-107">`MinLength`([System. Int32](/dotnet/api/System.Int32)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="900a0-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="900a0-108">Указывает минимальное допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="900a0-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="900a0-109">`MaxLength`([System. Int32](/dotnet/api/System.Int32)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="900a0-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="900a0-110">Указывает максимально допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="900a0-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="900a0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="900a0-111">Remarks</span></span>

- <span data-ttu-id="900a0-112">Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять правила проверки входных данных](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="900a0-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="900a0-113">Если этот атрибут не используется, соответствующий аргумент параметра может иметь любую длину.</span><span class="sxs-lookup"><span data-stu-id="900a0-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="900a0-114">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="900a0-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="900a0-115">Если значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="900a0-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="900a0-116">Если `MaxLength` параметр атрибута имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="900a0-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="900a0-117">Если аргумент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="900a0-117">When the argument is not a string.</span></span>

- <span data-ttu-id="900a0-118">Атрибут Валидателенгс определяется классом [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .</span><span class="sxs-lookup"><span data-stu-id="900a0-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="900a0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="900a0-119">See Also</span></span>

[<span data-ttu-id="900a0-120">System. Management. Automation. Валидателенгсаттрибуте</span><span class="sxs-lookup"><span data-stu-id="900a0-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="900a0-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="900a0-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

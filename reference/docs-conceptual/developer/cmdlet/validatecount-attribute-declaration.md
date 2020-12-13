---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateCount
description: Объявление атрибута ValidateCount
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646265"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="09b7e-103">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="09b7e-103">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="09b7e-104">Атрибут Валидатекаунт указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="09b7e-104">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="09b7e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09b7e-105">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="09b7e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="09b7e-106">Parameters</span></span>

<span data-ttu-id="09b7e-107">`MinLength` ([System. Int32][]) обязательный.</span><span class="sxs-lookup"><span data-stu-id="09b7e-107">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="09b7e-108">Указывает минимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="09b7e-108">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="09b7e-109">`MaxLength`([System. Int32][]) обязательный.</span><span class="sxs-lookup"><span data-stu-id="09b7e-109">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="09b7e-110">Указывает максимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="09b7e-110">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="09b7e-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="09b7e-111">Remarks</span></span>

- <span data-ttu-id="09b7e-112">Дополнительные сведения об объявлении этого атрибута см. в разделе [проверка числа аргументов][].</span><span class="sxs-lookup"><span data-stu-id="09b7e-112">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="09b7e-113">Если этот атрибут не вызывается, соответствующий параметр командлета может иметь любое количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="09b7e-113">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="09b7e-114">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="09b7e-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="09b7e-115">`MinLength` `MaxLength` Параметры атрибута и не относятся к типу [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="09b7e-115">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="09b7e-116">Значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="09b7e-116">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="09b7e-117">Атрибут Валидатекаунт определяется классом [System. Management. Automation. валидатекаунтаттрибуте][] .</span><span class="sxs-lookup"><span data-stu-id="09b7e-117">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b7e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="09b7e-118">See Also</span></span>

<span data-ttu-id="09b7e-119">[System. Management. Automation. Валидатекаунтаттрибуте][]</span><span class="sxs-lookup"><span data-stu-id="09b7e-119">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="09b7e-120">[Как проверить количество аргументов][]</span><span class="sxs-lookup"><span data-stu-id="09b7e-120">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="09b7e-121">[Запись командлета Windows PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="09b7e-121">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. Валидатекаунтаттрибуте]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute

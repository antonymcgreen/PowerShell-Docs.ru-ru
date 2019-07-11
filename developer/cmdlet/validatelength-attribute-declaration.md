---
title: Объявление атрибута ValidateLength | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735107"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="d010f-102">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="d010f-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="d010f-103">Атрибут ValidateLength указывает минимальное и максимальное количество символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="d010f-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="d010f-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d010f-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="d010f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d010f-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="d010f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d010f-106">Parameters</span></span>

<span data-ttu-id="d010f-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) требуется.</span><span class="sxs-lookup"><span data-stu-id="d010f-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="d010f-108">Указывает минимальное число символов.</span><span class="sxs-lookup"><span data-stu-id="d010f-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="d010f-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) требуется.</span><span class="sxs-lookup"><span data-stu-id="d010f-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="d010f-110">Указывает максимальное допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="d010f-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d010f-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="d010f-111">Remarks</span></span>

- <span data-ttu-id="d010f-112">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="d010f-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="d010f-113">Если этот атрибут не используется, что соответствующий аргумент параметра может быть любой длины.</span><span class="sxs-lookup"><span data-stu-id="d010f-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="d010f-114">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="d010f-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="d010f-115">Если значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="d010f-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="d010f-116">Когда `MaxLength` параметр атрибута имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="d010f-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="d010f-117">Если аргумент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="d010f-117">When the argument is not a string.</span></span>

- <span data-ttu-id="d010f-118">Атрибут ValidateLength определяется [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="d010f-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d010f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d010f-119">See Also</span></span>

[<span data-ttu-id="d010f-120">System.Management.Automation.Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="d010f-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="d010f-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d010f-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

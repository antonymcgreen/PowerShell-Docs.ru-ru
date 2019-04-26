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
ms.openlocfilehash: 3a4c5f279ce8587eeb5d583376ea3d2286210b83
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067167"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="098ec-102">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="098ec-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="098ec-103">Атрибут ValidateLength указывает минимальное и максимальное количество символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="098ec-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="098ec-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="098ec-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="098ec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="098ec-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="098ec-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="098ec-106">Parameters</span></span>

<span data-ttu-id="098ec-107">`MinLength` ([System.Integer](/dotnet/api/System.Integer)) требуется.</span><span class="sxs-lookup"><span data-stu-id="098ec-107">`MinLength` ([System.Integer](/dotnet/api/System.Integer)) Required.</span></span> <span data-ttu-id="098ec-108">Указывает минимальное число символов.</span><span class="sxs-lookup"><span data-stu-id="098ec-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="098ec-109">`MaxLength` ([System.Integer](/dotnet/api/System.Integer)) требуется.</span><span class="sxs-lookup"><span data-stu-id="098ec-109">`MaxLength` ([System.Integer](/dotnet/api/System.Integer)) Required.</span></span> <span data-ttu-id="098ec-110">Указывает максимальное допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="098ec-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="098ec-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="098ec-111">Remarks</span></span>

- <span data-ttu-id="098ec-112">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span><span class="sxs-lookup"><span data-stu-id="098ec-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span></span>

- <span data-ttu-id="098ec-113">Если этот атрибут не используется, что соответствующий аргумент параметра может быть любой длины.</span><span class="sxs-lookup"><span data-stu-id="098ec-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="098ec-114">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="098ec-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="098ec-115">Если значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="098ec-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="098ec-116">Когда `MaxLength` параметр атрибута имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="098ec-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="098ec-117">Если аргумент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="098ec-117">When the argument is not a string.</span></span>

- <span data-ttu-id="098ec-118">Атрибут ValidateLength определяется [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="098ec-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="098ec-119">См. также</span><span class="sxs-lookup"><span data-stu-id="098ec-119">See Also</span></span>

[<span data-ttu-id="098ec-120">System.Management.Automation.Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="098ec-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="098ec-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="098ec-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

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
ms.openlocfilehash: 1e8364c78abba5272007019550ffcb2cedaf9fd0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858870"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="e064c-102">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="e064c-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="e064c-103">Атрибут ValidateLength указывает минимальное и максимальное количество символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="e064c-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="e064c-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e064c-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="e064c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e064c-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="e064c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e064c-106">Parameters</span></span>

<span data-ttu-id="e064c-107">`MinLength` ([System.Integer](/dotnet/api/System.Integer)) требуется.</span><span class="sxs-lookup"><span data-stu-id="e064c-107">`MinLength` ([System.Integer](/dotnet/api/System.Integer)) Required.</span></span> <span data-ttu-id="e064c-108">Указывает минимальное число символов.</span><span class="sxs-lookup"><span data-stu-id="e064c-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="e064c-109">`MaxLength` ([System.Integer](/dotnet/api/System.Integer)) требуется.</span><span class="sxs-lookup"><span data-stu-id="e064c-109">`MaxLength` ([System.Integer](/dotnet/api/System.Integer)) Required.</span></span> <span data-ttu-id="e064c-110">Указывает максимальное допустимое число символов.</span><span class="sxs-lookup"><span data-stu-id="e064c-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e064c-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="e064c-111">Remarks</span></span>

- <span data-ttu-id="e064c-112">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span><span class="sxs-lookup"><span data-stu-id="e064c-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span></span>
- <span data-ttu-id="e064c-113">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span><span class="sxs-lookup"><span data-stu-id="e064c-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span></span>

- <span data-ttu-id="e064c-114">Если этот атрибут не используется, что соответствующий аргумент параметра может быть любой длины.</span><span class="sxs-lookup"><span data-stu-id="e064c-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="e064c-115">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="e064c-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="e064c-116">Если значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="e064c-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="e064c-117">Когда `MaxLength` параметр атрибута имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="e064c-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="e064c-118">Если аргумент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="e064c-118">When the argument is not a string.</span></span>

- <span data-ttu-id="e064c-119">Атрибут ValidateLength определяется [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="e064c-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e064c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e064c-120">See Also</span></span>

[<span data-ttu-id="e064c-121">System.Management.Automation.Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="e064c-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="e064c-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e064c-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

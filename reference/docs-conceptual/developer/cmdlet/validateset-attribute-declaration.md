---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateSet
description: Объявление атрибута ValidateSet
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660463"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="50f7e-103">Объявление атрибута ValidateSet</span><span class="sxs-lookup"><span data-stu-id="50f7e-103">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="50f7e-104">Атрибут Валидатесетаттрибуте задает набор возможных значений для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="50f7e-104">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="50f7e-105">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50f7e-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="50f7e-106">Если этот атрибут указан, среда выполнения Windows PowerShell определяет, соответствует ли переданный аргумент параметру командлета элементу в указанном наборе элементов.</span><span class="sxs-lookup"><span data-stu-id="50f7e-106">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="50f7e-107">Командлет выполняется, только если аргумент параметра соответствует элементу в наборе.</span><span class="sxs-lookup"><span data-stu-id="50f7e-107">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="50f7e-108">Если совпадений не найдено, среда выполнения Windows PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="50f7e-108">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="50f7e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50f7e-109">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="50f7e-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="50f7e-110">Parameters</span></span>

<span data-ttu-id="50f7e-111">`ValidValues` ([System. String](/dotnet/api/System.String)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="50f7e-111">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="50f7e-112">Указывает допустимые значения элементов параметров.</span><span class="sxs-lookup"><span data-stu-id="50f7e-112">Specifies the valid parameter element values.</span></span> <span data-ttu-id="50f7e-113">В следующем примере показано, как указать один элемент или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="50f7e-113">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="50f7e-114">`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="50f7e-114">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="50f7e-115">Значение по умолчанию, равное `true` , указывает, что регистр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="50f7e-115">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="50f7e-116">Значение `false` делает командлет с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="50f7e-116">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="50f7e-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="50f7e-117">Remarks</span></span>

- <span data-ttu-id="50f7e-118">Этот атрибут можно использовать только один раз для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="50f7e-118">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="50f7e-119">Если значение параметра является массивом, каждый элемент массива должен соответствовать элементу набора атрибутов.</span><span class="sxs-lookup"><span data-stu-id="50f7e-119">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="50f7e-120">Атрибут Валидатесетаттрибуте определяется классом [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .</span><span class="sxs-lookup"><span data-stu-id="50f7e-120">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="50f7e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="50f7e-121">See Also</span></span>

[<span data-ttu-id="50f7e-122">System. Management. Automation. Валидатесетаттрибуте</span><span class="sxs-lookup"><span data-stu-id="50f7e-122">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="50f7e-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50f7e-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

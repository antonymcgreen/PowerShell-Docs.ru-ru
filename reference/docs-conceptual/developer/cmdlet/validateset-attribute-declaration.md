---
title: Объявление атрибута "Validate" | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.openlocfilehash: 0b6833efb0ce8e9474e9d91049fd201fc845cbea
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787773"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="f79f1-102">Объявление атрибута ValidateSet</span><span class="sxs-lookup"><span data-stu-id="f79f1-102">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="f79f1-103">Атрибут Валидатесетаттрибуте задает набор возможных значений для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="f79f1-103">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="f79f1-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f79f1-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="f79f1-105">Если этот атрибут указан, среда выполнения Windows PowerShell определяет, соответствует ли переданный аргумент параметру командлета элементу в указанном наборе элементов.</span><span class="sxs-lookup"><span data-stu-id="f79f1-105">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="f79f1-106">Командлет выполняется, только если аргумент параметра соответствует элементу в наборе.</span><span class="sxs-lookup"><span data-stu-id="f79f1-106">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="f79f1-107">Если совпадений не найдено, среда выполнения Windows PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="f79f1-107">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="f79f1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f79f1-108">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="f79f1-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="f79f1-109">Parameters</span></span>

<span data-ttu-id="f79f1-110">`ValidValues`([System. String](/dotnet/api/System.String)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="f79f1-110">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="f79f1-111">Указывает допустимые значения элементов параметров.</span><span class="sxs-lookup"><span data-stu-id="f79f1-111">Specifies the valid parameter element values.</span></span> <span data-ttu-id="f79f1-112">В следующем примере показано, как указать один элемент или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="f79f1-112">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="f79f1-113">`IgnoreCase`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="f79f1-113">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="f79f1-114">Значение по умолчанию, равное `true` , указывает, что регистр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f79f1-114">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="f79f1-115">Значение `false` делает командлет с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="f79f1-115">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="f79f1-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="f79f1-116">Remarks</span></span>

- <span data-ttu-id="f79f1-117">Этот атрибут можно использовать только один раз для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="f79f1-117">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="f79f1-118">Если значение параметра является массивом, каждый элемент массива должен соответствовать элементу набора атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f79f1-118">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="f79f1-119">Атрибут Валидатесетаттрибуте определяется классом [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .</span><span class="sxs-lookup"><span data-stu-id="f79f1-119">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79f1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f79f1-120">See Also</span></span>

[<span data-ttu-id="f79f1-121">System. Management. Automation. Валидатесетаттрибуте</span><span class="sxs-lookup"><span data-stu-id="f79f1-121">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="f79f1-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79f1-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

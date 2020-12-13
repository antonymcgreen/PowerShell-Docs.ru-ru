---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить диапазон аргумента
description: Как проверить диапазон аргумента
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666932"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="114ee-103">Как проверить диапазон аргумента</span><span class="sxs-lookup"><span data-stu-id="114ee-103">How to Validate an Argument Range</span></span>

<span data-ttu-id="114ee-104">В этом примере показано, как указать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки минимального и максимального значений аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="114ee-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="114ee-105">Это правило проверки задается путем объявления атрибута Валидатеранже.</span><span class="sxs-lookup"><span data-stu-id="114ee-105">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="114ee-106">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="114ee-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="114ee-107">Проверка диапазона аргументов</span><span class="sxs-lookup"><span data-stu-id="114ee-107">To validate an argument range</span></span>

- <span data-ttu-id="114ee-108">Добавьте атрибут Валидатеранже, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="114ee-108">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="114ee-109">В этом примере в качестве параметра указывается диапазон от 0 до 5 `InputData` .</span><span class="sxs-lookup"><span data-stu-id="114ee-109">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="114ee-110">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="114ee-110">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="114ee-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="114ee-111">See Also</span></span>

[<span data-ttu-id="114ee-112">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="114ee-112">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="114ee-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="114ee-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

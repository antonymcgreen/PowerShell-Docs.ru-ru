---
title: Проверка диапазона аргументов | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange attribute, example
ms.openlocfilehash: b48b1b87425add51e855c48ec700c78c3ae296c1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782078"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="52901-102">Как проверить диапазон аргумента</span><span class="sxs-lookup"><span data-stu-id="52901-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="52901-103">В этом примере показано, как указать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки минимального и максимального значений аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="52901-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="52901-104">Это правило проверки задается путем объявления атрибута Валидатеранже.</span><span class="sxs-lookup"><span data-stu-id="52901-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="52901-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="52901-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="52901-106">Проверка диапазона аргументов</span><span class="sxs-lookup"><span data-stu-id="52901-106">To validate an argument range</span></span>

- <span data-ttu-id="52901-107">Добавьте атрибут Валидатеранже, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="52901-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="52901-108">В этом примере в качестве параметра указывается диапазон от 0 до 5 `InputData` .</span><span class="sxs-lookup"><span data-stu-id="52901-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

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

<span data-ttu-id="52901-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="52901-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52901-110">См. также</span><span class="sxs-lookup"><span data-stu-id="52901-110">See Also</span></span>

[<span data-ttu-id="52901-111">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="52901-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="52901-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52901-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

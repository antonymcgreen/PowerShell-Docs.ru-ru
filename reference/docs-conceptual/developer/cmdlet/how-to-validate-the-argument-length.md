---
title: Проверка длины аргумента | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784084"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="e44e8-102">Как проверить длину аргумента</span><span class="sxs-lookup"><span data-stu-id="e44e8-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="e44e8-103">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки числа символов (длины) аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e44e8-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="e44e8-104">Это правило проверки задается путем объявления атрибута Валидателенгс.</span><span class="sxs-lookup"><span data-stu-id="e44e8-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="e44e8-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="e44e8-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="e44e8-106">Проверка длины аргумента</span><span class="sxs-lookup"><span data-stu-id="e44e8-106">To validate the argument length</span></span>

- <span data-ttu-id="e44e8-107">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e44e8-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="e44e8-108">В этом примере указывается, что длина аргумента должна иметь длину от 0 до 10 символов.</span><span class="sxs-lookup"><span data-stu-id="e44e8-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="e44e8-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="e44e8-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e44e8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e44e8-110">See Also</span></span>

[<span data-ttu-id="e44e8-111">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="e44e8-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="e44e8-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e44e8-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

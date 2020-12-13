---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить длину аргумента
description: Как проверить длину аргумента
ms.openlocfilehash: 460aedbe6847033f976cb7bf70b6c77ac5a3a3c9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652629"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="7160a-103">Как проверить длину аргумента</span><span class="sxs-lookup"><span data-stu-id="7160a-103">How to Validate the Argument Length</span></span>

<span data-ttu-id="7160a-104">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки числа символов (длины) аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="7160a-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="7160a-105">Это правило проверки задается путем объявления атрибута Валидателенгс.</span><span class="sxs-lookup"><span data-stu-id="7160a-105">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="7160a-106">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="7160a-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="7160a-107">Проверка длины аргумента</span><span class="sxs-lookup"><span data-stu-id="7160a-107">To validate the argument length</span></span>

- <span data-ttu-id="7160a-108">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7160a-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="7160a-109">В этом примере указывается, что длина аргумента должна иметь длину от 0 до 10 символов.</span><span class="sxs-lookup"><span data-stu-id="7160a-109">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="7160a-110">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7160a-110">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7160a-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="7160a-111">See Also</span></span>

[<span data-ttu-id="7160a-112">Объявление атрибута ValidateLength</span><span class="sxs-lookup"><span data-stu-id="7160a-112">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="7160a-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7160a-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

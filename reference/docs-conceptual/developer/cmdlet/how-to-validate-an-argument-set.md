---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить набор аргументов
description: Как проверить набор аргументов
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650368"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="5a4e0-103">Как проверить набор аргументов</span><span class="sxs-lookup"><span data-stu-id="5a4e0-103">How to Validate an Argument Set</span></span>

<span data-ttu-id="5a4e0-104">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5a4e0-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="5a4e0-105">Это правило проверки предоставляет набор допустимых значений аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="5a4e0-105">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="5a4e0-106">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="5a4e0-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="5a4e0-107">Проверка набора аргументов</span><span class="sxs-lookup"><span data-stu-id="5a4e0-107">To validate an argument set</span></span>

- <span data-ttu-id="5a4e0-108">Добавьте атрибут "Validate", как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="5a4e0-108">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="5a4e0-109">В этом примере указывается набор из трех возможных значений для `UserName` параметра.</span><span class="sxs-lookup"><span data-stu-id="5a4e0-109">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

<span data-ttu-id="5a4e0-110">Дополнительные сведения об объявлении этого атрибута см. в разделе [Проверка объявления атрибута](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5a4e0-110">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a4e0-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a4e0-111">See Also</span></span>

[<span data-ttu-id="5a4e0-112">System. Management. Automation. Валидатесетаттрибуте</span><span class="sxs-lookup"><span data-stu-id="5a4e0-112">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="5a4e0-113">Объявление атрибута ValidateSet</span><span class="sxs-lookup"><span data-stu-id="5a4e0-113">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="5a4e0-114">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a4e0-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

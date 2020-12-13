---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить количество аргументов
description: Как проверить количество аргументов
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666949"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="e469b-103">Как проверить количество аргументов</span><span class="sxs-lookup"><span data-stu-id="e469b-103">How to Validate an Argument Count</span></span>

<span data-ttu-id="e469b-104">В этом примере показано, как задать правило проверки, которое может использовать среда выполнения Windows PowerShell для проверки числа аргументов (счетчика), принимаемых параметром перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e469b-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="e469b-105">Это правило проверки задается путем объявления атрибута Валидатекаунт.</span><span class="sxs-lookup"><span data-stu-id="e469b-105">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="e469b-106">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатекаунтаттрибуте](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="e469b-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="e469b-107">Проверка числа аргументов</span><span class="sxs-lookup"><span data-stu-id="e469b-107">To validate an argument count</span></span>

- <span data-ttu-id="e469b-108">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e469b-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="e469b-109">В этом примере указывается, что параметр принимает один аргумент или не больше трех аргументов.</span><span class="sxs-lookup"><span data-stu-id="e469b-109">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

<span data-ttu-id="e469b-110">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="e469b-110">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e469b-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="e469b-111">See Also</span></span>

[<span data-ttu-id="e469b-112">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="e469b-112">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="e469b-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e469b-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

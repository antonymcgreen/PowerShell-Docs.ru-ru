---
title: Проверка числа аргументов | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782129"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="a49f2-102">Как проверить количество аргументов</span><span class="sxs-lookup"><span data-stu-id="a49f2-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="a49f2-103">В этом примере показано, как задать правило проверки, которое может использовать среда выполнения Windows PowerShell для проверки числа аргументов (счетчика), принимаемых параметром перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a49f2-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="a49f2-104">Это правило проверки задается путем объявления атрибута Валидатекаунт.</span><span class="sxs-lookup"><span data-stu-id="a49f2-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="a49f2-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатекаунтаттрибуте](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="a49f2-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="a49f2-106">Проверка числа аргументов</span><span class="sxs-lookup"><span data-stu-id="a49f2-106">To validate an argument count</span></span>

- <span data-ttu-id="a49f2-107">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a49f2-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="a49f2-108">В этом примере указывается, что параметр принимает один аргумент или не больше трех аргументов.</span><span class="sxs-lookup"><span data-stu-id="a49f2-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="a49f2-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="a49f2-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a49f2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a49f2-110">See Also</span></span>

[<span data-ttu-id="a49f2-111">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="a49f2-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="a49f2-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a49f2-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

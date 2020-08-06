---
title: Проверка набора аргументов | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782010"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="52005-102">Как проверить набор аргументов</span><span class="sxs-lookup"><span data-stu-id="52005-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="52005-103">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="52005-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="52005-104">Это правило проверки предоставляет набор допустимых значений аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="52005-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="52005-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="52005-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="52005-106">Проверка набора аргументов</span><span class="sxs-lookup"><span data-stu-id="52005-106">To validate an argument set</span></span>

- <span data-ttu-id="52005-107">Добавьте атрибут "Validate", как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="52005-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="52005-108">В этом примере указывается набор из трех возможных значений для `UserName` параметра.</span><span class="sxs-lookup"><span data-stu-id="52005-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="52005-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [Проверка объявления атрибута](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="52005-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52005-110">См. также</span><span class="sxs-lookup"><span data-stu-id="52005-110">See Also</span></span>

[<span data-ttu-id="52005-111">System. Management. Automation. Валидатесетаттрибуте</span><span class="sxs-lookup"><span data-stu-id="52005-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="52005-112">Объявление атрибута ValidateSet</span><span class="sxs-lookup"><span data-stu-id="52005-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="52005-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52005-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

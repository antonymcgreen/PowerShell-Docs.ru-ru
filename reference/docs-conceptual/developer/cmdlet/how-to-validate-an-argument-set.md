---
title: Проверка набора аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateSet attribute, example
ms.assetid: 55f0f664-d2ad-4501-a3dc-9f7a27c8ab11
caps.latest.revision: 8
ms.openlocfilehash: 6d8b189ed6311efd5a7348ab1e58934e9bff12a3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365513"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="46f77-102">Как проверить набор аргументов</span><span class="sxs-lookup"><span data-stu-id="46f77-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="46f77-103">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="46f77-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="46f77-104">Это правило проверки предоставляет набор допустимых значений аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="46f77-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="46f77-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="46f77-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="46f77-106">Проверка набора аргументов</span><span class="sxs-lookup"><span data-stu-id="46f77-106">To validate an argument set</span></span>

- <span data-ttu-id="46f77-107">Добавьте атрибут "Validate", как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="46f77-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="46f77-108">В этом примере задается набор из трех возможных значений для параметра `UserName`.</span><span class="sxs-lookup"><span data-stu-id="46f77-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="46f77-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [Проверка объявления атрибута](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="46f77-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46f77-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="46f77-110">See Also</span></span>

[<span data-ttu-id="46f77-111">System. Management. Automation. Валидатесетаттрибуте</span><span class="sxs-lookup"><span data-stu-id="46f77-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="46f77-112">Объявление атрибута "Validate"</span><span class="sxs-lookup"><span data-stu-id="46f77-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="46f77-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f77-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

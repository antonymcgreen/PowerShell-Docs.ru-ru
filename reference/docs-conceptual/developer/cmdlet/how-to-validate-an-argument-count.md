---
title: Проверка числа аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateCount attribute, example
ms.assetid: 4e6b6ac4-1003-4e7e-9d4a-9f1cf74fc4af
caps.latest.revision: 8
ms.openlocfilehash: b6ddb8185f21a65b2e3142ebb640962047e11763
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365533"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="644b1-102">Как проверить количество аргументов</span><span class="sxs-lookup"><span data-stu-id="644b1-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="644b1-103">В этом примере показано, как задать правило проверки, которое может использовать среда выполнения Windows PowerShell для проверки числа аргументов (счетчика), принимаемых параметром перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="644b1-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="644b1-104">Это правило проверки задается путем объявления атрибута Валидатекаунт.</span><span class="sxs-lookup"><span data-stu-id="644b1-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="644b1-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатекаунтаттрибуте](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="644b1-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="644b1-106">Проверка числа аргументов</span><span class="sxs-lookup"><span data-stu-id="644b1-106">To validate an argument count</span></span>

- <span data-ttu-id="644b1-107">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="644b1-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="644b1-108">В этом примере указывается, что параметр принимает один аргумент или не больше трех аргументов.</span><span class="sxs-lookup"><span data-stu-id="644b1-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="644b1-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="644b1-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="644b1-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="644b1-110">See Also</span></span>

[<span data-ttu-id="644b1-111">Объявление атрибута Валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="644b1-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="644b1-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="644b1-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

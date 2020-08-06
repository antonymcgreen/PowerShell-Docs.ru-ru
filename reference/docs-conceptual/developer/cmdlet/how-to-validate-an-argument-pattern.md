---
title: Проверка шаблона аргумента | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidatePattern attribute, example
ms.openlocfilehash: 35104e786d4b809a711d97fea52ae0e348dd5ca3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782095"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="50320-102">Как проверить шаблон аргумента</span><span class="sxs-lookup"><span data-stu-id="50320-102">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="50320-103">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки шаблона символов аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="50320-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="50320-104">Это правило проверки задается путем объявления атрибута ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="50320-104">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="50320-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="50320-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="50320-106">Проверка шаблона аргумента</span><span class="sxs-lookup"><span data-stu-id="50320-106">To validate an argument pattern</span></span>

- <span data-ttu-id="50320-107">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="50320-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="50320-108">В этом примере указывается шаблон из четырех цифр, где каждая цифра имеет значение от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="50320-108">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

<span data-ttu-id="50320-109">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="50320-109">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50320-110">См. также</span><span class="sxs-lookup"><span data-stu-id="50320-110">See Also</span></span>

[<span data-ttu-id="50320-111">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="50320-111">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="50320-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50320-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

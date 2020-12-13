---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить шаблон аргумента
description: Как проверить шаблон аргумента
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666915"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="44a32-103">Как проверить шаблон аргумента</span><span class="sxs-lookup"><span data-stu-id="44a32-103">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="44a32-104">В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки шаблона символов аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="44a32-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="44a32-105">Это правило проверки задается путем объявления атрибута ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="44a32-105">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="44a32-106">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="44a32-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="44a32-107">Проверка шаблона аргумента</span><span class="sxs-lookup"><span data-stu-id="44a32-107">To validate an argument pattern</span></span>

- <span data-ttu-id="44a32-108">Добавьте атрибут Validate, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="44a32-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="44a32-109">В этом примере указывается шаблон из четырех цифр, где каждая цифра имеет значение от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="44a32-109">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

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

<span data-ttu-id="44a32-110">Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="44a32-110">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44a32-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="44a32-111">See Also</span></span>

[<span data-ttu-id="44a32-112">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="44a32-112">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="44a32-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44a32-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

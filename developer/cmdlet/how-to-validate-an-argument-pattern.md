---
title: Как проверить шаблон аргумент | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidatePattern attribute, example
ms.assetid: 7ff76d4c-443a-4887-9ff8-241225f0aeec
caps.latest.revision: 9
ms.openlocfilehash: 5efc1210328c76e57a31d93b9eb52de114816c3c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067779"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="08ced-102">Как проверить шаблон аргумента</span><span class="sxs-lookup"><span data-stu-id="08ced-102">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="08ced-103">В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки комбинация символов аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="08ced-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="08ced-104">Это правило проверки устанавливается путем объявления атрибута ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="08ced-104">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="08ced-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="08ced-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="08ced-106">Чтобы проверить шаблон аргумент</span><span class="sxs-lookup"><span data-stu-id="08ced-106">To validate an argument pattern</span></span>

- <span data-ttu-id="08ced-107">Добавьте атрибут проверки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="08ced-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="08ced-108">В этом примере определяет шаблон из четырех цифр, где каждая цифра имеет значение от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="08ced-108">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

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

<span data-ttu-id="08ced-109">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="08ced-109">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08ced-110">См. также</span><span class="sxs-lookup"><span data-stu-id="08ced-110">See Also</span></span>

[<span data-ttu-id="08ced-111">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="08ced-111">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="08ced-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08ced-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

---
title: Способы проверки диапазона аргумент | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange attribute, example
ms.assetid: 3cba3ab7-c3b6-4d17-aa17-88377496551b
caps.latest.revision: 9
ms.openlocfilehash: a39e34d1f1c333185f09b4a934819e1368d29a48
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067796"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="98a5f-102">Как проверить диапазон аргумента</span><span class="sxs-lookup"><span data-stu-id="98a5f-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="98a5f-103">В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки минимальное и максимальное значения аргумента параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="98a5f-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="98a5f-104">Это правило проверки устанавливается путем объявления атрибута ValidateRange.</span><span class="sxs-lookup"><span data-stu-id="98a5f-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="98a5f-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="98a5f-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="98a5f-106">Для проверки диапазона аргументов</span><span class="sxs-lookup"><span data-stu-id="98a5f-106">To validate an argument range</span></span>

- <span data-ttu-id="98a5f-107">Добавьте атрибут ValidateRange, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="98a5f-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="98a5f-108">В этом примере указывает диапазон 0 – 5 для `InputData` параметра.</span><span class="sxs-lookup"><span data-stu-id="98a5f-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="98a5f-109">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="98a5f-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="98a5f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="98a5f-110">See Also</span></span>

[<span data-ttu-id="98a5f-111">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="98a5f-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="98a5f-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98a5f-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

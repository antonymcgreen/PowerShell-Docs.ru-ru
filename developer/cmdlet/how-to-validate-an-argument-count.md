---
title: Как проверить количество аргументов | Документация Майкрософт
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859140"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="f3a25-102">Как проверить количество аргументов</span><span class="sxs-lookup"><span data-stu-id="f3a25-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="f3a25-103">В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки число аргументов (число), которая принимает параметр перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f3a25-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="f3a25-104">Это правило проверки устанавливается путем объявления атрибута ValidateCount.</span><span class="sxs-lookup"><span data-stu-id="f3a25-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="f3a25-105">Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="f3a25-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="f3a25-106">Чтобы проверить количество аргументов</span><span class="sxs-lookup"><span data-stu-id="f3a25-106">To validate an argument count</span></span>

- <span data-ttu-id="f3a25-107">Добавьте атрибут проверки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f3a25-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="f3a25-108">В этом примере указывает, что параметр принимает один аргумент или до трех аргументов.</span><span class="sxs-lookup"><span data-stu-id="f3a25-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="f3a25-109">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="f3a25-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3a25-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f3a25-110">See Also</span></span>

[<span data-ttu-id="f3a25-111">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="f3a25-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="f3a25-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3a25-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

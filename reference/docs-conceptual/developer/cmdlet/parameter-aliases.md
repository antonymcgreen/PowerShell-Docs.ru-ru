---
title: Псевдонимы параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369593"
---
# <a name="parameter-aliases"></a><span data-ttu-id="5047a-102">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="5047a-102">Parameter Aliases</span></span>

<span data-ttu-id="5047a-103">Параметры командлетов могут также иметь псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="5047a-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="5047a-104">Вместо имен параметров можно использовать псевдонимы при вводе или указании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="5047a-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="5047a-105">Преимущества использования псевдонимов</span><span class="sxs-lookup"><span data-stu-id="5047a-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="5047a-106">Добавление псевдонимов в параметры предоставляет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="5047a-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="5047a-107">Можно указать ярлык, чтобы пользователю не применялись полные имена параметров при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="5047a-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="5047a-108">Например, можно использовать псевдоним CN вместо имени параметра ComputerName.</span><span class="sxs-lookup"><span data-stu-id="5047a-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="5047a-109">Можно определить несколько псевдонимов, если нужно указать разные имена для одного и того же параметра.</span><span class="sxs-lookup"><span data-stu-id="5047a-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="5047a-110">Может потребоваться определить несколько псевдонимов, если необходимо работать с несколькими группами пользователей, которые ссылаются на одни и те же данные различными способами.</span><span class="sxs-lookup"><span data-stu-id="5047a-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="5047a-111">При изменении имени параметра можно обеспечить обратную совместимость существующих скриптов.</span><span class="sxs-lookup"><span data-stu-id="5047a-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="5047a-112">С помощью атрибута Alias вместе с атрибутом Валуефромпипелинебинаме можно определить параметр, позволяющий командлету выполнить привязку к различным типам объектов.</span><span class="sxs-lookup"><span data-stu-id="5047a-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="5047a-113">Например, предположим, что у вас есть два объекта различных типов и первый объект имел свойство Writer, а второй объект имел свойство редактора.</span><span class="sxs-lookup"><span data-stu-id="5047a-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="5047a-114">Если у командлета есть параметр, имеющий псевдонимы модуля записи и редактора, а командлет принял входные данные конвейера на основе имен свойств, командлет может выполнить привязку к обоим объектам с помощью двух псевдонимов параметров.</span><span class="sxs-lookup"><span data-stu-id="5047a-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="5047a-115">Дополнительные сведения о псевдонимах, которые можно использовать с конкретными параметрами, см. в разделе [Общие имена параметров](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="5047a-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="5047a-116">Определение псевдонимов параметров</span><span class="sxs-lookup"><span data-stu-id="5047a-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="5047a-117">Чтобы определить псевдоним для параметра, объявите атрибут Alias, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="5047a-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="5047a-118">В этом примере для одного и того же параметра определено несколько псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="5047a-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="5047a-119">(Дополнительные сведения см.[в разделе как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).)</span><span class="sxs-lookup"><span data-stu-id="5047a-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

```csharp
[Alias("UN","Writer","Editor")]
[Parameter()]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="see-also"></a><span data-ttu-id="5047a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5047a-120">See Also</span></span>

[<span data-ttu-id="5047a-121">Общие имена параметров</span><span class="sxs-lookup"><span data-stu-id="5047a-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="5047a-122">Как объявлять параметры командлета</span><span class="sxs-lookup"><span data-stu-id="5047a-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="5047a-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5047a-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

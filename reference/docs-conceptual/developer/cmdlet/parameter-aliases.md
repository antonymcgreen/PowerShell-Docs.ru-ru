---
ms.date: 09/13/2016
ms.topic: reference
title: Псевдонимы параметров
description: Псевдонимы параметров
ms.openlocfilehash: 0895e2c4df3a149ae75a9741fb65134a8e1122c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648517"
---
# <a name="parameter-aliases"></a><span data-ttu-id="45567-103">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="45567-103">Parameter Aliases</span></span>

<span data-ttu-id="45567-104">Параметры командлета также могут иметь псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="45567-104">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="45567-105">Вместо имен параметров можно использовать псевдонимы при вводе или указании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="45567-105">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="45567-106">Преимущества использования псевдонимов</span><span class="sxs-lookup"><span data-stu-id="45567-106">Benefits of Using Aliases</span></span>

<span data-ttu-id="45567-107">Добавление псевдонимов в параметры предоставляет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="45567-107">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="45567-108">Можно указать ярлык, чтобы пользователю не применялись полные имена параметров при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="45567-108">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="45567-109">Например, можно использовать псевдоним CN вместо имени параметра ComputerName.</span><span class="sxs-lookup"><span data-stu-id="45567-109">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="45567-110">Можно определить несколько псевдонимов, если нужно указать разные имена для одного и того же параметра.</span><span class="sxs-lookup"><span data-stu-id="45567-110">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="45567-111">Может потребоваться определить несколько псевдонимов, если необходимо работать с несколькими группами пользователей, которые ссылаются на одни и те же данные различными способами.</span><span class="sxs-lookup"><span data-stu-id="45567-111">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="45567-112">При изменении имени параметра можно обеспечить обратную совместимость существующих скриптов.</span><span class="sxs-lookup"><span data-stu-id="45567-112">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="45567-113">С помощью атрибута Alias вместе с атрибутом Валуефромпипелинебинаме можно определить параметр, позволяющий командлету выполнить привязку к различным типам объектов.</span><span class="sxs-lookup"><span data-stu-id="45567-113">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="45567-114">Например, предположим, что у вас есть два объекта различных типов и первый объект имел свойство Writer, а второй объект имел свойство редактора.</span><span class="sxs-lookup"><span data-stu-id="45567-114">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="45567-115">Если у командлета есть параметр, имеющий псевдонимы модуля записи и редактора, а командлет принял входные данные конвейера на основе имен свойств, командлет может выполнить привязку к обоим объектам с помощью двух псевдонимов параметров.</span><span class="sxs-lookup"><span data-stu-id="45567-115">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="45567-116">Дополнительные сведения о псевдонимах, которые можно использовать с конкретными параметрами, см. в разделе [Общие имена параметров](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="45567-116">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="45567-117">Определение псевдонимов параметров</span><span class="sxs-lookup"><span data-stu-id="45567-117">Defining Parameter Aliases</span></span>

<span data-ttu-id="45567-118">Чтобы определить псевдоним для параметра, объявите атрибут Alias, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="45567-118">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="45567-119">В этом примере для одного и того же параметра определено несколько псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="45567-119">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="45567-120">(Дополнительные сведения см.[в разделе как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).)</span><span class="sxs-lookup"><span data-stu-id="45567-120">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="45567-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="45567-121">See Also</span></span>

[<span data-ttu-id="45567-122">Общие имена параметров</span><span class="sxs-lookup"><span data-stu-id="45567-122">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="45567-123">Как объявить параметры командлета</span><span class="sxs-lookup"><span data-stu-id="45567-123">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="45567-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45567-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

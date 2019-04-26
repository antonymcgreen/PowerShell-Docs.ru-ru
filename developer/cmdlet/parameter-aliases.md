---
title: Псевдонимы параметра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067592"
---
# <a name="parameter-aliases"></a><span data-ttu-id="fa4d6-102">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="fa4d6-102">Parameter Aliases</span></span>

<span data-ttu-id="fa4d6-103">Параметры командлетов могут также иметь псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="fa4d6-104">При вводе или укажите параметр в команде, можно использовать псевдонимы вместо имени параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="fa4d6-105">Преимущества использования псевдонимов</span><span class="sxs-lookup"><span data-stu-id="fa4d6-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="fa4d6-106">Добавление псевдонимы для параметров обеспечивает следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="fa4d6-107">Можно предоставить ярлык, чтобы пользователю не нужно использовать имя полный параметра при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="fa4d6-108">Например можно использовать псевдоним «CN» вместо «Имя_компьютера» имя параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="fa4d6-109">Если вы хотите, чтобы для предоставления разных имен для одного параметра можно определить несколько псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="fa4d6-110">Можно определить несколько псевдонимов, если необходимо работать с несколькими группами пользователей, которые ссылаются на те же данные различными способами.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="fa4d6-111">Вы можете предоставить обратной совместимости для существующих сценариев при изменении имени параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="fa4d6-112">С помощью атрибута псевдоним вместе с атрибутом ValueFromPipelineByName, можно определить параметр, который позволяет командлета для привязки к различным типам объектов.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="fa4d6-113">Например, имеется два разных объекта и первый объект имеет свойства модуля записи и второй объект имеет свойство, которое редактора.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="fa4d6-114">Если командлет имеет параметр, который бы модуля записи и редактор псевдонимы и командлет принимаются входные данные конвейера, в именах свойств, командлет удалось выполнить привязку к оба объекта, используя два псевдонима параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="fa4d6-115">Дополнительные сведения о псевдонимах, которые могут использоваться с определенными параметрами, см. в разделе [общие имена параметров](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="fa4d6-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="fa4d6-116">Определение параметра псевдонимы</span><span class="sxs-lookup"><span data-stu-id="fa4d6-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="fa4d6-117">Определить псевдоним для параметра, объявите атрибут псевдоним, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="fa4d6-118">В этом примере несколько псевдонимов определены для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="fa4d6-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="fa4d6-119">(Дополнительные сведения см. в разделе[как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md).)</span><span class="sxs-lookup"><span data-stu-id="fa4d6-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fa4d6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fa4d6-120">See Also</span></span>

[<span data-ttu-id="fa4d6-121">Имена общих параметров</span><span class="sxs-lookup"><span data-stu-id="fa4d6-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="fa4d6-122">Как объявить параметры командлета</span><span class="sxs-lookup"><span data-stu-id="fa4d6-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="fa4d6-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa4d6-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

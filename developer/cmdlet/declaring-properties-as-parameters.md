---
title: Объявление свойств как параметры | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f71ea35d-cff5-4e44-a5c6-3a747ed4c4d9
caps.latest.revision: 9
ms.openlocfilehash: 6f6640afb15b3608669538f9b5f53d7a8a5c380d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861380"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="46d6a-102">Объявление свойств в качестве параметров</span><span class="sxs-lookup"><span data-stu-id="46d6a-102">Declaring Properties as Parameters</span></span>

<span data-ttu-id="46d6a-103">В этом разделе содержит основные сведения, которыми необходимо ознакомиться, прежде чем объявить параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="46d6a-103">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="46d6a-104">Чтобы объявить параметры командлета в классе командлета, определять открытые свойства, которые представляют каждый параметр и затем добавьте один или несколько атрибутов параметра для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="46d6a-104">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="46d6a-105">Среда выполнения Windows PowerShell использует атрибуты параметра для идентификации свойства в виде параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="46d6a-105">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="46d6a-106">Базовый синтаксис для объявления атрибута параметра `[Parameter()]`.</span><span class="sxs-lookup"><span data-stu-id="46d6a-106">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="46d6a-107">Ниже приведен пример свойства, определенные как обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="46d6a-107">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="46d6a-108">Ниже приведены некоторые важные советы о параметрах.</span><span class="sxs-lookup"><span data-stu-id="46d6a-108">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="46d6a-109">Параметр должен быть явно помечен как общедоступный.</span><span class="sxs-lookup"><span data-stu-id="46d6a-109">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="46d6a-110">Параметры, которые не помечены как открытые, по умолчанию внутренний и не будет найдена средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46d6a-110">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="46d6a-111">Параметры должны быть определены как типы платформы Microsoft .NET Framework для обеспечения лучшей проверки параметра.</span><span class="sxs-lookup"><span data-stu-id="46d6a-111">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="46d6a-112">Например параметры, которые ограничены одно значение из набора значений должен быть определен как тип перечисления.</span><span class="sxs-lookup"><span data-stu-id="46d6a-112">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="46d6a-113">Параметры, которые принимают значение универсального кода ресурса (URI) должен иметь тип [System.Uri](/dotnet/api/System.Uri).</span><span class="sxs-lookup"><span data-stu-id="46d6a-113">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="46d6a-114">Избегайте основных строковых параметров для свойств все, кроме текста в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="46d6a-114">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="46d6a-115">Можно добавить параметр в любое количество наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="46d6a-115">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="46d6a-116">Дополнительные сведения о наборах параметров см. в разделе [командлет задает параметр](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="46d6a-116">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="46d6a-117">Windows PowerShell также предоставляет набор общих параметров, которые автоматически доступны для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="46d6a-117">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="46d6a-118">Дополнительные сведения об этих параметрах и их псевдонимы см. в разделе [общих параметров командлета](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="46d6a-118">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46d6a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="46d6a-119">See Also</span></span>

[<span data-ttu-id="46d6a-120">Командлет Общие параметры</span><span class="sxs-lookup"><span data-stu-id="46d6a-120">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="46d6a-121">Типы параметра командлета</span><span class="sxs-lookup"><span data-stu-id="46d6a-121">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="46d6a-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46d6a-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

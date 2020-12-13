---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление свойств в качестве параметров
description: Объявление свойств в качестве параметров
ms.openlocfilehash: ade7928e2ca277da8bbd1a5e04997bd1d05f1e5d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653157"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="a4ea1-103">Объявление свойств в качестве параметров</span><span class="sxs-lookup"><span data-stu-id="a4ea1-103">Declaring Properties as Parameters</span></span>

<span data-ttu-id="a4ea1-104">В этом разделе приводятся основные сведения, которые необходимо знать перед объявлением параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-104">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="a4ea1-105">Чтобы объявить параметры командлета в классе командлета, определите открытые свойства, представляющие каждый параметр, а затем добавьте один или несколько атрибутов параметров в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-105">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="a4ea1-106">Среда выполнения Windows PowerShell использует атрибуты параметра для задания свойства в качестве параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-106">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="a4ea1-107">Базовый синтаксис для объявления атрибута Parameter — `[Parameter()]` .</span><span class="sxs-lookup"><span data-stu-id="a4ea1-107">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="a4ea1-108">Ниже приведен пример свойства, определенного как обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-108">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="a4ea1-109">Ниже приведены некоторые моменты, которые следует учитывать при работе с параметрами.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-109">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="a4ea1-110">Параметр должен быть явно помечен как public.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-110">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="a4ea1-111">Параметры, которые не помечены как открытые по умолчанию, являются внутренними и не будут найдены средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-111">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="a4ea1-112">Параметры должны быть определены как Microsoft .NET типы платформы, чтобы обеспечить лучшую проверку параметров.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-112">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="a4ea1-113">Например, параметры, которые ограничены одним значением из набора значений, должны быть определены как тип перечисления.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-113">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="a4ea1-114">Параметры, принимающие значение универсального кода ресурса (URI), должны иметь тип [System. URI](/dotnet/api/System.Uri).</span><span class="sxs-lookup"><span data-stu-id="a4ea1-114">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="a4ea1-115">Избегайте использования основных строковых параметров для всех свойств текста в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-115">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="a4ea1-116">Можно добавить параметр в любое количество наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-116">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="a4ea1-117">Дополнительные сведения о наборах параметров см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a4ea1-117">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="a4ea1-118">Windows PowerShell также предоставляет набор общих параметров, которые автоматически доступны для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="a4ea1-118">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="a4ea1-119">Дополнительные сведения об этих параметрах и их псевдонимах см. в разделе [Общие параметры командлета](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="a4ea1-119">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4ea1-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4ea1-120">See Also</span></span>

[<span data-ttu-id="a4ea1-121">Общие параметры командлета</span><span class="sxs-lookup"><span data-stu-id="a4ea1-121">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="a4ea1-122">Типы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="a4ea1-122">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="a4ea1-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4ea1-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

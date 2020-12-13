---
ms.date: 09/13/2016
ms.topic: reference
title: Как объявить параметры командлета
description: Как объявить параметры командлета
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667102"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="9a153-103">Как объявить параметры командлета</span><span class="sxs-lookup"><span data-stu-id="9a153-103">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="9a153-104">В этих примерах показано, как объявить именованные, позиционированные, обязательные, необязательные и параметры Switch.</span><span class="sxs-lookup"><span data-stu-id="9a153-104">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="9a153-105">В этих примерах также показано, как определить псевдоним параметра.</span><span class="sxs-lookup"><span data-stu-id="9a153-105">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="9a153-106">Как объявить именованный параметр</span><span class="sxs-lookup"><span data-stu-id="9a153-106">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="9a153-107">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9a153-107">Define a public property as shown in the following code.</span></span> <span data-ttu-id="9a153-108">При добавлении атрибута параметра опустите `Position` ключевое слово из атрибута.</span><span class="sxs-lookup"><span data-stu-id="9a153-108">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="9a153-109">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="9a153-109">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="9a153-110">Как объявить Позиционированный параметр</span><span class="sxs-lookup"><span data-stu-id="9a153-110">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="9a153-111">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9a153-111">Define a public property as shown in the following code.</span></span> <span data-ttu-id="9a153-112">При добавлении атрибута Parameter задайте `Position` для ключевого слова значение, равное положению аргумента.</span><span class="sxs-lookup"><span data-stu-id="9a153-112">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="9a153-113">Значение 0 указывает на первую точку.</span><span class="sxs-lookup"><span data-stu-id="9a153-113">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="9a153-114">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="9a153-114">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="9a153-115">Как объявить обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="9a153-115">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="9a153-116">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9a153-116">Define a public property as shown in the following code.</span></span> <span data-ttu-id="9a153-117">При добавлении атрибута параметра задайте `Mandatory` для ключевого слова значение `true` .</span><span class="sxs-lookup"><span data-stu-id="9a153-117">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="9a153-118">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="9a153-118">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="9a153-119">Как объявить необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="9a153-119">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="9a153-120">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9a153-120">Define a public property as shown in the following code.</span></span> <span data-ttu-id="9a153-121">При добавлении атрибута параметра опустите `Mandatory` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="9a153-121">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="9a153-122">Как объявить параметр Switch</span><span class="sxs-lookup"><span data-stu-id="9a153-122">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="9a153-123">Определите открытое свойство как Type [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter), а затем объявите атрибут Parameter.</span><span class="sxs-lookup"><span data-stu-id="9a153-123">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="9a153-124">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="9a153-124">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="9a153-125">Как объявить параметр с псевдонимами</span><span class="sxs-lookup"><span data-stu-id="9a153-125">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="9a153-126">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9a153-126">Define a public property as shown in the following code.</span></span> <span data-ttu-id="9a153-127">Добавьте атрибут Alias, содержащий псевдонимы для параметра.</span><span class="sxs-lookup"><span data-stu-id="9a153-127">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="9a153-128">В этом примере для одного и того же параметра определены три псевдонима.</span><span class="sxs-lookup"><span data-stu-id="9a153-128">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="9a153-129">Первый псевдоним предоставляет ярлык.</span><span class="sxs-lookup"><span data-stu-id="9a153-129">The first alias provides a shortcut.</span></span> <span data-ttu-id="9a153-130">Второй и третий псевдонимы предоставляют имена, которые можно использовать для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="9a153-130">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="9a153-131">Дополнительные сведения об атрибуте Alias см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="9a153-131">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a153-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a153-132">See Also</span></span>

[<span data-ttu-id="9a153-133">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9a153-133">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="9a153-134">Объявление атрибута параметра</span><span class="sxs-lookup"><span data-stu-id="9a153-134">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="9a153-135">Объявление атрибута псевдонима</span><span class="sxs-lookup"><span data-stu-id="9a153-135">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="9a153-136">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a153-136">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

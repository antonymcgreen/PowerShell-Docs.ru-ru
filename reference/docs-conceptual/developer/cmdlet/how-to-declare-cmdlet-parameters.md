---
title: Как объявить параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c0509cc-5a50-49ad-a74f-5527023d0270
caps.latest.revision: 10
ms.openlocfilehash: 80e3e27bcf72b078c192525a843a3b3afb306529
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365683"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="ae96f-102">Как объявить параметры командлета</span><span class="sxs-lookup"><span data-stu-id="ae96f-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="ae96f-103">В этих примерах показано, как объявить именованные, позиционированные, обязательные, необязательные и параметры Switch.</span><span class="sxs-lookup"><span data-stu-id="ae96f-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="ae96f-104">В этих примерах также показано, как определить псевдоним параметра.</span><span class="sxs-lookup"><span data-stu-id="ae96f-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="ae96f-105">Как объявить именованный параметр</span><span class="sxs-lookup"><span data-stu-id="ae96f-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="ae96f-106">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ae96f-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="ae96f-107">При добавлении атрибута параметра опустите ключевое слово `Position` из атрибута.</span><span class="sxs-lookup"><span data-stu-id="ae96f-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="ae96f-108">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="ae96f-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="ae96f-109">Как объявить Позиционированный параметр</span><span class="sxs-lookup"><span data-stu-id="ae96f-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="ae96f-110">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ae96f-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="ae96f-111">При добавлении атрибута Parameter задайте для ключевого слова `Position` значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="ae96f-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="ae96f-112">Значение 0 указывает на первую точку.</span><span class="sxs-lookup"><span data-stu-id="ae96f-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="ae96f-113">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="ae96f-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="ae96f-114">Как объявить обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="ae96f-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="ae96f-115">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ae96f-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="ae96f-116">При добавлении атрибута параметра задайте для ключевого слова `Mandatory` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ae96f-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="ae96f-117">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="ae96f-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="ae96f-118">Как объявить необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="ae96f-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="ae96f-119">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ae96f-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="ae96f-120">При добавлении атрибута Parameter опустите ключевое слово `Mandatory`.</span><span class="sxs-lookup"><span data-stu-id="ae96f-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="ae96f-121">Как объявить параметр Switch</span><span class="sxs-lookup"><span data-stu-id="ae96f-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="ae96f-122">Определите открытое свойство как Type [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter), а затем объявите атрибут Parameter.</span><span class="sxs-lookup"><span data-stu-id="ae96f-122">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="ae96f-123">Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="ae96f-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="ae96f-124">Как объявить параметр с псевдонимами</span><span class="sxs-lookup"><span data-stu-id="ae96f-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="ae96f-125">Определите открытое свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ae96f-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="ae96f-126">Добавьте атрибут Alias, содержащий псевдонимы для параметра.</span><span class="sxs-lookup"><span data-stu-id="ae96f-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="ae96f-127">В этом примере для одного и того же параметра определены три псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ae96f-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="ae96f-128">Первый псевдоним предоставляет ярлык.</span><span class="sxs-lookup"><span data-stu-id="ae96f-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="ae96f-129">Второй и третий псевдонимы предоставляют имена, которые можно использовать для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="ae96f-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="ae96f-130">Дополнительные сведения об атрибуте Alias см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="ae96f-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae96f-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae96f-131">See Also</span></span>

[<span data-ttu-id="ae96f-132">System. Management. Automation. переключатель</span><span class="sxs-lookup"><span data-stu-id="ae96f-132">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="ae96f-133">Объявление атрибута Parameter</span><span class="sxs-lookup"><span data-stu-id="ae96f-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="ae96f-134">Объявление атрибута Alias</span><span class="sxs-lookup"><span data-stu-id="ae96f-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="ae96f-135">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae96f-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

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
ms.openlocfilehash: d6613889ebd2ba139ce0b3de1b8d24e4aec37d2a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861400"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="8c180-102">Как объявить параметры командлета</span><span class="sxs-lookup"><span data-stu-id="8c180-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="8c180-103">Эти примеры показывают, как объявить именованный, позиционные, необходимые, необязательные и параметры-переключатели.</span><span class="sxs-lookup"><span data-stu-id="8c180-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="8c180-104">Этих примерах также показано, как определить псевдоним параметра.</span><span class="sxs-lookup"><span data-stu-id="8c180-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="8c180-105">Как объявить именованный параметр</span><span class="sxs-lookup"><span data-stu-id="8c180-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="8c180-106">Определите общедоступное свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8c180-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="8c180-107">При добавлении атрибут Parameter, опустите `Position` ключевое слово из атрибута.</span><span class="sxs-lookup"><span data-stu-id="8c180-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="8c180-108">Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8c180-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="8c180-109">Как объявить позиционного параметра</span><span class="sxs-lookup"><span data-stu-id="8c180-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="8c180-110">Определите общедоступное свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8c180-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="8c180-111">При добавлении атрибут Parameter установите `Position` ключевое слово в позицию аргумента.</span><span class="sxs-lookup"><span data-stu-id="8c180-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="8c180-112">Значение 0 указывает первую позицию.</span><span class="sxs-lookup"><span data-stu-id="8c180-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="8c180-113">Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8c180-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="8c180-114">Как объявить обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="8c180-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="8c180-115">Определите общедоступное свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8c180-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="8c180-116">При добавлении атрибут Parameter установите `Mandatory` ключевое слово `true`.</span><span class="sxs-lookup"><span data-stu-id="8c180-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="8c180-117">Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8c180-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="8c180-118">Как объявить необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="8c180-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="8c180-119">Определите общедоступное свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8c180-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="8c180-120">При добавлении атрибут Parameter, опустите `Mandatory` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="8c180-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="8c180-121">Как объявить параметр-переключатель</span><span class="sxs-lookup"><span data-stu-id="8c180-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="8c180-122">Определить открытое свойство в качестве типа [System.Management.Automation.Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter), а затем объявить атрибут Parameter.</span><span class="sxs-lookup"><span data-stu-id="8c180-122">Define a public property as type [System.Management.Automation.Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="8c180-123">Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8c180-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="8c180-124">Способ объявления параметра с псевдонимами</span><span class="sxs-lookup"><span data-stu-id="8c180-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="8c180-125">Определите общедоступное свойство, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8c180-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="8c180-126">Добавьте атрибут псевдоним, который выводит список псевдонимов для параметра.</span><span class="sxs-lookup"><span data-stu-id="8c180-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="8c180-127">В этом примере три псевдонима определены для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="8c180-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="8c180-128">Первый псевдоним существует сочетание клавиш.</span><span class="sxs-lookup"><span data-stu-id="8c180-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="8c180-129">Второй и третий псевдонимы предоставляют имена, которые можно использовать для разных сценариев.</span><span class="sxs-lookup"><span data-stu-id="8c180-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="8c180-130">Дополнительные сведения об атрибуте псевдонима см. в разделе [объявление атрибута псевдоним](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8c180-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c180-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8c180-131">See Also</span></span>

[<span data-ttu-id="8c180-132">System.Management.Automation.Switchparameter</span><span class="sxs-lookup"><span data-stu-id="8c180-132">System.Management.Automation.Switchparameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="8c180-133">Объявление параметра-атрибут</span><span class="sxs-lookup"><span data-stu-id="8c180-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="8c180-134">Атрибут объявления псевдонима</span><span class="sxs-lookup"><span data-stu-id="8c180-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="8c180-135">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c180-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

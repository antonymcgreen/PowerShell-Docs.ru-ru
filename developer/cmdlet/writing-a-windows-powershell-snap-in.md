---
title: Написание оснастки Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], PSSnapin example
ms.assetid: 875024f4-e02b-4416-80b9-af5e5b50aad6
caps.latest.revision: 7
ms.openlocfilehash: d4f57c062fee09e85c290445082be745ab229985
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795040"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="b78f2-102">Написание оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b78f2-102">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="b78f2-103">В этом примере показано, как написать оснастки Windows PowerShell, который может использоваться, чтобы зарегистрировать все командлеты и поставщики Windows PowerShell в сборке.</span><span class="sxs-lookup"><span data-stu-id="b78f2-103">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="b78f2-104">С этим типом оснастки вы не выбирайте какие командлеты и поставщики, которые вы хотите зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="b78f2-104">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="b78f2-105">Для записи, можно выбрать, что регистрируется оснастки см. в разделе [написания пользовательских Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="b78f2-105">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="b78f2-106">Написание оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b78f2-106">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="b78f2-107">Добавьте атрибут RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="b78f2-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="b78f2-108">Создайте открытый класс, производный от [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) класса.</span><span class="sxs-lookup"><span data-stu-id="b78f2-108">Create a public class that derives from the [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="b78f2-109">В этом примере имя класса — «GetProcPSSnapIn01».</span><span class="sxs-lookup"><span data-stu-id="b78f2-109">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="b78f2-110">Добавьте, общедоступное свойство имя оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="b78f2-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="b78f2-111">При именовании оснасток, не используйте следующие символы: #.</span><span class="sxs-lookup"><span data-stu-id="b78f2-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="b78f2-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > ; ?</span><span class="sxs-lookup"><span data-stu-id="b78f2-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > ; ?</span></span> <span data-ttu-id="b78f2-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="b78f2-113">@ \` \*</span></span>

    <span data-ttu-id="b78f2-114">В этом примере в оснастке называется «GetProcPSSnapIn01».</span><span class="sxs-lookup"><span data-stu-id="b78f2-114">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="b78f2-115">Добавьте открытое свойство для поставщика оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="b78f2-115">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="b78f2-116">В этом примере поставщиком является корпорация «Майкрософт».</span><span class="sxs-lookup"><span data-stu-id="b78f2-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="b78f2-117">Добавьте открытое свойство для соответствующего ресурса поставщика оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="b78f2-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="b78f2-118">В этом примере ресурс поставщика является «GetProcPSSnapIn01 Майкрософт».</span><span class="sxs-lookup"><span data-stu-id="b78f2-118">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="b78f2-119">Добавьте открытое свойство для описания оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="b78f2-119">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="b78f2-120">В этом примере описание является «This is оснастка Windows PowerShell, которая регистрирует командлет get-proc».</span><span class="sxs-lookup"><span data-stu-id="b78f2-120">In this example, the description is "This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

7. <span data-ttu-id="b78f2-121">Добавьте открытое свойство для соответствующего ресурса описание оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="b78f2-121">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="b78f2-122">В этом примере ресурс поставщика является «GetProcPSSnapIn01, это оснастка Windows PowerShell, которая регистрирует командлет get-proc».</span><span class="sxs-lookup"><span data-stu-id="b78f2-122">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="b78f2-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b78f2-123">Example</span></span>

<span data-ttu-id="b78f2-124">В этом примере показано, как написать оснастки Windows PowerShell, который может использоваться для регистрации командлет Get-Proc в оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b78f2-124">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="b78f2-125">Имейте в виду, что в этом примере завершения сборки будет содержать только GetProcPSSnapIn01 оснастки класс и класс командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="b78f2-125">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the Get-Proc cmdlet class.</span></span>

```csharp
[RunInstaller(true)]
public class GetProcPSSnapIn01 : PSSnapIn
{
  /// <summary>
  /// Create an instance of the GetProcPSSnapIn01 class.
  /// </summary>
  public GetProcPSSnapIn01()
         : base()
  {
  }

  /// <summary>
  /// Specify the name of the PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "GetProcPSSnapIn01";
    }
  }

  /// <summary>
  /// Specify the vendor for the PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,VendorName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
      return "GetProcPSSnapIn01,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
      return "GetProcPSSnapIn01,This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="b78f2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b78f2-126">See Also</span></span>

[<span data-ttu-id="b78f2-127">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="b78f2-127">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="b78f2-128">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="b78f2-128">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)

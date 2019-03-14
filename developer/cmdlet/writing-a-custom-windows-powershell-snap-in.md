---
title: Написание пользовательских Windows PowerShell – – оснастка | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.assetid: 55c8b5cb-8ee2-4080-afc4-3f09c9f20128
caps.latest.revision: 6
ms.openlocfilehash: 4d50ef4dcd75d5c0ba802fbcfe2d7d1d7c954707
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795595"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="008a9-102">Написание пользовательской оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="008a9-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="008a9-103">В этом примере показано, как написать оснастка Windows PowerShell, которая регистрирует командлеты.</span><span class="sxs-lookup"><span data-stu-id="008a9-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="008a9-104">С этим типом оснастки укажите, какие командлеты, поставщики, типы или форматы для регистрации.</span><span class="sxs-lookup"><span data-stu-id="008a9-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="008a9-105">Дополнительные сведения о способах создания оснастка, которая регистрирует все командлеты и поставщики в сборке, см. в разделе [написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="008a9-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="008a9-106">Для записи оснастки Windows PowerShell, который регистрирует командлеты.</span><span class="sxs-lookup"><span data-stu-id="008a9-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="008a9-107">Добавьте атрибут RunInstallerAttribute.</span><span class="sxs-lookup"><span data-stu-id="008a9-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="008a9-108">Создайте открытый класс, производный от [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) класса.</span><span class="sxs-lookup"><span data-stu-id="008a9-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="008a9-109">В этом примере имя класса — «CustomPSSnapinTest».</span><span class="sxs-lookup"><span data-stu-id="008a9-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="008a9-110">Добавьте, общедоступное свойство имя оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="008a9-111">При именовании оснасток, не используйте следующие символы: #.</span><span class="sxs-lookup"><span data-stu-id="008a9-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="008a9-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span><span class="sxs-lookup"><span data-stu-id="008a9-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span></span> <span data-ttu-id="008a9-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="008a9-113">@ \` \*</span></span>

   <span data-ttu-id="008a9-114">В этом примере в оснастке называется «CustomPSSnapInTest».</span><span class="sxs-lookup"><span data-stu-id="008a9-114">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="008a9-115">Добавьте открытое свойство для поставщика оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-115">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="008a9-116">В этом примере поставщиком является корпорация «Майкрософт».</span><span class="sxs-lookup"><span data-stu-id="008a9-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="008a9-117">Добавьте открытое свойство для соответствующего ресурса поставщика оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="008a9-118">В этом примере ресурс поставщика является «CustomPSSnapInTest Майкрософт».</span><span class="sxs-lookup"><span data-stu-id="008a9-118">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="008a9-119">Добавьте открытое свойство для описания оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-119">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="008a9-120">В этом примере является Описание: «This is пользовательских Windows PowerShell – – оснастка, включает в себя тест-HelloWorld и командлеты CustomSnapinTest теста».</span><span class="sxs-lookup"><span data-stu-id="008a9-120">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

7. <span data-ttu-id="008a9-121">Добавьте открытое свойство для соответствующего ресурса описание оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-121">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="008a9-122">В этом примере ресурс поставщика является «CustomPSSnapInTest, это пользовательский Windows PowerShell – – оснастка, включает в себя командлеты HelloWorld тест и тест-CustomSnapinTest».</span><span class="sxs-lookup"><span data-stu-id="008a9-122">In this example, the vendor resource is "CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="008a9-123">Укажите командлеты, которые принадлежат пользовательские оснастки (необязательно) с помощью [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) класса.</span><span class="sxs-lookup"><span data-stu-id="008a9-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="008a9-124">Добавленные здесь сведения включают имя командлета, его тип .NET и имя файла справки командлета (формат имени файла справки, командлет должен быть name.dll help.xml).</span><span class="sxs-lookup"><span data-stu-id="008a9-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be name.dll-help.xml).</span></span>

   <span data-ttu-id="008a9-125">Этот пример добавляет тест-HelloWorld и TestCustomSnapinTest командлетов.</span><span class="sxs-lookup"><span data-stu-id="008a9-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="008a9-126">Укажите поставщики, которые принадлежат пользовательские оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="008a9-127">В этом примере не содержит все доступные поставщики.</span><span class="sxs-lookup"><span data-stu-id="008a9-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="008a9-128">Укажите типы, которые принадлежат пользовательские оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="008a9-129">В этом примере не содержит все типы.</span><span class="sxs-lookup"><span data-stu-id="008a9-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="008a9-130">Укажите форматы, которые принадлежат пользовательские оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="008a9-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="008a9-131">В этом примере не содержит все форматы.</span><span class="sxs-lookup"><span data-stu-id="008a9-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="008a9-132">Пример</span><span class="sxs-lookup"><span data-stu-id="008a9-132">Example</span></span>

<span data-ttu-id="008a9-133">В этом примере показано, как написать оснастки Custom Windows PowerShell, который может использоваться для регистрации HelloWorld тестирования и тестирования CustomSnapinTest командлетов.</span><span class="sxs-lookup"><span data-stu-id="008a9-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the Test-HelloWorld and Test-CustomSnapinTest cmdlets.</span></span> <span data-ttu-id="008a9-134">Имейте в виду, что в этом примере завершения сборки может содержать другие командлеты и поставщики, которые не регистрируются, эта оснастка.</span><span class="sxs-lookup"><span data-stu-id="008a9-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
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
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
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
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="008a9-135">Дополнительные сведения о регистрации оснастки см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) в [Руководство программиста Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="008a9-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="008a9-136">См. также</span><span class="sxs-lookup"><span data-stu-id="008a9-136">See Also</span></span>

[<span data-ttu-id="008a9-137">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="008a9-137">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="008a9-138">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="008a9-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)

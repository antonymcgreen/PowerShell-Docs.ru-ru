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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067031"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a>Написание пользовательской оснастки Windows PowerShell

В этом примере показано, как написать оснастка Windows PowerShell, которая регистрирует командлеты.

С этим типом оснастки укажите, какие командлеты, поставщики, типы или форматы для регистрации. Дополнительные сведения о способах создания оснастка, которая регистрирует все командлеты и поставщики в сборке, см. в разделе [написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md).

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a>Для записи оснастки Windows PowerShell, который регистрирует командлеты.

1. Добавьте атрибут RunInstallerAttribute.

2. Создайте открытый класс, производный от [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) класса.

   В этом примере имя класса — «CustomPSSnapinTest».

3. Добавьте, общедоступное свойство имя оснастки (обязательно). При именовании оснасток, не используйте следующие символы: #. , ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ? @ ` *

   В этом примере в оснастке называется «CustomPSSnapInTest».

4. Добавьте открытое свойство для поставщика оснастки (обязательно).

   В этом примере поставщиком является корпорация «Майкрософт».

5. Добавьте открытое свойство для соответствующего ресурса поставщика оснастки (необязательно).

   В этом примере ресурс поставщика является «CustomPSSnapInTest Майкрософт».

6. Добавьте открытое свойство для описания оснастки (обязательно).

   В этом примере является Описание: «This is пользовательских Windows PowerShell – – оснастка, включает в себя тест-HelloWorld и командлеты CustomSnapinTest теста».

7. Добавьте открытое свойство для соответствующего ресурса описание оснастки (необязательно).

   В этом примере ресурс поставщика является «CustomPSSnapInTest, это пользовательский Windows PowerShell – – оснастка, включает в себя командлеты HelloWorld тест и тест-CustomSnapinTest».

8. Укажите командлеты, которые принадлежат пользовательские оснастки (необязательно) с помощью [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) класса. Добавленные здесь сведения включают имя командлета, его тип .NET и имя файла справки командлета (формат имени файла справки, командлет должен быть name.dll help.xml).

   Этот пример добавляет тест-HelloWorld и TestCustomSnapinTest командлетов.

9. Укажите поставщики, которые принадлежат пользовательские оснастки (необязательно).

   В этом примере не содержит все доступные поставщики.

10. Укажите типы, которые принадлежат пользовательские оснастки (необязательно).

    В этом примере не содержит все типы.

11. Укажите форматы, которые принадлежат пользовательские оснастки (необязательно).

    В этом примере не содержит все форматы.

## <a name="example"></a>Пример

В этом примере показано, как написать оснастки Custom Windows PowerShell, который может использоваться для регистрации HelloWorld тестирования и тестирования CustomSnapinTest командлетов. Имейте в виду, что в этом примере завершения сборки может содержать другие командлеты и поставщики, которые не регистрируются, эта оснастка.

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

Дополнительные сведения о регистрации оснастки см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) в [Руководство программиста Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).

## <a name="see-also"></a>См. также

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

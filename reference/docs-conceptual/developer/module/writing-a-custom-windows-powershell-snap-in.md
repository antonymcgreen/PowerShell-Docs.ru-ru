---
title: Написание пользовательской оснастки Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: 9cf4499ec2992c6cfea83fc5d0bf51d0bbfaa96a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811633"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a>Написание пользовательской оснастки Windows PowerShell

В этом примере показано, как создать оснастку Windows PowerShell, которая регистрирует определенные командлеты.

С помощью этого типа оснастки вы указываете, какие командлеты, поставщики, типы или форматы нужно зарегистрировать. Дополнительные сведения о написании оснастки, которая регистрирует все командлеты и поставщики в сборке, см. [в разделе написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md).

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a>Для создания оснастки Windows PowerShell, которая регистрирует определенные командлеты.

1. Добавьте атрибут Рунинсталлераттрибуте.
2. Создайте открытый класс, производный от класса [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .

   В этом примере имя класса — «Кустомпсснапинтест».

3. Добавьте открытое свойство для имени оснастки (обязательно). При именовании оснасток не используйте следующие символы: `#` , `.` , `,` ,, `(` `)` , `{` , `}` , `[` , `]` , `&` , `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` `` ` `` ,,,,,,,,,,,,,,`*`

   В этом примере имя оснастки — «Кустомпсснапинтест».

4. Добавьте открытое свойство для поставщика оснастки (обязательно).

   В этом примере поставщиком является "Microsoft".

5. Добавьте открытое свойство для ресурса поставщика оснастки (необязательно).

   В этом примере ресурсом поставщика является "Кустомпсснапинтест, Microsoft".

6. Добавьте открытое свойство для описания оснастки (обязательно).

   В этом примере описание: "это пользовательская оснастка Windows PowerShell, которая включает `Test-HelloWorld` `Test-CustomSnapinTest` командлеты и".

7. Добавьте открытое свойство для ресурса описания оснастки (необязательно).

   В этом примере ресурсом поставщика является:

   > Кустомпсснапинтест, это пользовательская оснастка Windows PowerShell, которая включает командлеты Test-HelloWorld и Test-Кустомснапинтест.

8. Укажите командлеты, принадлежащие к пользовательской оснастке (необязательно), с помощью класса [System. Management. Automation. пространства. кмдлетконфигуратионентри](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) . Добавляемые здесь сведения включают имя командлета, его тип .NET и имя файла справки командлета (формат имени файла справки командлета должен быть `name.dll-help.xml` ).

   В этом примере добавляются командлеты Test-HelloWorld и Тесткустомснапинтест.

9. Укажите поставщиков, принадлежащих к пользовательской оснастке (необязательно).

   В этом примере не указаны поставщики.

10. Укажите типы, принадлежащие к пользовательской оснастке (необязательно).

    В этом примере не указаны типы.

11. Укажите форматы, принадлежащие к пользовательской оснастке (необязательно).

    В этом примере не указаны никакие форматы.

## <a name="example"></a>Пример

В этом примере показано, как написать пользовательскую оснастку Windows PowerShell, которая может использоваться для регистрации `Test-HelloWorld` `Test-CustomSnapinTest` командлетов и. Имейте в виду, что в этом примере полная сборка может содержать другие командлеты и поставщики, которые не будут зарегистрированы в этой оснастке.

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

Дополнительные сведения о регистрации оснасток см. в разделе [Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85)) [руководства программиста Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).

## <a name="see-also"></a>См. также:

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))

[Пакет SDK оболочки Windows PowerShell](../windows-powershell-reference.md)

---
ms.date: 09/13/2016
ms.topic: reference
title: Написание оснастки Windows PowerShell
description: Написание оснастки Windows PowerShell
ms.openlocfilehash: f658c2fa1211bfb77d2e8edd3999ce7f92df13bb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659443"
---
# <a name="writing-a-windows-powershell-snap-in"></a>Написание оснастки Windows PowerShell

В этом примере показано, как создать оснастку Windows PowerShell, которая может использоваться для регистрации всех командлетов и поставщиков Windows PowerShell в сборке.

При использовании этого типа оснастки не следует выбирать командлеты и поставщики, которые нужно зарегистрировать. Чтобы создать оснастку, которая позволяет выбрать регистрируемые объекты, см. раздел [написание пользовательской оснастки Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md).

### <a name="writing-a-windows-powershell-snap-in"></a>Написание оснастки Windows PowerShell

1. Добавьте атрибут Рунинсталлераттрибуте.

2. Создайте открытый класс, производный от класса [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) .

    В этом примере имя класса — «GetProcPSSnapIn01».

3. Добавьте открытое свойство для имени оснастки (обязательно). При именовании оснасток не используйте следующие символы: `#` , `.` , `,` ,, `(` `)` , `{` , `}` , `[` , `]` , `&` , `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` `` ` `` ,,,,,,,,,,,,,, `*`

    В этом примере имя оснастки — «GetProcPSSnapIn01».

4. Добавьте открытое свойство для поставщика оснастки (обязательно).

    В этом примере поставщиком является "Microsoft".

5. Добавьте открытое свойство для ресурса поставщика оснастки (необязательно).

    В этом примере ресурсом поставщика является "GetProcPSSnapIn01, Microsoft".

6. Добавьте открытое свойство для описания оснастки (обязательно).

    В этом примере описание: «это оснастка Windows PowerShell, которая регистрирует командлет Get-proc».

7. Добавьте открытое свойство для ресурса описания оснастки (необязательно).

    В этом примере ресурсом поставщика является «GetProcPSSnapIn01, это оснастка Windows PowerShell, которая регистрирует командлет Get-proc».

## <a name="example"></a>Пример

В этом примере показано, как создать оснастку Windows PowerShell, которая может использоваться для регистрации командлета Get-Proc в оболочке Windows PowerShell. Имейте в виду, что в этом примере полная сборка будет содержать только класс оснастки GetProcPSSnapIn01 и `Get-Proc` класс командлета.

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

## <a name="see-also"></a>См. также:

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))

[Пакет SDK Windows PowerShell](../windows-powershell-reference.md)

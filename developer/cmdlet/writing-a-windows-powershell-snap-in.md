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
ms.openlocfilehash: 0c99f4bcfe5e2d34d31714dc85a53b5e8abe0925
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057796"
---
# <a name="writing-a-windows-powershell-snap-in"></a>Написание оснастки Windows PowerShell

В этом примере показано, как написать оснастки Windows PowerShell, который может использоваться, чтобы зарегистрировать все командлеты и поставщики Windows PowerShell в сборке.

С этим типом оснастки вы не выбирайте какие командлеты и поставщики, которые вы хотите зарегистрировать. Для записи, можно выбрать, что регистрируется оснастки см. в разделе [написания пользовательских Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).

### <a name="writing-a-windows-powershell-snap-in"></a>Написание оснастки Windows PowerShell

1. Добавьте атрибут RunInstallerAttribute.

2. Создайте открытый класс, производный от [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) класса.

    В этом примере имя класса — «GetProcPSSnapIn01».

3. Добавьте, общедоступное свойство имя оснастки (обязательно). При именовании оснасток, не используйте следующие символы: #. , ( ) { } [ ] & - /\ $ ; : " ' \< > ; ? @ ` *

    В этом примере в оснастке называется «GetProcPSSnapIn01».

4. Добавьте открытое свойство для поставщика оснастки (обязательно).

    В этом примере поставщиком является корпорация «Майкрософт».

5. Добавьте открытое свойство для соответствующего ресурса поставщика оснастки (необязательно).

    В этом примере ресурс поставщика является «GetProcPSSnapIn01 Майкрософт».

6. Добавьте открытое свойство для описания оснастки (обязательно).

    В этом примере описание является «This is оснастка Windows PowerShell, которая регистрирует командлет get-proc».

7. Добавьте открытое свойство для соответствующего ресурса описание оснастки (необязательно).

    В этом примере ресурс поставщика является «GetProcPSSnapIn01, это оснастка Windows PowerShell, которая регистрирует командлет get-proc».

## <a name="example"></a>Пример

В этом примере показано, как написать оснастки Windows PowerShell, который может использоваться для регистрации командлет Get-Proc в оболочке Windows PowerShell. Имейте в виду, что в этом примере завершения сборки будет содержать только GetProcPSSnapIn01 оснастки класс и класс командлета Get-Proc.

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

## <a name="see-also"></a>См. также

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

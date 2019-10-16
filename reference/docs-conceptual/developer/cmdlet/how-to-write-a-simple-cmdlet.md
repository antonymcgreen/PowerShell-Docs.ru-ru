---
title: Написание простого командлета | Документация Майкрософт
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365473"
---
# <a name="how-to-write-a-cmdlet"></a>Написание командлета

В этой статье показано, как написать командлет. Командлет `Send-Greeting` принимает одно имя пользователя в качестве входных данных, а затем записывает приветствие для этого пользователя. Хотя командлет не выполняет много операций, в этом примере демонстрируются основные разделы командлета.

## <a name="steps-to-write-a-cmdlet"></a>Действия по написанию командлета

1. Чтобы объявить класс в качестве командлета, используйте атрибут **командлета** . Атрибут **командлета** задает глагол и существительное для имени командлета.

   Дополнительные сведения об атрибуте **командлета** см. в описании [объявления CmdletAttribute](cmdlet-attribute-declaration.md).

2. Укажите имя класса.

3. Укажите, что командлет является производным от любого из следующих классов:

   * [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet)
   * [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

4. Чтобы определить параметры для командлета, используйте атрибут **Parameter** . В этом случае указывается только один обязательный параметр.

   Дополнительные сведения об атрибуте **Parameter** см. в разделе [объявление параметераттрибуте](parameter-attribute-declaration.md).

5. Переопределите метод обработки ввода, обрабатывающий входные данные. В этом случае метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределен.

6. Чтобы написать приветствие, используйте метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).
   Приветствие отображается в следующем формате:

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a>Пример

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>См. также статью

[System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet)

[System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[Объявление CmdletAttribute](cmdlet-attribute-declaration.md)

[Объявление Параметераттрибуте](parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](writing-a-windows-powershell-cmdlet.md)
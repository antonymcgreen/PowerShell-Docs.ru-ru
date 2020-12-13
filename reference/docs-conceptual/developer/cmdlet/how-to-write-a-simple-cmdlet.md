---
ms.date: 01/15/2019
ms.topic: reference
title: Как написать простой командлет
description: Как написать простой командлет
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646501"
---
# <a name="how-to-write-a-cmdlet"></a>Написание командлета

В этой статье показано, как написать командлет. `Send-Greeting`Командлет принимает одно имя пользователя в качестве входных данных, а затем записывает приветствие этому пользователю. Хотя командлет не выполняет много операций, в этом примере демонстрируются основные разделы командлета.

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

## <a name="see-also"></a>См. также раздел

[System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet)

[System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[Объявление CmdletAttribute](cmdlet-attribute-declaration.md)

[Объявление Параметераттрибуте](parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](writing-a-windows-powershell-cmdlet.md)

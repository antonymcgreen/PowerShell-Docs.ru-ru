---
title: Как написать простой командлет | Документация Майкрософт
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251461"
---
# <a name="how-to-write-a-cmdlet"></a>Как написать командлет

В этой статье показано, как написать командлет. `Send-Greeting` Командлет принимает имя одного пользователя в качестве входных данных, а затем записывает приветствие этого пользователя. Несмотря на то, что командлет не выполняет много работы, в этом примере демонстрируются основные разделы командлета.

## <a name="steps-to-write-a-cmdlet"></a>Описывается, как создать командлет

1. Чтобы объявить класс как командлет, используйте **командлет** атрибута. **Командлет** атрибут задает глагол и существительное для имени командлета.

   Дополнительные сведения о **командлет** атрибут, см. в разделе [объявление CmdletAttribute](cmdlet-attribute-declaration.md).

2. Укажите имя класса.

3. Укажите, что командлет является производным от любого из следующих классов:

   * [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)
   * [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

4. Чтобы определить параметры для командлета, используйте **параметр** атрибута. В этом случае только один обязательный параметр указан.

   Дополнительные сведения о **параметр** атрибут, см. в разделе [ParameterAttribute объявление](parameter-attribute-declaration.md).

5. Переопределите метод, который обрабатывает входные данные обработки входных данных. В этом случае [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределяется метод.

6. Чтобы написать приветствие, используйте метод [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).
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

## <a name="see-also"></a>См. также:

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)

[System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[Объявление CmdletAttribute](cmdlet-attribute-declaration.md)

[Объявление ParameterAttribute](parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](writing-a-windows-powershell-cmdlet.md)
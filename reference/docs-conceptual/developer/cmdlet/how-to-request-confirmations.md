---
title: Как запросить подтверждения | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ebe928724f1b750afc11c1e3c1207375f4ec8e42
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784101"
---
# <a name="how-to-request-confirmations"></a>Как запросить подтверждение

В этом примере показано, как вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) для запроса подтверждения от пользователя до выполнения действия.

> [!IMPORTANT]
> Дополнительные сведения о том, как Windows PowerShell обрабатывает эти запросы, см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

## <a name="to-request-confirmation"></a>Запрос подтверждения

1. Убедитесь, что `SupportsShouldProcess` параметру атрибута командлет присвоено значение `true` . (Для функций это параметр атрибута CmdletBinding.)

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. Добавьте `Force` параметр в командлет, чтобы пользователь мог переопределить запрос на подтверждение.

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. Добавьте `if` инструкцию, которая использует возвращаемое значение метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , чтобы определить, вызывается ли метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) .

4. Добавьте второй `if` оператор, использующий возвращаемое значение метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) и значение `Force` параметра, чтобы определить, следует ли выполнять операцию.

## <a name="example"></a>Пример

В следующем примере кода методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызываются из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . Однако эти методы также можно вызывать из других методов обработки ввода.

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

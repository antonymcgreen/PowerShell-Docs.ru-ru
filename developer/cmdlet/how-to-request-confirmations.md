---
title: Как запросить подтверждения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f24f77d5-e224-4b62-b128-535e045d333e
caps.latest.revision: 9
ms.openlocfilehash: 19e96b612a8778d82cdbafb528a7ffeb01f15f99
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058833"
---
# <a name="how-to-request-confirmations"></a>Как запросить подтверждение

В этом примере показан способ вызова [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы для запроса подтверждения из пользователь, прежде чем произойдет.

> [!IMPORTANT]
> Дополнительные сведения о том, как Windows PowerShell обрабатывает эти запросы, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

## <a name="to-request-confirmation"></a>Чтобы запросить подтверждение

1. Убедитесь, что `SupportsShouldProcess` командлет атрибута установлено значение `true`. (Для функций это параметр атрибута CmdletBinding.)

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. Добавление `Force` параметра командлета, чтобы пользователь может отменить запрос на подтверждение.

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. Добавить `if` инструкцию, которая использует возвращаемое значение [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод на предмет [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызывается метод.

4. Добавьте второй `if` инструкцию, которая использует возвращаемое значение [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод и значения `Force` параметр, чтобы определить, следует ли операции выполнить.

## <a name="example"></a>Пример

В следующем примере кода [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы вызываются из в рамках переопределения из [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод. Тем не менее эти методы можно вызывать другие методы обработки входных данных.

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

---
ms.date: 09/13/2016
ms.topic: reference
title: Методы обработки входных данных командлета
description: Методы обработки входных данных командлета
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653393"
---
# <a name="cmdlet-input-processing-methods"></a>Методы обработки входных данных командлета

Командлеты должны переопределять один или несколько методов обработки ввода, описанных в этом разделе, для выполнения их работы.
Эти методы позволяют командлету выполнять операции предварительной обработки, обработки входных данных и последующей обработки.
Эти методы также позволяют прерывать обработку командлетов.
Более подробный пример использования этих методов см. в разделе Учебник по [селектстр](selectstr-tutorial.md).

## <a name="pre-processing-operations"></a>Операции предварительной обработки

Командлеты должны переопределять метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) для добавления любых операций предварительной обработки, допустимых для всех записей, которые будут обрабатываться этим командлетом позже.
Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).

В следующем коде показана реализация метода BeginProcessing.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>Операции обработки входных данных

Командлеты могут переопределять метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для обработки входных данных, отправляемых в командлет.
Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод для каждой входной записи, обрабатываемой командлетом.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).

В следующем коде показана реализация метода ProcessRecord.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>Операции, выполняемые после обработки

Командлеты должны переопределять метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) для добавления любых операций последующей обработки, допустимых для всех записей, обработанных командлетом.
Например, командлету может потребоваться очистить переменные объекта после завершения обработки.

Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.
Однако важно помнить, что среда выполнения PowerShell не будет вызывать метод EndProcessing, если посрединное значение командлета отменяется через входную обработку или если в какой-либо части командлета возникает неустранимая ошибка.
По этой причине командлет, требующий очистки объектов, должен реализовать полный шаблон [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения могла вызывать методы EndProcessing и [System. IDisposable. Dispose](/dotnet/api/System.IDisposable.Dispose) в конце обработки.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).

В следующем коде показана реализация метода EndProcessing.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>См. также:

[System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Руководство по SelectStr](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Пакет SDK Windows PowerShell](../windows-powershell-reference.md)

---
title: Методы обработки входных данных командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual methods (PowerShell SDK]
ms.assetid: b0bb8172-c9fa-454b-9f1b-57c3fe60671b
caps.latest.revision: 12
ms.openlocfilehash: a28c8d3df19bc72bf338d6abc4e02768c5097209
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369873"
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

[Руководство по Селектстр](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Пакет SDK оболочки Windows PowerShell](../windows-powershell-reference.md)

---
title: Методы обработки ввода, командлет | Документация Майкрософт
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
ms.sourcegitcommit: 00cf9a99972ce40db7c25b9a3fc6152dec6bddb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64670304"
---
# <a name="cmdlet-input-processing-methods"></a>Методы обработки входных данных командлета

Командлеты необходимо переопределить один или несколько методов, описанных в этом разделе для выполнения своей работы обработки ввода.
Эти методы позволяют выполнять операции предварительной обработки, обработки ввода и завершающей обработки командлета.
Эти методы позволяют для остановки обработки командлета.
Более подробный пример использования этих методов, см. в разделе [SelectStr руководстве](selectstr-tutorial.md).

## <a name="pre-processing-operations"></a>Перед обработкой операции

Командлеты должны переопределять [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод, чтобы добавить любой операции предварительно обработки, которые являются допустимыми для всех записей, которые будут обрабатываться позднее с помощью командлета.
Когда PowerShell обрабатывает конвейер команд, PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).

Следующий код показывает реализацию метода BeginProcessing.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>Операции обработки входных данных

Командлеты можно переопределить [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки входных данных, который отправляется в командлет.
Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод для каждой входной записи, который обрабатывается с помощью командлета.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).

Следующий код показывает реализацию метода ProcessRecord.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>После обработки операции

Командлеты должны переопределять [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод, чтобы добавить любые операции постобработки, которые являются допустимыми для всех записей, которые были обработаны с помощью командлета.
Например, командлет может потребоваться очистить объектные переменные после завершения обработки.

Когда PowerShell обрабатывает конвейер команд, PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.
Тем не менее важно помнить, что среда PowerShell не вызовет метод EndProcessing если командлет середине отменяется до его обработки ввода, или если происходит неустранимая ошибка в любой части командлета.
По этой причине следует реализовать полный командлет, который требует очистки объектов [System.IDisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, среда выполнения может вызывать оба EndProcessing и [ System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) методы в конце обработки.
Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).

Следующий код показывает реализацию метода EndProcessing.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Учебник SelectStr](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

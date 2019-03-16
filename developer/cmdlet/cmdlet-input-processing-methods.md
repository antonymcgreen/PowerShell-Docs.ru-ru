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
ms.openlocfilehash: 065214647dfa6d376b727930fe75140911095faf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059377"
---
# <a name="cmdlet-input-processing-methods"></a>Методы обработки входных данных командлета

Командлеты необходимо переопределить один или несколько методов, описанных в этом разделе для выполнения своей работы обработки ввода. Эти методы позволяют командлет для выполнения предварительной обработки операций, входной операций обработки и постобработки операций. Эти методы позволяют для остановки обработки командлета.

## <a name="pre-processing-tasks"></a>Задачи предварительной обработки

Командлеты должны переопределять [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод, чтобы добавить любой операции предварительно обработки, которые являются допустимыми для всех записей, которые будут обрабатываться позднее с помощью командлета. Когда Windows PowerShell обрабатывает конвейер команд, Windows PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере. Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).

Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the BeginProcessing template."
  WriteObject("This is a test of the BeginProcessing template.");
}
```

Более подробный пример использования [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md). В этом руководстве **выберите Str** командлет использует [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод для генерации регулярное выражение, которое будет использоваться для поиска записей обработки ввода.

## <a name="input-processing-tasks"></a>Входные данные задачи обработки

Командлеты можно переопределить [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод для обработки входных данных, который отправляется в командлет. Когда Windows PowerShell обрабатывает конвейер команд, этот метод вызывается в Windows PowerShell для каждой входной записи, который обрабатывается с помощью командлета. Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).

Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the ProcessRecord template."
  WriteObject("This is a test of the ProcessRecord template.");
}
```

Более подробный пример использования [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md).

## <a name="post-processing-tasks"></a>После обработки задач

Командлеты должны переопределять [System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) метод, чтобы добавить любые операции постобработки, которые являются допустимыми для всех записей, которые были обработаны с помощью командлета. Например, командлет может потребоваться очистить объектные переменные после завершения обработки.

Когда Windows PowerShell обрабатывает конвейер команд, Windows PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере. Тем не менее, важно помнить, что среда выполнения Windows PowerShell не вызовет [System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) метод, если командлет отменяется середине до его обработки ввода, или если завершающей в любой части командлета возникает ошибка. По этой причине следует реализовать полный командлет, который требует очистки объектов [System.IDisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, чтобы среда выполнения может вызвать оба [ System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) и [System.IDisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose) методы в конце обработки. Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).

Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the EndProcessing template."
  WriteObject("This is a test of the EndProcessing template.");
}
```

Более подробный пример использования [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md).

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)

[System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)

[System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

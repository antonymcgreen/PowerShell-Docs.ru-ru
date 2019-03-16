---
title: Как переопределить методы обработки ввода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: cfee55576518cf9ce38501192872ce94054f5213
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056402"
---
# <a name="how-to-override-input-processing-methods"></a>Как переопределить методы обработки входных данных

Эти примеры показывают, как перезаписать методы в командлет обработки ввода. Эти методы используются для выполнения следующих операций:

- [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод используется для выполнения одноразового запуска операций, которые являются допустимыми для всех объектов, обработанных с помощью командлета. Среда выполнения Windows PowerShell, этот метод вызывается только один раз.

- [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод используется для обработки объектов, переданных в командлет. Среда выполнения Windows PowerShell этот метод вызывается для каждого объекта, переданного в командлет.

- [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод используется для выполнения операций обработки одноразовый post. Среда выполнения Windows PowerShell, этот метод вызывается только один раз.

## <a name="to-override-the-beginprocessing-method"></a>Чтобы переопределить метод BeginProcessing

- Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.

Следующий класс печатает пример сообщения. Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.BeginProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a>Чтобы переопределить метод ProcessRecord

- Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.

Следующий класс печатает пример сообщения. Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a>Чтобы переопределить метод EndProcessing

- Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.

Следующий класс печатает образец. Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.EndProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

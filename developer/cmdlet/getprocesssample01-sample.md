---
title: Пример GetProcessSample01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b48bf80-cbf0-4cb1-8d5b-3b8d06196598
caps.latest.revision: 10
ms.openlocfilehash: 00190c7350cb0f1cfc5c389b56e48e9397480446
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859840"
---
# <a name="getprocesssample01-sample"></a>Пример командлета GetProcessSample01

В этом примере показано, как выполнить командлет, который извлекает процессы на локальном компьютере. Этот командлет представляет упрощенную версию `Get-Process` командлет, предоставляемый Windows PowerShell 2.0.

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>Как построить образец с помощью Visual Studio.

1. С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке GetProcessSample01. Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.

2. Дважды щелкните значок файла решения (SLN). Пример проекта откроется в Microsoft Visual Studio.

3. В **построения** меню, выберите **построить решение**.

  Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Откройте окно командной строки.

2. Перейдите в каталог, содержащий пример DLL-файла.

3. Выполнение программы installutil «GetProcessSample01.dll».

4. Запустите Windows PowerShell.

5. Выполните следующую команду, чтобы добавить оснастку в оболочку.

   `Add-PSSnapin GetProcPSSnapIn01`

6. Введите следующую команду, чтобы запустить командлет. `get-proc`

   `get-proc`

   Это пример выходных данных, полученный в результате следующие действия.

   ```output
   Id              Name            State      HasMoreData     Location             Command
   --              ----            -----      -----------     --------             -------
   1               26932870-d3b... NotStarted False                                 Write-Host "A f...

   ```

   ```powershell
   Set-Content $env:temp\test.txt "This is a test file"
   ```

   ```output
   A file was created in the TEMP directory
   ```

## <a name="requirements"></a>Требования

Этого образца необходима среда Windows PowerShell 1.0 или более поздней версии.

## <a name="demonstrates"></a>Демонстрация

В этом примере демонстрируется следующее.

- Создание простой пример командлета.

- Определение класса командлета с помощью атрибута командлет.

- Создание оснастки, работает с Windows PowerShell 1.0 и Windows PowerShell 2.0. В следующих примерах используйте модули вместо оснастки, поэтому им требуется Windows PowerShell 2.0.

## <a name="example"></a>Пример

В этом примере показано, как создать простой командлет и его оснастку.

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{

   #region GetProcCommand

   /// <summary>
   /// This class implements the Get-Proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes of the local computer.
      /// Then, the WriteObject method writes the associated processes
      /// to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
         // Retrieve the current processes.
         Process[] processes = Process.GetProcesses();

         // Write the processes to the pipeline to make them available
         // to the next cmdlet. The second argument (true) tells Windows
         // PowerShell to enumerate the array and to send one process
         // object at a time to the pipeline.
         WriteObject(processes, true);
      }

      #endregion Overrides

   } //GetProcCommand

   #endregion GetProcCommand

   #region PowerShell snap-in

   /// <summary>
   /// Create this sample as an PowerShell snap-in
   /// </summary>
   [RunInstaller(true)]
   public class GetProcPSSnapIn01 : PSSnapIn
   {
       /// <summary>
       /// Create an instance of the GetProcPSSnapIn01
       /// </summary>
       public GetProcPSSnapIn01()
           : base()
       {
       }

       /// <summary>
       /// Get a name for this PowerShell snap-in. This name will be used in registering
       /// this PowerShell snap-in.
       /// </summary>
       public override string Name
       {
           get
           {
               return "GetProcPSSnapIn01";
           }
       }

       /// <summary>
       /// Vendor information for this PowerShell snap-in.
       /// </summary>
       public override string Vendor
       {
           get
           {
               return "Microsoft";
           }
       }

       /// <summary>
       /// Gets resource information for vendor. This is a string of format:
       /// resourceBaseName,resourceName.
       /// </summary>
       public override string VendorResource
       {
           get
           {
               return "GetProcPSSnapIn01,Microsoft";
           }
       }

       /// <summary>
       /// Description of this PowerShell snap-in.
       /// </summary>
       public override string Description
       {
           get
           {
               return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
           }
       }
   }

   #endregion PowerShell snap-in
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
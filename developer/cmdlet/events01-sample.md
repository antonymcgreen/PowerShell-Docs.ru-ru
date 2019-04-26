---
title: Пример Events01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27d0ee5e-2589-4530-92ef-c09996b80994
caps.latest.revision: 10
ms.openlocfilehash: c9963819f1842d1245735dabc487babaa566c160
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068136"
---
# <a name="events01-sample"></a>Пример командлета Events01

В этом примере показано, как создать командлет, который позволяет пользователю регистрировать события, вызываемые с [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher). С помощью этого командлета пользователи могут регистрировать действие для выполнения при создании файла в конкретном каталоге. В этом примере является производным от [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) базового класса.

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>Как построить образец с помощью Visual Studio.

1. С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке Events01. Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01.

2. Дважды щелкните значок файла решения (SLN). Пример проекта откроется в Microsoft Visual Studio.

3. В **построения** меню, выберите **построить решение**.

    Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Создайте следующую папку модуля:

    `[user]/documents/windowspowershell/modules/events01`

2. Скопируйте файл библиотеки для примера в папку модуля.

3. Запустите Windows PowerShell.

4. Выполните следующую команду, чтобы загрузить командлет в Windows PowerShell:

    ```powershell
    import-module events01
    ```

5. Используйте командлет Register-FileSystemEvent для регистрации действия, которое будет записывать сообщения, при создании файла в каталоге TEMP.

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. Создайте файл в каталоге TEMP и обратите внимание на то, что действие выполняется (появляется сообщение).

Это пример выходных данных, которое следует за следующие действия.

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

В этом примере требуется Windows PowerShell 2.0.

## <a name="demonstrates"></a>Демонстрирует

В этом примере демонстрируется следующее.

- Как написать командлет для регистрации событий. Командлет является производным от [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) класс, который поддерживает параметры, общие для Register-* командлеты событий. Командлеты, которые являются производными от [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) только необходимо определить их определенными параметрами и переопределить `GetSourceObject` и `GetSourceObjectEventName` абстрактные методы.

## <a name="example"></a>Пример

В этом примере показано, как регистрировать события, вызванные [System.IO.FileSystemWatcher](https://msdn.microsoft.com/en-us/library/system.io.filesystemwatcher\(v=vs.110\).aspx).

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the MSDN documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
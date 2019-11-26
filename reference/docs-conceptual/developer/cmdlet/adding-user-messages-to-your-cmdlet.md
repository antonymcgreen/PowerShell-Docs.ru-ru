---
title: Добавление сообщений пользователя в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 9079f40e75dae86c22fd8b4f8a45d501c6125498
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416022"
---
# <a name="adding-user-messages-to-your-cmdlet"></a>Добавление пользовательских сообщений в командлет

Командлеты могут записывать сообщения нескольких типов, которые могут отображаться для пользователя средой выполнения Windows PowerShell. Эти сообщения включают следующие типы:

- Подробные сообщения, содержащие общие сведения о пользователях.

- Сообщения отладки, содержащие сведения об устранении неполадок.

- Предупреждающие сообщения, содержащие уведомление о том, что командлет собирается выполнить операцию, которая может привести к непредвиденным результатам.

- Сообщения отчета о состоянии, содержащие сведения о том, сколько работы командлета выполнила при выполнении операции, которая занимает много времени.

Количество сообщений, которые может записывать командлет, и тип сообщений, записываемых командлетом, не ограничены. Каждое сообщение записывается путем выполнения определенного вызова в методе обработки входных данных командлета.

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Любой командлет может записывать пользовательские уведомления из своих методов обработки входных данных. Таким образом, можно присвоить этому командлету имя, используя любую команду, которая указывает, какие изменения системы выполняет командлет. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Командлет «останавливает-proc» предназначен для изменения системы; Поэтому объявление [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) для класса .NET должно включать ключевое слово `SupportsShouldProcess` Attribute и иметь значение `true`.

Следующий код является определением для этого класса командлета-proc. Дополнительные сведения об этом определении см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

Командлет "останавливает-proc" определяет три параметра: `Name`, `Force`и `PassThru`. Дополнительные сведения об определении этих параметров см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

Ниже приведено объявление параметра для командлета "останавливает-proc".

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Командлет должен переопределять метод обработки ввода, чаще всего это будет [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). Этот командлет-Process переопределяет метод обработки ввода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . В этой реализации командлета "останавливает-proc" выполняются вызовы для записи подробных сообщений, сообщений отладки и предупреждающих сообщений.

> [!NOTE]
> Дополнительные сведения о том, как этот метод вызывает методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="writing-a-verbose-message"></a>Запись подробного сообщения

Метод [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) используется для записи общих сведений на уровне пользователя, не связанных с конкретными условиями ошибок. Затем системный администратор может использовать эти сведения для продолжения обработки других команд. Кроме того, любые сведения, написанные с помощью этого метода, должны быть локализованы по мере необходимости.

В следующем коде из командлета "останавливает-proc" показаны два вызова метода [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a>Запись сообщения об отладке

Метод [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) используется для записи отладочных сообщений, которые можно использовать для устранения неполадок в работе командлета. Вызов выполняется из метода обработки входных данных.

> [!NOTE]
> Windows PowerShell также определяет параметр `Debug`, который предоставляет как подробную, так и отладочную информацию. Если командлет поддерживает этот параметр, ему не нужно вызывать [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в том же коде, который вызывает [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).

В следующих двух разделах кода из командлета "Sample-proc" показаны вызовы метода [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

Это сообщение отладки записывается непосредственно перед вызовом [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

Это сообщение отладки записывается непосредственно перед вызовом [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

Windows PowerShell автоматически направляет все вызовы [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в инфраструктуру и командлеты трассировки. Это позволяет отслеживать вызовы методов для ведущего приложения, файла или отладчика без необходимости выполнять какие-либо дополнительные действия по разработке в командлете. Следующая запись командной строки реализует операцию трассировки.

**PS > Трассировка-выражение "Trace-proc-File proc. log-Command"**

## <a name="writing-a-warning-message"></a>Создание сообщения с предупреждением

Метод [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) используется для записи предупреждения о том, что командлет собирается выполнить операцию, которая может иметь непредвиденный результат, например перезапись файла, доступного только для чтения.

В следующем коде командлета "Sample-proc" показан вызов метода [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a>Запись сообщения о ходе выполнения

[System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) используется для записи сообщений о ходе выполнения, когда выполнение операций командлета занимает продолжительное время. Вызов [System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) передает объект [System. Management. Automation. Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) , который отправляется в приложение размещения для отрисовки пользователю.

> [!NOTE]
> Этот командлет «останавливает-proc» не включает вызов метода [System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

Следующий код является примером сообщения о ходе выполнения, написанного командлетом, который пытается скопировать элемент.

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a>Пример кода

Полный C# пример кода см. в разделе [StopProcessSample02 Sample](./stopprocesssample02-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке. Давайте протестируем пример командлета "останавливает-proc". Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Следующая запись командной строки используется для завершения процесса "Блокнот", предоставления подробных уведомлений и печати отладочной информации.

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

Отобразятся следующие выходные данные.

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a>См. также

[Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md)

[Создание командлета Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

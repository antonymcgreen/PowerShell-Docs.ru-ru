---
title: Добавление пользовательских сообщений командлета | Документация Майкрософт
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
ms.openlocfilehash: 1e048f6ae94ac226218c18c8f8f7590a4db26226
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733756"
---
# <a name="adding-user-messages-to-your-cmdlet"></a>Добавление пользовательских сообщений в командлет

Командлеты можно написать несколько типов сообщений, которые могут отображаться для пользователя средой выполнения Windows PowerShell. Эти сообщения включают следующие типы:

- Подробные сообщения, которые содержат общие сведения о пользователях.

- Отладка сообщения, содержащие сведения об устранении неполадок.

- Предупреждающие сообщения, содержащие уведомление, которое командлет собирается выполнить операцию, которая может иметь непредвиденные результаты.

- Отчет о ходе выполнения, что сообщения, содержащие сведения о том, какую работать командлет завершения при выполнении операции, которая занимает много времени.

Отсутствуют ограничения на количество сообщений, командлет может записывать или тип сообщений, которые записывает командлета. Каждое сообщение записывается из определенных вызовом в метод командлета обработки входных данных.

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Каких-либо командлета можно написать уведомления для пользователей из входного потока обработки методов. Таким образом как правило, можно назвать этот командлет, используя любой команды, которая указывает, какие изменения системы, командлет выполняет. Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Командлет Stop-Proc предназначен для изменения системы. Таким образом [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) объявление класса .NET должен включать `SupportsShouldProcess` атрибута ключевое слово и присвоить `true`.

Ниже приведено определение для этого класса командлет Stop-Proc. Дополнительные сведения о это определение, см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

Командлет Stop-Proc определяет три параметра: `Name`, `Force`, и `PassThru`. Дополнительные сведения об определении этих параметров см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

Ниже приведено объявление параметра для командлета Stop-Proc.

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

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

Командлет необходимо переопределить метод обработки входных данных, чаще всего она будет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). Этот командлет Stop-Proc переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод обработки ввода. В этой реализации командлет Stop-Proc вызовы выполняются для записи подробных сообщений, сообщения отладки и предупреждающие сообщения.

> [!NOTE]
> Дополнительные сведения о том, как этот метод вызывает [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="writing-a-verbose-message"></a>Запись подробных сообщений

[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метод используется для записи Общие сведения уровня пользователя, который не связан с условия возникновения данной ошибки. Системный администратор затем можно использовать эту информацию, чтобы продолжить обработку других команд. Кроме того вся информация, записываемая с помощью этого метода должно быть локализовано, при необходимости.

В следующем коде из этого командлета Stop-Proc показано два вызова [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метода из переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a>Запись сообщения отладки

[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метод используется для записи сообщений отладки, которые можно использовать для устранения неполадок в работе командлета. Вызов выполняется из метод обработки входных данных.

> [!NOTE]
> Windows PowerShell также определяет `Debug` параметр, который представляется как verbose и сведений об отладке. Если командлет поддерживает этот параметр, он не требуется вызывать [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в тот же код, который вызывает [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .

Следующих двух разделах кода из командлета Stop-Proc образец Показать вызовы [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метода из переопределение метода [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.

Это сообщение отладки записывается непосредственно перед [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывается.

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

Это сообщение отладки записывается непосредственно перед [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) вызывается.

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

Windows PowerShell автоматически направляет все [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) вызовы инфраструктура трассировки и командлеты. Это позволяет отследить ведущего приложения, в файл или отладчик не нужно прикладывать усилия дополнительной разработки в данном командлете вызовы методов. Параметр командной строки реализует операции трассировки.

**PS > выражение трассировки stop-proc-файл proc.log-команда stop-proc Блокнот**

## <a name="writing-a-warning-message"></a>Написание предупреждающее сообщение

[System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метод используется для записи предупреждения в случае, когда командлет собирается выполнить операцию, которую может иметь непредвиденный результат, например, перезапись файла только для чтения.

В следующем коде из командлета Stop-Proc примера показано вызов [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метода из переопределение метода [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.

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

[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) используется для записи сообщения о ходе выполнения при операции командлет занять продолжительное время. Вызов [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) передает [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) объект, который отправляется в приложение для подготовки к просмотру для пользователя.

> [!NOTE]
> Этот командлет Stop-Proc не включает вызов [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) метод.

Следующий код является примером сообщение о ходе выполнения, написанной командлет, который пытается выполнить копирование элемента.

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

Для полной C# пример кода, см. в разделе [пример StopProcessSample02](./stopprocesssample02-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирования

Windows PowerShell передает данные между командлетами, используя объекты .NET. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, его необходимо зарегистрировать с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке. Давайте протестируем командлет Stop-Proc образец. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Параметр командной строки использует многопроцессорную Stop для остановки процесса с именем «Блокнот», предоставляют подробные уведомления и печать отладочной информации.

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

Появляется следующий результат.

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

[Создать командлет, который изменяет системы](./creating-a-cmdlet-that-modifies-the-system.md)

[Как создать командлет Windows PowerShell](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

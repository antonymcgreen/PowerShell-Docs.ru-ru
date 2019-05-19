---
title: Создание командлета, который изменяет система | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- should process [PowerShell Programmer's Guide]
- should continue [PowerShell Programmer's Guide]
- user feedback [PowerShell Programmer's Guide]
- confirm impact [PowerShell Programmer's Guide]
ms.assetid: 59be4120-1700-4d92-a308-ef4a32ccf11a
caps.latest.revision: 8
ms.openlocfilehash: a4fa9ce52855928679a2425f24f2e49a68030c63
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854920"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>Создание командлета, который изменяет систему

Иногда командлета необходимо изменить состояние системы, а не только состояние среды выполнения Windows PowerShell. В этих случаях командлет должен позволять пользователю шанс подтвердить необходимость внесения изменений.

Для поддержки подтверждения командлета необходимо сделать две вещи.

- Объявите, что командлет поддерживает подтверждение при указании [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) атрибута, задав ключевое слово SupportsShouldProcess `true`.

- Вызовите [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) во время выполнения командлета (как показано в следующем примере).

Благодаря поддержке подтверждения, предоставляет командлет `Confirm` и `WhatIf` параметры, предоставляемые Windows PowerShell, а также соответствуют рекомендации по разработке для командлетов (Дополнительные сведения о рекомендации по разработке командлет, см. в разделе [ Рекомендации по разработке командлет](./cmdlet-development-guidelines.md).).

## <a name="changing-the-system"></a>Изменение системы

Операция «Изменение системы» относится к любой командлет, потенциально изменяет состояние системы за пределами Windows PowerShell. Например остановка процесса, включение или отключение учетной записи пользователя или добавление строк в таблицу базы данных являются все изменения в системе, которая должна быть подтверждена. Напротив операции, которые считывать данные, или установить временные подключения и не меняются системы обычно не требуют подтверждение. Подтверждения не требуется также для действий, эффект которого ограничено внутри среды выполнения Windows PowerShell, такие как `set-variable`. Командлеты, которые могут или не может внести постоянные изменения должны объявлять `SupportsShouldProcess` и вызвать [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) только в том случае, если они будут внесены постоянные изменения.

> [!NOTE]
> Подтверждение ShouldProcess применяется только к командлетам. Если команда или сценарий изменяет состояние системы путем прямого вызова методов .NET или свойства, или вызывающий приложениями за пределы Windows PowerShell, эта форма подтверждения будет недоступен.

## <a name="the-stopproc-cmdlet"></a>Командлет StopProc

В этом разделе описывается командлет Stop-Proc, который пытается остановить процессы, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Так как вы записываете командлета для изменения системы, его имя должно соответствующим образом. Этот командлет останавливает системные процессы, чтобы имя команды, выбираем «Stop», определяемый [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) класс с существительным «Proc», чтобы указать, что командлет останавливает процессы. Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведен в определении класса для этого командлета Stop-Proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

Имейте в виду, что в [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) объявление, `SupportsShouldProcess` атрибут ключевого слова задано `true` для включения командлет, чтобы выполнять вызовы [ System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue). Без этого набора ключевое слово `Confirm` и `WhatIf` параметры не будут доступны пользователю.

### <a name="extremely-destructive-actions"></a>Очень разрушительные действия

Некоторые операции являются очень уничтожения данных, например переформатирования active жесткого диска. В этих случаях следует установить командлет `ConfirmImpact`  =  `ConfirmImpact.High` при объявлении [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) атрибута. Этот параметр заставляет командлет для запроса подтверждения пользователя, даже в том случае, если пользователь не указал `Confirm` параметра. Тем не менее, разработчикам командлетов следует избегать чрезмерное `ConfirmImpact` для операций, которые являются просто потенциально необратимыми, например, удаление учетной записи пользователя. Помните, что если `ConfirmImpact` присваивается [System.Management.Automation.Confirmimpact.High](/dotnet/api/System.Management.Automation.ConfirmImpact.High).

Аналогично некоторые операции вряд ли уничтожения данных, несмотря на то, что они в теории изменяют состояние системы за пределами Windows PowerShell. Можно задать такие командлеты `ConfirmImpact` для [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0). Эта конструкция запросы подтверждения, где пользователю поступает запрос на подтверждение операции только влияние medium и значительное влияние.

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

В этом разделе описывается, как задать параметры командлета, включая те, которые необходимы для поддержки системы изменения. См. в разделе [Добавление параметров командной строки этого процесса входа](./adding-parameters-that-process-command-line-input.md) Общие сведения об определении параметров.

Командлет Stop-Proc определяет три параметра: `Name`, `Force`, и `PassThru`.

`Name` Параметр соответствует параметру `Name` свойства входного объекта процесса. Имейте в виду, что `Name` параметр в этом образце обязателен, так как командлет завершится ошибкой, если он не имеет именованный процесс для остановки.

`Force` Параметр позволяет переопределить вызовы [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue). На самом деле, любой командлет, который вызывает [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) должны иметь `Force` параметр, чтобы при `Force` указан, командлет пропускает вызов [ System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , после чего с операцией. Имейте в виду, что это не влияет на вызовы [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).

`PassThru` Параметр позволяет пользователю указать, командлет прошло ли объект вывода через конвейер, в этом случае после остановки процесса. Имейте в виду, что этот параметр привязан к командлету сам вместо свойства входного объекта.

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

Командлет необходимо переопределить метод обработки входных данных. В следующем коде показано [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределение, используемых в командлет Stop-Proc образец. Для каждого запроса имя процесса, этот метод гарантирует, что процесс не специального процесса, пытается остановить процесс, а затем отправляет выходного объекта, если `PassThru` указан параметр.

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a>Вызов метода ShouldProcess

Необходимо вызвать метод командлета обработки ввода [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод для подтверждения выполнения операции, прежде чем в рабочее состояние вносится изменение (например, удаление файлов) системы. Это позволяет среде выполнения Windows PowerShell для предоставления правильного поведения «WhatIf» и «Подтвердить», в оболочке.

> [!NOTE]
> Если командлет определяет, что он поддерживает должен обработать и не может обеспечить [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызова, пользователь может изменять система неожиданно.

Вызов [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) отправляет имя ресурса, необходимо изменить на пользователя, в среде выполнения Windows PowerShell, принимая во внимание любые параметры командной строки или привилегированные переменные При определении, что должно быть отображено пользователю.

В следующем примере показано вызов [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) из переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в примере метода Командлет Stop-Proc.

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>Вызов метода ShouldContinue

Вызов [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод отправляет сообщение-получателя для пользователя. Этот вызов выполняется после вызова [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) возвращает `true` и если `Force` параметра не было задано значение `true`. Затем пользователь может указать отзыв, чтобы сказать, следует ли продолжить операцию. В командлет вызывается [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) как дополнительную проверку для изменения потенциально опасных системы или если вы хотите предоставить пользователю Да для все и нет все параметры.

В следующем примере показано вызов [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в примере метода Командлет Stop-Proc.

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a>Остановка обработки ввода

Метод командлета, который вносит изменения системы обработки входных данных необходимо указать способ остановки обработки входных данных. В случае этот командлет Stop-Proc вызов выполняется из [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод [System.Diagnostics.Process.Kill*](/dotnet/api/System.Diagnostics.Process.Kill) метод. Так как `PassThru` параметр имеет значение `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) также вызывает [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки объект процесса в конвейер.

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример StopProcessSample01](./stopprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает данные между командлетами, используя объекты .net. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, его необходимо зарегистрировать с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке. Ниже приведены несколько тестов, которые проверяют командлет Stop-Proc. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Запустите Windows PowerShell и используйте командлет Stop-Proc для остановки обработки, как показано ниже. Так как командлет задает `Name` параметр как обязательные, командлет запросы для параметра.

    ```powershell
    PS> stop-proc
    ```

Появляется следующий результат.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- Теперь давайте используем командлет для остановки процесса с именем «Блокнот». Командлет запрашивает подтверждение действия.

    ```powershell
    PS> stop-proc -Name notepad
    ```

Появляется следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Используйте Stop-Proc, как показано для остановки критических процесса с именем «WINLOGON». Вы являетесь запрос и получает предупреждение о выполнении этого действия, так как он вызовет перезагрузку операционной системы.

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

Появляется следующий результат.

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- Давайте теперь попробуйте остановить процесс WINLOGON без получения предупреждения. Имейте в виду, что эта запись команды использует `Force` параметр можно переопределить предупреждение.

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

Появляется следующий результат.

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также

[Добавление параметров, которые обрабатывают данные в командной строке](./adding-parameters-that-process-command-line-input.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
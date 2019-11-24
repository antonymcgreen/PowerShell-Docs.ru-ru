---
title: Создание командлета, изменяющего систему | Документация Майкрософт
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
ms.openlocfilehash: 8a65915b88a04e36e773853b903528a65fe11e99
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365763"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>Создание командлета, который изменяет систему

Иногда командлет должен изменить состояние выполнения системы, а не только состояние среды выполнения Windows PowerShell. В таких случаях командлет позволяет пользователю проверить, вносить ли изменения.

Для поддержки подтверждения командлет должен выполнить два действия.

- Объявите, что командлет поддерживает подтверждение при указании атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , установив для ключевого слова SupportsShouldProcess значение `true`.

- Вызовите [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) во время выполнения командлета (как показано в следующем примере).

При поддержке подтверждения командлет предоставляет параметры `Confirm` и `WhatIf`, предоставляемые Windows PowerShell, а также рекомендации по разработке для командлетов (Дополнительные сведения о рекомендациях по разработке командлетов см. в разделе [рекомендации по разработке командлетов](./cmdlet-development-guidelines.md)).

## <a name="changing-the-system"></a>Изменение системы

Действие «изменение системы» относится к любому командлету, который потенциально изменяет состояние системы за пределами Windows PowerShell. Например, остановка процесса, включение или отключение учетной записи пользователя или добавление строки в таблицу базы данных — это все изменения в системе, которые должны быть подтверждены. В отличие от этого, операции, считывающие данные или устанавливающие временные подключения, не изменяют систему и, как правило, не нуждаются в подтверждении. Подтверждение также не требуется для действий, воздействие которых ограничено внутри среды выполнения Windows PowerShell, например `set-variable`. Командлеты, которые могут или не могут вносить постоянные изменения, должны объявлять `SupportsShouldProcess` и вызывать [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , только если они собирается внести постоянные изменения.

> [!NOTE]
> Подтверждение ShouldProcess применяется только к командлетам. Если команда или сценарий изменяет состояние выполнения системы путем непосредственного вызова методов или свойств .NET или путем вызова приложений за пределами Windows PowerShell, такая форма подтверждения будет недоступна.

## <a name="the-stopproc-cmdlet"></a>Командлет Стоппрок

В этом разделе описывается командлет-proc, который пытается прерывать процессы, полученные с помощью командлета Get-proc (описывается в статье [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена. Этот командлет останавливает системные процессы, поэтому выбранное здесь имя команды — Stop, определенное классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) с существительным «proc», которое указывает, что командлет останавливает процессы. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение класса для этого командлета «останавливает-proc».

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

Учтите, что в объявлении [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) ключевое слово `SupportsShouldProcess` Attribute имеет значение `true`, чтобы позволить командлету вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue). Если это ключевое слово не задано, параметры `Confirm` и `WhatIf` не будут доступны пользователю.

### <a name="extremely-destructive-actions"></a>Чрезвычайно разрушительные действия

Некоторые операции являются чрезвычайно разрушительными, например переформатирование активного раздела жесткого диска. В этих случаях командлет должен задать `ConfirmImpact` = `ConfirmImpact.High` при объявлении атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) . Этот параметр заставляет командлет запрашивать подтверждение пользователя даже в том случае, если пользователь не указал параметр `Confirm`. Однако разработчикам командлетов следует избегать использования `ConfirmImpact` для операций, которые являются просто разрушительными, например удаление учетной записи пользователя. Помните, что если `ConfirmImpact` имеет значение [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.

Аналогично, некоторые операции вряд ли будут разрушительными, хотя они и теоретически изменяют состояние выполнения системы за пределами Windows PowerShell. Такие командлеты могут устанавливать `ConfirmImpact` в значение [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0). Это позволит обходить запросы на подтверждение, когда пользователь попросит подтвердить только средние и значительные последствия.

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

В этом разделе описывается, как определить параметры командлета, включая те, которые необходимы для поддержки изменения системы. Общие сведения об определении параметров см. [в разделе Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md) .

Командлет "останавливает-proc" определяет три параметра: `Name`, `Force`и `PassThru`.

Параметр `Name` соответствует свойству `Name` для входного объекта обработки. Имейте в виду, что параметр `Name` в этом образце является обязательным, так как командлет завершится ошибкой, если у него нет именованного процесса для его завершения.

Параметр `Force` позволяет пользователю переопределить вызовы метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue). Фактически, любой командлет, вызывающий [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , должен иметь параметр `Force`, чтобы при указании `Force` командлет пропускает вызов метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) и продолжает операцию. Имейте в виду, что это не влияет на вызовы метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).

Параметр `PassThru` позволяет пользователю указать, передает ли командлет выходной объект через конвейер, в данном случае после остановки процесса. Имейте в виду, что этот параметр привязан к самому командлету, а не к свойству входного объекта.

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

Командлет должен переопределять метод обработки ввода. В следующем коде показано переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , используемое в командлете-proc. Для каждого запрошенного имени процесса этот метод гарантирует, что процесс не является специальным процессом, пытается прерывать процесс, а затем отправляет выходной объект, если указан параметр `PassThru`.

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

Метод обработки входных данных командлета должен вызвать метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , чтобы подтвердить выполнение операции перед изменением (например, удаление файлов), в состояние выполнения системы. Это позволяет среде выполнения Windows PowerShell предоставить правильные правила "WhatIf" и "Confirm" в оболочке.

> [!NOTE]
> Если командлет сообщает, что он поддерживает, и не может выполнить вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , пользователь может неожиданно изменить систему.

Вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные в определении того, что должно отображаться пользователю.

В следующем примере показан вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете-proc.

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>Вызов метода ShouldContinue

Вызов метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) отправляет пользователю дополнительное сообщение. Этот вызов выполняется после вызова метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , возвращающего `true` и если для параметра `Force` не задано значение `true`. Пользователь может предоставить отзыв, чтобы сказать, следует ли продолжать операцию. Командлет вызывает [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) в качестве дополнительной проверки потенциально опасных изменений системы или для предоставления пользователю параметров «Да» и «нет».

В следующем примере показан вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете-proc.

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

Метод обработки входных данных командлета, который вносит изменения в систему, должен обеспечить способ остановки обработки входных данных. В случае с этим командлетом остановить-proc вызывается метод System. [Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метода System [. Diagnostics. Process. Kill *](/dotnet/api/System.Diagnostics.Process.Kill) . Поскольку параметр `PassThru` имеет значение `true`, [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) также вызывает [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки объекта процесса в конвейер.

## <a name="code-sample"></a>Пример кода

Полный C# пример кода см. в разделе [StopProcessSample01 Sample](./stopprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке. Ниже приведено несколько тестов, которые проверяют командлет «прекращать-proc». Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Запустите Windows PowerShell и используйте командлет "останавливает-обработать", чтобы прерывать обработку, как показано ниже. Поскольку командлет задает `Name` параметр как обязательный, командлет запрашивает параметр.

    ```powershell
    PS> stop-proc
    ```

Отобразятся следующие выходные данные.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- Теперь давайте воспользуемся командлетом, чтобы прерывать процесс с именем «Блокнот». Командлет предложит подтвердить действие.

    ```powershell
    PS> stop-proc -Name notepad
    ```

Отобразятся следующие выходные данные.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Чтобы прерывать критически важный процесс с именем "WINLOGON", используйте процедуру "останавливает-обработать". Появится запрос и будет выведено предупреждение о выполнении этого действия, так как это приведет к перезагрузке операционной системы.

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

Отобразятся следующие выходные данные.

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- Теперь попробуем прерывать процесс WINLOGON без предупреждения. Имейте в виду, что эта запись команды использует параметр `Force` для переопределения предупреждения.

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

Отобразятся следующие выходные данные.

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также:

[Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
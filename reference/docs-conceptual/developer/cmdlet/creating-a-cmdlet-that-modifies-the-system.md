---
ms.date: 09/13/2016
ms.topic: reference
title: Создание командлета, который изменяет систему
description: Создание командлета, который изменяет систему
ms.openlocfilehash: 757f2c97bb4b5dcf2fb633cd35fe52bc5f6c5cf9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355550"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>Создание командлета, который изменяет систему

Иногда командлет должен изменить состояние выполнения системы, а не только состояние среды выполнения Windows PowerShell. В таких случаях командлет позволяет пользователю проверить, вносить ли изменения.

Для поддержки подтверждения командлет должен выполнить два действия.

- Объявите, что командлет поддерживает подтверждение при указании атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , установив для ключевого слова SupportsShouldProcess значение `true` .

- Вызовите [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) во время выполнения командлета (как показано в следующем примере).

При поддержке подтверждения командлет предоставляет `Confirm` `WhatIf` Параметры и, предоставляемые Windows PowerShell, а также рекомендации по разработке для командлетов (Дополнительные сведения о рекомендациях по разработке командлетов см. в разделе [рекомендации по разработке командлетов](./cmdlet-development-guidelines.md)).

## <a name="changing-the-system"></a>Изменение системы

Действие «изменение системы» относится к любому командлету, который потенциально изменяет состояние системы за пределами Windows PowerShell. Например, остановка процесса, включение или отключение учетной записи пользователя или добавление строки в таблицу базы данных — это все изменения в системе, которые должны быть подтверждены.
В отличие от этого, операции, считывающие данные или устанавливающие временные подключения, не изменяют систему и, как правило, не нуждаются в подтверждении. Подтверждение также не требуется для действий, воздействие которых ограничено внутри среды выполнения Windows PowerShell, например `set-variable` . Командлеты, которые могут или не могут вносить постоянные изменения, должны объявлять `SupportsShouldProcess` и вызывать [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) только в том случае, если они собирается внести постоянные изменения.

> [!NOTE]
> Подтверждение ShouldProcess применяется только к командлетам. Если команда или сценарий изменяет состояние выполнения системы путем непосредственного вызова методов или свойств .NET или путем вызова приложений за пределами Windows PowerShell, такая форма подтверждения будет недоступна.

## <a name="the-stopproc-cmdlet"></a>Командлет Стоппрок

В этом разделе описывается командлет Stop-Proc, который пытается прерывать процессы, полученные с помощью командлета Get-Proc (описывается в статье [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена. Этот командлет останавливает системные процессы, поэтому выбранное здесь имя команды — Stop, определенное классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) с существительным «proc», которое указывает, что командлет останавливает процессы. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение класса для этого командлета Stop-Proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

Имейте в виду, что в объявлении [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) `SupportsShouldProcess` ключевое слово Attribute имеет значение, `true` чтобы позволить командлету вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).
Если это ключевое слово не задано, `Confirm` `WhatIf` Параметры и не будут доступны пользователю.

### <a name="extremely-destructive-actions"></a>Чрезвычайно разрушительные действия

Некоторые операции являются чрезвычайно разрушительными, например переформатирование активного раздела жесткого диска. В этих случаях командлет должен быть задан `ConfirmImpact`  =  `ConfirmImpact.High` при объявлении атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) . Этот параметр заставляет командлет запрашивать подтверждение пользователя даже в том случае, если пользователь не указал `Confirm` параметр. Однако разработчики командлетов должны избегать использования `ConfirmImpact` для операций, которые просто являются обратимыми, например для удаления учетной записи пользователя. Помните, что если для задано `ConfirmImpact` значение [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **High**.

Аналогично, некоторые операции вряд ли будут разрушительными, хотя они и теоретически изменяют состояние выполнения системы за пределами Windows PowerShell. Такие командлеты могут иметь значение `ConfirmImpact` [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact).
Это позволит обходить запросы на подтверждение, когда пользователь попросит подтвердить только средние и значительные последствия.

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

В этом разделе описывается, как определить параметры командлета, включая те, которые необходимы для поддержки изменения системы. Общие сведения об определении параметров см. [в разделе Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md) .

Командлет Stop-Proc определяет три параметра: `Name` , `Force` и `PassThru` .

`Name`Параметр соответствует `Name` свойству входного объекта процесса. Имейте в виду, что `Name` параметр в этом образце является обязательным, так как командлет завершится ошибкой, если у него нет именованного процесса для его завершения.

`Force`Параметр позволяет пользователю переопределить вызовы метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).
Фактически, любой командлет, вызывающий [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , должен иметь `Force` параметр, чтобы при `Force` указании командлет пропустить вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) и продолжить операцию. Имейте в виду, что это не влияет на вызовы метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).

`PassThru`Параметр позволяет пользователю указать, передает ли командлет выходной объект через конвейер, в данном случае после остановки процесса. Имейте в виду, что этот параметр привязан к самому командлету, а не к свойству входного объекта.

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

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Командлет должен переопределять метод обработки ввода. В следующем коде показано переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , используемое в командлете Sample Stop-Proc. Для каждого запрошенного имени процесса этот метод гарантирует, что процесс не является специальным процессом, пытается прерывать процесс, а затем отправляет выходной объект, если `PassThru` указан параметр.

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

В следующем примере показан вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) из переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете Sample Stop-Proc.

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>Вызов метода ShouldContinue

Вызов метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) отправляет пользователю дополнительное сообщение. Этот вызов выполняется после вызова метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `true` и если `Force` параметру не было присвоено значение `true` . Пользователь может предоставить отзыв, чтобы сказать, следует ли продолжать операцию. Командлет вызывает [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) в качестве дополнительной проверки потенциально опасных изменений системы или для предоставления пользователю параметров «Да» и «нет».

В следующем примере показан вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете Sample Stop-Proc.

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

Метод обработки входных данных командлета, который вносит изменения в систему, должен обеспечить способ остановки обработки входных данных. В случае использования этого командлета Stop-Proc выполняется вызов метода [System. Management. Automation. командлета](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [System. Diagnostics. Process. Kill *](/dotnet/api/System.Diagnostics.Process.Kill) . Поскольку `PassThru` параметр имеет значение `true` , [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) также вызывает [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки объекта процесса в конвейер.

## <a name="code-sample"></a>Образец кода

Полный пример кода на C# см. в разделе [StopProcessSample01 Sample](./stopprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке. Ниже приведены несколько тестов, тестирующих командлет Stop-Proc. Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Запустите Windows PowerShell и используйте командлет Stop-Proc, чтобы прерывать обработку, как показано ниже. Поскольку командлет задает `Name` параметр как обязательный, командлет запрашивает параметр.

    ```powershell
    PS> stop-proc
    ```

    Появится следующий результат.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- Теперь давайте воспользуемся командлетом, чтобы прерывать процесс с именем «Блокнот». Командлет предложит подтвердить действие.

    ```powershell
    PS> stop-proc -Name notepad
    ```

    Появится следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Используйте Stop-Proc, как показано ниже, чтобы прерывать критический процесс с именем "WINLOGON". Появится запрос и будет выведено предупреждение о выполнении этого действия, так как это приведет к перезагрузке операционной системы.

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    Появится следующий результат.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- Теперь попробуем прерывать процесс WINLOGON без предупреждения. Имейте в виду, что эта запись команды использует `Force` параметр для переопределения предупреждения.

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    Появится следующий результат.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также:

[Добавление параметров, обрабатывающих Command-Line входе](./adding-parameters-that-process-command-line-input.md)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)

---
title: Создание командлета, изменяющего систему | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- should process [PowerShell Programmer's Guide]
- should continue [PowerShell Programmer's Guide]
- user feedback [PowerShell Programmer's Guide]
- confirm impact [PowerShell Programmer's Guide]
ms.openlocfilehash: 03ffe0c9c02dcdeb2dd24f81014b2013ae169aa4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782180"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="e75c0-102">Создание командлета, который изменяет систему</span><span class="sxs-lookup"><span data-stu-id="e75c0-102">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="e75c0-103">Иногда командлет должен изменить состояние выполнения системы, а не только состояние среды выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e75c0-103">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="e75c0-104">В таких случаях командлет позволяет пользователю проверить, вносить ли изменения.</span><span class="sxs-lookup"><span data-stu-id="e75c0-104">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="e75c0-105">Для поддержки подтверждения командлет должен выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="e75c0-105">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="e75c0-106">Объявите, что командлет поддерживает подтверждение при указании атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , установив для ключевого слова SupportsShouldProcess значение `true` .</span><span class="sxs-lookup"><span data-stu-id="e75c0-106">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="e75c0-107">Вызовите [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) во время выполнения командлета (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="e75c0-107">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="e75c0-108">При поддержке подтверждения командлет предоставляет `Confirm` `WhatIf` Параметры и, предоставляемые Windows PowerShell, а также рекомендации по разработке для командлетов (Дополнительные сведения о рекомендациях по разработке командлетов см. в разделе [рекомендации по разработке командлетов](./cmdlet-development-guidelines.md)).</span><span class="sxs-lookup"><span data-stu-id="e75c0-108">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="e75c0-109">Изменение системы</span><span class="sxs-lookup"><span data-stu-id="e75c0-109">Changing the System</span></span>

<span data-ttu-id="e75c0-110">Действие «изменение системы» относится к любому командлету, который потенциально изменяет состояние системы за пределами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e75c0-110">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="e75c0-111">Например, остановка процесса, включение или отключение учетной записи пользователя или добавление строки в таблицу базы данных — это все изменения в системе, которые должны быть подтверждены.</span><span class="sxs-lookup"><span data-stu-id="e75c0-111">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span> <span data-ttu-id="e75c0-112">В отличие от этого, операции, считывающие данные или устанавливающие временные подключения, не изменяют систему и, как правило, не нуждаются в подтверждении.</span><span class="sxs-lookup"><span data-stu-id="e75c0-112">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="e75c0-113">Подтверждение также не требуется для действий, воздействие которых ограничено внутри среды выполнения Windows PowerShell, например `set-variable` .</span><span class="sxs-lookup"><span data-stu-id="e75c0-113">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="e75c0-114">Командлеты, которые могут или не могут вносить постоянные изменения, должны объявлять `SupportsShouldProcess` и вызывать [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) только в том случае, если они собирается внести постоянные изменения.</span><span class="sxs-lookup"><span data-stu-id="e75c0-114">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c0-115">Подтверждение ShouldProcess применяется только к командлетам.</span><span class="sxs-lookup"><span data-stu-id="e75c0-115">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="e75c0-116">Если команда или сценарий изменяет состояние выполнения системы путем непосредственного вызова методов или свойств .NET или путем вызова приложений за пределами Windows PowerShell, такая форма подтверждения будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="e75c0-116">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="e75c0-117">Командлет Стоппрок</span><span class="sxs-lookup"><span data-stu-id="e75c0-117">The StopProc Cmdlet</span></span>

<span data-ttu-id="e75c0-118">В этом разделе описывается командлет-proc, который пытается прерывать процессы, полученные с помощью командлета Get-proc (описывается в статье [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="e75c0-118">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="e75c0-119">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="e75c0-119">Defining the Cmdlet</span></span>

<span data-ttu-id="e75c0-120">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="e75c0-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="e75c0-121">Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена.</span><span class="sxs-lookup"><span data-stu-id="e75c0-121">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="e75c0-122">Этот командлет останавливает системные процессы, поэтому выбранное здесь имя команды — Stop, определенное классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) с существительным «proc», которое указывает, что командлет останавливает процессы.</span><span class="sxs-lookup"><span data-stu-id="e75c0-122">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="e75c0-123">Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="e75c0-123">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e75c0-124">Ниже приведено определение класса для этого командлета «останавливает-proc».</span><span class="sxs-lookup"><span data-stu-id="e75c0-124">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="e75c0-125">Имейте в виду, что в объявлении [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) `SupportsShouldProcess` ключевое слово Attribute имеет значение, `true` чтобы позволить командлету вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="e75c0-125">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="e75c0-126">Если это ключевое слово не задано, `Confirm` `WhatIf` Параметры и не будут доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="e75c0-126">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="e75c0-127">Чрезвычайно разрушительные действия</span><span class="sxs-lookup"><span data-stu-id="e75c0-127">Extremely Destructive Actions</span></span>

<span data-ttu-id="e75c0-128">Некоторые операции являются чрезвычайно разрушительными, например переформатирование активного раздела жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="e75c0-128">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="e75c0-129">В этих случаях командлет должен быть задан `ConfirmImpact`  =  `ConfirmImpact.High` при объявлении атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e75c0-129">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="e75c0-130">Этот параметр заставляет командлет запрашивать подтверждение пользователя даже в том случае, если пользователь не указал `Confirm` параметр.</span><span class="sxs-lookup"><span data-stu-id="e75c0-130">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="e75c0-131">Однако разработчики командлетов должны избегать использования `ConfirmImpact` для операций, которые просто являются обратимыми, например для удаления учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e75c0-131">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="e75c0-132">Помните, что если для задано `ConfirmImpact` значение [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span><span class="sxs-lookup"><span data-stu-id="e75c0-132">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span></span>

<span data-ttu-id="e75c0-133">Аналогично, некоторые операции вряд ли будут разрушительными, хотя они и теоретически изменяют состояние выполнения системы за пределами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e75c0-133">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="e75c0-134">Такие командлеты могут иметь значение `ConfirmImpact` [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="e75c0-134">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span></span> <span data-ttu-id="e75c0-135">Это позволит обходить запросы на подтверждение, когда пользователь попросит подтвердить только средние и значительные последствия.</span><span class="sxs-lookup"><span data-stu-id="e75c0-135">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="e75c0-136">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="e75c0-136">Defining Parameters for System Modification</span></span>

<span data-ttu-id="e75c0-137">В этом разделе описывается, как определить параметры командлета, включая те, которые необходимы для поддержки изменения системы.</span><span class="sxs-lookup"><span data-stu-id="e75c0-137">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="e75c0-138">Общие сведения об определении параметров см. [в разделе Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md) .</span><span class="sxs-lookup"><span data-stu-id="e75c0-138">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="e75c0-139">Командлет "останавливает-proc" определяет три параметра: `Name` , `Force` и `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="e75c0-139">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="e75c0-140">`Name`Параметр соответствует `Name` свойству входного объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="e75c0-140">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="e75c0-141">Имейте в виду, что `Name` параметр в этом образце является обязательным, так как командлет завершится ошибкой, если у него нет именованного процесса для его завершения.</span><span class="sxs-lookup"><span data-stu-id="e75c0-141">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="e75c0-142">`Force`Параметр позволяет пользователю переопределить вызовы метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="e75c0-142">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="e75c0-143">Фактически, любой командлет, вызывающий [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , должен иметь `Force` параметр, чтобы при `Force` указании командлет пропустить вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) и продолжить операцию.</span><span class="sxs-lookup"><span data-stu-id="e75c0-143">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="e75c0-144">Имейте в виду, что это не влияет на вызовы метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span><span class="sxs-lookup"><span data-stu-id="e75c0-144">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="e75c0-145">`PassThru`Параметр позволяет пользователю указать, передает ли командлет выходной объект через конвейер, в данном случае после остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="e75c0-145">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="e75c0-146">Имейте в виду, что этот параметр привязан к самому командлету, а не к свойству входного объекта.</span><span class="sxs-lookup"><span data-stu-id="e75c0-146">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="e75c0-147">Ниже приведено объявление параметра для командлета "останавливает-proc".</span><span class="sxs-lookup"><span data-stu-id="e75c0-147">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="e75c0-148">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="e75c0-148">Overriding an Input Processing Method</span></span>

<span data-ttu-id="e75c0-149">Командлет должен переопределять метод обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="e75c0-149">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="e75c0-150">В следующем коде показано переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , используемое в командлете-proc.</span><span class="sxs-lookup"><span data-stu-id="e75c0-150">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="e75c0-151">Для каждого запрошенного имени процесса этот метод гарантирует, что процесс не является специальным процессом, пытается прерывать процесс, а затем отправляет выходной объект, если `PassThru` указан параметр.</span><span class="sxs-lookup"><span data-stu-id="e75c0-151">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

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

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="e75c0-152">Вызов метода ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="e75c0-152">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="e75c0-153">Метод обработки входных данных командлета должен вызвать метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , чтобы подтвердить выполнение операции перед изменением (например, удаление файлов), в состояние выполнения системы.</span><span class="sxs-lookup"><span data-stu-id="e75c0-153">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="e75c0-154">Это позволяет среде выполнения Windows PowerShell предоставить правильные правила "WhatIf" и "Confirm" в оболочке.</span><span class="sxs-lookup"><span data-stu-id="e75c0-154">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="e75c0-155">Если командлет сообщает, что он поддерживает, и не может выполнить вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , пользователь может неожиданно изменить систему.</span><span class="sxs-lookup"><span data-stu-id="e75c0-155">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="e75c0-156">Вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные в определении того, что должно отображаться пользователю.</span><span class="sxs-lookup"><span data-stu-id="e75c0-156">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="e75c0-157">В следующем примере показан вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете-proc.</span><span class="sxs-lookup"><span data-stu-id="e75c0-157">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="e75c0-158">Вызов метода ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="e75c0-158">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="e75c0-159">Вызов метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) отправляет пользователю дополнительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="e75c0-159">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="e75c0-160">Этот вызов выполняется после вызова метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `true` и если `Force` параметру не было присвоено значение `true` .</span><span class="sxs-lookup"><span data-stu-id="e75c0-160">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="e75c0-161">Пользователь может предоставить отзыв, чтобы сказать, следует ли продолжать операцию.</span><span class="sxs-lookup"><span data-stu-id="e75c0-161">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="e75c0-162">Командлет вызывает [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) в качестве дополнительной проверки потенциально опасных изменений системы или для предоставления пользователю параметров «Да» и «нет».</span><span class="sxs-lookup"><span data-stu-id="e75c0-162">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="e75c0-163">В следующем примере показан вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете-proc.</span><span class="sxs-lookup"><span data-stu-id="e75c0-163">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

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

## <a name="stopping-input-processing"></a><span data-ttu-id="e75c0-164">Остановка обработки ввода</span><span class="sxs-lookup"><span data-stu-id="e75c0-164">Stopping Input Processing</span></span>

<span data-ttu-id="e75c0-165">Метод обработки входных данных командлета, который вносит изменения в систему, должен обеспечить способ остановки обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="e75c0-165">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="e75c0-166">В случае с этим командлетом остановить-proc вызывается метод System. [Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метода System [. Diagnostics. Process. Kill \*](/dotnet/api/System.Diagnostics.Process.Kill) .</span><span class="sxs-lookup"><span data-stu-id="e75c0-166">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="e75c0-167">Поскольку `PassThru` параметр имеет значение `true` , [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) также вызывает [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки объекта процесса в конвейер.</span><span class="sxs-lookup"><span data-stu-id="e75c0-167">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e75c0-168">Образец кода</span><span class="sxs-lookup"><span data-stu-id="e75c0-168">Code Sample</span></span>

<span data-ttu-id="e75c0-169">Полный пример кода на C# см. в разделе [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e75c0-169">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="e75c0-170">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="e75c0-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="e75c0-171">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="e75c0-171">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="e75c0-172">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="e75c0-172">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e75c0-173">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e75c0-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e75c0-174">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="e75c0-174">Building the Cmdlet</span></span>

<span data-ttu-id="e75c0-175">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e75c0-175">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e75c0-176">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e75c0-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e75c0-177">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="e75c0-177">Testing the Cmdlet</span></span>

<span data-ttu-id="e75c0-178">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e75c0-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="e75c0-179">Ниже приведено несколько тестов, которые проверяют командлет «прекращать-proc».</span><span class="sxs-lookup"><span data-stu-id="e75c0-179">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="e75c0-180">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e75c0-180">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="e75c0-181">Запустите Windows PowerShell и используйте командлет "останавливает-обработать", чтобы прерывать обработку, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e75c0-181">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="e75c0-182">Поскольку командлет задает `Name` параметр как обязательный, командлет запрашивает параметр.</span><span class="sxs-lookup"><span data-stu-id="e75c0-182">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="e75c0-183">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="e75c0-183">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="e75c0-184">Теперь давайте воспользуемся командлетом, чтобы прерывать процесс с именем «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="e75c0-184">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="e75c0-185">Командлет предложит подтвердить действие.</span><span class="sxs-lookup"><span data-stu-id="e75c0-185">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

    <span data-ttu-id="e75c0-186">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="e75c0-186">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="e75c0-187">Чтобы прерывать критически важный процесс с именем "WINLOGON", используйте процедуру "останавливает-обработать".</span><span class="sxs-lookup"><span data-stu-id="e75c0-187">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="e75c0-188">Появится запрос и будет выведено предупреждение о выполнении этого действия, так как это приведет к перезагрузке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e75c0-188">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    <span data-ttu-id="e75c0-189">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="e75c0-189">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="e75c0-190">Теперь попробуем прерывать процесс WINLOGON без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e75c0-190">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="e75c0-191">Имейте в виду, что эта запись команды использует `Force` параметр для переопределения предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e75c0-191">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    <span data-ttu-id="e75c0-192">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="e75c0-192">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="e75c0-193">См. также</span><span class="sxs-lookup"><span data-stu-id="e75c0-193">See Also</span></span>

[<span data-ttu-id="e75c0-194">Добавление параметров, обрабатывающих входные данные командной строки</span><span class="sxs-lookup"><span data-stu-id="e75c0-194">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="e75c0-195">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e75c0-195">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="e75c0-196">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e75c0-196">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e75c0-197">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e75c0-197">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="e75c0-198">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="e75c0-198">Cmdlet Samples</span></span>](./cmdlet-samples.md)

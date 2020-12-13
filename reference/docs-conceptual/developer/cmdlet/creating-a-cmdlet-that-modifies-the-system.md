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
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="b72c9-103">Создание командлета, который изменяет систему</span><span class="sxs-lookup"><span data-stu-id="b72c9-103">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="b72c9-104">Иногда командлет должен изменить состояние выполнения системы, а не только состояние среды выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72c9-104">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="b72c9-105">В таких случаях командлет позволяет пользователю проверить, вносить ли изменения.</span><span class="sxs-lookup"><span data-stu-id="b72c9-105">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="b72c9-106">Для поддержки подтверждения командлет должен выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="b72c9-106">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="b72c9-107">Объявите, что командлет поддерживает подтверждение при указании атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) , установив для ключевого слова SupportsShouldProcess значение `true` .</span><span class="sxs-lookup"><span data-stu-id="b72c9-107">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="b72c9-108">Вызовите [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) во время выполнения командлета (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="b72c9-108">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="b72c9-109">При поддержке подтверждения командлет предоставляет `Confirm` `WhatIf` Параметры и, предоставляемые Windows PowerShell, а также рекомендации по разработке для командлетов (Дополнительные сведения о рекомендациях по разработке командлетов см. в разделе [рекомендации по разработке командлетов](./cmdlet-development-guidelines.md)).</span><span class="sxs-lookup"><span data-stu-id="b72c9-109">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="b72c9-110">Изменение системы</span><span class="sxs-lookup"><span data-stu-id="b72c9-110">Changing the System</span></span>

<span data-ttu-id="b72c9-111">Действие «изменение системы» относится к любому командлету, который потенциально изменяет состояние системы за пределами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72c9-111">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="b72c9-112">Например, остановка процесса, включение или отключение учетной записи пользователя или добавление строки в таблицу базы данных — это все изменения в системе, которые должны быть подтверждены.</span><span class="sxs-lookup"><span data-stu-id="b72c9-112">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span>
<span data-ttu-id="b72c9-113">В отличие от этого, операции, считывающие данные или устанавливающие временные подключения, не изменяют систему и, как правило, не нуждаются в подтверждении.</span><span class="sxs-lookup"><span data-stu-id="b72c9-113">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="b72c9-114">Подтверждение также не требуется для действий, воздействие которых ограничено внутри среды выполнения Windows PowerShell, например `set-variable` .</span><span class="sxs-lookup"><span data-stu-id="b72c9-114">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="b72c9-115">Командлеты, которые могут или не могут вносить постоянные изменения, должны объявлять `SupportsShouldProcess` и вызывать [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) только в том случае, если они собирается внести постоянные изменения.</span><span class="sxs-lookup"><span data-stu-id="b72c9-115">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="b72c9-116">Подтверждение ShouldProcess применяется только к командлетам.</span><span class="sxs-lookup"><span data-stu-id="b72c9-116">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="b72c9-117">Если команда или сценарий изменяет состояние выполнения системы путем непосредственного вызова методов или свойств .NET или путем вызова приложений за пределами Windows PowerShell, такая форма подтверждения будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="b72c9-117">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="b72c9-118">Командлет Стоппрок</span><span class="sxs-lookup"><span data-stu-id="b72c9-118">The StopProc Cmdlet</span></span>

<span data-ttu-id="b72c9-119">В этом разделе описывается командлет Stop-Proc, который пытается прерывать процессы, полученные с помощью командлета Get-Proc (описывается в статье [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="b72c9-119">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="b72c9-120">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="b72c9-120">Defining the Cmdlet</span></span>

<span data-ttu-id="b72c9-121">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="b72c9-121">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="b72c9-122">Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена.</span><span class="sxs-lookup"><span data-stu-id="b72c9-122">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="b72c9-123">Этот командлет останавливает системные процессы, поэтому выбранное здесь имя команды — Stop, определенное классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) с существительным «proc», которое указывает, что командлет останавливает процессы.</span><span class="sxs-lookup"><span data-stu-id="b72c9-123">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="b72c9-124">Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="b72c9-124">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="b72c9-125">Ниже приведено определение класса для этого командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-125">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="b72c9-126">Имейте в виду, что в объявлении [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) `SupportsShouldProcess` ключевое слово Attribute имеет значение, `true` чтобы позволить командлету вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="b72c9-126">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="b72c9-127">Если это ключевое слово не задано, `Confirm` `WhatIf` Параметры и не будут доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="b72c9-127">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="b72c9-128">Чрезвычайно разрушительные действия</span><span class="sxs-lookup"><span data-stu-id="b72c9-128">Extremely Destructive Actions</span></span>

<span data-ttu-id="b72c9-129">Некоторые операции являются чрезвычайно разрушительными, например переформатирование активного раздела жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="b72c9-129">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="b72c9-130">В этих случаях командлет должен быть задан `ConfirmImpact`  =  `ConfirmImpact.High` при объявлении атрибута [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .</span><span class="sxs-lookup"><span data-stu-id="b72c9-130">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="b72c9-131">Этот параметр заставляет командлет запрашивать подтверждение пользователя даже в том случае, если пользователь не указал `Confirm` параметр.</span><span class="sxs-lookup"><span data-stu-id="b72c9-131">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="b72c9-132">Однако разработчики командлетов должны избегать использования `ConfirmImpact` для операций, которые просто являются обратимыми, например для удаления учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b72c9-132">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="b72c9-133">Помните, что если для задано `ConfirmImpact` значение [System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **High**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-133">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact)
**High**.</span></span>

<span data-ttu-id="b72c9-134">Аналогично, некоторые операции вряд ли будут разрушительными, хотя они и теоретически изменяют состояние выполнения системы за пределами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72c9-134">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="b72c9-135">Такие командлеты могут иметь значение `ConfirmImpact` [System. Management. Automation. ConfirmImpact. Low](/dotnet/api/system.management.automation.confirmimpact).</span><span class="sxs-lookup"><span data-stu-id="b72c9-135">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact).</span></span>
<span data-ttu-id="b72c9-136">Это позволит обходить запросы на подтверждение, когда пользователь попросит подтвердить только средние и значительные последствия.</span><span class="sxs-lookup"><span data-stu-id="b72c9-136">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="b72c9-137">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="b72c9-137">Defining Parameters for System Modification</span></span>

<span data-ttu-id="b72c9-138">В этом разделе описывается, как определить параметры командлета, включая те, которые необходимы для поддержки изменения системы.</span><span class="sxs-lookup"><span data-stu-id="b72c9-138">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="b72c9-139">Общие сведения об определении параметров см. [в разделе Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md) .</span><span class="sxs-lookup"><span data-stu-id="b72c9-139">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="b72c9-140">Командлет Stop-Proc определяет три параметра: `Name` , `Force` и `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="b72c9-140">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="b72c9-141">`Name`Параметр соответствует `Name` свойству входного объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="b72c9-141">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="b72c9-142">Имейте в виду, что `Name` параметр в этом образце является обязательным, так как командлет завершится ошибкой, если у него нет именованного процесса для его завершения.</span><span class="sxs-lookup"><span data-stu-id="b72c9-142">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="b72c9-143">`Force`Параметр позволяет пользователю переопределить вызовы метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span><span class="sxs-lookup"><span data-stu-id="b72c9-143">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="b72c9-144">Фактически, любой командлет, вызывающий [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , должен иметь `Force` параметр, чтобы при `Force` указании командлет пропустить вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) и продолжить операцию.</span><span class="sxs-lookup"><span data-stu-id="b72c9-144">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="b72c9-145">Имейте в виду, что это не влияет на вызовы метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span><span class="sxs-lookup"><span data-stu-id="b72c9-145">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="b72c9-146">`PassThru`Параметр позволяет пользователю указать, передает ли командлет выходной объект через конвейер, в данном случае после остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="b72c9-146">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="b72c9-147">Имейте в виду, что этот параметр привязан к самому командлету, а не к свойству входного объекта.</span><span class="sxs-lookup"><span data-stu-id="b72c9-147">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="b72c9-148">Ниже приведено объявление параметра для командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-148">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="b72c9-149">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="b72c9-149">Overriding an Input Processing Method</span></span>

<span data-ttu-id="b72c9-150">Командлет должен переопределять метод обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="b72c9-150">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="b72c9-151">В следующем коде показано переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , используемое в командлете Sample Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-151">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="b72c9-152">Для каждого запрошенного имени процесса этот метод гарантирует, что процесс не является специальным процессом, пытается прерывать процесс, а затем отправляет выходной объект, если `PassThru` указан параметр.</span><span class="sxs-lookup"><span data-stu-id="b72c9-152">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

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

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="b72c9-153">Вызов метода ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="b72c9-153">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="b72c9-154">Метод обработки входных данных командлета должен вызвать метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , чтобы подтвердить выполнение операции перед изменением (например, удаление файлов), в состояние выполнения системы.</span><span class="sxs-lookup"><span data-stu-id="b72c9-154">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="b72c9-155">Это позволяет среде выполнения Windows PowerShell предоставить правильные правила "WhatIf" и "Confirm" в оболочке.</span><span class="sxs-lookup"><span data-stu-id="b72c9-155">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="b72c9-156">Если командлет сообщает, что он поддерживает, и не может выполнить вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , пользователь может неожиданно изменить систему.</span><span class="sxs-lookup"><span data-stu-id="b72c9-156">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="b72c9-157">Вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные в определении того, что должно отображаться пользователю.</span><span class="sxs-lookup"><span data-stu-id="b72c9-157">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="b72c9-158">В следующем примере показан вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) из переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете Sample Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-158">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="b72c9-159">Вызов метода ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="b72c9-159">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="b72c9-160">Вызов метода [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) отправляет пользователю дополнительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="b72c9-160">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="b72c9-161">Этот вызов выполняется после вызова метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `true` и если `Force` параметру не было присвоено значение `true` .</span><span class="sxs-lookup"><span data-stu-id="b72c9-161">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="b72c9-162">Пользователь может предоставить отзыв, чтобы сказать, следует ли продолжать операцию.</span><span class="sxs-lookup"><span data-stu-id="b72c9-162">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="b72c9-163">Командлет вызывает [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) в качестве дополнительной проверки потенциально опасных изменений системы или для предоставления пользователю параметров «Да» и «нет».</span><span class="sxs-lookup"><span data-stu-id="b72c9-163">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="b72c9-164">В следующем примере показан вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) в командлете Sample Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-164">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

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

## <a name="stopping-input-processing"></a><span data-ttu-id="b72c9-165">Остановка обработки ввода</span><span class="sxs-lookup"><span data-stu-id="b72c9-165">Stopping Input Processing</span></span>

<span data-ttu-id="b72c9-166">Метод обработки входных данных командлета, который вносит изменения в систему, должен обеспечить способ остановки обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="b72c9-166">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="b72c9-167">В случае использования этого командлета Stop-Proc выполняется вызов метода [System. Management. Automation. командлета](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [System. Diagnostics. Process. Kill \*](/dotnet/api/System.Diagnostics.Process.Kill) .</span><span class="sxs-lookup"><span data-stu-id="b72c9-167">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="b72c9-168">Поскольку `PassThru` параметр имеет значение `true` , [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) также вызывает [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки объекта процесса в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b72c9-168">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b72c9-169">Образец кода</span><span class="sxs-lookup"><span data-stu-id="b72c9-169">Code Sample</span></span>

<span data-ttu-id="b72c9-170">Полный пример кода на C# см. в разделе [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b72c9-170">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="b72c9-171">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="b72c9-171">Defining Object Types and Formatting</span></span>

<span data-ttu-id="b72c9-172">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b72c9-172">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="b72c9-173">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="b72c9-173">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="b72c9-174">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b72c9-174">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="b72c9-175">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="b72c9-175">Building the Cmdlet</span></span>

<span data-ttu-id="b72c9-176">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72c9-176">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="b72c9-177">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b72c9-177">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="b72c9-178">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="b72c9-178">Testing the Cmdlet</span></span>

<span data-ttu-id="b72c9-179">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b72c9-179">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="b72c9-180">Ниже приведены несколько тестов, тестирующих командлет Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="b72c9-180">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="b72c9-181">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b72c9-181">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="b72c9-182">Запустите Windows PowerShell и используйте командлет Stop-Proc, чтобы прерывать обработку, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b72c9-182">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="b72c9-183">Поскольку командлет задает `Name` параметр как обязательный, командлет запрашивает параметр.</span><span class="sxs-lookup"><span data-stu-id="b72c9-183">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="b72c9-184">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="b72c9-184">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="b72c9-185">Теперь давайте воспользуемся командлетом, чтобы прерывать процесс с именем «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="b72c9-185">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="b72c9-186">Командлет предложит подтвердить действие.</span><span class="sxs-lookup"><span data-stu-id="b72c9-186">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

    <span data-ttu-id="b72c9-187">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="b72c9-187">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="b72c9-188">Используйте Stop-Proc, как показано ниже, чтобы прерывать критический процесс с именем "WINLOGON".</span><span class="sxs-lookup"><span data-stu-id="b72c9-188">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="b72c9-189">Появится запрос и будет выведено предупреждение о выполнении этого действия, так как это приведет к перезагрузке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b72c9-189">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    <span data-ttu-id="b72c9-190">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="b72c9-190">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="b72c9-191">Теперь попробуем прерывать процесс WINLOGON без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b72c9-191">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="b72c9-192">Имейте в виду, что эта запись команды использует `Force` параметр для переопределения предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b72c9-192">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    <span data-ttu-id="b72c9-193">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="b72c9-193">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="b72c9-194">См. также:</span><span class="sxs-lookup"><span data-stu-id="b72c9-194">See Also</span></span>

[<span data-ttu-id="b72c9-195">Добавление параметров, обрабатывающих Command-Line входе</span><span class="sxs-lookup"><span data-stu-id="b72c9-195">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="b72c9-196">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b72c9-196">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="b72c9-197">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b72c9-197">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="b72c9-198">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72c9-198">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="b72c9-199">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="b72c9-199">Cmdlet Samples</span></span>](./cmdlet-samples.md)

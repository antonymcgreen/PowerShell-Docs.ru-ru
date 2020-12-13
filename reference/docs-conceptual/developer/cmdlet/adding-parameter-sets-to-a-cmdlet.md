---
ms.date: 09/13/2016
ms.topic: reference
title: Добавление наборов параметров в командлет
description: Добавление наборов параметров в командлет
ms.openlocfilehash: dd5ee2a880a4d516ea82e5afe0ced12369197243
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648655"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a>Добавление наборов параметров в командлет

## <a name="things-to-know-about-parameter-sets"></a>Сведения о наборах параметров

Windows PowerShell определяет набор параметров как группу параметров, которые работают вместе. Группируя параметры командлета, можно создать один командлет, который может изменить его функциональность в зависимости от того, какую группу параметров указывает пользователь.

Примером командлета, использующего два набора параметров для определения различных функциональных возможностей, является `Get-EventLog` командлет, предоставляемый Windows PowerShell. Этот командлет возвращает другие сведения, когда пользователь указывает `List` параметр или `LogName` . Если `LogName` указан параметр, командлет возвращает сведения о событиях в заданном журнале событий. Если `List` указан параметр, командлет возвращает сведения о самих файлах журнала (а не сведения о событиях, которые они содержат). В этом случае `List` `LogName` Параметры и указывают два отдельных набора параметров.

Два важных момента, о которых следует помнить, — это то, что среда выполнения Windows PowerShell использует только один набор параметров для конкретного входа и что каждый набор параметров должен иметь по крайней мере один параметр, уникальный для этого набора параметров.

Чтобы проиллюстрировать этот последний момент, этот командлет Stop-Proc использует три набора параметров: `ProcessName` , `ProcessId` и `InputObject` . Каждый из этих наборов параметров имеет один параметр, который не входит в другие наборы параметров. Наборы параметров могут совместно использовать другие параметры, но командлет использует уникальные параметры, `ProcessName` `ProcessId` и, `InputObject` чтобы определить, какой набор параметров следует использовать в среде выполнения Windows PowerShell.

## <a name="declaring-the-cmdlet-class"></a>Объявление класса командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Для этого командлета используется команда жизненного цикла "Stop", так как командлет останавливает системные процессы. Имя существительное "proc" используется, так как командлет работает с процессами. Обратите внимание, что в приведенном ниже объявлении команда командлета и имя существительное отражаются в имени класса командлета.

> [!NOTE]
> Дополнительные сведения о утвержденных именах глаголов командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Следующий код является определением класса для этого командлета Stop-Proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a>Объявление параметров командлета

Этот командлет определяет три параметра, необходимые в качестве входных данных для командлета (эти параметры также определяют наборы параметров), а также `Force` параметр, который управляет действием командлета и `PassThru` параметром, который определяет, отправляет ли командлет выходной объект через конвейер. По умолчанию этот командлет не передает объект через конвейер. Дополнительные сведения об этих двух последних параметрах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

### <a name="declaring-the-name-parameter"></a>Объявление параметра Name

Этот входной параметр позволяет пользователю указать имена процессов, которые должны быть остановлены. Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `ProcessName` набор параметров для этого параметра.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="44-58":::

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

Обратите внимание, что этому параметру присваивается псевдоним «ProcessName».

### <a name="declaring-the-id-parameter"></a>Объявление параметра ID

Этот входной параметр позволяет пользователю указать идентификаторы процессов, которые должны быть остановлены. Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `ProcessId` набор параметров.

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

Обратите внимание, что этому параметру присваивается псевдоним «ProcessId».

### <a name="declaring-the-inputobject-parameter"></a>Объявление параметра InputObject

Этот входной параметр позволяет пользователю указать входной объект, содержащий сведения о останавливаемых процессах. Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `InputObject` набор параметров для этого параметра.

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

Обратите внимание, что у этого параметра нет псевдонима.

### <a name="declaring-parameters-in-multiple-parameter-sets"></a>Объявление параметров в нескольких наборах параметров

Хотя для каждого набора параметров должен существовать уникальный параметр, параметры могут принадлежать нескольким наборам параметров. В этих случаях предоставьте общему параметру объявление атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) для каждого набора, которому принадлежит параметр. Если параметр находится во всех наборах параметров, достаточно объявить атрибут Parameter только один раз и не нужно указывать имя набора параметров.

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Каждый командлет должен переопределять метод обработки ввода, чаще всего это будет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . В этом командлете метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределен, чтобы командлет мог обработать любое количество процессов. Он содержит инструкцию SELECT, которая вызывает другой метод в зависимости от того, какой набор параметров задан пользователем.

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

Вспомогательные методы, вызываемые инструкцией SELECT, не описаны здесь, но их реализация можно увидеть в полном примере кода в следующем разделе.

## <a name="code-sample"></a>Образец кода

Полный пример кода на C# см. в разделе [StopProcessSample04 Sample](./stopprocesssample04-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

После регистрации командлета в Windows PowerShell проверьте его, запустив в командной строке. Ниже приведены некоторые тесты, показывающие, как `ProcessId` `InputObject` можно использовать параметры и для проверки наборов параметров для завершения процесса.

- После запуска Windows PowerShell выполните командлет Stop-Proc с `ProcessId` набором параметров, чтобы приступить к прерыванию процесса на основе его идентификатора. В этом случае командлет использует `ProcessId` набор параметров для завершения процесса.

  ```
  PS> stop-proc -Id 444
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
  ```

- После запуска Windows PowerShell выполните командлет Stop-Proc с параметром, равным, `InputObject` чтобы останавливаются процессы объекта Notepad, полученного с помощью `Get-Process` команды.

  ```
  PS> get-process notepad | stop-proc
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
  ```

## <a name="see-also"></a>См. также:

[Создание командлета, который изменяет систему](./creating-a-cmdlet-that-modifies-the-system.md)

[Создание командлета Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

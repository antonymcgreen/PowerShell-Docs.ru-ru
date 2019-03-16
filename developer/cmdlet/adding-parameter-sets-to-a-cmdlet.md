---
title: Добавление параметра наборов в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: f0bff11618c18bf53b9c2a185445795a17306fa3
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054991"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a>Добавление наборов параметров в командлет

В этом разделе описывается добавление наборов параметров в командлет Stop-Proc (описано в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md)). Как и другие командлеты Stop-Proc, описанные в руководстве по программированию, этот командлет пытается остановить процессы, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)).

Следующие подразделы этого раздела.

- [Что нужно знать о наборов параметров](#Adding-Parameter-Sets-to-a-Cmdlet)

- [Объявление класса командлета](#Declaring-the-Cmdlet-Class)

- [Объявление параметров командлета](#Declaring-the-Parameters-of-the-Cmdlet)

- [Переопределив метод обработки входных данных](#Overriding-an-Input-Processing-Method)

- [Пример кода](#Declaring-the-Parameters-of-the-Cmdlet)

- [Определение типов объектов и форматирование](#Defining-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

## <a name="things-to-know-about-parameter-sets"></a>Что нужно знать о наборов параметров

Windows PowerShell определяет группу параметров, которые работают совместно в качестве параметра. Группируя параметры командлета, можно создать один командлет, который можно изменить его функциональных возможностей, в зависимости от того, какие группу параметров, указанных пользователем.

Например, командлет, который использует два набора параметров, чтобы определить различные функции `Get-EventLog` командлет, предоставляемый Windows PowerShell. Этот командлет возвращает различные сведения, когда пользователь указывает `List` или `LogName` параметра. Если `LogName` параметр указан, командлет возвращает информацию о событиях в данном журнале событий. Если `List` параметр указан, командлет возвращает сведения о журнале файлов самостоятельно (не о событиях в них). В этом случае `List` и `LogName` параметры определяют две различные наборы параметров.

Два соображения следует помнить о наборов параметров том, что среда выполнения Windows PowerShell использует только один набор параметров для отдельного входного, и что каждый набор параметров должен иметь по крайней мере один параметр, является уникальным для этого набора параметров.

Для иллюстрации этой последней точки, этот командлет Stop-Proc использует три набора параметров: `ProcessName`, `ProcessId`, и `InputObject`. Каждый из этих наборов параметров имеет один параметр, который не находится в другие наборы параметров. Наборы параметров может совместно использовать другие параметры, но командлет будет использовать уникальные параметры `ProcessName`, `ProcessId`, и `InputObject` для определения, какой набор параметров, которые следует использовать среды выполнения Windows PowerShell.

## <a name="declaring-the-cmdlet-class"></a>Объявление класса командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Для этого командлета используется жизненным циклом команду «Stop», поскольку командлет останавливает системные процессы. Имя существительное «Proc» используется в том случае, так как командлет работает по процессам. В приведенном ниже объявлении Обратите внимание, что имя командлета глагол и существительное, отражаются в имени класса cmdlet.

> [!NOTE]
> Дополнительные сведения о командлет утвержденных глаголов, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Следующий код является определение класса для этого командлета Stop-Proc.

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

Этот командлет определяет три параметра, используется в качестве входных данных командлету (эти параметры также определяют наборы параметров), а также `Force` параметр, который управляет действие командлета и `PassThru` параметр, который определяет, отправляет ли командлет выходной объект по конвейеру. По умолчанию этот командлет не передать объект по конвейеру. Дополнительные сведения об этих двух последних параметрах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

### <a name="declaring-the-name-parameter"></a>Объявление параметра Name

Данный входной параметр позволяет пользователю указать имена процессов нужно остановить. Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `ProcessName` набор параметров для этого параметра.

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

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

### <a name="declaring-the-id-parameter"></a>Объявление параметра Id

Данный входной параметр позволяет пользователю указать идентификаторы процессов нужно остановить. Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `ProcessId` набор параметров.

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

Данный входной параметр позволяет пользователю указать входной объект, содержащий сведения о процессах, которые нужно остановить. Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `InputObject` набор параметров для этого параметра.

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

Обратите внимание, что этот параметр не имеет псевдонима.

### <a name="declaring-parameters-in-multiple-parameter-sets"></a>Объявление параметров в несколько наборов параметров

Несмотря на то, что должен быть уникальный параметр для каждого набора параметров, параметры могут принадлежать к более чем одним набором параметров. В таких случаях присвойте общий параметр [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута для каждого параметра, которому принадлежит. Если параметр является во всех наборах параметров, у вас один раз объявить атрибут parameter и не обязательно должны указать имя набора параметров.

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

Каждый командлет необходимо переопределить метод обработки входных данных, чаще всего это будет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод. В этом командлете [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод переопределяется, так что этот командлет может обработать любое количество процессов. Он содержит инструкцию Select, вызывает другой метод на основе какой набор параметров пользователя с указанными.

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

Вспомогательные методы, вызываемые оператором Select здесь не описываются, но вы увидите их реализации в полный пример кода в следующем разделе.

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример StopProcessSample04](./stopprocesssample04-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает данные между командлетами, используя объекты .NET. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

Если командлет зарегистрирован с помощью Windows PowerShell, проверьте его, запустив его в командной строке. Ниже приведены некоторые тесты, которые показывают, каким образом `ProcessId` и `InputObject` параметры могут использоваться для проверки их наборы параметров для остановки процесса.

- С помощью Windows PowerShell к работе, выполните командлет Stop-Proc с `ProcessId` задать параметр для остановки процесса на основе его идентификатора. В этом случае используется командлет `ProcessId` задать параметр для остановки процесса.

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- С помощью Windows PowerShell к работе, выполните командлет Stop-Proc с `InputObject` параметру для остановки процессов, в блокноте объект, возвращенный командлетом `Get-Process` команды.

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также

[Создание командлета, который изменяет системы](./creating-a-cmdlet-that-modifies-the-system.md)

[Как создать командлет Windows PowerShell](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

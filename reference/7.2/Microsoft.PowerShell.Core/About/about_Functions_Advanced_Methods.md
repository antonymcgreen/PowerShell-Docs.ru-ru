---
description: Описывает, как функции, указывающие `CmdletBinding` атрибут, могут использовать методы и свойства, доступные для скомпилированных командлетов.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 13a9d7258f1a52d5fcbb2d8c55b91c8d6454452d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604673"
---
# <a name="about-functions-advanced-methods"></a>О функциях дополнительные методы

## <a name="short-description"></a>Краткое описание

Описывает, как функции, указывающие `CmdletBinding` атрибут, могут использовать методы и свойства, доступные для скомпилированных командлетов.

## <a name="long-description"></a>Подробное описание

Функции, которые задают `CmdletBinding` атрибут, могут обращаться к ряду методов и свойств через `$PSCmdlet` переменную. К этим методам относятся следующие методы.

- Методы обработки ввода, которые скомпилированные командлеты используют для выполнения своей работы.
- `ShouldProcess`Методы и `ShouldContinue` , используемые для получения отзывов пользователей перед выполнением действия.
- `ThrowTerminatingError`Метод создания записей об ошибках.
- Несколько `Write` методов, возвращающих различные типы выходных данных.

Все методы и свойства класса **PSCmdlet** доступны для расширенных функций. Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Дополнительные сведения об `CmdletBinding` атрибуте см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).
Сведения о классе **кмдлетбиндингаттрибуте** см. в разделе [System. Management. Automation. командлет. кмдлетбиндингаттрибуте](/dotnet/api/system.management.automation.cmdletbindingattribute).

### <a name="input-processing-methods"></a>Методы обработки входных данных

Методы, описанные в этом разделе, называются методами обработки ввода. Для функций эти три метода представлены `Begin` `Process` `End` блоками, и функции. В функциях не обязательно использовать ни один из этих блоков.

> [!NOTE]
> Эти блоки также доступны для функций, которые не используют `CmdletBinding` атрибут.

#### <a name="begin"></a>Начать

Этот блок используется для предоставления необязательной одноразовой предварительной обработки для функции.
Среда выполнения PowerShell использует код в этом блоке один раз для каждого экземпляра функции в конвейере.

#### <a name="process"></a>Процесс

Этот блок используется для обеспечения обработки записей по записям для функции. Блок можно использовать `Process` без определения других блоков. Количество `Process` выполнений блоков зависит от того, как используется функция и какие входные данные получает функция.

Автоматическая переменная `$_` или `$PSItem` содержит текущий объект в конвейере для использования в `Process` блоке. `$input`Автоматическая переменная содержит перечислитель, доступный только для функций и блоков сценариев.
Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

- Вызов функции в начале или за пределами конвейера выполняет `Process` блок один раз.
- В конвейере `Process` блок выполняется один раз для каждого входного объекта, который достигает функции.
- Если входные данные конвейера, которые достигают функции, пусты, `Process` блок **не** выполняется.
  - `Begin`Блоки и `End` по-прежнему выполняются.

> [!IMPORTANT]
> Если параметр функции принимает входные данные конвейера, а `Process` блок не определен, обработка записи по записям завершится ошибкой. В этом случае функция будет выполняться только один раз, независимо от входных данных.

#### <a name="end"></a>Конец

Этот блок используется для предоставления функции необязательной однократной последующей обработки.

В следующем примере показана структура функции, которая содержит `Begin` блок для одноразовой предварительной обработки, `Process` блок для обработки нескольких записей и `End` блок для однократной последующей обработки.

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> Для использования `Begin` блока или необходимо `End` определить все три блока. При использовании всех трех блоков весь код PowerShell должен находиться внутри одного из блоков.

### <a name="confirmation-methods"></a>Методы подтверждения

#### <a name="shouldprocess"></a>ShouldProcess

Этот метод вызывается для запроса подтверждения от пользователя до того, как функция выполняет действие, которое привело бы к изменению системы. Функция может продолжаться на основе логического значения, возвращаемого методом. Этот метод может быть вызван только внутри `Process{}` блока функции. `CmdletBinding`Атрибут также должен объявлять, что функция поддерживает `ShouldProcess` (как показано в предыдущем примере).

Дополнительные сведения об этом методе см. в разделе [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).

Дополнительные сведения о запросе подтверждения см. в разделе [запрос подтверждения](/powershell/scripting/developer/cmdlet/requesting-confirmation).

#### <a name="shouldcontinue"></a>ShouldContinue

Этот метод вызывается для запроса второго сообщения с подтверждением. Он должен вызываться, когда `ShouldProcess` метод возвращает значение `$true` . Дополнительные сведения об этом методе см. в разделе [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).

### <a name="error-methods"></a>Методы ошибок

Функции могут вызывать два разных метода при возникновении ошибок. При возникновении неустранимой ошибки функция должна вызвать `WriteError` метод, который описан в `Write` разделе методы. Когда возникает завершающая ошибка и функция не может продолжить работу, она должна вызвать `ThrowTerminatingError` метод. Можно также использовать `Throw` инструкцию для завершения ошибок и командлет [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) для устранимых ошибок.

Дополнительные сведения см. в разделе [System. Management. Automation. командлет. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).

### <a name="write-methods"></a>Методы записи

Функция может вызывать следующие методы для возврата различных типов выходных данных.
Обратите внимание, что не все выходные данные переходят к следующей команде в конвейере. Можно также использовать различные `Write` командлеты, например `Write-Error` .

#### <a name="writecommanddetail"></a>вритекомманддетаил

Дополнительные сведения о `WriteCommandDetails` методе см. в разделе [System. Management. Automation. командлет. вритекомманддетаил](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).

#### <a name="writedebug"></a>вритедебуг

Чтобы предоставить сведения, которые можно использовать для устранения неполадок функции, сделайте ее вызовом `WriteDebug` метода. `WriteDebug`Метод отображает сообщения отладки для пользователя. Дополнительные сведения см. в разделе [System. Management. Automation. командлет. вритедебуг](/dotnet/api/system.management.automation.cmdlet.writedebug).

#### <a name="writeerror"></a>WriteError

Функции должны вызывать этот метод при возникновении устранимых ошибок, а функция предназначена для продолжения обработки записей. Дополнительные сведения см. в разделе [System. Management. Automation. командлет. WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).

> [!NOTE]
> При возникновении завершающей ошибки функция должна вызвать метод [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) .

#### <a name="writeobject"></a>WriteObject

`WriteObject`Метод позволяет функции отправить объект в следующую команду в конвейере. В большинстве случаев `WriteObject` метод используется, когда функция возвращает данные. Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).

#### <a name="writeprogress"></a>вритепрогресс

Для функций с действиями, выполнение которых занимает много времени, этот метод позволяет функции вызвать `WriteProgress` метод, чтобы отображались сведения о ходе выполнения. Например, можно отобразить процент завершенных.
Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритепрогресс](/dotnet/api/system.management.automation.cmdlet.writeprogress).

#### <a name="writeverbose"></a>вритевербосе

Чтобы получить подробные сведения о том, что делает функция, вызовите `WriteVerbose` метод, чтобы отобразить подробные сообщения для пользователя. По умолчанию подробные сообщения не отображаются. Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритевербосе](/dotnet/api/system.management.automation.cmdlet.writeverbose).

#### <a name="writewarning"></a>вритеварнинг

Чтобы предоставить сведения об условиях, которые могут привести к непредвиденным результатам, сделайте функцию вызовом метода Вритеварнинг, чтобы отобразить предупреждающие сообщения пользователю. По умолчанию отображаются предупреждающие сообщения. Дополнительные сведения см. в разделе [System. Management. Automation. PSCmdlet. вритеварнинг](/dotnet/api/system.management.automation.cmdlet.writewarning).

> [!NOTE]
> Можно также отобразить предупреждающие сообщения, настроив `$WarningPreference` переменную или используя `Verbose` `Debug` Параметры командной строки и. Дополнительные сведения о `$WarningPreference` переменной см. в разделе [about_Preference_Variables](about_Preference_Variables.md).

### <a name="other-methods-and-properties"></a>Другие методы и свойства

Дополнительные сведения о других методах и свойствах, к которым можно получить доступ через `$PSCmdlet` переменную, см. в разделе [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Например, свойство [параметерсетнаме](/dotnet/api/system.management.automation.pscmdlet.parametersetname) позволяет увидеть используемый набор параметров. Наборы параметров позволяют создавать функции, выполняющие различные задачи на основе параметров, указанных при выполнении функции.

## <a name="see-also"></a>См. также

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Preference_Variables](about_Preference_Variables.md)


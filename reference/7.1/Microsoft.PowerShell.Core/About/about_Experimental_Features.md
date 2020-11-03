---
description: Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О экспериментальных функциях
ms.openlocfilehash: fb13d605607b3f6daaba30cef9e7ee339221191c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231690"
---
# <a name="experimental-features"></a>Экспериментальные возможности

Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.

Экспериментальной функцией называется та, которая находится на этапе проектирования. Эта функция доступна пользователям для тестирования и предоставления отзывов о ней. Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими. Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы.

Экспериментальные функции по умолчанию отключены и должны быть явно включены пользователем или администратором системы.

Включенные экспериментальные функции перечислены в `powershell.config.json` файле в `$PSHOME` для всех пользователей или в файле конфигурации конкретного пользователя.

> [!NOTE]
> Экспериментальные функции, включенные в файл конфигурации пользователя, имеют приоритет над экспериментальными функциями, перечисленными в файле конфигурации системы.

## <a name="the-experimental-attribute"></a>Экспериментальный атрибут

Используйте `Experimental` атрибут, чтобы объявить некоторый код как экспериментальный.

Используйте следующий синтаксис, чтобы объявить `Experimental` атрибут, предоставляющий имя экспериментального компонента, и действие, которое будет выполнено, если экспериментальная функция включена:

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

Для модулей параметр `NameOfExperimentalFeature` должен соответствовать форме `<modulename>.<experimentname>` . `ExperimentAction`Необходимо указать параметр и допустимые значения:

- `Show` означает, что эта экспериментальная функция отображается, если эта функция включена
- `Hide` возможность скрыть эту экспериментальную функцию, если эта функция включена

### <a name="declaring-experimental-features-in-modules-written-in-c"></a>Объявление экспериментальных функций в модулях, написанных на языке C\#

Авторы модулей, желающие использовать экспериментальные флаги функций, могут объявить командлет как экспериментальный с помощью `Experimental` атрибута.

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a>Объявление экспериментальных функций в модулях, написанных в PowerShell

Модуль, написанный в PowerShell, также может использовать `Experimental` атрибут для объявления экспериментальных командлетов:

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a>Взаимоисключающие экспериментальные функции

Бывают случаи, когда экспериментальная функция не может существовать параллельно с существующей функцией или с другой экспериментальной функцией.

Например, можно использовать экспериментальный командлет, переопределяющий существующий командлет. Две версии не могут сосуществовать параллельно. `ExperimentAction.Hide`Параметр позволяет одновременно включить только один из двух командлетов.

В этом примере мы создадим новый экспериментальный `Invoke-WebRequest` командлет.
`InvokeWebRequestCommand` содержит неэкспериментальную реализацию.
`InvokeWebRequestCommandV2` содержит экспериментальную версию командлета.

Использование компонента позволяет `ExperimentAction.Hide` одновременно включить только одну из двух функций:

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

Если `MyWebCmdlets.PSWebCmdletV2` экспериментальная функция включена, существующая `InvokeWebRequestCommand` Реализация скрывается и `InvokeWebRequestCommandV2` предоставляет реализацию `Invoke-WebRequest` .

Это позволяет пользователям испытать новый командлет и отправить отзыв, когда это необходимо, к неэкспериментальной версии.

### <a name="experimental-parameters-in-cmdlets"></a>Экспериментальные параметры в командлетах

`Experimental`Атрибут также может применяться к отдельным параметрам. Это позволяет создать экспериментальный набор параметров для существующего командлета, а не совершенно нового командлета.

Ниже приведен пример на языке C#.

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

Вот другой пример в сценарии PowerShell:

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a>Проверяется, включена ли экспериментальная функция

В коде необходимо проверить, включена ли экспериментальная функция, прежде чем предпринимать необходимые действия. Можно определить, включена ли экспериментальная функция с помощью статического `IsEnabled()` метода `System.Management.Automation.ExperimentalFeature` класса.

Ниже приведен пример на языке C#.

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

Ниже приведен пример сценария PowerShell.

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a>См. также статью

[Enable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[Disable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[Get-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)


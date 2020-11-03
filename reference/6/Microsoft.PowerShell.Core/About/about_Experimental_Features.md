---
description: Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О экспериментальных функциях
ms.openlocfilehash: 663b8bbd8659b972004499e0c8a247818b8ef311
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231501"
---
# <a name="experimental-features"></a><span data-ttu-id="b8d02-104">Экспериментальные возможности</span><span class="sxs-lookup"><span data-stu-id="b8d02-104">Experimental Features</span></span>

<span data-ttu-id="b8d02-105">Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8d02-105">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="b8d02-106">Экспериментальной функцией называется та, которая находится на этапе проектирования.</span><span class="sxs-lookup"><span data-stu-id="b8d02-106">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="b8d02-107">Эта функция доступна пользователям для тестирования и предоставления отзывов о ней.</span><span class="sxs-lookup"><span data-stu-id="b8d02-107">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="b8d02-108">Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими.</span><span class="sxs-lookup"><span data-stu-id="b8d02-108">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="b8d02-109">Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы.</span><span class="sxs-lookup"><span data-stu-id="b8d02-109">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="b8d02-110">Экспериментальные функции по умолчанию отключены и должны быть явно включены пользователем или администратором системы.</span><span class="sxs-lookup"><span data-stu-id="b8d02-110">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="b8d02-111">Включенные экспериментальные функции перечислены в `powershell.config.json` файле в `$PSHOME` для всех пользователей или в файле конфигурации конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8d02-111">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="b8d02-112">Экспериментальные функции, включенные в файл конфигурации пользователя, имеют приоритет над экспериментальными функциями, перечисленными в файле конфигурации системы.</span><span class="sxs-lookup"><span data-stu-id="b8d02-112">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="b8d02-113">Экспериментальный атрибут</span><span class="sxs-lookup"><span data-stu-id="b8d02-113">The Experimental Attribute</span></span>

<span data-ttu-id="b8d02-114">Используйте `Experimental` атрибут, чтобы объявить некоторый код как экспериментальный.</span><span class="sxs-lookup"><span data-stu-id="b8d02-114">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="b8d02-115">Используйте следующий синтаксис, чтобы объявить `Experimental` атрибут, предоставляющий имя экспериментального компонента, и действие, которое будет выполнено, если экспериментальная функция включена:</span><span class="sxs-lookup"><span data-stu-id="b8d02-115">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="b8d02-116">Для модулей параметр `NameOfExperimentalFeature` должен соответствовать форме `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="b8d02-116">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="b8d02-117">`ExperimentAction`Необходимо указать параметр и допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b8d02-117">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="b8d02-118">`Show` означает, что эта экспериментальная функция отображается, если эта функция включена</span><span class="sxs-lookup"><span data-stu-id="b8d02-118">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="b8d02-119">`Hide` возможность скрыть эту экспериментальную функцию, если эта функция включена</span><span class="sxs-lookup"><span data-stu-id="b8d02-119">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="b8d02-120">Объявление экспериментальных функций в модулях, написанных на языке C\#</span><span class="sxs-lookup"><span data-stu-id="b8d02-120">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="b8d02-121">Авторы модулей, желающие использовать экспериментальные флаги функций, могут объявить командлет как экспериментальный с помощью `Experimental` атрибута.</span><span class="sxs-lookup"><span data-stu-id="b8d02-121">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="b8d02-122">Объявление экспериментальных функций в модулях, написанных в PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8d02-122">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="b8d02-123">Модуль, написанный в PowerShell, также может использовать `Experimental` атрибут для объявления экспериментальных командлетов:</span><span class="sxs-lookup"><span data-stu-id="b8d02-123">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="b8d02-124">Взаимоисключающие экспериментальные функции</span><span class="sxs-lookup"><span data-stu-id="b8d02-124">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="b8d02-125">Бывают случаи, когда экспериментальная функция не может существовать параллельно с существующей функцией или с другой экспериментальной функцией.</span><span class="sxs-lookup"><span data-stu-id="b8d02-125">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="b8d02-126">Например, можно использовать экспериментальный командлет, переопределяющий существующий командлет.</span><span class="sxs-lookup"><span data-stu-id="b8d02-126">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="b8d02-127">Две версии не могут сосуществовать параллельно.</span><span class="sxs-lookup"><span data-stu-id="b8d02-127">The two versions can't coexist side by side.</span></span> <span data-ttu-id="b8d02-128">`ExperimentAction.Hide`Параметр позволяет одновременно включить только один из двух командлетов.</span><span class="sxs-lookup"><span data-stu-id="b8d02-128">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="b8d02-129">В этом примере мы создадим новый экспериментальный `Invoke-WebRequest` командлет.</span><span class="sxs-lookup"><span data-stu-id="b8d02-129">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="b8d02-130">`InvokeWebRequestCommand` содержит неэкспериментальную реализацию.</span><span class="sxs-lookup"><span data-stu-id="b8d02-130">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="b8d02-131">`InvokeWebRequestCommandV2` содержит экспериментальную версию командлета.</span><span class="sxs-lookup"><span data-stu-id="b8d02-131">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="b8d02-132">Использование компонента позволяет `ExperimentAction.Hide` одновременно включить только одну из двух функций:</span><span class="sxs-lookup"><span data-stu-id="b8d02-132">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="b8d02-133">Если `MyWebCmdlets.PSWebCmdletV2` экспериментальная функция включена, существующая `InvokeWebRequestCommand` Реализация скрывается и `InvokeWebRequestCommandV2` предоставляет реализацию `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="b8d02-133">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="b8d02-134">Это позволяет пользователям испытать новый командлет и отправить отзыв, когда это необходимо, к неэкспериментальной версии.</span><span class="sxs-lookup"><span data-stu-id="b8d02-134">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="b8d02-135">Экспериментальные параметры в командлетах</span><span class="sxs-lookup"><span data-stu-id="b8d02-135">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="b8d02-136">`Experimental`Атрибут также может применяться к отдельным параметрам.</span><span class="sxs-lookup"><span data-stu-id="b8d02-136">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="b8d02-137">Это позволяет создать экспериментальный набор параметров для существующего командлета, а не совершенно нового командлета.</span><span class="sxs-lookup"><span data-stu-id="b8d02-137">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="b8d02-138">Ниже приведен пример на языке C#.</span><span class="sxs-lookup"><span data-stu-id="b8d02-138">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="b8d02-139">Вот другой пример в сценарии PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b8d02-139">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="b8d02-140">Проверяется, включена ли экспериментальная функция</span><span class="sxs-lookup"><span data-stu-id="b8d02-140">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="b8d02-141">В коде необходимо проверить, включена ли экспериментальная функция, прежде чем предпринимать необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="b8d02-141">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="b8d02-142">Можно определить, включена ли экспериментальная функция с помощью статического `IsEnabled()` метода `System.Management.Automation.ExperimentalFeature` класса.</span><span class="sxs-lookup"><span data-stu-id="b8d02-142">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="b8d02-143">Ниже приведен пример на языке C#.</span><span class="sxs-lookup"><span data-stu-id="b8d02-143">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="b8d02-144">Ниже приведен пример сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8d02-144">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="b8d02-145">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b8d02-145">See also</span></span>

[<span data-ttu-id="b8d02-146">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8d02-146">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="b8d02-147">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8d02-147">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="b8d02-148">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b8d02-148">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

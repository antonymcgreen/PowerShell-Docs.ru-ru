---
description: Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О экспериментальных функциях
ms.openlocfilehash: 82f5ef9838fcbb98e71e362ad00b1ec68f9a9f67
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604494"
---
# <a name="experimental-features"></a><span data-ttu-id="8142d-103">Экспериментальные возможности</span><span class="sxs-lookup"><span data-stu-id="8142d-103">Experimental Features</span></span>

<span data-ttu-id="8142d-104">Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8142d-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="8142d-105">Экспериментальной функцией называется та, которая находится на этапе проектирования.</span><span class="sxs-lookup"><span data-stu-id="8142d-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="8142d-106">Эта функция доступна пользователям для тестирования и предоставления отзывов о ней.</span><span class="sxs-lookup"><span data-stu-id="8142d-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="8142d-107">Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими.</span><span class="sxs-lookup"><span data-stu-id="8142d-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="8142d-108">Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы.</span><span class="sxs-lookup"><span data-stu-id="8142d-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="8142d-109">Экспериментальные функции по умолчанию отключены и должны быть явно включены пользователем или администратором системы.</span><span class="sxs-lookup"><span data-stu-id="8142d-109">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="8142d-110">Включенные экспериментальные функции перечислены в `powershell.config.json` файле в `$PSHOME` для всех пользователей или в файле конфигурации конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="8142d-110">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="8142d-111">Экспериментальные функции, включенные в файл конфигурации пользователя, имеют приоритет над экспериментальными функциями, перечисленными в файле конфигурации системы.</span><span class="sxs-lookup"><span data-stu-id="8142d-111">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="8142d-112">Экспериментальный атрибут</span><span class="sxs-lookup"><span data-stu-id="8142d-112">The Experimental Attribute</span></span>

<span data-ttu-id="8142d-113">Используйте `Experimental` атрибут, чтобы объявить некоторый код как экспериментальный.</span><span class="sxs-lookup"><span data-stu-id="8142d-113">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="8142d-114">Используйте следующий синтаксис, чтобы объявить `Experimental` атрибут, предоставляющий имя экспериментального компонента, и действие, которое будет выполнено, если экспериментальная функция включена:</span><span class="sxs-lookup"><span data-stu-id="8142d-114">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="8142d-115">Для модулей параметр `NameOfExperimentalFeature` должен соответствовать форме `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="8142d-115">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="8142d-116">`ExperimentAction`Необходимо указать параметр и допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8142d-116">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="8142d-117">`Show` означает, что эта экспериментальная функция отображается, если эта функция включена</span><span class="sxs-lookup"><span data-stu-id="8142d-117">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="8142d-118">`Hide` возможность скрыть эту экспериментальную функцию, если эта функция включена</span><span class="sxs-lookup"><span data-stu-id="8142d-118">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="8142d-119">Объявление экспериментальных функций в модулях, написанных на языке C\#</span><span class="sxs-lookup"><span data-stu-id="8142d-119">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="8142d-120">Авторы модулей, желающие использовать экспериментальные флаги функций, могут объявить командлет как экспериментальный с помощью `Experimental` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8142d-120">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="8142d-121">Объявление экспериментальных функций в модулях, написанных в PowerShell</span><span class="sxs-lookup"><span data-stu-id="8142d-121">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="8142d-122">Модуль, написанный в PowerShell, также может использовать `Experimental` атрибут для объявления экспериментальных командлетов:</span><span class="sxs-lookup"><span data-stu-id="8142d-122">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="8142d-123">Взаимоисключающие экспериментальные функции</span><span class="sxs-lookup"><span data-stu-id="8142d-123">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="8142d-124">Бывают случаи, когда экспериментальная функция не может существовать параллельно с существующей функцией или с другой экспериментальной функцией.</span><span class="sxs-lookup"><span data-stu-id="8142d-124">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="8142d-125">Например, можно использовать экспериментальный командлет, переопределяющий существующий командлет.</span><span class="sxs-lookup"><span data-stu-id="8142d-125">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="8142d-126">Две версии не могут сосуществовать параллельно.</span><span class="sxs-lookup"><span data-stu-id="8142d-126">The two versions can't coexist side by side.</span></span> <span data-ttu-id="8142d-127">`ExperimentAction.Hide`Параметр позволяет одновременно включить только один из двух командлетов.</span><span class="sxs-lookup"><span data-stu-id="8142d-127">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="8142d-128">В этом примере мы создадим новый экспериментальный `Invoke-WebRequest` командлет.</span><span class="sxs-lookup"><span data-stu-id="8142d-128">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="8142d-129">`InvokeWebRequestCommand` содержит неэкспериментальную реализацию.</span><span class="sxs-lookup"><span data-stu-id="8142d-129">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="8142d-130">`InvokeWebRequestCommandV2` содержит экспериментальную версию командлета.</span><span class="sxs-lookup"><span data-stu-id="8142d-130">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="8142d-131">Использование компонента позволяет `ExperimentAction.Hide` одновременно включить только одну из двух функций:</span><span class="sxs-lookup"><span data-stu-id="8142d-131">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="8142d-132">Если `MyWebCmdlets.PSWebCmdletV2` экспериментальная функция включена, существующая `InvokeWebRequestCommand` Реализация скрывается и `InvokeWebRequestCommandV2` предоставляет реализацию `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="8142d-132">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="8142d-133">Это позволяет пользователям испытать новый командлет и отправить отзыв, когда это необходимо, к неэкспериментальной версии.</span><span class="sxs-lookup"><span data-stu-id="8142d-133">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="8142d-134">Экспериментальные параметры в командлетах</span><span class="sxs-lookup"><span data-stu-id="8142d-134">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="8142d-135">`Experimental`Атрибут также может применяться к отдельным параметрам.</span><span class="sxs-lookup"><span data-stu-id="8142d-135">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="8142d-136">Это позволяет создать экспериментальный набор параметров для существующего командлета, а не совершенно нового командлета.</span><span class="sxs-lookup"><span data-stu-id="8142d-136">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="8142d-137">Ниже приведен пример на языке C#.</span><span class="sxs-lookup"><span data-stu-id="8142d-137">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="8142d-138">Вот другой пример в сценарии PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8142d-138">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="8142d-139">Проверяется, включена ли экспериментальная функция</span><span class="sxs-lookup"><span data-stu-id="8142d-139">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="8142d-140">В коде необходимо проверить, включена ли экспериментальная функция, прежде чем предпринимать необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="8142d-140">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="8142d-141">Можно определить, включена ли экспериментальная функция с помощью статического `IsEnabled()` метода `System.Management.Automation.ExperimentalFeature` класса.</span><span class="sxs-lookup"><span data-stu-id="8142d-141">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="8142d-142">Ниже приведен пример на языке C#.</span><span class="sxs-lookup"><span data-stu-id="8142d-142">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="8142d-143">Ниже приведен пример сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8142d-143">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="8142d-144">См. также</span><span class="sxs-lookup"><span data-stu-id="8142d-144">See also</span></span>

[<span data-ttu-id="8142d-145">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="8142d-145">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="8142d-146">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="8142d-146">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="8142d-147">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="8142d-147">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)


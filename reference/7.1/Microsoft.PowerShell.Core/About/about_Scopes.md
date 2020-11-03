---
description: Объясняет концепцию Scope в PowerShell и показывает, как устанавливать и изменять область элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 8bf35e1309f027e1cf0061a95bdede0926d39ee0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231658"
---
# <a name="about-scopes"></a><span data-ttu-id="ac421-104">Сведения об областях</span><span class="sxs-lookup"><span data-stu-id="ac421-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="ac421-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ac421-105">Short description</span></span>
<span data-ttu-id="ac421-106">Объясняет концепцию Scope в PowerShell и показывает, как устанавливать и изменять область элементов.</span><span class="sxs-lookup"><span data-stu-id="ac421-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="ac421-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ac421-107">Long description</span></span>

<span data-ttu-id="ac421-108">PowerShell защищает доступ к переменным, псевдонимам, функциям и дискам PowerShell (Псдривес), ограничивая место для чтения и изменения.</span><span class="sxs-lookup"><span data-stu-id="ac421-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="ac421-109">PowerShell использует правила области, чтобы предотвратить случайное изменение элемента, который не должен изменяться.</span><span class="sxs-lookup"><span data-stu-id="ac421-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="ac421-110">Ниже приведены основные правила области.</span><span class="sxs-lookup"><span data-stu-id="ac421-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="ac421-111">Области могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="ac421-111">Scopes may nest.</span></span> <span data-ttu-id="ac421-112">Внешняя область называется родительской областью.</span><span class="sxs-lookup"><span data-stu-id="ac421-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="ac421-113">Все вложенные области являются дочерними областями этого родителя.</span><span class="sxs-lookup"><span data-stu-id="ac421-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="ac421-114">Элемент отображается в области, в которой он был создан, и во всех дочерних областях, если вы явно не сделаете его частным.</span><span class="sxs-lookup"><span data-stu-id="ac421-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="ac421-115">Вы можете разместить переменные, псевдонимы, функции или диски PowerShell в одной или нескольких областях.</span><span class="sxs-lookup"><span data-stu-id="ac421-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="ac421-116">Элемент, созданный в области, может быть изменен только в той области, в которой она была создана, если только вы явно не указали другую область.</span><span class="sxs-lookup"><span data-stu-id="ac421-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="ac421-117">При создании элемента в области и его имени вместе с элементом в другой области исходный элемент может быть скрыт под новым элементом, но не переопределен или не изменен.</span><span class="sxs-lookup"><span data-stu-id="ac421-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="ac421-118">Области PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac421-118">PowerShell Scopes</span></span>

<span data-ttu-id="ac421-119">PowerShell поддерживает следующие области:</span><span class="sxs-lookup"><span data-stu-id="ac421-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="ac421-120">Global — область, действующая при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac421-120">Global: The scope that is in effect when PowerShell starts.</span></span> <span data-ttu-id="ac421-121">Переменные и функции, которые имеются при запуске PowerShell в глобальной области, такие как автоматические переменные и привилегированные переменные.</span><span class="sxs-lookup"><span data-stu-id="ac421-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="ac421-122">Переменные, псевдонимы и функции в профилях PowerShell также создаются в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span>

- <span data-ttu-id="ac421-123">Local: текущая область.</span><span class="sxs-lookup"><span data-stu-id="ac421-123">Local: The current scope.</span></span> <span data-ttu-id="ac421-124">Локальная область может быть глобальной или любой другой областью.</span><span class="sxs-lookup"><span data-stu-id="ac421-124">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="ac421-125">Скрипт: область, созданная во время выполнения файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac421-125">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="ac421-126">В области скрипта выполняются только команды в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ac421-126">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="ac421-127">Для команд в скрипте областью скрипта является локальная область.</span><span class="sxs-lookup"><span data-stu-id="ac421-127">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="ac421-128">**Частный** не является областью.</span><span class="sxs-lookup"><span data-stu-id="ac421-128">**Private** is not a scope.</span></span> <span data-ttu-id="ac421-129">Это [параметр](#private-option) , который изменяет видимость элемента за пределами области, в которой определен элемент.</span><span class="sxs-lookup"><span data-stu-id="ac421-129">It is an [option](#private-option) that changes the visibility of an item outside of the the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="ac421-130">Родительские и дочерние области</span><span class="sxs-lookup"><span data-stu-id="ac421-130">Parent and Child Scopes</span></span>

<span data-ttu-id="ac421-131">Новую область можно создать, выполнив скрипт или функцию, создав сеанс или запустив новый экземпляр PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac421-131">You can create a new scope by running a script or function, by creating a session, or by starting a new instance of PowerShell.</span></span> <span data-ttu-id="ac421-132">При создании новой области результатом является родительская область (исходная область) и дочерняя область (созданная область).</span><span class="sxs-lookup"><span data-stu-id="ac421-132">When you create a new scope, the result is a parent scope (the original scope) and a child scope (the scope that you created).</span></span>

<span data-ttu-id="ac421-133">В PowerShell все области являются дочерними областями глобальной области, но можно создать множество областей и много рекурсивных областей.</span><span class="sxs-lookup"><span data-stu-id="ac421-133">In PowerShell, all scopes are child scopes of the global scope, but you can create many scopes and many recursive scopes.</span></span>

<span data-ttu-id="ac421-134">Если явно не сделать элементы закрытыми, элементы в родительской области становятся доступными для дочерней области.</span><span class="sxs-lookup"><span data-stu-id="ac421-134">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="ac421-135">Однако элементы, создаваемые и изменяемые в дочерней области, не влияют на родительскую область, если только при создании элементов не будет явно задана область.</span><span class="sxs-lookup"><span data-stu-id="ac421-135">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

## <a name="inheritance"></a><span data-ttu-id="ac421-136">Наследование</span><span class="sxs-lookup"><span data-stu-id="ac421-136">Inheritance</span></span>

<span data-ttu-id="ac421-137">Дочерняя область не наследует переменные, псевдонимы и функции из родительской области.</span><span class="sxs-lookup"><span data-stu-id="ac421-137">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="ac421-138">Если элемент не является частным, дочерняя область может просматривать элементы в родительской области.</span><span class="sxs-lookup"><span data-stu-id="ac421-138">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="ac421-139">Кроме того, он может изменить элементы, явно указав родительскую область, но элементы не являются частью дочерней области.</span><span class="sxs-lookup"><span data-stu-id="ac421-139">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="ac421-140">Однако дочерняя область создается с набором элементов.</span><span class="sxs-lookup"><span data-stu-id="ac421-140">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="ac421-141">Как правило, он включает все псевдонимы с параметром **AllScope** .</span><span class="sxs-lookup"><span data-stu-id="ac421-141">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="ac421-142">Этот параметр обсуждается далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ac421-142">This option is discussed later in this article.</span></span> <span data-ttu-id="ac421-143">Он включает все переменные с параметром **AllScope** , а также некоторые автоматические переменные.</span><span class="sxs-lookup"><span data-stu-id="ac421-143">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="ac421-144">Чтобы найти элементы в определенной области, используйте параметр Scope в `Get-Variable` или `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="ac421-144">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="ac421-145">Например, чтобы получить все переменные в локальной области, введите:</span><span class="sxs-lookup"><span data-stu-id="ac421-145">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="ac421-146">Чтобы получить все переменные в глобальной области, введите:</span><span class="sxs-lookup"><span data-stu-id="ac421-146">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="ac421-147">Модификаторы области</span><span class="sxs-lookup"><span data-stu-id="ac421-147">Scope Modifiers</span></span>

<span data-ttu-id="ac421-148">Имя переменной, псевдонима или функции может содержать один из следующих необязательных модификаторов области:</span><span class="sxs-lookup"><span data-stu-id="ac421-148">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="ac421-149">`global:` — Указывает, что имя существует в **глобальной** области.</span><span class="sxs-lookup"><span data-stu-id="ac421-149">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="ac421-150">`local:` — Указывает, что имя существует в **локальной** области.</span><span class="sxs-lookup"><span data-stu-id="ac421-150">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="ac421-151">Текущая область всегда является **локальной** .</span><span class="sxs-lookup"><span data-stu-id="ac421-151">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="ac421-152">`private:` — Указывает, что имя является **частным** и видимым только для текущей области.</span><span class="sxs-lookup"><span data-stu-id="ac421-152">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="ac421-153">`script:` — Указывает, что имя существует в области **скрипта** .</span><span class="sxs-lookup"><span data-stu-id="ac421-153">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="ac421-154">Область **скрипта** является ближайшим областью файла скрипта-предка или **глобальным** , если не существует ближайшего файла скрипта-предка.</span><span class="sxs-lookup"><span data-stu-id="ac421-154">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="ac421-155">`using:` — Используется для доступа к переменным, определенным в другой области, при выполнении скриптов с помощью таких командлетов `Start-Job` , как и `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="ac421-155">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="ac421-156">`workflow:` — Указывает, что имя существует в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ac421-156">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="ac421-157">Примечание. рабочие процессы не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="ac421-157">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="ac421-158">`<variable-namespace>` — Модификатор, созданный поставщиком PSDrive PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac421-158">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="ac421-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="ac421-159">For example:</span></span>

  |  <span data-ttu-id="ac421-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ac421-160">Namespace</span></span>  |                    <span data-ttu-id="ac421-161">Описание</span><span class="sxs-lookup"><span data-stu-id="ac421-161">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="ac421-162">Псевдонимы, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="ac421-162">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="ac421-163">Переменные среды, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="ac421-163">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="ac421-164">Функции, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="ac421-164">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="ac421-165">Переменные, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="ac421-165">Variables defined in the current scope</span></span>             |

<span data-ttu-id="ac421-166">По умолчанию для скриптов используется область скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac421-166">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="ac421-167">Областью действия по умолчанию для функций и псевдонимов является локальная область, даже если они определены в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ac421-167">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="ac421-168">Использование модификаторов области</span><span class="sxs-lookup"><span data-stu-id="ac421-168">Using scope modifiers</span></span>

<span data-ttu-id="ac421-169">Чтобы указать область новой переменной, псевдонима или функции, используйте модификатор области.</span><span class="sxs-lookup"><span data-stu-id="ac421-169">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="ac421-170">Синтаксис модификатора области в переменной:</span><span class="sxs-lookup"><span data-stu-id="ac421-170">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="ac421-171">Синтаксис модификатора области в функции:</span><span class="sxs-lookup"><span data-stu-id="ac421-171">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="ac421-172">Следующая команда, не использующая модификатор области, создает переменную в текущей или **локальной** области:</span><span class="sxs-lookup"><span data-stu-id="ac421-172">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="ac421-173">Чтобы создать ту же переменную в **глобальной** области, используйте модификатор scope `global:` :</span><span class="sxs-lookup"><span data-stu-id="ac421-173">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="ac421-174">Чтобы создать ту же переменную в области **скрипта** , используйте `script:` Модификатор scope:</span><span class="sxs-lookup"><span data-stu-id="ac421-174">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="ac421-175">Кроме того, можно использовать модификатор области с функциями.</span><span class="sxs-lookup"><span data-stu-id="ac421-175">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="ac421-176">Следующее определение функции создает функцию в **глобальной** области видимости:</span><span class="sxs-lookup"><span data-stu-id="ac421-176">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="ac421-177">Кроме того, можно использовать модификаторы области для ссылки на переменную в другой области.</span><span class="sxs-lookup"><span data-stu-id="ac421-177">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="ac421-178">Следующая команда ссылается на `$test` переменную, сначала в локальной области, а затем в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="ac421-178">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="ac421-179">`Using:`Модификатор области видимости</span><span class="sxs-lookup"><span data-stu-id="ac421-179">The `Using:` scope modifier</span></span>

<span data-ttu-id="ac421-180">Использование — это специальный модификатор области, который определяет локальную переменную в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="ac421-180">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="ac421-181">Без модификатора PowerShell требует, чтобы переменные в удаленных командах были определены в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ac421-181">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="ac421-182">`Using`Модификатор области представлен в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ac421-182">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="ac421-183">Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="ac421-183">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="ac421-184">`Using`Модификатор области поддерживается в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ac421-184">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="ac421-185">Удаленно выполненные команды, запущенные с `Invoke-Command` использованием параметров **ComputerName** , **HostName** , **сшконнектион** или **Session** (удаленный сеанс)</span><span class="sxs-lookup"><span data-stu-id="ac421-185">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="ac421-186">Фоновые задания, запущенные с помощью `Start-Job` (вне процесса)</span><span class="sxs-lookup"><span data-stu-id="ac421-186">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="ac421-187">Задания потоков, запущенные через `Start-ThreadJob` или `ForEach-Object -Parallel` (отдельный сеанс потока)</span><span class="sxs-lookup"><span data-stu-id="ac421-187">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="ac421-188">В зависимости от контекста значения внедренных переменных — это либо независимые копии данных в области вызывающего объекта, либо ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="ac421-188">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="ac421-189">В удаленных и необработанных сеансах они всегда являются независимыми копиями.</span><span class="sxs-lookup"><span data-stu-id="ac421-189">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="ac421-190">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ac421-190">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="ac421-191">В сеансах потока они передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="ac421-191">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="ac421-192">Это означает, что переменные области вызовов можно изменять в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="ac421-192">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="ac421-193">Для безопасного изменения переменных требуется синхронизация потоков.</span><span class="sxs-lookup"><span data-stu-id="ac421-193">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="ac421-194">Дополнительные сведения см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="ac421-194">For more information see:</span></span>

- [<span data-ttu-id="ac421-195">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="ac421-195">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)
- [<span data-ttu-id="ac421-196">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="ac421-196">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="ac421-197">Сериализация значений переменных</span><span class="sxs-lookup"><span data-stu-id="ac421-197">Serialization of variable values</span></span>

<span data-ttu-id="ac421-198">Удаленные команды и фоновые задания выполняются вне процесса.</span><span class="sxs-lookup"><span data-stu-id="ac421-198">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="ac421-199">Необработанные сеансы используют сериализацию и десериализацию на основе XML, чтобы сделать значения переменных доступными через границы процесса.</span><span class="sxs-lookup"><span data-stu-id="ac421-199">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="ac421-200">Процесс сериализации преобразует объекты в **PSObject** , который содержит исходные свойства объектов, но не его методы.</span><span class="sxs-lookup"><span data-stu-id="ac421-200">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="ac421-201">Для ограниченного набора типов десериализация восстанавливает объекты обратно в исходный тип.</span><span class="sxs-lookup"><span data-stu-id="ac421-201">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="ac421-202">Восстановленный объект является копией исходного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="ac421-202">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="ac421-203">Он содержит свойства и методы типа.</span><span class="sxs-lookup"><span data-stu-id="ac421-203">It has the type properties and methods.</span></span> <span data-ttu-id="ac421-204">Для простых типов, таких как **System. Version** , копия является точной.</span><span class="sxs-lookup"><span data-stu-id="ac421-204">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="ac421-205">Для сложных типов копия — неидеальны.</span><span class="sxs-lookup"><span data-stu-id="ac421-205">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="ac421-206">Например, rehydratя объектов сертификатов не включает закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ac421-206">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="ac421-207">Экземпляры всех остальных типов являются экземплярами **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="ac421-207">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="ac421-208">Свойство **PSTypeNames** содержит имя исходного типа с префиксом **десериализации** , например **Deserialized.SysTEM. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="ac421-208">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="ac421-209">Параметр AllScope</span><span class="sxs-lookup"><span data-stu-id="ac421-209">The AllScope Option</span></span>

<span data-ttu-id="ac421-210">Переменные и псевдонимы имеют свойство **Option** , которое может принимать значение **AllScope** .</span><span class="sxs-lookup"><span data-stu-id="ac421-210">Variables and aliases have an **Option** property that can take a value of **AllScope** .</span></span> <span data-ttu-id="ac421-211">Элементы, имеющие свойство **AllScope** , становятся частью любых создаваемых дочерних областей, хотя они не задним числом наследуются родительскими областями.</span><span class="sxs-lookup"><span data-stu-id="ac421-211">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="ac421-212">Элемент, имеющий свойство **AllScope** , отображается в дочерней области и является частью этой области.</span><span class="sxs-lookup"><span data-stu-id="ac421-212">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="ac421-213">Изменения элемента в любой области влияют на все области, в которых определена переменная.</span><span class="sxs-lookup"><span data-stu-id="ac421-213">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="ac421-214">Управление областью</span><span class="sxs-lookup"><span data-stu-id="ac421-214">Managing Scope</span></span>

<span data-ttu-id="ac421-215">Несколько командлетов имеют параметр **области** , который позволяет получать или задавать (создавать и изменять) элементы в определенной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-215">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="ac421-216">Используйте следующую команду, чтобы найти все командлеты в сеансе с параметром **области** :</span><span class="sxs-lookup"><span data-stu-id="ac421-216">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="ac421-217">Чтобы найти переменные, видимые в определенной области, используйте `Scope` параметр `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="ac421-217">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="ac421-218">Видимые переменные включают в себя глобальные переменные, переменные в родительской области и переменные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ac421-218">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="ac421-219">Например, следующая команда получает переменные, видимые в локальной области:</span><span class="sxs-lookup"><span data-stu-id="ac421-219">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="ac421-220">Чтобы создать переменную в определенной области, используйте модификатор области или параметр **Scope** в `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="ac421-220">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="ac421-221">Следующая команда создает переменную в глобальной области видимости:</span><span class="sxs-lookup"><span data-stu-id="ac421-221">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="ac421-222">Для указания области можно также использовать параметр scope `New-Alias` `Set-Alias` командлетов, или `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="ac421-222">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="ac421-223">Следующая команда создает псевдоним в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="ac421-223">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="ac421-224">Чтобы получить функции в определенной области, используйте `Get-Item` командлет в области.</span><span class="sxs-lookup"><span data-stu-id="ac421-224">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="ac421-225">`Get-Item`Командлет не имеет параметра **области** .</span><span class="sxs-lookup"><span data-stu-id="ac421-225">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="ac421-226">Для командлетов, использующих параметр **области** , можно также ссылаться на области по числу.</span><span class="sxs-lookup"><span data-stu-id="ac421-226">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="ac421-227">Число описывает относительное расположение одной области в другую.</span><span class="sxs-lookup"><span data-stu-id="ac421-227">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="ac421-228">Область 0 представляет текущую или локальную область.</span><span class="sxs-lookup"><span data-stu-id="ac421-228">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="ac421-229">Область 1 указывает непосредственную родительскую область.</span><span class="sxs-lookup"><span data-stu-id="ac421-229">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="ac421-230">Область 2 указывает родителя родительской области и т. д.</span><span class="sxs-lookup"><span data-stu-id="ac421-230">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="ac421-231">Пронумерованные области полезны, если создано много рекурсивных областей.</span><span class="sxs-lookup"><span data-stu-id="ac421-231">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="ac421-232">Использование нотации источника точки с областью видимости</span><span class="sxs-lookup"><span data-stu-id="ac421-232">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="ac421-233">Сценарии и функции соответствуют всем правилам области.</span><span class="sxs-lookup"><span data-stu-id="ac421-233">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="ac421-234">Они создаются в определенной области и влияют только на эту область, если только не используется параметр командлета или модификатор области для изменения этой области.</span><span class="sxs-lookup"><span data-stu-id="ac421-234">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="ac421-235">Однако можно добавить скрипт или функцию в текущую область с помощью точечной нотации источника.</span><span class="sxs-lookup"><span data-stu-id="ac421-235">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="ac421-236">Затем, когда сценарий выполняется в текущей области, все функции, псевдонимы и переменные, создаваемые сценарием, доступны в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ac421-236">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="ac421-237">Чтобы добавить функцию в текущую область, введите точку (.) и пробел перед путем и именем функции в вызове функции.</span><span class="sxs-lookup"><span data-stu-id="ac421-237">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="ac421-238">Например, чтобы запустить скрипт Sample.ps1 из каталога C:\Scripts в области скрипта (по умолчанию для сценариев), используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac421-238">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="ac421-239">Чтобы запустить скрипт Sample.ps1 в локальной области, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac421-239">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="ac421-240">При использовании оператора Call (&) для выполнения функции или скрипта он не добавляется в текущую область.</span><span class="sxs-lookup"><span data-stu-id="ac421-240">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="ac421-241">В следующем примере используется оператор Call:</span><span class="sxs-lookup"><span data-stu-id="ac421-241">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="ac421-242">Дополнительные сведения о операторе Call можно узнать в [about_operators](about_operators.md).</span><span class="sxs-lookup"><span data-stu-id="ac421-242">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="ac421-243">Любые псевдонимы, функции или переменные, создаваемые сценарием Sample.ps1, недоступны в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ac421-243">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="ac421-244">Ограничение без области</span><span class="sxs-lookup"><span data-stu-id="ac421-244">Restricting Without Scope</span></span>

<span data-ttu-id="ac421-245">Несколько концепций PowerShell похожи на область или взаимодействуют с областью действия.</span><span class="sxs-lookup"><span data-stu-id="ac421-245">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="ac421-246">Эти понятия можно путать с областью действия или поведением области.</span><span class="sxs-lookup"><span data-stu-id="ac421-246">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="ac421-247">Сеансы, модули и вложенные запросы являются автономными средами, но они не являются дочерними областями глобальной области в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ac421-247">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="ac421-248">Сеансы</span><span class="sxs-lookup"><span data-stu-id="ac421-248">Sessions</span></span>

<span data-ttu-id="ac421-249">Сеанс — это среда, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac421-249">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="ac421-250">При создании сеанса на удаленном компьютере PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ac421-250">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="ac421-251">Постоянное подключение позволяет использовать сеанс для нескольких связанных команд.</span><span class="sxs-lookup"><span data-stu-id="ac421-251">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="ac421-252">Поскольку сеанс является автономной средой, он имеет собственную область, но сеанс не является дочерней областью сеанса, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="ac421-252">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="ac421-253">Сеанс начинается с собственной глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-253">The session starts with its own global scope.</span></span> <span data-ttu-id="ac421-254">Эта область не зависит от глобальной области действия сеанса.</span><span class="sxs-lookup"><span data-stu-id="ac421-254">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="ac421-255">В сеансе можно создать дочерние области.</span><span class="sxs-lookup"><span data-stu-id="ac421-255">You can create child scopes in the session.</span></span> <span data-ttu-id="ac421-256">Например, можно выполнить сценарий для создания дочерней области в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ac421-256">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="ac421-257">Модули</span><span class="sxs-lookup"><span data-stu-id="ac421-257">Modules</span></span>

<span data-ttu-id="ac421-258">Вы можете использовать модуль PowerShell для совместного использования и доставки средств PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac421-258">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="ac421-259">Модуль — это единица, которая может содержать командлеты, скрипты, функции, переменные, псевдонимы и другие полезные элементы.</span><span class="sxs-lookup"><span data-stu-id="ac421-259">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="ac421-260">Если явно не определено, элементы в модуле недоступны за пределами модуля.</span><span class="sxs-lookup"><span data-stu-id="ac421-260">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="ac421-261">Таким образом, можно добавить модуль в сеанс и использовать открытые элементы, не заботясь о том, что другие элементы могут переопределять командлеты, сценарии, функции и другие элементы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ac421-261">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="ac421-262">По умолчанию модули загружаются в верхний уровень текущего _состояния сеанса_ , а не в текущую _область_ .</span><span class="sxs-lookup"><span data-stu-id="ac421-262">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_ .</span></span> <span data-ttu-id="ac421-263">Текущее состояние сеанса может быть состоянием сеанса модуля или глобальным состоянием сеанса.</span><span class="sxs-lookup"><span data-stu-id="ac421-263">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="ac421-264">Добавление модуля в сеанс не приводит к изменению области.</span><span class="sxs-lookup"><span data-stu-id="ac421-264">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="ac421-265">Если вы используете глобальную область, модули загружаются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="ac421-265">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="ac421-266">Все операции экспорта помещаются в глобальные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ac421-266">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="ac421-267">При загрузке _Module2 из Module1_ Module2 загружается в состояние сеанса Module1, а не в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="ac421-267">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="ac421-268">Все операции экспорта из Module2 размещаются в верхней части состояния сеанса Module1.</span><span class="sxs-lookup"><span data-stu-id="ac421-268">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="ac421-269">Если используется `Import-Module -Scope local` , то экспорты помещаются в текущий объект области, а не на верхний уровень.</span><span class="sxs-lookup"><span data-stu-id="ac421-269">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="ac421-270">Если вы используете _модуль_ и используете `Import-Module -Scope global` (или `Import-Module -Global` ) для загрузки другого модуля, этот модуль и его экспорты загружаются в глобальное состояние сеанса, а не в локальное состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="ac421-270">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="ac421-271">Эта функция предназначена для написания модуля, который управляет модулями.</span><span class="sxs-lookup"><span data-stu-id="ac421-271">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="ac421-272">Модуль **виндовскомпатибилити** выполняет это для импорта прокси-модулей в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="ac421-272">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="ac421-273">В состоянии сеанса модули имеют собственную область действия.</span><span class="sxs-lookup"><span data-stu-id="ac421-273">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="ac421-274">Рассмотрим следующий модуль `C:\temp\mod1.psm1` :</span><span class="sxs-lookup"><span data-stu-id="ac421-274">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="ac421-275">Теперь создадим глобальную переменную `$a` , присвойте ей значение и вызовите функцию **foo** .</span><span class="sxs-lookup"><span data-stu-id="ac421-275">Now we create a global variable `$a`, give it a value and call the function **foo** .</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="ac421-276">Модуль объявляет переменную `$a` в области модуля, а функция **foo** выводит значение переменной в обеих областях.</span><span class="sxs-lookup"><span data-stu-id="ac421-276">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="ac421-277">Вложенные запросы</span><span class="sxs-lookup"><span data-stu-id="ac421-277">Nested Prompts</span></span>

<span data-ttu-id="ac421-278">Вложенные запросы не имеют собственной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-278">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="ac421-279">При вводе вложенного запроса вложенный запрос является подмножеством среды.</span><span class="sxs-lookup"><span data-stu-id="ac421-279">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="ac421-280">Но остается в локальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-280">But, you remain within the local scope.</span></span>

<span data-ttu-id="ac421-281">Скрипты имеют собственную область действия.</span><span class="sxs-lookup"><span data-stu-id="ac421-281">Scripts do have their own scope.</span></span> <span data-ttu-id="ac421-282">При отладке скрипта и достижении точки останова в скрипте необходимо ввести область скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac421-282">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="ac421-283">Частный вариант</span><span class="sxs-lookup"><span data-stu-id="ac421-283">Private Option</span></span>

<span data-ttu-id="ac421-284">Псевдонимы и переменные имеют свойство **Option** , которое может принимать значение **Private** .</span><span class="sxs-lookup"><span data-stu-id="ac421-284">Aliases and variables have an **Option** property that can take a value of **Private** .</span></span> <span data-ttu-id="ac421-285">Элементы с **закрытым** параметром можно просматривать и изменять в области, в которой они создаются, но их нельзя просматривать или изменять вне этой области.</span><span class="sxs-lookup"><span data-stu-id="ac421-285">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="ac421-286">Например, если вы создаете переменную с частным параметром в глобальной области, а затем выполняете сценарий, `Get-Variable` команды в скрипте не отображают закрытую переменную.</span><span class="sxs-lookup"><span data-stu-id="ac421-286">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="ac421-287">Использование модификатора глобальной области в этом экземпляре не приводит к отображению закрытой переменной.</span><span class="sxs-lookup"><span data-stu-id="ac421-287">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="ac421-288">Можно использовать параметр Option `New-Variable` `Set-Variable` `New-Alias` командлетов,,, и, `Set-Alias` чтобы задать для свойства параметра значение Private.</span><span class="sxs-lookup"><span data-stu-id="ac421-288">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="ac421-289">Видимость</span><span class="sxs-lookup"><span data-stu-id="ac421-289">Visibility</span></span>

<span data-ttu-id="ac421-290">Свойство **видимости** переменной или псевдонима определяет, можно ли видеть элемент за пределами контейнера, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="ac421-290">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="ac421-291">Контейнером может быть модуль, сценарий или оснастка.</span><span class="sxs-lookup"><span data-stu-id="ac421-291">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="ac421-292">Видимость предназначена для контейнеров так же, как и **закрытое** значение свойства **Option** для областей.</span><span class="sxs-lookup"><span data-stu-id="ac421-292">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="ac421-293">Свойство **Visibility** принимает **открытые** и **закрытые** значения.</span><span class="sxs-lookup"><span data-stu-id="ac421-293">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="ac421-294">Элементы, имеющие закрытую видимость, можно просматривать и изменять только в контейнере, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="ac421-294">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="ac421-295">Если контейнер добавлен или импортирован, элементы, имеющие закрытую видимость, не могут быть просмотрены или изменены.</span><span class="sxs-lookup"><span data-stu-id="ac421-295">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="ac421-296">Поскольку видимость предназначена для контейнеров, она работает по-разному в области.</span><span class="sxs-lookup"><span data-stu-id="ac421-296">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="ac421-297">При создании элемента с закрытой видимостью в глобальной области нельзя просматривать или изменять элемент в какой бы то ни было области.</span><span class="sxs-lookup"><span data-stu-id="ac421-297">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="ac421-298">При попытке просмотра или изменения значения переменной, имеющей закрытую видимость, PowerShell возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ac421-298">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="ac421-299">`New-Variable` `Set-Variable` Для создания переменной с закрытой видимостью можно использовать командлеты и.</span><span class="sxs-lookup"><span data-stu-id="ac421-299">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="ac421-300">Примеры</span><span class="sxs-lookup"><span data-stu-id="ac421-300">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="ac421-301">Пример 1. изменение значения переменной только в скрипте</span><span class="sxs-lookup"><span data-stu-id="ac421-301">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="ac421-302">Следующая команда изменяет значение `$ConfirmPreference` переменной в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ac421-302">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="ac421-303">Изменение не влияет на глобальную область.</span><span class="sxs-lookup"><span data-stu-id="ac421-303">The change does not affect the global scope.</span></span>

<span data-ttu-id="ac421-304">Сначала для вывода значения `$ConfirmPreference` переменной в локальной области используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac421-304">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="ac421-305">Создайте скрипт Scope.ps1, который содержит следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ac421-305">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="ac421-306">Выполните скрипт.</span><span class="sxs-lookup"><span data-stu-id="ac421-306">Run the script.</span></span> <span data-ttu-id="ac421-307">Скрипт изменяет значение `$ConfirmPreference` переменной, а затем сообщает свое значение в области скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac421-307">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="ac421-308">Выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac421-308">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="ac421-309">Затем проверьте текущее значение `$ConfirmPreference` переменной в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ac421-309">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="ac421-310">В этом примере показано, что изменения значения переменной в области скрипта не влияют на значение переменной в родительской области.</span><span class="sxs-lookup"><span data-stu-id="ac421-310">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="ac421-311">Пример 2. Просмотр значения переменной в разных областях</span><span class="sxs-lookup"><span data-stu-id="ac421-311">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="ac421-312">Модификаторы области можно использовать для просмотра значения переменной в локальной области и в родительской области.</span><span class="sxs-lookup"><span data-stu-id="ac421-312">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="ac421-313">Сначала определите `$test` переменную в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-313">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="ac421-314">Затем создайте скрипт Sample.ps1, определяющий `$test` переменную.</span><span class="sxs-lookup"><span data-stu-id="ac421-314">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="ac421-315">В скрипте используйте модификатор области для ссылки на глобальную или локальную версию `$test` переменной.</span><span class="sxs-lookup"><span data-stu-id="ac421-315">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="ac421-316">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="ac421-316">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="ac421-317">При запуске Sample.ps1 выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac421-317">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="ac421-318">По завершении скрипта `$test` в сеансе определяется только глобальное значение.</span><span class="sxs-lookup"><span data-stu-id="ac421-318">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="ac421-319">Пример 3. изменение значения переменной в родительской области</span><span class="sxs-lookup"><span data-stu-id="ac421-319">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="ac421-320">Если вы не защищаете элемент с помощью параметра private или другого метода, то можете просмотреть и изменить значение переменной в родительской области.</span><span class="sxs-lookup"><span data-stu-id="ac421-320">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="ac421-321">Сначала определите `$test` переменную в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-321">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="ac421-322">Затем создайте скрипт Sample.ps1, определяющий `$test` переменную.</span><span class="sxs-lookup"><span data-stu-id="ac421-322">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="ac421-323">В скрипте используйте модификатор области для ссылки на глобальную или локальную версию `$test` переменной.</span><span class="sxs-lookup"><span data-stu-id="ac421-323">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="ac421-324">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="ac421-324">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="ac421-325">По завершении скрипта изменяется глобальное значение `$test` .</span><span class="sxs-lookup"><span data-stu-id="ac421-325">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="ac421-326">Пример 4. Создание закрытой переменной</span><span class="sxs-lookup"><span data-stu-id="ac421-326">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="ac421-327">Частная переменная — это переменная, которая имеет свойство **Option** со значением *Private* .</span><span class="sxs-lookup"><span data-stu-id="ac421-327">A private variable is a variable that has an **Option** property that has a value of *Private* .</span></span> <span data-ttu-id="ac421-328">*Закрытые* переменные наследуются дочерней областью, но их можно просматривать или изменять только в области, в которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="ac421-328">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="ac421-329">Следующая команда создает закрытую переменную с именем `$ptest` в локальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-329">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="ac421-330">Можно отобразить и изменить значение `$ptest` в локальной области.</span><span class="sxs-lookup"><span data-stu-id="ac421-330">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="ac421-331">Затем создайте скрипт Sample.ps1, содержащий следующие команды.</span><span class="sxs-lookup"><span data-stu-id="ac421-331">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="ac421-332">Команда пытается отобразить и изменить значение `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="ac421-332">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="ac421-333">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="ac421-333">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="ac421-334">`$ptest`Переменная не видна в области скрипта, выходные данные пусты.</span><span class="sxs-lookup"><span data-stu-id="ac421-334">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="ac421-335">Пример 5. Использование локальной переменной в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="ac421-335">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="ac421-336">Для переменных в удаленной команде, созданной в локальном сеансе, используйте `Using` Модификатор области.</span><span class="sxs-lookup"><span data-stu-id="ac421-336">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="ac421-337">В PowerShell предполагается, что переменные в удаленных командах были созданы в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ac421-337">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="ac421-338">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ac421-338">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="ac421-339">Например, следующие команды создают `$Cred` переменную в локальном сеансе, а затем используют эту `$Cred` переменную в удаленной команде:</span><span class="sxs-lookup"><span data-stu-id="ac421-339">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="ac421-340">Область использования была введена в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ac421-340">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="ac421-341">В PowerShell 2,0, чтобы указать, что переменная была создана в локальном сеансе, используйте следующий формат команды.</span><span class="sxs-lookup"><span data-stu-id="ac421-341">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="ac421-342">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ac421-342">See also</span></span>

[<span data-ttu-id="ac421-343">about_Variables</span><span class="sxs-lookup"><span data-stu-id="ac421-343">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="ac421-344">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="ac421-344">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="ac421-345">about_Functions</span><span class="sxs-lookup"><span data-stu-id="ac421-345">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="ac421-346">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="ac421-346">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="ac421-347">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="ac421-347">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)


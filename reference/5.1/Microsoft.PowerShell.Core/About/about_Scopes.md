---
description: Объясняет концепцию Scope в PowerShell и показывает, как устанавливать и изменять область элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 6a86348bb70afdcbd8ffe00339d1597efd8f88c4
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354581"
---
# <a name="about-scopes"></a><span data-ttu-id="209bc-104">Сведения об областях</span><span class="sxs-lookup"><span data-stu-id="209bc-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="209bc-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="209bc-105">Short description</span></span>
<span data-ttu-id="209bc-106">Объясняет концепцию Scope в PowerShell и показывает, как устанавливать и изменять область элементов.</span><span class="sxs-lookup"><span data-stu-id="209bc-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="209bc-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="209bc-107">Long description</span></span>

<span data-ttu-id="209bc-108">PowerShell защищает доступ к переменным, псевдонимам, функциям и дискам PowerShell (Псдривес), ограничивая место для чтения и изменения.</span><span class="sxs-lookup"><span data-stu-id="209bc-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="209bc-109">PowerShell использует правила области, чтобы предотвратить случайное изменение элемента, который не должен изменяться.</span><span class="sxs-lookup"><span data-stu-id="209bc-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="209bc-110">Ниже приведены основные правила области.</span><span class="sxs-lookup"><span data-stu-id="209bc-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="209bc-111">Области могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="209bc-111">Scopes may nest.</span></span> <span data-ttu-id="209bc-112">Внешняя область называется родительской областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="209bc-113">Все вложенные области являются дочерними областями этого родителя.</span><span class="sxs-lookup"><span data-stu-id="209bc-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="209bc-114">Элемент отображается в области, в которой он был создан, и во всех дочерних областях, если вы явно не сделаете его частным.</span><span class="sxs-lookup"><span data-stu-id="209bc-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="209bc-115">Вы можете разместить переменные, псевдонимы, функции или диски PowerShell в одной или нескольких областях.</span><span class="sxs-lookup"><span data-stu-id="209bc-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="209bc-116">Элемент, созданный в области, может быть изменен только в той области, в которой она была создана, если только вы явно не указали другую область.</span><span class="sxs-lookup"><span data-stu-id="209bc-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="209bc-117">При создании элемента в области и его имени вместе с элементом в другой области исходный элемент может быть скрыт под новым элементом, но не переопределен или не изменен.</span><span class="sxs-lookup"><span data-stu-id="209bc-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="209bc-118">Области PowerShell</span><span class="sxs-lookup"><span data-stu-id="209bc-118">PowerShell Scopes</span></span>

<span data-ttu-id="209bc-119">PowerShell поддерживает следующие области:</span><span class="sxs-lookup"><span data-stu-id="209bc-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="209bc-120">Global — область, которая действует при запуске PowerShell или при создании нового сеанса или пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="209bc-120">Global: The scope that is in effect when PowerShell starts or when you create a new session or runspace.</span></span> <span data-ttu-id="209bc-121">Переменные и функции, которые имеются при запуске PowerShell в глобальной области, такие как автоматические переменные и привилегированные переменные.</span><span class="sxs-lookup"><span data-stu-id="209bc-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="209bc-122">Переменные, псевдонимы и функции в профилях PowerShell также создаются в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span> <span data-ttu-id="209bc-123">Глобальная область — это корневая родительская область в сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-123">The global scope is the root parent scope in a session.</span></span>

- <span data-ttu-id="209bc-124">Local: текущая область.</span><span class="sxs-lookup"><span data-stu-id="209bc-124">Local: The current scope.</span></span> <span data-ttu-id="209bc-125">Локальная область может быть глобальной или любой другой областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-125">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="209bc-126">Скрипт: область, созданная во время выполнения файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="209bc-126">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="209bc-127">В области скрипта выполняются только команды в скрипте.</span><span class="sxs-lookup"><span data-stu-id="209bc-127">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="209bc-128">Для команд в скрипте областью скрипта является локальная область.</span><span class="sxs-lookup"><span data-stu-id="209bc-128">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="209bc-129">**Частный** не является областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-129">**Private** is not a scope.</span></span> <span data-ttu-id="209bc-130">Это [параметр](#private-option) , который изменяет видимость элемента за пределами области, в которой определен элемент.</span><span class="sxs-lookup"><span data-stu-id="209bc-130">It is an [option](#private-option) that changes the visibility of an item outside of the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="209bc-131">Родительские и дочерние области</span><span class="sxs-lookup"><span data-stu-id="209bc-131">Parent and Child Scopes</span></span>

<span data-ttu-id="209bc-132">Новую дочернюю область можно создать путем вызова скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="209bc-132">You can create a new child scope by calling a script or function.</span></span> <span data-ttu-id="209bc-133">Вызывающая область является родительской областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-133">The calling scope is the parent scope.</span></span> <span data-ttu-id="209bc-134">Вызываемый скрипт или функция является дочерней областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-134">The called script or function is the child scope.</span></span>
<span data-ttu-id="209bc-135">Вызываемые функции или скрипты могут вызывать другие функции, создавая иерархию дочерних областей, корневая область которых является глобальной областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-135">The functions or scripts you call may call other functions, creating a hierarchy of child scopes whose root scope is the global scope.</span></span>

<span data-ttu-id="209bc-136">Если явно не сделать элементы закрытыми, элементы в родительской области становятся доступными для дочерней области.</span><span class="sxs-lookup"><span data-stu-id="209bc-136">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="209bc-137">Однако элементы, создаваемые и изменяемые в дочерней области, не влияют на родительскую область, если только при создании элементов не будет явно задана область.</span><span class="sxs-lookup"><span data-stu-id="209bc-137">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

> [!NOTE]
> <span data-ttu-id="209bc-138">Функции из модуля не выполняются в дочерней области вызывающей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-138">Functions from a module do not run in a child scope of the calling scope.</span></span>
> <span data-ttu-id="209bc-139">Модули имеют собственное состояние сеанса, связанное с глобальной областью.</span><span class="sxs-lookup"><span data-stu-id="209bc-139">Modules have their own session state that is linked to the global scope.</span></span>
> <span data-ttu-id="209bc-140">Весь код модуля выполняется в иерархии областей, относящихся к конкретному модулю, имеющей собственную корневую область.</span><span class="sxs-lookup"><span data-stu-id="209bc-140">All module code runs in a module-specific hierarchy of scopes that has its own root scope.</span></span>

## <a name="inheritance"></a><span data-ttu-id="209bc-141">Наследование</span><span class="sxs-lookup"><span data-stu-id="209bc-141">Inheritance</span></span>

<span data-ttu-id="209bc-142">Дочерняя область не наследует переменные, псевдонимы и функции из родительской области.</span><span class="sxs-lookup"><span data-stu-id="209bc-142">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="209bc-143">Если элемент не является частным, дочерняя область может просматривать элементы в родительской области.</span><span class="sxs-lookup"><span data-stu-id="209bc-143">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="209bc-144">Кроме того, он может изменить элементы, явно указав родительскую область, но элементы не являются частью дочерней области.</span><span class="sxs-lookup"><span data-stu-id="209bc-144">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="209bc-145">Однако дочерняя область создается с набором элементов.</span><span class="sxs-lookup"><span data-stu-id="209bc-145">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="209bc-146">Как правило, он включает все псевдонимы с параметром **AllScope** .</span><span class="sxs-lookup"><span data-stu-id="209bc-146">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="209bc-147">Этот параметр обсуждается далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="209bc-147">This option is discussed later in this article.</span></span> <span data-ttu-id="209bc-148">Он включает все переменные с параметром **AllScope** , а также некоторые автоматические переменные.</span><span class="sxs-lookup"><span data-stu-id="209bc-148">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="209bc-149">Чтобы найти элементы в определенной области, используйте параметр Scope в `Get-Variable` или `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="209bc-149">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="209bc-150">Например, чтобы получить все переменные в локальной области, введите:</span><span class="sxs-lookup"><span data-stu-id="209bc-150">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="209bc-151">Чтобы получить все переменные в глобальной области, введите:</span><span class="sxs-lookup"><span data-stu-id="209bc-151">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="209bc-152">Модификаторы области</span><span class="sxs-lookup"><span data-stu-id="209bc-152">Scope Modifiers</span></span>

<span data-ttu-id="209bc-153">Имя переменной, псевдонима или функции может содержать один из следующих необязательных модификаторов области:</span><span class="sxs-lookup"><span data-stu-id="209bc-153">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="209bc-154">`global:` — Указывает, что имя существует в **глобальной** области.</span><span class="sxs-lookup"><span data-stu-id="209bc-154">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="209bc-155">`local:` — Указывает, что имя существует в **локальной** области.</span><span class="sxs-lookup"><span data-stu-id="209bc-155">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="209bc-156">Текущая область всегда является **локальной** .</span><span class="sxs-lookup"><span data-stu-id="209bc-156">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="209bc-157">`private:` — Указывает, что имя является **частным** и видимым только для текущей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-157">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="209bc-158">`script:` — Указывает, что имя существует в области **скрипта** .</span><span class="sxs-lookup"><span data-stu-id="209bc-158">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="209bc-159">Область **скрипта** является ближайшим областью файла скрипта-предка или **глобальным** , если не существует ближайшего файла скрипта-предка.</span><span class="sxs-lookup"><span data-stu-id="209bc-159">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="209bc-160">`using:` — Используется для доступа к переменным, определенным в другой области, при выполнении скриптов с помощью таких командлетов `Start-Job` , как и `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="209bc-160">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="209bc-161">`workflow:` — Указывает, что имя существует в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="209bc-161">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="209bc-162">Примечание. рабочие процессы не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="209bc-162">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="209bc-163">`<variable-namespace>` — Модификатор, созданный поставщиком PSDrive PowerShell.</span><span class="sxs-lookup"><span data-stu-id="209bc-163">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="209bc-164">Пример:</span><span class="sxs-lookup"><span data-stu-id="209bc-164">For example:</span></span>

  |  <span data-ttu-id="209bc-165">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="209bc-165">Namespace</span></span>  |                    <span data-ttu-id="209bc-166">Описание</span><span class="sxs-lookup"><span data-stu-id="209bc-166">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="209bc-167">Псевдонимы, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="209bc-167">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="209bc-168">Переменные среды, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="209bc-168">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="209bc-169">Функции, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="209bc-169">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="209bc-170">Переменные, определенные в текущей области</span><span class="sxs-lookup"><span data-stu-id="209bc-170">Variables defined in the current scope</span></span>             |

<span data-ttu-id="209bc-171">По умолчанию для скриптов используется область скрипта.</span><span class="sxs-lookup"><span data-stu-id="209bc-171">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="209bc-172">Областью действия по умолчанию для функций и псевдонимов является локальная область, даже если они определены в скрипте.</span><span class="sxs-lookup"><span data-stu-id="209bc-172">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="209bc-173">Использование модификаторов области</span><span class="sxs-lookup"><span data-stu-id="209bc-173">Using scope modifiers</span></span>

<span data-ttu-id="209bc-174">Чтобы указать область новой переменной, псевдонима или функции, используйте модификатор области.</span><span class="sxs-lookup"><span data-stu-id="209bc-174">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="209bc-175">Синтаксис модификатора области в переменной:</span><span class="sxs-lookup"><span data-stu-id="209bc-175">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="209bc-176">Синтаксис модификатора области в функции:</span><span class="sxs-lookup"><span data-stu-id="209bc-176">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="209bc-177">Следующая команда, не использующая модификатор области, создает переменную в текущей или **локальной** области:</span><span class="sxs-lookup"><span data-stu-id="209bc-177">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="209bc-178">Чтобы создать ту же переменную в **глобальной** области, используйте модификатор scope `global:` :</span><span class="sxs-lookup"><span data-stu-id="209bc-178">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="209bc-179">Чтобы создать ту же переменную в области **скрипта** , используйте `script:` Модификатор scope:</span><span class="sxs-lookup"><span data-stu-id="209bc-179">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="209bc-180">Кроме того, можно использовать модификатор области с функциями.</span><span class="sxs-lookup"><span data-stu-id="209bc-180">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="209bc-181">Следующее определение функции создает функцию в **глобальной** области видимости:</span><span class="sxs-lookup"><span data-stu-id="209bc-181">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="209bc-182">Кроме того, можно использовать модификаторы области для ссылки на переменную в другой области.</span><span class="sxs-lookup"><span data-stu-id="209bc-182">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="209bc-183">Следующая команда ссылается на `$test` переменную, сначала в локальной области, а затем в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="209bc-183">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="209bc-184">`Using:`Модификатор области видимости</span><span class="sxs-lookup"><span data-stu-id="209bc-184">The `Using:` scope modifier</span></span>

<span data-ttu-id="209bc-185">Использование — это специальный модификатор области, который определяет локальную переменную в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="209bc-185">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="209bc-186">Без модификатора PowerShell требует, чтобы переменные в удаленных командах были определены в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-186">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="209bc-187">`Using`Модификатор области представлен в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="209bc-187">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="209bc-188">Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="209bc-188">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="209bc-189">`Using`Модификатор области поддерживается в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="209bc-189">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="209bc-190">Удаленно выполненные команды, запущенные с `Invoke-Command` использованием **ComputerName** или параметра **Session** (удаленный сеанс)</span><span class="sxs-lookup"><span data-stu-id="209bc-190">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** or **Session** parameter (remote session)</span></span>
- <span data-ttu-id="209bc-191">Фоновые задания, запущенные с помощью `Start-Job` (вне процесса)</span><span class="sxs-lookup"><span data-stu-id="209bc-191">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="209bc-192">Задания потоков, запущенные через `Start-ThreadJob` или `ForEach-Object -Parallel` (отдельный сеанс потока)</span><span class="sxs-lookup"><span data-stu-id="209bc-192">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="209bc-193">В зависимости от контекста значения внедренных переменных — это либо независимые копии данных в области вызывающего объекта, либо ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="209bc-193">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="209bc-194">В удаленных и необработанных сеансах они всегда являются независимыми копиями.</span><span class="sxs-lookup"><span data-stu-id="209bc-194">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="209bc-195">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="209bc-195">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="209bc-196">В сеансах потока они передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="209bc-196">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="209bc-197">Это означает, что переменные области вызовов можно изменять в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="209bc-197">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="209bc-198">Для безопасного изменения переменных требуется синхронизация потоков.</span><span class="sxs-lookup"><span data-stu-id="209bc-198">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="209bc-199">Дополнительные сведения см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="209bc-199">For more information see:</span></span>

- [<span data-ttu-id="209bc-200">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="209bc-200">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="209bc-201">Сериализация значений переменных</span><span class="sxs-lookup"><span data-stu-id="209bc-201">Serialization of variable values</span></span>

<span data-ttu-id="209bc-202">Удаленные команды и фоновые задания выполняются вне процесса.</span><span class="sxs-lookup"><span data-stu-id="209bc-202">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="209bc-203">Необработанные сеансы используют сериализацию и десериализацию на основе XML, чтобы сделать значения переменных доступными через границы процесса.</span><span class="sxs-lookup"><span data-stu-id="209bc-203">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="209bc-204">Процесс сериализации преобразует объекты в **PSObject** , который содержит исходные свойства объектов, но не его методы.</span><span class="sxs-lookup"><span data-stu-id="209bc-204">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="209bc-205">Для ограниченного набора типов десериализация восстанавливает объекты обратно в исходный тип.</span><span class="sxs-lookup"><span data-stu-id="209bc-205">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="209bc-206">Восстановленный объект является копией исходного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="209bc-206">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="209bc-207">Он содержит свойства и методы типа.</span><span class="sxs-lookup"><span data-stu-id="209bc-207">It has the type properties and methods.</span></span> <span data-ttu-id="209bc-208">Для простых типов, таких как **System. Version** , копия является точной.</span><span class="sxs-lookup"><span data-stu-id="209bc-208">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="209bc-209">Для сложных типов копия — неидеальны.</span><span class="sxs-lookup"><span data-stu-id="209bc-209">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="209bc-210">Например, rehydratя объектов сертификатов не включает закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="209bc-210">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="209bc-211">Экземпляры всех остальных типов являются экземплярами **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="209bc-211">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="209bc-212">Свойство **PSTypeNames** содержит имя исходного типа с префиксом **десериализации** , например **Deserialized.SysTEM. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="209bc-212">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="209bc-213">Параметр AllScope</span><span class="sxs-lookup"><span data-stu-id="209bc-213">The AllScope Option</span></span>

<span data-ttu-id="209bc-214">Переменные и псевдонимы имеют свойство **Option** , которое может принимать значение **AllScope**.</span><span class="sxs-lookup"><span data-stu-id="209bc-214">Variables and aliases have an **Option** property that can take a value of **AllScope**.</span></span> <span data-ttu-id="209bc-215">Элементы, имеющие свойство **AllScope** , становятся частью любых создаваемых дочерних областей, хотя они не задним числом наследуются родительскими областями.</span><span class="sxs-lookup"><span data-stu-id="209bc-215">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="209bc-216">Элемент, имеющий свойство **AllScope** , отображается в дочерней области и является частью этой области.</span><span class="sxs-lookup"><span data-stu-id="209bc-216">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="209bc-217">Изменения элемента в любой области влияют на все области, в которых определена переменная.</span><span class="sxs-lookup"><span data-stu-id="209bc-217">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="209bc-218">Управление областью</span><span class="sxs-lookup"><span data-stu-id="209bc-218">Managing Scope</span></span>

<span data-ttu-id="209bc-219">Несколько командлетов имеют параметр **области** , который позволяет получать или задавать (создавать и изменять) элементы в определенной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-219">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="209bc-220">Используйте следующую команду, чтобы найти все командлеты в сеансе с параметром **области** :</span><span class="sxs-lookup"><span data-stu-id="209bc-220">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="209bc-221">Чтобы найти переменные, видимые в определенной области, используйте `Scope` параметр `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="209bc-221">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="209bc-222">Видимые переменные включают в себя глобальные переменные, переменные в родительской области и переменные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-222">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="209bc-223">Например, следующая команда получает переменные, видимые в локальной области:</span><span class="sxs-lookup"><span data-stu-id="209bc-223">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="209bc-224">Чтобы создать переменную в определенной области, используйте модификатор области или параметр **Scope** в `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="209bc-224">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="209bc-225">Следующая команда создает переменную в глобальной области видимости:</span><span class="sxs-lookup"><span data-stu-id="209bc-225">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="209bc-226">Для указания области можно также использовать параметр scope `New-Alias` `Set-Alias` командлетов, или `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="209bc-226">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="209bc-227">Следующая команда создает псевдоним в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="209bc-227">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="209bc-228">Чтобы получить функции в определенной области, используйте `Get-Item` командлет в области.</span><span class="sxs-lookup"><span data-stu-id="209bc-228">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="209bc-229">`Get-Item`Командлет не имеет параметра **области** .</span><span class="sxs-lookup"><span data-stu-id="209bc-229">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="209bc-230">Для командлетов, использующих параметр **области** , можно также ссылаться на области по числу.</span><span class="sxs-lookup"><span data-stu-id="209bc-230">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="209bc-231">Число описывает относительное расположение одной области в другую.</span><span class="sxs-lookup"><span data-stu-id="209bc-231">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="209bc-232">Область 0 представляет текущую или локальную область.</span><span class="sxs-lookup"><span data-stu-id="209bc-232">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="209bc-233">Область 1 указывает непосредственную родительскую область.</span><span class="sxs-lookup"><span data-stu-id="209bc-233">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="209bc-234">Область 2 указывает родителя родительской области и т. д.</span><span class="sxs-lookup"><span data-stu-id="209bc-234">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="209bc-235">Пронумерованные области полезны, если создано много рекурсивных областей.</span><span class="sxs-lookup"><span data-stu-id="209bc-235">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="209bc-236">Использование нотации источника точки с областью видимости</span><span class="sxs-lookup"><span data-stu-id="209bc-236">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="209bc-237">Сценарии и функции соответствуют всем правилам области.</span><span class="sxs-lookup"><span data-stu-id="209bc-237">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="209bc-238">Они создаются в определенной области и влияют только на эту область, если только не используется параметр командлета или модификатор области для изменения этой области.</span><span class="sxs-lookup"><span data-stu-id="209bc-238">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="209bc-239">Однако можно добавить скрипт или функцию в текущую область с помощью точечной нотации источника.</span><span class="sxs-lookup"><span data-stu-id="209bc-239">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="209bc-240">Затем, когда сценарий выполняется в текущей области, все функции, псевдонимы и переменные, создаваемые сценарием, доступны в текущей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-240">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="209bc-241">Чтобы добавить функцию в текущую область, введите точку (.) и пробел перед путем и именем функции в вызове функции.</span><span class="sxs-lookup"><span data-stu-id="209bc-241">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="209bc-242">Например, чтобы запустить скрипт Sample.ps1 из каталога C:\Scripts в области скрипта (по умолчанию для сценариев), используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="209bc-242">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="209bc-243">Чтобы запустить скрипт Sample.ps1 в локальной области, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="209bc-243">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="209bc-244">При использовании оператора Call (&) для выполнения функции или скрипта он не добавляется в текущую область.</span><span class="sxs-lookup"><span data-stu-id="209bc-244">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="209bc-245">В следующем примере используется оператор Call:</span><span class="sxs-lookup"><span data-stu-id="209bc-245">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="209bc-246">Дополнительные сведения о операторе Call можно узнать в [about_operators](about_operators.md).</span><span class="sxs-lookup"><span data-stu-id="209bc-246">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="209bc-247">Любые псевдонимы, функции или переменные, создаваемые сценарием Sample.ps1, недоступны в текущей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-247">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="209bc-248">Ограничение без области</span><span class="sxs-lookup"><span data-stu-id="209bc-248">Restricting Without Scope</span></span>

<span data-ttu-id="209bc-249">Несколько концепций PowerShell похожи на область или взаимодействуют с областью действия.</span><span class="sxs-lookup"><span data-stu-id="209bc-249">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="209bc-250">Эти понятия можно путать с областью действия или поведением области.</span><span class="sxs-lookup"><span data-stu-id="209bc-250">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="209bc-251">Сеансы, модули и вложенные запросы являются автономными средами, но они не являются дочерними областями глобальной области в сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-251">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="209bc-252">Сеансы</span><span class="sxs-lookup"><span data-stu-id="209bc-252">Sessions</span></span>

<span data-ttu-id="209bc-253">Сеанс — это среда, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="209bc-253">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="209bc-254">При создании сеанса на удаленном компьютере PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="209bc-254">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="209bc-255">Постоянное подключение позволяет использовать сеанс для нескольких связанных команд.</span><span class="sxs-lookup"><span data-stu-id="209bc-255">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="209bc-256">Поскольку сеанс является автономной средой, он имеет собственную область, но сеанс не является дочерней областью сеанса, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="209bc-256">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="209bc-257">Сеанс начинается с собственной глобальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-257">The session starts with its own global scope.</span></span> <span data-ttu-id="209bc-258">Эта область не зависит от глобальной области действия сеанса.</span><span class="sxs-lookup"><span data-stu-id="209bc-258">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="209bc-259">В сеансе можно создать дочерние области.</span><span class="sxs-lookup"><span data-stu-id="209bc-259">You can create child scopes in the session.</span></span> <span data-ttu-id="209bc-260">Например, можно выполнить сценарий для создания дочерней области в сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-260">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="209bc-261">Модули</span><span class="sxs-lookup"><span data-stu-id="209bc-261">Modules</span></span>

<span data-ttu-id="209bc-262">Вы можете использовать модуль PowerShell для совместного использования и доставки средств PowerShell.</span><span class="sxs-lookup"><span data-stu-id="209bc-262">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="209bc-263">Модуль — это единица, которая может содержать командлеты, скрипты, функции, переменные, псевдонимы и другие полезные элементы.</span><span class="sxs-lookup"><span data-stu-id="209bc-263">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="209bc-264">Если явно не определено, элементы в модуле недоступны за пределами модуля.</span><span class="sxs-lookup"><span data-stu-id="209bc-264">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="209bc-265">Таким образом, можно добавить модуль в сеанс и использовать открытые элементы, не заботясь о том, что другие элементы могут переопределять командлеты, сценарии, функции и другие элементы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-265">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="209bc-266">По умолчанию модули загружаются в верхний уровень текущего _состояния сеанса_ , а не в текущую _область_.</span><span class="sxs-lookup"><span data-stu-id="209bc-266">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_.</span></span> <span data-ttu-id="209bc-267">Текущее состояние сеанса может быть состоянием сеанса модуля или глобальным состоянием сеанса.</span><span class="sxs-lookup"><span data-stu-id="209bc-267">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="209bc-268">Добавление модуля в сеанс не приводит к изменению области.</span><span class="sxs-lookup"><span data-stu-id="209bc-268">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="209bc-269">Если вы используете глобальную область, модули загружаются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="209bc-269">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="209bc-270">Все операции экспорта помещаются в глобальные таблицы.</span><span class="sxs-lookup"><span data-stu-id="209bc-270">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="209bc-271">При загрузке _Module2 из Module1_ Module2 загружается в состояние сеанса Module1, а не в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="209bc-271">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="209bc-272">Все операции экспорта из Module2 размещаются в верхней части состояния сеанса Module1.</span><span class="sxs-lookup"><span data-stu-id="209bc-272">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="209bc-273">Если используется `Import-Module -Scope local` , то экспорты помещаются в текущий объект области, а не на верхний уровень.</span><span class="sxs-lookup"><span data-stu-id="209bc-273">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="209bc-274">Если вы используете _модуль_ и используете `Import-Module -Scope global` (или `Import-Module -Global` ) для загрузки другого модуля, этот модуль и его экспорты загружаются в глобальное состояние сеанса, а не в локальное состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="209bc-274">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="209bc-275">Эта функция предназначена для написания модуля, который управляет модулями.</span><span class="sxs-lookup"><span data-stu-id="209bc-275">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="209bc-276">Модуль **виндовскомпатибилити** выполняет это для импорта прокси-модулей в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="209bc-276">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="209bc-277">В состоянии сеанса модули имеют собственную область действия.</span><span class="sxs-lookup"><span data-stu-id="209bc-277">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="209bc-278">Рассмотрим следующий модуль `C:\temp\mod1.psm1` :</span><span class="sxs-lookup"><span data-stu-id="209bc-278">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="209bc-279">Теперь создадим глобальную переменную `$a` , присвойте ей значение и вызовите функцию **foo**.</span><span class="sxs-lookup"><span data-stu-id="209bc-279">Now we create a global variable `$a`, give it a value and call the function **foo**.</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="209bc-280">Модуль объявляет переменную `$a` в области модуля, а функция **foo** выводит значение переменной в обеих областях.</span><span class="sxs-lookup"><span data-stu-id="209bc-280">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="209bc-281">Вложенные запросы</span><span class="sxs-lookup"><span data-stu-id="209bc-281">Nested Prompts</span></span>

<span data-ttu-id="209bc-282">Вложенные запросы не имеют собственной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-282">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="209bc-283">При вводе вложенного запроса вложенный запрос является подмножеством среды.</span><span class="sxs-lookup"><span data-stu-id="209bc-283">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="209bc-284">Но остается в локальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-284">But, you remain within the local scope.</span></span>

<span data-ttu-id="209bc-285">Скрипты имеют собственную область действия.</span><span class="sxs-lookup"><span data-stu-id="209bc-285">Scripts do have their own scope.</span></span> <span data-ttu-id="209bc-286">При отладке скрипта и достижении точки останова в скрипте необходимо ввести область скрипта.</span><span class="sxs-lookup"><span data-stu-id="209bc-286">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="209bc-287">Частный вариант</span><span class="sxs-lookup"><span data-stu-id="209bc-287">Private Option</span></span>

<span data-ttu-id="209bc-288">Псевдонимы и переменные имеют свойство **Option** , которое может принимать значение **Private**.</span><span class="sxs-lookup"><span data-stu-id="209bc-288">Aliases and variables have an **Option** property that can take a value of **Private**.</span></span> <span data-ttu-id="209bc-289">Элементы с **закрытым** параметром можно просматривать и изменять в области, в которой они создаются, но их нельзя просматривать или изменять вне этой области.</span><span class="sxs-lookup"><span data-stu-id="209bc-289">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="209bc-290">Например, если вы создаете переменную с частным параметром в глобальной области, а затем выполняете сценарий, `Get-Variable` команды в скрипте не отображают закрытую переменную.</span><span class="sxs-lookup"><span data-stu-id="209bc-290">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="209bc-291">Использование модификатора глобальной области в этом экземпляре не приводит к отображению закрытой переменной.</span><span class="sxs-lookup"><span data-stu-id="209bc-291">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="209bc-292">Можно использовать параметр Option `New-Variable` `Set-Variable` `New-Alias` командлетов,,, и, `Set-Alias` чтобы задать для свойства параметра значение Private.</span><span class="sxs-lookup"><span data-stu-id="209bc-292">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="209bc-293">Видимость</span><span class="sxs-lookup"><span data-stu-id="209bc-293">Visibility</span></span>

<span data-ttu-id="209bc-294">Свойство **видимости** переменной или псевдонима определяет, можно ли видеть элемент за пределами контейнера, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="209bc-294">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="209bc-295">Контейнером может быть модуль, сценарий или оснастка.</span><span class="sxs-lookup"><span data-stu-id="209bc-295">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="209bc-296">Видимость предназначена для контейнеров так же, как и **закрытое** значение свойства **Option** для областей.</span><span class="sxs-lookup"><span data-stu-id="209bc-296">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="209bc-297">Свойство **Visibility** принимает **открытые** и **закрытые** значения.</span><span class="sxs-lookup"><span data-stu-id="209bc-297">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="209bc-298">Элементы, имеющие закрытую видимость, можно просматривать и изменять только в контейнере, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="209bc-298">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="209bc-299">Если контейнер добавлен или импортирован, элементы, имеющие закрытую видимость, не могут быть просмотрены или изменены.</span><span class="sxs-lookup"><span data-stu-id="209bc-299">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="209bc-300">Поскольку видимость предназначена для контейнеров, она работает по-разному в области.</span><span class="sxs-lookup"><span data-stu-id="209bc-300">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="209bc-301">При создании элемента с закрытой видимостью в глобальной области нельзя просматривать или изменять элемент в какой бы то ни было области.</span><span class="sxs-lookup"><span data-stu-id="209bc-301">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="209bc-302">При попытке просмотра или изменения значения переменной, имеющей закрытую видимость, PowerShell возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="209bc-302">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="209bc-303">`New-Variable` `Set-Variable` Для создания переменной с закрытой видимостью можно использовать командлеты и.</span><span class="sxs-lookup"><span data-stu-id="209bc-303">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="209bc-304">Примеры</span><span class="sxs-lookup"><span data-stu-id="209bc-304">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="209bc-305">Пример 1. изменение значения переменной только в скрипте</span><span class="sxs-lookup"><span data-stu-id="209bc-305">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="209bc-306">Следующая команда изменяет значение `$ConfirmPreference` переменной в скрипте.</span><span class="sxs-lookup"><span data-stu-id="209bc-306">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="209bc-307">Изменение не влияет на глобальную область.</span><span class="sxs-lookup"><span data-stu-id="209bc-307">The change does not affect the global scope.</span></span>

<span data-ttu-id="209bc-308">Сначала для вывода значения `$ConfirmPreference` переменной в локальной области используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="209bc-308">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="209bc-309">Создайте скрипт Scope.ps1, который содержит следующие команды:</span><span class="sxs-lookup"><span data-stu-id="209bc-309">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="209bc-310">Выполните скрипт.</span><span class="sxs-lookup"><span data-stu-id="209bc-310">Run the script.</span></span> <span data-ttu-id="209bc-311">Скрипт изменяет значение `$ConfirmPreference` переменной, а затем сообщает свое значение в области скрипта.</span><span class="sxs-lookup"><span data-stu-id="209bc-311">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="209bc-312">Выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="209bc-312">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="209bc-313">Затем проверьте текущее значение `$ConfirmPreference` переменной в текущей области.</span><span class="sxs-lookup"><span data-stu-id="209bc-313">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="209bc-314">В этом примере показано, что изменения значения переменной в области скрипта не влияют на значение переменной в родительской области.</span><span class="sxs-lookup"><span data-stu-id="209bc-314">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="209bc-315">Пример 2. Просмотр значения переменной в разных областях</span><span class="sxs-lookup"><span data-stu-id="209bc-315">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="209bc-316">Модификаторы области можно использовать для просмотра значения переменной в локальной области и в родительской области.</span><span class="sxs-lookup"><span data-stu-id="209bc-316">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="209bc-317">Сначала определите `$test` переменную в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-317">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="209bc-318">Затем создайте скрипт Sample.ps1, определяющий `$test` переменную.</span><span class="sxs-lookup"><span data-stu-id="209bc-318">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="209bc-319">В скрипте используйте модификатор области для ссылки на глобальную или локальную версию `$test` переменной.</span><span class="sxs-lookup"><span data-stu-id="209bc-319">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="209bc-320">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="209bc-320">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="209bc-321">При запуске Sample.ps1 выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="209bc-321">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="209bc-322">По завершении скрипта `$test` в сеансе определяется только глобальное значение.</span><span class="sxs-lookup"><span data-stu-id="209bc-322">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="209bc-323">Пример 3. изменение значения переменной в родительской области</span><span class="sxs-lookup"><span data-stu-id="209bc-323">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="209bc-324">Если вы не защищаете элемент с помощью параметра private или другого метода, то можете просмотреть и изменить значение переменной в родительской области.</span><span class="sxs-lookup"><span data-stu-id="209bc-324">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="209bc-325">Сначала определите `$test` переменную в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-325">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="209bc-326">Затем создайте скрипт Sample.ps1, определяющий `$test` переменную.</span><span class="sxs-lookup"><span data-stu-id="209bc-326">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="209bc-327">В скрипте используйте модификатор области для ссылки на глобальную или локальную версию `$test` переменной.</span><span class="sxs-lookup"><span data-stu-id="209bc-327">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="209bc-328">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="209bc-328">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="209bc-329">По завершении скрипта изменяется глобальное значение `$test` .</span><span class="sxs-lookup"><span data-stu-id="209bc-329">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="209bc-330">Пример 4. Создание закрытой переменной</span><span class="sxs-lookup"><span data-stu-id="209bc-330">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="209bc-331">Частная переменная — это переменная, которая имеет свойство **Option** со значением *Private*.</span><span class="sxs-lookup"><span data-stu-id="209bc-331">A private variable is a variable that has an **Option** property that has a value of *Private*.</span></span> <span data-ttu-id="209bc-332">*Закрытые* переменные наследуются дочерней областью, но их можно просматривать или изменять только в области, в которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="209bc-332">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="209bc-333">Следующая команда создает закрытую переменную с именем `$ptest` в локальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-333">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="209bc-334">Можно отобразить и изменить значение `$ptest` в локальной области.</span><span class="sxs-lookup"><span data-stu-id="209bc-334">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="209bc-335">Затем создайте скрипт Sample.ps1, содержащий следующие команды.</span><span class="sxs-lookup"><span data-stu-id="209bc-335">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="209bc-336">Команда пытается отобразить и изменить значение `$ptest` .</span><span class="sxs-lookup"><span data-stu-id="209bc-336">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="209bc-337">В Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="209bc-337">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="209bc-338">`$ptest`Переменная не видна в области скрипта, выходные данные пусты.</span><span class="sxs-lookup"><span data-stu-id="209bc-338">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="209bc-339">Пример 5. Использование локальной переменной в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="209bc-339">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="209bc-340">Для переменных в удаленной команде, созданной в локальном сеансе, используйте `Using` Модификатор области.</span><span class="sxs-lookup"><span data-stu-id="209bc-340">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="209bc-341">В PowerShell предполагается, что переменные в удаленных командах были созданы в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="209bc-341">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="209bc-342">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="209bc-342">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="209bc-343">Например, следующие команды создают `$Cred` переменную в локальном сеансе, а затем используют эту `$Cred` переменную в удаленной команде:</span><span class="sxs-lookup"><span data-stu-id="209bc-343">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="209bc-344">Область использования была введена в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="209bc-344">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="209bc-345">В PowerShell 2,0, чтобы указать, что переменная была создана в локальном сеансе, используйте следующий формат команды.</span><span class="sxs-lookup"><span data-stu-id="209bc-345">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="209bc-346">См. также</span><span class="sxs-lookup"><span data-stu-id="209bc-346">See also</span></span>

[<span data-ttu-id="209bc-347">about_Variables</span><span class="sxs-lookup"><span data-stu-id="209bc-347">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="209bc-348">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="209bc-348">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="209bc-349">about_Functions</span><span class="sxs-lookup"><span data-stu-id="209bc-349">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="209bc-350">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="209bc-350">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="209bc-351">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="209bc-351">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: c77eb9c64022d028c3c4b2de6bf4551886b940e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599790"
---
# <span data-ttu-id="f597a-102">New-Variable</span><span class="sxs-lookup"><span data-stu-id="f597a-102">New-Variable</span></span>

## <span data-ttu-id="f597a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f597a-103">SYNOPSIS</span></span>
<span data-ttu-id="f597a-104">Создает новую переменную.</span><span class="sxs-lookup"><span data-stu-id="f597a-104">Creates a new variable.</span></span>

## <span data-ttu-id="f597a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f597a-105">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="f597a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f597a-106">DESCRIPTION</span></span>
<span data-ttu-id="f597a-107">Командлет **New-Variable** создает новую переменную в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f597a-107">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="f597a-108">Значение для переменной можно назначить при ее создании или изменив созданное значение.</span><span class="sxs-lookup"><span data-stu-id="f597a-108">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="f597a-109">Для задания свойств переменной, определения области видимости переменной и проверки того, являются ли переменные общедоступными или частными, можно использовать параметры **новой переменной** .</span><span class="sxs-lookup"><span data-stu-id="f597a-109">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="f597a-110">Как правило, Новая переменная создается путем ввода имени переменной и ее значения, например `$Var = 3` , но можно использовать командлет **New-Variable** , чтобы использовать его параметры.</span><span class="sxs-lookup"><span data-stu-id="f597a-110">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="f597a-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="f597a-111">EXAMPLES</span></span>

### <span data-ttu-id="f597a-112">Пример 1. Создание переменной</span><span class="sxs-lookup"><span data-stu-id="f597a-112">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="f597a-113">Эта команда создает новую переменную с именем Days.</span><span class="sxs-lookup"><span data-stu-id="f597a-113">This command creates a new variable named days.</span></span>
<span data-ttu-id="f597a-114">Вам не нужно вводить параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="f597a-114">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="f597a-115">Пример 2. Создание переменной и присвоение ей значения</span><span class="sxs-lookup"><span data-stu-id="f597a-115">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="f597a-116">Эта команда создает переменную с именем ZipCode и присваивает ей значение 98033.</span><span class="sxs-lookup"><span data-stu-id="f597a-116">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="f597a-117">Пример 3. Создание переменной с параметром ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f597a-117">Example 3: Create a variable with the ReadOnly option</span></span>

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

<span data-ttu-id="f597a-118">В этом примере показано, как использовать параметр ReadOnly **переменной New-Variable** , чтобы защитить переменную от переписывания.</span><span class="sxs-lookup"><span data-stu-id="f597a-118">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="f597a-119">Первая команда создает новую переменную с именем Max и присваивает ей значение 256.</span><span class="sxs-lookup"><span data-stu-id="f597a-119">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="f597a-120">В нем используется параметр *Option* со значением ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="f597a-120">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="f597a-121">Вторая команда пытается создать вторую переменную с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="f597a-121">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="f597a-122">Эта команда возвращает ошибку, поскольку для переменной задан параметр "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="f597a-122">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="f597a-123">Третья команда использует параметр *Force* , чтобы переопределить защиту только для чтения для переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-123">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="f597a-124">В этом случае команда создания новой переменной с тем же именем успешно выполняется.</span><span class="sxs-lookup"><span data-stu-id="f597a-124">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="f597a-125">Пример 4. Создание закрытой переменной</span><span class="sxs-lookup"><span data-stu-id="f597a-125">Example 4: Create a private variable</span></span>

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

<span data-ttu-id="f597a-126">Эта команда демонстрирует поведение частной переменной в модуле.</span><span class="sxs-lookup"><span data-stu-id="f597a-126">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="f597a-127">Модуль содержит командлет Get-Counter, который имеет закрытую переменную с именем Counter.</span><span class="sxs-lookup"><span data-stu-id="f597a-127">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="f597a-128">Команда использует параметр *видимости* со значением Private, чтобы создать переменную.</span><span class="sxs-lookup"><span data-stu-id="f597a-128">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="f597a-129">В примере выходных данных показано поведение частной переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-129">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="f597a-130">Пользователь, загрузивший модуль, не может просматривать или изменять значение переменной Counter, но переменную Counter можно прочитать и изменить с помощью команд в модуле.</span><span class="sxs-lookup"><span data-stu-id="f597a-130">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="f597a-131">Пример 5. Создание переменной с пробелом</span><span class="sxs-lookup"><span data-stu-id="f597a-131">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="f597a-132">Эта команда показывает, что можно создать переменные с пробелами.</span><span class="sxs-lookup"><span data-stu-id="f597a-132">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="f597a-133">Доступ к переменным можно получить с помощью командлета **Get-Variable** или напрямую, разделив переменную фигурными скобками.</span><span class="sxs-lookup"><span data-stu-id="f597a-133">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="f597a-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f597a-134">PARAMETERS</span></span>

### <span data-ttu-id="f597a-135">-Description</span><span class="sxs-lookup"><span data-stu-id="f597a-135">-Description</span></span>
<span data-ttu-id="f597a-136">Указывает описание переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-136">Specifies a description of the variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-137">-Force</span><span class="sxs-lookup"><span data-stu-id="f597a-137">-Force</span></span>
<span data-ttu-id="f597a-138">Указывает, что командлет создает переменную с тем же именем, что и существующая переменная, доступная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f597a-138">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="f597a-139">По умолчанию переменную можно перезаписать, за исключением случаев, когда она имеет значение параметра ReadOnly или Constant.</span><span class="sxs-lookup"><span data-stu-id="f597a-139">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="f597a-140">Дополнительные сведения см. в описании параметра *Option* .</span><span class="sxs-lookup"><span data-stu-id="f597a-140">For more information, see the *Option* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-141">-Name</span><span class="sxs-lookup"><span data-stu-id="f597a-141">-Name</span></span>
<span data-ttu-id="f597a-142">Указывает имя новой переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-142">Specifies a name for the new variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-143">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="f597a-143">-Option</span></span>
<span data-ttu-id="f597a-144">Задает значение свойства **Options** переменной. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f597a-144">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f597a-145">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f597a-145">None.</span></span>
<span data-ttu-id="f597a-146">не определяет параметров</span><span class="sxs-lookup"><span data-stu-id="f597a-146">Sets no options.</span></span>
<span data-ttu-id="f597a-147">(Значение по умолчанию — None.)</span><span class="sxs-lookup"><span data-stu-id="f597a-147">(None is the default.)</span></span>
- <span data-ttu-id="f597a-148">Доступно.</span><span class="sxs-lookup"><span data-stu-id="f597a-148">ReadOnly.</span></span>
<span data-ttu-id="f597a-149">псевдоним можно удалить,</span><span class="sxs-lookup"><span data-stu-id="f597a-149">Can be deleted.</span></span>
<span data-ttu-id="f597a-150">Нельзя изменить, за исключением использования параметра *Force* .</span><span class="sxs-lookup"><span data-stu-id="f597a-150">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="f597a-151">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="f597a-151">Private.</span></span>
<span data-ttu-id="f597a-152">переменная доступна только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="f597a-152">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="f597a-153">AllScope.</span><span class="sxs-lookup"><span data-stu-id="f597a-153">AllScope.</span></span>
<span data-ttu-id="f597a-154">переменная копируется в новые созданные области.</span><span class="sxs-lookup"><span data-stu-id="f597a-154">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="f597a-155">Константа.</span><span class="sxs-lookup"><span data-stu-id="f597a-155">Constant.</span></span>
<span data-ttu-id="f597a-156">псевдоним нельзя удалить или изменить.</span><span class="sxs-lookup"><span data-stu-id="f597a-156">Cannot be deleted or changed.</span></span>
<span data-ttu-id="f597a-157">Константа допустима только при создании переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-157">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="f597a-158">Параметры существующей переменной нельзя изменить на константу.</span><span class="sxs-lookup"><span data-stu-id="f597a-158">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="f597a-159">Чтобы просмотреть свойство **Options** всех переменных в сеансе, введите `Get-Variable | Format-Table -Property name, options -autosize` .</span><span class="sxs-lookup"><span data-stu-id="f597a-159">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f597a-160">-PassThru</span></span>
<span data-ttu-id="f597a-161">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="f597a-161">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="f597a-162">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f597a-162">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-163">-Scope</span><span class="sxs-lookup"><span data-stu-id="f597a-163">-Scope</span></span>
<span data-ttu-id="f597a-164">Задает область новой переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-164">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="f597a-165">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f597a-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f597a-166">Глобального.</span><span class="sxs-lookup"><span data-stu-id="f597a-166">Global.</span></span>
<span data-ttu-id="f597a-167">Переменные, созданные в глобальной области, доступны везде в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f597a-167">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="f597a-168">Локальный.</span><span class="sxs-lookup"><span data-stu-id="f597a-168">Local.</span></span>
<span data-ttu-id="f597a-169">Локальная область ссылается на текущую область, это может быть любая область в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="f597a-169">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="f597a-170">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="f597a-170">Script.</span></span>
<span data-ttu-id="f597a-171">Переменные, созданные в области скриптов, доступны только в файле скрипта или модуле, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="f597a-171">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="f597a-172">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="f597a-172">Private.</span></span>
<span data-ttu-id="f597a-173">К переменным, созданным в закрытой области, нельзя обращаться за пределами области, в которой они существуют.</span><span class="sxs-lookup"><span data-stu-id="f597a-173">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="f597a-174">Частную область можно использовать для создания закрытой версии элемента с тем же именем в другой области.</span><span class="sxs-lookup"><span data-stu-id="f597a-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="f597a-175">Число относительно текущей области (от 0 до количества областей, где 0 является текущей областью, 1 — ее родителем, 2 родителя родительской области и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f597a-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="f597a-176">Отрицательные числа использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="f597a-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="f597a-177">Значение Local является областью по умолчанию, если параметр области не указан.</span><span class="sxs-lookup"><span data-stu-id="f597a-177">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="f597a-178">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="f597a-178">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-179">-Value</span><span class="sxs-lookup"><span data-stu-id="f597a-179">-Value</span></span>
<span data-ttu-id="f597a-180">Указывает первоначальное значение переменной.</span><span class="sxs-lookup"><span data-stu-id="f597a-180">Specifies the initial value of the variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-181">— Видимость</span><span class="sxs-lookup"><span data-stu-id="f597a-181">-Visibility</span></span>
<span data-ttu-id="f597a-182">Определяет, видима ли переменная вне сеанса, в котором она была создана.</span><span class="sxs-lookup"><span data-stu-id="f597a-182">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="f597a-183">Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="f597a-183">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="f597a-184">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f597a-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f597a-185">Общедоступный.</span><span class="sxs-lookup"><span data-stu-id="f597a-185">Public.</span></span>
<span data-ttu-id="f597a-186">переменная видима.</span><span class="sxs-lookup"><span data-stu-id="f597a-186">The variable is visible.</span></span>
<span data-ttu-id="f597a-187">(Значение по умолчанию — Public.)</span><span class="sxs-lookup"><span data-stu-id="f597a-187">(Public is the default.)</span></span>
- <span data-ttu-id="f597a-188">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="f597a-188">Private.</span></span>
<span data-ttu-id="f597a-189">переменная невидима.</span><span class="sxs-lookup"><span data-stu-id="f597a-189">The variable is not visible.</span></span>

<span data-ttu-id="f597a-190">Если переменная частная, она не отображается в списках переменных, например возвращаемых командлетом Get-Variable, или в выходных данных для диска Variable:.</span><span class="sxs-lookup"><span data-stu-id="f597a-190">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="f597a-191">Команды чтения или изменения значения частной переменной возвращают ошибку.</span><span class="sxs-lookup"><span data-stu-id="f597a-191">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="f597a-192">Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.</span><span class="sxs-lookup"><span data-stu-id="f597a-192">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f597a-193">-Confirm</span></span>
<span data-ttu-id="f597a-194">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f597a-194">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f597a-195">-WhatIf</span></span>
<span data-ttu-id="f597a-196">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f597a-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f597a-197">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f597a-197">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f597a-198">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f597a-198">CommonParameters</span></span>
<span data-ttu-id="f597a-199">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f597a-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f597a-200">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f597a-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f597a-201">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f597a-201">INPUTS</span></span>

### <span data-ttu-id="f597a-202">System.Object</span><span class="sxs-lookup"><span data-stu-id="f597a-202">System.Object</span></span>
<span data-ttu-id="f597a-203">Значение можно передать в командлет **New-Variable**.</span><span class="sxs-lookup"><span data-stu-id="f597a-203">You can pipe a value to **New-Variable**.</span></span>

## <span data-ttu-id="f597a-204">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f597a-204">OUTPUTS</span></span>

### <span data-ttu-id="f597a-205">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="f597a-205">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="f597a-206">При использовании параметра *PassThru* командлет **New-Variable** создает объект **System. Management. Automation. PSVariable** , представляющий новую переменную.</span><span class="sxs-lookup"><span data-stu-id="f597a-206">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="f597a-207">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f597a-207">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f597a-208">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f597a-208">NOTES</span></span>

## <span data-ttu-id="f597a-209">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f597a-209">RELATED LINKS</span></span>

[<span data-ttu-id="f597a-210">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="f597a-210">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="f597a-211">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="f597a-211">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="f597a-212">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="f597a-212">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="f597a-213">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="f597a-213">Set-Variable</span></span>](Set-Variable.md)


---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: faf8bc399185da402bebb678b02927e0e5628662
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228698"
---
# <span data-ttu-id="3a511-103">New-Variable</span><span class="sxs-lookup"><span data-stu-id="3a511-103">New-Variable</span></span>

## <span data-ttu-id="3a511-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3a511-104">SYNOPSIS</span></span>
<span data-ttu-id="3a511-105">Создает новую переменную.</span><span class="sxs-lookup"><span data-stu-id="3a511-105">Creates a new variable.</span></span>

## <span data-ttu-id="3a511-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a511-106">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="3a511-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a511-107">DESCRIPTION</span></span>
<span data-ttu-id="3a511-108">Командлет **New-Variable** создает новую переменную в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a511-108">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="3a511-109">Значение для переменной можно назначить при ее создании или изменив созданное значение.</span><span class="sxs-lookup"><span data-stu-id="3a511-109">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="3a511-110">Для задания свойств переменной, определения области видимости переменной и проверки того, являются ли переменные общедоступными или частными, можно использовать параметры **новой переменной** .</span><span class="sxs-lookup"><span data-stu-id="3a511-110">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="3a511-111">Как правило, Новая переменная создается путем ввода имени переменной и ее значения, например `$Var = 3` , но можно использовать командлет **New-Variable** , чтобы использовать его параметры.</span><span class="sxs-lookup"><span data-stu-id="3a511-111">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="3a511-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="3a511-112">EXAMPLES</span></span>

### <span data-ttu-id="3a511-113">Пример 1. Создание переменной</span><span class="sxs-lookup"><span data-stu-id="3a511-113">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="3a511-114">Эта команда создает новую переменную с именем Days.</span><span class="sxs-lookup"><span data-stu-id="3a511-114">This command creates a new variable named days.</span></span>
<span data-ttu-id="3a511-115">Вам не нужно вводить параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="3a511-115">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="3a511-116">Пример 2. Создание переменной и присвоение ей значения</span><span class="sxs-lookup"><span data-stu-id="3a511-116">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="3a511-117">Эта команда создает переменную с именем ZipCode и присваивает ей значение 98033.</span><span class="sxs-lookup"><span data-stu-id="3a511-117">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="3a511-118">Пример 3. Создание переменной с параметром ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3a511-118">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="3a511-119">В этом примере показано, как использовать параметр ReadOnly **переменной New-Variable** , чтобы защитить переменную от переписывания.</span><span class="sxs-lookup"><span data-stu-id="3a511-119">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="3a511-120">Первая команда создает новую переменную с именем Max и присваивает ей значение 256.</span><span class="sxs-lookup"><span data-stu-id="3a511-120">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="3a511-121">В нем используется параметр *Option* со значением ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="3a511-121">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="3a511-122">Вторая команда пытается создать вторую переменную с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="3a511-122">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="3a511-123">Эта команда возвращает ошибку, поскольку для переменной задан параметр "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="3a511-123">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="3a511-124">Третья команда использует параметр *Force* , чтобы переопределить защиту только для чтения для переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-124">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="3a511-125">В этом случае команда создания новой переменной с тем же именем успешно выполняется.</span><span class="sxs-lookup"><span data-stu-id="3a511-125">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="3a511-126">Пример 4. Создание закрытой переменной</span><span class="sxs-lookup"><span data-stu-id="3a511-126">Example 4: Create a private variable</span></span>

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

<span data-ttu-id="3a511-127">Эта команда демонстрирует поведение частной переменной в модуле.</span><span class="sxs-lookup"><span data-stu-id="3a511-127">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="3a511-128">Модуль содержит командлет Get-Counter, который имеет закрытую переменную с именем Counter.</span><span class="sxs-lookup"><span data-stu-id="3a511-128">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="3a511-129">Команда использует параметр *видимости* со значением Private, чтобы создать переменную.</span><span class="sxs-lookup"><span data-stu-id="3a511-129">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="3a511-130">В примере выходных данных показано поведение частной переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-130">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="3a511-131">Пользователь, загрузивший модуль, не может просматривать или изменять значение переменной Counter, но переменную Counter можно прочитать и изменить с помощью команд в модуле.</span><span class="sxs-lookup"><span data-stu-id="3a511-131">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="3a511-132">Пример 5. Создание переменной с пробелом</span><span class="sxs-lookup"><span data-stu-id="3a511-132">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="3a511-133">Эта команда показывает, что можно создать переменные с пробелами.</span><span class="sxs-lookup"><span data-stu-id="3a511-133">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="3a511-134">Доступ к переменным можно получить с помощью командлета **Get-Variable** или напрямую, разделив переменную фигурными скобками.</span><span class="sxs-lookup"><span data-stu-id="3a511-134">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="3a511-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a511-135">PARAMETERS</span></span>

### <span data-ttu-id="3a511-136">-Description</span><span class="sxs-lookup"><span data-stu-id="3a511-136">-Description</span></span>
<span data-ttu-id="3a511-137">Указывает описание переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-137">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="3a511-138">-Force</span><span class="sxs-lookup"><span data-stu-id="3a511-138">-Force</span></span>
<span data-ttu-id="3a511-139">Указывает, что командлет создает переменную с тем же именем, что и существующая переменная, доступная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3a511-139">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="3a511-140">По умолчанию переменную можно перезаписать, за исключением случаев, когда она имеет значение параметра ReadOnly или Constant.</span><span class="sxs-lookup"><span data-stu-id="3a511-140">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="3a511-141">Дополнительные сведения см. в описании параметра *Option* .</span><span class="sxs-lookup"><span data-stu-id="3a511-141">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="3a511-142">-Name</span><span class="sxs-lookup"><span data-stu-id="3a511-142">-Name</span></span>
<span data-ttu-id="3a511-143">Указывает имя новой переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-143">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="3a511-144">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="3a511-144">-Option</span></span>
<span data-ttu-id="3a511-145">Задает значение свойства **Options** переменной. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3a511-145">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3a511-146">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a511-146">None.</span></span>
<span data-ttu-id="3a511-147">не определяет параметров</span><span class="sxs-lookup"><span data-stu-id="3a511-147">Sets no options.</span></span>
<span data-ttu-id="3a511-148">(Значение по умолчанию — None.)</span><span class="sxs-lookup"><span data-stu-id="3a511-148">(None is the default.)</span></span>
- <span data-ttu-id="3a511-149">Доступно.</span><span class="sxs-lookup"><span data-stu-id="3a511-149">ReadOnly.</span></span>
<span data-ttu-id="3a511-150">псевдоним можно удалить,</span><span class="sxs-lookup"><span data-stu-id="3a511-150">Can be deleted.</span></span>
<span data-ttu-id="3a511-151">Нельзя изменить, за исключением использования параметра *Force* .</span><span class="sxs-lookup"><span data-stu-id="3a511-151">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="3a511-152">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="3a511-152">Private.</span></span>
<span data-ttu-id="3a511-153">переменная доступна только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="3a511-153">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="3a511-154">AllScope.</span><span class="sxs-lookup"><span data-stu-id="3a511-154">AllScope.</span></span>
<span data-ttu-id="3a511-155">переменная копируется в новые созданные области.</span><span class="sxs-lookup"><span data-stu-id="3a511-155">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="3a511-156">Константа.</span><span class="sxs-lookup"><span data-stu-id="3a511-156">Constant.</span></span>
<span data-ttu-id="3a511-157">псевдоним нельзя удалить или изменить.</span><span class="sxs-lookup"><span data-stu-id="3a511-157">Cannot be deleted or changed.</span></span>
<span data-ttu-id="3a511-158">Константа допустима только при создании переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-158">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="3a511-159">Параметры существующей переменной нельзя изменить на константу.</span><span class="sxs-lookup"><span data-stu-id="3a511-159">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="3a511-160">Чтобы просмотреть свойство **Options** всех переменных в сеансе, введите `Get-Variable | Format-Table -Property name, options -autosize` .</span><span class="sxs-lookup"><span data-stu-id="3a511-160">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="3a511-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3a511-161">-PassThru</span></span>
<span data-ttu-id="3a511-162">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="3a511-162">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="3a511-163">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="3a511-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3a511-164">-Scope</span><span class="sxs-lookup"><span data-stu-id="3a511-164">-Scope</span></span>
<span data-ttu-id="3a511-165">Задает область новой переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-165">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="3a511-166">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3a511-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3a511-167">Глобального.</span><span class="sxs-lookup"><span data-stu-id="3a511-167">Global.</span></span>
<span data-ttu-id="3a511-168">Переменные, созданные в глобальной области, доступны везде в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a511-168">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="3a511-169">Локальный.</span><span class="sxs-lookup"><span data-stu-id="3a511-169">Local.</span></span>
<span data-ttu-id="3a511-170">Локальная область ссылается на текущую область, это может быть любая область в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="3a511-170">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="3a511-171">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="3a511-171">Script.</span></span>
<span data-ttu-id="3a511-172">Переменные, созданные в области скриптов, доступны только в файле скрипта или модуле, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="3a511-172">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="3a511-173">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="3a511-173">Private.</span></span>
<span data-ttu-id="3a511-174">К переменным, созданным в закрытой области, нельзя обращаться за пределами области, в которой они существуют.</span><span class="sxs-lookup"><span data-stu-id="3a511-174">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="3a511-175">Частную область можно использовать для создания закрытой версии элемента с тем же именем в другой области.</span><span class="sxs-lookup"><span data-stu-id="3a511-175">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="3a511-176">Число относительно текущей области (от 0 до количества областей, где 0 является текущей областью, 1 — ее родителем, 2 родителя родительской области и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3a511-176">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="3a511-177">Отрицательные числа использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="3a511-177">Negative numbers cannot be used.</span></span>

<span data-ttu-id="3a511-178">Значение Local является областью по умолчанию, если параметр области не указан.</span><span class="sxs-lookup"><span data-stu-id="3a511-178">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="3a511-179">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="3a511-179">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="3a511-180">-Value</span><span class="sxs-lookup"><span data-stu-id="3a511-180">-Value</span></span>
<span data-ttu-id="3a511-181">Указывает первоначальное значение переменной.</span><span class="sxs-lookup"><span data-stu-id="3a511-181">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="3a511-182">— Видимость</span><span class="sxs-lookup"><span data-stu-id="3a511-182">-Visibility</span></span>
<span data-ttu-id="3a511-183">Определяет, видима ли переменная вне сеанса, в котором она была создана.</span><span class="sxs-lookup"><span data-stu-id="3a511-183">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="3a511-184">Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="3a511-184">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="3a511-185">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3a511-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3a511-186">Общедоступный.</span><span class="sxs-lookup"><span data-stu-id="3a511-186">Public.</span></span>
<span data-ttu-id="3a511-187">переменная видима.</span><span class="sxs-lookup"><span data-stu-id="3a511-187">The variable is visible.</span></span>
<span data-ttu-id="3a511-188">(Значение по умолчанию — Public.)</span><span class="sxs-lookup"><span data-stu-id="3a511-188">(Public is the default.)</span></span>
- <span data-ttu-id="3a511-189">Закрытый.</span><span class="sxs-lookup"><span data-stu-id="3a511-189">Private.</span></span>
<span data-ttu-id="3a511-190">переменная невидима.</span><span class="sxs-lookup"><span data-stu-id="3a511-190">The variable is not visible.</span></span>

<span data-ttu-id="3a511-191">Если переменная частная, она не отображается в списках переменных, например возвращаемых командлетом Get-Variable, или в выходных данных для диска Variable:.</span><span class="sxs-lookup"><span data-stu-id="3a511-191">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="3a511-192">Команды чтения или изменения значения частной переменной возвращают ошибку.</span><span class="sxs-lookup"><span data-stu-id="3a511-192">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="3a511-193">Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.</span><span class="sxs-lookup"><span data-stu-id="3a511-193">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="3a511-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3a511-194">-Confirm</span></span>
<span data-ttu-id="3a511-195">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3a511-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3a511-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3a511-196">-WhatIf</span></span>
<span data-ttu-id="3a511-197">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3a511-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3a511-198">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3a511-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3a511-199">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3a511-199">CommonParameters</span></span>
<span data-ttu-id="3a511-200">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a511-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a511-201">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a511-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a511-202">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3a511-202">INPUTS</span></span>

### <span data-ttu-id="3a511-203">System.Object</span><span class="sxs-lookup"><span data-stu-id="3a511-203">System.Object</span></span>
<span data-ttu-id="3a511-204">Значение можно передать в командлет **New-Variable** .</span><span class="sxs-lookup"><span data-stu-id="3a511-204">You can pipe a value to **New-Variable** .</span></span>

## <span data-ttu-id="3a511-205">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3a511-205">OUTPUTS</span></span>

### <span data-ttu-id="3a511-206">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="3a511-206">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="3a511-207">При использовании параметра *PassThru* командлет **New-Variable** создает объект **System. Management. Automation. PSVariable** , представляющий новую переменную.</span><span class="sxs-lookup"><span data-stu-id="3a511-207">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="3a511-208">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3a511-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3a511-209">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3a511-209">NOTES</span></span>

## <span data-ttu-id="3a511-210">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3a511-210">RELATED LINKS</span></span>

[<span data-ttu-id="3a511-211">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="3a511-211">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="3a511-212">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="3a511-212">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="3a511-213">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="3a511-213">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="3a511-214">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="3a511-214">Set-Variable</span></span>](Set-Variable.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 573bb0054b60e8c17b79da72ebc712c6ef5575a5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605298"
---
# <span data-ttu-id="b21a4-102">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="b21a4-102">Set-Variable</span></span>

## <span data-ttu-id="b21a4-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b21a4-103">SYNOPSIS</span></span>
<span data-ttu-id="b21a4-104">Задает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-104">Sets the value of a variable.</span></span> <span data-ttu-id="b21a4-105">Создает переменную, если переменной с запрошенным именем не существует.</span><span class="sxs-lookup"><span data-stu-id="b21a4-105">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="b21a4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b21a4-106">SYNTAX</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b21a4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b21a4-107">DESCRIPTION</span></span>

<span data-ttu-id="b21a4-108">`Set-Variable`Командлет присваивает значение указанной переменной или изменяет текущее значение.</span><span class="sxs-lookup"><span data-stu-id="b21a4-108">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="b21a4-109">Если переменная не существует, командлет создает ее.</span><span class="sxs-lookup"><span data-stu-id="b21a4-109">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="b21a4-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="b21a4-110">EXAMPLES</span></span>

### <span data-ttu-id="b21a4-111">Пример 1. задание переменной и получение ее значения</span><span class="sxs-lookup"><span data-stu-id="b21a4-111">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="b21a4-112">Эти команды задают значение `$desc` переменной `A description` , а затем получает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-112">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="b21a4-113">Пример 2. Задание глобальной переменной, доступной только для чтения</span><span class="sxs-lookup"><span data-stu-id="b21a4-113">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="b21a4-114">В этом примере создается глобальная переменная, доступная только для чтения, которая содержит все процессы в системе, а затем отображаются все свойства переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-114">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="b21a4-115">Команда использует `Set-Variable` командлет для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-115">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="b21a4-116">Он использует параметр **PassThru** для создания объекта, представляющего новую переменную, и использует оператор конвейера ( `|` ) для передачи объекта в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="b21a4-116">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="b21a4-117"> `Format-List` `*` Для вывода всех свойств только что созданной переменной в нем используется параметр Property со значением All ().</span><span class="sxs-lookup"><span data-stu-id="b21a4-117">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="b21a4-118">Значение, `(Get-Process)` , заключено в круглые скобки, чтобы убедиться, что оно выполняется перед сохранением в переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-118">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="b21a4-119">В противном случае переменная содержит слова «**Get-Process**».</span><span class="sxs-lookup"><span data-stu-id="b21a4-119">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="b21a4-120">Пример 3. Знакомство с открытыми и частными переменными</span><span class="sxs-lookup"><span data-stu-id="b21a4-120">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="b21a4-121">В этом примере показано, как изменить видимость переменной на `Private` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-121">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="b21a4-122">Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b21a4-122">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

<span data-ttu-id="b21a4-123">Эта команда показывает, как изменить видимость переменной на Private.</span><span class="sxs-lookup"><span data-stu-id="b21a4-123">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="b21a4-124">Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b21a4-124">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="b21a4-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b21a4-125">PARAMETERS</span></span>

### <span data-ttu-id="b21a4-126">-Description</span><span class="sxs-lookup"><span data-stu-id="b21a4-126">-Description</span></span>

<span data-ttu-id="b21a4-127">Задает описание переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-127">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="b21a4-128">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b21a4-128">-Exclude</span></span>

<span data-ttu-id="b21a4-129">Указывает массив элементов, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="b21a4-129">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="b21a4-130">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="b21a4-130">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b21a4-131">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-131">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="b21a4-132">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b21a4-132">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b21a4-133">-Force</span><span class="sxs-lookup"><span data-stu-id="b21a4-133">-Force</span></span>

<span data-ttu-id="b21a4-134">Позволяет создать переменную с тем же именем, как у существующей переменной только для чтения, или изменить значение переменной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b21a4-134">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="b21a4-135">По умолчанию переменная может быть перезаписана, если только переменная не имеет значение параметра `ReadOnly` или `Constant` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-135">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="b21a4-136">Дополнительные сведения см. в описании параметра **Option** .</span><span class="sxs-lookup"><span data-stu-id="b21a4-136">For more information, see the **Option** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b21a4-137">-Include</span><span class="sxs-lookup"><span data-stu-id="b21a4-137">-Include</span></span>

<span data-ttu-id="b21a4-138">Задает массив элементов, включаемых этим командлетом в операцию.</span><span class="sxs-lookup"><span data-stu-id="b21a4-138">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b21a4-139">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="b21a4-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="b21a4-140">Введите имя или шаблон имени, например `c*` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-140">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="b21a4-141">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b21a4-141">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b21a4-142">-Name</span><span class="sxs-lookup"><span data-stu-id="b21a4-142">-Name</span></span>

<span data-ttu-id="b21a4-143">Определяет имя переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-143">Specifies the variable name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b21a4-144">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="b21a4-144">-Option</span></span>

<span data-ttu-id="b21a4-145">Задает значение свойства **Options** переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-145">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="b21a4-146">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b21a4-146">Valid values are:</span></span>

- <span data-ttu-id="b21a4-147">`None`: Задает параметры без параметров.</span><span class="sxs-lookup"><span data-stu-id="b21a4-147">`None`: Sets no options.</span></span> <span data-ttu-id="b21a4-148">(по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b21a4-148">("None" is the default.)</span></span>
- <span data-ttu-id="b21a4-149">`ReadOnly`: Можно удалить.</span><span class="sxs-lookup"><span data-stu-id="b21a4-149">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="b21a4-150">Нельзя изменить, за исключением использования параметра Force.</span><span class="sxs-lookup"><span data-stu-id="b21a4-150">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="b21a4-151">`Constant`: Невозможно удалить или изменить.</span><span class="sxs-lookup"><span data-stu-id="b21a4-151">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="b21a4-152">`Constant` параметр допустим только при создании переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-152">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="b21a4-153">Параметры существующей переменной нельзя изменить на `Constant` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-153">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="b21a4-154">`Private`: Переменная доступна только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="b21a4-154">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="b21a4-155">`AllScope`: Переменная копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="b21a4-155">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

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

### <span data-ttu-id="b21a4-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b21a4-156">-PassThru</span></span>

<span data-ttu-id="b21a4-157">Возвращает объект, представляющий новую переменную.</span><span class="sxs-lookup"><span data-stu-id="b21a4-157">Returns an object representing the new variable.</span></span> <span data-ttu-id="b21a4-158">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b21a4-158">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b21a4-159">-Scope</span><span class="sxs-lookup"><span data-stu-id="b21a4-159">-Scope</span></span>

<span data-ttu-id="b21a4-160">Задает область действия переменной. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b21a4-160">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b21a4-161">Глобальный</span><span class="sxs-lookup"><span data-stu-id="b21a4-161">Global</span></span>
- <span data-ttu-id="b21a4-162">Локальная</span><span class="sxs-lookup"><span data-stu-id="b21a4-162">Local</span></span>
- <span data-ttu-id="b21a4-163">Скрипт</span><span class="sxs-lookup"><span data-stu-id="b21a4-163">Script</span></span>
- <span data-ttu-id="b21a4-164">Частные</span><span class="sxs-lookup"><span data-stu-id="b21a4-164">Private</span></span>
- <span data-ttu-id="b21a4-165">Число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).</span><span class="sxs-lookup"><span data-stu-id="b21a4-165">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="b21a4-166">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="b21a4-166">Local is the default.</span></span>

<span data-ttu-id="b21a4-167">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="b21a4-167">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b21a4-168">-Value</span><span class="sxs-lookup"><span data-stu-id="b21a4-168">-Value</span></span>

<span data-ttu-id="b21a4-169">Задает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b21a4-169">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="b21a4-170">— Видимость</span><span class="sxs-lookup"><span data-stu-id="b21a4-170">-Visibility</span></span>

<span data-ttu-id="b21a4-171">Определяет, видима ли переменная вне сеанса, в котором она была создана.</span><span class="sxs-lookup"><span data-stu-id="b21a4-171">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="b21a4-172">Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="b21a4-172">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="b21a4-173">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b21a4-173">Valid values are:</span></span>

- <span data-ttu-id="b21a4-174">Public: переменная является видимой.</span><span class="sxs-lookup"><span data-stu-id="b21a4-174">Public:  The variable is visible.</span></span> <span data-ttu-id="b21a4-175">(Значение Public используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="b21a4-175">("Public" is the default.)</span></span>
- <span data-ttu-id="b21a4-176">Private: переменная не видна.</span><span class="sxs-lookup"><span data-stu-id="b21a4-176">Private: The variable is not visible.</span></span>

<span data-ttu-id="b21a4-177">Если переменная является закрытой, она не отображается в списках переменных, например, возвращаемых `Get-Variable` , или в режиме отображения **переменной:** Drive.</span><span class="sxs-lookup"><span data-stu-id="b21a4-177">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="b21a4-178">Команды чтения или изменения значения частной переменной возвращают ошибку.</span><span class="sxs-lookup"><span data-stu-id="b21a4-178">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="b21a4-179">Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.</span><span class="sxs-lookup"><span data-stu-id="b21a4-179">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b21a4-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b21a4-180">-Confirm</span></span>

<span data-ttu-id="b21a4-181">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b21a4-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b21a4-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b21a4-182">-WhatIf</span></span>

<span data-ttu-id="b21a4-183">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b21a4-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b21a4-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b21a4-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b21a4-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b21a4-185">CommonParameters</span></span>

<span data-ttu-id="b21a4-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b21a4-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b21a4-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b21a4-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b21a4-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b21a4-188">INPUTS</span></span>

### <span data-ttu-id="b21a4-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="b21a4-189">System.Object</span></span>

<span data-ttu-id="b21a4-190">Объект, представляющий значение переменной, можно передать по конвейеру `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="b21a4-190">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="b21a4-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b21a4-191">OUTPUTS</span></span>

### <span data-ttu-id="b21a4-192">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="b21a4-192">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="b21a4-193">При использовании параметра **PassThru** `Set-Variable` создает объект **System. Management. Automation. PSVariable** , представляющий новую или измененную переменную.</span><span class="sxs-lookup"><span data-stu-id="b21a4-193">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="b21a4-194">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b21a4-194">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b21a4-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b21a4-195">NOTES</span></span>

## <span data-ttu-id="b21a4-196">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b21a4-196">RELATED LINKS</span></span>

[<span data-ttu-id="b21a4-197">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="b21a4-197">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="b21a4-198">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="b21a4-198">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="b21a4-199">New-Variable</span><span class="sxs-lookup"><span data-stu-id="b21a4-199">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="b21a4-200">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="b21a4-200">Remove-Variable</span></span>](Remove-Variable.md)

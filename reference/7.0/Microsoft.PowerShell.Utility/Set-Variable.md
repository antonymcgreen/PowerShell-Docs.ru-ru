---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 876129fc8df9a78df257bf95220fc6587e68b9a2
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239845"
---
# <span data-ttu-id="2e63b-103">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="2e63b-103">Set-Variable</span></span>

## <span data-ttu-id="2e63b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2e63b-104">SYNOPSIS</span></span>
<span data-ttu-id="2e63b-105">Задает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-105">Sets the value of a variable.</span></span> <span data-ttu-id="2e63b-106">Создает переменную, если переменной с запрошенным именем не существует.</span><span class="sxs-lookup"><span data-stu-id="2e63b-106">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="2e63b-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e63b-107">SYNTAX</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2e63b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e63b-108">DESCRIPTION</span></span>

<span data-ttu-id="2e63b-109">`Set-Variable`Командлет присваивает значение указанной переменной или изменяет текущее значение.</span><span class="sxs-lookup"><span data-stu-id="2e63b-109">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="2e63b-110">Если переменная не существует, командлет создает ее.</span><span class="sxs-lookup"><span data-stu-id="2e63b-110">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="2e63b-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="2e63b-111">EXAMPLES</span></span>

### <span data-ttu-id="2e63b-112">Пример 1. задание переменной и получение ее значения</span><span class="sxs-lookup"><span data-stu-id="2e63b-112">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="2e63b-113">Эти команды задают значение `$desc` переменной `A description` , а затем получает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-113">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="2e63b-114">Пример 2. Задание глобальной переменной, доступной только для чтения</span><span class="sxs-lookup"><span data-stu-id="2e63b-114">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="2e63b-115">В этом примере создается глобальная переменная, доступная только для чтения, которая содержит все процессы в системе, а затем отображаются все свойства переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-115">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="2e63b-116">Команда использует `Set-Variable` командлет для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-116">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="2e63b-117">Он использует параметр **PassThru** для создания объекта, представляющего новую переменную, и использует оператор конвейера ( `|` ) для передачи объекта в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="2e63b-117">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="2e63b-118">**Property** `Format-List` `*` Для вывода всех свойств только что созданной переменной в нем используется параметр Property со значением All ().</span><span class="sxs-lookup"><span data-stu-id="2e63b-118">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="2e63b-119">Значение, `(Get-Process)` , заключено в круглые скобки, чтобы убедиться, что оно выполняется перед сохранением в переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-119">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="2e63b-120">В противном случае переменная содержит слова « **Get-Process** ».</span><span class="sxs-lookup"><span data-stu-id="2e63b-120">Otherwise, the variable contains the words " **Get-Process** ".</span></span>

### <span data-ttu-id="2e63b-121">Пример 3. Знакомство с открытыми и частными переменными</span><span class="sxs-lookup"><span data-stu-id="2e63b-121">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="2e63b-122">В этом примере показано, как изменить видимость переменной на `Private` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-122">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="2e63b-123">Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e63b-123">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

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

<span data-ttu-id="2e63b-124">Эта команда показывает, как изменить видимость переменной на Private.</span><span class="sxs-lookup"><span data-stu-id="2e63b-124">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="2e63b-125">Эту переменную могут читать и изменять скрипты с необходимыми разрешениями, но она невидима для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e63b-125">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="2e63b-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e63b-126">PARAMETERS</span></span>

### <span data-ttu-id="2e63b-127">-Description</span><span class="sxs-lookup"><span data-stu-id="2e63b-127">-Description</span></span>

<span data-ttu-id="2e63b-128">Задает описание переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-128">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="2e63b-129">-Exclude</span><span class="sxs-lookup"><span data-stu-id="2e63b-129">-Exclude</span></span>

<span data-ttu-id="2e63b-130">Указывает массив элементов, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="2e63b-130">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="2e63b-131">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="2e63b-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2e63b-132">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-132">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="2e63b-133">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2e63b-133">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2e63b-134">-Force</span><span class="sxs-lookup"><span data-stu-id="2e63b-134">-Force</span></span>

<span data-ttu-id="2e63b-135">Позволяет создать переменную с тем же именем, как у существующей переменной только для чтения, или изменить значение переменной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2e63b-135">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="2e63b-136">По умолчанию переменная может быть перезаписана, если только переменная не имеет значение параметра `ReadOnly` или `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-136">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="2e63b-137">Дополнительные сведения см. в описании параметра **Option** .</span><span class="sxs-lookup"><span data-stu-id="2e63b-137">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="2e63b-138">-Include</span><span class="sxs-lookup"><span data-stu-id="2e63b-138">-Include</span></span>

<span data-ttu-id="2e63b-139">Задает массив элементов, включаемых этим командлетом в операцию.</span><span class="sxs-lookup"><span data-stu-id="2e63b-139">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="2e63b-140">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="2e63b-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="2e63b-141">Введите имя или шаблон имени, например `c*` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-141">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="2e63b-142">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2e63b-142">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2e63b-143">-Name</span><span class="sxs-lookup"><span data-stu-id="2e63b-143">-Name</span></span>

<span data-ttu-id="2e63b-144">Определяет имя переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-144">Specifies the variable name.</span></span>

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

### <span data-ttu-id="2e63b-145">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="2e63b-145">-Option</span></span>

<span data-ttu-id="2e63b-146">Задает значение свойства **Options** переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-146">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="2e63b-147">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2e63b-147">Valid values are:</span></span>

- <span data-ttu-id="2e63b-148">`None`: Задает параметры без параметров.</span><span class="sxs-lookup"><span data-stu-id="2e63b-148">`None`: Sets no options.</span></span> <span data-ttu-id="2e63b-149">(по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2e63b-149">("None" is the default.)</span></span>
- <span data-ttu-id="2e63b-150">`ReadOnly`: Можно удалить.</span><span class="sxs-lookup"><span data-stu-id="2e63b-150">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="2e63b-151">Нельзя изменить, за исключением использования параметра Force.</span><span class="sxs-lookup"><span data-stu-id="2e63b-151">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="2e63b-152">`Constant`: Невозможно удалить или изменить.</span><span class="sxs-lookup"><span data-stu-id="2e63b-152">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="2e63b-153">`Constant` параметр допустим только при создании переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-153">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="2e63b-154">Параметры существующей переменной нельзя изменить на `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-154">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="2e63b-155">`Private`: Переменная доступна только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="2e63b-155">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="2e63b-156">`AllScope`: Переменная копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="2e63b-156">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

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

### <span data-ttu-id="2e63b-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2e63b-157">-PassThru</span></span>

<span data-ttu-id="2e63b-158">Возвращает объект, представляющий новую переменную.</span><span class="sxs-lookup"><span data-stu-id="2e63b-158">Returns an object representing the new variable.</span></span> <span data-ttu-id="2e63b-159">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2e63b-159">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2e63b-160">-Scope</span><span class="sxs-lookup"><span data-stu-id="2e63b-160">-Scope</span></span>

<span data-ttu-id="2e63b-161">Задает область действия переменной. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2e63b-161">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2e63b-162">Глобальный</span><span class="sxs-lookup"><span data-stu-id="2e63b-162">Global</span></span>
- <span data-ttu-id="2e63b-163">Локальная</span><span class="sxs-lookup"><span data-stu-id="2e63b-163">Local</span></span>
- <span data-ttu-id="2e63b-164">Сценарий</span><span class="sxs-lookup"><span data-stu-id="2e63b-164">Script</span></span>
- <span data-ttu-id="2e63b-165">Private</span><span class="sxs-lookup"><span data-stu-id="2e63b-165">Private</span></span>
- <span data-ttu-id="2e63b-166">Число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).</span><span class="sxs-lookup"><span data-stu-id="2e63b-166">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="2e63b-167">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="2e63b-167">Local is the default.</span></span>

<span data-ttu-id="2e63b-168">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="2e63b-168">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

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

### <span data-ttu-id="2e63b-169">-Value</span><span class="sxs-lookup"><span data-stu-id="2e63b-169">-Value</span></span>

<span data-ttu-id="2e63b-170">Задает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="2e63b-170">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="2e63b-171">— Видимость</span><span class="sxs-lookup"><span data-stu-id="2e63b-171">-Visibility</span></span>

<span data-ttu-id="2e63b-172">Определяет, видима ли переменная вне сеанса, в котором она была создана.</span><span class="sxs-lookup"><span data-stu-id="2e63b-172">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="2e63b-173">Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="2e63b-173">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="2e63b-174">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2e63b-174">Valid values are:</span></span>

- <span data-ttu-id="2e63b-175">Public: переменная является видимой.</span><span class="sxs-lookup"><span data-stu-id="2e63b-175">Public:  The variable is visible.</span></span> <span data-ttu-id="2e63b-176">(Значение Public используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="2e63b-176">("Public" is the default.)</span></span>
- <span data-ttu-id="2e63b-177">Private: переменная не видна.</span><span class="sxs-lookup"><span data-stu-id="2e63b-177">Private: The variable is not visible.</span></span>

<span data-ttu-id="2e63b-178">Если переменная является закрытой, она не отображается в списках переменных, например, возвращаемых `Get-Variable` , или в режиме отображения **переменной:** Drive.</span><span class="sxs-lookup"><span data-stu-id="2e63b-178">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="2e63b-179">Команды чтения или изменения значения частной переменной возвращают ошибку.</span><span class="sxs-lookup"><span data-stu-id="2e63b-179">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="2e63b-180">Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.</span><span class="sxs-lookup"><span data-stu-id="2e63b-180">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="2e63b-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e63b-181">-Confirm</span></span>

<span data-ttu-id="2e63b-182">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2e63b-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2e63b-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e63b-183">-WhatIf</span></span>

<span data-ttu-id="2e63b-184">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2e63b-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2e63b-185">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2e63b-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2e63b-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2e63b-186">CommonParameters</span></span>

<span data-ttu-id="2e63b-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e63b-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e63b-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e63b-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e63b-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2e63b-189">INPUTS</span></span>

### <span data-ttu-id="2e63b-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="2e63b-190">System.Object</span></span>

<span data-ttu-id="2e63b-191">Объект, представляющий значение переменной, можно передать по конвейеру `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="2e63b-191">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="2e63b-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2e63b-192">OUTPUTS</span></span>

### <span data-ttu-id="2e63b-193">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="2e63b-193">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="2e63b-194">При использовании параметра **PassThru** `Set-Variable` создает объект **System. Management. Automation. PSVariable** , представляющий новую или измененную переменную.</span><span class="sxs-lookup"><span data-stu-id="2e63b-194">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="2e63b-195">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2e63b-195">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2e63b-196">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2e63b-196">NOTES</span></span>

## <span data-ttu-id="2e63b-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2e63b-197">RELATED LINKS</span></span>

[<span data-ttu-id="2e63b-198">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="2e63b-198">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="2e63b-199">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="2e63b-199">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="2e63b-200">New-Variable</span><span class="sxs-lookup"><span data-stu-id="2e63b-200">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="2e63b-201">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="2e63b-201">Remove-Variable</span></span>](Remove-Variable.md)

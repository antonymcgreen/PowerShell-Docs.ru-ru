---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: fcb9af654f9e95f44e49ea984294b80752aa3453
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601595"
---
# <span data-ttu-id="05009-102">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="05009-102">Export-ModuleMember</span></span>

## <span data-ttu-id="05009-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="05009-103">SYNOPSIS</span></span>
<span data-ttu-id="05009-104">Задает элементы модуля, доступные для экспорта.</span><span class="sxs-lookup"><span data-stu-id="05009-104">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="05009-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05009-105">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="05009-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="05009-106">DESCRIPTION</span></span>

<span data-ttu-id="05009-107">Командлет **Export-ModuleMember** указывает элементы модуля, которые экспортируются из файла модуля скрипта (. PSM1), или из динамического модуля, созданного с помощью командлета New-Module.</span><span class="sxs-lookup"><span data-stu-id="05009-107">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="05009-108">К членам модуля относятся командлеты, функции, переменные и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="05009-108">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="05009-109">Этот командлет может использоваться только в файле модуля скрипта или в динамическом модуле.</span><span class="sxs-lookup"><span data-stu-id="05009-109">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="05009-110">Если модуль скрипта не содержит команду **Export-ModuleMember** , то функции и псевдонимы в модуле скрипта экспортируются, а переменные — нет.</span><span class="sxs-lookup"><span data-stu-id="05009-110">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="05009-111">Если модуль скрипта содержит команды **Export-ModuleMember** , экспортируются только элементы, указанные в командах **Export-ModuleMember** .</span><span class="sxs-lookup"><span data-stu-id="05009-111">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="05009-112">Можно также использовать **Export-ModuleMember** для подавления или экспорта элементов, импортируемых модулем скрипта из других модулей.</span><span class="sxs-lookup"><span data-stu-id="05009-112">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="05009-113">Команда **Export-ModuleMember** является необязательной, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="05009-113">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="05009-114">Даже если команда подтверждает значения по умолчанию, она демонстрирует намерения автора модуля.</span><span class="sxs-lookup"><span data-stu-id="05009-114">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="05009-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="05009-115">EXAMPLES</span></span>

### <span data-ttu-id="05009-116">Пример 1. Экспорт функций и псевдонимов в модуль скрипта</span><span class="sxs-lookup"><span data-stu-id="05009-116">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="05009-117">Эта команда экспортирует все функции и псевдонимы, определенные в модуле скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-117">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="05009-118">Пример 2. экспорт специальных псевдонимов и функций</span><span class="sxs-lookup"><span data-stu-id="05009-118">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="05009-119">Эта команда экспортирует три псевдонима и три функции, определенные в модуле скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-119">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="05009-120">Формат этой команды позволяет указать имена элементов модуля.</span><span class="sxs-lookup"><span data-stu-id="05009-120">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="05009-121">Пример 3. экспорт без элементов</span><span class="sxs-lookup"><span data-stu-id="05009-121">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="05009-122">Эта команда указывает, что экспорт элементов, определенных в модуле скрипта, запрещен.</span><span class="sxs-lookup"><span data-stu-id="05009-122">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="05009-123">Она запрещает экспорт элементов модуля, но не скрывает элементы.</span><span class="sxs-lookup"><span data-stu-id="05009-123">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="05009-124">Пользователи могут читать и копировать элементы модуля и использовать оператор вызова (&) для обращения к неэкспортируемым элементам модуля.</span><span class="sxs-lookup"><span data-stu-id="05009-124">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="05009-125">Пример 4. экспорт определенной переменной</span><span class="sxs-lookup"><span data-stu-id="05009-125">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="05009-126">Эта команда экспортирует из модуля скрипта только переменную $increment.</span><span class="sxs-lookup"><span data-stu-id="05009-126">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="05009-127">Остальные элементы не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="05009-127">No other members are exported.</span></span>

<span data-ttu-id="05009-128">Если вы хотите экспортировать переменную, помимо экспорта функций в модуль, команда **Export-ModuleMember** должна включать имена всех функций и имя переменной.</span><span class="sxs-lookup"><span data-stu-id="05009-128">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="05009-129">Пример 5. несколько команд экспорта</span><span class="sxs-lookup"><span data-stu-id="05009-129">Example 5: Multiple export commands</span></span>

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

<span data-ttu-id="05009-130">Эти команды показывают, как несколько команд **Export-ModuleMember** интерпретируется в файле модуля скрипта (. PSM1).</span><span class="sxs-lookup"><span data-stu-id="05009-130">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="05009-131">Они создают три функции и один псевдоним, а затем экспортируют две функции и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="05009-131">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="05009-132">Без команд **Export-ModuleMember** все три функции и псевдоним будут экспортированы.</span><span class="sxs-lookup"><span data-stu-id="05009-132">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="05009-133">При использовании команд **Export-ModuleMember** экспортируются только функции **New-Test** и **Start-Test** , а также псевдоним самонастраивающихся пороговых значений.</span><span class="sxs-lookup"><span data-stu-id="05009-133">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="05009-134">Пример 6. Экспорт элементов в динамический модуль</span><span class="sxs-lookup"><span data-stu-id="05009-134">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="05009-135">Эта команда показывает, как использовать Export-ModuleMember в динамическом модуле, созданном с помощью командлета **New-Module** .</span><span class="sxs-lookup"><span data-stu-id="05009-135">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="05009-136">В этом примере **Export-ModuleMember** используется для экспорта псевдонима Hi и функции **sayHello** в динамическом модуле.</span><span class="sxs-lookup"><span data-stu-id="05009-136">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="05009-137">Пример 7. объявление и экспорт функции в одной команде</span><span class="sxs-lookup"><span data-stu-id="05009-137">Example 7: Declare and export a function in a single command</span></span>

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

<span data-ttu-id="05009-138">В этом примере содержится функция с именем **Export** , которая объявляет функцию или создает переменную, а затем записывает `Export-ModuleMember` команду для функции или переменной.</span><span class="sxs-lookup"><span data-stu-id="05009-138">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="05009-139">Это позволяет объявлять и экспортировать функцию или переменную в одной команде.</span><span class="sxs-lookup"><span data-stu-id="05009-139">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="05009-140">Чтобы использовать функцию **экспорта** , включите ее в модуль скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-140">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="05009-141">Чтобы экспортировать функцию, введите `Export` перед ключевым словом **Function** .</span><span class="sxs-lookup"><span data-stu-id="05009-141">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="05009-142">Чтобы экспортировать переменную, используйте следующий формат для объявления переменной и задания ее значения:</span><span class="sxs-lookup"><span data-stu-id="05009-142">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="05009-143">В примере показан правильный формат команд.</span><span class="sxs-lookup"><span data-stu-id="05009-143">The commands in the example show the correct format.</span></span>
<span data-ttu-id="05009-144">В этом примере экспортируются только функция **New-Test** и переменная $Interval.</span><span class="sxs-lookup"><span data-stu-id="05009-144">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="05009-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05009-145">PARAMETERS</span></span>

### <span data-ttu-id="05009-146">-Alias</span><span class="sxs-lookup"><span data-stu-id="05009-146">-Alias</span></span>

<span data-ttu-id="05009-147">Задает псевдонимы, экспортируемые из файла модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-147">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="05009-148">Введите имена псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="05009-148">Enter the alias names.</span></span>
<span data-ttu-id="05009-149">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05009-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="05009-150">Командлет</span><span class="sxs-lookup"><span data-stu-id="05009-150">-Cmdlet</span></span>

<span data-ttu-id="05009-151">Задает командлеты, экспортируемые из файла модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-151">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="05009-152">Введите имена командлетов.</span><span class="sxs-lookup"><span data-stu-id="05009-152">Enter the cmdlet names.</span></span>
<span data-ttu-id="05009-153">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05009-153">Wildcard characters are permitted.</span></span>

<span data-ttu-id="05009-154">В файле модуля скрипта нельзя создавать командлеты, однако, их можно импортировать из двоичного модуля в модуль скрипта и экспортировать из модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-154">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="05009-155">-Function</span><span class="sxs-lookup"><span data-stu-id="05009-155">-Function</span></span>

<span data-ttu-id="05009-156">Задает функции, экспортируемые из файла модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-156">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="05009-157">Введите имена функций.</span><span class="sxs-lookup"><span data-stu-id="05009-157">Enter the function names.</span></span>
<span data-ttu-id="05009-158">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05009-158">Wildcard characters are permitted.</span></span>
<span data-ttu-id="05009-159">Вы также можете передать строки имени функции в **Export-ModuleMember**.</span><span class="sxs-lookup"><span data-stu-id="05009-159">You can also pipe function name strings to **Export-ModuleMember**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="05009-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="05009-160">-Variable</span></span>

<span data-ttu-id="05009-161">Задает переменные, экспортируемые из файла модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="05009-161">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="05009-162">Введите имена переменных без знака доллара.</span><span class="sxs-lookup"><span data-stu-id="05009-162">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="05009-163">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05009-163">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="05009-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="05009-164">CommonParameters</span></span>

<span data-ttu-id="05009-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="05009-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="05009-166">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="05009-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="05009-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="05009-167">INPUTS</span></span>

### <span data-ttu-id="05009-168">System.String</span><span class="sxs-lookup"><span data-stu-id="05009-168">System.String</span></span>

<span data-ttu-id="05009-169">В этот командлет можно передать строки имени функции.</span><span class="sxs-lookup"><span data-stu-id="05009-169">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="05009-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="05009-170">OUTPUTS</span></span>

### <span data-ttu-id="05009-171">None</span><span class="sxs-lookup"><span data-stu-id="05009-171">None</span></span>

<span data-ttu-id="05009-172">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="05009-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="05009-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="05009-173">NOTES</span></span>

* <span data-ttu-id="05009-174">Чтобы исключить член из списка экспортируемых элементов, добавьте команду **Export-ModuleMember** , которая перечисляет все остальные элементы, но не включает элемент, который требуется исключить.</span><span class="sxs-lookup"><span data-stu-id="05009-174">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="05009-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="05009-175">RELATED LINKS</span></span>

[<span data-ttu-id="05009-176">Get-Module</span><span class="sxs-lookup"><span data-stu-id="05009-176">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="05009-177">Import-Module</span><span class="sxs-lookup"><span data-stu-id="05009-177">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="05009-178">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="05009-178">Remove-Module</span></span>](Remove-Module.md)


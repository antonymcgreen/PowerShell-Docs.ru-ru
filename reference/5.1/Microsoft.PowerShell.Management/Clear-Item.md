---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: a0854fbff06ea51c322bdaf46c81f47f76af978b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228438"
---
# <span data-ttu-id="89089-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="89089-103">Clear-Item</span></span>

## <span data-ttu-id="89089-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="89089-104">SYNOPSIS</span></span>
<span data-ttu-id="89089-105">Удаляет содержимое элемента, но не удаляет его.</span><span class="sxs-lookup"><span data-stu-id="89089-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="89089-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89089-106">SYNTAX</span></span>

### <span data-ttu-id="89089-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="89089-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="89089-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89089-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="89089-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89089-109">DESCRIPTION</span></span>

<span data-ttu-id="89089-110">`Clear-Item`Командлет удаляет содержимое элемента, но элемент не удаляется.</span><span class="sxs-lookup"><span data-stu-id="89089-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="89089-111">Например, `Clear-Item` командлет может удалить значение переменной, но не удаляет переменную.</span><span class="sxs-lookup"><span data-stu-id="89089-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="89089-112">Значение, которое используется для представления пустого элемента, определяется каждым поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89089-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="89089-113">Этот командлет аналогичен `Clear-Content` , но он работает с псевдонимами и переменными, а не с файлами.</span><span class="sxs-lookup"><span data-stu-id="89089-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="89089-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="89089-114">EXAMPLES</span></span>

### <span data-ttu-id="89089-115">Пример 1. Очистка значения переменной</span><span class="sxs-lookup"><span data-stu-id="89089-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="89089-116">Эта команда очищает значение переменной с именем `TestVar1` .</span><span class="sxs-lookup"><span data-stu-id="89089-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="89089-117">Переменная остается и является допустимой, но ей присваивается значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="89089-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="89089-118">Имя переменной указывается с префиксом, `Variable:` чтобы указать поставщика переменных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89089-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="89089-119">Альтернативные команды показывают, что для получения такого же результата можно переключиться на диск PowerShell, `Variable:` а затем выполнить `Clear-Item` команду.</span><span class="sxs-lookup"><span data-stu-id="89089-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="89089-120">Пример 2. Очистка всех записей реестра</span><span class="sxs-lookup"><span data-stu-id="89089-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="89089-121">Эта команда удаляет все записи реестра в подразделе "MyKey", но только после того, как предложит подтвердить намерение.</span><span class="sxs-lookup"><span data-stu-id="89089-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="89089-122">Он не удаляет подраздел "MyKey" или не влияет на другие разделы или записи реестра.</span><span class="sxs-lookup"><span data-stu-id="89089-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="89089-123">Параметры **Include** и **Exclude** можно использовать для задания определенных разделов реестра, однако их нельзя использовать для задания записей реестра.</span><span class="sxs-lookup"><span data-stu-id="89089-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="89089-124">Чтобы удалить определенные записи реестра, используйте `Remove-ItemProperty` командлет.</span><span class="sxs-lookup"><span data-stu-id="89089-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="89089-125">Чтобы удалить значение записи реестра, используйте `Clear-ItemProperty` командлет.</span><span class="sxs-lookup"><span data-stu-id="89089-125">To delete the value of a registry entry, use the `Clear-ItemProperty` cmdlet.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="89089-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89089-126">PARAMETERS</span></span>

### <span data-ttu-id="89089-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="89089-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="89089-128">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89089-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="89089-129">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="89089-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89089-130">-Exclude</span><span class="sxs-lookup"><span data-stu-id="89089-130">-Exclude</span></span>

<span data-ttu-id="89089-131">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="89089-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="89089-132">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="89089-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89089-133">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="89089-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="89089-134">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="89089-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="89089-135">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="89089-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89089-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="89089-136">-Filter</span></span>

<span data-ttu-id="89089-137">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="89089-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="89089-138">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="89089-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="89089-139">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="89089-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="89089-140">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="89089-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="89089-141">-Force</span><span class="sxs-lookup"><span data-stu-id="89089-141">-Force</span></span>

<span data-ttu-id="89089-142">Указывает, что командлет очищает элементы, которые в противном случае не могут быть изменены, например псевдонимы только для чтения.</span><span class="sxs-lookup"><span data-stu-id="89089-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="89089-143">Командлет не может очищать константы.</span><span class="sxs-lookup"><span data-stu-id="89089-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="89089-144">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="89089-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="89089-145">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="89089-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="89089-146">Командлет не может переопределить ограничения безопасности, даже если используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="89089-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="89089-147">-Include</span><span class="sxs-lookup"><span data-stu-id="89089-147">-Include</span></span>

<span data-ttu-id="89089-148">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="89089-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="89089-149">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="89089-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89089-150">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="89089-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="89089-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="89089-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="89089-152">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="89089-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89089-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89089-153">-LiteralPath</span></span>

<span data-ttu-id="89089-154">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="89089-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="89089-155">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="89089-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="89089-156">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="89089-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="89089-157">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="89089-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="89089-158">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="89089-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="89089-159">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="89089-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89089-160">-Path</span><span class="sxs-lookup"><span data-stu-id="89089-160">-Path</span></span>

<span data-ttu-id="89089-161">Указывает путь к очищаемым элементам.</span><span class="sxs-lookup"><span data-stu-id="89089-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="89089-162">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="89089-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="89089-163">Этот параметр является обязательным, но **путь к** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="89089-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="89089-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="89089-164">-UseTransaction</span></span>

<span data-ttu-id="89089-165">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="89089-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="89089-166">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="89089-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="89089-167">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="89089-167">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89089-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="89089-168">-Confirm</span></span>

<span data-ttu-id="89089-169">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="89089-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="89089-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="89089-170">-WhatIf</span></span>

<span data-ttu-id="89089-171">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="89089-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="89089-172">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="89089-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="89089-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="89089-173">CommonParameters</span></span>

<span data-ttu-id="89089-174">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="89089-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="89089-175">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="89089-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="89089-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="89089-176">INPUTS</span></span>

### <span data-ttu-id="89089-177">System.String</span><span class="sxs-lookup"><span data-stu-id="89089-177">System.String</span></span>

<span data-ttu-id="89089-178">Строку пути можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="89089-178">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="89089-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="89089-179">OUTPUTS</span></span>

### <span data-ttu-id="89089-180">Нет</span><span class="sxs-lookup"><span data-stu-id="89089-180">None</span></span>

<span data-ttu-id="89089-181">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="89089-181">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="89089-182">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="89089-182">NOTES</span></span>

- <span data-ttu-id="89089-183">`Clear-Item`Командлет поддерживается только несколькими поставщиками PowerShell, включая **псевдонимы** , **среды** , **функции** , **Реестр** и поставщики **переменных** .</span><span class="sxs-lookup"><span data-stu-id="89089-183">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="89089-184">Таким образом, можно использовать `Clear-Item` для удаления содержимого элементов в пространствах имен поставщика.</span><span class="sxs-lookup"><span data-stu-id="89089-184">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="89089-185">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="89089-185">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="89089-186">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="89089-186">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="89089-187">Нельзя использовать `Clear-Item` для удаления содержимого файла, так как поставщик файловой системы PowerShell не поддерживает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="89089-187">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="89089-188">Чтобы очистить файлы, используйте `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="89089-188">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="89089-189">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="89089-189">RELATED LINKS</span></span>

[<span data-ttu-id="89089-190">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="89089-190">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="89089-191">Get-Item</span><span class="sxs-lookup"><span data-stu-id="89089-191">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="89089-192">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="89089-192">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="89089-193">Move-Item</span><span class="sxs-lookup"><span data-stu-id="89089-193">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="89089-194">New-Item</span><span class="sxs-lookup"><span data-stu-id="89089-194">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="89089-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="89089-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="89089-196">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="89089-196">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="89089-197">Set-Item</span><span class="sxs-lookup"><span data-stu-id="89089-197">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="89089-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="89089-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

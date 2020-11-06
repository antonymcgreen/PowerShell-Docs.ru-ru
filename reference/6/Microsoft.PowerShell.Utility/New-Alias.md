---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: f3ae6a8873b82fd0efe39f677c640917ce9dd779
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228954"
---
# <span data-ttu-id="0e770-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="0e770-103">New-Alias</span></span>

## <span data-ttu-id="0e770-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0e770-104">SYNOPSIS</span></span>
<span data-ttu-id="0e770-105">Создает новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0e770-105">Creates a new alias.</span></span>

## <span data-ttu-id="0e770-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e770-106">SYNTAX</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e770-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e770-107">DESCRIPTION</span></span>

<span data-ttu-id="0e770-108">Командлет **New-Alias** создает новый псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e770-108">The **New-Alias** cmdlet creates a new alias in the current PowerShell session.</span></span>
<span data-ttu-id="0e770-109">Псевдонимы, созданные с помощью **New-Alias** , не сохраняются после выхода из сеанса или закрытия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e770-109">Aliases created by using **New-Alias** are not saved after you exit the session or close PowerShell.</span></span>
<span data-ttu-id="0e770-110">Командлет Export-Alias можно использовать для сохранения сведений о псевдонимах в файл.</span><span class="sxs-lookup"><span data-stu-id="0e770-110">You can use the Export-Alias cmdlet to save your alias information to a file.</span></span>
<span data-ttu-id="0e770-111">Позже можно будет использовать **Import-Alias** для получения сохраненных сведений о псевдониме.</span><span class="sxs-lookup"><span data-stu-id="0e770-111">You can later use **Import-Alias** to retrieve that saved alias information.</span></span>

## <span data-ttu-id="0e770-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="0e770-112">EXAMPLES</span></span>

### <span data-ttu-id="0e770-113">Пример 1. Создание псевдонима для командлета</span><span class="sxs-lookup"><span data-stu-id="0e770-113">Example 1: Create an alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="0e770-114">Эта команда создает псевдоним с именем List для представления командлета Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="0e770-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="0e770-115">Пример 2. Создание псевдонима, доступного только для чтения, для командлета</span><span class="sxs-lookup"><span data-stu-id="0e770-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

<span data-ttu-id="0e770-116">Эта команда создает псевдоним W для представления командлета Get-WmiObject.</span><span class="sxs-lookup"><span data-stu-id="0e770-116">This command creates an alias named W to represent the Get-WmiObject cmdlet.</span></span>
<span data-ttu-id="0e770-117">Он создает описание, быстрый псевдоним WMI для псевдонима и делает его доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0e770-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span>
<span data-ttu-id="0e770-118">В последней строке командлет Get-Alias возвращает новый псевдоним и передает его в командлет Format-List по конвейеру для отображения всех данных о псевдониме.</span><span class="sxs-lookup"><span data-stu-id="0e770-118">The last line of the command uses Get-Alias to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="0e770-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e770-119">PARAMETERS</span></span>

### <span data-ttu-id="0e770-120">-Description</span><span class="sxs-lookup"><span data-stu-id="0e770-120">-Description</span></span>

<span data-ttu-id="0e770-121">Указывает описание псевдонима.</span><span class="sxs-lookup"><span data-stu-id="0e770-121">Specifies a description of the alias.</span></span>
<span data-ttu-id="0e770-122">Можно ввести любую строку.</span><span class="sxs-lookup"><span data-stu-id="0e770-122">You can type any string.</span></span>
<span data-ttu-id="0e770-123">Если описание содержит пробелы, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="0e770-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="0e770-124">-Force</span><span class="sxs-lookup"><span data-stu-id="0e770-124">-Force</span></span>

<span data-ttu-id="0e770-125">Указывает, что командлет действует как Set-Alias, если псевдоним с именем уже существует.</span><span class="sxs-lookup"><span data-stu-id="0e770-125">Indicates that the cmdlet acts like Set-Alias if the alias named already exists.</span></span>

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

### <span data-ttu-id="0e770-126">-Name</span><span class="sxs-lookup"><span data-stu-id="0e770-126">-Name</span></span>

<span data-ttu-id="0e770-127">Указывает новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0e770-127">Specifies the new alias.</span></span>
<span data-ttu-id="0e770-128">В псевдониме можно использовать любые буквы или цифры, но первым знаком не может быть цифра.</span><span class="sxs-lookup"><span data-stu-id="0e770-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

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

### <span data-ttu-id="0e770-129">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="0e770-129">-Option</span></span>

<span data-ttu-id="0e770-130">Задает значение свойства **Options** псевдонима.</span><span class="sxs-lookup"><span data-stu-id="0e770-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="0e770-131">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0e770-131">Valid values are:</span></span>

- <span data-ttu-id="0e770-132">Нет: псевдоним не имеет ограничений (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0e770-132">None: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="0e770-133">ReadOnly: псевдоним можно удалить, но нельзя изменить, только используя параметр **Force**</span><span class="sxs-lookup"><span data-stu-id="0e770-133">ReadOnly: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="0e770-134">Константа: невозможно удалить или изменить псевдоним</span><span class="sxs-lookup"><span data-stu-id="0e770-134">Constant: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="0e770-135">Частный: псевдоним доступен только в текущей области видимости</span><span class="sxs-lookup"><span data-stu-id="0e770-135">Private: The alias is available only in the current scope</span></span>
- <span data-ttu-id="0e770-136">AllScope: Псевдоним копируется во все новые создаваемые области</span><span class="sxs-lookup"><span data-stu-id="0e770-136">AllScope: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="0e770-137">Не указано: параметр не указан</span><span class="sxs-lookup"><span data-stu-id="0e770-137">Unspecified: The option is not specified</span></span>

<span data-ttu-id="0e770-138">Чтобы просмотреть свойство **Options** всех псевдонимов в сеансе, введите `Get-Alias | Format-Table -Property Name, Options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="0e770-138">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e770-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0e770-139">-PassThru</span></span>

<span data-ttu-id="0e770-140">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="0e770-140">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="0e770-141">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0e770-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0e770-142">-Scope</span><span class="sxs-lookup"><span data-stu-id="0e770-142">-Scope</span></span>

<span data-ttu-id="0e770-143">Указывает область действия нового псевдонима.</span><span class="sxs-lookup"><span data-stu-id="0e770-143">Specifies the scope of the new alias.</span></span>
<span data-ttu-id="0e770-144">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0e770-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0e770-145">Глобальный</span><span class="sxs-lookup"><span data-stu-id="0e770-145">Global</span></span>
- <span data-ttu-id="0e770-146">Локальная</span><span class="sxs-lookup"><span data-stu-id="0e770-146">Local</span></span>
- <span data-ttu-id="0e770-147">Сценарий</span><span class="sxs-lookup"><span data-stu-id="0e770-147">Script</span></span>
- <span data-ttu-id="0e770-148">Число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).</span><span class="sxs-lookup"><span data-stu-id="0e770-148">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="0e770-149">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="0e770-149">Local is the default.</span></span>
<span data-ttu-id="0e770-150">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="0e770-150">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="0e770-151">-Value</span><span class="sxs-lookup"><span data-stu-id="0e770-151">-Value</span></span>

<span data-ttu-id="0e770-152">Указывает имя командлета или элемента команды, для которого создается псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0e770-152">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e770-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e770-153">-Confirm</span></span>

<span data-ttu-id="0e770-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0e770-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e770-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e770-155">-WhatIf</span></span>

<span data-ttu-id="0e770-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0e770-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0e770-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0e770-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e770-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0e770-158">CommonParameters</span></span>

<span data-ttu-id="0e770-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e770-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e770-160">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e770-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e770-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0e770-161">INPUTS</span></span>

### <span data-ttu-id="0e770-162">Нет</span><span class="sxs-lookup"><span data-stu-id="0e770-162">None</span></span>

<span data-ttu-id="0e770-163">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="0e770-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0e770-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0e770-164">OUTPUTS</span></span>

### <span data-ttu-id="0e770-165">None или System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="0e770-165">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="0e770-166">При использовании параметра *PassThru* командлет **New-Alias** создает объект **System. Management. Automation. AliasInfo** , представляющий новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0e770-166">When you use the *Passthru* parameter, **New-Alias** generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span>
<span data-ttu-id="0e770-167">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0e770-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e770-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0e770-168">NOTES</span></span>

* <span data-ttu-id="0e770-169">Чтобы создать новый псевдоним, используйте `Set-Alias` или `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="0e770-169">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="0e770-170">Чтобы изменить псевдоним, используйте `Set-Alias` .</span><span class="sxs-lookup"><span data-stu-id="0e770-170">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="0e770-171">Чтобы удалить псевдоним, используйте `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="0e770-171">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="0e770-172">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0e770-172">RELATED LINKS</span></span>

[<span data-ttu-id="0e770-173">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="0e770-173">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="0e770-174">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="0e770-174">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="0e770-175">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="0e770-175">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="0e770-176">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="0e770-176">Set-Alias</span></span>](Set-Alias.md)
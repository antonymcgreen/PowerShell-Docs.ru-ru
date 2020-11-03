---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 438f089c1cd6e647ae5ee858234a3919bdc0328d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228701"
---
# <span data-ttu-id="08e35-103">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="08e35-103">Import-Alias</span></span>

## <span data-ttu-id="08e35-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="08e35-104">SYNOPSIS</span></span>
<span data-ttu-id="08e35-105">Импортирует список псевдонимов из файла.</span><span class="sxs-lookup"><span data-stu-id="08e35-105">Imports an alias list from a file.</span></span>

## <span data-ttu-id="08e35-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08e35-106">SYNTAX</span></span>

### <span data-ttu-id="08e35-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="08e35-107">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08e35-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="08e35-108">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="08e35-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e35-109">DESCRIPTION</span></span>

<span data-ttu-id="08e35-110">`Import-Alias`Командлет импортирует список псевдонимов из файла.</span><span class="sxs-lookup"><span data-stu-id="08e35-110">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="08e35-111">Начиная с Windows PowerShell 3,0, в качестве функции безопасности не `Import-Alias` перезаписывает существующие псевдонимы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08e35-111">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="08e35-112">Для перезаписи существующего псевдонима используйте параметр **Force** (предварительно убедившись в безопасности содержимого файла этого псевдонима).</span><span class="sxs-lookup"><span data-stu-id="08e35-112">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="08e35-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="08e35-113">EXAMPLES</span></span>

### <span data-ttu-id="08e35-114">Пример 1. импорт псевдонимов из файла</span><span class="sxs-lookup"><span data-stu-id="08e35-114">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="08e35-115">Эта команда импортирует сведения о псевдонимах из файла Test.txt.</span><span class="sxs-lookup"><span data-stu-id="08e35-115">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="08e35-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08e35-116">PARAMETERS</span></span>

### <span data-ttu-id="08e35-117">-Force</span><span class="sxs-lookup"><span data-stu-id="08e35-117">-Force</span></span>

<span data-ttu-id="08e35-118">Позволяет командлету импортировать псевдоним, который уже определен и доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="08e35-118">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="08e35-119">Для отображения сведений об определенных на текущий момент псевдонимах можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="08e35-119">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="08e35-120">Если соответствующий псевдоним доступен только для чтения, это будет указано в значении свойства **Options** .</span><span class="sxs-lookup"><span data-stu-id="08e35-120">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="08e35-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="08e35-121">-LiteralPath</span></span>

<span data-ttu-id="08e35-122">Задает путь к файлу, содержащему экспортированные сведения о псевдонимах.</span><span class="sxs-lookup"><span data-stu-id="08e35-122">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="08e35-123">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="08e35-123">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="08e35-124">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="08e35-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="08e35-125">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="08e35-125">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="08e35-126">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="08e35-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="08e35-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="08e35-127">-PassThru</span></span>

<span data-ttu-id="08e35-128">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="08e35-128">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="08e35-129">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="08e35-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="08e35-130">-Path</span><span class="sxs-lookup"><span data-stu-id="08e35-130">-Path</span></span>

<span data-ttu-id="08e35-131">Задает путь к файлу, содержащему экспортированные сведения о псевдонимах.</span><span class="sxs-lookup"><span data-stu-id="08e35-131">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="08e35-132">Использовать подстановочные знаки можно, но они должны указывать только на одно имя.</span><span class="sxs-lookup"><span data-stu-id="08e35-132">Wildcards are allowed but they must resolve to a single name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="08e35-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="08e35-133">-Scope</span></span>

<span data-ttu-id="08e35-134">Задает область, в которую будут импортироваться псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="08e35-134">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="08e35-135">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="08e35-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="08e35-136">Глобальный</span><span class="sxs-lookup"><span data-stu-id="08e35-136">Global</span></span>
- <span data-ttu-id="08e35-137">Локальная</span><span class="sxs-lookup"><span data-stu-id="08e35-137">Local</span></span>
- <span data-ttu-id="08e35-138">Сценарий</span><span class="sxs-lookup"><span data-stu-id="08e35-138">Script</span></span>
- <span data-ttu-id="08e35-139">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="08e35-139">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="08e35-140">Значение по умолчанию — Local.</span><span class="sxs-lookup"><span data-stu-id="08e35-140">The default is Local.</span></span>
<span data-ttu-id="08e35-141">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="08e35-141">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="08e35-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08e35-142">-Confirm</span></span>

<span data-ttu-id="08e35-143">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="08e35-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08e35-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08e35-144">-WhatIf</span></span>

<span data-ttu-id="08e35-145">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="08e35-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="08e35-146">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="08e35-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="08e35-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="08e35-147">CommonParameters</span></span>

<span data-ttu-id="08e35-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08e35-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08e35-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08e35-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08e35-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="08e35-150">INPUTS</span></span>

### <span data-ttu-id="08e35-151">System.String</span><span class="sxs-lookup"><span data-stu-id="08e35-151">System.String</span></span>

<span data-ttu-id="08e35-152">Можно передать строку, содержащую путь, в `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="08e35-152">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="08e35-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="08e35-153">OUTPUTS</span></span>

### <span data-ttu-id="08e35-154">None или System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="08e35-154">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="08e35-155">При использовании параметра **PassThru** `Import-Alias` возвращает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="08e35-155">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="08e35-156">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="08e35-156">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08e35-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="08e35-157">NOTES</span></span>

## <span data-ttu-id="08e35-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="08e35-158">RELATED LINKS</span></span>

[<span data-ttu-id="08e35-159">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="08e35-159">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="08e35-160">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="08e35-160">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="08e35-161">New-Alias</span><span class="sxs-lookup"><span data-stu-id="08e35-161">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="08e35-162">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="08e35-162">Set-Alias</span></span>](Set-Alias.md)

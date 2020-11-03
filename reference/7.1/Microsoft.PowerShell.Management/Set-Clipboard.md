---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 6fbe7b1e5534b1227bcfd73fd58f3602186ef8c5
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239675"
---
# <span data-ttu-id="d3541-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d3541-103">Set-Clipboard</span></span>

## <span data-ttu-id="d3541-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d3541-104">SYNOPSIS</span></span>
<span data-ttu-id="d3541-105">Задает содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="d3541-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="d3541-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3541-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d3541-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3541-107">DESCRIPTION</span></span>

<span data-ttu-id="d3541-108">`Set-Clipboard`Командлет задает содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="d3541-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="d3541-109">В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.</span><span class="sxs-lookup"><span data-stu-id="d3541-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="d3541-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d3541-110">EXAMPLES</span></span>

### <span data-ttu-id="d3541-111">Пример 1. копирование текста в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="d3541-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

## <span data-ttu-id="d3541-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3541-112">PARAMETERS</span></span>

### <span data-ttu-id="d3541-113">— Добавление</span><span class="sxs-lookup"><span data-stu-id="d3541-113">-Append</span></span>

<span data-ttu-id="d3541-114">Указывает, что командлет не очищает буфер обмена и добавляет к нему содержимое.</span><span class="sxs-lookup"><span data-stu-id="d3541-114">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="d3541-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d3541-115">-Confirm</span></span>

<span data-ttu-id="d3541-116">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d3541-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d3541-117">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d3541-117">-WhatIf</span></span>

<span data-ttu-id="d3541-118">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d3541-118">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d3541-119">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d3541-119">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d3541-120">-Value</span><span class="sxs-lookup"><span data-stu-id="d3541-120">-Value</span></span>

<span data-ttu-id="d3541-121">Строковые значения, которые необходимо добавить в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d3541-121">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d3541-122">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d3541-122">CommonParameters</span></span>

<span data-ttu-id="d3541-123">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3541-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3541-124">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3541-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3541-125">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d3541-125">INPUTS</span></span>

### <span data-ttu-id="d3541-126">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d3541-126">System.String[]</span></span>

## <span data-ttu-id="d3541-127">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d3541-127">OUTPUTS</span></span>

## <span data-ttu-id="d3541-128">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d3541-128">NOTES</span></span>

<span data-ttu-id="d3541-129">В редких случаях при `Set-Clipboard` быстром выполнении с большим количеством значений, например в цикле, вы можете регулярно получать пустое значение из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="d3541-129">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="d3541-130">Это можно исправить с помощью `Start-Sleep -Milliseconds 1` в цикле.</span><span class="sxs-lookup"><span data-stu-id="d3541-130">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="d3541-131">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d3541-131">RELATED LINKS</span></span>

[<span data-ttu-id="d3541-132">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d3541-132">Get-Clipboard</span></span>](Get-Clipboard.md)

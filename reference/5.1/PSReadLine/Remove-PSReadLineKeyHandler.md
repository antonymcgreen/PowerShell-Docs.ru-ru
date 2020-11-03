---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadline
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: e0cdd2358cfd4819285947b1f703963691088e2b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93232998"
---
# <span data-ttu-id="57f67-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="57f67-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="57f67-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="57f67-104">SYNOPSIS</span></span>
<span data-ttu-id="57f67-105">Удаляет привязку клавиш.</span><span class="sxs-lookup"><span data-stu-id="57f67-105">Removes a key binding.</span></span>

## <span data-ttu-id="57f67-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57f67-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="57f67-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="57f67-107">DESCRIPTION</span></span>

<span data-ttu-id="57f67-108">`Remove-PSReadLineKeyHandler`Командлет удаляет указанную привязку ключа.</span><span class="sxs-lookup"><span data-stu-id="57f67-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="57f67-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="57f67-109">EXAMPLES</span></span>

### <span data-ttu-id="57f67-110">Пример 1. Удаление привязки</span><span class="sxs-lookup"><span data-stu-id="57f67-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="57f67-111">Эта команда удаляет привязку из сочетания клавиш или аккорд `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="57f67-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="57f67-112">`Ctrl+B`Аккорд создается в этой `Set-PSReadLineKeyHandler` статье.</span><span class="sxs-lookup"><span data-stu-id="57f67-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="57f67-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57f67-113">PARAMETERS</span></span>

### <span data-ttu-id="57f67-114">-Chord</span><span class="sxs-lookup"><span data-stu-id="57f67-114">-Chord</span></span>

<span data-ttu-id="57f67-115">Указывает массив ключей или последовательностей удаляемых ключей.</span><span class="sxs-lookup"><span data-stu-id="57f67-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="57f67-116">Одну привязку можно задать в одной строке.</span><span class="sxs-lookup"><span data-stu-id="57f67-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="57f67-117">Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="57f67-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="57f67-118">Этот параметр принимает массив строк.</span><span class="sxs-lookup"><span data-stu-id="57f67-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="57f67-119">Каждая строка — это отдельная привязка, а не сочетание клавиш для одной привязки.</span><span class="sxs-lookup"><span data-stu-id="57f67-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57f67-120">-Вимоде</span><span class="sxs-lookup"><span data-stu-id="57f67-120">-ViMode</span></span>

<span data-ttu-id="57f67-121">Укажите режим VI, к которому применяется привязка.</span><span class="sxs-lookup"><span data-stu-id="57f67-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="57f67-122">Возможные значения: INSERT, Command.</span><span class="sxs-lookup"><span data-stu-id="57f67-122">Possible values are: Insert, Command.</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57f67-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="57f67-123">CommonParameters</span></span>

<span data-ttu-id="57f67-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="57f67-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57f67-125">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="57f67-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="57f67-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="57f67-126">INPUTS</span></span>

### <span data-ttu-id="57f67-127">Нет</span><span class="sxs-lookup"><span data-stu-id="57f67-127">None</span></span>

<span data-ttu-id="57f67-128">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="57f67-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="57f67-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="57f67-129">OUTPUTS</span></span>

### <span data-ttu-id="57f67-130">Нет</span><span class="sxs-lookup"><span data-stu-id="57f67-130">None</span></span>

## <span data-ttu-id="57f67-131">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="57f67-131">NOTES</span></span>

## <span data-ttu-id="57f67-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="57f67-132">RELATED LINKS</span></span>

[<span data-ttu-id="57f67-133">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="57f67-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="57f67-134">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="57f67-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="57f67-135">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="57f67-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="57f67-136">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="57f67-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

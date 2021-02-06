---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601490"
---
# <span data-ttu-id="afbde-102">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="afbde-102">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="afbde-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="afbde-103">SYNOPSIS</span></span>
<span data-ttu-id="afbde-104">Удаляет привязку клавиш.</span><span class="sxs-lookup"><span data-stu-id="afbde-104">Removes a key binding.</span></span>

## <span data-ttu-id="afbde-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="afbde-105">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="afbde-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="afbde-106">DESCRIPTION</span></span>

<span data-ttu-id="afbde-107">`Remove-PSReadLineKeyHandler`Командлет удаляет указанную привязку ключа.</span><span class="sxs-lookup"><span data-stu-id="afbde-107">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="afbde-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="afbde-108">EXAMPLES</span></span>

### <span data-ttu-id="afbde-109">Пример 1. Удаление привязки</span><span class="sxs-lookup"><span data-stu-id="afbde-109">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="afbde-110">Эта команда удаляет привязку из сочетания клавиш или аккорд `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="afbde-110">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="afbde-111">`Ctrl+B`Аккорд создается в этой `Set-PSReadLineKeyHandler` статье.</span><span class="sxs-lookup"><span data-stu-id="afbde-111">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="afbde-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="afbde-112">PARAMETERS</span></span>

### <span data-ttu-id="afbde-113">-Chord</span><span class="sxs-lookup"><span data-stu-id="afbde-113">-Chord</span></span>

<span data-ttu-id="afbde-114">Указывает массив ключей или последовательностей удаляемых ключей.</span><span class="sxs-lookup"><span data-stu-id="afbde-114">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="afbde-115">Одну привязку можно задать в одной строке.</span><span class="sxs-lookup"><span data-stu-id="afbde-115">A single binding is specified by using a single string.</span></span> <span data-ttu-id="afbde-116">Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="afbde-116">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="afbde-117">Этот параметр принимает массив строк.</span><span class="sxs-lookup"><span data-stu-id="afbde-117">This parameter accepts an array of strings.</span></span> <span data-ttu-id="afbde-118">Каждая строка — это отдельная привязка, а не сочетание клавиш для одной привязки.</span><span class="sxs-lookup"><span data-stu-id="afbde-118">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="afbde-119">-Вимоде</span><span class="sxs-lookup"><span data-stu-id="afbde-119">-ViMode</span></span>

<span data-ttu-id="afbde-120">Укажите режим VI, к которому применяется привязка.</span><span class="sxs-lookup"><span data-stu-id="afbde-120">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="afbde-121">Возможные значения: INSERT, Command.</span><span class="sxs-lookup"><span data-stu-id="afbde-121">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="afbde-122">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="afbde-122">CommonParameters</span></span>

<span data-ttu-id="afbde-123">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="afbde-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="afbde-124">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="afbde-124">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="afbde-125">Входные данные</span><span class="sxs-lookup"><span data-stu-id="afbde-125">INPUTS</span></span>

### <span data-ttu-id="afbde-126">None</span><span class="sxs-lookup"><span data-stu-id="afbde-126">None</span></span>

<span data-ttu-id="afbde-127">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="afbde-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="afbde-128">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="afbde-128">OUTPUTS</span></span>

### <span data-ttu-id="afbde-129">None</span><span class="sxs-lookup"><span data-stu-id="afbde-129">None</span></span>

## <span data-ttu-id="afbde-130">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="afbde-130">NOTES</span></span>

## <span data-ttu-id="afbde-131">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="afbde-131">RELATED LINKS</span></span>

[<span data-ttu-id="afbde-132">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="afbde-132">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="afbde-133">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="afbde-133">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="afbde-134">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="afbde-134">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="afbde-135">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="afbde-135">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)


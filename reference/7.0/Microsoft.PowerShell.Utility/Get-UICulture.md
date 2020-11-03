---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209217"
---
# <span data-ttu-id="8fcfe-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="8fcfe-103">Get-UICulture</span></span>

## <span data-ttu-id="8fcfe-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8fcfe-104">SYNOPSIS</span></span>
<span data-ttu-id="8fcfe-105">Возвращает текущие параметры языка и региональных параметров пользовательского интерфейса в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="8fcfe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8fcfe-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="8fcfe-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8fcfe-107">DESCRIPTION</span></span>

<span data-ttu-id="8fcfe-108">`Get-UICulture`Командлет возвращает сведения о текущем языке и региональных параметрах пользовательского интерфейса для Windows.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-108">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="8fcfe-109">Язык и региональные параметры пользовательского интерфейса определяют, какие строки текста используются для элементов пользовательского интерфейса, например меню и сообщений.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="8fcfe-110">Можно также использовать `Get-Culture` командлет, который получает текущий язык и региональные параметры в системе.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-110">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="8fcfe-111">Язык и региональные параметры определяют формат отображения таких элементов, как числа, валюты и даты.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="8fcfe-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="8fcfe-112">EXAMPLES</span></span>

### <span data-ttu-id="8fcfe-113">Пример 1. получение языка и региональных параметров пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8fcfe-113">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="8fcfe-114">Эта команда получает сведения о текущем языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="8fcfe-115">Пример 2. получение языка и региональных параметров пользовательского интерфейса и форматирование результатов</span><span class="sxs-lookup"><span data-stu-id="8fcfe-115">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="8fcfe-116">Эта команда отображает значения всех свойств текущего языка и региональных параметров пользовательского интерфейса в списке.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="8fcfe-117">Пример 3. получение значения свойства Calendar</span><span class="sxs-lookup"><span data-stu-id="8fcfe-117">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="8fcfe-118">Эта команда отображает текущие значения свойства **Calendar** текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-118">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="8fcfe-119">Calendar — это только одно из свойств языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="8fcfe-120">Чтобы просмотреть все свойства, введите `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="8fcfe-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="8fcfe-121">Пример 4. получение краткого шаблона даты</span><span class="sxs-lookup"><span data-stu-id="8fcfe-121">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="8fcfe-122">Эта команда отображает шаблон краткой даты для текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="8fcfe-123">Чтобы просмотреть все вложенные свойства свойства **DateTimeFormat** языка и региональных параметров пользовательского интерфейса, введите `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="8fcfe-123">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="8fcfe-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8fcfe-124">PARAMETERS</span></span>

### <span data-ttu-id="8fcfe-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8fcfe-125">CommonParameters</span></span>

<span data-ttu-id="8fcfe-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8fcfe-127">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8fcfe-127">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8fcfe-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8fcfe-128">INPUTS</span></span>

### <span data-ttu-id="8fcfe-129">Нет</span><span class="sxs-lookup"><span data-stu-id="8fcfe-129">None</span></span>

<span data-ttu-id="8fcfe-130">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8fcfe-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8fcfe-131">OUTPUTS</span></span>

### <span data-ttu-id="8fcfe-132">System. Globalization. CultureInfo, Microsoft. PowerShell. Вистакултуреинфо</span><span class="sxs-lookup"><span data-stu-id="8fcfe-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="8fcfe-133">`Get-UICulture` Возвращает объект, представляющий текущий язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-133">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="8fcfe-134">В Windows PowerShell 3,0 он возвращает объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="8fcfe-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="8fcfe-135">В Windows PowerShell 2,0 он возвращает объект **вистакултуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="8fcfe-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="8fcfe-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8fcfe-136">NOTES</span></span>

- <span data-ttu-id="8fcfe-137">Можно также использовать `$PsCulture` `$PsUICulture` переменные и.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-137">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="8fcfe-138">`$PsCulture`Переменная хранит имя текущего языка и региональных параметров, а `$PsUICulture` переменная сохраняет имя текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-138">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="8fcfe-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8fcfe-139">RELATED LINKS</span></span>

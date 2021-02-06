---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 4bd912db3f86ffa8b495faf3e62259f207340938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605286"
---
# <span data-ttu-id="3d8ee-102">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="3d8ee-102">Get-UICulture</span></span>

## <span data-ttu-id="3d8ee-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3d8ee-103">SYNOPSIS</span></span>
<span data-ttu-id="3d8ee-104">Возвращает текущие параметры языка и региональных параметров пользовательского интерфейса в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-104">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="3d8ee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d8ee-105">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="3d8ee-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d8ee-106">DESCRIPTION</span></span>

<span data-ttu-id="3d8ee-107">`Get-UICulture`Командлет возвращает сведения о текущем языке и региональных параметрах пользовательского интерфейса для Windows.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-107">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="3d8ee-108">Язык и региональные параметры пользовательского интерфейса определяют, какие строки текста используются для элементов пользовательского интерфейса, например меню и сообщений.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-108">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="3d8ee-109">Можно также использовать `Get-Culture` командлет, который получает текущий язык и региональные параметры в системе.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-109">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="3d8ee-110">Язык и региональные параметры определяют формат отображения таких элементов, как числа, валюты и даты.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-110">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="3d8ee-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3d8ee-111">EXAMPLES</span></span>

### <span data-ttu-id="3d8ee-112">Пример 1. получение языка и региональных параметров пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3d8ee-112">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="3d8ee-113">Эта команда получает сведения о текущем языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-113">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="3d8ee-114">Пример 2. получение языка и региональных параметров пользовательского интерфейса и форматирование результатов</span><span class="sxs-lookup"><span data-stu-id="3d8ee-114">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="3d8ee-115">Эта команда отображает значения всех свойств текущего языка и региональных параметров пользовательского интерфейса в списке.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-115">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="3d8ee-116">Пример 3. получение значения свойства Calendar</span><span class="sxs-lookup"><span data-stu-id="3d8ee-116">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="3d8ee-117">Эта команда отображает текущие значения свойства **Calendar** текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-117">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="3d8ee-118">Calendar — это только одно из свойств языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-118">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="3d8ee-119">Чтобы просмотреть все свойства, введите `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="3d8ee-119">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="3d8ee-120">Пример 4. получение краткого шаблона даты</span><span class="sxs-lookup"><span data-stu-id="3d8ee-120">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="3d8ee-121">Эта команда отображает шаблон краткой даты для текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-121">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="3d8ee-122">Чтобы просмотреть все вложенные свойства свойства **DateTimeFormat** языка и региональных параметров пользовательского интерфейса, введите `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="3d8ee-122">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="3d8ee-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d8ee-123">PARAMETERS</span></span>

### <span data-ttu-id="3d8ee-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3d8ee-124">CommonParameters</span></span>

<span data-ttu-id="3d8ee-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d8ee-126">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ee-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3d8ee-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3d8ee-127">INPUTS</span></span>

### <span data-ttu-id="3d8ee-128">None</span><span class="sxs-lookup"><span data-stu-id="3d8ee-128">None</span></span>

<span data-ttu-id="3d8ee-129">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-129">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3d8ee-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3d8ee-130">OUTPUTS</span></span>

### <span data-ttu-id="3d8ee-131">System. Globalization. CultureInfo, Microsoft. PowerShell. Вистакултуреинфо</span><span class="sxs-lookup"><span data-stu-id="3d8ee-131">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="3d8ee-132">`Get-UICulture` Возвращает объект, представляющий текущий язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-132">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="3d8ee-133">В Windows PowerShell 3,0 он возвращает объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="3d8ee-133">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="3d8ee-134">В Windows PowerShell 2,0 он возвращает объект **вистакултуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="3d8ee-134">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="3d8ee-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3d8ee-135">NOTES</span></span>

- <span data-ttu-id="3d8ee-136">Можно также использовать `$PsCulture` `$PsUICulture` переменные и.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-136">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="3d8ee-137">`$PsCulture`Переменная хранит имя текущего языка и региональных параметров, а `$PsUICulture` переменная сохраняет имя текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3d8ee-137">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="3d8ee-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3d8ee-138">RELATED LINKS</span></span>


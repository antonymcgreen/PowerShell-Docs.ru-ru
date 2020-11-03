---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default;
ms.openlocfilehash: 19871bcfd1e045ab30bfef0dc88aa42a4c4aecf4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228861"
---
# <span data-ttu-id="89ac9-103">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="89ac9-103">Out-Default</span></span>

## <span data-ttu-id="89ac9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="89ac9-104">SYNOPSIS</span></span>
<span data-ttu-id="89ac9-105">Отправляет выходные данные в модуль форматирования и в выходной командлет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89ac9-105">Sends the output to the default formatter and to the default output cmdlet.</span></span>

## <span data-ttu-id="89ac9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89ac9-106">SYNTAX</span></span>

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="89ac9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89ac9-107">DESCRIPTION</span></span>

<span data-ttu-id="89ac9-108">PowerShell автоматически добавляет `Out-Default` в конец каждого конвейера.</span><span class="sxs-lookup"><span data-stu-id="89ac9-108">PowerShell automatically adds `Out-Default` to the end of every pipeline.</span></span> <span data-ttu-id="89ac9-109">`Out-Default` Определяет, как форматировать и выводить поток объекта.</span><span class="sxs-lookup"><span data-stu-id="89ac9-109">`Out-Default` decides how to format and output the object stream.</span></span> <span data-ttu-id="89ac9-110">Если поток объекта представляет собой поток строк, передает `Out-Default` их напрямую, `Out-Host` который вызывает соответствующие API, предоставляемые узлом.</span><span class="sxs-lookup"><span data-stu-id="89ac9-110">If the object stream is a stream of strings, `Out-Default` pipes these directly to `Out-Host` which calls the appropriate APIs provided by the host.</span></span> <span data-ttu-id="89ac9-111">Если поток объекта не содержит строк, `Out-Default` проверяет объект, чтобы определить, что делать.</span><span class="sxs-lookup"><span data-stu-id="89ac9-111">If the object stream does not contain strings, `Out-Default` inspects the object to determine what to do.</span></span>
<span data-ttu-id="89ac9-112">Сначала он просматривает тип объекта и определяет, есть ли зарегистрированное _представление_ для этого типа объекта.</span><span class="sxs-lookup"><span data-stu-id="89ac9-112">First it looks at the object type and determines whether there is a registered _view_ for this object type.</span></span>

<span data-ttu-id="89ac9-113">PowerShell определяет схему XML и механизм ( `Update-FormatData` командлет), где любой пользователь может регистрировать представления для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="89ac9-113">PowerShell defines XML schema and a mechanism (the `Update-FormatData` cmdlet) where anyone can register views for an object type.</span></span> <span data-ttu-id="89ac9-114">Для любого типа объекта можно указать **широкие** , **Список** , **таблицу** или **пользовательские** представления.</span><span class="sxs-lookup"><span data-stu-id="89ac9-114">You can specify **wide** , **list** , **table** , or **custom** views for any object type.</span></span> <span data-ttu-id="89ac9-115">Представления определяют отображаемые свойства и способ их отображения.</span><span class="sxs-lookup"><span data-stu-id="89ac9-115">The views specify which properties to display and how they should be displayed.</span></span> <span data-ttu-id="89ac9-116">Если представление зарегистрировано, оно определяет, какой модуль форматирования использовать.</span><span class="sxs-lookup"><span data-stu-id="89ac9-116">If a view is registered, it defines which formatter to use.</span></span> <span data-ttu-id="89ac9-117">Поэтому, если зарегистрированное представление является **табличным** представлением, объекты передаются `Out-Default` в поток `Format-Table | Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="89ac9-117">So if the registered view is a **table** view, `Out-Default` streams the objects to `Format-Table | Out-Host`.</span></span> <span data-ttu-id="89ac9-118">`Format-Table` Преобразует объекты в поток записей форматирования (на основе данных в определении представления) и `Out-Host` преобразует записи форматирования в вызовы в интерфейсе узла.</span><span class="sxs-lookup"><span data-stu-id="89ac9-118">`Format-Table` transforms the objects into a stream of Formatting records (driven by the data in the view definition) and `Out-Host` transforms the formatting records into calls on the Host interface.</span></span>

## <span data-ttu-id="89ac9-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="89ac9-119">EXAMPLES</span></span>

### <span data-ttu-id="89ac9-120">Пример 1</span><span class="sxs-lookup"><span data-stu-id="89ac9-120">Example 1</span></span>

<span data-ttu-id="89ac9-121">Хотя этот командлет не предназначен для непосредственного запуска конечным пользователем, он может иметь значение.</span><span class="sxs-lookup"><span data-stu-id="89ac9-121">While this cmdlet is not intended to be run directly by the end user, it can be.</span></span>

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## <span data-ttu-id="89ac9-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89ac9-122">PARAMETERS</span></span>

### <span data-ttu-id="89ac9-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="89ac9-123">-InputObject</span></span>

<span data-ttu-id="89ac9-124">Принимает входные данные в командлет.</span><span class="sxs-lookup"><span data-stu-id="89ac9-124">Accepts input to the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="89ac9-125">-Транскрипция</span><span class="sxs-lookup"><span data-stu-id="89ac9-125">-Transcript</span></span>

<span data-ttu-id="89ac9-126">Определяет, следует ли отправлять выходные данные в службы транскрипции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ac9-126">Determines whether the output should be sent to PowerShell's transcription services.</span></span>

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

### <span data-ttu-id="89ac9-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="89ac9-127">CommonParameters</span></span>

<span data-ttu-id="89ac9-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89ac9-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89ac9-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="89ac9-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89ac9-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="89ac9-130">INPUTS</span></span>

## <span data-ttu-id="89ac9-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="89ac9-131">OUTPUTS</span></span>

## <span data-ttu-id="89ac9-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="89ac9-132">NOTES</span></span>

## <span data-ttu-id="89ac9-133">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="89ac9-133">RELATED LINKS</span></span>

[<span data-ttu-id="89ac9-134">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="89ac9-134">Format-Custom</span></span>](../Microsoft.PowerShell.Utility/Format-Custom.md)

[<span data-ttu-id="89ac9-135">Format-List</span><span class="sxs-lookup"><span data-stu-id="89ac9-135">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="89ac9-136">Format-Table</span><span class="sxs-lookup"><span data-stu-id="89ac9-136">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="89ac9-137">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="89ac9-137">Format-Wide</span></span>](../Microsoft.PowerShell.Utility/Format-Wide.md)

[<span data-ttu-id="89ac9-138">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="89ac9-138">about_Format.ps1xml</span></span>](About/about_Format.ps1xml.md)

[<span data-ttu-id="89ac9-139">Как работает форматирование и вывод в PowerShell</span><span class="sxs-lookup"><span data-stu-id="89ac9-139">How PowerShell Formatting and Outputting REALLY works</span></span>](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)

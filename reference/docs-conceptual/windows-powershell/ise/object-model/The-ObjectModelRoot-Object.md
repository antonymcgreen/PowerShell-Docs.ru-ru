---
ms.date: 08/25/2017
title: Объект ObjectModelRoot
description: Объект $psISE, который является основным корневым объектом в PowerShell ISE, представляет собой экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot. В этом разделе описаны свойства объекта ObjectModelRoot.
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660938"
---
# <a name="the-objectmodelroot-object"></a>Объект ObjectModelRoot

Объект `$psISE`, который является основным корневым объектом в интегрированной среде сценариев Windows PowerShell&reg; (ISE), представляет собой экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot. В этом разделе описаны свойства объекта **ObjectModelRoot**.

## <a name="properties"></a>Свойства

### <a name="currentfile"></a>CurrentFile

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает файл, связанный с этим объектом узла, находящимся в данный момент в фокусе.

### <a name="currentpowershelltab"></a>CurrentPowerShellTab

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает вкладку PowerShell, находящуюся в фокусе.

### <a name="currentvisiblehorizontaltool"></a>CurrentVisibleHorizontalTool

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в горизонтальной области инструментов в нижней части редактора.

### <a name="currentvisibleverticaltool"></a>CurrentVisibleVerticalTool

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в вертикальной области инструментов в правой части редактора.

### <a name="options"></a>Варианты

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает различные параметры, изменяющие настройки в интегрированной среде сценариев Windows PowerShell.

### <a name="powershelltabs"></a>PowerShellTabs

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает коллекцию вкладок PowerShell, открытых в интегрированной среде сценариев Windows PowerShell. По умолчанию этот объект содержит одну вкладку PowerShell. Тем не менее можно добавить в этот объект больше вкладок PowerShell с помощью сценариев или меню в интегрированной среде сценариев Windows PowerShell.

## <a name="see-also"></a>См. также:

- [Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)

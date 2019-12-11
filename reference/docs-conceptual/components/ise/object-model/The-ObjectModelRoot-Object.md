---
ms.date: 08/25/2017
keywords: powershell,командлет
title: Объект ObjectModelRoot
ms.openlocfilehash: 2670321ebac1eac4ecc8457afb796f9f260da471
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "62086788"
---
# <a name="the-objectmodelroot-object"></a>Объект ObjectModelRoot

Объект **$PsISE**, который является основным корневым объектом в интегрированной среде скриптов Windows PowerShell® (ISE), — это экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot.
В этом разделе описаны свойства объекта **ObjectModelRoot**.

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

### <a name="options"></a>Параметры

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает различные параметры, изменяющие настройки в интегрированной среде сценариев Windows PowerShell.

### <a name="powershelltabs"></a>PowerShellTabs

> Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Свойство только для чтения, которое получает коллекцию вкладок PowerShell, открытых в интегрированной среде сценариев Windows PowerShell. По умолчанию этот объект содержит одну вкладку PowerShell. Тем не менее можно добавить в этот объект больше вкладок PowerShell с помощью сценариев или меню в интегрированной среде сценариев Windows PowerShell.

## <a name="see-also"></a>См. также

- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
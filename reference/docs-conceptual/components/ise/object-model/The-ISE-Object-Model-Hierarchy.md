---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Иерархия объектной модели интегрированной среды сценариев
ms.openlocfilehash: 1ec5810fc5e7b765c2a08af83bce0415dd61a54b
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737038"
---
# <a name="the-ise-object-model-hierarchy"></a>Иерархия объектной модели интегрированной среды сценариев

В этом разделе демонстрируется иерархия объектов, которые входят в состав интегрированной среды сценариев Windows PowerShell (ISE). Интегрированная среда сценариев Windows PowerShell входит в состав Windows PowerShell 3.0, 4.0 и 5.1. Щелкните объект, чтобы перейти к справочной документации для класса, определяющего объект.

## <a name="psise-object"></a>Объект $psISE

Объект `$psISE` — это [корневой объект](The-ObjectModelRoot-Object.md) иерархии объектов интегрированной среды сценариев Windows PowerShell. Располагаясь на верхнем уровне, он предоставляет доступ к следующим объектам для создания сценариев:

## <a name="psisecurrentfilethe-isefile-objectmd"></a>[$psISE.CurrentFile](The-ISEFile-Object.md)

Объект `$psISE.CurrentFile` является экземпляром класса [ISEFile](The-ISEFile-Object.md).

## <a name="psisecurrentpowershelltabthe-powershelltab-objectmd"></a>[$psISE.CurrentPowerShellTab](The-PowerShellTab-Object.md)

Объект `$psISE.CurrentPowerShellTab` является экземпляром класса [PowerShellTab](The-PowerShellTab-Object.md).

## <a name="psisecurrentvisiblehorizontaltool"></a>$psISE.CurrentVisibleHorizontalTool

Объект `$psISE.CurrentVisibleHorizontalTool` является экземпляром класса [ISEAddOnTool](The-ISEAddOnTool-Object.md). Он представляет установленную надстройку, закрепленную в верхней части окна интегрированной среды сценариев Windows PowerShell.

## <a name="psisecurrentvisibleverticaltool"></a>$psISE.CurrentVisibleVerticalTool

Объект `$psISE.CurrentVisibleHorizontalTool` является экземпляром класса [ISEAddOnTool](The-ISEAddOnTool-Object.md). Он представляет установленную надстройку, закрепленную в правой части окна интегрированной среды сценариев Windows PowerShell.

## <a name="psiseoptionsthe-iseoptions-objectmd"></a>[$psISE.Options](The-ISEOptions-Object.md)

Объект `$psISE.Options` является экземпляром класса [ISEOptions](The-ISEOptions-Object.md). Объект ISEOptions представляет различные параметры для интегрированной среды сценариев Windows PowerShell. Он является экземпляром класса Microsoft.PowerShell.Host.ISE.ISEOptions.

## <a name="psisepowershelltabsthe-powershelltabcollection-objectmd"></a>[$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md)

Объект `$psISE.PowerShellTabs` является экземпляром класса [PowerShellTabCollection](The-PowerShellTabCollection-Object.md). Это коллекция всех открытых вкладок PowerShell, представляющих доступные среды выполнения Windows PowerShell на локальном компьютере или на подключенных удаленных компьютерах. Каждый элемент в коллекции является экземпляром класса [PowerShellTab](The-PowerShellTab-Object.md).

## <a name="see-also"></a>См. также:

- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)

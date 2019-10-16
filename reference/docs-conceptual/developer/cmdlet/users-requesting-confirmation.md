---
title: Пользователи, запрашивающие подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: ed9ff9fc1668a89e1ac0ceac8f0800a15b349226
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369253"
---
# <a name="users-requesting-confirmation"></a>Запрос на подтверждение от пользователей

При указании значения `true` для параметра `SupportsShouldProcess` в объявлении атрибута командлета пользователи могут указать параметр `Confirm` в командной строке.

В среде по умолчанию пользователи могут указать параметр `Confirm` или `"-Confirm:$true`, чтобы подтверждение запрашивалось при вызове метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Это обходит запросы подтверждения [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , даже для операций с высоким уровнем влияния.

Если `Confirm` не указан, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение, если переменная предпочтений `$ConfirmPreference` больше или равна значению параметра `ConfirmImpact` командлета или поставщика. Значение по умолчанию `$ConfirmPreference` — High. Таким образом, в среде по умолчанию только командлеты и поставщики, которые задают подтверждение запроса на действие с высокой степенью влияния.

Если `Confirm` имеет значение false или если задано `"-Confirm:$false`, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение от пользователя, а переменная оболочки `$ConfirmPreference` игнорируется.

## <a name="remarks"></a>Замечания

- Для командлетов и поставщиков, которые задают `SupportsShouldProcess`, но не `ConfirmImpact`, эти действия обрабатываются как действия "среднего влияния" и не запрашиваются по умолчанию. Их уровень влияния меньше значения по умолчанию для привилегированной переменной `$ConfirmPreference`.

- Если пользователь указывает параметр `Verbose`, он будет уведомлен об этой операции, даже если у них нет запроса на подтверждение.

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

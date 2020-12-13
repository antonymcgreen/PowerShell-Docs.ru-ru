---
ms.date: 09/13/2016
ms.topic: reference
title: Запрос на подтверждение от пользователей
description: Запрос на подтверждение от пользователей
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646305"
---
# <a name="users-requesting-confirmation"></a>Запрос на подтверждение от пользователей

При указании значения `true` для `SupportsShouldProcess` параметра объявления атрибута командлета пользователи могут указать `Confirm` параметр в командной строке.

В среде по умолчанию пользователи могут указать `Confirm` параметр или `"-Confirm:$true` , чтобы подтверждение запрашивалось при вызове метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Это обходит запросы подтверждения [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , даже для операций с высоким уровнем влияния.

Если `Confirm` параметр не указан, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение, если `$ConfirmPreference` привилегированная переменная равна или превышает `ConfirmImpact` значение параметра командлета или поставщика. Значение по умолчанию `$ConfirmPreference` — High. Таким образом, в среде по умолчанию только командлеты и поставщики, которые задают подтверждение запроса на действие с высокой степенью влияния.

Если `Confirm` параметр имеет значение false или `"-Confirm:$false` указан, то вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение от пользователя, а `$ConfirmPreference` переменная оболочки игнорируется.

## <a name="remarks"></a>Комментарии

- Для командлетов и поставщиков, которые указывают `SupportsShouldProcess` , но не могут `ConfirmImpact` обрабатывать эти действия как действия "среднего влияния" и не запрашиваются по умолчанию. Их уровень влияния меньше значения по умолчанию для `$ConfirmPreference` привилегированной переменной.

- Если пользователь указывает `Verbose` параметр, он будет уведомлен об операции, даже если они не запрашивают подтверждение.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

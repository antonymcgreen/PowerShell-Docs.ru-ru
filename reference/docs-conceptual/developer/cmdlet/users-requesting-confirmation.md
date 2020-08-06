---
title: Пользователи, запрашивающие подтверждение | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6f0effb35a110f33248a582fab874e3ab95c7df4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786345"
---
# <a name="users-requesting-confirmation"></a>Запрос на подтверждение от пользователей

При указании значения `true` для `SupportsShouldProcess` параметра объявления атрибута командлета пользователи могут указать `Confirm` параметр в командной строке.

В среде по умолчанию пользователи могут указать `Confirm` параметр или `"-Confirm:$true` , чтобы подтверждение запрашивалось при вызове метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Это обходит запросы подтверждения [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , даже для операций с высоким уровнем влияния.

Если `Confirm` параметр не указан, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение, если `$ConfirmPreference` привилегированная переменная равна или превышает `ConfirmImpact` значение параметра командлета или поставщика. Значение по умолчанию `$ConfirmPreference` — High. Таким образом, в среде по умолчанию только командлеты и поставщики, которые задают подтверждение запроса на действие с высокой степенью влияния.

Если `Confirm` параметр имеет значение false или `"-Confirm:$false` указан, то вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение от пользователя, а `$ConfirmPreference` переменная оболочки игнорируется.

## <a name="remarks"></a>Примечания

- Для командлетов и поставщиков, которые указывают `SupportsShouldProcess` , но не могут `ConfirmImpact` обрабатывать эти действия как действия "среднего влияния" и не запрашиваются по умолчанию. Их уровень влияния меньше значения по умолчанию для `$ConfirmPreference` привилегированной переменной.

- Если пользователь указывает `Verbose` параметр, он будет уведомлен об операции, даже если они не запрашивают подтверждение.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

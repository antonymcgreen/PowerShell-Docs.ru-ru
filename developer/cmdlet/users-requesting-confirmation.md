---
title: Пользователи с запросом на подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: e4abbb14b31406b845d9b6af6b6372338fb0d926
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856240"
---
# <a name="users-requesting-confirmation"></a>Запрос на подтверждение от пользователей

При указании параметра `true` для `SupportsShouldProcess` параметра в объявлении атрибута командлет, пользователи могут указать `Confirm` параметр в командной строке.

В среде по умолчанию, пользователи могут указать `Confirm` параметр или `"-Confirm:$true` таким образом, запрашивается подтверждение при [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывается метод. Это позволяет обойти [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запросов подтверждения, даже для операций с высоким уровнем влияния.

Если `Confirm` не указан, [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов запрашивает подтверждение, если `$ConfirmPreference` привилегированной переменной равно или больше, чем `ConfirmImpact` параметр командлет или поставщика. Значение по умолчанию `$ConfirmPreference` — высокий. Таким образом в среде по умолчанию, только командлеты и поставщики, укажите действие качественные запросит подтверждение.

Если `Confirm` имеет значение false или если `"-Confirm:$false` указано, [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов запрашивает подтверждение от пользователя и `$ConfirmPreference` переменной оболочки учитывается.

## <a name="remarks"></a>Замечания

- Для командлеты и поставщики, которые указывают `SupportsShouldProcess`, но не `ConfirmImpact`, эти действия будут обрабатываться как действия «со средним уровнем влияния», и они не будут запрашивать по умолчанию. Их уровень влияния меньше, чем значение по умолчанию `$ConfirmPreference` привилегированной переменной.

- Если пользователь указывает `Verbose` параметра, они будут уведомлены о операции, даже если они не запрашивается подтверждение.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

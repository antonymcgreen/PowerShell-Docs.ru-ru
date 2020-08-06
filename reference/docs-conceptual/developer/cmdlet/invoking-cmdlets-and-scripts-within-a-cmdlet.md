---
title: Вызов командлетов и скриптов в командлете | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786583"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>Вызов командлетов и сценариев внутри командлета

Командлет может вызывать другие командлеты и скрипты в методе обработки входных данных командлета. Это позволяет добавлять в командлет функциональные возможности существующих командлетов и скриптов без необходимости переписывать код.

## <a name="the-invoke-method"></a>Метод Invoke

Все командлеты могут вызывать существующий командлет, вызывая метод [System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) из метода обработки входных данных, например [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), который переопределяется командлетом. Однако можно вызывать только те командлеты, которые являются производными непосредственно от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) . Нельзя вызвать командлет, производный от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .

Метод [System. Management. Automation. командлет. Invoke *](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) имеет следующие варианты.

[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этот вариант вызывает объект командлета и возвращает коллекцию объектов типа "T".

[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает объект командлета и возвращает строго типизированный емумератор. Этот вариант позволяет пользователю использовать объекты в коллекции для выполнения пользовательских операций.

## <a name="examples"></a>Примеры

|Пример|Описание|
|-------------|-----------------|
|[Вызов командлетов в командлете](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|В этом примере показано, как вызвать командлет из другого командлета.|
|[Вызов скриптов в командлете](./how-to-invoke-scripts-within-a-cmdlet.md)|В этом примере показано, как вызвать скрипт, передаваемый в командлет из другого командлета.|

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

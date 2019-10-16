---
title: Вызов командлетов и скриптов в командлете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364293"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>Вызов командлетов и сценариев внутри командлета

Командлет может вызывать другие командлеты и скрипты в методе обработки входных данных командлета. Это позволяет добавлять в командлет функциональные возможности существующих командлетов и скриптов без необходимости переписывать код.

## <a name="the-invoke-method"></a>Метод Invoke

Все командлеты могут вызывать существующий командлет, вызывая метод [System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) из метода обработки входных данных, например [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), который переопределяется Командлет. Однако можно вызывать только те командлеты, которые являются производными непосредственно от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) . Нельзя вызвать командлет, производный от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .

Метод [System. Management. Automation. командлет. Invoke *](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) имеет следующие варианты.

[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этот вариант вызывает объект командлета и возвращает коллекцию объектов типа "T".

[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает объект командлета и возвращает строго типизированный емумератор. Этот вариант позволяет пользователю использовать объекты в коллекции для выполнения пользовательских операций.

## <a name="examples"></a>Примеры

|Пример|Описание|
|-------------|-----------------|
|[Вызов командлетов в командлете](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|В этом примере показано, как вызвать командлет из другого командлета.|
|[Вызов скриптов в командлете](./how-to-invoke-scripts-within-a-cmdlet.md)|В этом примере показано, как вызвать скрипт, передаваемый в командлет из другого командлета.|

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

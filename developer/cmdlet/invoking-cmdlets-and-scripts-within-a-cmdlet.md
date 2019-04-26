---
title: Вызов командлеты и сценарии в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067677"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>Вызов командлетов и сценариев внутри командлета

Командлет можно вызывать другие командлеты и сценарии из в метод командлета обработки входных данных. Это позволяет добавить функциональные возможности существующих командлетов и скриптов для командлета не требуется переписывать код.

## <a name="the-invoke-method"></a>Вызов метода

Все командлеты могут вызывать существующий командлет с помощью [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метода в метод, например обработки входных данных [ System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), то есть переопределено с помощью командлета. Тем не менее, можно вызвать только нужные командлеты, которые наследуются от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса. Не удается вызвать командлет, который является производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.

[System.Management.Automation.Cmdlet.Invoke*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метод имеет следующие варианты.

[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает коллекцию объектов типа «T».

[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает строго типизированный emumerator. Этот вариант позволяет использовать объекты в коллекции для выполнения пользовательских операций.

## <a name="examples"></a>Примеры

|Пример|Описание|
|-------------|-----------------|
|[Вызов командлеты в командлет](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|В этом примере показано, как для вызова командлета из в другой командлет.|
|[Вызов скриптов в командлет](./how-to-invoke-scripts-within-a-cmdlet.md)|В этом примере показано, как вызвать скрипт, который передается в командлет в другой командлет.|

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

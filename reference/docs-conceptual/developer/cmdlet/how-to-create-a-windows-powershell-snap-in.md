---
title: Создание оснастки Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.assetid: 71bd9b2c-5f2e-4aa8-b5fe-08c956540d37
caps.latest.revision: 10
ms.openlocfilehash: 43199544dc02ccae4b61053c30d6ed36576adfcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364433"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Как создать оснастку Windows PowerShell

Оснастка Windows PowerShell предоставляет механизм для регистрации наборов командлетов и другого поставщика Windows PowerShell с оболочкой, тем самым расширяя функциональные возможности оболочки. Оснастка Windows PowerShell может зарегистрировать все командлеты и поставщики в одной сборке или зарегистрировать конкретный список командлетов и поставщиков.

Сборки оснастки должны быть установлены в защищенном каталоге так же, как и в других операционных системах. В противном случае злонамеренные пользователи могут заменить сборку на небезопасный код.

## <a name="windows-powershell-snap-in-classes"></a>Классы оснастки Windows PowerShell

Все классы оснастки Windows PowerShell являются производными от классов [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) или [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .

## <a name="examples"></a>Примеры

Создание [оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md). в этом примере показано, как создать оснастку, которая будет использоваться для регистрации всех командлетов и поставщиков в сборке.

[Написание пользовательской оснастки Windows PowerShell. в](./writing-a-custom-windows-powershell-snap-in.md)этом примере показано, как создать пользовательскую оснастку, которая будет использоваться для регистрации определенного набора командлетов и поставщиков, которые могут существовать или отсутствовать в одной сборке.

## <a name="see-also"></a>См. также:

[System. Management. Automation. PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)

[System. Management. Automation. Кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[Регистрация командлетов](./registering-cmdlets.md)

[Пакет SDK оболочки Windows PowerShell](../windows-powershell-reference.md)

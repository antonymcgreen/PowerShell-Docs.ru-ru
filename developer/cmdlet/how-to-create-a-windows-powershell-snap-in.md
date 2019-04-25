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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068000"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Как создать оснастку Windows PowerShell

Оснастки Windows PowerShell предоставляет механизм для регистрации наборы командлетов и другого поставщика Windows PowerShell с оболочкой, расширяя таким образом функциональных возможностей оболочки. Оснастки Windows PowerShell можно зарегистрировать все командлеты и поставщики в одной сборке, или для регистрации в определенный список командлетов и поставщиков.

Оснастка сборки должны быть установлены в защищенный каталог, так же, как они будут иметь с другими операционными системами. В противном случае пользователи-злоумышленники можно заменить сборку небезопасного кода.

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell Snap-in классы

Все классы оснастки Windows PowerShell являются производными от [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) или [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) классы.

## <a name="examples"></a>Примеры

[Написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md): В этом примере показано, как создать это оснастка, который позволяет зарегистрировать все командлеты и поставщики в сборке.

[Написание пользовательских Windows PowerShell – – оснастка](./writing-a-custom-windows-powershell-snap-in.md): В этом примере показано, как создать пользовательский оснастки, используемый для регистрации определенного набора командлетов и поставщиков, которые могут или не существовать в одной сборке.

## <a name="see-also"></a>См. также

[System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)

[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[Регистрация командлетов](./registering-cmdlets.md)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

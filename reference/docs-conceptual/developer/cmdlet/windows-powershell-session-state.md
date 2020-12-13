---
ms.date: 09/13/2016
ms.topic: reference
title: Состояние сеанса Windows PowerShell
description: Состояние сеанса Windows PowerShell
ms.openlocfilehash: 51de92f1f392f708cf49c7ccb4a6808fd628076c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668139"
---
# <a name="windows-powershell-session-state"></a>Состояние сеанса Windows PowerShell

Состояние сеанса относится к текущей конфигурации сеанса или модуля Windows PowerShell. Сеанс Windows PowerShell — это Рабочая среда, используемая пользователем командной строки в интерактивном режиме или программно ведущим приложением. Состояние сеанса для сеанса называется глобальным состоянием сеанса.

С точки зрения разработчика, сеанс Windows PowerShell ссылается на время между открытием пространства выполнения Windows PowerShell и его закрытием. В другом случае сеанс является временем существования экземпляра обработчика Windows PowerShell, который вызывается, пока существует пространство выполнения.

## <a name="module-session-state"></a>Состояние сеанса модуля

Состояния сеанса модуля создаются всякий раз, когда модуль или один из его вложенных модулей импортируется в сеанс. Когда модуль экспортирует элемент, например командлет, функцию или скрипт, в глобальное состояние сеанса в сеансе добавляется ссылка на этот элемент. Однако при выполнении элемента он выполняется в состоянии сеанса модуля.

## <a name="session-state-data"></a>Session-State данных

Данные состояния сеанса могут быть открытыми или закрытыми. Общедоступные данные доступны для вызовов извне состояния сеанса, в то время как закрытые данные доступны только для вызовов в состоянии сеанса. Например, модуль может иметь закрытую функцию, которая может быть вызвана только модулем или внутренним экспортируемым открытым элементом. Это похоже на закрытый и открытый члены типа .NET Framework.

Данные состояния сеанса хранятся в текущем экземпляре подсистемы выполнения в контексте текущего сеанса Windows PowerShell. Данные состояния сеанса состоят из следующих элементов:

- Сведения о пути

- Сведения о диске

- Сведения о поставщике Windows PowerShell

- Сведения о импортированных модулях и ссылках на элементы модуля (например, командлеты, функции и скрипты), которые экспортируются модулем. Эти сведения и эти ссылки предназначены только для глобального состояния сеанса.

- Сведения о переменной состояния сеанса

## <a name="accessing-session-state-data-within-cmdlets"></a>Доступ к данным Session-State в командлетах

Командлеты могут обращаться к данным состояния сеанса непрямо через свойство [System. Management. Automation. PSCmdlet. sessionState *](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) класса командлета или напрямую через класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) . Класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) предоставляет свойства, которые можно использовать для анализа различных типов данных состояния сеанса.

## <a name="see-also"></a>См. также:

[System. Management. Automation. PSCmdlet. sessionState](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[System. Management. Automation. sessionState? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.SessionState)

[Командлеты Windows PowerShell](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK Windows PowerShell](../windows-powershell-reference.md)

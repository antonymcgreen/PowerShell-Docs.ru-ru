---
title: Состояние сеанса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.assetid: 74912940-2b10-4a76-b174-6d035d71c02b
caps.latest.revision: 8
ms.openlocfilehash: fa207130bbb120750780bb0aa9b32150a32daaa2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369103"
---
# <a name="windows-powershell-session-state"></a>Состояние сеанса Windows PowerShell

Состояние сеанса относится к текущей конфигурации сеанса или модуля Windows PowerShell. Сеанс Windows PowerShell — это Рабочая среда, используемая пользователем командной строки в интерактивном режиме или программно ведущим приложением. Состояние сеанса для сеанса называется глобальным состоянием сеанса.

С точки зрения разработчика, сеанс Windows PowerShell ссылается на время между открытием пространства выполнения Windows PowerShell и его закрытием. В другом случае сеанс является временем существования экземпляра обработчика Windows PowerShell, который вызывается, пока существует пространство выполнения.

## <a name="module-session-state"></a>Состояние сеанса модуля

Состояния сеанса модуля создаются всякий раз, когда модуль или один из его вложенных модулей импортируется в сеанс. Когда модуль экспортирует элемент, например командлет, функцию или скрипт, в глобальное состояние сеанса в сеансе добавляется ссылка на этот элемент. Однако при выполнении элемента он выполняется в состоянии сеанса модуля.

## <a name="session-state-data"></a>Данные состояния сеанса

Данные состояния сеанса могут быть открытыми или закрытыми. Общедоступные данные доступны для вызовов извне состояния сеанса, в то время как закрытые данные доступны только для вызовов в состоянии сеанса. Например, модуль может иметь закрытую функцию, которая может быть вызвана только модулем или внутренним экспортируемым открытым элементом. Это похоже на закрытый и открытый члены типа .NET Framework.

Данные состояния сеанса хранятся в текущем экземпляре подсистемы выполнения в контексте текущего сеанса Windows PowerShell. Данные состояния сеанса состоят из следующих элементов:

- Сведения о пути

- Сведения о диске

- Сведения о поставщике Windows PowerShell

- Сведения о импортированных модулях и ссылках на элементы модуля (например, командлеты, функции и скрипты), которые экспортируются модулем. Эти сведения и эти ссылки предназначены только для глобального состояния сеанса.

- Сведения о переменной состояния сеанса

## <a name="accessing-session-state-data-within-cmdlets"></a>Доступ к данным состояния сеанса в командлетах

Командлеты могут обращаться к данным состояния сеанса непрямо через свойство [System. Management. Automation. PSCmdlet. sessionState *](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) класса командлета или напрямую через класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) . Класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) предоставляет свойства, которые можно использовать для анализа различных типов данных состояния сеанса.

## <a name="see-also"></a>См. также:

[System. Management. Automation. PSCmdlet. sessionState](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[System. Management. Automation. sessionState? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.SessionState)

[Командлеты Windows PowerShell](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK оболочки Windows PowerShell](../windows-powershell-reference.md)

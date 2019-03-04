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
ms.openlocfilehash: 5d4effb508c9f2544832dad557671520cb0a7ac7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862990"
---
# <a name="windows-powershell-session-state"></a>Состояние сеанса Windows PowerShell

Состояние сеанса относится к текущей конфигурации сеанса Windows PowerShell или модуля. Сеанс Windows PowerShell — операционную среду с интерактивного использования пользователем командной строки, или программным образом ведущим приложением. Состояние сеанса для сеанса называется глобальное состояние сеанса.

С точки зрения разработчика сеанс Windows PowerShell — это время между при открытии пространства выполнения Windows PowerShell в ведущее приложение и при его закрытии пространства выполнения. Сеанс рассмотрели другим способом, и составляет время жизни экземпляра ядра Windows PowerShell, который вызывается, пока существует пространство выполнения.

## <a name="module-session-state"></a>Состояние сеанса модуля

Модуль состояния сеанса создаются каждый раз, когда модуль или одного из его вложенные модули не импортированы в сеанс. Когда модуль экспортирует элемент, такой как командлета, функции или сценарии, ссылку на этот элемент добавляется в глобальное состояние сеанса сеанса. Тем не менее при запуске элемента, она выполняется в состояние сеанса модуля.

## <a name="session-state-data"></a>Данные о состоянии сеанса

Данные о состоянии сеанса может быть открытым или закрытым. Общедоступные данные, позволяющих вызовы из за пределами состояние сеанса, хотя личных данных доступен только для вызовов из состояния сеанса. Например, модуль может иметь закрытой функции, который может быть вызван только модулем или только для внутреннего использования, общим элементам, которые были экспортированы. Это похоже на частные и общедоступные члены типа платформы .NET Framework.

Данные о состоянии сеанса хранится в текущем экземпляре ядра выполнения в контексте текущего сеанса Windows PowerShell. Данные о состоянии сеанса состоит из следующих элементов:

- Сведения о пути

- Сведения о диске

- Сведения о поставщике Windows PowerShell

- Сведения об импортированных модулей и ссылки на элементы модуля (например, командлеты, функции и сценарии), которые экспортируются модулем. Эти сведения и эти ссылки предназначены для глобальное состояние сеанса только.

- Сведения о переменных состояния сеанса

## <a name="accessing-session-state-data-within-cmdlets"></a>Доступ к данным состояния сеанса в командлеты

Командлеты можно получить доступ к данным состояния сеанса либо косвенно через [System.Management.Automation.Pscmdlet.Sessionstate*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) свойство класса командлета или напрямую через [ System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) класса. [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) класс предоставляет свойства, которые можно использовать для изучения различных типов данных состояния сеанса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Pscmdlet.Sessionstate](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[System.Management.Automation.Sessionstate? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.SessionState)

[Командлеты Windows PowerShell](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Оболочка Windows PowerShell SDK](../windows-powershell-reference.md)

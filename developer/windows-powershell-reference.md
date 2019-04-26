---
title: Справочник по Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows PowerShell SDK
ms.assetid: cbba4879-bcac-484a-9906-4bbe2cd1eb33
caps.latest.revision: 11
ms.openlocfilehash: 86595ebaac32318a4e3b9a3c4b295c73fb2e1c75
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080504"
---
# <a name="windows-powershell-reference"></a>Справочник по Windows PowerShell

Windows PowerShell является средой Microsoft связанных с .NET Framework, созданной для автоматизации администрирования. Windows PowerShell предоставляет новый подход к построения команд, создание решения и создания графического пользовательского интерфейса-средства управления.

Windows PowerShell позволяет системным администраторам автоматизировать администрирование системных ресурсов при выполнении команды напрямую или через сценарии.

## <a name="developer-audience"></a>Аудитория разработчиков

Windows PowerShell Software Development Kit (SDK) записывается для команды разработчиков, которым нужны справочные сведения об API, предоставляемые Windows PowerShell. Команда разработчиков использовать Windows PowerShell для создания команды и поставщики, которые расширяют задачи, которые можно выполнить с Windows PowerShell.

## <a name="windows-powershell-resources"></a>Ресурсы Windows PowerShell

Помимо пакета SDK для Windows PowerShell следующие ресурсы содержат дополнительные сведения.

[Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell) введение в Windows PowerShell: язык, командлеты, поставщики и использование объектов.

[Написание модуля Windows PowerShell](./module/writing-a-windows-powershell-module.md) содержатся сведения и примеры для администраторов, скрипт разработчикам и разработчикам командлетов, которым необходимо упаковать и распространять их решения Windows PowerShell, с помощью модулей Windows PowerShell.

[Запись командлета Windows PowerShell](./cmdlet/writing-a-windows-powershell-cmdlet.md) предоставляет сведения и примеры кода для руководителей программ, которые при разработке командлетов и разработчиками, реализующими код командлета.

[Блог группы Windows PowerShell](https://blogs.msdn.microsoft.com/PowerShell/) самый лучший ресурс для обучения и сотрудничества с другими пользователями Windows PowerShell. Читать блог группы Windows PowerShell, а затем присоедините форум пользователей Windows PowerShell (microsoft.public.windows.powershell). Используйте Windows Live Search, чтобы найти другие блоги по Windows PowerShell и ресурсы. Затем при разработке свой опыт, свободно Предлагайте свои идеи.

[Браузер модуля PowerShell](/powershell/module/) предоставляет последние версии разделов справки командной строки.

## <a name="class-libraries"></a>Библиотеки классов

[System.Management.Automation](/dotnet/api/System.Management.Automation) это пространство имен является корневое пространство имен для Windows PowerShell. Он содержит классы, перечисления и интерфейсы, необходимые для реализации пользовательских командлетов. В частности [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класс является базовым классом, из какой все командлет должен быть производным классам. Дополнительные сведения о командлетах см. в разделе.

[System.Management.Automation.Provider](/dotnet/api/System.Management.Automation.Provider) это пространство имен содержит классы, перечисления и интерфейсы, необходимые для реализации поставщика Windows PowerShell. В частности [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) класс является базовым классом, из какой всех Windows PowerShell должен быть производным классы поставщика.

[Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) это пространство имен содержит классы для командлеты и поставщики, реализованные в Windows PowerShell. Аналогичным образом, рекомендуется создать *YourName*. Пространство имен команд для командлетов, которые реализовать.

[System.Management.Automation.Host](/dotnet/api/System.Management.Automation.Host) это пространство имен содержит классы, перечисления и интерфейсы, командлет будет использовать для определения взаимодействия между пользователем и Windows PowerShell.

[System.Management.Automation.Internal](/dotnet/api/System.Management.Automation.Internal) это пространство имен содержит базовые классы, используемые другими классами пространства имен. Например [System.Management.Automation.Internal.Cmdletmetadataattribute](/dotnet/api/System.Management.Automation.Internal.CmdletMetadataAttribute) класс является базовым классом для [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) класса.

[System.Management.Automation.Runspaces](/dotnet/api/System.Management.Automation.Runspaces) это пространство имен содержит классы, перечисления и интерфейсы, используемые для создания пространства выполнения Windows PowerShell. В данном контексте пространства выполнения Windows PowerShell является контекст, в котором один или несколько конвейеров Windows PowerShell вызвать командлеты. То есть командлеты работают в контексте пространства выполнения Windows PowerShell. Дополнительные сведения о aboutWindows пространства выполнения PowerShell, см. в разделе [пространства выполнения Windows PowerShell](http://msdn.microsoft.com/en-us/a1582cfe-f06d-4aff-adc6-71f49a860ce9).

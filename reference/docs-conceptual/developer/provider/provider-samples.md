---
title: Примеры поставщиков | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4933dad-fec9-4337-a1a9-9dc16ee87cc3
caps.latest.revision: 9
ms.openlocfilehash: 1e7aeb5bcb6bd5a2845648c3327e2245e6c428ba
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366303"
---
# <a name="provider-samples"></a>Примеры поставщиков

В этом разделе приводятся примеры поставщиков, обращающихся к базе данных Microsoft Access. Эти примеры включают классы поставщиков, производные от всех базовых классов поставщиков.

## <a name="in-this-section"></a>Содержание

Этот раздел содержит следующие темы:

[Пример AccessDBProviderSample01](./accessdbprovidersample01.md) В этом примере показано, как объявить класс поставщика, производный непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) . Он приводится здесь только для полноты картины.

[AccessDBProviderSample02](./accessdbprovidersample02.md) В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки вызовов командлетов `New-PSDrive` и `Remove-PSDrive`. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .

[AccessDBProviderSample03](./accessdbprovidersample03.md) В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов командлетов `Get-Item` и `Set-Item`. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

[AccessDBProviderSample04](./accessdbprovidersample04.md) В этом примере показано, как перезаписать методы контейнера для поддержки вызовов командлетов `Copy-Item`, `Get-ChildItem`, `New-Item`и `Remove-Item`. Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

[AccessDBProviderSample05](./accessdbprovidersample05.md) В этом примере показано, как перезаписать методы контейнера для поддержки вызовов командлетов `Move-Item` и `Join-Path`. Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

[AccessDBProviderSample06](./accessdbprovidersample06.md) В этом примере показано, как перезаписывать методы содержимого для поддержки вызовов `Clear-Content`, `Get-Content`и командлетов `Set-Content`. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и реализует интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

## <a name="see-also"></a>См. также:

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
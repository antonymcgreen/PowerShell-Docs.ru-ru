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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853130"
---
# <a name="provider-samples"></a>Примеры поставщиков

Этот раздел содержит примеры поставщиков, которые обращаются к базе данных Microsoft Access. Эти примеры содержат классы поставщиков, которые являются производными от всех классов базового поставщика.

## <a name="in-this-section"></a>Содержание

Этот раздел содержит следующие темы:

[Пример AccessDBProviderSample01](./accessdbprovidersample01.md) в этом примере показано, как объявить класс поставщика, который является производным непосредственно от [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) класса. Он приводится здесь только для полноты картины.

[AccessDBProviderSample02](./accessdbprovidersample02.md) в этом примере показано, как перезаписать [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [ System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) методы для поддержки вызовов в `New-PSDrive` и `Remove-PSDrive` командлетов. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса.

[AccessDBProviderSample03](./accessdbprovidersample03.md) в этом примере показано, как перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [ System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) методы для поддержки вызовов в `Get-Item` и `Set-Item` командлетов. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.

[AccessDBProviderSample04](./accessdbprovidersample04.md) в этом примере показано, как перезаписать методы контейнера для поддержки вызовов в `Copy-Item`, `Get-ChildItem`, `New-Item`, и `Remove-Item` командлетов. Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.

[AccessDBProviderSample05](./accessdbprovidersample05.md) в этом примере показано, как перезаписать методы контейнера для поддержки вызовов в `Move-Item` и `Join-Path` командлетов. Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.

[AccessDBProviderSample06](./accessdbprovidersample06.md) в этом примере показано, как перезаписать методы содержимого для поддержки вызовов в `Clear-Content`, `Get-Content`, и `Set-Content` командлетов. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс, который реализует [ System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.

## <a name="see-also"></a>См. также

[Разработка поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
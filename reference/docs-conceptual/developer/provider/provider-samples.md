---
title: Примеры поставщиков | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9eb8eb64bbe585ebd8024c0215853ff04a5c3e54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778440"
---
# <a name="provider-samples"></a>Примеры поставщиков

В этом разделе приводятся примеры поставщиков, обращающихся к базе данных Microsoft Access. Эти примеры включают классы поставщиков, производные от всех базовых классов поставщиков.

## <a name="in-this-section"></a>В этом разделе

Этот раздел содержит следующие подразделы:

[Пример AccessDBProviderSample01](./accessdbprovidersample01.md) В этом примере показано, как объявить класс поставщика, производный непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) . Он приводится здесь только для полноты картины.

[AccessDBProviderSample02](./accessdbprovidersample02.md) В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки вызовов `New-PSDrive` `Remove-PSDrive` командлетов и. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .

[AccessDBProviderSample03](./accessdbprovidersample03.md) В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов `Get-Item` `Set-Item` командлетов и. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

[AccessDBProviderSample04](./accessdbprovidersample04.md) В этом примере показано, как перезаписать методы контейнера для поддержки вызовов к `Copy-Item` `Get-ChildItem` `New-Item` командлетам,, и `Remove-Item` . Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

[AccessDBProviderSample05](./accessdbprovidersample05.md) В этом примере показано, как перезаписать методы контейнера для поддержки вызовов `Move-Item` `Join-Path` командлетов и. Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

[AccessDBProviderSample06](./accessdbprovidersample06.md) В этом примере показано, как перезаписывать методы содержимого для поддержки вызовов к `Clear-Content` `Get-Content` `Set-Content` командлетам, и. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и реализует интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

## <a name="see-also"></a>См. также

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)

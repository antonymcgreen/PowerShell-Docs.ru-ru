---
title: AccessDBProviderSample05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a26661f2-a63c-4ca7-ad3e-dcb4d32ce5a1
caps.latest.revision: 8
ms.openlocfilehash: 43d18672ec4f52961b2a2460635468a2d6fb41e5
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633385"
---
# <a name="accessdbprovidersample05"></a>AccessDBProviderSample05

В этом примере показано, как перезаписать методы контейнера для поддержки вызовов `Move-Item` `Join-Path` командлетов и. Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

## <a name="demonstrates"></a>Что демонстрирует

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:
>
> - Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . См. [AccessDBProviderSample03](./accessdbprovidersample03.md).
> - Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . См. [AccessDBProviderSample04](./accessdbprovidersample04.md).
> - Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .
>
> Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).

В этом образце демонстрируется следующее:

- Объявление `CmdletProvider` атрибута.

- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) для изменения поведения `Move-Item` командлета, позволяя пользователю перемещать элементы из одного расположения в другое. (В этом примере не показано, как добавить динамические параметры в `Move-Item` командлет.)

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) для изменения поведения `Join-Path` командлета.

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) .

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) .

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) .

- Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) .

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для перемещения элементов в базе данных Microsoft Access.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

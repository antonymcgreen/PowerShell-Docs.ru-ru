---
title: AccessDBProviderSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: c0efd10680d3323b6c8d932604176c4425e7266a
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633368"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

В этом примере показано, как перезаписать методы контейнера для поддержки вызовов к `Copy-Item` `Get-ChildItem` `New-Item` командлетам,, и `Remove-Item` . Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

## <a name="demonstrates"></a>Что демонстрирует

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

В этом образце демонстрируется следующее:

- Объявление `CmdletProvider` атрибута.
- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .
- Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) для изменения поведения `Copy-Item` командлета, который позволяет пользователю копировать элементы из одного расположения в другое. (В этом примере не показано, как добавить динамические параметры в `Copy-Item` командлет.)
- Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) для изменения поведения командлета Get-чилдитемс, который позволяет пользователю получить дочерние элементы родительского элемента. (В этом примере не показано, как добавлять динамические параметры в командлет Get-Чилдитемс.)
- Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) для изменения поведения командлета Get-чилдитемс при `Name` указании параметра командлета.
- Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) для изменения поведения `New-Item` командлета, что позволяет пользователю добавлять элементы в хранилище данных. (В этом примере не показано, как добавить динамические параметры в `New-Item` командлет.)
- Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) для изменения поведения `Remove-Item` командлета. (В этом примере не показано, как добавить динамические параметры в `Remove-Item` командлет.)

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для копирования, создания и удаления элементов, а также методы получения дочерних элементов родительского элемента.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

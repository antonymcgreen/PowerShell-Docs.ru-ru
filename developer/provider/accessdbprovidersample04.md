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
ms.openlocfilehash: d9109e8d5b69a25ad52b90bcaff9628b01067211
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057626"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

В этом примере показано, как перезаписать методы контейнера для поддержки вызовов в `Copy-Item`, `Get-ChildItem`, `New-Item`, и `Remove-Item` командлетов. Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.

## <a name="demonstrates"></a>Демонстрация

> [!IMPORTANT]
> Класс поставщика, скорее всего будут производными от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

Этот образец демонстрирует следующее:

- Объявление `CmdletProvider` атрибута.

- Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.

- Перезапись [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод, чтобы изменить поведение `Copy-Item` командлет, который позволяет пользователю копировать элементы из одного расположения в другое. (В этом примере показано, как добавлять динамические параметры для `Copy-Item` командлет.)

- Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод, чтобы изменить поведение командлет Get-ChildItems, который позволяет пользователю получить дочерние элементы родительского элемента . (В этом примере показано, как добавлять динамические параметры в командлет Get-ChildItems.)

- Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) метод, чтобы изменить поведение командлета Get-ChildItems при `Name` указан параметр командлета.

- Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод, чтобы изменить поведение `New-Item` командлет, который позволяет пользователю добавлять элементы в хранилище данных. (В этом примере показано, как добавлять динамические параметры для `New-Item` командлет.)

- Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод, чтобы изменить поведение `Remove-Item` командлета. (В этом примере показано, как добавлять динамические параметры для `Remove-Item` командлет.)

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для копирования, создавать и удалять элементы, а также методы для получения дочерних элементов родительского элемента.

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a>См. также

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)
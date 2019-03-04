---
title: AccessDBProviderSample06 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: 59832ed8a4fad3b07a171946bff28fb3e1dbe442
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854660"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

В этом примере показано, как перезаписать методы содержимого для поддержки вызовов в `Clear-Content`, `Get-Content`, и `Set-Content` командлетов. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс, который реализует [ System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.

## <a name="demonstrates"></a>Демонстрация

> [!IMPORTANT]
> Класс поставщика будет скорее являются производными от одного из следующих классов и возможно реализовать другие интерфейсы поставщика:
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса. См. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md).
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса. См. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.
>
> Дополнительные сведения о выборе какой класс поставщика, являются производными от поставщика функций, см. в разделе [проектирование ваш поставщик PowerShell Windows](./provider-types.md).

Этот образец демонстрирует следующее:

- Объявление `CmdletProvider` атрибута.

- Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса и объявляет [ System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.

- Перезапись [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метод, чтобы изменить поведение `Clear-Content` командлета, позволяя пользователю удалить содержимое из элемента. (В этом примере показано, как добавлять динамические параметры для `Clear-Content` командлет.)

- Перезапись [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) метод, чтобы изменить поведение `Get-Content` командлета, позволяя пользователю извлекать содержимое элемента. (В этом примере показано, как добавлять динамические параметры для `Get-Content` командлет.).

- Перезапись [Microsoft.Powershell.Commands.Filesystemprovider.Getcontentwriter*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) метод, чтобы изменить поведение `Set-Content` командлет, что позволяет пользователю изменить содержимое элемента. (В этом примере показано, как добавлять динамические параметры для `Set-Content` командлет.)

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для очистки, получение и установка базового содержимого для элементов в данных Microsoft Access.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a>См. также

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)
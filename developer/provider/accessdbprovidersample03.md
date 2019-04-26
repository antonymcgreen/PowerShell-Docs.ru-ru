---
title: AccessDBProviderSample03 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: 57b6cfaa5f29300c60a5a745797111b6beba3133
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081076"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

В этом примере показано, как перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) методы для поддержки вызовов в `Get-Item` и `Set-Item` командлетов. Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.

## <a name="demonstrates"></a>Демонстрирует

> [!IMPORTANT]
> Класс поставщика будет скорее являются производными от одного из следующих классов и возможно реализовать другие интерфейсы поставщика:
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса. См. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса. См. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Дополнительные сведения о выборе какой класс поставщика, являются производными от поставщика функций, см. в разделе [проектирование ваш поставщик PowerShell Windows](./provider-types.md).

Этот образец демонстрирует следующее:

- Объявление `CmdletProvider` атрибута.

- Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.

- Перезапись [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод, чтобы изменить поведение `New-PSDrive` командлет, что позволяет пользователю создавать новые диски. (В этом примере показано, как добавлять динамические параметры для `New-PSDrive` командлет.)

- Перезапись [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод для поддержки удаления существующих дисков.

- Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод, чтобы изменить поведение `Get-Item` командлета, позволяя пользователю извлекать элементы из хранилища данных. (В этом примере показано, как добавлять динамические параметры для `Get-Item` командлет.)

- Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод, чтобы изменить поведение `Set-Item` командлета, позволяя пользователю обновлять элементы в хранилище данных. (В этом примере показано, как добавлять динамические параметры для `Get-Item` командлет.)

- Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метод, чтобы изменить поведение `Test-Path` командлета. (В этом примере показано, как добавлять динамические параметры для `Test-Path` командлет.)

- Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) метод, чтобы определить, если указанный путь является допустимым.

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для получения и задания базовых элементов данных Microsoft Access.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a>См. также

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)
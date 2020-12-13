---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample02
description: AccessDBProviderSample02
ms.openlocfilehash: ebba2381370cf73f1e39015990f81dc4fd6dd937
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667442"
---
# <a name="accessdbprovidersample02"></a>AccessDBProviderSample02

В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки вызовов `New-PSDrive` `Remove-PSDrive` командлетов и. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .

## <a name="demonstrates"></a>Что демонстрирует

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:
>
> - Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . См. [AccessDBProviderSample03](./accessdbprovidersample03.md).
> - Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . См. [AccessDBProviderSample04](./accessdbprovidersample04.md).
> - Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . См. [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).

В этом образце демонстрируется следующее:

- Объявление `CmdletProvider` атрибута.

- Определение класса поставщика, который управляется от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .

- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для поддержки создания новых дисков. (В этом примере не показано, как добавить динамические параметры в `New-PSDrive` командлет.)

- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки удаления существующих дисков.

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) . Для этого примера поставщика при создании диска сведения о его соединении хранятся в `AccessDBPsDriveInfo` объекте.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

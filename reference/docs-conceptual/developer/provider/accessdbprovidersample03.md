---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample03
description: AccessDBProviderSample03
ms.openlocfilehash: bfd402903a9023b58dec8865663e3d649a50e1e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667408"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов `Get-Item` `Set-Item` командлетов и. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

## <a name="demonstrates"></a>Что демонстрирует

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:
>
> - Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
> - Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . См. [AccessDBProviderSample04](./accessdbprovidersample04.md).
> - Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . См. [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).

В этом образце демонстрируется следующее:

- Объявление `CmdletProvider` атрибута.
- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для изменения поведения `New-PSDrive` командлета, позволяя пользователю создавать новые диски.
  (В этом примере не показано, как добавить динамические параметры в `New-PSDrive` командлет.)
- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки удаления существующих дисков.
- Перезапись метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для изменения поведения `Get-Item` командлета, позволяя пользователю получать элементы из хранилища данных. (В этом примере не показано, как добавить динамические параметры в `Get-Item` командлет.)
- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для изменения поведения `Set-Item` командлета, позволяя пользователю обновлять элементы в хранилище данных. (В этом примере не показано, как добавить динамические параметры в `Get-Item` командлет.)
- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) для изменения поведения `Test-Path` командлета. (В этом примере не показано, как добавить динамические параметры в `Test-Path` командлет.)
- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) , чтобы определить, является ли указанный путь допустимым.

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для получения и задания элементов в базе данных Microsoft Access.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

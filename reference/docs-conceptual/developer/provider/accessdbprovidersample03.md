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
ms.openlocfilehash: aa67bb605f90c1ea40323b4583766069ff1226fb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359993"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов `Get-Item` и @no__ Командлеты t-3. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

## <a name="demonstrates"></a>Демонстрирующее

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:
>
> -   Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .
> -   Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . См. [AccessDBProviderSample04](./accessdbprovidersample04.md).
> -   Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . См. [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).

В этом образце демонстрируется следующее.

- Объявление атрибута `CmdletProvider`.

- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для изменения поведения командлета `New-PSDrive`, позволяя пользователю создавать новые диски. (В этом примере не показано, как добавлять динамические параметры в командлет `New-PSDrive`).

- Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки удаления существующих дисков.

- Перезапись метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для изменения поведения командлета `Get-Item`, позволяя пользователю получать элементы из хранилища данных. (В этом примере не показано, как добавлять динамические параметры в командлет `Get-Item`).

- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для изменения поведения командлета `Set-Item`, позволяя пользователю обновлять элементы в хранилище данных. (В этом примере не показано, как добавлять динамические параметры в командлет `Get-Item`).

- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) для изменения поведения командлета `Test-Path`. (В этом примере не показано, как добавлять динамические параметры в командлет `Test-Path`).

- Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) , чтобы определить, является ли указанный путь допустимым.

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для получения и задания элементов в базе данных Microsoft Access.

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

---
title: AccessDBProviderSample01 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 50ec218e8d0fe6b2be5c8ac00956f72c6723f84a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786923"
---
# <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

В этом примере показано, как объявить класс поставщика, производный непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) . Он приводится здесь только для полноты картины.

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

- Определение класса поставщика, производного непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .

## <a name="example"></a>Пример

В этом примере показано, как определить класс поставщика и как объявить `CmdletProvider` атрибут.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a>См. также

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

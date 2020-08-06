---
title: AccessDBProviderSample06 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 893eb80574c7f142f92906961588e22b1ced0052
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786838"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

В этом примере показано, как перезаписывать методы содержимого для поддержки вызовов к `Clear-Content` `Get-Content` `Set-Content` командлетам, и. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и реализует интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

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
- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и объявляющего интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .
- Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для изменения поведения `Clear-Content` командлета, позволяя пользователю удалить содержимое из элемента. (В этом примере не показано, как добавить динамические параметры в `Clear-Content` командлет.)
- Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для изменения поведения `Get-Content` командлета, позволяя пользователю извлекать содержимое элемента. (В этом примере не показано, как добавить динамические параметры в `Get-Content` командлет.)
- Перезапись метода [Microsoft. PowerShell. Commands. филесистемпровидер. жетконтентвритер *](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) для изменения поведения `Set-Content` командлета, позволяя пользователю обновлять содержимое элемента. (В этом примере не показано, как добавить динамические параметры в `Set-Content` командлет.)

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для очистки, получения и установки содержимого элементов в базе данных Microsoft Access.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a>См. также

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

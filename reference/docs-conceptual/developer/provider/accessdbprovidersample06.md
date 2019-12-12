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
ms.openlocfilehash: 9c00ec6de987729fec42dc57245a949d11e31f4b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366333"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

В этом примере показано, как перезаписывать методы содержимого для поддержки вызовов `Clear-Content`, `Get-Content`и командлетов `Set-Content`. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и реализует интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

## <a name="demonstrates"></a>Демонстрация

> [!IMPORTANT]
> Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:
>
> -   Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . См. [AccessDBProviderSample03](./accessdbprovidersample03.md).
> -   Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . См. [AccessDBProviderSample04](./accessdbprovidersample04.md).
> -   Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .
>
> Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).

В этом образце демонстрируется следующее:

- Объявление атрибута `CmdletProvider`.

- Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и объявляющего интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

- Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для изменения поведения командлета `Clear-Content`, позволяя пользователю удалить содержимое из элемента. (В этом примере не показано, как добавлять динамические параметры в командлет `Clear-Content`.)

- Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для изменения поведения командлета `Get-Content`, позволяя пользователю извлекать содержимое элемента. (В этом примере не показано, как добавлять динамические параметры в командлет `Get-Content`.).

- Перезапись метода [Microsoft. PowerShell. Commands. филесистемпровидер. жетконтентвритер *](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) для изменения поведения командлета `Set-Content`, позволяя пользователю обновлять содержимое элемента. (В этом примере не показано, как добавлять динамические параметры в командлет `Set-Content`.)

## <a name="example"></a>Пример

В этом примере показано, как перезаписать методы, необходимые для очистки, получения и установки содержимого элементов в базе данных Microsoft Access.

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a>См. также:

[System. Management. Automation. Provider. Итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. Контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Разработка поставщика Windows PowerShell](./provider-types.md)

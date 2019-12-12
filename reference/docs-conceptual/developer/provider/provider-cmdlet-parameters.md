---
title: Параметры командлета поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: ad7f9737c646dd5cea5abb14b828236e40feac5a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366313"
---
# <a name="provider-cmdlet-parameters"></a>Параметры командлета поставщика

Командлеты поставщика поставляются с набором статических параметров, доступных для всех поставщиков, поддерживающих командлет, а также динамических параметров, которые добавляются, когда пользователь указывает определенное значение для определенных статических параметров командлета поставщика.

## <a name="provider-cmdlet-static-parameters"></a>Статические параметры командлета поставщика

Статические параметры определяются Windows PowerShell. Большой набор этих параметров реализуется с помощью Windows PowerShell для обеспечения согласованности всех поставщиков и обеспечения более простого процесса разработки. Примерами этих параметров являются параметры `literalPath`, `exclude`и `include` командлета `Get-Item`. Небольшой набор этих параметров может быть перезаписан для предоставления действий, относящихся к конкретному поставщику. Примерами этих параметров являются параметры `Path` и `Value` командлета `Set-Item`. Ниже приведен список параметров, которые могут быть перезаписаны для командлетов поставщика.

`Clear-Content` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Clear-Content`, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

`Clear-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Clear-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

`Clear-ItemProperty` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` командлета `Clear-ItemProperty`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

`Copy-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `Destination`и `Recurse` командлета `Copy-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) .

Командлет Get-Чилдитемс. Вы можете определить, как поставщик будет использовать значения, передаваемые в `Path` и `Recurse` параметры командлета `Get-ChildItem`. для этого нужно реализовать методы [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

`Get-Content` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Get-Content`, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Get-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

`Get-ItemProperty` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` командлета `Get-ItemProperty`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер., свойство *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

`Invoke-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Invoke-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

`Move-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Destination` командлета `Move-Item`, реализовав метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

`New-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `ItemType`и `Value` командлета `New-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) .

`New-ItemProperty` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `Name`, `PropertyType`и `Value` командлета `New-ItemProperty`, реализовав метод [Microsoft. PowerShell. Commands. регистрипровидер. невпроперти *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) .

`Remove-Item` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Recurse` командлета `Remove-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` командлета `Remove-ItemProperty`, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. Removeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) .

`Rename-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `NewName` командлета `Rename-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `NewName`и `Name` командлета `Rename-ItemProperty`, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) .

`Set-Content` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Set-Content`, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

`Set-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Value` командлета `Set-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

`Set-ItemProperty` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Value` командлета `Set-Item`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

`Test-Path` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Test-Path`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Кроме того, нельзя указывать характеристики этих параметров, например, являются ли они необязательными или обязательными, а также не могут предоставлять этим параметрам псевдоним или указывать какие либо атрибуты проверки. В отличие от этого, можно указать характеристики параметров в изолированных командлетах с помощью атрибутов, таких как атрибут `Parameters`.

## <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Динамические параметры для поставщиков командлетов похожи на динамические поставщики для отдельных командлетов. В обоих случаях параметры добавляются в командлет, когда пользователь указывает определенное значение для одного из параметров по умолчанию, например параметр `path`. Однако не все статические параметры можно использовать для активации добавления динамических параметров. Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета Provider](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>См. также:

[Динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md)

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
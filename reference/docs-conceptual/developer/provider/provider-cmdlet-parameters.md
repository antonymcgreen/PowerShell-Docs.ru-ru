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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366313"
---
# <a name="provider-cmdlet-parameters"></a>Параметры командлета поставщика

Командлеты поставщика поставляются с набором статических параметров, доступных для всех поставщиков, поддерживающих командлет, а также динамических параметров, которые добавляются, когда пользователь указывает определенное значение для определенных статических параметров командлета поставщика.

## <a name="provider-cmdlet-static-parameters"></a>Статические параметры командлета поставщика

Статические параметры определяются Windows PowerShell. Большой набор этих параметров реализуется с помощью Windows PowerShell для обеспечения согласованности всех поставщиков и обеспечения более простого процесса разработки. Примерами этих параметров являются параметры `literalPath`, `exclude` и `include` для командлета `Get-Item`. Небольшой набор этих параметров может быть перезаписан для предоставления действий, относящихся к конкретному поставщику. Примерами этих параметров являются параметры `Path` и `Value` командлета `Set-Item`. Ниже приведен список параметров, которые могут быть перезаписаны для командлетов поставщика.

Командлет `Clear-Content` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Clear-Content`, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

Командлет `Clear-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Clear-Item`, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

Командлет `Clear-ItemProperty` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` для командлета `Clear-ItemProperty`, путем реализации метода [System. Management. автоматизации. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

Командлет `Copy-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `Destination` и `Recurse` командлета `Copy-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) Method.

Командлет Get-Чилдитемс. Вы можете определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Recurse` командлета `Get-ChildItem`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

Командлет `Get-Content` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Get-Content`, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item` командлет можно определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Get-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

Командлет `Get-ItemProperty` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` для командлета `Get-ItemProperty`, путем реализации метода [System. Management. автоматизации. Provider. ипропертикмдлетпровидер. WebMethod *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

Командлет `Invoke-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Invoke-Item`, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Командлет `Move-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Destination` для командлета `Move-Item`, путем реализации метода [System. Management. автоматизации. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

Командлет `New-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `ItemType` и `Value` командлета `New-Item`, путем реализации класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) Method.

Командлет `New-ItemProperty` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `Name`, `PropertyType` и `Value` командлета `New-ItemProperty`, путем реализации [Microsoft. PowerShell. Commands. регистрипровидер. невпроперти *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) Method.

`Remove-Item` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Recurse` для командлета `Remove-Item`, путем реализации метода [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Name` для командлета `Remove-ItemProperty`, путем реализации класса [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. Removeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) Method.

Командлет `Rename-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `NewName` для командлета `Rename-Item`, путем реализации метода [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty` можно определить, как поставщик будет использовать значения, передаваемые в параметры `Path`, `NewName` и `Name` командлета `Rename-ItemProperty`, путем реализации класса [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти * ](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)метод.

Командлет `Set-Content` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Set-Content`, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

Командлет `Set-Item` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Value` для командлета `Set-Item`, путем реализации метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

Командлет `Set-ItemProperty` позволяет определить, как поставщик будет использовать значения, передаваемые в параметры `Path` и `Value` для командлета `Set-Item`, путем реализации метода [System. Management. автоматизации. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

Командлет `Test-Path` позволяет определить, как поставщик будет использовать значения, передаваемые в параметр `Path` командлета `Test-Path`, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Кроме того, нельзя указывать характеристики этих параметров, например, являются ли они необязательными или обязательными, а также не могут предоставлять этим параметрам псевдоним или указывать какие либо атрибуты проверки. В отличие от этого, можно указать характеристики параметров в изолированных командлетах с помощью атрибутов, таких как атрибут `Parameters`.

## <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Динамические параметры для поставщиков командлетов похожи на динамические поставщики для отдельных командлетов. В обоих случаях параметры добавляются в командлет, когда пользователь указывает определенное значение для одного из параметров по умолчанию, например параметр `path`. Однако не все статические параметры можно использовать для активации добавления динамических параметров. Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета Provider](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>См. также:

[Динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md)

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
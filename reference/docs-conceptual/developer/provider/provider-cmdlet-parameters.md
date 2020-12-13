---
ms.date: 09/13/2016
ms.topic: reference
title: Параметры командлета поставщика
description: Параметры командлета поставщика
ms.openlocfilehash: 6fd340f22202d984b7111c34806e3461a356c670
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662774"
---
# <a name="provider-cmdlet-parameters"></a>Параметры командлета поставщика

Командлеты поставщика поставляются с набором статических параметров, доступных для всех поставщиков, поддерживающих командлет, а также динамических параметров, которые добавляются, когда пользователь указывает определенное значение для определенных статических параметров командлета поставщика.

## <a name="provider-cmdlet-static-parameters"></a>Статические параметры командлета поставщика

Статические параметры определяются Windows PowerShell. Большой набор этих параметров реализуется с помощью Windows PowerShell для обеспечения согласованности всех поставщиков и обеспечения более простого процесса разработки. Примеры этих параметров включают `literalPath` `exclude` Параметры, и `include` `Get-Item` командлета. Небольшой набор этих параметров может быть перезаписан для предоставления действий, относящихся к конкретному поставщику. Примерами этих параметров являются `Path` параметр и `Value` `Set-Item` командлет. Ниже приведен список параметров, которые могут быть перезаписаны для командлетов поставщика.

`Clear-Content` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Clear-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

`Clear-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Clear-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

`Clear-ItemProperty` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Clear-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

`Copy-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `Destination` и `Recurse` `Copy-Item` командлета, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) .

Get-ChildItems командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Recurse` `Get-ChildItem` командлета, путем реализации методов [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

`Get-Content` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Get-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Get-Item` командлета, путем реализации метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

`Get-ItemProperty` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Get-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. WebMethod *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

`Invoke-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Invoke-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

`Move-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Destination` `Move-Item` командлета, путем реализации метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

`New-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `ItemType` и `Value` `New-Item` командлета, путем реализации метода [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) .

`New-ItemProperty` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `Name` , `PropertyType` и `Value` `New-ItemProperty` командлета, путем реализации метода [Microsoft. PowerShell. Commands. регистрипровидер. невпроперти *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) .

`Remove-Item` Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Recurse` `Remove-Item` командлета, путем реализации метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty` Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Remove-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. Removeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) .

`Rename-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `NewName` `Rename-Item` командлета, путем реализации метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty` Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `NewName` и `Name` `Rename-ItemProperty` командлета, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) .

`Set-Content` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Set-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

`Set-Item` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Value` `Set-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

`Set-ItemProperty` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Value` `Set-Item` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

`Test-Path` Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Test-Path` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Кроме того, нельзя указывать характеристики этих параметров, например, являются ли они необязательными или обязательными, а также не могут предоставлять этим параметрам псевдоним или указывать какие либо атрибуты проверки. В отличие от этого, можно указать характеристики параметров в изолированных командлетах с помощью атрибутов, таких как `Parameters` атрибут.

## <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Динамические параметры для поставщиков командлетов похожи на динамические поставщики для отдельных командлетов. В обоих случаях параметры добавляются в командлет, когда пользователь указывает определенное значение для одного из параметров по умолчанию, таких как `path` параметр. Однако не все статические параметры можно использовать для активации добавления динамических параметров. Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета Provider](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>См. также:

[Динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md)

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)

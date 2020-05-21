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
ms.openlocfilehash: 8ce13032a55d164121a073ef94086dc1de09b902
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564212"
---
# <a name="provider-cmdlet-parameters"></a>Параметры командлета поставщика

Командлеты поставщика поставляются с набором статических параметров, доступных для всех поставщиков, поддерживающих командлет, а также динамических параметров, которые добавляются, когда пользователь указывает определенное значение для определенных статических параметров командлета поставщика.

## <a name="provider-cmdlet-static-parameters"></a>Статические параметры командлета поставщика

Статические параметры определяются Windows PowerShell. Большой набор этих параметров реализуется с помощью Windows PowerShell для обеспечения согласованности всех поставщиков и обеспечения более простого процесса разработки. Примеры этих параметров включают `literalPath` `exclude` Параметры, и `include` `Get-Item` командлета. Небольшой набор этих параметров может быть перезаписан для предоставления действий, относящихся к конкретному поставщику. Примерами этих параметров являются `Path` параметр и `Value` `Set-Item` командлет. Ниже приведен список параметров, которые могут быть перезаписаны для командлетов поставщика.

`Clear-Content`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Clear-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) .

`Clear-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Clear-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .

`Clear-ItemProperty`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Clear-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) .

`Copy-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `Destination` и `Recurse` `Copy-Item` командлета, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) .

Командлет Get-Чилдитемс. Вы можете определить, как поставщик будет использовать значения, передаваемые `Path` в `Recurse` Параметры и `Get-ChildItem` командлет, путем реализации методов [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) .

`Get-Content`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Get-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) .

`Get-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Get-Item` командлета, путем реализации метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .

`Get-ItemProperty`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Get-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. WebMethod *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) .

`Invoke-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Invoke-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

`Move-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Destination` `Move-Item` командлета, путем реализации метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) .

`New-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `ItemType` и `Value` `New-Item` командлета, путем реализации метода [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) .

`New-ItemProperty`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `Name` , `PropertyType` и `Value` `New-ItemProperty` командлета, путем реализации метода [Microsoft. PowerShell. Commands. регистрипровидер. невпроперти *](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) .

`Remove-Item`Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Recurse` `Remove-Item` командлета, путем реализации метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) .

`Remove-ItemProperty`Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Name` `Remove-ItemProperty` командлета, путем реализации метода [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. Removeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) .

`Rename-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `NewName` `Rename-Item` командлета, путем реализации метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) .

`Rename-ItemProperty`Можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры, `NewName` и `Name` `Rename-ItemProperty` командлета, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) .

`Set-Content`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Set-Content` командлета, путем реализации метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) .

`Set-Item`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Value` `Set-Item` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) .

`Set-ItemProperty`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` Параметры и `Value` `Set-Item` командлета, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) .

`Test-Path`Командлет можно определить, как поставщик будет использовать значения, передаваемые в `Path` параметр `Test-Path` командлета, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

Кроме того, нельзя указывать характеристики этих параметров, например, являются ли они необязательными или обязательными, а также не могут предоставлять этим параметрам псевдоним или указывать какие либо атрибуты проверки. В отличие от этого, можно указать характеристики параметров в изолированных командлетах с помощью атрибутов, таких как `Parameters` атрибут.

## <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Динамические параметры для поставщиков командлетов похожи на динамические поставщики для отдельных командлетов. В обоих случаях параметры добавляются в командлет, когда пользователь указывает определенное значение для одного из параметров по умолчанию, таких как `path` параметр. Однако не все статические параметры можно использовать для активации добавления динамических параметров. Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета Provider](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>См. также:

[Динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md)

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)

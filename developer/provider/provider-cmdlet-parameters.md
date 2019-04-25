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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081144"
---
# <a name="provider-cmdlet-parameters"></a>Параметры командлета поставщика

Командлеты поставщика в состав набора статические параметры, доступные для всех поставщиков, которые поддерживают этот командлет, а также как динамические параметры, которые добавляются, когда пользователь задает определенное значение для определенных статических параметров командлета поставщика.

## <a name="provider-cmdlet-static-parameters"></a>Параметры поставщика Static командлета

Статические параметры определяются с Windows PowerShell. Windows PowerShell позволяет обеспечить согласованность всех поставщиков и обеспечивают более простую рабочую среду разработки реализуют большой набор этих параметров. Эти параметры относятся `literalPath`, `exclude`, и `include` параметры `Get-Item` командлета. Меньший набор этих параметров могут быть перезаписаны для выполнения действий, относящихся к поставщику. Эти параметры относятся `Path` и `Value` параметр `Set-Item` командлета. Ниже приведен список параметров, которые могут быть перезаписаны по командлетам поставщика.

`Clear-Content` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Clear-Content` командлета путем реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)метод.

`Clear-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Clear-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) метод.

`Clear-ItemProperty` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `Name` параметры `Clear-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) метод.

`Copy-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path`, `Destination`, и `Recurse` параметры `Copy-Item` командлета путем реализации [ System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод.

Командлет Get-ChildItems, вы можете определить, как поставщик будет использовать значения, передаваемые `Path` и `Recurse` параметры `Get-ChildItem` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) методы.

`Get-Content` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Get-Content` командлета путем реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) метод.

`Get-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Get-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод.

`Get-ItemProperty` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `Name` параметры `Get-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) метод.

`Invoke-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Invoke-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)метод.

`Move-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `Destination` параметры `Move-Item` командлета путем реализации [ System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод.

`New-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path`, `ItemType`, и `Value` параметры `New-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод.

`New-ItemProperty` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path`, `Name`, `PropertyType`, и `Value` параметры `New-ItemProperty` командлета путем реализации [ Microsoft.PowerShell.Commands.Registryprovider.Newproperty*](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) метод.

`Remove-Item` Вы можете определить, как поставщик будет использовать значения, передаваемые `Path` и `Recurse` параметры `Remove-Item` командлета путем реализации [System.Management.Automation.Provider.Containercmdletprovider.Removeitem* ](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод.

`Remove-ItemProperty` Вы можете определить, как поставщик будет использовать значения, передаваемые `Path` и `Name` параметры `Remove-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) метод.

`Rename-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `NewName` параметры `Rename-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод.

`Rename-ItemProperty` Вы можете определить, как поставщик будет использовать значения, передаваемые `Path`, `NewName`, и `Name` параметры `Rename-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) метод.

`Set-Content` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Set-Content` командлета путем реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) метод.

`Set-Item` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `Value` параметры `Set-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Setitem* ](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод.

`Set-ItemProperty` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` и `Value` параметры `Set-Item` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) метод.

`Test-Path` командлет, можно определить как поставщик будет использовать значения, передаваемые `Path` параметр `Test-Path` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)метод.

Кроме того нельзя указать характеристики этих параметров, например, являются ли они обязательными или необязательными, и не может предоставить эти параметры, псевдоним или указывать какие-либо атрибуты проверки. Напротив, можно указать характеристики параметров в изолированной командлетов с помощью атрибутов, таких как `Parameters` атрибута.

## <a name="provider-cmdlet-dynamic-parameters"></a>Параметры командлета динамической поставщика

Динамические параметры для командлета поставщиков похожи на динамические поставщиков для автономного командлетов. В обоих случаях параметры добавляются в командлет, когда пользователь задает определенное значение для одного из параметров по умолчанию, такие как `path` параметр. Однако не все статические параметры можно использовать для активации Добавление динамических параметров. Дополнительные сведения о динамических параметров, см. в разделе [динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md).

## <a name="see-also"></a>См. также

[Параметры командлета динамической поставщика](./provider-cmdlet-dynamic-parameters.md)

[Разработка поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
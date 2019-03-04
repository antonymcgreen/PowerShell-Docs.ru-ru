---
title: Командлеты поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2465420-0970-4408-9ee5-260cf444cb67
caps.latest.revision: 8
ms.openlocfilehash: e6a0711cff6a550100f584fb64ae7f59f71a3cfb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854770"
---
# <a name="provider-cmdlets"></a>Командлеты поставщика

Командлеты, которые пользователь может выполнять для управления хранилищем данных, называются командлеты поставщика. Для поддержки этих командлетов, необходимо перезаписать, некоторые из методов, определенных для базового поставщика классы и интерфейсы.

## <a name="provider-cmdlets"></a>Командлеты поставщика

Ниже приведены командлеты поставщика, который может выполняться пользователем.

### <a name="psdrive-cmdlets"></a>Командлеты PSDrive

- `Get-PSDrive`: Этот командлет возвращает диски Windows PowerShell в текущем сеансе. Необходимо перезаписать любые методы для поддержки этого командлета.

- `New-PSDrive`: Этот командлет позволяет пользователю создавать диски Windows PowerShell для доступа к хранилищу данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [ System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) методы.

- `Remove-PSDrive`: Этот командлет позволяет пользователю удалять диски Windows PowerShell, которые обращаются к хранилищу данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод.

### <a name="item-cmdlets"></a>Командлеты Item

- `Clear-Item`: Этот командлет позволяет пользователю удалить значение элемента в хранилище данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) и [ System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) методы.

- `Copy-Item`: Этот командлет позволяет пользователю скопировать элемент из одного расположения в другое. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Containercmdletprovider.Copyitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) и [ System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) методы.

- `Get-Item`: Этот командлет позволяет пользователю получать данные из хранилища данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters ](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) методы.

- `Get-ChildItem`: Этот командлет позволяет получить дочерние элементы родительского элемента. Для поддержки этого командлета, перезапишите следующие методы:

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`: Этот командлет позволяет пользователю выполнять действие по умолчанию, заданному элементом. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) и [ System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) методы.

- `Move-Item`: Этот командлет позволяет пользователю на перемещение элемента из одного расположения в другое расположение. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) и [ System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s методы.

- `New-ItemProperty`: Этот командлет позволяет создать новый элемент в хранилище данных.

- `Remove-Item`: Этот командлет позволяет пользователю удалять элементы из хранилища данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Containercmdletprovider.Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) и [ System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) методы.

- `Rename-Item`: Этот командлет позволяет переименовывать элементы в хранилище данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Containercmdletprovider.Renameitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) и [ System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) методы.

- `Set-Item`: Этот командлет позволяет пользователю изменить значения элементов в хранилище данных. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters ](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) методы.

### <a name="item-content-cmdlets"></a>Командлеты content элемента

- `Add-Content`: Этот командлет позволяет пользователю добавлять содержимое к элементу.

- `Clear-Content`: Этот командлет позволяет пользователю удалить содержимое элемента без удаления элемента. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) и [ System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) методы.

- `Get-Content`: Этот командлет позволяет пользователю для получения содержимого элемента. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) и [ System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) методы. [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) возвращает [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) интерфейс, определяющий методы, используемые для чтения содержимого.

- `Set-Content`: Этот командлет позволяет пользователю изменить содержимое элемента. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) и [ System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) методы. [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) возвращает [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) интерфейс, определяющий методы, используемые для записи содержимого.

### <a name="item-property-cmdlets"></a>Свойство командлетов Item

- `Clear-ItemProperty`: Этот командлет позволяет пользователю удалить значение свойства. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) и [ System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) методы.

- `Copy-ItemProperty`: Этот командлет позволяет пользователю скопировать свойства и его значение из одного расположения в другое. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) методы.

- `Get-ItemProperty`: Этот командлет возвращает свойства элемента. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) и [ System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) методы.

- `Move-ItemProperty`: Этот командлет позволяет пользователю перемещать свойство и его значение из одного расположения в другое. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) методы.

- `New-ItemProperty`: Этот командлет позволяет создать новое свойство и присвойте ему значение. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) методы.

- `Remove-ItemProperty`: Этот командлет позволяет пользователю удалить свойство и его значение. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) методы.

- `Rename-ItemProperty`: Этот командлет позволяет пользователю изменять имя свойства. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) методы.

- `Set-ItemProperty`: Этот командлет позволяет обновить свойства элемента. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) и [ System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) методы.

### <a name="location-cmdlets"></a>Командлеты Location

- `Get-Location`: Извлекает сведения о текущем рабочем расположении. Необходимо перезаписать любые методы для поддержки этого командлета.

- `Pop-Location`: Этот командлет изменяет текущее расположение на расположение, наиболее недавно помещается в стек. Необходимо перезаписать любые методы для поддержки этого командлета.

- `Push-Location`: Этот командлет добавляет текущее расположение в начало списка расположений («стек»). Необходимо перезаписать любые методы для поддержки этого командлета.

- `Set-Location`: Этот командлет задает текущему рабочему расположению указанное расположение. Необходимо перезаписать любые методы для поддержки этого командлета.

### <a name="path-cmdlets"></a>Командлеты путь

- `Join-Path`: Этот командлет позволяет пользователю для объединения родительских и дочерних сегмент пути для создания поставщика внутреннего пути. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод.

- `Convert-Path`: Этот командлет преобразует путь из пути Windows PowerShell в путь поставщика Windows PowerShell.

- `Split-Path`: Возвращает указанную часть пути.

- `Resolve-Path`: Разрешает подстановочные знаки в пути и отображает содержимое пути.

- `Test-Path`: Этот командлет определяет, существуют ли все элементы пути. Для поддержки этого командлета, перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) и [ System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) методы.

### <a name="psprovider-cmdlets"></a>Командлеты PSProvider

- `Get-PSProvider`: Этот командлет возвращает сведения о поставщиках, доступных в сеансе. Необходимо перезаписать любые методы для поддержки этого командлета.
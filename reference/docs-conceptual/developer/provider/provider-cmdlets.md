---
title: Командлеты поставщика | Документация Майкрософт
ms.date: 09/12/2016
ms.openlocfilehash: 24838eeec8e2d59ff3cc549c8659d5afb1c8f92f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771691"
---
# <a name="provider-cmdlets"></a>Командлеты поставщика

Командлеты, которые пользователь может запускать для управления хранилищем данных, называются командлетами поставщика. Для поддержки этих командлетов необходимо переписать некоторые методы, определенные базовыми классами и интерфейсами поставщика.

## <a name="provider-cmdlets"></a>Командлеты поставщика

Ниже приведены командлеты поставщика, которые могут быть запущены пользователем:

### <a name="psdrive-cmdlets"></a>Командлеты PSDrive

- `Get-PSDrive`: Этот командлет возвращает диски Windows PowerShell в текущем сеансе. Для поддержки этого командлета не требуется перезаписывать методы.

- `New-PSDrive`: Этот командлет позволяет пользователю создавать диски Windows PowerShell для доступа к хранилищу данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

- `Remove-PSDrive`: Этот командлет позволяет пользователю удалять диски Windows PowerShell, которые обращаются к хранилищу данных. Для поддержки этого командлета Перепишите метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) .

### <a name="item-cmdlets"></a>Командлеты элементов

- `Clear-Item`: Этот командлет позволяет пользователю удалить значение элемента в хранилище данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

- `Copy-Item`: Этот командлет позволяет пользователю копировать элемент из одного расположения в другое. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

- `Get-Item`: Этот командлет позволяет пользователю получать данные из хранилища данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

- `Get-ChildItem`: Этот командлет позволяет пользователю получать дочерние элементы родительского элемента. Для поддержки этого командлета Перепишите следующие методы:

  - [System. Management. Automation. Provider. Контаинеркмдлетпровидер. Жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [System. Management. Automation. Provider. Контаинеркмдлетпровидер. Жетчилдитемсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [System. Management. Automation. Provider. Контаинеркмдлетпровидер. Жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [System. Management. Automation. Provider. Контаинеркмдлетпровидер. Жетчилднамесдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`: Этот командлет позволяет пользователю выполнять действие по умолчанию, заданное элементом. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) и [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) .

- `Move-Item`: Этот командлет позволяет пользователю переместить элемент из одного расположения в другое. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) и [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s.

- `New-ItemProperty`: Этот командлет позволяет пользователю создать новый элемент в хранилище данных.

- `Remove-Item`: Этот командлет позволяет пользователю удалять элементы из хранилища данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

- `Rename-Item`: Этот командлет позволяет пользователю переименовывать элементы в хранилище данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

- `Set-Item`: Этот командлет позволяет пользователю обновлять значения элементов в хранилище данных. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

### <a name="item-content-cmdlets"></a>Командлеты содержимого элементов

- `Add-Content`: Этот командлет позволяет пользователю добавлять содержимое в элемент.

- `Clear-Content`: Этот командлет позволяет пользователю удалять содержимое элемента, не удаляя элемент. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

- `Get-Content`: Этот командлет позволяет пользователю получить содержимое элемента. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) . Метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) возвращает интерфейс [System. Management. Automation. Provider. иконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentReader) , который определяет методы, используемые для чтения содержимого.

- `Set-Content`: Этот командлет позволяет пользователю обновлять содержимое элемента. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) . Метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) возвращает интерфейс [System. Management. Automation. Provider. иконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentWriter) , который определяет методы, используемые для записи содержимого.

### <a name="item-property-cmdlets"></a>Командлеты свойств элементов

- `Clear-ItemProperty`: Этот командлет позволяет пользователю удалить значение свойства. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) и [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

- `Copy-ItemProperty`: Этот командлет позволяет пользователю копировать свойство и его значение из одного расположения в другое. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. копипроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. копипропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) .

- `Get-ItemProperty`: Этот командлет получает свойства элемента. Для поддержки этого командлета Перепишите методы [System. Management. Automation. Provider. ипропертикмдлетпровидер.](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) [ипропертикмдлетпровидер. жетпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

- `Move-ItemProperty`: Этот командлет позволяет пользователю переместить свойство и его значение из одного расположения в другое. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. мовепроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. мовепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) .

- `New-ItemProperty`: Этот командлет позволяет пользователю создать новое свойство и задать его значение. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

- `Remove-ItemProperty`: Этот командлет позволяет пользователю удалить свойство и его значение. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ремовепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

- `Rename-ItemProperty`: Этот командлет позволяет пользователю изменить имя свойства. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

- `Set-ItemProperty`: Этот командлет позволяет пользователю обновлять свойства элемента. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) и [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

### <a name="location-cmdlets"></a>Командлеты Location

- `Get-Location`— Получает сведения о текущем рабочем расположении. Для поддержки этого командлета не требуется перезаписывать методы.

- `Pop-Location`: Этот командлет изменяет текущее расположение на расположение, которое недавно было отправлено в стек. Для поддержки этого командлета не требуется перезаписывать методы.

- `Push-Location`: Этот командлет добавляет текущее расположение в начало списка расположений ("Stack"). Для поддержки этого командлета не требуется перезаписывать методы.

- `Set-Location`: Этот командлет задает для текущего рабочего расположения указанное расположение. Для поддержки этого командлета не требуется перезаписывать методы.

### <a name="path-cmdlets"></a>Командлеты пути

- `Join-Path`: Этот командлет позволяет пользователю объединять родительский и дочерний сегмент пути для создания внутреннего пути поставщика. Для поддержки этого командлета Перепишите метод [System. Management. Automation. Provider. Navigationcmdletprovider. макепас](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) .

- `Convert-Path`: Этот командлет преобразует путь из пути Windows PowerShell в путь поставщика Windows PowerShell.

- `Split-Path`: Возвращает указанную часть пути.

- `Resolve-Path`: Разрешает подстановочные знаки в пути и отображает содержимое пути.

- `Test-Path`: Этот командлет определяет, существуют ли все элементы пути. Для поддержки этого командлета перезапишите методы [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) и [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистсдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) .

### <a name="psprovider-cmdlets"></a>Командлеты PSProvider

- `Get-PSProvider`: Этот командлет возвращает сведения о поставщиках, доступных в сеансе. Для поддержки этого командлета не требуется перезаписывать методы.

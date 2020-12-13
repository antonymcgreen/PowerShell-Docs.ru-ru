---
ms.date: 08/21/2019
ms.topic: reference
title: Типы поставщиков
description: Типы поставщиков
ms.openlocfilehash: 9d3b458d7647a297fcda086db3540a0c15c576db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661760"
---
# <a name="provider-types"></a>Типы поставщиков

Поставщики определяют их основные функциональные возможности, изменяя действия командлетов поставщика, предоставляемых PowerShell, для выполнения их действий. Например, поставщики могут использовать функциональность командлета по умолчанию `Get-Item` или изменить способ работы командлета при извлечении элементов из хранилища данных. Функциональные возможности поставщика, описанные в этом документе, включают функциональные возможности, определенные перезаписью методов из базовых классов и интерфейсов конкретного поставщика.

> [!NOTE]
> Сведения о функциях поставщиков, предварительно определенных с помощью PowerShell, см. в разделе [возможности поставщика](/previous-versions//ee126189(v=vs.85)).

## <a name="drive-enabled-providers"></a>Поставщики с поддержкой дисков

Поставщики с поддержкой дисков указывают диски по умолчанию, доступные пользователю, и позволяют пользователю добавлять или удалять диски. В большинстве случаев поставщики являются поставщиками с поддержкой устройств, так как для доступа к хранилищу данных требуется некоторый диск по умолчанию. Однако при написании собственного поставщика может быть нежелательно, чтобы пользователь мог создавать и удалять диски.

Чтобы создать поставщик с поддержкой устройств, класс поставщика должен быть производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) или другого класса, производного от этого класса. Класс **System. Management. Automation. Provider. дривекмдлетпровидер** определяет следующие методы реализации дисков поставщика по умолчанию и поддержки `New-PSDrive` `Remove-PSDrive` командлетов и. В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `NewDrive` метод для `New-PSDrive` командлета, и при необходимости можно перезаписать второй метод, например `NewDriveDynamicParameters` , для добавления динамических параметров к командлету.

- Метод [System.Management.Automation.Provider.DriveCmdletProvider.Iniтиализедефаултдривес](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) определяет диски по умолчанию, доступные пользователю при каждом использовании поставщика.

- Методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) определяют, как поставщик поддерживает `New-PSDrive` командлет поставщика. Этот командлет позволяет пользователю создавать диски для доступа к хранилищу данных.

- Метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) определяет, как поставщик поддерживает `Remove-PSDrive` командлет поставщика. Этот командлет позволяет пользователю удалять диски из хранилища данных.

## <a name="item-enabled-providers"></a>Поставщики с поддержкой элементов

Поставщики с поддержкой элементов позволяют пользователю получать, устанавливать или очищать элементы в хранилище данных. "Элемент" — это элемент хранилища данных, к которому пользователь может обращаться независимо или управлять им. Чтобы создать поставщик с поддержкой элементов, класс поставщика должен быть производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) или другого класса, производного от этого класса.

Класс **System. Management. Automation. Provider. итемкмдлетпровидер** определяет следующие методы реализации конкретных командлетов поставщика. В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `ClearItem` метод для `Clear-Item` командлета, и при необходимости можно перезаписать второй метод, например `ClearItemDynamicParameters` , для добавления динамических параметров к командлету.

- Методы [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) определяют, как поставщик поддерживает `Clear-Item` командлет поставщика. Этот командлет позволяет пользователю удалить значение элемента в хранилище данных.

- Методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) определяют, как поставщик поддерживает `Get-Item` командлет поставщика. Этот командлет позволяет пользователю получать данные из хранилища данных.

- Методы [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) определяют, как поставщик поддерживает `Set-Item` командлет поставщика. Этот командлет позволяет пользователю обновлять значения элементов в хранилище данных.

- Методы [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) и [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс](/dotnet/api/system.management.automation.provider.itemcmdletprovider.invokedefaultactiondynamicparameters) определяют, как поставщик поддерживает `Invoke-Item` командлет поставщика. Этот командлет позволяет пользователю выполнить действие по умолчанию, заданное элементом.

- Методы [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) и [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистсдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) определяют, как поставщик поддерживает `Test-Path` командлет поставщика. Этот командлет позволяет пользователю определить, существуют ли все элементы пути.

В дополнение к методам, используемым для реализации командлетов поставщика, класс **System. Management. Automation. Provider. итемкмдлетпровидер** также определяет следующие методы:

- Метод [System. Management. Automation. Provider. итемкмдлетпровидер. експандпас](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ExpandPath) позволяет пользователю использовать подстановочные знаки при указании пути к поставщику.

- [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) используется, чтобы определить, является ли путь синтаксически и семантически допустимым для поставщика.

## <a name="container-enabled-providers"></a>Поставщики с поддержкой контейнеров

Поставщики с поддержкой контейнеров позволяют пользователю управлять элементами, которые являются контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Чтобы создать поставщик с поддержкой контейнеров, класс поставщика должен быть производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) или другого класса, производного от этого класса.

> [!IMPORTANT]
> Поставщики с поддержкой контейнеров не могут обращаться к хранилищам данных, содержащим вложенные контейнеры. Если дочерний элемент контейнера является другим контейнером, необходимо реализовать поставщик с поддержкой навигации.

Класс **System. Management. Automation. Provider. контаинеркмдлетпровидер** определяет следующие методы реализации конкретных командлетов поставщика. В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `CopyItem` метод для `Copy-Item` командлета, и при необходимости можно перезаписать второй метод, например `CopyItemDynamicParameters` , для добавления динамических параметров к командлету.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) определяют, как поставщик поддерживает `Copy-Item` командлет поставщика. Этот командлет позволяет пользователю копировать элемент из одного расположения в другое.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемсдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) определяют, как поставщик поддерживает `Get-ChildItem` командлет поставщика. Этот командлет позволяет пользователю получить дочерние элементы родительского элемента.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамесдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) определяют, как поставщик поддерживает `Get-ChildItem` командлет поставщика, если его `Name` параметр указан.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. NewItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. невитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) определяют, как поставщик поддерживает `New-Item` командлет поставщика. Этот командлет позволяет пользователю создавать новые элементы в хранилище данных.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) определяют, как поставщик поддерживает `Remove-Item` командлет поставщика. Этот командлет позволяет пользователю удалять элементы из хранилища данных.

- Методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) определяют, как поставщик поддерживает `Rename-Item` командлет поставщика. Этот командлет позволяет пользователю переименовывать элементы в хранилище данных.

В дополнение к методам, используемым для реализации командлетов поставщика, класс **System. Management. Automation. Provider. контаинеркмдлетпровидер** также определяет следующие методы:

- Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. хасчилдитемс](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) может использоваться классом поставщика для определения наличия у элемента дочерних элементов.

- Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. конвертпас](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.ConvertPath) может использоваться классом поставщика для создания нового пути, зависящего от поставщика, по указанному пути.

## <a name="navigation-enabled-providers"></a>Поставщики с поддержкой навигации

Поставщики с поддержкой навигации позволяют пользователю перемещать элементы в хранилище данных. Чтобы создать поставщик с поддержкой навигации, класс поставщика должен быть производным от класса [System. Management. Automation. Provider. NavigationCmdletProvider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

Класс **System. Management. Automation. Provider. NavigationCmdletProvider** определяет следующие методы реализации конкретных командлетов поставщика. В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `MoveItem` метод для `Move-Item` командлета, и при необходимости можно перезаписать второй метод, например `MoveItemDynamicParameters` , для добавления динамических параметров к командлету.

- Методы [System. Management. Automation. Provider. NavigationCmdletProvider. мовеитем](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) и [System. Management. Automation. Provider. NavigationCmdletProvider. мовеитемдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) определяют, как поставщик поддерживает `Move-Item` командлет поставщика. Этот командлет позволяет пользователю переместить элемент из одного места хранения в другое.

- Метод [System. Management. Automation. Provider. NavigationCmdletProvider. макепас](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) определяет, как поставщик поддерживает `Join-Path` командлет поставщика. Этот командлет позволяет пользователю объединять родительский и дочерний сегмент пути для создания внутреннего пути поставщика.

В дополнение к методам, используемым для реализации командлетов поставщика, класс **System. Management. Automation. Provider. NavigationCmdletProvider** также определяет следующие методы:

- Метод [System. Management. Automation. Provider. NavigationCmdletProvider. жетчилднаме](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) извлекает имя дочернего узла пути.

- Метод [System. Management. Automation. Provider. NavigationCmdletProvider. жетпарентпас](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) извлекает родительскую часть пути.

- Метод [System. Management. Automation. Provider. NavigationCmdletProvider. иситемконтаинер](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) определяет, является ли элемент контейнерным элементом. В этом контексте контейнер — это группа дочерних элементов в общем родительском элементе.

- Метод [System. Management. Automation. Provider. NavigationCmdletProvider. нормализерелативепас](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) Возвращает путь к элементу, который относится к указанному базовому пути.

## <a name="content-enabled-providers"></a>Поставщики с поддержкой содержимого

Поставщики с поддержкой содержимого позволяют пользователю очищать, получать или задавать содержимое элементов в хранилище данных.
Например, Поставщик FileSystem позволяет очищать, получать и устанавливать содержимое файлов в файловой системе. Чтобы создать поставщик с поддержкой содержимого, класс поставщика должен реализовать методы интерфейса [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .

Интерфейс **System. Management. Automation. Provider. иконтенткмдлетпровидер** определяет следующие методы реализации конкретных командлетов поставщика. В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `ClearContent` метод для `Clear-Content` командлета, и при необходимости можно перезаписать второй метод, например `ClearContentDynamicParameters` , для добавления динамических параметров к командлету.

- Методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) определяют, как поставщик поддерживает `Clear-Content` командлет поставщика. Этот командлет позволяет пользователю удалить содержимое элемента, не удаляя элемент.

- Методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) определяют, как поставщик поддерживает `Get-Content` командлет поставщика. Этот командлет позволяет пользователю получить содержимое элемента. `System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader`Метод возвращает интерфейс [System. Management. Automation. Provider. иконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentReader) , который определяет методы, используемые для чтения содержимого.

- Методы [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) и [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) определяют, как поставщик поддерживает `Set-Content` командлет поставщика. Этот командлет позволяет пользователю обновлять содержимое элемента. `System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter`Метод возвращает интерфейс [System. Management. Automation. Provider. иконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentWriter) , который определяет методы, используемые для записи содержимого.

## <a name="property-enabled-providers"></a>Поставщики с поддержкой свойств

Поставщики с поддержкой свойств позволяют пользователю управлять свойствами элементов в хранилище данных.
Чтобы создать поставщик с поддержкой свойств, класс поставщика должен реализовать методы интерфейсов [System. Management. Automation. Provider. ипропертикмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) . В большинстве случаев для поддержки командлета поставщика необходимо переписать метод, который вызывает обработчик PowerShell для вызова командлета, например `ClearProperty` метод для командлета Clear-Property, и при необходимости можно перезаписать второй метод, например `ClearPropertyDynamicParameters` , для добавления динамических параметров к командлету.

Интерфейс **System. Management. Automation. Provider. ипропертикмдлетпровидер** определяет следующие методы реализации конкретных командлетов поставщика:

- Методы [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) и [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) определяют, как поставщик поддерживает `Clear-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю удалить значение свойства.

- Методы [System. Management. Automation. Provider. ипропертикмдлетпровидер.](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) [ипропертикмдлетпровидер. жетпропертидинамикпараметерс и System. Management. Automation. Provider.](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) , определяющие, как поставщик поддерживает `Get-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю получить свойство элемента.

- Методы [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) и [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) определяют, как поставщик поддерживает `Set-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю обновлять свойства элемента.

  Интерфейс **System. Management. Automation. Provider. идинамикпропертикмдлетпровидер** определяет следующие методы реализации конкретных командлетов поставщика:

- Методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. копипроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. копипропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) определяют, как поставщик поддерживает `Copy-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю копировать свойство и его значение из одного расположения в другое.

- Методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. мовепроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. мовепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) определяют, как поставщик поддерживает `Move-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю переместить свойство и его значение из одного расположения в другое.

- Методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) определяют, как поставщик поддерживает `New-ItemProperty` командлет поставщика. Этот командлет позволяет пользователю создать новое свойство и задать его значение.

- Методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. RemoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ремовепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) определяют, как поставщик поддерживает этот `Remove-ItemProperty` командлет. Этот командлет позволяет пользователю удалить свойство и его значение.

- Методы [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепроперти](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) и [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепропертидинамикпараметерс](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) определяют, как поставщик поддерживает этот `Rename-ItemProperty` командлет. Этот командлет позволяет пользователю изменить имя свойства.

## <a name="see-also"></a>См. также раздел

[about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)

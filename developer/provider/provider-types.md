---
title: Типы поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523a8e1-42e4-4633-887f-fb74b3464561
caps.latest.revision: 12
ms.openlocfilehash: 37689571eb1650e5991af2e7002cd037ae99dd68
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057966"
---
# <a name="provider-types"></a>Типы поставщиков

Поставщики определить их базовую функциональность, изменив способ выполнения действий в командлетах поставщика (предоставляемое Windows PowerShell). Например, поставщики могут использовать функции по умолчанию `Get-Item` командлет, или же их можно изменить, как этот командлет работает при извлечении элементов из хранилища данных. Функциональные возможности поставщика, описанных в этом разделе включает функциональные возможности, определенные путем перезаписи методов из определенного поставщика базовые классы и интерфейсы.

> [!NOTE]
> Функции поставщика, предварительно определенные по Windows PowerShell, см. в разделе [возможностей поставщика](http://msdn.microsoft.com/en-us/864e4807-554a-4016-80ea-bf643a090fc6).

## <a name="drive-enabled-providers"></a>Диск с поддержкой поставщиков

Диск с поддержкой поставщиков укажите дисков по умолчанию, доступных для пользователя и пользователи могут добавлять или удалять диски. В большинстве случаев поставщики, диск с поддержкой поставщиков, так как они требуют некоторых диска по умолчанию доступ к хранилищу данных. Тем не менее при написании собственного поставщика может или не может потребоваться разрешить пользователю создавать и удалять диски.

Чтобы создать диск с поддержкой поставщика, ваш класс поставщика должен быть производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс или другой класс, производный от этого класса. [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс определяет следующие методы для развертывания дисков по умолчанию поставщика и поддержки `New-PSDrive` и `Remove-PSDrive` командлетов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `NewDrive` метод `New-PSDrive` командлет и при необходимости можно перезаписать второго метода, например `NewDriveDynamicParameters`, для добавления динамических параметров в командлет.

- [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) метода определяется по умолчанию диски, доступные для пользователя каждый раз, когда используется поставщик.

- [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) методы Определяет, как используемый поставщик поддерживает `New-PSDrive` командлетом поставщика. Этот командлет позволяет пользователю создавать диски для доступа к хранилищу данных.

- [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод определяет, как используемый поставщик поддерживает `Remove-PSDrive` командлетом поставщика. Этот командлет позволяет пользователю удалять диски из хранилища данных.

## <a name="item-enabled-providers"></a>Элемент с поддержкой поставщиков

Элемент с поддержкой поставщики разрешают пользователю получить, устанавливать или удалять элементы в хранилище данных. «Элемент» является элементом хранилища данных, в котором пользователь может получить доступ к или управлять независимо друг от друга. Создание поставщика с поддержкой элемента, ваш класс поставщика должен быть производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класс или другой класс, производный от этого класса.

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класс определяет следующие методы для реализации определенного поставщика командлетов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `ClearItem` метод `Clear-Item` командлет и при необходимости можно перезаписать второго метода, например `ClearItemDynamicParameters`, для добавления динамических параметров в командлет.

- [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) методы Определите, как используемый поставщик поддерживает `Clear-Item` командлетом поставщика. Этот командлет позволяет пользователю удалять значения элемента в хранилище данных.

- [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) методы определяют как ваш поставщик поддерживает `Get-Item` командлетом поставщика. Этот командлет позволяет пользователю получать данные из хранилища данных.

- [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) методы определяют как ваш поставщик поддерживает `Set-Item` командлетом поставщика. Этот командлет позволяет пользователю изменить значения элементов в хранилище данных.

- [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) и [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) методы Определите, как используемый поставщик поддерживает `Invoke-Item` командлетом поставщика. Этот командлет позволяет пользователю выполнять действие по умолчанию, заданному элементом.

- [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) и [System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) методы Определите, как используемый поставщик поддерживает `Test-Path` командлетом поставщика. Этот командлет позволяет пользователю определить, имеются ли все элементы пути.

  В дополнение к методам, используемый для реализации командлетов поставщика [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класс также определяет следующие методы:

- [System.Management.Automation.Provider.Itemcmdletprovider.Expandpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ExpandPath) метода позволяет использовать подстановочные знаки, при указании пути к поставщику.

- [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) используется для определения того, если путь является синтаксически и семантически допустимым для поставщика.

## <a name="container-enabled-providers"></a>Контейнер с поддержкой поставщиков

Контейнер с поддержкой поставщики разрешают пользователю управлять элементами, которые являются контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Создание поставщика с поддержкой контейнеров, ваш класс поставщика должен быть производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класс или другой класс, производный от этого класса.

> [!IMPORTANT]
> Контейнер с поддержкой поставщиков нет доступа к хранилищам данных, которые содержат вложенные контейнеры. Если дочерний элемент контейнера другой контейнер, необходимо реализовать поставщик поддержкой навигации.

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класс определяет следующие методы для реализации определенного поставщика командлетов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `CopyItem` метод `Copy-Item` командлет и при необходимости можно перезаписать второго метода, например `CopyItemDynamicParameters`, для добавления динамических параметров в командлет.

- [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) и [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) методы определяют, как используемый поставщик поддерживает `Copy-Item` командлетом поставщика. Этот командлет позволяет пользователю скопировать элемент из одного расположения в другое.

- [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) и [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) методы определяют, как используемый поставщик поддерживает `Get-ChildItem` командлетом поставщика. Этот командлет позволяет получить дочерние элементы родительского элемента.

- [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) и [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) методы определяют, как используемый поставщик поддерживает `Get-ChildItem` командлетом поставщика при его `Name` указан параметр.

- [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) и [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) методы определяют, как используемый поставщик поддерживает `New-Item` командлетом поставщика. Этот командлет позволяет пользователю создавать новые элементы в хранилище данных.

- [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) и [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) методы определяют, как используемый поставщик поддерживает `Remove-Item` командлетом поставщика. Этот командлет позволяет пользователю удалять элементы из хранилища данных.

- [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) и [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) методы определяют, как используемый поставщик поддерживает `Rename-Item` командлетом поставщика. Этот командлет позволяет переименовывать элементы в хранилище данных.

  В дополнение к методам, используемый для реализации командлетов поставщика [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класс также определяет следующие методы:

- [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) метод может использоваться с помощью класса поставщика для определения, имеет ли элемент дочерних элементов.

- [System.Management.Automation.Provider.Containercmdletprovider.Convertpath*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.ConvertPath) метод может использоваться с помощью класса поставщика для создания нового пути поставщика из указанного пути.

## <a name="navigation-enabled-providers"></a>Поставщики с поддержкой навигации

С поддержкой навигации поставщики разрешают пользователю перемещать элементы в хранилище данных. Создание поставщика с поддержкой навигации, ваш класс поставщика должен быть производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс определяет следующие методы для реализации определенного поставщика командлетов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `MoveItem` метод `Move-Item` командлет и при необходимости можно перезаписать второго метода, например `MoveItemDynamicParameters`, для добавления динамических параметров в командлет.

- [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) и [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) методы определяют, как используемый поставщик поддерживает `Move-Item` командлетом поставщика. Этот командлет позволяет пользователю на перемещение элемента из одного места в хранилище в другое расположение.

- [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод определяет, как используемый поставщик поддерживает `Join-Path` командлетом поставщика. Этот командлет позволяет пользователю для объединения родительских и дочерних сегмент пути для создания поставщика внутреннего пути.

  В дополнение к методам, используемый для реализации командлетов поставщика [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс также определяет следующие методы:

- [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) метод извлекает имя дочернего узла пути.

- [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) метод извлекает родительский часть пути.

- [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) метод определяет, является ли элемент контейнером. В этом контексте контейнер — это набор дочерних элементов в составе общего родительского элемента.

- [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) метод возвращает путь к элементу, вычисляемый относительно указанного базового пути.

## <a name="content-enabled-providers"></a>Поставщики содержимого с поддержкой

Поставщики содержимого с поддержкой разрешают пользователю очистить, получение или установка содержимого для элементов в хранилище данных. Например поставщик FileSystem позволяет очистить, получение и установка содержимого файлов в файловой системе. Для создания поставщика содержимого включен, ваш класс поставщика должен реализовывать методы [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.

[System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс определяет следующие методы для реализации определенного поставщика командлетов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `ClearContent` метод `Clear-Content` командлет и при необходимости можно перезаписать второго метода, например `ClearContentDynamicParameters`, для добавления динамических параметров в командлет.

- [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) и [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)методы определяют, как используемый поставщик поддерживает `Clear-Content` командлетом поставщика. Этот командлет позволяет пользователю удалять содержимое элемента без удаления элемента.

- [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) и [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) методы определяют, как используемый поставщик поддерживает `Get-Content` командлетом поставщика. Этот командлет позволяет пользователю для получения содержимого элемента. [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) возвращает [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) интерфейс, определяющий методы, используемые для чтения содержимого.

- [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) и [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) методы определяют, как используемый поставщик поддерживает `Set-Content` командлетом поставщика. Этот командлет позволяет пользователю изменить содержимое элемента. [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) возвращает [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) интерфейс, определяющий методы, используемые для записи содержимого.

## <a name="property-enabled-providers"></a>Свойство с поддержкой поставщиков

Свойство с поддержкой поставщики разрешают пользователю управлять свойств элементов в хранилище данных. Для создания поставщика свойство включено, ваш класс поставщика должен реализовывать методы [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) интерфейсов. В большинстве случаев для поддержки командлету поставщика необходимо перезаписать метод, который вызывается обработчиком Windows PowerShell для вызова командлета, такие как `ClearProperty` метод командлет Clear-свойство и при необходимости можно перезаписать второго метода, например `ClearPropertyDynamicParameters`, для добавления динамических параметров в командлет.

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) интерфейс определяет следующие методы для реализации определенного поставщика командлетов:

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) и [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `Clear-ItemProperty` командлетом поставщика. Этот командлет позволяет пользователю удалить значение свойства.

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) и [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)методы определяют, как используемый поставщик поддерживает `Get-ItemProperty` командлетом поставщика. Этот командлет позволяет получить значение свойства элемента.

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) и [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)методы определяют, как используемый поставщик поддерживает `Set-ItemProperty` командлетом поставщика. Этот командлет позволяет обновить свойства элемента.

  [System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) интерфейс определяет следующие методы для реализации определенного поставщика командлетов:

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `Copy-ItemProperty` командлетом поставщика. Этот командлет позволяет пользователю скопировать свойства и его значение из одного расположения в другое.

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `Move-ItemProperty` командлетом поставщика. Этот командлет позволяет пользователю перемещать свойство и его значение из одного расположения в другое.

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `New-ItemProperty` командлетом поставщика. Этот командлет позволяет создать новое свойство и присвойте ему значение.

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `Remove-ItemProperty` командлета. Этот командлет позволяет пользователю удалить свойство и его значение.

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) и [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) методы определяют, как используемый поставщик поддерживает `Rename-ItemProperty` командлета. Этот командлет позволяет пользователю изменять имя свойства.

## <a name="see-also"></a>См. также

[Разработка поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
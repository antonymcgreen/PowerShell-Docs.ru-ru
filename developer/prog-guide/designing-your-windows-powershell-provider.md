---
title: Разработка поставщика Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], designing
ms.assetid: 11d20319-cc40-4227-b810-4af33372b182
caps.latest.revision: 10
ms.openlocfilehash: 711a85e9b2eade7b9095d7560f53610e709e380a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081824"
---
# <a name="designing-your-windows-powershell-provider"></a>Разработка поставщика Windows PowerShell

Если ваш продукт или конфигурации предоставляет набор хранимых данных, таких как базы данных, пользователю будет необходимо просматривают следует реализовать поставщик Windows PowerShell. Кроме того Если ваш продукт предоставляет контейнер, даже если он не является контейнером многоуровневой, имеет смысл для реализации поставщика Windows PowerShell. Например может потребоваться реализовать поставщик контейнеров Windows PowerShell, если командлет команды копирования, перемещения, переименования, новых или удалить имеет смысл как операцию над данными вашей продукции или конфигурации.

## <a name="windows-powershell-paths-identify-your-provider"></a>Пути Windows PowerShell определить поставщика

Среда выполнения Windows PowerShell использует пути Windows PowerShell для доступа к соответствующего поставщика Windows PowerShell. Если командлет задает один из этих путей, среда выполнения знает, какой поставщик должен использоваться для доступа к хранилищу данных. Эти пути включения диска с указанием пути, поставщика с указанием пути, пути напрямую с поставщиками и поставщик внутреннего пути. Каждый поставщик Windows PowerShell должен поддерживать один или несколько из этих путей.

Дополнительные сведения о путях Windows PowerShell см. в разделе принципы работы Windows PowerShell.

### <a name="defining-a-drive-qualified-path"></a>Определении диска с указанием пути

Чтобы разрешить пользователю доступ к данным, расположенным на физический диск, поставщик Windows PowerShell должен поддерживать диск с указанием пути. Этот путь начинается с имени диска, за которым следует двоеточие (:), например, mydrive:\abc\bar.

### <a name="defining-a-provider-qualified-path"></a>Определение поставщика с указанием пути

Чтобы среда выполнения Windows PowerShell для инициализации и инициализации поставщика, поставщик Windows PowerShell должен поддерживать путь с указанием поставщика. Например, файловая система::\\\uncshare\abc\bar — это путь с указанием поставщик для Windows PowerShell, предоставляемые поставщиком filesystem.

### <a name="defining-a-provider-direct-path"></a>Определение пути поставщика Direct

Чтобы разрешить удаленный доступ к поставщику Windows PowerShell, должен поддерживать путь direct поставщика для передачи непосредственно поставщика Windows PowerShell для текущего расположения. Например, можно использовать поставщик реестра Windows PowerShell \\\server\regkeypath как путь напрямую с поставщиками.

### <a name="defining-a-provider-internal-path"></a>Определение внутреннего поставщика путь

Чтобы разрешить командлету поставщика доступа к данным с помощью отличных от Windows PowerShell прикладного программирования (API), поставщик Windows PowerShell должен поддерживать поставщик внутреннего пути. Этот путь, указанный после «::» в пути поставщика с указанием. Например, поставщик: внутренняя путь для поставщика filesystem Windows PowerShell является \\\uncshare\abc\bar.

## <a name="changing-stored-data"></a>Изменение хранимых данных

При переопределении методов, которые изменяют базового хранилища данных, всегда вызывать [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) метод с самую последнюю версию элемента изменено, метод. Инфраструктура поставщик определяет, если объект необходимо передать в конвейер, например при указании параметра - PassThru пользователем. Если извлечение последних элемента является дорогостоящей операцией (с точки), можно протестировать Context.PassThru свойство, определяющее, действительно необходимость написать итоговый элемент.

## <a name="choose-a-base-class-for-your-provider"></a>Выберите базовый класс для поставщика

Windows PowerShell предоставляет несколько базовых классов, которые можно использовать для реализации поставщика Windows PowerShell. При разработке поставщика, выбор базового класса, описанные в этом разделе, который наиболее подходит в соответствии с требованиями.

Каждый базовый класс поставщика Windows PowerShell делает доступными набор командлетов. В этом разделе описаны командлеты, но не приведены их параметры.

Используется состояние сеанса, среды выполнения Windows PowerShell доступны некоторые командлеты расположения для некоторых поставщиков Windows PowerShell, такие как `Get-Location`, `Set-Location`, `Pop-Location`, и `Push-Location` командлетов. Можно использовать `Get-Help` командлет для получения сведений об этих командлетах расположение.

### <a name="cmdletprovider-base-class"></a>CmdletProvider базовый класс

[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) класс определяет базовый поставщик Windows PowerShell. Этот класс поддерживает объявление поставщика и предоставляет ряд свойств и методов, которые доступны для всех поставщиков Windows PowerShell. Этот класс вызывается `Get-PSProvider` командлет, чтобы получить список всех доступных поставщиков для сеанса. Реализация этого командлета, предоставляемые состояние сеанса.

> [!NOTE]
> Поставщики Windows PowerShell доступны для всех областей языка Windows PowerShell.

### <a name="drivecmdletprovider-base-class"></a>DriveCmdletProvider базовый класс

[System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс определяет поставщик диск Windows PowerShell, который поддерживает операции для добавления новых дисков, удалив существующие диски и инициализация дисков по умолчанию. Например добавляемый поставщиком FileSystem Windows PowerShell, предоставляемые инициализирует дисков для всех томов, которые подключены, таких как жесткие диски и диски CD/DVD-устройства.

Этот класс является производным от [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) базового класса. В следующей таблице перечислены командлетов, предоставляемых этим классом. Кроме перечисленных `Get-PSDrive` командлет, (открытого по состоянию сеанса) является соответствующим командлет, который используется для получения доступных дисков.

|Командлет|Определение|
|------------|----------------|
|`New-PSDrive`|Создает новый диск для сеанса и выполняет потоковую передачу сведений о диске.|
|`Remove-PSDrive`|Удаляет диск из сеанса.|

### <a name="itemcmdletprovider-base-class"></a>ItemCmdletProvider базовый класс

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класс определяет поставщика элементов Windows PowerShell, который выполняет операции для каждого элемента в хранилище данных, и не используется любой контейнер или возможности навигации. Этот класс является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса. В следующей таблице перечислены командлетов, предоставляемых этим классом.

|Командлет|Определение|
|------------|----------------|
|`Clear-Item`|Очищает текущее содержимое элементов в указанном расположении и заменяет его значение «clear», указанное поставщиком. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Get-Item`|Извлекает элементы из указанного местоположения и отправляет результирующие объекты.|
|`Invoke-Item`|Вызывает действие по умолчанию для элемента по указанному пути.|
|`Set-Item`|Задает элемент в указанном расположении с помощью указанного значения. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Resolve-Path`|Разрешает подстановочные знаки для пути Windows PowerShell и сведения о пути потоков.|
|`Test-Path`|Проверяет для указанного пути и возвращает `true` если он существует и `false` в противном случае. Этот командлет применяется для поддержки `IsContainer` параметр для [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) метод.|

### <a name="containercmdletprovider-base-class"></a>ContainerCmdletProvider базовый класс

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класс определяет поставщик контейнеров Windows PowerShell, который предоставляет контейнер для элементов хранилища данных, для пользователя. Имейте в виду, что поставщик контейнеров Windows PowerShell может использоваться только в том случае, если имеется один контейнер (не вложенные контейнеры) с элементами в его. Если имеются вложенные контейнеры, необходимо реализовать поставщик навигации Windows PowerShell.

Этот класс является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) базового класса. В следующей таблице определены командлетов, реализованные этим классом.

|Командлет|Определение|
|------------|----------------|
|`Copy-Item`|Копирует элементы из одного расположения в другое. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Get-Childitem`|Извлекает дочерние элементы в указанном месте и передает их в виде объектов.|
|`New-Item`|Создает новые элементы в указанном месте и передает результирующий объект.|
|`Remove-Item`|Удаляет элементы из указанного расположения.|
|`Rename-Item`|Переименовывает элемент в указанном расположении. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|

### <a name="navigationcmdletprovider-base-class"></a>NavigationCmdletProvider базовый класс

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс определяет поставщик навигации Windows PowerShell, который выполняет операции для элементов, использующих несколько контейнеров. Этот класс является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) базового класса. В следующей таблице перечислены командлетов, предоставляемых этим классом.

|Командлет|Определение|
|------------|----------------|
|Объединение Path|Объединяет два пути в единый путь, используя поставщика в качестве разделителя пути. Этот командлет выполняет потоковую передачу строк.|
|`Move-Item`|Перемещение элементов в указанное расположение. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|

Связанные командлет является простой командлет синтаксического анализа пути, предоставляемые Windows PowerShell. Этот командлет можно использовать для синтаксического анализа пути Windows PowerShell для поддержки `Parent` параметра. Он выполняет потоковую передачу, путь к родительской строке.

## <a name="select-provider-interfaces-to-support"></a>Выберите интерфейсы поставщика в службу поддержки

В дополнение к производным от одного из базовых классов Windows PowerShell, поставщик Windows PowerShell может поддерживать другие функциональные возможности путем наследования из одной или нескольких из следующих интерфейсов поставщика. В этом разделе определяет эти интерфейсы и командлеты, поддерживаемые каждым. Он не описывает параметры для командлетов интерфейс поддерживается. Сведения о параметрах командлета доступна через Интернет с помощью `Get-Command` и `Get-Help` командлетов.

### <a name="icontentcmdletprovider"></a>IContentCmdletProvider

[System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс определяет поставщика содержимого, выполняющей операции над содержимым элемента данных. В следующей таблице перечислены командлеты, предоставляемые этим интерфейсом.

|Командлет|Определение|
|------------|----------------|
|`Add-Content`|Добавляет указанное значение длины содержимого указанного элемента. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Clear-Content`|Задает содержимое указанного элемента к значению «clear». Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Get-Content`|Извлекает указанные элементы и потоковую передачу результирующие объекты.|
|`Set-Content`|Заменяет существующее содержимое для указанных элементов. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|

### <a name="ipropertycmdletprovider"></a>IPropertyCmdletProvider

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) интерфейс определяет свойства поставщика Windows PowerShell, который выполняет операции со свойствами элементов в хранилище данных. В следующей таблице перечислены командлеты, предоставляемые этим интерфейсом.

> [!NOTE]
> `Path` По этим командлетам указывает путь к элементу, а не идентификации свойства.

|Командлет|Определение|
|------------|----------------|
|`Clear-ItemProperty`|Задает свойства указанных элементов значение «clear». Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Get-ItemProperty`|Извлекает свойства из указанного элемента и потоковую передачу результирующие объекты.|
|`Set-ItemProperty`|Задает свойства указанных элементов с указанного значения. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|

### <a name="idynamicpropertycmdletprovider"></a>IDynamicPropertyCmdletProvider

[System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) интерфейса, производного от [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider), определяет Поставщик, который указывает динамические параметры для его поддерживаемых командлетов. Этот тип поставщиков обрабатывает операции, для которых свойства могут быть определены во время выполнения, например, свойство операцию. Такие операции невозможны для элементов, которые статически после определения свойства. В следующей таблице перечислены командлеты, предоставляемые этим интерфейсом.

|Командлет|Определение|
|------------|----------------|
|`Copy-ItemProperty`|Копирует свойства из указанного элемента в другой элемент. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`Move-ItemProperty`|Перемещает свойство из указанного элемента в другой элемент. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|
|`New-ItemProperty`|Создает свойство для указанных элементов и потоковую передачу результирующие объекты.|
|`Remove-ItemProperty`|Удаляет свойство для указанных элементов.|
|`Rename-ItemProperty`|Переименовывает свойство указанные элементы. Этот командлет не передачи объекта выходных данных через конвейер, если его `PassThru` указан параметр.|

### <a name="isecuritydescriptorcmdletprovider"></a>ISecurityDescriptorCmdletProvider

[System.Management.Automation.Provider.Isecuritydescriptorcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ISecurityDescriptorCmdletProvider) интерфейс расширяет функциональные возможности дескриптора безопасности поставщика. Этот интерфейс позволяет пользователю получать и задавать данные дескриптора безопасности для элемента в хранилище данных. В следующей таблице перечислены командлеты, предоставляемые этим интерфейсом.

|Командлет|Определение|
|------------|----------------|
|`Get-Acl`|Извлекает сведения, содержащиеся в список управления доступом (ACL), который является частью дескриптора безопасности, используемый для защиты ресурсов операционной системы, например, файл или объект.|
|`Set-Acl`|Задает информацию для ACL. Он находится в форме экземпляра [System.Security.Accesscontrol.Objectsecurity](/dotnet/api/System.Security.AccessControl.ObjectSecurity) на эти элементы, предназначенные для указанного пути. Этот командлет можно задать сведения о файлах, разделов и подразделов в реестре или любого другого поставщика элемента, если поставщика Windows PowerShell поддерживает установку сведения о безопасности.|

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Как работает Windows PowerShell](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
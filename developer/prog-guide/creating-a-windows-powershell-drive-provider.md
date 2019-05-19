---
title: Создание поставщика Windows PowerShell диска | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.assetid: 2b446841-6616-4720-9ff8-50801d7576ed
caps.latest.revision: 6
ms.openlocfilehash: 2696d78cae7739310b7684161b597ce436dabe92
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855203"
---
# <a name="creating-a-windows-powershell-drive-provider"></a>Создание поставщика дисков Windows PowerShell

В этом разделе описывается создание поставщика диска Windows PowerShell, который предоставляет способ доступа к хранилищу данных через диск Windows PowerShell. Этот тип поставщиков также называется поставщики диск Windows PowerShell. На дисках Windows PowerShell, используемый поставщиком предоставляют средства для подключения к хранилищу данных.

Поставщик диск Windows PowerShell, описанные здесь предоставляет доступ к базе данных Microsoft Access. Для этого поставщика на диск Windows PowerShell представляет базу данных (это можно добавить любое количество дисков в поставщик диска), контейнеров верхнего уровня диска представления таблиц в базе данных и строки указывают элементы из контейнеров таблицы.

## <a name="defining-the-windows-powershell-provider-class"></a>Определение класса поставщика PowerShell Windows

Ваш поставщик диска необходимо определить класс .NET, который является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса. Ниже приведен в определении класса для этого поставщика диска.

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

Обратите внимание, что в этом примере [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут задает понятное имя для поставщика и специальной совместимости с Windows PowerShell, поставщик предоставляет доступ к среде выполнения Windows PowerShell во время обработки команды. Возможные значения для возможностей поставщика определяются [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. Этот диск поставщик не поддерживает эти возможности.

## <a name="defining-base-functionality"></a>Определение базовой функциональности

Как описано в разделе [разработки ваш поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс является производным от [ System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) базового класса, который определяет методы, необходимые для инициализации и Отмена инициализации поставщика. Чтобы реализовать функциональные возможности для добавления сведений инициализации сеанса, а также для освобождения ресурсов, которые используются поставщиком, см. в разделе [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Тем не менее большинство поставщиков (включая поставщика, описанные здесь) можно использовать реализацию по умолчанию эта функция, предоставляемая Windows PowerShell.

## <a name="creating-drive-state-information"></a>Создание сведений о состоянии дисков

Всеми поставщиками Windows PowerShell, считаются без отслеживания состояния, что означает, что ваш поставщик диска необходимо создать все сведения о состоянии, который необходим средой выполнения Windows PowerShell, при вызове поставщика.

Для этого поставщика диска сведения о состоянии включает соединение с базой данных, который хранится как часть сведений о диске. Ниже приведен код, который показывает, каким образом эти сведения хранятся в [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , описывающий диска:

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a>Создание диска

Чтобы среда выполнения Windows PowerShell для создания диска, диск поставщик должен реализовывать [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод. Следующий код показывает реализацию [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метода для данного поставщика диска:

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

Переопределение этого метода следует сделайте следующее:

- Убедитесь, что [System.Management.Automation.PSDriveinfo.Root*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) элемент существует и в хранилище данных можно установить соединение.

- Создание диска и заполнить элемент подключения поддержки `New-PSDrive` командлета.

- Проверка [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) объекта для предложенных диска.

- Изменить [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) объект, описывающий на диск с обязательным производительности или надежности сведения или установить дополнительные данные для вызывающих объектов, с помощью диска.

- Обработка ошибок с помощью [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод, а затем возвратить `null`.

  Этот метод возвращает либо сведениями о диске, переданный к методу или его версию поставщика.

## <a name="attaching-dynamic-parameters-to-newdrive"></a>Присоединение к NewDrive динамических параметров

`New-PSDrive` Командлета поддерживается поставщиком диска могут потребовать дополнительных параметров. Чтобы присоединить эти динамические параметры командлета, поставщик реализует [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) метод. Этот метод возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта.

Этот поставщик диска не Переопределите этот метод. Тем не менее приведенный ниже показана реализация по умолчанию этого метода:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a>Удаление диска

Чтобы закрыть подключение к базе данных, необходимо реализовать поставщика [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод. Этот метод закрывает соединение на диск после очистки любые сведения о поставщике.

Следующий код показывает реализацию [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метода для данного поставщика диска:

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

Если диск может быть удален, метод должен вернуть информацию, передаваемую методу через `drive` параметра. Если не удается удалить диск, метод должен записи исключение и затем возврата `null`. Если ваш поставщик не переопределять этот метод, реализация по умолчанию этот метод просто возвращает диск информацию, передаваемую в качестве входных данных.

## <a name="initializing-default-drives"></a>Инициализация по умолчанию диски

Пользовательский поставщик реализует диск [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) метод для подключения дисков. Например поставщик Active Directory может подключить диск для контекста именования, если компьютер присоединен к домену по умолчанию.

Этот метод возвращает коллекцию сведений о диске об инициализации дисков, или пустая коллекция. Вызов этого метода выполняется после вызова среды выполнения Windows PowerShell [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод для инициализации поставщика.

Этот поставщик диска не переопределяет [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) метод. Тем не менее в следующем коде показано реализации по умолчанию, которая возвращает коллекцию пустой диск:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a>О чем следует помнить о реализации InitializeDefaultDrives

Все поставщики диск следует подключать корневой диск, чтобы помочь пользователю с возможность обнаружения. В корне диска могут быть перечислены расположения, которые служат в качестве корневых элементов для других подключенных дисков. Например, создать поставщик Active Directory на диск, который перечисляет контексты именования в `namingContext` атрибуты в корне среды Distributed System (DSE). Это позволяет пользователям обнаруживать точки подключения для других дисков.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).

## <a name="testing-the-windows-powershell-drive-provider"></a>Проверка поставщика диск PowerShell в Windows

После регистрации поставщиком Windows PowerShell с помощью Windows PowerShell, можно проверить его, выполнив Поддерживаемые командлеты в командной строке, включая все командлеты, доступные через наследование. Давайте протестируем диска к образцу поставщика.

1. Запустите `Get-PSProvider` командлет, чтобы получить список поставщиков, чтобы убедиться, что поставщика AccessDB присутствует:

   **PS &GT; `Get-PSProvider`**

   Появляется следующий результат:

   ```output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. Убедитесь, что имя сервера базы данных (DSN) существует для базы данных, обратившись к **источников данных** часть **Администрирование** для операционной системы. В **DSN пользователя** таблицы, дважды щелкните **базы данных MS Access** и добавьте путь к диску C:\ps\northwind.mdb.

3. Создание нового диска с помощью диска к образцу поставщика:

   **PS > новый psdrive-name mydb-корневой c:\ps\northwind.mdb - psprovider AccessDb**

   Появляется следующий результат:

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. Проверка подключения. Так как соединение определяется как член диска, можно проверить с помощью командлета Get-PDDrive.

   > [!NOTE]
   > Пользователь еще не может взаимодействовать с поставщиком как диск, как поставщик должен функциональные возможности контейнеров, реализуемый. Дополнительные сведения см. в разделе [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).

   **PS > .connection (get-psdrive mydb)**

   Появляется следующий результат:

   ```output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. Удалите диск и выйдите из оболочки:

   **PS > remove-psdrive mydb**

   **PS > выйти из**

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Создание поставщика базовый Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)
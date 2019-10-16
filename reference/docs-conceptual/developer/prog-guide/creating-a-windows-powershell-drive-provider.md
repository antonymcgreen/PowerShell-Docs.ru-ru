---
title: Создание поставщика диска Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: 2e3d97e224b06bdf36ac0bc1237911e029ea762d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366833"
---
# <a name="creating-a-windows-powershell-drive-provider"></a>Создание поставщика дисков Windows PowerShell

В этом разделе описывается создание поставщика диска Windows PowerShell, предоставляющего способ доступа к хранилищу данных с помощью диска Windows PowerShell. Этот тип поставщика также называются поставщиками дисков Windows PowerShell. Диски Windows PowerShell, используемые поставщиком, предоставляют средства для подключения к хранилищу данных.

Поставщик диска Windows PowerShell, описанный здесь, предоставляет доступ к базе данных Microsoft Access. Для этого поставщика диск Windows PowerShell представляет базу данных (можно добавить любое количество дисков к поставщику накопителя), контейнеры верхнего уровня диска представляют таблицы в базе данных, а элементы контейнеров представляют строки в таблицы.

## <a name="defining-the-windows-powershell-provider-class"></a>Определение класса поставщика Windows PowerShell

Поставщик дисков должен определять класс .NET, производный от базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Ниже приведено определение класса для этого поставщика диска:

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

Обратите внимание, что в этом примере атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) указывает понятное имя поставщика и возможности Windows PowerShell, предоставляемые поставщиком в Windows. Среда выполнения PowerShell во время обработки команды. Возможные значения для возможностей поставщика определяются перечислением [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Этот поставщик дисков не поддерживает ни одну из этих возможностей.

## <a name="defining-base-functionality"></a>Определение базовых функций

Как описано в статье [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) является производным от базового класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) , который Определяет методы, необходимые для инициализации и деинициализации поставщика. Сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. в разделе [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Однако большинство поставщиков (включая описанный здесь поставщик) могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

## <a name="creating-drive-state-information"></a>Создание сведений о состоянии диска

Все поставщики Windows PowerShell считаются без отслеживания состояния. Это означает, что поставщику дисков необходимо создать все сведения о состоянии, необходимые среде выполнения Windows PowerShell при вызове поставщика.

Для этого поставщика дисков сведения о состоянии включают подключение к базе данных, которая хранится в составе сведений о диске. Ниже приведен код, который показывает, как эта информация хранится в объекте [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , описывающем диск:

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a>Создание диска

Чтобы разрешить среде выполнения Windows PowerShell создать диск, поставщик накопителя должен реализовать метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) . В следующем коде показана реализация метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для данного поставщика накопителя:

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

Переопределение этого метода должно выполнять следующие действия:

- Убедитесь, что член [System. Management. Automation. PSDriveinfo. root *](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) существует и что можно установить подключение к хранилищу данных.

- Создайте диск и заполните элемент Connection, чтобы обеспечить поддержку командлета `New-PSDrive`.

- Проверьте объект [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) для предложенного диска.

- Измените объект [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , который описывает диск с любой необходимой информацией о производительности или надежности, или предоставьте дополнительные данные для вызывающих объектов с помощью диска.

- Обработка сбоев с помощью метода [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) и возврата `null`.

  Этот метод возвращает либо сведения о диске, которые были переданы методу, либо зависящую от поставщика версию этого метода.

## <a name="attaching-dynamic-parameters-to-newdrive"></a>Присоединение динамических параметров к Невдриве

Для командлета `New-PSDrive`, поддерживаемого поставщиком дисков, могут потребоваться дополнительные параметры. Чтобы присоединить эти динамические параметры к командлету, поставщик реализует метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) . Этот метод возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Этот метод не переопределяется этим поставщиком диска. Однако следующий код демонстрирует реализацию этого метода по умолчанию:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a>Удаление диска

Чтобы закрыть подключение к базе данных, поставщик накопителя должен реализовать метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) . Этот метод закрывает подключение к диску после очистки сведений, относящихся к поставщику.

В следующем коде показана реализация метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для данного поставщика накопителя:

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

Если диск можно удалить, метод должен вернуть сведения, передаваемые в метод, с помощью параметра `drive`. Если диск не может быть удален, метод должен записать исключение, а затем вернуть `null`. Если поставщик не переопределяет этот метод, реализация по умолчанию этого метода просто возвращает сведения о диске, переданные в качестве входных данных.

## <a name="initializing-default-drives"></a>Инициализация дисков по умолчанию

Поставщик дисков реализует метод [System. Management. Automation. Provider. дривекмдлетпровидер. инитиализедефаултдривес *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) для подключения дисков. Например, поставщик Active Directory может подключить диск для контекста именования по умолчанию, если компьютер присоединен к домену.

Этот метод возвращает коллекцию сведений о инициализированных дисках или пустую коллекцию. Вызов этого метода выполняется после того, как среда выполнения Windows PowerShell вызывает метод [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) для инициализации поставщика.

Этот поставщик дисков не переопределяет метод [System. Management. Automation. Provider. дривекмдлетпровидер. инитиализедефаултдривес *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) . Однако в следующем коде показана реализация по умолчанию, которая возвращает пустую коллекцию Drive:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a>Вопросы, связанные с реализацией Инитиализедефаултдривес

Все поставщики дисков должны подключить корневой диск, чтобы помочь пользователю с его обнаружением. Корневой диск может иметь список расположений, которые служат корнями для других подключенных дисков. Например, поставщик Active Directory может создать диск, содержащий список контекстов именования, находящихся в атрибутах `namingContext` в корневой распределенной среде системы (DSE). Это помогает пользователям обнаружить точки подключения для других дисков.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).

## <a name="testing-the-windows-powershell-drive-provider"></a>Тестирование поставщика диска Windows PowerShell

Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно протестировать, запустив в командной строке поддерживаемые командлеты, включая все командлеты, доступные при наследовании. Давайте протестируем пример поставщика дисков.

1. Выполните командлет `Get-PSProvider`, чтобы получить список поставщиков, чтобы убедиться в наличии поставщика диска Акцессдб.

   **PS > `Get-PSProvider`**

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

2. Убедитесь, что имя сервера базы данных (DSN) существует для базы данных, путем доступа к части **данных** **средств администрирования** для операционной системы. В таблице **пользовательское имя пользователя** дважды щелкните **база данных MS Access** и добавьте путь к диску к:\пс\норсвинд.МДБ.

3. Создайте новый диск с помощью образца поставщика дисков:

   **PS > New-PSDrive-имя MyDB-root к:\пс\норсвинд.МДБ-psprovider Акцессдб**

   Появляется следующий результат:

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. Проверьте подключение. Так как подключение определено как член диска, его можно проверить с помощью командлета Get-Пддриве.

   > [!NOTE]
   > Пользователь еще не может взаимодействовать с поставщиком как диск, так как поставщику требуются функциональные возможности контейнера для этого взаимодействия. Дополнительные сведения см. [в разделе Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

   **> PS ("Get-PSDrive MyDB"). подключение**

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

5. Удалите диск и завершите работу оболочки:

   **> POWERSHELL Remove-PSDrive MyDB**

   **Выход > PS**

## <a name="see-also"></a>См. также:

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)

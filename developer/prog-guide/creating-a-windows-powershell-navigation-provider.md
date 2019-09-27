---
title: Создание поставщика навигации Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- navigation providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], navigation provider
ms.assetid: 8bd3224d-ca6f-4640-9464-cb4d9f4e13b1
caps.latest.revision: 5
ms.openlocfilehash: 10927381993d89e83fd9f7870138542eeb60fc59
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323401"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>Создание поставщика навигации Windows PowerShell

В этом разделе описывается создание поставщика навигации Windows PowerShell, который может перемещаться по хранилищу данных. Этот тип поставщика поддерживает рекурсивные команды, вложенные контейнеры и относительные пути.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider05.cs) для этого поставщика с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в  **\<примерах PowerShell >** Directory.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

Описываемый здесь поставщик позволяет пользователю обращаться к базе данных Access как диску, чтобы пользователь мог перейти к таблицам данных в базе данных. При создании собственного поставщика навигации можно реализовать методы, которые могут создавать пути к дискам, необходимые для навигации, нормализовать относительные пути, перемещать элементы хранилища данных, а также методы, которые получают дочерние имена, получают родительский путь к элементу и тест для выяснения, является ли элемент контейнером.

> [!CAUTION]
> Имейте в виду, что в этом проекте предполагается, что база данных имеет поле с ИДЕНТИФИКАТОРом Name, а тип поля — Лонгинтежер.

## <a name="define-the-windows-powershell-provider"></a>Определение поставщика Windows PowerShell

Поставщик навигации Windows PowerShell должен создать класс .NET, производный от базового класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Ниже приведено определение класса для поставщика навигации, описанного в этом разделе.

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L31-L32 "AccessDBProviderSample05.cs")]

Обратите внимание, что в этом поставщике атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) включает два параметра. Первый параметр задает понятное имя для поставщика, используемого Windows PowerShell. Второй параметр указывает специальные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Для этого поставщика не добавляются специальные возможности Windows PowerShell.

## <a name="defining-base-functionality"></a>Определение базовых функций

Как описано в разделе [проектирование поставщика PS](./designing-your-windows-powershell-provider.md), базовый класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) является производным от нескольких других классов, предоставилих различные функции поставщика. Следовательно, поставщик навигации Windows PowerShell должен определить все функциональные возможности, предоставляемые этими классами.

Сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. в разделе [Создание базового поставщика PS](./creating-a-basic-windows-powershell-provider.md). Однако большинство поставщиков (включая описанный здесь поставщик) могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

Чтобы получить доступ к хранилищу данных через диск Windows PowerShell, необходимо реализовать методы базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Чтобы управлять элементами хранилища данных, такими как получение, установка и очистка элементов, поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

Для получения дочерних элементов, их имен, хранилища данных, а также методов создания, копирования, переименования и удаления элементов необходимо реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

## <a name="creating-a-windows-powershell-path"></a>Создание пути Windows PowerShell

Поставщик навигации Windows PowerShell использует внутренний путь Windows PowerShell поставщика для навигации по элементам хранилища данных. Чтобы создать поставщик — внутренний путь, поставщик должен реализовать метод [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) для поддержки вызовов из командлета Combine-Path. Этот метод сочетает родительский и дочерний путь к внутреннему пути поставщика, используя разделитель пути, зависящий от поставщика, между родительским и дочерним путями.

Реализация по умолчанию принимает пути с символом "/\\" или "" в качестве разделителя пути, нормализует разделитель пути до\\"", объединяет родительские и дочерние части пути с разделителем между ними, а затем возвращает строку, содержащую Объединенные пути.

Этот метод не реализуется этим поставщиком навигации. Однако следующий код является реализацией метода [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>Вопросы, связанные с реализацией Макепас

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):

- Реализация метода [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) не должна проверять путь как допустимый полный путь в пространстве имен поставщика. Имейте в виду, что каждый параметр может представлять только часть пути, а Объединенные части могут не создавать полный путь. Например, метод [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) для поставщика FileSystem может получить "Windows\System32" в `parent` параметре и "ABC. `child` DLL" в параметре. Метод соединяет эти значения с разделителем "\\" и возвращает значение "windows\system32\abc.dll", которое не является полным путем к файловой системе.

  > [!IMPORTANT]
  > Части пути, предоставленные при вызове [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) , могут содержать символы, недопустимые в пространстве имен поставщика. Эти символы, скорее всего, используются для расширения подстановочных знаков, и реализация этого метода не должна удалять их.

## <a name="retrieving-the-parent-path"></a>Получение родительского пути

Поставщики навигации Windows PowerShell реализуют метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) для получения родительской части указанного полного или частичного пути, зависящего от поставщика. Метод удаляет дочернюю часть пути и возвращает часть родительского пути. `root` Параметр указывает полный путь к корню диска. Этот параметр может иметь значение null или быть пустым, если подключенный диск не используется для операции получения. Если указан корень, метод должен возвращать путь к контейнеру в том же дереве, что и корень.

Образец поставщика навигации не переопределяет этот метод, но использует реализацию по умолчанию. Он принимает пути, в которых используются разделители пути "\\/" и "". Сначала он нормализует путь, чтобы он имел только разделители "\\", а затем разбивает родительский путь на последний "\\" и возвращает родительский путь.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>Помните о реализации Жетпарентпас

Реализация метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) должна разбить путь на лексему пути для пространства имен поставщика. Например, Поставщик FileSystem использует этот метод для поиска последней "\\" и возвращает все, что находится слева от разделителя.

## <a name="retrieve-the-child-path-name"></a>Получение имени дочернего пути

Поставщик навигации реализует метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) для получения имени (конечного элемента) дочернего элемента, расположенного в указанном полном или частичном путь, зависящий от поставщика.

Образец поставщика навигации не переопределяет этот метод. Реализация по умолчанию показана ниже. Он принимает пути, в которых используются разделители пути "\\/" и "". Сначала он нормализует путь, чтобы он имел только разделители "\\", а затем разбивает родительский путь на последний "\\" и возвращает имя части дочернего пути.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>Вопросы, связанные с реализацией Жетчилднаме

Реализация метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) должна разбить путь на лексему пути. Если указанный путь не содержит разделителей пути, метод должен вернуть путь в неизмененном виде.

> [!IMPORTANT]
> Путь, указанный в вызове этого метода, может содержать символы, недопустимые в пространстве имен provider. Эти символы, скорее всего, используются для расширения подстановочных знаков или сопоставления регулярных выражений, и реализация этого метода не должна удалять их.

## <a name="determining-if-an-item-is-a-container"></a>Определение, является ли элемент контейнером

Поставщик навигации может реализовать метод [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) , чтобы определить, указывает ли указанный путь на контейнер. Он возвращает значение true, если путь представляет контейнер, и false в противном случае. Пользователю требуется этот метод, чтобы иметь возможность использовать `Test-Path` командлет для предоставленного пути.

В следующем коде показана реализация [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) в нашем примере поставщика навигации. Метод проверяет, правильно ли указан путь, и если таблица существует, и возвращает значение true, если путь указывает на контейнер.

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L847-L872 "AccessDBProviderSample05.cs")]

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>Вопросы, связанные с реализацией Иситемконтаинер

В классе навигации поставщика функций .NET могут объявляться возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В этом случае реализация [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) должна обеспечить соответствие пути требованиям. Для этого метод должен получить доступ к соответствующему свойству, например свойству [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .

## <a name="moving-an-item"></a>Перемещение элемента

При поддержке `Move-Item` командлета поставщик навигации реализует метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) . Этот метод перемещает элемент, заданный `path` параметром, в контейнер по пути, указанному `destination` в параметре.

Образец поставщика навигации не переопределяет метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) . Ниже приведена реализация по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>Вопросы, связанные с реализацией Мовеитем

В классе навигации поставщика функций .NET могут объявляться возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В этом случае реализация [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) должна обеспечивать соответствие пути требованиям. Для этого метод должен получить доступ к соответствующему свойству, например к свойству **кмдлетпровидер. Exclude** .

По умолчанию переопределения этого метода не должны перемещать объекты поверх существующих объектов, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Например, Поставщик FileSystem не будет копировать к:\темп\абк.ткст для существующего файла к:\бар.ткст, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь, указанный в `destination` параметре, существует и является контейнером, свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не является обязательным. В этом случае [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) должен переместить элемент, `path` указанный параметром, в `destination` контейнер, указанный параметром в качестве дочернего.

Реализация метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение до внесение любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в состояние системы, например при удалении файлов. [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные при определении что следует отображать пользователю.

После того как вызов метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) должен вызывать [ Метод System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение, чтобы разрешить отзыв, если операция должна быть продолжена. Поставщик должен вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) в качестве дополнительной проверки потенциально опасной модификации системы.

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>Присоединение динамических параметров к командлету Move-Item

`Move-Item` Иногда командлету требуются дополнительные параметры, которые динамически предоставляются во время выполнения. Чтобы предоставить эти динамические параметры, поставщик навигации должен реализовать метод [System. Management. автоматизации. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) для получения требуемых значений параметров из элемента в указанный путь и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Этот метод не реализуется этим поставщиком навигации. Однако следующий код является реализацией класса [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>Нормализация относительного пути

Поставщик навигации реализует метод [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) , чтобы нормализовать полный путь, указанный в `path` параметре, как относительный к элементу управления путь, `basePath` заданный параметром. Метод возвращает строковое представление нормализованного пути. Он записывает ошибку, `path` если параметр указывает несуществующий путь.

Образец поставщика навигации не переопределяет этот метод. Ниже приведена реализация по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>Вопросы, связанные с реализацией Нормализерелативепас

Ваша реализация [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) должна проанализировать `path` параметр, но не обязательно использовать чисто синтаксический синтаксический анализ. Рекомендуется разработать этот метод, чтобы использовать путь для поиска сведений о пути в хранилище данных и создать путь, соответствующий синтаксису регистра и стандартизованного пути.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Поставщик может добавлять элементы в существующие объекты или определять новые объекты. Дополнительные сведения см. в разделе[расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

Дополнительные сведения см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно протестировать, запустив в командной строке поддерживаемые командлеты, включая командлеты, доступные при наследовании. В этом примере проверяется пример поставщика навигации.

1. Запустите новую оболочку и используйте командлет `Set-Location` , чтобы указать путь к базе данных Access.

   ```powershell
   Set-Location mydb:
   ```

2. Теперь запустите `Get-Childitem` командлет, чтобы получить список элементов базы данных, которые являются доступными таблицами базы данных. Для каждой таблицы этот командлет также извлекает количество строк таблицы.

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. Повторно используйте `Set-Location` командлет, чтобы задать расположение таблицы данных Employees.

   ```powershell
   Set-Location Employees
   ```

4. Теперь мы используем `Get-Location` командлет для получения пути к таблице Employees.

   ```powershell
   Get-Location
   ```

   ```output
   Path
   ----
   mydb:\Employees
   ```

5. Теперь используйте `Get-Childitem` командлет `Format-Table` , переданный командлету. Этот набор командлетов извлекает элементы для таблицы данных Employees, которые являются строками таблицы. Они форматируются, как указано в `Format-Table` командлете.

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. Теперь можно запустить `Get-Item` командлет, чтобы получить элементы для строки 0 таблицы данных Employees.

   ```powershell
   Get-Item 0
   ```

   ```output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. Повторно используйте `Get-Item` командлет, чтобы получить данные о сотрудниках для элементов в строке 0.

   ```powershell
   (Get-Item 0).data
   ```

   ```output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Реализация контейнера Windows PowerShell provider](./creating-a-windows-powershell-container-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
---
title: Создание поставщика Windows PowerShell навигации | Документация Майкрософт
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
ms.openlocfilehash: 066aa188d5d7dfde5af424a3bb8f15ff51c1e936
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856960"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>Создание поставщика навигации Windows PowerShell

В этом разделе описывается, как создать поставщик навигации Windows PowerShell, можно перейти в хранилище данных. Этот тип поставщика поддерживает рекурсивной команды, вложенные контейнеры и относительные пути.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider05.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
> Вы можете скачать C# исходный файл (AccessDBSampleProvider05.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

Описанные здесь поставщик обеспечивает дескриптор пользователя базы данных Access как диск, таким образом, чтобы пользователь мог перейти к таблицам данных в базе данных. При создании собственного поставщика навигации, можно реализовать методы, которые можно сделать диск с указанием пути, необходимые для навигации, нормализовать относительные пути, перемещать элементы в хранилище данных, а также методы, которые получают имена дочерних, получить путь родительского элемента и тестирования Чтобы определить, если элемент является контейнером.

> [!CAUTION]
> Имейте в виду, что такой подход предполагает базу, которая содержит поле с именем Идентификатором и типом поля является LongInteger.

В следующем списке приведены разделы этой статьи. Если вы не знакомы с записью поставщик навигации Windows PowerShell, прочтите эти сведения, в том порядке, в котором она появляется. Тем не менее если вы знакомы с записью поставщик навигации Windows PowerShell, перейдите непосредственно к сведениям, вам потребуется.

- [Определение класса поставщика навигации PS](#Define-the-Windows-PowerShell-provider)

- [Определение базовой функциональности](#Defining-Base-Functionality)

- [Создание контура PS](#Creating-a-Windows-PowerShell-Path)

- [Получение родительского пути](#Retrieving-the-Parent-Path)

- [Получение имени дочерний путь](#Retrieve-the-Child-Path-Name)

- [Определение, является ли элемент контейнера](#Determining-if-an-Item-is-a-Container)

- [Перемещение элемента](#Moving-an-Item)

- [Присоединение динамических параметров в `Move-Item` командлета](#Attaching-Dynamic-Parameters-to-the-Move-Item-Cmdlet)

- [Нормализация относительный путь](#Normalizing-a-Relative-Path)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование](#Defining-Object-Types-and-Formatting)

- [Создание поставщика Windows PowerShell](#Building-the-Windows-PowerShell-provider)

- [Проверка поставщика в Windows PowerShell](#Testing-the-Windows-PowerShell-provider)

## <a name="define-the-windows-powershell-provider"></a>Определение поставщика Windows PowerShell

Поставщик навигации Windows PowerShell необходимо создать класс .NET, который является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) базового класса. Вот определение класса для поставщика навигации, описанные в этом разделе.

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L31-L32 "AccessDBProviderSample05.cs")]

Обратите внимание, что в этом поставщике [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут содержит два параметра. Первый параметр указывает понятное имя для поставщика, который используется Windows PowerShell. Второй параметр указывает специальной совместимости с Windows PowerShell, которые предоставляет поставщик среды выполнения Windows PowerShell во время обработки команды. Для этого поставщика нет конкретных возможности Windows PowerShell, которые добавляются.

## <a name="defining-base-functionality"></a>Определение базовой функциональности

Как описано в разделе [разработки ваш поставщик PS](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) базовый класс является производным от нескольких других классов для другого поставщика функциональные возможности. Поставщик навигации Windows PowerShell, поэтому необходимо определить все функциональные возможности, предоставляемые этими классами.

Чтобы реализовать функциональные возможности для добавления сведений инициализации сеанса, а также для освобождения ресурсов, которые используются поставщиком, см. в разделе [Создание базовый поставщик PS](./creating-a-basic-windows-powershell-provider.md). Тем не менее большинство поставщиков (включая поставщика, описанные здесь) можно использовать реализацию по умолчанию этой функции, предоставляемые Windows PowerShell.

Чтобы получить доступ к хранилищу данных через диск Windows PowerShell, необходимо реализовать методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Для работы с элементами в хранилище данных, например начало, параметр и очистка элементов, поставщик должен реализовывать методы, предоставленные [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md).

Чтобы получить дочерние элементы, или их имена, хранилище данных, а также способы создания, копирования, переименования и удаления элементов, необходимо реализовать методы, предоставленные [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).

## <a name="creating-a-windows-powershell-path"></a>Создание пути Windows PowerShell

Поставщик навигации Windows PowerShell используйте внутренний поставщик путь Windows PowerShell для перемещения элементов в хранилище данных. Для создания поставщика внутреннего пути поставщик должен реализовывать [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) вызывает метод для поддержки из командлета объединение-Path. Этот метод объединяет родительский и дочерний путь в поставщик внутреннего пути, используя разделитель пути поставщика между родительским и дочерним путями.

Реализация по умолчанию получает пути с «/» или "\\«как разделитель пути, нормализует разделитель пути для»\\«, объединяет части пути к родительским и дочерним с разделителем между ними, а затем возвращает строку, содержащую объединенные пути.

Этот поставщик навигации не реализует этот метод. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>О чем следует помнить о реализации MakePath

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):

- Реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод не следует проверить путь как юридические полный путь в пространстве имен поставщика. Имейте в виду, каждый параметр может представлять только часть пути, что объединенный частей может не создаваться, полный путь. Например [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод для поставщика filesystem может появиться «windows\system32» в `parent` параметр и «abc.dll» в `child` параметра. Метод объединяет эти значения с "\\" Разделитель "и" возвращает «windows\system32\abc.dll», не являющийся указания полного пути.

  > [!IMPORTANT]
  > Части пути, предоставленные в вызове [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) может содержать символы не допускаются в пространство имен поставщика. Эти символы чаще всего используются для подстановочных знаков и реализация этого метода не следует удалять их.

## <a name="retrieving-the-parent-path"></a>Получение родительского пути

Поставщики Windows PowerShell переходов реализуют [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) метод для извлечения родительского часть указанный полный или частичный путь от поставщика. Метод удаляет дочерний часть пути и возвращает путь в родительский объект. `root` Параметр указывает полный путь к корневому каталогу диска. Этот параметр может быть null или пусто, если не используется для операции по извлечению подключенного диска. Если корень указан, метод должен возвращать путь к контейнеру в качестве корневого элемента дерева.

Поставщик навигации пример переопределения этого метода, но использует реализацию по умолчанию. Он принимает пути, которые используются оба «/» и "\\" в качестве разделителей пути. Сначала он нормализует путь к только "\\" разделителей, затем разделяет родительский путь из системы последнего "\\" и возвращает путь к родительскому.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>Следует помнить о реализации GetParentPath

Реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) метод следует разбить путь лексически на разделитель пути для пространства имен поставщика. Например, поставщик filesystem использует этот метод для поиска последнего "\\" и возвращает все, что слева от разделителя.

## <a name="retrieve-the-child-path-name"></a>Получить имя пути дочерних

Пользовательский поставщик реализует навигации [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) метод для извлечения имени дочернего элемента (конечный элемент), расположенный в указанной полной или частичный путь от поставщика.

Пример поставщика навигации не Переопределите этот метод. Реализация по умолчанию. ниже. Он принимает пути, которые используются оба «/» и "\\" в качестве разделителей пути. Сначала он нормализует путь к только "\\" разделителей, затем разделяет родительский путь из системы последнего "\\" и возвращает имя дочернего элемента, часть пути.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>О чем следует помнить о реализации GetChildName

Реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) метод следует разбить путь лексически на разделитель пути. Если указанный путь содержит без разделителей пути, метод должен вернуть путь без изменений.

> [!IMPORTANT]
> Путь, указанный в вызове этого метода может содержать символы, недопустимые в пространство имен поставщика. Эти символы, скорее всего, используемых для подстановочных знаков или сопоставление регулярных выражений и реализация этого метода не следует удалять их.

## <a name="determining-if-an-item-is-a-container"></a>Определение, является ли элемент контейнера

Поставщик навигации может реализовать [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) метод, чтобы определить, если указанный путь контейнера. Она возвращает значение true, если путь представляет контейнер и false в противном случае. Пользователь должен иметь возможность использовать этот метод `Test-Path` командлет для предоставленного пути.

В следующем коде показан [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) реализацию в наш образец поставщика навигации. Метод проверяет правильность указанного пути, и если таблица существует и возвращает значение true, если путь указывает на контейнер.

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L847-L872 "AccessDBProviderSample05.cs")]

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>О чем следует помнить о реализации IsItemContainer

Поставщик навигации класс .NET может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этом случае реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) необходимо убедиться, что путь, переданный соответствует требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) свойство.

## <a name="moving-an-item"></a>Перемещение элемента

Поддержки `Move-Item` реализует поставщик навигации командлета, [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод. Этот метод перемещает элемент, заданный параметром `path` параметр контейнера по пути, предоставленного в `destination` параметра.

Пример поставщика навигации не переопределяет [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод. Ниже приводится реализация по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>О чем следует помнить о реализации MoveItem

Поставщик навигации класс .NET может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этом случае реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) необходимо убедиться, что путь, переданный соответствует требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, **CmdletProvider.Exclude** свойство.

По умолчанию переопределения этого метода не следует перемещать объекты через существующие объекты Если [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Например, поставщик filesystem не будет копировать c:\temp\abc.txt через существующий файл c:\bar.txt Если [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Если путь, указанный в `destination` параметр существует и является контейнером, [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойство не является обязательным. В этом случае [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) следует переместить элемент обозначается `path` параметр в контейнер обозначается `destination` параметр как дочерний элемент.

Реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при изменении состояния системы, например, удаление файлов. [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, необходимо изменить на пользователя, в среде выполнения Windows PowerShell, принимая во внимание любые параметры командной строки или привилегированных переменных в Определяет, что должно быть отображено пользователю.

После вызова [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение пользователю, чтобы разрешить отзыв, чтобы сказать, если операция должна быть продолжено. Поставщик должен вызывать [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) как дополнительную проверку для изменения потенциально опасных системы.

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>Присоединение динамических параметров в командлет Move-Item

Иногда `Move-Item` командлета требуется Дополнительные параметры, которые можно динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик навигации [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) метод для получения значения обязательных параметров из элемента в заданный путь и возвращают объект, имеющий свойства и поля с помощью синтаксического анализа атрибуты аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта.

Этот поставщик навигации не реализует этот метод. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>Нормализация относительный путь

Пользовательский поставщик реализует навигации [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) метод для нормализации полный путь, указанный в `path` параметр как относительно пути, указанному свойством `basePath` параметра. Метод возвращает строковое представление нормализованный путь. Записывает ошибку, если `path` параметр указывает несуществующий путь.

Пример поставщика навигации не Переопределите этот метод. Ниже приводится реализация по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>О чем следует помнить о реализации NormalizeRelativePath

Реализация [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) синтаксический анализ `path` параметр, но его не нужно использовать исключительно синтаксического анализа. Рекомендуется для разработки, что этот метод следует использовать путь для поиска сведения о пути в хранилище данных и создать путь, который соответствует регистр и стандартизированный синтаксис пути.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Это возможно для поставщика для добавления членов к существующим объектам или определения новых объектов. Дополнительные сведения см. в разделе[расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).
Это возможно для поставщика для добавления членов к существующим объектам или определения новых объектов. Дополнительные сведения см. в разделе[расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

Дополнительные сведения см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).
Дополнительные сведения см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Проверка поставщика в Windows PowerShell

После регистрации поставщиком Windows PowerShell с помощью Windows PowerShell, можно проверить его, выполнив Поддерживаемые командлеты в командной строке, включая командлеты, доступные через наследование. В этом примере тестирование навигации к образцу поставщика.

1. Запуска новой оболочки и использовать `Set-Location` командлет, чтобы задать путь для указания базы данных Access.

   ```powershell
   Set-Location mydb:
   ```

2. Теперь запустите `Get-Childitem` командлет, чтобы получить список элементов базы данных, которые являются таблицами базы данных. Для каждой таблицы этот командлет также извлекает количество строк таблицы.

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

3. Используйте `Set-Location` еще раз, чтобы задать расположение данных таблицы «Сотрудники».

   ```powershell
   Set-Location Employees
   ```

4. Давайте теперь используем `Get-Location` командлет, чтобы получить путь к таблице сотрудников.

   ```powershell
   Get-Location
   ```

   ```output
   Path
   ----
   mydb:\Employees
   ```

5. Теперь с помощью `Get-Childitem` командлет по конвейеру в `Format-Table` командлета. Этот набор командлетов извлекает элементы для таблицы данных сотрудников, которые являются строки таблицы. Они форматируются в соответствии со значениями `Format-Table` командлета.

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

6. Теперь вы можете запустить `Get-Item` командлет, чтобы получить элементы для строк 0 таблицы данных сотрудников.

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

7. Используйте `Get-Item` еще раз, чтобы получить данные о сотрудниках для элементов в строке 0.

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

[Поставщик разработки Your Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Реализация поставщика Windows PowerShell для контейнеров](./creating-a-windows-powershell-container-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
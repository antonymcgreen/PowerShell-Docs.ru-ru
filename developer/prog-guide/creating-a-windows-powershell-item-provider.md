---
title: Создание поставщика Windows PowerShell элемент | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], item provider
ms.assetid: a5a304ce-fc99-4a5b-a779-de7d85e031fe
caps.latest.revision: 6
ms.openlocfilehash: 6f91fd53d41dd72c99f8fbc7bc7b863322d88787
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855057"
---
# <a name="creating-a-windows-powershell-item-provider"></a>Создание поставщика элементов Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который может обрабатывать данные в хранилище данных. В этом разделе элементы данных в хранилище, рассматриваются как «элементы» данных хранения. Как следствие поставщик, который может обрабатывать данные в хранилище называется как поставщик элементов Windows PowerShell.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider03.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

Элемент поставщика Windows PowerShell, описанных в этом разделе получает элементы данных из базы данных Access. В этом случае «item» является либо таблицу в базе данных Access, либо строку в таблице.

## <a name="defining-the-windows-powershell-item-provider-class"></a>Определение класса поставщика Windows PowerShell элемента

Элемент поставщика Windows PowerShell необходимо определить класс .NET, который является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) базового класса. Ниже приведен в определении класса для поставщика элементов, описанных в этом разделе.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L34-L36 "AccessDBProviderSample03.cs")]

Обратите внимание, что в это определение класса [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут содержит два параметра. Первый параметр указывает понятное имя для поставщика, который используется Windows PowerShell. Второй параметр указывает специальной совместимости с Windows PowerShell, которые предоставляет поставщик среды выполнения Windows PowerShell во время обработки команды. Для этого поставщика существуют определенные возможности Windows PowerShell не добавлены.

## <a name="defining-base-functionality"></a>Определение базовой функциональности

Как описано в разделе [разработки ваш поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс является производным от несколько других классов, которые указаны в другой функциональные возможности поставщика. Элемент поставщика Windows PowerShell, таким образом, необходимо определить все функциональные возможности, предоставляемые этими классами.

Дополнительные сведения о том, как реализовать функциональность для добавления сведений инициализации сеанса, а также для освобождения ресурсов, используемый поставщиком, см. в разделе [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Тем не менее большинство поставщиков, включая поставщика, описанные здесь, можно использовать реализацию по умолчанию эта функция, предоставляемая Windows PowerShell.

Прежде чем элемент поставщика Windows PowerShell можно работать с позициями в хранилище, он должен реализовать методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базовый класс для доступа к хранилищу данных. Дополнительные сведения о реализации этого класса см. в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

## <a name="checking-for-path-validity"></a>Проверка допустимости пути

При поиске элемента данных, среда выполнения Windows PowerShell предоставляет путь Windows PowerShell поставщику, как определено в разделе «Основные понятия PSPath» [как Windows PowerShell работает](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58). Поставщик Windows PowerShell элемента необходимо проверить действительность синтаксические и семантические любого пути, передаваемый ему по реализации [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) метод. Этот метод возвращает `true` Если путь является допустимым, и `false` в противном случае. Быть виду, что реализация этого метода не нужно проверять наличие элемента в пути, но только что путь является синтаксически и семантически правильный.

Вот реализация [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) метода для данного поставщика. Обратите внимание на то, что эта реализация вызывает вспомогательный метод NormalizePath, чтобы преобразовать все разделители в пути универсального кода.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L274-L298 "AccessDBProviderSample03.cs")]

## <a name="determining-if-an-item-exists"></a>Определение наличия элемента

После проверки того, путь, среда выполнения Windows PowerShell необходимо определить, существует ли элемент данных по этому пути. Для поддержки этого типа запросов, реализующий поставщика элементов Windows PowerShell [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метод. Этот метод возвращает `true` найден элемент по указанному пути и `false` (по умолчанию) в противном случае.

Вот реализация [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метода для данного поставщика. Обратите внимание, что этот метод вызывает PathIsDrive ChunkPath и GetTable вспомогательные методы и использует поставщик определены DatabaseTableInfo объекта.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L229-L267 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-itemexists"></a>О чем следует помнить о реализации ItemExists

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists):

- При определении класса поставщика, элемент поставщика Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метода необходимо убедиться, что путь, переданный в метод требованиям указанные возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- Реализация этого метода должен обрабатывать доступ к элементу, может сделать элемент видимым для пользователя в любой форме. Например, если пользователь имеет доступ на запись в файл через поставщик FileSystem (указанного в Windows PowerShell), но не доступ на чтение, файл по-прежнему существует и [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) возвращает `true`. Реализация может потребоваться проверка родительского элемента, чтобы увидеть, если дочерний элемент может быть перечислимым.

## <a name="attaching-dynamic-parameters-to-the-test-path-cmdlet"></a>Присоединение динамических параметров в командлет Test-Path

Иногда `Test-Path` командлет, который вызывает [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) требуются дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров Windows PowerShell, необходимо реализовать поставщик элемента [System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Test-Path` командлета.

Этот элемент поставщик Windows PowerShell не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovideritemexistdynamicparameters](Msh_samplestestcmdlets#testprovideritemexistdynamicparameters)]  -->

## <a name="retrieving-an-item"></a>Извлечение элемента

Чтобы получить элемент, необходимо переопределить элемент поставщика Windows PowerShell [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод для поддержки вызовов из `Get-Item` командлета. Этот метод записывает элемента с помощью [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) метод.

Вот реализация [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метода для данного поставщика. Обратите внимание на то, что этот метод использует GetTable и GetRow вспомогательные методы для получения элементов, которые являются либо таблиц в базе данных Access или строк в таблице данных.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L132-L163 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-getitem"></a>О чем следует помнить о реализации GetItem

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem):

- При определении класса поставщика, элемент поставщика Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) необходимо убедиться, что путь, переданный в метод соответствует этим требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не должен извлекать объекты, которые обычно скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Например [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод для проверки поставщика FileSystem [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойства, прежде чем он пытается вызвать [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) скрытых или системных файлов.

## <a name="attaching-dynamic-parameters-to-the-get-item-cmdlet"></a>Присоединение динамических параметров в командлет Get-Item

Иногда `Get-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров Windows PowerShell, необходимо реализовать поставщик элемента [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Get-Item` командлета.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetitemdynamicparameters](Msh_samplestestcmdlets#testprovidergetitemdynamicparameters)]  -->

## <a name="setting-an-item"></a>Задание элемента

Чтобы задать элемент, необходимо переопределить элемент поставщика Windows PowerShell [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод для поддержки вызовов из `Set-Item` командлета. Этот метод задает значение элемента по указанному пути.

Этот поставщик не поддерживает переопределение для [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод. Тем не менее ниже приведен пример реализации этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitem](Msh_samplestestcmdlets#testprovidersetitem)]  -->

#### <a name="things-to-remember-about-implementing-setitem"></a>О чем следует помнить о реализации SetItem

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem):

- При определении класса поставщика, элемент поставщика Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) необходимо убедиться, что путь, переданный в метод соответствует этим требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует задать или записи объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны отправляться [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод, если путь представляет скрытый элемент и [ System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

- Реализация [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при внесении изменений в хранилище данных, например, удаление файлов. [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) метод отправляет имя ресурса, чтобы изменить для пользователя, с помощью среды выполнения Windows PowerShell, принимая во внимание параметры командной строки или привилегированные переменные для определения того, что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение пользователю, чтобы разрешить обратной связи для проверки, если операция должна быть продолжено. Вызов [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку для изменения потенциально опасных системы.

## <a name="retrieving-dynamic-parameters-for-setitem"></a>Получение динамических параметров SetItem

Иногда `Set-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров Windows PowerShell, необходимо реализовать поставщик элемента [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Set-Item` командлета.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitemdynamicparameters](Msh_samplestestcmdlets#testprovidersetitemdynamicparameters)]  -->

## <a name="clearing-an-item"></a>Удаление элемента

Чтобы удалить элемент, реализующий поставщика элементов Windows PowerShell [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) метод для поддержки вызовов из `Clear-Item` командлета. Этот метод удаляет элемент данных по указанному пути.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitem](Msh_samplestestcmdlets#testproviderclearitem)]  -->

#### <a name="things-to-remember-about-implementing-clearitem"></a>О чем следует помнить о реализации ClearItem

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem):

- При определении класса поставщика, элемент поставщика Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) необходимо убедиться, что путь, переданный в метод соответствует этим требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует задать или записи объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны отправляться [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод, если путь представляет элемент, который является скрытым от пользователя и [ System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

- Реализация [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при внесении изменений в хранилище данных, например, удаление файлов. [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) метод отправляет имя ресурса изменить для пользователя со средой выполнения Windows PowerShell и обрабатывать любые параметры командной строки или предпочтений переменные для определения того, что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение пользователю, чтобы разрешить обратной связи для проверки, если операция должна быть продолжено. Вызов [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку для изменения потенциально опасных системы.

## <a name="retrieve-dynamic-parameters-for-clearitem"></a>Получить динамические параметры для ClearItem

Иногда `Clear-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров Windows PowerShell, необходимо реализовать поставщик элемента [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Clear-Item` командлета.

Этот элемент поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitemdynamicparameters](Msh_samplestestcmdlets#testproviderclearitemdynamicparameters)]  -->

## <a name="performing-a-default-action-for-an-item"></a>Выполняет действие по умолчанию для элемента

Поставщик элемента Windows PowerShell может реализовать [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) метод для поддержки вызовов из `Invoke-Item` командлет, который позволяет поставщику для выполните действия по умолчанию для элемента по указанному пути. Например, поставщик FileSystem может этот метод позволяет вызывают ShellExecute для конкретного элемента.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultaction](Msh_samplestestcmdlets#testproviderinvokedefaultaction)]  -->

#### <a name="things-to-remember-about-implementing-invokedefaultaction"></a>О чем следует помнить о реализации InvokeDefaultAction

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction):

- При определении класса поставщика, элемент поставщика Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) необходимо убедиться, что путь, переданный в метод соответствует этим требованиям. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует задать или записи объектов, скрытые от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны отправляться [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод, если путь представляет элемент, который является скрытым от пользователя и [ System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

## <a name="retrieve-dynamic-parameters-for-invokedefaultaction"></a>Получить динамические параметры для InvokeDefaultAction

Иногда `Invoke-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров Windows PowerShell, необходимо реализовать поставщик элемента [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления динамических параметров в `Invoke-Item` командлета.

Этот элемент поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters](Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters)]  -->

## <a name="implementing-helper-methods-and-classes"></a>Реализация вспомогательные методы и классы

Этот элемент поставщик реализует несколько вспомогательных методов и классы, используемые в общественном переопределения методов, определенных для Windows PowerShell. Код этих вспомогательных методов и классов отображаются в [пример кода](#code-sample) раздел.

### <a name="normalizepath-method"></a>Метод NormalizePath

Этот элемент поставщик реализует NormalizePath вспомогательный метод, чтобы обеспечить согласованный формат пути. Формат, указанный обратная косая черта (\\) в качестве разделителя.

### <a name="pathisdrive-method"></a>Метод PathIsDrive

Этот элемент поставщик реализует PathIsDrive вспомогательный метод для определения того, является ли указанный путь фактически имя диска.

### <a name="chunkpath-method"></a>Метод ChunkPath

Этот элемент поставщик реализует ChunkPath вспомогательный метод, который разбивает по указанному пути, чтобы поставщик может идентифицировать его отдельные элементы. Он возвращает массив, состоящий из элементов пути.

### <a name="gettable-method"></a>Методом getTable

Этот элемент поставщик реализует GetTables вспомогательный метод, возвращающий объект DatabaseTableInfo, представляющий сведения о таблице, указанной в вызове.

### <a name="getrow-method"></a>Метод GetRow

[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод поставщика элемента вызывает вспомогательный метод GetRows. Этот вспомогательный метод возвращает объект DatabaseRowInfo, который представляет сведения о заданной строки в таблице.

### <a name="databasetableinfo-class"></a>Класс DatabaseTableInfo

Этот поставщик элемента определяет DatabaseTableInfo класс, который представляет коллекцию данных в таблицу данных в базе данных. Этот класс аналогичен [System.IO.Directoryinfo](/dotnet/api/System.IO.DirectoryInfo) класса.

Элемент образца поставщика определяет DatabaseTableInfo.GetTables метод, возвращающий коллекцию объектов сведения таблицы определение таблицы в базе данных. Этот метод содержит блок try/catch, чтобы убедиться, что любая ошибка базы данных отображается как строка ноль элементов.

### <a name="databaserowinfo-class"></a>Класс DatabaseRowInfo

Этот поставщик элемента определяет вспомогательный класс DatabaseRowInfo, который представляет строку в таблице базы данных. Этот класс аналогичен [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo) класса.

Образец поставщика определяет метод DatabaseRowInfo.GetRows для возврата коллекции объектов сведения строки для указанной таблицы. Этот метод содержит блок try/catch для перехвата исключений. Все ошибки приведет к нет сведений о строке.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample03](./accessdbprovidersample03-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

При написании поставщика, может потребоваться добавление членов в существующие объекты или определение новых объектов. После завершения создания файла типов, Windows PowerShell можно использовать для идентификации членов объекта и файла форматирования, определяющий способ отображения объекта. Дополнительные сведения о см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. в разделе [регистрация командлетов, поставщиков и размещения приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Проверка поставщика в Windows PowerShell

Когда этот элемент поставщик Windows PowerShell регистрируется с помощью Windows PowerShell, можно протестировать базовый и только диска функциональные возможности поставщика. Чтобы протестировать манипуляции элементов, необходимо также реализовать контейнера функций, описанных в [реализация поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Your Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Как работает Windows PowerShell](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Создание поставщика Windows PowerShell для контейнеров](./creating-a-windows-powershell-container-provider.md)

[Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)
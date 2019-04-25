---
title: Создание контейнера поставщика Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], container provider
- container providers [PowerShell Programmer's Guide]
ms.assetid: a7926647-0d18-45b2-967e-b31f92004bc4
caps.latest.revision: 5
ms.openlocfilehash: 33effed9a96cf1b9ee5f1a50b60a1937526db9d1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081909"
---
# <a name="creating-a-windows-powershell-container-provider"></a>Создание поставщика контейнеров Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, которая может работать в хранилищах данных многоуровневой. Для этого типа хранилища данных верхнем уровне хранилища содержит корневых элементов, и каждый последующий уровень называется узлом дочерних элементов. Позволяя пользователям работать на эти дочерние узлы, пользователь может иерархически взаимодействовать через хранилище данных.

Поставщики, которые могут работать в хранилищах многоуровневыми данными, называются контейнера поставщиков Windows PowerShell. Однако имейте в виду, что поставщик контейнеров Windows PowerShell может использоваться только в том случае, если имеется один контейнер (не вложенные контейнеры) с элементами в его. Если имеются вложенные контейнеры, необходимо реализовать поставщик навигации Windows PowerShell. Дополнительные сведения о реализации поставщик навигации Windows PowerShell см. в разделе [Создание поставщика Windows PowerShell навигации](./creating-a-windows-powershell-navigation-provider.md).

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider04.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

Поставщик контейнеров Windows PowerShell, описанные здесь определяет базу данных в качестве ее единый контейнер, в таблицах и строках базы данных, определяемый как элементы контейнера.

> [!CAUTION]
> Имейте в виду, что такой подход предполагает базу, которая содержит поле с именем Идентификатором и типом поля является LongInteger.

Ниже приведен список разделов этой статьи. Если вы не знакомы с разработка контейнера поставщика Windows PowerShell, прочтите эту информацию в порядке, в котором он отображается. Тем не менее если вы знакомы с разработка контейнера поставщика Windows PowerShell, перейдите непосредственно к сведениям, вам потребуется.

- [Определение класса поставщика контейнера Windows PowerShell](#Defining-a-Windows-PowerShell-Container-Provider-Class)

- [Определение базовой функциональности](#defining-base-functionality)

- [Получение дочерних элементов](#Retrieving-Child-Items)

- [Присоединение динамических параметров в `Get-ChildItem` командлета](#Attaching-Dynamic-Parameters-to-the-Get-ChildItem-Cmdlet)

- [Получение имен дочерних элементов](#Retrieving-Child-Item-Names)

- [Присоединение динамических параметров в `Get-ChildItem` командлет (имя)](#Attaching-Dynamic-Parameters-to-the-Get-ChildItem-Cmdlet-(Name))

- [Переименование элементов](#Renaming-Items)

- [Присоединение динамических параметров в `Rename-Item` командлета](#Attaching-Dynamic-Parameters-to-the-Rename-Item-Cmdlet)

- [Создание новых элементов](#Creating-New-Items)

- [Присоединение динамических параметров в `New-Item` командлета](#Attaching-Dynamic-Parameters-to-the-New-Item-Cmdlet)

- [Удаление элементов](#Removing-Items)

- [Присоединение динамических параметров в `Remove-Item` командлета](#Attaching-Dynamic-Parameters-to-the-Remove-Item-Cmdlet)

- [Запрос для дочерних элементов](#Querying-for-Child-Items)

- [Копирование элементов](#Copying-Items)

- [Присоединение динамических параметров в `Copy-Item` командлета](#Attaching-Dynamic-Parameters-to-the-Copy-Item-Cmdlet)

- [Пример кода](#Code-Sample)

- [Создание поставщика Windows PowerShell](#Building-the-Windows-PowerShell-Provider)

- [Проверка поставщика в Windows PowerShell](#Testing-the-Windows-PowerShell-Provider)

## <a name="defining-a-windows-powershell-container-provider-class"></a>Определение класса поставщика контейнера Windows PowerShell

Поставщик контейнеров Windows PowerShell необходимо определить класс .NET, который является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) базового класса. Вот определение класса для поставщика контейнера Windows PowerShell, описанные в этом разделе.

```csharp
   [CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : ContainerCmdletProvider
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L34-L35 "AccessDBProviderSample04.cs")]

Обратите внимание, что в это определение класса [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут содержит два параметра. Первый параметр указывает понятное имя для поставщика, который используется Windows PowerShell. Второй параметр указывает специальной совместимости с Windows PowerShell, которые предоставляет поставщик среды выполнения Windows PowerShell во время обработки команды. Для этого поставщика нет конкретных возможности Windows PowerShell, которые добавляются.

## <a name="defining-base-functionality"></a>Определение базовой функциональности

Как описано в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класс является производным от несколько других классов, которые предоставлены функциональные возможности другого поставщика. Поставщик контейнеров Windows PowerShell, таким образом, необходимо определить все функциональные возможности, предоставляемые этими классами.

Чтобы реализовать функциональные возможности для добавления сведений инициализации сеанса, а также для освобождения ресурсов, которые используются поставщиком, см. в разделе [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Тем не менее большинство поставщиков (включая поставщика, описанные здесь) можно использовать реализацию по умолчанию эта функция, предоставляемая Windows PowerShell.

Чтобы получить доступ к хранилищу данных, поставщик должен реализовывать методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Для работы с элементами в хранилище данных, например начало, параметр и очистка элементов, поставщик должен реализовывать методы, предоставленные [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md).

## <a name="retrieving-child-items"></a>Получение дочерних элементов

Для получения дочернего элемента, поставщик контейнеров Windows PowerShell необходимо переопределить [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод для поддержки вызовов из `Get-ChildItem` командлета. Этот метод извлекает дочерние элементы из хранилища данных и записывает их в конвейер, как объекты. Если `recurse` указан параметр командлета, этот метод извлекает все дочерние элементы, независимо от того, какой уровень, они состоятся. Если `recurse` параметр не указан, этот метод извлекает только один уровень дочерних элементов.

Вот реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метода для данного поставщика. Обратите внимание на то, что этот метод получает дочерние элементы во всех таблицах базы данных, когда путь указывает базы данных Access, а также получает дочерние элементы из строки этой таблицы, если путь указывает на таблицу данных.

```csharp
protected override void GetChildItems(string path, bool recurse)
{
    // If path represented is a drive then the children in the path are
    // tables. Hence all tables in the drive represented will have to be
    // returned
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table, path, true);

            // if the specified item exists and recurse has been set then
            // all child items within it have to be obtained as well
            if (ItemExists(path) && recurse)
            {
                GetChildItems(path + pathSeparator + table.Name, recurse);
            }
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get the table name, row number and type of path from the
        // path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Obtain all the rows within the table
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);
            WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
        }
        else
        {
            // In this case, the path specified is not valid
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L311-L362 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchilditems"></a>О чем следует помнить о реализации GetChildItems

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- При определении класса поставщика, поставщик контейнеров Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- Реализация этого метода должна быть учтена в любой форме доступ к элементу, может сделать элемент видимым для пользователя. Например, если пользователь имеет доступ на запись в файл через поставщик FileSystem (указанного в Windows PowerShell), но не доступ на чтение, файл по-прежнему существует и [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) возвращает `true`. Реализация может потребоваться проверка параметров родительского элемента, чтобы увидеть, могут быть перечислены дочерние.

- При написании несколько элементов, [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод может занять некоторое время. Можно спроектировать ваш поставщик нужно записать элементы с помощью [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) метод одной за раз. При использовании этого метода будет представлять элементы для пользователя в потоке.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) отвечает за Предотвращение бесконечной рекурсии, при наличии циклических ссылок и т.п. Завершающий соответствующее исключение должно вызываться для отражения таких условий.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a>Присоединение динамических параметров в командлет Get-ChildItem

Иногда `Get-ChildItem` командлет, который вызывает [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) требуются дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Get-ChildItem` командлета.

Этот поставщик контейнеров Windows PowerShell не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a>Получение имен дочерних элементов

Чтобы получить имена дочерних элементов, необходимо переопределить поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) метод для поддержки вызовов из `Get-ChildItem`командлет при его `Name` указан параметр. Этот метод извлекает имена дочерних элементов для указанных имен путь или дочернего элемента для всех контейнеров, если `returnAllContainers` указан параметр командлета. Имя дочернего приведен фрагмент конечного пути. Например «abc.dll» имеет имя дочернего c:\windows\system32\abc.dll путь. Дочерний каталог c:\windows\system32 называется «system32».

Вот реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) метода для данного поставщика. Обратите внимание на то, что этот метод извлекает имена таблиц, если указанный путь указывает базы данных Access (диск) и номера строк, если путь указывает на таблицу.

```csharp
protected override void GetChildNames(string path,
                            ReturnContainers returnContainers)
{
    // If the path represented is a drive, then the child items are
    // tables. get the names of all the tables in the drive.
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table.Name, path, true);
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get type, table name and row number from path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Get all the rows in the table and then write out the
            // row numbers.
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row.RowNumber, path, false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);

            WriteItemObject(row.RowNumber, path, false);
        }
        else
        {
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildNames
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L369-L411 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-getchildnames"></a>О чем следует помнить о реализации GetChildNames

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- При определении класса поставщика, поставщик контейнеров Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

  > [!NOTE]
  > Исключение этого правила возникает, когда `returnAllContainers` указан параметр командлета. В этом случае метод должен получать любое имя дочернего контейнера, даже если он не соответствует значения [System.Management.Automation.Provider.Cmdletprovider.Filter*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter), [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include), или [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) свойства.

- По умолчанию переопределения этого метода не должен извлекать имена объектов, которые обычно скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) указано свойство. Если указанный путь указывает на контейнер, [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойство не является обязательным.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) отвечает за Предотвращение бесконечной рекурсии, при наличии циклических ссылок и т.п. Завершающий соответствующее исключение должно вызываться для отражения таких условий.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a>Присоединение динамических параметров в командлет Get-ChildItem (имя)

Иногда `Get-ChildItem` командлета (с `Name` параметр) требуются дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Get-ChildItem` командлета.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a>Переименование элементов

Чтобы переименовать элемент, необходимо переопределить поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод для поддержки вызовов из `Rename-Item` командлета. Этот метод изменяет имя элемента по указанному пути к предоставлен новое имя. Новое имя всегда должен быть относительно родительского элемента (контейнер).

Этот поставщик не переопределяет [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод. Тем не менее ниже приведен пример реализации по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a>О чем следует помнить о реализации RenameItem

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):

- При определении класса поставщика, поставщик контейнеров Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод предназначен для изменения имени только элемент, а не для операции перемещения. Реализация метода следует писать ошибку, если `newName` содержит разделители путей или иначе могут привести к записи родительского расположения.

- По умолчанию переопределения этого метода нельзя переименовывать объекты Если [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) указано свойство. Если указанный путь указывает на контейнер, [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойство не является обязательным.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при изменении состояния системы, например, переименование файлов. [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, необходимо изменить на пользователя, в среде выполнения Windows PowerShell, принимая во внимание любые параметры командной строки или привилегированных переменных в Определяет, что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение с подтверждением сообщение пользователю, чтобы разрешить дополнительный отзыв сказать, если операция должна быть продолжено. Поставщик должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) как дополнительную проверку для изменения потенциально опасных системы.

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a>Присоединение динамических параметров в командлет Rename-Item

Иногда `Rename-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) метод. Этот метод извлекает параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Rename-Item` командлета.

Этот контейнер поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a>Создание новых элементов

Чтобы создать новые элементы, должен реализовывать поставщик контейнера [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод для поддержки вызовов из `New-Item` командлета. Этот метод создает элемент данных, расположенный по указанному пути. `type` Параметр командлета содержит тип определяемых поставщиком для нового элемента. Например, используется поставщик FileSystem `type` параметр со значением «файл» или «каталог». `newItemValue` Параметр командлета указывает значение от поставщика для нового элемента.

Вот реализация [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метода для данного поставщика.

```csharp
protected override void NewItem( string path, string type,
                                 object newItemValue )
{
    // Create the new item here after
    // performing necessary validations
    //
    // WriteItemObject(newItemValue, path, false);

    // Example
    //
    // if (ShouldProcess(path, "new item"))
    // {
    //      // Create a new item and then call WriteObject
    //      WriteObject(newItemValue, path, false);
    // }

} // NewItem
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L939-L955 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-newitem"></a>О чем следует помнить о реализации NewItem

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод должен выполнять сравнение без учета регистра строки, переданной `type` параметра. Что следует учесть также бы неоднозначным совпадений. Например для типов «файл» и «каталог», только первая буква требуется для однозначного определения. Если `type` параметр указывает тип, не удается создать поставщик, [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод должен записывать ArgumentException с сообщением указывающее типы можно создать поставщик.

- Для `newItemValue` параметр, реализация [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) рекомендуется принять строки как минимум. Он также должен принять тип объекта, который извлекается [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод тот же путь. [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) можно использовать метод [System.Management.Automation.Languageprimitives.Convertto*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo) метод для преобразования типов требуемый тип.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает значение true, [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод как дополнительную проверку для изменения потенциально опасных системы.

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a>Присоединение динамических параметров в командлет New-Item

Иногда `New-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) метод. Этот метод извлекает параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `New-Item` командлета.

Этот поставщик не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a>Удаление элементов

Чтобы удалить элементы, необходимо переопределить поставщика Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод для поддержки вызовов из `Remove-Item` командлета. Этот метод удаляет элемент из хранилища данных по указанному пути. Если `recurse` параметр `Remove-Item` командлета задано значение `true`, метод удаляет все дочерние элементы, независимо от их уровня. Если параметр имеет значение `false`, метод удаляет только один элемент по указанному пути.

Этот поставщик не поддерживает удаление элементов. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a>О чем следует помнить о реализации RemoveItem

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- При определении класса поставщика, поставщик контейнеров Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода следует удалять объекты, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) задано значение true. Если указанный путь указывает на контейнер, [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойство не является обязательным.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) отвечает за Предотвращение бесконечной рекурсии, при наличии циклических ссылок и т.п. Завершающий соответствующее исключение должно вызываться для отражения таких условий.

- Реализация [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод как дополнительную проверку для изменения потенциально опасных системы.

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a>Присоединение динамических параметров в командлет Remove-Item

Иногда `Remove-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) метод для обработки этих параметров. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Remove-Item` командлета.

Этот контейнер поставщик не реализует этот метод. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a>Запрос для дочерних элементов

Для проверки существования дочерних элементов по указанному пути, необходимо переопределить поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) метод. Этот метод возвращает `true` Если элемент имеет дочерние элементы, и `false` в противном случае. Значение null или пустой путь к, метод считает, что все элементы в хранилище данных как дочерние элементы и возвращает `true`.

Вот переопределение для [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) метод. Если существует более двух частей пути, созданным с помощью вспомогательного метода ChunkPath, метод возвращает `false`, поскольку определяются только контейнер базы данных и таблицы. Дополнительные сведения о этот вспомогательный метод, см. в статье рассматривается метод ChunkPath [Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md).

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L1094-L1097 "AccessDBProviderSample04.cs")]

#### <a name="things-to-remember-about-implementing-haschilditems"></a>О чем следует помнить о реализации HasChildItems

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):

- Если поставщик контейнер предоставляет корневой элемент, содержащий интересные точки подключения, реализация [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) метод должен возвращать `true`когда значение null или пустая строка передается в для пути.

## <a name="copying-items"></a>Копирование элементов

Копирование элементов, необходимо реализовать поставщик контейнеров [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод для поддержки вызовов из `Copy-Item` командлета. Этот метод копирует элемент данных из местоположения, указанного параметром `path` параметр командлета для местоположения, указанного параметром `copyPath` параметр. Если `recurse` параметр указан, метод копирует всех вложенных контейнерах. Если этот параметр не указан, метод копирует только один уровень элементов.

Этот поставщик не реализует этот метод. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a>О чем следует помнить о реализации CopyItem

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):

- При определении класса поставщика, поставщик контейнеров Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует копировать объекты через существующие объекты Если [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Например, поставщик FileSystem не будет копировать c:\temp\abc.txt через существующий файл c:\abc.txt Если [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Если путь, указанный в `copyPath` параметр существует и указывает контейнер, [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойство не является обязательным. В этом случае [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) следует скопировать элемент обозначается `path` параметр в контейнер обозначается `copyPath` параметр как дочерний элемент.

- Реализация [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) отвечает за Предотвращение бесконечной рекурсии, при наличии циклических ссылок и т.п. Завершающий соответствующее исключение должно вызываться для отражения таких условий.

- Реализация [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает значение true, [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод как дополнительную проверку для изменения потенциально опасных системы. Дополнительные сведения о вызове этих методов, см. в разделе [переименование элементов](#Renaming-Items).

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a>Присоединение динамических параметров в командлет Copy-Item

Иногда `Copy-Item` командлета требуется Дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать поставщик контейнеров Windows PowerShell [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) метод для обработки этих параметры. Этот метод извлекает параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров к `Copy-Item` командлета.

Этот поставщик не реализует этот метод. Тем не менее, следующий код является реализация по умолчанию [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. в разделе [регистрация командлетов, поставщиков и размещения приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Проверка поставщика в Windows PowerShell

При регистрации поставщика Windows PowerShell с помощью Windows PowerShell можно проверить его с помощью командлетов поддерживаемых в командной строке. Имейте в виду, что в следующем примере выходных данных используется вымышленная базы данных Access.

1. Запустите `Get-ChildItem` командлет, чтобы получить список дочерних элементов из таблицы Customers в базе данных Access.

   ```powershell
   Get-ChildItem mydb:customers
   ```

   Появляется следующий результат.

   ```output
   PSPath        : AccessDB::customers
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : True
   Data          : System.Data.DataRow
   Name          : Customers
   RowCount      : 91
   Columns       :
   ```

2. Запустите `Get-ChildItem` еще раз, чтобы получить данные из таблицы.

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   Появляется следующий результат.

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. Теперь с помощью `Get-Item` командлет для получения элементов в строке 0 в таблице данных.

   ```powershell
   Get-Item mydb:\customers\0
   ```

   Появляется следующий результат.

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. Повторно использовать `Get-Item` для получения данных для элементов в строке 0.

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   Появляется следующий результат.

   ```output
   CustomerID   : 1234
   CompanyName  : Fabrikam
   ContactName  : Eric Gruber
   ContactTitle : President
   Address      : 4567 Main Street
   City         : Buffalo
   Region       : NY
   PostalCode   : 98052
   Country      : USA
   Phone        : (425) 555-0100
   Fax          : (425) 555-0101
   ```

5. Теперь с помощью `New-Item` командлет, чтобы добавить строку в существующую таблицу. `Path` Определяет полный путь к строке и необходимо указать номер строки, больше, чем существующего количества строк в таблице. `Type` Задаёт «row», для указания типа добавляемого элемента. Наконец `Value` параметр задает разделенный запятыми список значений столбцов для строки.

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. Проверьте правильность работы нового элемента следующим образом.

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   Появляется следующий результат.

   ```output
   ID        : 3
   FirstName : Eric
   LastName  : Gruber
   Email     : ericgruber@fabrikam.com
   Title     : President
   Company   : Fabrikam
   WorkPhone : (425) 555-0100
   Address   : 4567 Main Street
   City      : Buffalo
   State     : NY
   Zip       : 98052
   Country   : USA
   ```

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Реализация поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md)

[Реализация поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)
---
title: Создание поставщика контейнеров Windows PowerShell
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: eec92d526ad78d2351eef6679eaa0df19900715b
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978497"
---
# <a name="creating-a-windows-powershell-container-provider"></a>Создание поставщика контейнеров Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который может работать с хранилищами данных с несколькими уровнями. Для этого типа хранилища данных верхний уровень хранилища содержит корневые элементы, а каждый последующий уровень называется узлом дочерних элементов. Разрешая пользователю работать с этими дочерними узлами, пользователь может выполнять иерархическую работу через хранилище данных.

Поставщики, которые могут работать с многоуровневые хранилищами данных, называются поставщиками контейнеров Windows PowerShell. Однако имейте в виду, что поставщик контейнеров Windows PowerShell можно использовать только при наличии одного контейнера (без вложенных контейнеров) с элементами в нем. При наличии вложенных контейнеров необходимо реализовать поставщик навигации Windows PowerShell. Дополнительные сведения о реализации поставщика навигации Windows PowerShell см. [в разделе Создание поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider04.cs) для этого поставщика с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory. Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

Поставщик контейнера Windows PowerShell, описанный здесь, определяет базу данных в качестве единого контейнера с таблицами и строками базы данных, определенными в качестве элементов контейнера.

> [!CAUTION]
> Имейте в виду, что в этом проекте предполагается, что база данных имеет поле с ИДЕНТИФИКАТОРом Name, а тип поля — Лонгинтежер.

## <a name="defining-a-windows-powershell-container-provider-class"></a>Определение класса поставщика контейнеров Windows PowerShell

Поставщик контейнера Windows PowerShell должен определять класс .NET, производный от базового класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Ниже приведено определение класса для поставщика контейнеров Windows PowerShell, описанного в этом разделе.

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
public class AccessDBProvider : ContainerCmdletProvider
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="34-35":::

Обратите внимание, что в этом определении класса атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) включает два параметра. Первый параметр задает понятное имя для поставщика, используемого Windows PowerShell. Второй параметр указывает специальные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Для этого поставщика не добавляются специальные возможности Windows PowerShell.

## <a name="defining-base-functionality"></a>Определение базовых функций

Как описано в разделе [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) является производным от нескольких других классов, предоставилих различные функции поставщика. Таким образом, поставщик контейнера Windows PowerShell должен определить все функциональные возможности, предоставляемые этими классами.

Сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. в разделе [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
Однако большинство поставщиков (включая описанный здесь поставщик) могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

Чтобы получить доступ к хранилищу данных, поставщик должен реализовать методы базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Чтобы управлять элементами хранилища данных, такими как получение, установка и очистка элементов, поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

## <a name="retrieving-child-items"></a>Получение дочерних элементов

Чтобы получить дочерний элемент, поставщик контейнера Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) для поддержки вызовов из командлета `Get-ChildItem`. Этот метод получает дочерние элементы из хранилища данных и записывает их в конвейер в виде объектов. Если указан параметр `recurse` командлета, метод получает все дочерние элементы независимо от того, на каком уровне они находятся. Если параметр `recurse` не указан, метод извлекает только один уровень дочерних элементов.

Ниже приведена реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) для этого поставщика. Обратите внимание, что этот метод получает дочерние элементы во всех таблицах базы данных, если путь указывает на базу данных Access, и получает дочерние элементы из строк этой таблицы, если путь указывает на таблицу данных.

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

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="311-362":::

#### <a name="things-to-remember-about-implementing-getchilditems"></a>Вопросы, связанные с реализацией Жетчилдитемс

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- При определении класса поставщика поставщик контейнера Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Реализация этого метода должна учитывать любую форму доступа к элементу, который может сделать элемент видимым для пользователя. Например, если пользователь имеет доступ на запись к файлу через поставщик FileSystem (предоставляемый Windows PowerShell), но не имеет доступа на чтение, файл все еще существует, а [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) возвращает `true`. Для реализации может потребоваться проверка родительского элемента, чтобы узнать, можно ли перечислить дочерний элемент.

- При записи нескольких элементов метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) может занять некоторое время. Вы можете спроектировать поставщик для записи элементов с помощью метода [System. Management. автоматизации. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) по одному за раз. При использовании этого метода элементы будут представлены пользователю в потоке.

- Реализация [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) отвечает за предотвращение бесконечной рекурсии при наличии циклических ссылок и подобной. Для отражения такого условия должно быть создано соответствующее завершающее исключение.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a>Присоединение динамических параметров к командлету Get-ChildItem

Иногда для командлета `Get-ChildItem`, вызывающего [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) , требуются дополнительные параметры, которые динамически задаются во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `Get-ChildItem`.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a>Получение имен дочерних элементов

Чтобы получить имена дочерних элементов, поставщик контейнера Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) для поддержки вызовов из командлета `Get-ChildItem`, если задан его `Name`. Этот метод получает имена дочерних элементов для указанных пути или имен дочерних элементов для всех контейнеров, если указан параметр `returnAllContainers` командлета. Дочернее имя — это конечная часть пути. Например, дочерним именем для пути c:\windows\system32\abc.dll является ABC. dll. Дочернее имя каталога c:\Windows\System32 — System32.

Ниже приведена реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) для этого поставщика. Обратите внимание, что метод получает имена таблиц, если указанный путь указывает на базу данных Access (диск) и номера строк, если путь указывает на таблицу.

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

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="369-411":::

#### <a name="things-to-remember-about-implementing-getchildnames"></a>Вопросы, связанные с реализацией Жетчилднамес

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):

- При определении класса поставщика поставщик контейнера Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

  > [!NOTE]
  > Исключение из этого правила возникает, когда указан параметр `returnAllContainers` командлета. В этом случае метод должен получить любое дочернее имя для контейнера, даже если оно не соответствует значениям свойств [System. Management. Automation. Provider. кмдлетпровидер. Filter *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter), [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)или [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .

- По умолчанию переопределения этого метода не должны извлекать имена объектов, которые обычно скрыты от пользователя, если не указано свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) . Если указанный путь указывает на контейнер, свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не является обязательным.

- Реализация [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) отвечает за предотвращение бесконечной рекурсии при наличии циклических ссылок и подобной. Для отражения такого условия должно быть создано соответствующее завершающее исключение.

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a>Присоединение динамических параметров к командлету Get-ChildItem (имя)

Иногда для командлета `Get-ChildItem` (с параметром `Name`) требуются дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамесдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `Get-ChildItem`.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a>Переименование элементов

Для переименования элемента поставщик контейнера Windows PowerShell должен переопределять метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) для поддержки вызовов из командлета `Rename-Item`. Этот метод изменяет имя элемента по указанному пути на новое указанное имя. Новое имя всегда должно относиться к родительскому элементу (контейнеру).

Этот поставщик не переопределяет метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) . Однако ниже приведена реализация по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a>Вопросы, связанные с реализацией Ренамеитем

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):

- При определении класса поставщика поставщик контейнера Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) предназначен только для изменения имени элемента, а не для операций перемещения.
  Ваша реализация метода должна записать ошибку, если параметр `newName` содержит разделители пути или в противном случае может привести к изменению родительского расположения элемента.

- По умолчанию переопределения этого метода не должны переименовывать объекты, если не указано свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) . Если указанный путь указывает на контейнер, свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не является обязательным.

- Реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в состояние системы, например при переименовании файлов.
  [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, которое будет изменено пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные в определении того, что следует отображать.

  После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитем *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) должен вызывать метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение с подтверждением, чтобы разрешить дополнительные отзывы, чтобы сказать, следует ли продолжать операцию. Поставщик должен вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) в качестве дополнительной проверки потенциально опасной модификации системы.

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a>Присоединение динамических параметров к командлету Rename-Item

Иногда командлету `Rename-Item` требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) . Этот метод получает параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `Rename-Item`.

Этот метод не реализуется этим поставщиком контейнера. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a>Создание новых элементов

Для создания новых элементов поставщик контейнера должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) для поддержки вызовов из командлета `New-Item`. Этот метод создает элемент данных, расположенный по указанному пути. Параметр `type` командлета содержит тип, определяемый поставщиком для нового элемента. Например, Поставщик FileSystem использует параметр `type` со значением "File" или "Directory". Параметр `newItemValue` командлета задает зависящее от поставщика значение для нового элемента.

Ниже приведена реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) для этого поставщика.

```csharp
protected override void NewItem( string path, string type, object newItemValue )
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

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="939-955":::

#### <a name="things-to-remember-about-implementing-newitem"></a>Вопросы, связанные с реализацией NewItem

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) должен выполнять сравнение строки, переданной в параметре `type`, без учета регистра.
  Он также должен позволять наименее неоднозначные совпадения. Например, для типов "File" и "Directory" для устранения неоднозначности требуется только первая буква. Если параметр `type` указывает тип, который поставщик не может создать, метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) должен записать исключение типа ArgumentException с сообщением, указывающим типы, которые может создать поставщик.

- Для параметра `newItemValue` рекомендуется реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) , чтобы принимать строки как минимум. Он также должен принять тип объекта, который извлекается методом [System. Management. Automation. Provider. итемкмдлетпровидер. GetObject *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для того же пути. Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) может использовать метод [System. Management. Automation. Languageprimitives. ConvertTo *](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo) для преобразования типов в нужный тип.

- Реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает значение true, метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) должен вызывать метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) в качестве дополнительной проверки потенциально опасной модификации системы.

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a>Присоединение динамических параметров к командлету New-Item

Иногда командлету `New-Item` требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера должен реализовать метод [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. невитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) . Этот метод получает параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `New-Item`.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a>Удаление элементов

Чтобы удалить элементы, поставщик Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) для поддержки вызовов из командлета `Remove-Item`. Этот метод удаляет элемент из хранилища данных по указанному пути. Если параметр `recurse` командлета `Remove-Item` имеет значение `true`, метод удаляет все дочерние элементы независимо от их уровня. Если параметр имеет значение `false`, метод удаляет только один элемент по указанному пути.

Этот поставщик не поддерживает удаление элементов. Однако следующий код является реализацией класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a>Вопросы, связанные с реализацией RemoveItem

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):

- При определении класса поставщика поставщик контейнера Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны удалять объекты, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение true. Если указанный путь указывает на контейнер, свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не является обязательным.

- Реализация [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) отвечает за предотвращение бесконечной рекурсии при наличии циклических ссылок и подобной. Для отражения такого условия должно быть создано соответствующее завершающее исключение.

- Реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) должен вызывать метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) в качестве дополнительной проверки потенциально опасной модификации системы.

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a>Присоединение динамических параметров к командлету Remove-Item

Иногда командлету `Remove-Item` требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) для работы с этими параметрами. Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `Remove-Item`.

Этот метод не реализуется этим поставщиком контейнера. Однако следующий код является реализацией класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a>Запрос дочерних элементов

Чтобы проверить, существуют ли дочерние элементы по указанному пути, поставщик контейнера Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. хасчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) . Этот метод возвращает `true`, если элемент имеет дочерние элементы, и `false` в противном случае. Для неопределенного или пустого пути метод считает, что все элементы в хранилище данных являются дочерними, и возвращает `true`.

Ниже приведено переопределение для метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. хасчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) . При наличии более двух частей пути, созданных вспомогательным методом Чункпас, метод возвращает `false`, так как определены только контейнер базы данных и контейнер таблицы. Дополнительные сведения об этом вспомогательном методе см. в описании метода Чункпас в разделе [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="1094-1097":::

#### <a name="things-to-remember-about-implementing-haschilditems"></a>Вопросы, связанные с реализацией Хасчилдитемс

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. хасчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):

- Если поставщик контейнеров предоставляет корень, который содержит интересные точки подключения, реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. хасчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) должна возвращать `true`, если для пути передается значение null или пустая строка.

## <a name="copying-items"></a>Копирование элементов

Для копирования элементов поставщик контейнера должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) для поддержки вызовов из командлета `Copy-Item`. Этот метод копирует элемент данных из расположения, указанного параметром `path` командлета, в расположение, указанное параметром `copyPath`. Если указан параметр `recurse`, метод копирует все подконтейнеры. Если параметр не указан, метод копирует только один уровень элементов.

Этот метод не реализуется этим поставщиком. Однако следующий код является реализацией класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a>Вопросы, связанные с реализацией CopyItem

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):

- При определении класса поставщика поставщик контейнера Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны копировать объекты поверх существующих объектов, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Например, Поставщик FileSystem не будет копировать к:\темп\абк.ткст в существующий файл к:\абк.ткст, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь, указанный в параметре `copyPath`, существует и указывает на контейнер, свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не является обязательным. В этом случае [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) должен скопировать элемент, указанный параметром `path`, в контейнер, указанный параметром `copyPath` в качестве дочернего.

- Реализация [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) отвечает за предотвращение бесконечной рекурсии при наличии циклических ссылок и подобной. Для отражения такого условия должно быть создано соответствующее завершающее исключение.

- Реализация метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением любых изменений в хранилище данных. После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает значение true, метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) должен вызывать метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) в качестве дополнительной проверки потенциально опасной модификации системы. Дополнительные сведения о вызове этих методов см. в разделе [Rename Items](#renaming-items).

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a>Присоединение динамических параметров к командлету Copy-Item

Иногда командлету `Copy-Item` требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик контейнера Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) для работы с этими параметрами. Этот метод получает параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет `Copy-Item`.

Этот метод не реализуется этим поставщиком. Однако следующий код является реализацией класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a>Образец кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. раздел [Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно проверить, запустив в командной строке поддерживаемые командлеты. Имейте в виду, что в следующем примере выходных данных используется вымышленная БД Access.

1. Выполните командлет `Get-ChildItem`, чтобы получить список дочерних элементов из таблицы Customers в базе данных Access.

   ```powershell
   Get-ChildItem mydb:customers
   ```

   Отобразятся следующие выходные данные.

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

2. Выполните командлет `Get-ChildItem` еще раз, чтобы получить данные таблицы.

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   Отобразятся следующие выходные данные.

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. Теперь используйте командлет `Get-Item` для получения элементов в строке 0 в таблице данных.

   ```powershell
   Get-Item mydb:\customers\0
   ```

   Отобразятся следующие выходные данные.

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. Повторное использование `Get-Item` для получения данных для элементов в строке 0.

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   Отобразятся следующие выходные данные.

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

5. Теперь используйте командлет `New-Item`, чтобы добавить строку в существующую таблицу. Параметр `Path` задает полный путь к строке и должен указывать номер строки, который больше, чем существующее число строк в таблице. Параметр `Type` указывает "Row", указывающий добавляемый тип элемента.
   Наконец, параметр `Value` задает разделенный запятыми список значений столбцов для строки.

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. Проверьте правильность операции создания элемента следующим образом.

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   Отобразятся следующие выходные данные.

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

## <a name="see-also"></a>См. также:

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Реализация поставщика элемента Windows PowerShell](./creating-a-windows-powershell-item-provider.md)

[Реализация поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

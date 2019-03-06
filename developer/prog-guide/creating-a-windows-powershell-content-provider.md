---
title: Создание поставщика Windows PowerShell содержимого | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], content provider
ms.assetid: 3da88ff9-c4c7-4ace-aa24-0a29c8cfa060
caps.latest.revision: 6
ms.openlocfilehash: 5e35d2fdfa4c6bd70c1b69ca1f357ee8d8ebcdc4
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429981"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Создание поставщика содержимого Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который позволяет пользователю управлять содержимым элементов в хранилище данных. Как следствие поставщик, который может обрабатывать содержимое элементов называется поставщиком содержимого Windows PowerShell.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider06.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

Ниже перечислены подразделы этого раздела. Если вы не знакомы с записью поставщика содержимого Windows PowerShell, прочтите эти разделы в порядке их появления. Тем не менее если вы знакомы с записью поставщика содержимого Windows PowerShell, перейдите непосредственно к сведениям, вам потребуется.

- [Определение класса поставщика Windows PowerShell содержимого](#Define-the-Windows-PowerShell-Content-Provider-Class)

- [Определение базовой функциональности](#Define-Functionality-of-Base-Class)

- [Реализация модуля чтения содержимого](#Implementing-a-Content-Reader)

- [Реализация содержимого записи](#Implementing-a-Content-Writer)

- [Получение содержимого модуля чтения](#Retrieving-the-Content-Reader)

- [Присоединение динамических параметров в `Get-Content` командлета](#Attaching-Dynamic-Parameters-to-the-Get-Content-Cmdlet)

- [Получение содержимого модуля записи](#Retrieving-the-Content-Writer)

- [Присоединение к Add_Content динамических параметров и `Set-Content` командлетов](#Attaching-Dynamic-Parameters-to-the-Add-Content-and-Set-Content-Cmdlets)

- [Очистка содержимого](#Clearing-Content)

- [Присоединение динамических параметров в `Clear-Content` командлета](#Attaching-Dynamic-Parameters-to-the-Clear-Content-Cmdlet)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование]()

- [Создание поставщика Windows PowerShell](#Building-the-Windows-PowerShell-Provider)

- [Проверка поставщика в Windows PowerShell](#Testing-the-Windows-PowerShell-Provider)

## <a name="define-the-windows-powershell-content-provider-class"></a>Определите класс поставщика Windows PowerShell содержимого

Поставщик содержимого Windows PowerShell необходимо создать класс .NET, который поддерживает [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс. Вот определение класса для поставщика элементов, описанных в этом разделе.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

Обратите внимание, что в это определение класса [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут содержит два параметра. Первый параметр указывает понятное имя для поставщика, который используется Windows PowerShell. Второй параметр указывает специальной совместимости с Windows PowerShell, которые предоставляет поставщик среды выполнения Windows PowerShell во время обработки команды. Для этого поставщика существуют определенные возможности Windows PowerShell не добавлены.

## <a name="define-functionality-of-base-class"></a>Определить функциональные возможности базового класса

Как описано в разделе [разработки ваш поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс является производным от несколько других классов, которые предоставлены функциональные возможности другого поставщика. Поставщик содержимого Windows PowerShell, таким образом, обычно определяет все функции, предоставляемые этими классами.

Дополнительные сведения о том, как реализовать функциональность для добавления сведений инициализации сеанса, а также для освобождения ресурсов, которые используются поставщиком, см. в разделе [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Тем не менее большинство поставщиков, включая поставщика, описанные здесь, можно использовать реализацию по умолчанию эта функция, предоставляемая Windows PowerShell.

Доступ к хранилищу данных, поставщик должен реализовывать методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Для работы с элементами в хранилище данных, например начало, параметр и очистка элементов, поставщик должен реализовывать методы, предоставленные [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md).

Для работы в хранилищах данных многоуровневой, поставщик должен реализовывать методы, предоставленные [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) базового класса. Дополнительные сведения о реализации этих методов см. в разделе [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).

Чтобы обеспечить поддержку рекурсивной команды, вложенные контейнеры и относительные пути, поставщик должен реализовывать [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) базового класса. Кроме того, этот поставщик содержимого Windows PowerShell можно вкладывает [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс [ System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) базового класса и поэтому должен реализовывать методы, предоставляемые этим классом. Дополнительные сведения см. в разделе реализации этих методов, см. в разделе [реализовать поставщик навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

## <a name="implementing-a-content-reader"></a>Реализация модуля чтения содержимого

Читать содержимое элемента, поставщик должен реализует класс чтения содержимого, который является производным от [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader). Средство чтения содержимого для этого поставщика разрешает доступ к содержимое строки в таблице данных. Определяет класс содержимого модуля чтения **чтения** метод, который получает данные из указанной строки и возвращает список данных, представляющий **Seek** метод, который перемещает средство чтения содержимого,  **Закрыть** метод, который закрывает средство чтения содержимого, и **Dispose** метод.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241 "AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a>Реализация содержимого записи

Для записи содержимого элемента, должен реализовывать поставщик содержимого записи класс является производным от [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter). Определяет класс содержимого модуля записи **записи** метод, который записывает содержимое указанной строки, **Seek** метод, который перемещает средство содержимого записи **закрыть** метод, который закрывает содержимое записи и **Dispose** метод.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a>Получение содержимого модуля чтения

Для получения содержимого из элемента, поставщик должен реализовывать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для поддержки `Get-Content` командлета. Этот метод возвращает содержимого чтения для элемент, расположенный по указанному пути. Объект средства чтения можно открыть для чтения содержимого.

Вот реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для этого метода для данного поставщика.

```csharp
public IContentReader GetContentReader(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be obtained only for tables");
    }

    return new AccessDBContentReader(path, this);
} // GetContentReader
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1829-L1846 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>О чем следует помнить о реализации GetContentReader

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):

- При определении класса поставщика, поставщика содержимого Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) метода необходимо убедиться, что путь, переданный в метод соответствует требованиям указанного возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует получить средство чтения для объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>Присоединение динамических параметров в командлет Get-Content

`Get-Content` Командлета может потребоваться дополнительные параметры, заданные динамически во время выполнения. Для предоставления этих динамических параметров, поставщик содержимого Windows PowerShell, должен реализовывать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) метод. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот поставщик контейнеров Windows PowerShell не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a>Получение содержимого модуля записи

Для записи содержимого элемента, поставщик должен реализовывать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) для поддержки `Set-Content` и `Add-Content` командлетов. Этот метод возвращает модуль записи содержимого для элемент, расположенный по указанному пути.

Вот реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) для этого метода.

```csharp
public IContentWriter GetContentWriter(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be added only to tables");
    }

    return new AccessDBContentWriter(path, this);
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1863-L1880 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>О чем следует помнить о реализации GetContentWriter

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):

- При определении класса поставщика, поставщика содержимого Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) метода необходимо убедиться, что путь, переданный в метод соответствует требованиям указанного возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует получить средство записи для объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>Присоединение динамические параметры в командлеты Add-Content и Set-Content

`Add-Content` И `Set-Content` командлетов может требовать дополнительных динамических параметров, которые добавляются в среду выполнения. Для предоставления этих динамических параметров, поставщик содержимого Windows PowerShell, должен реализовывать [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) метод для обработки этих параметры. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлеты.

Этот поставщик контейнеров Windows PowerShell не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a>Очистка содержимого

Пользовательский поставщик содержимого реализует [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метод поддержки `Clear-Content` командлета. Этот метод удаляет содержимое элемента по указанному пути, но оставляет без изменений элемента.

Вот реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метода для данного поставщика.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a>О чем следует помнить о реализации ClearContent

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):

- При определении класса поставщика, поставщика содержимого Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)перечисления. В этих случаях реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метода необходимо убедиться, что путь, переданный в метод соответствует требованиям указанного возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует очистить содержимое объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

- Реализация [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess* ](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при внесении изменений в хранилище данных, таких как очистка содержимого. [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) метод отправляет имя ресурса, необходимо изменить на пользователя, в среде выполнения Windows PowerShell, обработка параметров командной строки и предпочтений переменные для определения того, что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent* ](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение пользователю, чтобы разрешить обратной связи для проверки, если операция должна быть продолжено. Вызов [System.Management.Automation.Provider.Cmdletprovider.Shouldcontinue*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку для изменения потенциально опасных системы.

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Присоединение динамических параметров в командлет Clear-Content

`Clear-Content` Командлет могут потребовать дополнительных динамических параметров, которые добавляются во время выполнения. Для предоставления этих динамических параметров, поставщик содержимого Windows PowerShell, должен реализовывать [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) метод для обработки этих параметры. Этот метод извлекает параметры для элемента в указанный путь. Этот метод получает динамические параметры для элемента в заданный путь и возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [ System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот поставщик контейнеров Windows PowerShell не реализует этот метод. Однако следующий код является реализация по умолчанию этот метод.

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1819-L1822 "AccessDBProviderSample06.cs")]

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

При написании поставщика, может потребоваться добавление членов в существующие объекты или определение новых объектов. Если это сделано, необходимо создать файл типов, Windows PowerShell можно использовать для идентификации членов объекта и файл форматирования, который определяет порядок отображения объекта. Дополнительные сведения см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. в разделе [регистрация командлетов, поставщиков и размещения приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Проверка поставщика в Windows PowerShell

При регистрации поставщика Windows PowerShell с помощью Windows PowerShell можно проверить его с помощью командлетов поддерживаемых в командной строке. Например проверьте образец поставщика содержимого.

Используйте `Get-Content` командлет, чтобы получить содержимое указанного элемента в таблице базы данных в каталоге, указанном `Path` параметра. `ReadCount` Параметр указывает количество элементов для определенного содержимого модуля чтения для чтения (по умолчанию 1). Параметр команды командлет возвращает две строки (элементы) из таблицы и отображает их содержимое. Обратите внимание на то, что в следующем примере выходных данных используется вымышленная базы данных Access.

```powershell
Get-Content -Path mydb:\Customers -ReadCount 2
```

```output
ID        : 1
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
ID        : 2
FirstName : Eva
LastName  : Corets
Email     : evacorets@cohowinery.com
Title     : Sales Representative
Company   : Coho Winery
WorkPhone : (360) 555-0100
Address   : 8910 Main Street
City      : Cabmerlot
State     : WA
Zip       : 98089
Country   : USA
```

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Поставщик разработки Your Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Реализация поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

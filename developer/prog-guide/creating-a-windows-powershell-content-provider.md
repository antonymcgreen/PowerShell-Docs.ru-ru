---
title: Создание поставщика содержимого Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: a897ba29835e6f04ccacf3c4d7d8a1d43cedb91e
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323213"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Создание поставщика содержимого Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который позволяет пользователю управлять содержимым элементов в хранилище данных. Как следствие, поставщик, который может манипулировать содержимым элементов, называется поставщиком содержимого Windows PowerShell.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider06.cs) для этого поставщика с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в  **\<примерах PowerShell >** Directory.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="define-the-windows-powershell-content-provider-class"></a>Определение класса поставщика содержимого Windows PowerShell

Поставщик содержимого Windows PowerShell должен создать класс .NET, который поддерживает интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) . Ниже приведено определение класса для поставщика элементов, описанного в этом разделе.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L32-L33 "AccessDBProviderSample06.cs")]

Обратите внимание, что в этом определении класса атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) включает два параметра. Первый параметр задает понятное имя для поставщика, используемого Windows PowerShell. Второй параметр указывает специальные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Для этого поставщика нет добавленных функций Windows PowerShell.

## <a name="define-functionality-of-base-class"></a>Определение функциональных возможностей базового класса

Как описано в статье [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) является производным от нескольких других классов, предоставилих различные функции поставщика. Таким образом, поставщик содержимого Windows PowerShell, как правило, определяет все функциональные возможности, предоставляемые этими классами.

Дополнительные сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. [в разделе Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Однако большинство поставщиков, включая описанный здесь поставщик, могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

Для доступа к хранилищу данных поставщик должен реализовать методы базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Чтобы управлять элементами хранилища данных, такими как получение, установка и очистка элементов, поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

Для работы с хранилищами данных с несколькими уровнями поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

Для поддержки рекурсивных команд, вложенных контейнеров и относительных путей поставщик должен реализовать базовый класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Кроме того, этот поставщик содержимого Windows PowerShell может присоединить интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) к базовому классу [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и Поэтому необходимо реализовать методы, предоставляемые этим классом. Дополнительные сведения см. в разделе Реализация [поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

## <a name="implementing-a-content-reader"></a>Реализация средства чтения содержимого

Для чтения содержимого из элемента поставщик должен реализовывать класс чтения содержимого, производный от класса [System. Management. Automation. Provider. иконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentReader). Читатель содержимого для этого поставщика предоставляет доступ к содержимому строки в таблице данных. Класс чтения содержимого определяет метод **Read** , который получает данные из указанной строки и возвращает список, представляющий эти данные, метод **Seek** , который перемещает средство чтения содержимого, метод **Close** , который закрывает средство чтения содержимого, и элемент  **Метод Dispose** .

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2115-L2241 "AccessDBProviderSample06.cs")]

## <a name="implementing-a-content-writer"></a>Реализация модуля записи содержимого

Чтобы записать содержимое в элемент, поставщик должен реализовать класс модуля записи содержимого, производный от [System. Management. Automation. Provider. иконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentWriter). Класс записи содержимого определяет метод **Write** , записывающий указанное содержимое строки, метод **Seek** , который перемещает средство записи содержимого, метод **Close** , который закрывает модуль записи содержимого, и метод **Dispose** .

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L2250-L2394 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-reader"></a>Получение средства чтения содержимого

Чтобы получить содержимое из элемента, поставщик должен реализовать [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для поддержки `Get-Content` командлета. Этот метод возвращает средство чтения содержимого для элемента, расположенного по указанному пути. Затем объект модуля чтения можно открыть для чтения содержимого.

Ниже приведена реализация класса [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для этого метода для данного поставщика.

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

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>Вопросы, связанные с реализацией Жетконтентреадер

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль чтения для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, то ошибка должна быть записана.

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>Присоединение динамических параметров к командлету Get-Content

`Get-Content` Командлету могут потребоваться дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объектами. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1853-L1856 "AccessDBProviderSample06.cs")]

## <a name="retrieving-the-content-writer"></a>Получение модуля записи содержимого

Для записи содержимого в элемент поставщик должен реализовать [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) для поддержки `Set-Content` командлетов и `Add-Content` . Этот метод возвращает модуль записи содержимого для элемента, расположенного по указанному пути.

Ниже приведена реализация класса [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) для этого метода.

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

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>Вопросы, связанные с реализацией Жетконтентвритер

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль записи для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, то ошибка должна быть записана.

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>Присоединение динамических параметров к командлетам Add-Content и Set-Content

Командлеты `Set-Content` и могут потребовать дополнительных динамических параметров, которые добавляют среду выполнения. `Add-Content` Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) для работы с этими параметрами. Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объектами. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлеты.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1887-L1890 "AccessDBProviderSample06.cs")]

## <a name="clearing-content"></a>Очистка содержимого

Поставщик содержимого реализует метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для поддержки `Clear-Content` командлета. Этот метод удаляет содержимое элемента по указанному пути, но оставляет элемент неизменным.

Ниже приведена реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для этого поставщика.

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L1775-L1812 "AccessDBProviderSample06.cs")]

#### <a name="things-to-remember-about-implementing-clearcontent"></a>Вопросы, связанные с реализацией ClearContent

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны очищать содержимое объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, то ошибка должна быть записана.

- Реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в хранилище данных, таких как очистка содержимого. Метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell обрабатывает все параметры командной строки или переменные предпочтений в определение того, что должно отображаться.

  После того как вызов метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должен вызывать [ Метод System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение, чтобы разрешить отзыв, чтобы убедиться, что операция должна быть продолжена. Вызов [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку потенциально опасного изменения системы.

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Присоединение динамических параметров к командлету Clear-Content

Для `Clear-Content` командлета могут потребоваться дополнительные динамические параметры, добавляемые во время выполнения. Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) для работы с этими параметрами. Этот метод получает параметры для элемента по указанному пути. Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объектами. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

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

При написании поставщика может потребоваться добавить элементы в существующие объекты или определить новые объекты. Когда это будет сделано, необходимо создать файл типов, который Windows PowerShell может использовать для определения членов объекта и файла форматирования, определяющего способ отображения объекта. Дополнительные сведения см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. раздел [Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно проверить, запустив в командной строке поддерживаемые командлеты. Например, протестируйте пример поставщика содержимого.

Используйте командлет `Get-Content` , чтобы получить содержимое указанного элемента в таблице базы данных по пути, указанному `Path` параметром. `ReadCount` Параметр задает число элементов, которое считывается для чтения определенным считыванием содержимого (по умолчанию 1). С помощью следующей записи команды командлет извлекает из таблицы две строки (элементы) и отображает их содержимое. Обратите внимание, что в следующем примере выходных данных используется вымышленная БД Access.

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

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Реализация поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

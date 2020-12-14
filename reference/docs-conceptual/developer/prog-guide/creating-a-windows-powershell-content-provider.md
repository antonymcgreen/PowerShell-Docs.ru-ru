---
ms.date: 09/13/2016
ms.topic: reference
title: Создание поставщика содержимого Windows PowerShell
description: Создание поставщика содержимого Windows PowerShell
ms.openlocfilehash: 7890f0ab8d1cc7f29bdc077b342bae950cfa7827
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645378"
---
# <a name="creating-a-windows-powershell-content-provider"></a>Создание поставщика содержимого Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который позволяет пользователю управлять содержимым элементов в хранилище данных. Как следствие, поставщик, который может манипулировать содержимым элементов, называется поставщиком содержимого Windows PowerShell.

> [!NOTE]
> Исходный файл C# (AccessDBSampleProvider06.cs) для этого поставщика можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге. Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="define-the-windows-powershell-content-provider-class"></a>Определение класса поставщика содержимого Windows PowerShell

Поставщик содержимого Windows PowerShell должен создать класс .NET, который поддерживает интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) . Ниже приведено определение класса для поставщика элементов, описанного в этом разделе.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="32-33":::

Обратите внимание, что в этом определении класса атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) включает два параметра. Первый параметр задает понятное имя для поставщика, используемого Windows PowerShell. Второй параметр указывает специальные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Для этого поставщика нет добавленных функций Windows PowerShell.

## <a name="define-functionality-of-base-class"></a>Определение функциональных возможностей базового класса

Как описано в статье [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) является производным от нескольких других классов, предоставилих различные функции поставщика. Таким образом, поставщик содержимого Windows PowerShell, как правило, определяет все функциональные возможности, предоставляемые этими классами.

Дополнительные сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. [в разделе Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
Однако большинство поставщиков, включая описанный здесь поставщик, могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

Для доступа к хранилищу данных поставщик должен реализовать методы базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

Чтобы управлять элементами хранилища данных, такими как получение, установка и очистка элементов, поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).

Для работы с хранилищами данных с несколькими уровнями поставщик должен реализовать методы, предоставляемые базовым классом [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Дополнительные сведения о реализации этих методов см. [в разделе Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).

Для поддержки рекурсивных команд, вложенных контейнеров и относительных путей поставщик должен реализовать базовый класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) . Кроме того, этот поставщик содержимого Windows PowerShell может подключить интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) к базовому классу [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и, следовательно, должен реализовать методы, предоставляемые этим классом. Дополнительные сведения см. в разделе Реализация [поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).

## <a name="implementing-a-content-reader"></a>Реализация средства чтения содержимого

Для чтения содержимого из элемента поставщик должен реализовывать класс чтения содержимого, производный от класса [System. Management. Automation. Provider. иконтентреадер](/dotnet/api/System.Management.Automation.Provider.IContentReader).
Читатель содержимого для этого поставщика предоставляет доступ к содержимому строки в таблице данных. Класс чтения содержимого определяет метод **Read** , который получает данные из указанной строки и возвращает список, представляющий эти данные, метод **Seek** , который перемещает средство чтения содержимого, метод **Close** , который закрывает средство чтения содержимого, и метод **Dispose** .

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="2115-2241":::

## <a name="implementing-a-content-writer"></a>Реализация модуля записи содержимого

Чтобы записать содержимое в элемент, поставщик должен реализовать класс модуля записи содержимого, производный от [System. Management. Automation. Provider. иконтентвритер](/dotnet/api/System.Management.Automation.Provider.IContentWriter).
Класс записи содержимого определяет метод **Write** , записывающий указанное содержимое строки, метод **Seek** , который перемещает средство записи содержимого, метод **Close** , который закрывает модуль записи содержимого, и метод **Dispose** .

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="2250-2394":::

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

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1829-1846":::

#### <a name="things-to-remember-about-implementing-getcontentreader"></a>Вопросы, связанные с реализацией Жетконтентреадер

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль чтения для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true` . Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение, то ошибка должна быть записана `false` .

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a>Присоединение динамических параметров к командлету Get-Content

`Get-Content`Командлету могут потребоваться дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1853-1856":::

## <a name="retrieving-the-content-writer"></a>Получение модуля записи содержимого

Для записи содержимого в элемент поставщик должен реализовать [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) для поддержки `Set-Content` `Add-Content` командлетов и. Этот метод возвращает модуль записи содержимого для элемента, расположенного по указанному пути.

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

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1863-1880":::

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a>Вопросы, связанные с реализацией Жетконтентвритер

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритер *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль записи для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true` . Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение, то ошибка должна быть записана `false` .

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a>Присоединение динамических параметров к командлетам Add-Content и Set-Content

`Add-Content` `Set-Content` Командлеты и могут потребовать дополнительных динамических параметров, которые добавляют среду выполнения. Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) для работы с этими параметрами. Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлеты.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1887-1890":::

## <a name="clearing-content"></a>Очистка содержимого

Поставщик содержимого реализует метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для поддержки `Clear-Content` командлета. Этот метод удаляет содержимое элемента по указанному пути, но оставляет элемент неизменным.

Ниже приведена реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для этого поставщика.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1775-1812":::

#### <a name="things-to-remember-about-implementing-clearcontent"></a>Вопросы, связанные с реализацией ClearContent

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):

- При определении класса поставщика поставщик содержимого Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны очищать содержимое объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true` . Если путь представляет элемент, который скрыт от User, а параметр [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение, то ошибка должна быть записана `false` .

- Реализация метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в хранилище данных, таких как очистка содержимого. Метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell обрабатывает все параметры командной строки или привилегированные переменные в определении того, что следует отображать.

  После того как вызов метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true` , метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) должен вызвать метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение, чтобы разрешить отзыв, чтобы убедиться, что операция должна быть продолжена. Вызов [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку потенциально опасного изменения системы.

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a>Присоединение динамических параметров к командлету Clear-Content

Для `Clear-Content` командлета могут потребоваться дополнительные динамические параметры, добавляемые во время выполнения. Чтобы предоставить эти динамические параметры, поставщик содержимого Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) для работы с этими параметрами. Этот метод получает параметры для элемента по указанному пути. Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Этот метод не реализуется этим поставщиком контейнера Windows PowerShell. Однако приведенный ниже код является реализацией этого метода по умолчанию.

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1819-1822":::

## <a name="code-sample"></a>Образец кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

При написании поставщика может потребоваться добавить элементы в существующие объекты или определить новые объекты. Когда это будет сделано, необходимо создать файл типов, который Windows PowerShell может использовать для определения членов объекта и файла форматирования, определяющего способ отображения объекта. Дополнительные сведения см. в разделе [расширение типов объектов и форматирование](/previous-versions/ms714665(v=vs.85)).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. раздел [Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно проверить, запустив в командной строке поддерживаемые командлеты. Например, протестируйте пример поставщика содержимого.

Используйте `Get-Content` командлет, чтобы получить содержимое указанного элемента в таблице базы данных по пути, указанному `Path` параметром. `ReadCount`Параметр задает число элементов, которое считывается для чтения определенным считыванием содержимого (по умолчанию 1). С помощью следующей записи команды командлет извлекает из таблицы две строки (элементы) и отображает их содержимое. Обратите внимание, что в следующем примере выходных данных используется вымышленная БД Access.

```powershell
Get-Content -Path mydb:\Customers -ReadCount 2
```

```Output
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

## <a name="see-also"></a>См. также:

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Реализация поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

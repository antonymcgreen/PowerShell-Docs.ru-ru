---
title: Создание поставщика элементов Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: c60da62a06fcb40b6970d4209e991e57af733f33
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323194"
---
# <a name="creating-a-windows-powershell-item-provider"></a>Создание поставщика элементов Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell, который может управлять данными в хранилище данных. В этом разделе элементы данных в хранилище называются "элементами" хранилища данных. Как следствие, поставщик, который может манипулировать данными в хранилище, называется поставщиком элементов Windows PowerShell.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider03.cs) для этого поставщика с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в  **\<примерах PowerShell >** Directory.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

Поставщик элементов Windows PowerShell, описанный в этом разделе, получает элементы данных из базы данных Access. В этом случае «Item» — это либо таблица в базе данных Access, либо строка в таблице.

## <a name="defining-the-windows-powershell-item-provider-class"></a>Определение класса поставщика элементов Windows PowerShell

Поставщик элементов Windows PowerShell должен определить класс .NET, производный от базового класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Ниже приведено определение класса для поставщика элементов, описанного в этом разделе.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L34-L36 "AccessDBProviderSample03.cs")]

Обратите внимание, что в этом определении класса атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) включает два параметра. Первый параметр задает понятное имя для поставщика, используемого Windows PowerShell. Второй параметр указывает специальные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Для этого поставщика нет добавленных функций Windows PowerShell.

## <a name="defining-base-functionality"></a>Определение базовых функций

Как описано в статье [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) является производным от нескольких других классов, предоставилих различные функции поставщика. Поэтому поставщик элементов Windows PowerShell должен определить все функциональные возможности, предоставляемые этими классами.

Дополнительные сведения о том, как реализовать функции для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. [в разделе Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Однако большинство поставщиков, включая описанный здесь поставщик, могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.

Прежде чем поставщик элементов Windows PowerShell сможет манипулировать элементами в хранилище, он должен реализовать методы базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) для доступа к хранилищу данных. Дополнительные сведения о реализации этого класса см. [в разделе Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).

## <a name="checking-for-path-validity"></a>Проверка допустимости пути

При поиске элемента данных среда выполнения Windows PowerShell обеспечивает для поставщика путь Windows PowerShell, как определено в разделе "Основные понятия PSPath", [как работает Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58). Поставщик элементов Windows PowerShell должен проверить синтаксическую и семантическую достоверность любого пути, переданного в него, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) . Этот метод возвращает `true` значение, если путь является допустимым `false` , и в противном случае —. Имейте в виду, что реализация этого метода не должна проверять существование элемента по пути, но синтаксические и Семантическо правильные пути.

Ниже приведена реализация метода [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) для этого поставщика. Обратите внимание, что эта реализация вызывает вспомогательный метод Нормализепас, чтобы преобразовать все разделители в пути в одинаковые.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L274-L298 "AccessDBProviderSample03.cs")]

## <a name="determining-if-an-item-exists"></a>Определение существования элемента

После проверки пути среда выполнения Windows PowerShell должна определить, существует ли в этом пути элемент данных. Для поддержки этого типа запросов поставщик элементов Windows PowerShell реализует метод [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) . Этот метод возвращает `true` элемент по указанному пути и `false` (по умолчанию) в противном случае.

Ниже приведена реализация метода [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) для этого поставщика. Обратите внимание, что этот метод вызывает вспомогательные методы Пасисдриве, Чункпас и GetObject и использует определенный поставщиком объект Датабасетаблеинфо.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L229-L267 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-itemexists"></a>Вопросы, связанные с реализацией Итемексистс

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists):

- При определении класса поставщика поставщик элементов Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- Реализация этого метода должна обеспечивать любой вид доступа к элементу, который может сделать элемент видимым для пользователя. Например, если пользователь имеет доступ на запись к файлу через поставщик FileSystem (предоставляемый Windows PowerShell), но не имеет доступа на чтение, файл все еще существует, а [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) возвращает `true`. Для реализации может потребоваться проверка родительского элемента, чтобы узнать, можно ли перечислить дочерний элемент.

## <a name="attaching-dynamic-parameters-to-the-test-path-cmdlet"></a>Присоединение динамических параметров к командлету Test-Path

Иногда командлет, вызывающий [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) , требует дополнительных параметров, заданных динамически во время выполнения. `Test-Path` Чтобы предоставить эти динамические параметры, поставщик элементов Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. итемексистсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)объект. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в `Test-Path` командлет.

Данный поставщик элементов Windows PowerShell не реализует этот метод. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovideritemexistdynamicparameters](Msh_samplestestcmdlets#testprovideritemexistdynamicparameters)]  -->

## <a name="retrieving-an-item"></a>Получение элемента

Чтобы получить элемент, поставщик элементов Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для поддержки вызовов из `Get-Item` командлета. Этот метод записывает элемент с помощью метода [System. Management. автоматизации. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .

Ниже приведена реализация метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для этого поставщика. Обратите внимание, что этот метод использует вспомогательные методы GetRows и GetRow для получения элементов, которые являются либо таблицами в базе данных Access, либо строками в таблице данных.

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs#L132-L163 "AccessDBProviderSample03.cs")]

#### <a name="things-to-remember-about-implementing-getitem"></a>Вопросы, связанные с реализацией функции DataItem

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem):

- При определении класса поставщика поставщик элементов Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) должна гарантировать, что путь, передаваемый в метод, соответствует этим требованиям. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны получать объекты, которые обычно скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Например, метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для поставщика FileSystem проверяет свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) перед тем, как оно попытается вызвать [System. Management. Automation. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) для скрытых или системных файлов.

## <a name="attaching-dynamic-parameters-to-the-get-item-cmdlet"></a>Присоединение динамических параметров к командлету Get-Item

`Get-Item` Иногда командлету требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик элементов Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)объект. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в `Get-Item` командлет.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetitemdynamicparameters](Msh_samplestestcmdlets#testprovidergetitemdynamicparameters)]  -->

## <a name="setting-an-item"></a>Задание элемента

Чтобы задать элемент, поставщик элементов Windows PowerShell должен переопределить метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов из `Set-Item` командлета. Этот метод задает значение элемента по указанному пути.

Этот поставщик не предоставляет переопределение для метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) . Однако ниже приведена реализация этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitem](Msh_samplestestcmdlets#testprovidersetitem)]  -->

#### <a name="things-to-remember-about-implementing-setitem"></a>Вопросы, связанные с реализацией Сетитем

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem):

- При определении класса поставщика поставщик элементов Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) должна гарантировать, что путь, передаваемый в метод, соответствует этим требованиям. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны устанавливать или записывать объекты, скрытые от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет скрытый элемент, то метод [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) должен отправить сообщение об ошибке, если в пути представлена скрытая запись, а [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) `false`имеет значение.

- Реализация метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед выполнением любые изменения в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в хранилище данных, например при удалении файлов. Метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или переменные предпочтений в определение того, что должно отображаться.

  После того как вызов метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) должен вызывать [ Метод System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение, чтобы разрешить отзыв, чтобы убедиться, что операция должна быть продолжена. Вызов [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку потенциально опасного изменения системы.

## <a name="retrieving-dynamic-parameters-for-setitem"></a>Получение динамических параметров для Сетитем

`Set-Item` Иногда командлету требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик элементов Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)объект. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в `Set-Item` командлет.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidersetitemdynamicparameters](Msh_samplestestcmdlets#testprovidersetitemdynamicparameters)]  -->

## <a name="clearing-an-item"></a>Очистка элемента

Чтобы очистить элемент, поставщик элементов Windows PowerShell реализует метод [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) для поддержки вызовов из `Clear-Item` командлета. Этот метод удаляет элемент данных по указанному пути.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitem](Msh_samplestestcmdlets#testproviderclearitem)]  -->

#### <a name="things-to-remember-about-implementing-clearitem"></a>Вопросы, связанные с реализацией Клеаритем

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem):

- При определении класса поставщика поставщик элементов Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) должна гарантировать, что путь, передаваемый в метод, соответствует этим требованиям. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны устанавливать или записывать объекты, скрытые от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User и [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) , то в метод [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) должна быть отправлена ошибка. Задайте для `false`значение.

- Реализация метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед выполнением любые изменения в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в хранилище данных, например при удалении файлов. Метод [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, с помощью среды выполнения Windows PowerShell и обрабатывает все параметры командной строки или переменные предпочтений в определение того, что должно отображаться.

  После того как вызов метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) должен вызывать [ Метод System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение, чтобы разрешить отзыв, чтобы убедиться, что операция должна быть продолжена. Вызов [System. Management. Automation. Provider. кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) обеспечивает дополнительную проверку потенциально опасного изменения системы.

## <a name="retrieve-dynamic-parameters-for-clearitem"></a>Получение динамических параметров для Клеаритем

`Clear-Item` Иногда командлету требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик элементов Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)объект. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в `Clear-Item` командлет.

Данный поставщик элементов не реализует этот метод. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderclearitemdynamicparameters](Msh_samplestestcmdlets#testproviderclearitemdynamicparameters)]  -->

## <a name="performing-a-default-action-for-an-item"></a>Выполнение действия по умолчанию для элемента

Поставщик элементов Windows PowerShell может реализовать метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) для поддержки вызовов из `Invoke-Item` командлета, что позволяет поставщику выполнять действие по умолчанию. для элемента по указанному пути. Например, Поставщик FileSystem может использовать этот метод для вызова ShellExecute для определенного элемента.

Этот метод не реализуется этим поставщиком. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultaction](Msh_samplestestcmdlets#testproviderinvokedefaultaction)]  -->

#### <a name="things-to-remember-about-implementing-invokedefaultaction"></a>Вопросы, связанные с реализацией Инвокедефаултактион

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction):

- При определении класса поставщика поставщик элементов Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактион *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) должна гарантировать, что путь, передаваемый в метод, соответствует этим требованиям. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны устанавливать или записывать объекты, скрытые от пользователя, если только свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User и [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) , то в метод [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) должна быть отправлена ошибка. Задайте для `false`значение.

## <a name="retrieve-dynamic-parameters-for-invokedefaultaction"></a>Получение динамических параметров для Инвокедефаултактион

`Invoke-Item` Иногда командлету требуются дополнительные параметры, которые задаются динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик элементов Windows PowerShell должен реализовать метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) . Этот метод получает динамические параметры для элемента по указанному пути и возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или [System. Management. Automation. рунтимедефинедпараметердиктионари ](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)объект. Среда выполнения Windows PowerShell использует возвращенный объект для добавления динамических параметров `Invoke-Item` в командлет.

Данный поставщик элементов не реализует этот метод. Однако приведенный ниже код является реализацией этого метода по умолчанию.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters](Msh_samplestestcmdlets#testproviderinvokedefaultactiondynamicparameters)]  -->

## <a name="implementing-helper-methods-and-classes"></a>Реализация вспомогательных методов и классов

Этот поставщик элементов реализует несколько вспомогательных методов и классов, которые используются открытыми методами переопределения, определенными в Windows PowerShell. Код для этих вспомогательных методов и классов показан в разделе [пример кода](#code-sample) .

### <a name="normalizepath-method"></a>Метод Нормализепас

Этот поставщик элементов реализует вспомогательный метод Нормализепас, чтобы обеспечить единообразный формат пути. В указанном формате используется обратная\\косая черта () в качестве разделителя.

### <a name="pathisdrive-method"></a>Метод Пасисдриве

Этот поставщик элементов реализует вспомогательный метод Пасисдриве, чтобы определить, действительно ли указанный путь является именем диска.

### <a name="chunkpath-method"></a>Метод Чункпас

Этот поставщик элементов реализует вспомогательный метод Чункпас, который разбивает указанный путь таким образом, чтобы поставщик мог опознать свои отдельные элементы. Он возвращает массив, состоящий из элементов Path.

### <a name="gettable-method"></a>Метод таблицы

Этот поставщик элементов реализует вспомогательный метод GetObject, который возвращает объект Датабасетаблеинфо, представляющий сведения о таблице, указанной в вызове.

### <a name="getrow-method"></a>Метод GetRow

Метод [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) этого поставщика элементов вызывает вспомогательный метод GetRows. Этот вспомогательный метод получает объект Датабасеровинфо, представляющий сведения о заданной строке в таблице.

### <a name="databasetableinfo-class"></a>Класс Датабасетаблеинфо

Этот поставщик элементов определяет класс Датабасетаблеинфо, представляющий коллекцию сведений в таблице данных в базе данных. Этот класс аналогичен классу [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) .

Поставщик образца элемента определяет метод Датабасетаблеинфо. WebMethod, который возвращает коллекцию объектов табличной информации, определяющих таблицы в базе данных. Этот метод включает блок try/catch, чтобы убедиться, что любая ошибка базы данных отображается как строка с нулевым числом записей.

### <a name="databaserowinfo-class"></a>Класс Датабасеровинфо

Этот поставщик элементов определяет вспомогательный класс Датабасеровинфо, представляющий строку в таблице базы данных. Этот класс аналогичен классу [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) .

В примере поставщика определяется метод Датабасеровинфо. GetRows, который возвращает коллекцию объектов со сведениями о строках для указанной таблицы. Этот метод включает блок try/catch для перехвата исключений. При любых ошибках не будет сведений о строках.

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample03](./accessdbprovidersample03-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

При написании поставщика может потребоваться добавить элементы в существующие объекты или определить новые объекты. По завершении создайте файл типов, который Windows PowerShell может использовать для определения членов объекта и файла форматирования, определяющего способ отображения объекта. Дополнительные сведения о см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. раздел [Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

Если этот поставщик элементов Windows PowerShell зарегистрирован в Windows PowerShell, можно протестировать только основные функциональные возможности и функции поставщика. Чтобы протестировать манипуляцию с элементами, необходимо также реализовать функциональные возможности контейнера, описанные в разделе [Реализация контейнера Windows PowerShell Provider](./creating-a-windows-powershell-container-provider.md).

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Как работает Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Создание контейнера Windows PowerShell provider](./creating-a-windows-powershell-container-provider.md)

[Создание поставщика Windows PowerShell для дисков](./creating-a-windows-powershell-drive-provider.md)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)
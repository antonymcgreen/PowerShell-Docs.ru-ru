---
title: Создание поставщика Windows PowerShell свойства | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- property providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], property provider
ms.assetid: a6adca44-b94b-4103-9970-a9b414355e60
caps.latest.revision: 5
ms.openlocfilehash: 6ec0752a9ae06c5c2cdd1a1851caeeff52d8eb74
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081841"
---
# <a name="creating-a-windows-powershell-property-provider"></a>Создание поставщика свойств Windows PowerShell

В этом разделе описывается, как создать поставщик, который позволяет пользователю управлять свойств элементов в хранилище данных. Как следствие этот тип поставщиков называется поставщика свойства Windows PowerShell. Например поставщик реестра предоставляемые значения раздела реестра Windows PowerShell обрабатывает как свойства элемента ключа реестра. Необходимо добавить этот тип поставщиков [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) интерфейс для реализации класса .NET.

> [!NOTE]
> Windows PowerShell предоставляет файл шаблона, который можно использовать для разработки поставщика Windows PowerShell. Файл TemplateProvider.cs можно найти в Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный шаблон доступен в  **\<примеры PowerShell >** каталога. Следует создать копию этого файла и используйте ее для создания нового поставщика Windows PowerShell, удаляя любые функции, которые не требуется.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

> [!CAUTION]
> Методы класса поставщика свойства должен записывать все объекты, с помощью [System.Management.Automation.Provider.Cmdletprovider.Writepropertyobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WritePropertyObject) метод.

Ниже перечислены подразделы этого раздела. Если вы не знакомы с записью поставщика свойства Windows PowerShell, прочтите эти сведения, в том порядке, в котором она появляется. Тем не менее если вы знакомы с записью поставщика свойства Windows PowerShell, перейдите непосредственно к сведениям, вам потребуется.

- [Определение поставщика Windows PowerShell](#Defining-the-Windows-PowerShell-provider)

- [Определение базовой функциональности](#Defining-Base-Functionality)

- [Получение свойств](#Retrieving-Properties)

- [Присоединение динамических параметров в `Get-ItemProperty` командлета](#Attaching-Dynamic-Parameters-to-the-Get-ItemProperty-Cmdlet)

- [Настройка свойств](#Setting-Properties)

- [Присоединение динамических параметров в `Set-ItemProperty` командлета](#Attaching-Dynamic-Parameters-for-the-Set-ItemProperty-Cmdlet)

- [Очистка свойства](#Clearing-Properties)

- [Присоединение динамических параметров в `Clear-ItemProperty` командлета](#Attaching-Dynamic-Parameters-to-the-Clear-ItemProperty-Cmdlet)

- [Создание поставщика Windows PowerShell](#Building-the-Windows-PowerShell-provider)

## <a name="defining-the-windows-powershell-provider"></a>Определение поставщика Windows PowerShell

Поставщик свойств необходимо создать класс .NET, который поддерживает [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) интерфейс. Ниже приведено объявление класса по умолчанию из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration](Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration)]  -->

## <a name="defining-base-functionality"></a>Определение базовой функциональности

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) интерфейс может быть подключен к любой из базовых классов поставщика, за исключением элемента [ System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса. Добавьте базовые функциональные возможности, которые требуются для базового класса, который вы используете. Дополнительные сведения о базовых классов, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

## <a name="retrieving-properties"></a>Получение свойств

Для получения свойств, поставщик должен реализовывать [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) метод для поддержки вызовов из `Get-ItemProperty` командлета. Этот метод извлекает свойства элемент, расположенный по указанному пути поставщика внутренней (полное).

`providerSpecificPickList` Параметр указывает, какие свойства следует извлечь. Если этот параметр имеет `null` или пустое, метод должен извлечь все свойства. Кроме того [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) записывает экземпляр [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) , представляющий контейнер свойств, полученных свойств. Метод должен вернуть nothing.

Рекомендуется реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) поддерживает развертывание знаков подстановки имен свойств для каждого элемента в списке выбора. Чтобы сделать это, используйте [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) Чтобы выполнить сопоставление по шаблону.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty)]  -->

#### <a name="things-to-remember-about-implementing-getproperty"></a>О чем следует помнить о реализации GetProperty

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty):

- При определении класса поставщика, поставщика свойства Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует получить средство чтения для объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

## <a name="attaching-dynamic-parameters-to-the-get-itemproperty-cmdlet"></a>Присоединение динамических параметров в командлет Get-ItemProperty

`Get-ItemProperty` Командлета может потребоваться дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать свойство поставщика Windows PowerShell [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) метод. `path` Задаёт полный поставщик внутреннего пути, хотя `providerSpecificPickList` параметр указывает поставщика свойства, введенные в командной строке. Этот параметр может быть `null` или пусто, если свойства передаются по конвейеру в командлет. В этом случае этот метод возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters)]  -->

## <a name="setting-properties"></a>Настройка свойств

Чтобы задать свойства, необходимо реализовать свойство поставщика Windows PowerShell [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) метод для поддержки вызовов из `Set-ItemProperty` командлета. Этот метод задает одно или несколько свойств элемента по указанному пути и перезаписывает предоставленного свойства при необходимости. [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) также записывает экземпляр [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) , представляющий контейнер, обновленный свойства.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty)]  -->

#### <a name="things-to-remember-about-implementing-set-itemproperty"></a>О чем следует помнить о реализации Set-ItemProperty

Следующие условия могут применяться к реализации [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty):

- При определении класса поставщика, поставщика свойства Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) метода необходимо убедиться, что путь, переданный в метод соответствует требованиям указанного возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует получить средство чтения для объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

- Реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, при изменении состояния системы, например, переименование файлов. [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, необходимо изменить на пользователя, со средой Windows PowerShell и обработка параметров командной строки и привилегированных переменных при определении что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, если можно модифицировать потенциально опасных системы, [ System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение с подтверждением пользователю, чтобы разрешить дополнительный отзыв указать, что операция должна быть продолжено.

## <a name="attaching-dynamic-parameters-for-the-set-itemproperty-cmdlet"></a>Присоединение динамических параметров для командлета Set-ItemProperty

`Set-ItemProperty` Командлета может потребоваться дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать свойство поставщика Windows PowerShell [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) метод. Этот метод возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. `null` Значения могут быть возвращены, если нет динамических параметров, должны быть добавлены.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters)]  -->

## <a name="clearing-properties"></a>Удаление свойства

Чтобы очистить свойства, необходимо реализовать свойство поставщика Windows PowerShell [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) метод для поддержки вызовов из `Clear-ItemProperty` командлета. Этот метод задает одно или несколько свойств для элемент, расположенный по указанному пути.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty](Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty)]  -->

#### <a name="thing-to-remember-about-implementing-clearproperty"></a>Следует помнить о реализации ClearProperty

Следующие условия могут относиться к реализации [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty):

- При определении класса поставщика, поставщика свойства Windows PowerShell может объявлять возможностей поставщика ExpandWildcards фильтра, Include и Exclude, из [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. В этих случаях реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) метод должен соответствовать требованиям указанного пути, передаваемые методу возможности. Чтобы сделать это, метод должен получить доступ к соответствующее свойство, например, [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [ System.Management.Automation.Provider.Cmdletprovider.Include*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) свойства.

- По умолчанию переопределения этого метода не следует получить средство чтения для объектов, которые скрыты от пользователя, если не [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) свойству `true`. Ошибка должны записываться, если путь представляет элемент, который является скрытым от пользователя и [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) присваивается `false`.

- Реализация [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess ](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверьте его возвращаемое значение перед внесением любых изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции, перед изменении состояния системы, таких как очистка содержимого. [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, необходимо изменить на пользователя, в среде выполнения Windows PowerShell, принимая во внимание любые параметры командной строки или привилегированных переменных в Определяет, что должно быть отображено.

  После вызова [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, если можно модифицировать потенциально опасных системы, [ System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) метод должен вызывать [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) метод. Этот метод отправляет сообщение с подтверждением пользователю, чтобы разрешить дополнительный отзыв указать, что потенциально опасные операции должно быть продолжено.

## <a name="attaching-dynamic-parameters-to-the-clear-itemproperty-cmdlet"></a>Присоединение динамических параметров в командлет Clear-ItemProperty

`Clear-ItemProperty` Командлета может потребоваться дополнительные параметры, заданные динамически во время выполнения. Для обеспечения этих динамических параметров, необходимо реализовать свойство поставщика Windows PowerShell [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) метод. Этот метод возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта. `null` Значения могут быть возвращены, если нет динамических параметров, должны быть добавлены.

Вот реализация по умолчанию [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) из файла TemplateProvider.cs, предоставляемые Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters)]  -->

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. в разделе [регистрация командлетов, поставщиков и размещения приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="see-also"></a>См. также

[Поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Поставщик разработки Your Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)
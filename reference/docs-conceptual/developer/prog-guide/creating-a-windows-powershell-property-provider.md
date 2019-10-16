---
title: Создание поставщика свойств Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: c36b93a5b4d3e7ef92d7f5b16381a8def2dd5466
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360483"
---
# <a name="creating-a-windows-powershell-property-provider"></a>Создание поставщика свойств Windows PowerShell

В этом разделе описывается создание поставщика, который позволяет пользователю управлять свойствами элементов в хранилище данных. Как следствие, этот тип поставщика называется поставщиком свойств Windows PowerShell. Например, поставщик реестра, предоставляемый Windows PowerShell, обрабатывает значения разделов реестра как свойства элемента раздела реестра. Поставщик этого типа должен добавить интерфейс [System. Management. Automation. Provider. ипропертикмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) в реализацию класса .NET.

> [!NOTE]
> Windows PowerShell предоставляет файл шаблона, который можно использовать для разработки поставщика Windows PowerShell. Файл TemplateProvider.cs доступен в пакете средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный шаблон доступен в каталоге **\<PowerShell samples >** Directory. Необходимо создать копию этого файла и использовать копию для создания нового поставщика Windows PowerShell, удалив все ненужные функции.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

> [!CAUTION]
> Методы поставщика свойств должны записывать любые объекты с помощью метода [System. Management. Automation. Provider. кмдлетпровидер. вритепропертйобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WritePropertyObject) .

## <a name="defining-the-windows-powershell-provider"></a>Определение поставщика Windows PowerShell

Поставщик свойств должен создать класс .NET, который поддерживает интерфейс [System. Management. Automation. Provider. ипропертикмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) . Ниже приведено объявление класса по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration](Msh_samplestestcmdlets#testcmdletspropertyproviderclassdeclaration)]  -->

## <a name="defining-base-functionality"></a>Определение базовых функций

Интерфейс [System. Management. Automation. Provider. ипропертикмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider) можно подключить к любому из базовых классов поставщика, за исключением класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Добавьте базовую функциональность, необходимую базовому классу, который вы используете. Дополнительные сведения о базовых классах см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="retrieving-properties"></a>Получение свойств

Чтобы получить свойства, поставщик должен реализовать метод [System. Management. автоматизации. Provider. ипропертикмдлетпровидер.-Property *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) для поддержки вызовов из командлета `Get-ItemProperty`. Этот метод получает свойства элемента, расположенного по указанному поставщику — внутренний путь (полный).

Параметр `providerSpecificPickList` указывает, какие свойства следует извлечь. Если этот параметр имеет значение `null` или пуст, метод должен получить все свойства. Кроме того, [System. Management. Automation. Provider. ипропертикмдлетпровидер. GetObject *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) записывает экземпляр объекта [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , представляющий контейнер свойств извлеченных свойств. Метод должен возвращать Nothing.

Рекомендуется, чтобы реализация [System. Management. Automation. Provider. ипропертикмдлетпровидер.-Property *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) поддерживала подстановочное расширение имен свойств для каждого элемента в списке выбора. Для этого используйте класс [System. Management. Automation. вилдкардпаттерн](/dotnet/api/System.Management.Automation.WildcardPattern) , чтобы выполнить сопоставление шаблонов с подстановочными знаками.

Ниже приведена реализация класса [System. Management. Automation. Provider. ипропертикмдлетпровидер.-Property *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidergetproperty)]  -->

#### <a name="things-to-remember-about-implementing-getproperty"></a>Вопросы, которые следует учитывать при реализации функции Property

Следующие условия могут быть применимы к реализации [System. Management. Automation. Provider. ипропертикмдлетпровидер. onproperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty):

- При определении класса поставщика поставщик свойств Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях в реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. WebMethod *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) необходимо убедиться, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль чтения для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, необходимо записать ошибку.

## <a name="attaching-dynamic-parameters-to-the-get-itemproperty-cmdlet"></a>Присоединение динамических параметров к командлету Get-ItemProperty

Для командлета `Get-ItemProperty` могут потребоваться дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик свойств Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) . Параметр `path` указывает полный внутренний путь к поставщику, а параметр `providerSpecificPickList` указывает свойства конкретного поставщика, указанные в командной строке. Этот параметр может быть `null` или пустым, если свойства передаются в командлет. В этом случае этот метод возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Среда выполнения Windows PowerShell использует возвращенный объект для добавления параметров в командлет.

Ниже приведена реализация класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidergetpropertydynamicparameters)]  -->

## <a name="setting-properties"></a>Установка свойств

Чтобы задать свойства, поставщик свойств Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) для поддержки вызовов из командлета `Set-ItemProperty`. Этот метод задает одно или несколько свойств элемента по указанному пути и перезаписывает указанные свойства в соответствии с требованиями. [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) также записывает экземпляр объекта [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , представляющий контейнер свойств обновленных свойств.

Ниже приведена реализация [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty](Msh_samplestestcmdlets#testcmdletspropertyprovidersetproperty)]  -->

#### <a name="things-to-remember-about-implementing-set-itemproperty"></a>Вопросы, связанные с реализацией Set-ItemProperty

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty):

- При определении класса поставщика поставщик свойств Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В этих случаях реализация метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) должна гарантировать, что путь, передаваемый в метод, соответствует требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль чтения для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, необходимо записать ошибку.

- Реализация метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции при внесении изменений в состояние системы, например при переименовании файлов. [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, с помощью среды выполнения Windows PowerShell и обрабатывая все параметры командной строки или привилегированные переменные в определении того, что должно отобразиться.

  После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, если могут быть сделаны потенциально опасные изменения системы, [ Метод System. Management. Automation. Provider. Ипропертикмдлетпровидер. SetProperty *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) должен вызывать метод [System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение с подтверждением, чтобы разрешить дополнительный отзыв, чтобы указать, что операция должна быть продолжена.

## <a name="attaching-dynamic-parameters-for-the-set-itemproperty-cmdlet"></a>Присоединение динамических параметров к командлету Set-ItemProperty

Для командлета `Set-ItemProperty` могут потребоваться дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик свойств Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) . Этот метод возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Значение `null` может быть возвращено, если не нужно добавлять динамические параметры.

Ниже приведена реализация класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyprovidersetpropertydynamicparameters)]  -->

## <a name="clearing-properties"></a>Очистка свойств

Чтобы очистить свойства, поставщик свойств Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) для поддержки вызовов из командлета `Clear-ItemProperty`. Этот метод задает одно или несколько свойств элемента, расположенного по указанному пути.

Ниже приведена реализация класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty](Msh_samplestestcmdlets#testcmdletspropertyproviderclearproperty)]  -->

#### <a name="thing-to-remember-about-implementing-clearproperty"></a>Важно помнить о реализации Клеарпроперти

Следующие условия могут применяться к реализации [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty):

- При определении класса поставщика поставщик свойств Windows PowerShell может объявлять возможности поставщика Експандвилдкардс, Filter, include или Exclude из перечисления [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . В таких случаях реализация метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) должна обеспечить соответствие пути, переданного методу, требованиям указанных возможностей. Для этого метод должен получить доступ к соответствующему свойству, например к свойствам [System. Management. Automation. Provider. кмдлетпровидер. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) и [System. Management. Automation. Provider. кмдлетпровидер. include *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) .

- По умолчанию переопределения этого метода не должны извлекать модуль чтения для объектов, которые скрыты от пользователя, если свойство [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) не имеет значение `true`. Если путь представляет элемент, который скрыт от User, а [System. Management. Automation. Provider. кмдлетпровидер. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) имеет значение `false`, необходимо записать ошибку.

- Реализация метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) должна вызывать [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) и проверять его возвращаемое значение перед внесением изменений в хранилище данных. Этот метод используется для подтверждения выполнения операции до внесения изменений в состояние системы, например для очистки содержимого. [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) отправляет имя ресурса, который будет изменен пользователю, при этом среда выполнения Windows PowerShell учитывает все параметры командной строки или привилегированные переменные при определении что следует отображать.

  После вызова метода [System. Management. Automation. Provider. кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) возвращает `true`, если могут быть сделаны потенциально опасные изменения системы, [ Метод System. Management. Automation. Provider. Ипропертикмдлетпровидер. Клеарпроперти *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) должен вызывать метод [System. Management. Automation. Provider. Кмдлетпровидер. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) . Этот метод отправляет пользователю сообщение с подтверждением, чтобы разрешить дополнительный отзыв, чтобы указать, что потенциально опасное действие должно быть продолжено.

## <a name="attaching-dynamic-parameters-to-the-clear-itemproperty-cmdlet"></a>Присоединение динамических параметров к командлету Clear-ItemProperty

Для командлета `Clear-ItemProperty` могут потребоваться дополнительные параметры, заданные динамически во время выполнения. Чтобы предоставить эти динамические параметры, поставщик свойств Windows PowerShell должен реализовать метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) . Этот метод возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) . Значение `null` может быть возвращено, если не нужно добавлять динамические параметры.

Ниже приведена реализация класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) по умолчанию из файла TemplateProvider.cs, предоставляемого Windows PowerShell.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters](Msh_samplestestcmdlets#testcmdletspropertyproviderclearpropertydynamicparameters)]  -->

## <a name="building-the-windows-powershell-provider"></a>Создание поставщика Windows PowerShell

См. раздел [Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="see-also"></a>См. также:

[Поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)
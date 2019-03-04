---
title: Создание поставщика базовый Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base provider [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], base provider
ms.assetid: 11eeea41-15c8-47ad-9016-0f4b72573305
caps.latest.revision: 7
ms.openlocfilehash: 19cc3817016d96e1412a5f3506e9d694ba55b48d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861770"
---
# <a name="creating-a-basic-windows-powershell-provider"></a>Создание базового поставщика Windows PowerShell

В этом разделе является начальной точкой для изучения способов для создания поставщика Windows PowerShell. Базовый поставщик, описанные здесь предоставляет методы для запуска и остановки поставщик, и несмотря на то, что этот поставщик не предоставляет средства для доступа к хранилищу данных или для получения или задания данные в хранилище данных, он предоставляет основные функциональные возможности, которые требуются для Все поставщики.

Как упоминалось ранее, базовый поставщик описанные здесь реализует методы для запуска и остановки поставщика. Среда выполнения Windows PowerShell вызывает эти методы для инициализации и инициализации поставщика.

> [!NOTE]
> Пример поставщика можно найти в файле AccessDBSampleProvider01.cs, предоставляемые Windows PowerShell.

Следующие подразделы этого раздела.

- [Определение класса поставщика PowerShell Windows](#Defining-the-Windows-PowerShell-Provider-Class)

- [Определение сведений о состоянии от поставщика](#Defining-Provider-Specific-State-Information)

- [Инициализация поставщика](#Initializing-the-Provider)

- [Динамические параметры запуска](#Start-Dynamic-Parameters)

- [Отмена инициализации поставщика](#Uninitializing-the-Provider)

- [Пример кода](#Code-Sample)

- [Проверка поставщика в Windows PowerShell](#Testing-the-Windows-PowerShell-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a>Определение класса поставщика PowerShell Windows

Первым шагом в создании поставщика Windows PowerShell является определение его класс .NET. Этот базовый поставщик определяется класс с именем `AccessDBProvider` , наследуемый от класса [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) базового класса.

Рекомендуется размещать ваши классы поставщика `Providers` пространство имен API пространства имен, например, xxx. PowerShell.Providers. Этот поставщик использует `Microsoft.Samples.PowerShell.Provider` пространства имен, в которой выполняются все примеры поставщиков Windows PowerShell.

> [!NOTE]
> Класс для поставщика Windows PowerShell должен быть явно помечен как общедоступный. Классы, не помеченные как открытые по умолчанию к внутренним и не будет найдена средой выполнения Windows PowerShell.

Ниже приведен в определении класса для этого базовый поставщик.

[!code-csharp[AccessDBProviderSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L23-L24 "AccessDBProviderSample01.cs")]

Прямо перед определением класса, необходимо объявить [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут, с помощью синтаксиса [CmdletProvider()].

Можно задать атрибут ключевые слова для дальнейшего объявления класса, при необходимости. Обратите внимание, что [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) здесь объявлен атрибут входят два параметра. Первый параметр атрибута указывает значение по умолчанию — понятное имя для поставщика, который пользователь может изменить позже. Второй параметр указывает возможности определяемые Windows PowerShell, которые предоставляет поставщик среды выполнения Windows PowerShell во время обработки команды. Возможные значения для возможностей поставщика определяются [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления. Так как это базовый поставщик, он поддерживает нет возможности.

> [!NOTE]
> Полное имя поставщика Windows PowerShell включает в себя имя сборки и другие атрибуты, определить с помощью Windows PowerShell после регистрации поставщика.

## <a name="defining-provider-specific-state-information"></a>Определение сведений о состоянии от поставщика

[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) базового класса и все производные классы считаются без отслеживания состояния, так как среда выполнения Windows PowerShell создает экземпляры поставщика только при необходимости. Таким образом, если поставщик требует полного доступа и состояние обслуживания для поставщика данных, он должен быть производным от класса [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) класса. Производный класс должен определять члены, необходимые для поддержания состояния, чтобы данные от поставщика может осуществляться при вызове среды выполнения Windows PowerShell [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод для инициализации поставщика.

Поставщик Windows PowerShell также могут поддерживать состояние на основе подключения. Дополнительные сведения о поддержание состояния подключения, см. в разделе [Создание поставщика диска PowerShell](./creating-a-windows-powershell-drive-provider.md).

## <a name="initializing-the-provider"></a>Инициализация поставщика

Для инициализации поставщика, вызовы среды выполнения Windows PowerShell [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод при запуске Windows PowerShell. В большинстве случаев, поставщик может использовать реализация по умолчанию этот метод, который просто возвращает [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) , описывающий поставщика. Тем не менее, в случае, где вы хотите добавить дополнительную инициализацию сведения, вам необходимо реализовать свою собственную [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод, который возвращает измененную версию [ System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) объект, передаваемый поставщику. Как правило, этот метод должен возвращать предоставленный [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) объект, передаваемый в его или измененную [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) объекта, содержит другие сведения об инициализации.

Этот базовый поставщик не Переопределите этот метод. Тем не менее приведенный ниже показана реализация по умолчанию этого метода:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

Поставщик может поддерживать состояние сведения о поставщике, как описано в разделе [состояние данных от поставщика определение](#Defining-Provider-Specific-State-Information). В этом случае необходимо переопределить реализации [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод для возврата экземпляра производного класса.

## <a name="start-dynamic-parameters"></a>Динамические параметры запуска

Реализация поставщика [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) способ может потребовать дополнительных параметров. В этом случае нужно переопределять в поставщике [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) метод и возвращают объект, имеющий свойства и поля с помощью синтаксического анализа атрибуты аналогичную Класс командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта.

Этот базовый поставщик не Переопределите этот метод. Тем не менее приведенный ниже показана реализация по умолчанию этого метода:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a>Отмена инициализации поставщика

Для освобождения ресурсов, которые использует поставщика Windows PowerShell, поставщик должен реализовать свой собственный [System.Management.Automation.Provider.Cmdletprovider.Stop*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) метод. Этот метод вызывается средой выполнения Windows PowerShell для инициализации поставщика при закрытии сеанса.

Этот базовый поставщик не Переопределите этот метод. Тем не менее приведенный ниже показана реализация по умолчанию этого метода:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a>Пример кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md).

## <a name="testing-the-windows-powershell-provider"></a>Проверка поставщика в Windows PowerShell

После регистрации поставщиком Windows PowerShell с помощью Windows PowerShell можно проверить его, выполнив Поддерживаемые командлеты в командной строке. Для этого базовый поставщик запускать новую оболочку и использовать `Get-PSProvider` командлет, чтобы получить список поставщиков и убедитесь, что поставщик AccessDb.

```powershell
Get-PSProvider
```

Появляется следующий результат:

```output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a>См. также

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)
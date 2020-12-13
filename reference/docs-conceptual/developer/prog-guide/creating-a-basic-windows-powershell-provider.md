---
ms.date: 09/13/2016
ms.topic: reference
title: Создание базового поставщика Windows PowerShell
description: Создание базового поставщика Windows PowerShell
ms.openlocfilehash: 03b5784fd063b5457fc64d92a32e286e3bf9cce4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647506"
---
# <a name="creating-a-basic-windows-powershell-provider"></a>Создание базового поставщика Windows PowerShell

Этот раздел является отправной точкой для изучения создания поставщика Windows PowerShell. Базовый поставщик, описанный здесь, предоставляет методы для запуска и остановки поставщика, и хотя этот поставщик не предоставляет средств для доступа к хранилищу данных или для получения или установки данных в хранилище данных, он предоставляет базовые функциональные возможности, необходимые для всех поставщиков.

Как упоминалось ранее, базовый поставщик, описанный здесь, реализует методы для запуска и остановки поставщика. Среда выполнения Windows PowerShell вызывает эти методы для инициализации и деинициализации поставщика.

> [!NOTE]
> Образец этого поставщика можно найти в файле AccessDBSampleProvider01.cs, предоставляемом Windows PowerShell.

## <a name="defining-the-windows-powershell-provider-class"></a>Определение класса поставщика Windows PowerShell

Первым шагом в создании поставщика Windows PowerShell является определение его класса .NET. Этот базовый поставщик определяет класс `AccessDBProvider` , производный от базового класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .

Рекомендуется размещать классы поставщиков в `Providers` пространстве имен API, например XXX. PowerShell. Providers. Этот поставщик использует `Microsoft.Samples.PowerShell.Provider` пространство имен, в котором выполняются все примеры поставщика Windows PowerShell.

> [!NOTE]
> Класс для поставщика Windows PowerShell должен быть явно помечен как открытый. Классы, не помеченные как открытые, по умолчанию будут внутренними и не будут найдены средой выполнения Windows PowerShell.

Ниже приведено определение класса для этого базового поставщика:

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="23-24":::

Непосредственно перед определением класса необходимо объявить атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) с синтаксисом [кмдлетпровидер ()].

При необходимости можно задать ключевые слова атрибутов для дальнейшего объявления класса. Обратите внимание, что объявленный здесь атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) содержит два параметра. Первый параметр атрибута указывает понятное по умолчанию имя поставщика, которое пользователь может изменить позже. Второй параметр задает определенные возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды. Возможные значения для возможностей поставщика определяются перечислением [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) . Поскольку этот поставщик является базовым, он не поддерживает никаких возможностей.

> [!NOTE]
> Полное имя поставщика Windows PowerShell содержит имя сборки и другие атрибуты, определенные Windows PowerShell при регистрации поставщика.

## <a name="defining-provider-specific-state-information"></a>Определение сведений о состоянии Provider-Specific

Базовый класс [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) и все производные классы считаются без отслеживания состояния, так как среда выполнения Windows PowerShell создает экземпляры поставщика только по мере необходимости. Таким образом, если поставщику требуется полное управление и обслуживание состояния для данных конкретного поставщика, он должен наследовать класс от класса [System. Management. Automation. провидеринфо](/dotnet/api/System.Management.Automation.ProviderInfo) . Производный класс должен определить элементы, необходимые для поддержания состояния, чтобы обеспечить доступ к данным, зависящим от поставщика, когда среда выполнения Windows PowerShell вызывает метод [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) для инициализации поставщика.

Поставщик Windows PowerShell также может поддерживать состояние на основе подключения. Дополнительные сведения о поддержке состояния подключения см. [в разделе Создание поставщика диска PowerShell](./creating-a-windows-powershell-drive-provider.md).

## <a name="initializing-the-provider"></a>Инициализация поставщика

Чтобы инициализировать поставщик, среда выполнения Windows PowerShell вызывает метод [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) при запуске Windows PowerShell. В большинстве случаев поставщик может использовать реализацию по умолчанию этого метода, который просто возвращает объект [System. Management. Automation. провидеринфо](/dotnet/api/System.Management.Automation.ProviderInfo) , описывающий поставщика. Однако в случае, когда необходимо добавить дополнительные сведения об инициализации, следует реализовать собственный метод [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) , возвращающий измененную версию объекта [System. Management. Automation. провидеринфо](/dotnet/api/System.Management.Automation.ProviderInfo) , который передается поставщику. Как правило, этот метод должен возвращать предоставленный объект [System. Management. Automation. провидеринфо](/dotnet/api/System.Management.Automation.ProviderInfo) , переданный в него, или измененный объект [System. Management. Automation. провидеринфо](/dotnet/api/System.Management.Automation.ProviderInfo) , который содержит другие сведения об инициализации.

Этот базовый поставщик не переопределяет этот метод. Однако следующий код демонстрирует реализацию этого метода по умолчанию:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

Поставщик может поддерживать состояние сведений, относящихся к поставщику, как описано в разделе [Определение состояния данных, зависящего от поставщика](#defining-provider-specific-state-information). В этом случае ваша реализация должна переопределить метод [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) , чтобы он возвращал экземпляр производного класса.

## <a name="start-dynamic-parameters"></a>Запуск динамических параметров

Реализация поставщика метода [System. Management. Automation. Provider. кмдлетпровидер. Start *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) может потребовать дополнительных параметров. В этом случае поставщик должен переопределять метод [System. Management. Automation. Provider. кмдлетпровидер. стартдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) и возвращать объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .

Этот базовый поставщик не переопределяет этот метод. Однако следующий код демонстрирует реализацию этого метода по умолчанию:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a>Отмена инициализации поставщика

Чтобы освободить ресурсы, используемые поставщиком Windows PowerShell, поставщик должен реализовать собственный метод [System. Management. Automation. Provider. кмдлетпровидер. останавливают *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) . Этот метод вызывается средой выполнения Windows PowerShell для деинициализации поставщика при закрытии сеанса.

Этот базовый поставщик не переопределяет этот метод. Однако следующий код демонстрирует реализацию этого метода по умолчанию:

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a>Образец кода

Полный пример кода см. в разделе [пример кода AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md).

## <a name="testing-the-windows-powershell-provider"></a>Тестирование поставщика Windows PowerShell

После регистрации поставщика Windows PowerShell в Windows PowerShell можно протестировать его, запустив в командной строке поддерживаемые командлеты. Для этого базового поставщика запустите новую оболочку и `Get-PSProvider` с помощью командлета извлеките список поставщиков и убедитесь в наличии поставщика акцессдб.

```powershell
Get-PSProvider
```

Отображаются следующие результаты:

```Output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a>См. также:

[Создание поставщиков Windows PowerShell](./how-to-create-a-windows-powershell-provider.md)

[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)

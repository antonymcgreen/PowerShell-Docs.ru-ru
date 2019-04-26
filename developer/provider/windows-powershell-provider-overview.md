---
title: Общие сведения о поставщике PowerShell Windows | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82244fbd-07b9-47f3-805c-3fb90ebbf58a
caps.latest.revision: 13
ms.openlocfilehash: 0d4addc0a064873701ae15c204dbd335f3374ab7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080919"
---
# <a name="windows-powershell-provider-overview"></a>Общие сведения о поставщиках Windows PowerShell

Поставщик Windows PowerShell позволяет любое хранилище данных, должен быть предоставлен как в файловой системе, как если бы он был подключенного диска. Например, встроенный поставщик реестра позволяет переходить в реестр, как перешла бы `c` диске компьютера. Можно также переопределить поставщик `Item` командлеты (например, `Get-Item`, `Set-Item`т. д.) таким образом, данные в хранилище данных, которые могут рассматриваться как файлы и каталоги, обрабатываются при навигации по файловой системе. Дополнительные сведения о поставщиках и дисков и встроенные поставщики в Windows PowerShell см. в разделе [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).

## <a name="providers-and-drives"></a>Поставщики и дисков

Поставщик определяет логику, которая используется для доступа к, перемещения и изменения в хранилище данных, во время диск указывает конкретной точкой входа для хранилища данных (или его часть в хранилище данных), принадлежащее к типу, определенной поставщиком. Например поставщик Registry позволяет обращаться к кусты и разделы в реестре и дисках HKLM и HKCU укажите соответствующий кустов реестра. Диски HKLM и HKCU использовать поставщик реестра.

При написании поставщика можно указать диски дисков по умолчанию, которые создаются автоматически, когда доступен поставщик. Можно также определить метод для создания новых дисков, которые используют этот поставщик.

## <a name="type-of-providers"></a>Тип поставщиков

Существует несколько типов поставщиков, каждый из которых предоставляет различный уровень функциональных возможностей. Поставщик реализуется как класс, производный от одного из потомков [System.Management.Automation.Sessionstatecategory.Cmdletprovider](/dotnet/api/System.Management.Automation.SessionStateCategory.CmdletProvider) класса. Сведения о различных типов поставщиков, см. в разделе [типы поставщиков](./provider-types.md).

## <a name="provider-cmdlets"></a>Командлеты поставщика

Поставщики могут реализовывать методы, соответствующие командлеты, создание пользовательских поведений для этих командлетов, при использовании на диске для данного поставщика. В зависимости от типа поставщика доступны различные наборы командлетов. Полный список командлетов, доступных для настройки в поставщиках, см. в разделе [командлеты поставщика](./provider-cmdlets.md).

## <a name="provider-paths"></a>Пути поставщика

Пользователи переходят поставщика носители, например файловых систем. По этой причине они ожидают синтаксис пути в соответствии с пути, используемые в Навигация по файловой системе. При выполнении командлета, поставщика, они укажите путь для доступа к элементу. Указываемый путь может интерпретироваться несколькими способами. Поставщик должен поддерживать один или несколько из следующих типов путь.

### <a name="drive-qualified-paths"></a>Диск с указанием пути

Диск с указанием пути представляет собой сочетание имени элемента, контейнера и подконтейнеров, в которых расположен элемент и диск Windows PowerShell, через который осуществляется элемента. (Диски определяются поставщиком, который используется для доступа к хранилищу данных. Этот путь начинается с имени диска, за которым следует двоеточие (:). Пример: `get-childitem C:`

### <a name="provider-qualified-paths"></a>Поставщик с указанием пути

Чтобы разрешить подсистемы Windows PowerShell для инициализации и отменить инициализацию поставщика, поставщик должен поддерживать путь с указанием поставщика. Например, пользователь может инициализировать и инициализации поставщика файловой системы, так как она определяет следующий путь с указанием поставщика: `FileSystem::\\uncshare\abc\bar`.

### <a name="provider-direct-paths"></a>Поставщик direct пути

Чтобы разрешить удаленный доступ к поставщику Windows PowerShell, должен поддерживать путь direct поставщика для передачи непосредственно поставщика Windows PowerShell для текущего расположения. Например, можно использовать поставщик реестра Windows PowerShell `\\server\regkeypath` как путь напрямую с поставщиками.

### <a name="provider-internal-paths"></a>Поставщик внутреннего пути

Чтобы разрешить командлету поставщика доступа к данным с помощью отличных от Windows PowerShell прикладного программирования (API), поставщик Windows PowerShell должен поддерживать поставщик внутреннего пути. Этот путь, указанный после «::» в пути поставщика с указанием. Например, поставщик: внутренняя путь для поставщика filesystem Windows PowerShell является `\\uncshare\abc\bar`.

## <a name="overriding-cmdlet-parameters"></a>Переопределение параметров командлета

Поведение некоторых командлетов поставщика можно переопределить с помощью поставщика. Список параметров, которые могут быть переопределены и как их можно переопределить в классе поставщика, см. в разделе [параметры командлета поставщика](./provider-cmdlet-parameters.md)

## <a name="dynamic-parameters"></a>Динамические параметры

Поставщики можно определить динамических параметров, которые добавляются к командлету поставщика, когда пользователь задает определенное значение для одного из статических параметров командлета. Поставщик делает это, реализовав один или несколько методов динамических параметров. Список параметров командлета, которые могут использоваться для добавления динамического параметра и методы, используемые для их реализации, см. в разделе [динамические параметры командлета поставщика](./provider-cmdlet-dynamic-parameters.md).

## <a name="provider-capabilities"></a>Возможностей поставщика

[System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисление определяет ряд возможностей, поддерживаемых поставщиков. К ним относятся возможность подстановочные элементы фильтра и поддерживает транзакции. Чтобы указать возможности для поставщика, добавьте в список значений [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления, в сочетании с логическим `OR` операции, как [ System.Management.Automation.Provider.Cmdletproviderattribute.Providercapabilities*](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities) свойство (второй параметр атрибута) [System.Management.Automation.Provider.Cmdletproviderattribute ](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибута для класса поставщика. Например, следующий атрибут указывает, что поставщик поддерживает [System.Management.Automation.Provider.Providercapabilities.Shouldprocess](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities.ShouldProcess) и [ System.Management.Automation.Provider.Providercapabilities.Transactions](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities.Transactions) возможности.

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a>Справку по командлетам поставщика

При написании поставщика, вы можете реализовать собственные справки по командлетам поставщика, вы поддерживаете. Сюда входят одного раздела справки для каждого командлета поставщика или несколько версий раздела справки для случаев, где работает командлет поставщика по-разному с помощью динамических параметров. Для поддержки конкретного командлета справки о поставщике, поставщик должен реализовывать [System.Management.Automation.Provider.Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp) интерфейс.

Вызывается подсистемой Windows PowerShell [System.Management.Automation.Provider.Icmdletprovidersupportshelp.Gethelpmaml*](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml) метод для отображения раздела справки для командлетов поставщика. Ядро предоставляет имя, заданное пользователем при выполнении командлета `Get-Help` командлета и путь текущего пользователя. Текущий путь является обязательным, если поставщик реализует различные версии того же командлета поставщика для разных дисков. Метод должен возвращать строку, которая содержит XML-код для справки по командлетам.

Содержимое файла справки написан с помощью PSMAML XML. Это той же схемой XML, который используется для записи содержимого справки для командлетов, автономный. Добавьте в него содержимое для пользовательский командлет справки к файлу справки для поставщика в разделе `CmdletHelpPaths` элемент. В следующем примере показан `command` элемента для одного поставщика, а также показано, как указать имя командлета, поставщик, поставщик. Поддерживает

```xml
<CmdletHelpPaths>
  <command:command>
    <command:details>
      <command:name>ProviderCmdletName</command:name>
      <command:verb>Verb</command:verb>
      <command:noun>Noun</command:noun>
    <command:details>
  </command:command>
<CmdletHelpPath>
```

## <a name="see-also"></a>См. также

[Функциональные возможности поставщика PowerShell Windows](./provider-types.md)

[Командлеты поставщика](./provider-cmdlets.md)

[Разработка поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
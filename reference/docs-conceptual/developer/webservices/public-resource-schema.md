---
title: Схема общих ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: 52244ee7496b99e11f0306e93728736fc9c51be5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564709"
---
# <a name="public-resource-schema"></a>Общедоступная схема ресурсов

Управление OData использует MOF для определения ресурсов и их свойств. Свойства сущности OData управления непосредственно соответствуют свойствам управляемого типа, возвращаемого базовым командлетом.

## <a name="defining-a-resource"></a>Определение ресурса

Каждый ресурс соответствует объекту, возвращенному командлетом Windows PowerShell. В MOF-файле общедоступного ресурса вы определяете ресурс, объявляя класс. Класс состоит из свойств, соответствующих свойствам объекта. Например, в следующем примере класс [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) представлен следующим MOF.

```csharp
class PswsTest_Process
{
    [Key] SInt32 Id;
    [Required] SInt32 BasePriority;
    [Required] SInt32 HandleCount;
    [Required] string MachineName;
    [Required] SInt32 MainWindowHandle;

    ...
};
```

Каждому имени свойства предшествует тип данных. Типы данных в этом примере соответствуют примитивным типам данных CLR в .NET Framework, но свойства также могут быть ссылками на другие ресурсы или сложные типы, которые описаны далее.

`Key`Квалификатор указывает, что свойство используется для уникальной идентификации экземпляра ресурса. Ресурс может иметь более одного ключа.

`Required`Квалификатор указывает, что свойство является обязательным. Если свойство помечено `Key` квалификатором, оно считается обязательным, а `Required` Квалификатор не требуется.

### <a name="complex-data-types"></a>Сложные типы данных

Свойства сущностей могут иметь сложные типы данных. Сложные типы данных — это типы, которые состоят из других типов, аналогично структурам в языке программирования C. Сложный тип объявляется в MOF-файле как класс с `ComplexType` квалификатором, как показано в следующем примере.

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

Чтобы объявить свойство сущности как сложный тип, объявите его как `string` тип с `EmbeddedInstance` квалификатором, включая имя сложного типа. В следующем примере показано объявление свойства `PswsTest_ProcessModule` типа, объявленного в предыдущем примере.

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a>Связывание сущностей

Связать две сущности можно с помощью квалификаторов Association и АссоЦиатионкласс. Дополнительные сведения см. в разделе [Сопоставление сущностей OData управления](./associating-management-odata-entities.md).

### <a name="derived-types"></a>Производные типы

Тип можно получить из другого типа. Производный тип наследует все свойства типа, от которого он является производным, помимо явно производных свойств. В следующем примере показано объявление типа, а затем объявление двух типов, производных от этого типа.

```csharp
Class Product {

    [Key] String ProductName;

};

Class DairyProduct : Product {

    Uint16 PercentFat;
};
Class POPProduct : Product {

    Boolean IsCarbonated;
};
```

---
title: Ресурс общедоступного схемы | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: c7e20ff0f36e8cab2d414ff2e5924b3359ad9c60
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080583"
---
# <a name="public-resource-schema"></a>Общедоступная схема ресурсов

OData для управления применяет MOF для определения ресурсов и их свойств. Свойства сущности OData для управления напрямую соответствуют управляемый тип, возвращаемый командлетом базового свойства.

## <a name="defining-a-resource"></a>Определение ресурса

Каждый ресурс соответствует объект, возвращаемый командлетом Windows PowerShell. В ресурс общедоступного MOF-файл можно определить ресурс, объявление класса. Класс состоит из свойств, которые соответствуют свойствам объекта. Например, в следующем примере [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) класс, представленный ниже MOF-ФАЙЛ.

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

Имя каждого свойства предшествует типом данных. Типы данных в этом примере соответствуют примитивные типы данных CLR в платформе .NET Frameworks, но свойства также могут иметь ссылки на другие ресурсы или сложные типы, которые оба описаны ниже.

`Key` Квалификатор указывает, что свойство используется для уникальной идентификации экземпляра ресурса. Ресурс может иметь более одного ключа.

`Required` Квалификатор означает, что свойство является обязательным. Если свойство имеет метку с `Key` квалификатор, он считается обязательным и `Required` квалификатора не является обязательным.

### <a name="complex-data-types"></a>Сложные типы данных

Свойства сущностей могут иметь сложные типы данных. Сложные типы данных являются типы, которые состоят из других типов, аналогичную структурам на языке программирования C. Сложный тип объявляется в MOF-файл как класс с `ComplexType` квалификатор, как показано в следующем примере.

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

Чтобы объявить свойство как сложный тип сущности, он объявляется как `string` тип с `EmbeddedInstance` квалификатор, включая имя сложного типа. В следующем примере показано объявление свойства `PswsTest_ProcessModule` тип, объявленный в предыдущем примере.

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a>Связывание сущностей

Можно связать две сущности с помощью ассоциации и AssociationClass квалификаторы. Дополнительные сведения см. в разделе [связывание сущностей OData управления](./associating-management-odata-entities.md).

### <a name="derived-types"></a>Производные типы

Можно наследовать тип от другого типа. Производный тип наследует все свойства, от которого он происходит в дополнение к любые свойства, которые явно производного типа. Пример объявления типа, а затем объявление двух типов, производных от этого типа.

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
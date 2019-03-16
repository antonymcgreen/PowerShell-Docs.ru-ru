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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057252"
---
# <a name="public-resource-schema"></a><span data-ttu-id="ca454-102">Общедоступная схема ресурсов</span><span class="sxs-lookup"><span data-stu-id="ca454-102">Public Resource Schema</span></span>

<span data-ttu-id="ca454-103">OData для управления применяет MOF для определения ресурсов и их свойств.</span><span class="sxs-lookup"><span data-stu-id="ca454-103">Management OData uses MOF to define resources and their properties.</span></span> <span data-ttu-id="ca454-104">Свойства сущности OData для управления напрямую соответствуют управляемый тип, возвращаемый командлетом базового свойства.</span><span class="sxs-lookup"><span data-stu-id="ca454-104">The properties of a Management OData entity correspond directly to the properties of the managed type returned by the underlying cmdlet.</span></span>

## <a name="defining-a-resource"></a><span data-ttu-id="ca454-105">Определение ресурса</span><span class="sxs-lookup"><span data-stu-id="ca454-105">Defining a resource</span></span>

<span data-ttu-id="ca454-106">Каждый ресурс соответствует объект, возвращаемый командлетом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca454-106">Each resource corresponds to an object returned by a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="ca454-107">В ресурс общедоступного MOF-файл можно определить ресурс, объявление класса.</span><span class="sxs-lookup"><span data-stu-id="ca454-107">In the public resource MOF file, you define a resource by declaring a class.</span></span> <span data-ttu-id="ca454-108">Класс состоит из свойств, которые соответствуют свойствам объекта.</span><span class="sxs-lookup"><span data-stu-id="ca454-108">The class consists of properties that correspond to the properties of the object.</span></span> <span data-ttu-id="ca454-109">Например, в следующем примере [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) класс, представленный ниже MOF-ФАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="ca454-109">For example, in the following example, the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) class is represented by the following MOF.</span></span>

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

<span data-ttu-id="ca454-110">Имя каждого свойства предшествует типом данных.</span><span class="sxs-lookup"><span data-stu-id="ca454-110">Each property name is preceded by a data type.</span></span> <span data-ttu-id="ca454-111">Типы данных в этом примере соответствуют примитивные типы данных CLR в платформе .NET Frameworks, но свойства также могут иметь ссылки на другие ресурсы или сложные типы, которые оба описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="ca454-111">The data types in this example correspond to primitive CLR data types in the .NET Frameworks, but properties can also be references to other resources or complex types, which are both described later.</span></span>

<span data-ttu-id="ca454-112">`Key` Квалификатор указывает, что свойство используется для уникальной идентификации экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="ca454-112">The `Key` qualifier indicates that a property is used to uniquely identify a resource instance.</span></span> <span data-ttu-id="ca454-113">Ресурс может иметь более одного ключа.</span><span class="sxs-lookup"><span data-stu-id="ca454-113">A resource can have more than one key.</span></span>

<span data-ttu-id="ca454-114">`Required` Квалификатор означает, что свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ca454-114">The `Required` qualifier indicates that the property is required.</span></span> <span data-ttu-id="ca454-115">Если свойство имеет метку с `Key` квалификатор, он считается обязательным и `Required` квалификатора не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ca454-115">If a property is labeled with the `Key` qualifier, it is considered to be required, and the `Required` qualifier is not necessary.</span></span>

### <a name="complex-data-types"></a><span data-ttu-id="ca454-116">Сложные типы данных</span><span class="sxs-lookup"><span data-stu-id="ca454-116">Complex data types</span></span>

<span data-ttu-id="ca454-117">Свойства сущностей могут иметь сложные типы данных.</span><span class="sxs-lookup"><span data-stu-id="ca454-117">Properties of entities can have complex data types.</span></span> <span data-ttu-id="ca454-118">Сложные типы данных являются типы, которые состоят из других типов, аналогичную структурам на языке программирования C.</span><span class="sxs-lookup"><span data-stu-id="ca454-118">Complex data types are types that are made up of other types, similar to structs in the C programming language.</span></span> <span data-ttu-id="ca454-119">Сложный тип объявляется в MOF-файл как класс с `ComplexType` квалификатор, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ca454-119">A complex type is declared in the MOF file as a class with the `ComplexType` qualifier, as in the following example.</span></span>

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

<span data-ttu-id="ca454-120">Чтобы объявить свойство как сложный тип сущности, он объявляется как `string` тип с `EmbeddedInstance` квалификатор, включая имя сложного типа.</span><span class="sxs-lookup"><span data-stu-id="ca454-120">To declare an entity property as a complex type, you declare it as a `string` type with the `EmbeddedInstance` qualifier, including the name of the complex type.</span></span> <span data-ttu-id="ca454-121">В следующем примере показано объявление свойства `PswsTest_ProcessModule` тип, объявленный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="ca454-121">The following example shows the declaration of a property of the `PswsTest_ProcessModule` type declared in the previous example.</span></span>

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a><span data-ttu-id="ca454-122">Связывание сущностей</span><span class="sxs-lookup"><span data-stu-id="ca454-122">Associating entities</span></span>

<span data-ttu-id="ca454-123">Можно связать две сущности с помощью ассоциации и AssociationClass квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="ca454-123">You can associate two entities by using the Association and AssociationClass qualifiers.</span></span> <span data-ttu-id="ca454-124">Дополнительные сведения см. в разделе [связывание сущностей OData управления](./associating-management-odata-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ca454-124">For more information, see [Associating Management OData Entities](./associating-management-odata-entities.md).</span></span>

### <a name="derived-types"></a><span data-ttu-id="ca454-125">Производные типы</span><span class="sxs-lookup"><span data-stu-id="ca454-125">Derived types</span></span>

<span data-ttu-id="ca454-126">Можно наследовать тип от другого типа.</span><span class="sxs-lookup"><span data-stu-id="ca454-126">You can derive a type from another type.</span></span> <span data-ttu-id="ca454-127">Производный тип наследует все свойства, от которого он происходит в дополнение к любые свойства, которые явно производного типа.</span><span class="sxs-lookup"><span data-stu-id="ca454-127">The derived type inherits all of the properties of the type from which it derives in addition to any properties explicitly derived.</span></span> <span data-ttu-id="ca454-128">Пример объявления типа, а затем объявление двух типов, производных от этого типа.</span><span class="sxs-lookup"><span data-stu-id="ca454-128">The following example shows a type declaration and then a declaration of two types derived from that type.</span></span>

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
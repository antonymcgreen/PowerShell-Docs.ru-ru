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
ms.openlocfilehash: a9204ca7b28fc5792ef9bd18f6b0b24964de7386
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859550"
---
# <a name="public-resource-schema"></a><span data-ttu-id="8d9a4-102">Общедоступная схема ресурсов</span><span class="sxs-lookup"><span data-stu-id="8d9a4-102">Public Resource Schema</span></span>

<span data-ttu-id="8d9a4-103">OData для управления применяет MOF для определения ресурсов и их свойств.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-103">Management OData uses MOF to define resources and their properties.</span></span> <span data-ttu-id="8d9a4-104">Свойства сущности OData для управления напрямую соответствуют управляемый тип, возвращаемый командлетом базового свойства.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-104">The properties of a Management OData entity correspond directly to the properties of the managed type returned by the underlying cmdlet.</span></span>

## <a name="defining-a-resource"></a><span data-ttu-id="8d9a4-105">Определение ресурса</span><span class="sxs-lookup"><span data-stu-id="8d9a4-105">Defining a resource</span></span>

<span data-ttu-id="8d9a4-106">Каждый ресурс соответствует объект, возвращаемый командлетом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-106">Each resource corresponds to an object returned by a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="8d9a4-107">В файле MOF ресурсов publc определить ресурс путем объявления класса.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-107">In the publc resource MOF file, you define a resource by declaring a class.</span></span> <span data-ttu-id="8d9a4-108">Класс состоит из свойств, которые соответствуют свойствам объекта.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-108">The class consists of properties that correspond to the properties of the object.</span></span> <span data-ttu-id="8d9a4-109">Например, в следующем примере [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) класс, представленный ниже MOF-ФАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-109">For example, in the following example, the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) class is represented by the following MOF.</span></span>

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

<span data-ttu-id="8d9a4-110">Имя каждого свойства предшествует типом данных.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-110">Each property name is preceded by a data type.</span></span> <span data-ttu-id="8d9a4-111">Типы данных в этом примере соответствуют примитивные типы данных CLR в платформе .NET Frameworks, но свойства также могут иметь ссылки на другие ресурсы или сложные типы, которые оба описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-111">The data types in this example correspond to primitive CLR data types in the .NET Frameworks, but properties can also be references to other resources or complex types, which are both described later.</span></span>

<span data-ttu-id="8d9a4-112">`Key` Квалификатор указывает, что свойство используется для уникальной идентификации экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-112">The `Key` qualifier indicates that a property is used to uniquely identify a resource instance.</span></span> <span data-ttu-id="8d9a4-113">Ресурс может иметь более одного ключа.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-113">A resource can have more than one key.</span></span>

<span data-ttu-id="8d9a4-114">`Required` Квалификатор означает, что свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-114">The `Required` qualifier indicates that the property is required.</span></span> <span data-ttu-id="8d9a4-115">Если свойство имеет метку с `Key` квалификатор, он считается обязательным и `Required` квалификатора не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-115">If a property is labeled with the `Key` qualifier, it is considered to be required, and the `Required` qualifier is not necessary.</span></span>

### <a name="complex-data-types"></a><span data-ttu-id="8d9a4-116">Сложные типы данных</span><span class="sxs-lookup"><span data-stu-id="8d9a4-116">Complex data types</span></span>

<span data-ttu-id="8d9a4-117">Свойства сущностей могут иметь сложные типы данных.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-117">Properties of entities can have complex data types.</span></span> <span data-ttu-id="8d9a4-118">Сложные типы данных являются типы, которые состоят из других типов, аналогичную структурам на языке программирования C.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-118">Complex data types are types that are made up of other types, similar to structs in the C programming language.</span></span> <span data-ttu-id="8d9a4-119">Сложный тип объявляется в MOF-файл как класс с `ComplexType` квалификатор, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-119">A complex type is declared in the MOF file as a class with the `ComplexType` qualifier, as in the following example.</span></span>

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

<span data-ttu-id="8d9a4-120">Чтобы объявить свойство как сложный тип сущности, он объявляется как `string` тип с `EmbeddedInstance` квалификатор, включая имя сложного типа.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-120">To declare an entity property as a complex type, you declare it as a `string` type with the `EmbeddedInstance` qualifier, including the name of the complex type.</span></span> <span data-ttu-id="8d9a4-121">Следующий пример hshows объявление свойства из `PswsTest_ProcessModule` тип, объявленный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-121">The following example hshows the declaration of a property of the `PswsTest_ProcessModule` type declared in the previous example.</span></span>

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a><span data-ttu-id="8d9a4-122">Связывание сущностей</span><span class="sxs-lookup"><span data-stu-id="8d9a4-122">Associating entities</span></span>

<span data-ttu-id="8d9a4-123">Можно связать две сущности с помощью ассоциации и AssocationClass квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-123">You can associate two entities by using the Association and AssocationClass qualifiers.</span></span> <span data-ttu-id="8d9a4-124">Дополнительные сведения см. в разделе [связывание сущностей OData управления](./associating-management-odata-entities.md).</span><span class="sxs-lookup"><span data-stu-id="8d9a4-124">For more information, see [Associating Management OData Entities](./associating-management-odata-entities.md).</span></span>

### <a name="derived-types"></a><span data-ttu-id="8d9a4-125">Производные типы</span><span class="sxs-lookup"><span data-stu-id="8d9a4-125">Derived types</span></span>

<span data-ttu-id="8d9a4-126">Можно наследовать тип от другого типа.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-126">You can derive a type from another type.</span></span> <span data-ttu-id="8d9a4-127">Производный тип наследует все свойства, от которого он происходит в дополнение к любые свойства, которые явно производного типа.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-127">The derived type inherits all of the properties of the type from which it derives in addition to any properties explicitly derived.</span></span> <span data-ttu-id="8d9a4-128">Пример объявления типа, а затем объявление двух типов, производных от этого типа.</span><span class="sxs-lookup"><span data-stu-id="8d9a4-128">The following example shows a type declaration and then a declaration of two types derived from that type.</span></span>

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
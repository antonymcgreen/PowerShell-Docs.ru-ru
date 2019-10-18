---
title: Связывание сущностей OData управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 947a3add-3593-400d-8144-8b44c8adbe5e
caps.latest.revision: 5
ms.openlocfilehash: 44b718e024eb98ac562edb50076287a31f5edc6b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359813"
---
# <a name="associating-management-odata-entities"></a><span data-ttu-id="294c6-102">Связывание сущностей управления OData</span><span class="sxs-lookup"><span data-stu-id="294c6-102">Associating Management OData Entities</span></span>

<span data-ttu-id="294c6-103">Часто бывает полезно создать ассоциацию между двумя разными сущностями OData управления.</span><span class="sxs-lookup"><span data-stu-id="294c6-103">It is often useful to create an association between two different Management OData entities.</span></span> <span data-ttu-id="294c6-104">Например, служба OData управления может иметь сущности, которые управляют каталогом продуктов, упорядоченных по категориям, и определяют сущности `Product` и `Category`.</span><span class="sxs-lookup"><span data-stu-id="294c6-104">For example, a Management OData service could have entities that manage a catalogue of products that are organized in categories, and define the entities `Product` and `Category`.</span></span> <span data-ttu-id="294c6-105">Связав эти две сущности, клиент может получить сведения обо всех продуктах в категории с одним запросом к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="294c6-105">By associating these two entities, a client can get information about all of the products in a category with a single request to the web service.</span></span>

<span data-ttu-id="294c6-106">Пример, демонстрирующий создание связей между сущностями, можно скачать в [примере Association](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span><span class="sxs-lookup"><span data-stu-id="294c6-106">A sample that shows how to create associations between entities can be downloaded at [Association sample](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span></span>

## <a name="creating-the-association-in-the-resource-schema-file"></a><span data-ttu-id="294c6-107">Создание связи в файле схемы ресурса</span><span class="sxs-lookup"><span data-stu-id="294c6-107">Creating the Association in the resource schema file</span></span>

<span data-ttu-id="294c6-108">Следующий MOF определяет две сущности.</span><span class="sxs-lookup"><span data-stu-id="294c6-108">The following MOF defines two entities.</span></span> <span data-ttu-id="294c6-109">Мы создадим связь между ними.</span><span class="sxs-lookup"><span data-stu-id="294c6-109">We will create an association between them.</span></span>

```csharp
class Product {

[key] string ProductName;

// other fields ...
};

class Category {

[key] string CategoryName;

string Products[];

// other fields
}
```

<span data-ttu-id="294c6-110">Класс `Category` определяет свойство, которое является массивом имен продуктов, принадлежащих к этой категории.</span><span class="sxs-lookup"><span data-stu-id="294c6-110">The `Category` class defines a property that is an array of the names of the products that belong to that category.</span></span>

<span data-ttu-id="294c6-111">Чтобы связать две сущности, необходимо определить класс с атрибутом `Association` в MOF-файле схемы ресурса для службы.</span><span class="sxs-lookup"><span data-stu-id="294c6-111">To associate two entities, you must define a class with the `Association` attribute in the resource schema MOF file for the service.</span></span> <span data-ttu-id="294c6-112">Класс должен определять две связываемые сущности, которые называются `ends` ассоциации.</span><span class="sxs-lookup"><span data-stu-id="294c6-112">The class must define the two entities to be associated, called `ends` of the association.</span></span> <span data-ttu-id="294c6-113">В следующем примере показано определение класса, определяющего связь между сущностями Category и Products.</span><span class="sxs-lookup"><span data-stu-id="294c6-113">The following example shows a definition of a class that defines an association between the Category and Products entities.</span></span>

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

<span data-ttu-id="294c6-114">Также необходимо изменить объявление свойства Products в классе Category.</span><span class="sxs-lookup"><span data-stu-id="294c6-114">You must also change the declaration of the Products property in the Category class.</span></span> <span data-ttu-id="294c6-115">Используйте ключевое слово `AssociationClass`, чтобы указать, что свойство является одним окончанием ассоциации.</span><span class="sxs-lookup"><span data-stu-id="294c6-115">You use the `AssociationClass` keyword to specify that the property is one end of the association.</span></span> <span data-ttu-id="294c6-116">Свойство также должно быть определено как ссылка на отдельную сущность, а не на массив строк.</span><span class="sxs-lookup"><span data-stu-id="294c6-116">The property must also be defined as a reference to a separate entity, rather than an array of strings.</span></span> <span data-ttu-id="294c6-117">Для этого используется ключевое слово `ref`.</span><span class="sxs-lookup"><span data-stu-id="294c6-117">You do this by using the `ref` keyword.</span></span> <span data-ttu-id="294c6-118">В следующем примере показано определение свойства для ассоциации.</span><span class="sxs-lookup"><span data-stu-id="294c6-118">The following example shows the property definition for the association.</span></span>

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

<span data-ttu-id="294c6-119">Наконец, необходимо объявить другой конец ассоциации, добавив определение свойства в класс `Product`.</span><span class="sxs-lookup"><span data-stu-id="294c6-119">Finally, you must declare the other end of the association by adding a property definition to the `Product` class.</span></span> <span data-ttu-id="294c6-120">Это ссылка на массив или на отдельную сущность.</span><span class="sxs-lookup"><span data-stu-id="294c6-120">This is a reference to either an array or to a single entity.</span></span> <span data-ttu-id="294c6-121">Предполагая, что каждый продукт принадлежит только одной категории, определение будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="294c6-121">Assuming that each product belongs to only one category, the definition would be as follows.</span></span>

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

<span data-ttu-id="294c6-122">Свойства, представляющие две конечные точки ассоциации, называются свойствами навигации.</span><span class="sxs-lookup"><span data-stu-id="294c6-122">The properties that represent the two ends of the association are called navigation properties.</span></span>

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a><span data-ttu-id="294c6-123">Действия по связыванию сущностей в файле схемы ресурса</span><span class="sxs-lookup"><span data-stu-id="294c6-123">Steps for associating entities in the resource schema file</span></span>

- <span data-ttu-id="294c6-124">Определите ассоциацию как класс с помощью ключевого слова `Association`.</span><span class="sxs-lookup"><span data-stu-id="294c6-124">Define the association as a class by using the `Association` keyword.</span></span>

- <span data-ttu-id="294c6-125">Определите конечные точки ассоциации с помощью ключевого слова АссоЦиатионкласс для уточнения свойств связанных сущностей.</span><span class="sxs-lookup"><span data-stu-id="294c6-125">Define the ends of the association by using the AssociationClass keyword to qualify properties of the associated entities.</span></span>

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a><span data-ttu-id="294c6-126">Создание связи в XML-файле сопоставления ресурсов</span><span class="sxs-lookup"><span data-stu-id="294c6-126">Creating the association in the resource mapping XML file</span></span>

<span data-ttu-id="294c6-127">Существует три разных варианта, которые следует учитывать при сопоставлении ассоциации в XML-файле сопоставления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="294c6-127">There are three different cases to consider when mapping an association in the resource mapping XML file.</span></span>

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a><span data-ttu-id="294c6-128">Определение способа связывания сущностей в файле сопоставления ресурсов</span><span class="sxs-lookup"><span data-stu-id="294c6-128">Determining how to associate entities in the resource mapping file</span></span>

- <span data-ttu-id="294c6-129">Значение, если свойство навигации имеется в базовом.</span><span class="sxs-lookup"><span data-stu-id="294c6-129">If the navigation property is present in the underlying.</span></span> <span data-ttu-id="294c6-130">.NET Framework тип, а это свойство содержит внешние ключи, явное сопоставление не требуется.</span><span class="sxs-lookup"><span data-stu-id="294c6-130">.NET Framework type, and that property contains foreign keys, no explicit mapping is necessary.</span></span>

- <span data-ttu-id="294c6-131">Если свойство навигации не существует в базовом типе .NET Framework, необходимо указать командлет, который получает список ключей связанных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="294c6-131">If the navigation property does not exist in the underlying .NET Framework type, you must specify a cmdlet that retrieves the list of keys of the associated instances.</span></span> <span data-ttu-id="294c6-132">Это можно сделать, добавив элемент `Association`, вложенный в элемент `CmdletImplementation`, после элементов, определяющих `cmdlets` для других команд CRUD.</span><span class="sxs-lookup"><span data-stu-id="294c6-132">You do this by adding an `Association` element nested under the `CmdletImplementation` element, following the elements that define the `cmdlets` for the other CRUD commands.</span></span>

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- <span data-ttu-id="294c6-133">Если свойство навигации существует в базовом типе .NET Framework, но оно содержит экземпляры объектов вместо внешних ключей, необходимо создать командлет (путем написания функции или скрипта Windows PowerShell) для получения внешних ключей.</span><span class="sxs-lookup"><span data-stu-id="294c6-133">If the navigation property does exist in the underlying .NET Framework type, but it contains object instances instead of foreign keys, then you must create a cmdlet (by writing a Windows PowerShell function or script) to retrieve the foreign keys.</span></span> <span data-ttu-id="294c6-134">Затем необходимо указать этот командлет в файле сопоставления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="294c6-134">You then specify that cmdlet in the resource mapping file.</span></span> <span data-ttu-id="294c6-135">Например, сценарий для извлечения ключей будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="294c6-135">For example, the script to retrieve the keys would look like the following.</span></span>

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  <span data-ttu-id="294c6-136">XML-код в файле сопоставления ресурсов будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="294c6-136">And the XML in the resource mapping file would look like the following.</span></span>

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory.ps1</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- <span data-ttu-id="294c6-137">Помимо указания командлета для получения связанных сущностей, можно также указать командлеты для добавления и удаления ссылок из коллекции.</span><span class="sxs-lookup"><span data-stu-id="294c6-137">In addition to specifying a cmdlet to retrieve the associated entities, you can also specify cmdlets to add and remove references from the collection.</span></span> <span data-ttu-id="294c6-138">В следующем примере предполагается, что командлеты Add-Продукттокатегори и Remove-Продуктфромкатегори существуют (они также могут быть определены в скрипте или функции, как в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="294c6-138">The following example assumes that the Add-ProductToCategory and Remove-ProductFromCategory cmdlets exist (they can also be defined in a script or function as in the previous example).</span></span>

  ```xml
  Class Name="Sample.Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
  ...
              </GetReference>
        <AddReference>
     <CmdletName>"Add-ProductToCategory"</>
     <ParameterForThisObject>"Product"</>
     <ParameterForReferredObject>"Category"</>
        </AddReference>
        <RemoveReference>
     <CmdletName="Remove-ProductFromCategory"/>
     <ParameterForThisObject >"Product"</>
     <ParameterForReferredObject >"Category"</>
        </RemoveReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

## <a name="querying-associated-entities"></a><span data-ttu-id="294c6-139">Запрос связанных сущностей</span><span class="sxs-lookup"><span data-stu-id="294c6-139">Querying associated entities</span></span>

<span data-ttu-id="294c6-140">Клиент может получить список экземпляров, связанных с сущностью, путем создания конкретных запросов.</span><span class="sxs-lookup"><span data-stu-id="294c6-140">The client can retrieve a list of the instances associated with an entity by creating specific queries.</span></span>

#### <a name="constructing-queries-for-associated-entities"></a><span data-ttu-id="294c6-141">Создание запросов для связанных сущностей</span><span class="sxs-lookup"><span data-stu-id="294c6-141">Constructing queries for associated entities</span></span>

- <span data-ttu-id="294c6-142">Клиент может запросить сведения о категории, не получая связанные с ней продукты.</span><span class="sxs-lookup"><span data-stu-id="294c6-142">A client can request the details of a category without retrieving its associated products.</span></span> <span data-ttu-id="294c6-143">Например, следующий запрос получает сведения о категории `food`.</span><span class="sxs-lookup"><span data-stu-id="294c6-143">For example, the following request gets details of the `food` category.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  <span data-ttu-id="294c6-144">Чтобы получить связанные продукты категории (но не сведения о самой категории, клиент указывает свойство навигации в запросе.</span><span class="sxs-lookup"><span data-stu-id="294c6-144">To get the associated products of the category (but not details of the category itself, the client specifies the navigation property in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- <span data-ttu-id="294c6-145">Чтобы получить только URL-адреса продуктов, используйте квалификатор `$links` в запросе.</span><span class="sxs-lookup"><span data-stu-id="294c6-145">To retrieve only URLs of the products, use the `$links` qualifier in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- <span data-ttu-id="294c6-146">Клиент может получить сведения о категории и связанных с ней продуктах с помощью квалификатора `$expand`.</span><span class="sxs-lookup"><span data-stu-id="294c6-146">The client can get both the category details and its associated products by using the `$expand` qualifier.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a><span data-ttu-id="294c6-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="294c6-147">See Also</span></span>

[<span data-ttu-id="294c6-148">Создание веб-службы управления OData расширения IIS</span><span class="sxs-lookup"><span data-stu-id="294c6-148">Creating a Management OData IIS Extension Web Service</span></span>](./creating-a-management-odata-web-service.md)
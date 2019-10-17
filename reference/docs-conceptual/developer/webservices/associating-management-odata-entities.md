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
# <a name="associating-management-odata-entities"></a>Связывание сущностей управления OData

Часто бывает полезно создать ассоциацию между двумя разными сущностями OData управления. Например, служба OData управления может иметь сущности, которые управляют каталогом продуктов, упорядоченных по категориям, и определяют сущности `Product` и `Category`. Связав эти две сущности, клиент может получить сведения обо всех продуктах в категории с одним запросом к веб-службе.

Пример, демонстрирующий создание связей между сущностями, можно скачать в [примере Association](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).

## <a name="creating-the-association-in-the-resource-schema-file"></a>Создание связи в файле схемы ресурса

Следующий MOF определяет две сущности. Мы создадим связь между ними.

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

Класс `Category` определяет свойство, которое является массивом имен продуктов, принадлежащих к этой категории.

Чтобы связать две сущности, необходимо определить класс с атрибутом `Association` в MOF-файле схемы ресурса для службы. Класс должен определять две связываемые сущности, которые называются `ends` ассоциации. В следующем примере показано определение класса, определяющего связь между сущностями Category и Products.

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

Также необходимо изменить объявление свойства Products в классе Category. Используйте ключевое слово `AssociationClass`, чтобы указать, что свойство является одним окончанием ассоциации. Свойство также должно быть определено как ссылка на отдельную сущность, а не на массив строк. Для этого используется ключевое слово `ref`. В следующем примере показано определение свойства для ассоциации.

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

Наконец, необходимо объявить другой конец ассоциации, добавив определение свойства в класс `Product`. Это ссылка на массив или на отдельную сущность. Предполагая, что каждый продукт принадлежит только одной категории, определение будет выглядеть следующим образом.

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

Свойства, представляющие две конечные точки ассоциации, называются свойствами навигации.

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>Действия по связыванию сущностей в файле схемы ресурса

- Определите ассоциацию как класс с помощью ключевого слова `Association`.

- Определите конечные точки ассоциации с помощью ключевого слова АссоЦиатионкласс для уточнения свойств связанных сущностей.

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>Создание связи в XML-файле сопоставления ресурсов

Существует три разных варианта, которые следует учитывать при сопоставлении ассоциации в XML-файле сопоставления ресурсов.

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>Определение способа связывания сущностей в файле сопоставления ресурсов

- Значение, если свойство навигации имеется в базовом. .NET Framework тип, а это свойство содержит внешние ключи, явное сопоставление не требуется.

- Если свойство навигации не существует в базовом типе .NET Framework, необходимо указать командлет, который получает список ключей связанных экземпляров. Это можно сделать, добавив элемент `Association`, вложенный в элемент `CmdletImplementation`, после элементов, определяющих `cmdlets` для других команд CRUD.

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

- Если свойство навигации существует в базовом типе .NET Framework, но оно содержит экземпляры объектов вместо внешних ключей, необходимо создать командлет (путем написания функции или скрипта Windows PowerShell) для получения внешних ключей. Затем необходимо указать этот командлет в файле сопоставления ресурсов. Например, сценарий для извлечения ключей будет выглядеть следующим образом.

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  XML-код в файле сопоставления ресурсов будет выглядеть следующим образом.

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

- Помимо указания командлета для получения связанных сущностей, можно также указать командлеты для добавления и удаления ссылок из коллекции. В следующем примере предполагается, что командлеты Add-Продукттокатегори и Remove-Продуктфромкатегори существуют (они также могут быть определены в скрипте или функции, как в предыдущем примере).

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

## <a name="querying-associated-entities"></a>Запрос связанных сущностей

Клиент может получить список экземпляров, связанных с сущностью, путем создания конкретных запросов.

#### <a name="constructing-queries-for-associated-entities"></a>Создание запросов для связанных сущностей

- Клиент может запросить сведения о категории, не получая связанные с ней продукты. Например, следующий запрос получает сведения о категории `food`.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  Чтобы получить связанные продукты категории (но не сведения о самой категории, клиент указывает свойство навигации в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- Чтобы получить только URL-адреса продуктов, используйте квалификатор `$links` в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- Клиент может получить сведения о категории и связанных с ней продуктах с помощью квалификатора `$expand`.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>См. также:

[Создание веб-службы управления OData расширения IIS](./creating-a-management-odata-web-service.md)
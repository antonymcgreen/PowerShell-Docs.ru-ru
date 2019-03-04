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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860830"
---
# <a name="associating-management-odata-entities"></a>Связывание сущностей управления OData

Часто бывает полезно создать ассоциацию между двумя разными субъектами OData для управления. Например, службы OData для управления может содержать сущности, которые управляют каталог продуктов, которые распределены по категориям и определения сущностей `Product` и `Category`. Связав эти две сущности, клиент сможет получить сведения обо всех продуктов в категории с отдельным запросом к веб-службе.

Пример, показывающий, как создавать связи между сущностями можно загрузить по адресу [пример ассоциации](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).

## <a name="creating-the-association-in-the-resource-schema-file"></a>Создание ассоциаций в файле схемы ресурсов

Следующие MOF-ФАЙЛ определяет две сущности. Мы создадим связь между ними.

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

`Category` Класс определяет свойство, которое представляет собой массив имена продуктов, относящихся к этой категории.

Чтобы связать две сущности, необходимо определить класс с `Association` атрибут в MOF-файл схемы ресурсов для службы. В классе необходимо определить две сущности, связанные, вызывается `ends` ассоциации. В следующем примере показано определение класса, который определяет ассоциацию между сущностями «категория» и «продукты.

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

Также необходимо изменить объявление свойства в классе категории продуктов. Использовании `AssociationClass` ключевое слово, чтобы указать, что свойство является окончанием ассоциации. Свойство также должен быть определен как ссылка на отдельную сущность, а не массив строк. Это делается с помощью `ref` ключевое слово. Следующий пример показывает определение свойства для ассоциации.

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

Наконец, необходимо объявить другой стороне ассоциации, добавив определение свойств к `Product` класса. Это ссылка либо массив или к одной сущности. Предположим, что каждый продукт принадлежит только одной категории, определение будет выглядеть следующим образом.

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

Свойства, которые соответствуют двум концам связи называются свойствами навигации.

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>Шаги для связывания сущностей в файле схемы ресурсов

- Определение связи в виде класса с помощью `Association` ключевое слово.

- Определите конечные точки ассоциации с помощью ключевого слова AssociationClass для определения свойств, сопоставленных сущностей.

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>Создание ассоциаций в XML-файле сопоставление ресурсов

Существует три различных сценария при сопоставлении ассоциации в XML-файл сопоставления ресурсов.

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>Определение того, как связывать сущности в файле сопоставления ресурсов

- При наличии в базовом свойство навигации. Тип платформы .NET framework и это свойство содержит внешние ключи, явное сопоставление не требуется.

- Если свойство навигации не существует в базовом типе платформы .NET Framework, необходимо указать командлет, который получает список ключей из связанных экземпляров. Это можно сделать, добавив `Association` элемент вложен в узел `CmdletImplementation` элемент, следующие элементы, определяющие `cmdlets` для других команд CRUD.

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

- Если свойство навигации существует в базовый тип .NET Framework, но он содержит экземпляры объектов, а не внешние ключи, то необходимо создать командлет (путем написания функции Windows PowerShell или скрипт) для получения внешних ключей. Затем задайте этому командлету в файле сопоставления ресурсов. Например сценарий для получения ключей будет выглядеть следующим образом.

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  И XML-данные в файле сопоставления ресурсов будет выглядеть следующим образом.

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

- Помимо указания командлетом для извлечения связанных сущностей, можно также указать командлеты для добавления и удаления ссылки из коллекции. В следующем примере предполагается, что существуют командлеты Add ProductToCategory и Remove-ProductFromCategory (их можно также определить в сценарии или функции, как показано в предыдущем примере).

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

Клиент может получить список экземпляров, связанных с сущностью, создав конкретных запросов.

#### <a name="constructing-queries-for-associated-entities"></a>Создание запросов для связанных сущностей

- Клиент может запрашивать сведения о категории, не извлекая его соответствующих продуктов. Например, следующий запрос возвращает сведения об `food` категории.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  Чтобы получить соответствующие продукты категории (но не сведения о категории, клиент указывает свойство навигации в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- Чтобы получить только URL-адреса из продуктов, используйте `$links` квалификатор в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- Клиента можно получить с помощью сведений о категории и соответствующие продукты `$expand` квалификатор.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>См. также

[Создание веб-служба управления расширение OData IIS](./creating-a-management-odata-web-service.md)
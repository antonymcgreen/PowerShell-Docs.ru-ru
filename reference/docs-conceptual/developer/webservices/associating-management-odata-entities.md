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
ms.openlocfilehash: 4849735bf412497f5590b109c67760b6a197cb2b
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561738"
---
# <a name="associating-management-odata-entities"></a>Связывание сущностей управления OData

Часто бывает полезно создать ассоциацию между двумя разными сущностями OData управления. Например, служба OData управления может иметь сущности, которые управляют каталогом продуктов, упорядоченных по категориям, и определяют сущности `Product` и `Category` . Связав эти две сущности, клиент может получить сведения обо всех продуктах в категории с одним запросом к веб-службе.

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

`Category`Класс определяет свойство, которое является массивом имен продуктов, принадлежащих к этой категории.

Чтобы связать две сущности, необходимо определить класс с `Association` атрибутом в MOF-файле схемы ресурса для службы. Класс должен определять две связываемые сущности, называемые `ends` связью. В следующем примере показано определение класса, определяющего связь между сущностями Category и Products.

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

Также необходимо изменить объявление свойства Products в классе Category. Используйте `AssociationClass` ключевое слово, чтобы указать, что свойство является одним окончанием ассоциации. Свойство также должно быть определено как ссылка на отдельную сущность, а не на массив строк. Для этого используется `ref` ключевое слово. В следующем примере показано определение свойства для ассоциации.

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

Наконец, необходимо объявить другой конец ассоциации, добавив определение свойства в `Product` класс. Это ссылка на массив или на отдельную сущность. Предполагая, что каждый продукт принадлежит только одной категории, определение будет выглядеть следующим образом.

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

Свойства, представляющие две конечные точки ассоциации, называются свойствами навигации.

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>Действия по связыванию сущностей в файле схемы ресурса

- Определите ассоциацию как класс с помощью `Association` ключевого слова.

- Определите конечные точки ассоциации с помощью ключевого слова АссоЦиатионкласс для уточнения свойств связанных сущностей.

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>Создание связи в XML-файле сопоставления ресурсов

Существует три разных варианта, которые следует учитывать при сопоставлении ассоциации в XML-файле сопоставления ресурсов.

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>Определение способа связывания сущностей в файле сопоставления ресурсов

- Значение, если свойство навигации имеется в базовом. .NET Framework тип, а это свойство содержит внешние ключи, явное сопоставление не требуется.

- Если свойство навигации не существует в базовом типе .NET Framework, необходимо указать командлет, который получает список ключей связанных экземпляров. Это делается путем добавления `Association` элемента, вложенного в `CmdletImplementation` элемент, после элементов, определяющих `cmdlets` для других команд CRUD.

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

- Клиент может запросить сведения о категории, не получая связанные с ней продукты. Например, следующий запрос получает сведения о `food` категории.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  Чтобы получить связанные продукты категории (но не сведения о самой категории, клиент указывает свойство навигации в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- Чтобы получить только URL-адреса продуктов, используйте `$links` квалификатор в запросе.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- Клиент может получить сведения о категории и связанных с ней продуктах с помощью `$expand` квалификатора.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>См. также:

[Создание веб-службы управления OData расширения IIS](./creating-a-management-odata-web-service.md)

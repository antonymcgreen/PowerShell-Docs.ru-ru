---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Environment в DSC
ms.openlocfilehash: d8519a66d457767dcbc0e08b01a69a9264997479
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464423"
---
# <a name="dsc-environment-resource"></a>Ресурс Environment в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Environment** в DSC Windows PowerShell предоставляет механизм управления системными переменными среды.

## <a name="syntax"></a>Синтаксис

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Target = [string] { Process | Machine } ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|Имя |Указывает имя переменной среды, для которой требуется обеспечить определенное состояние. |
|путь |Определяет настраиваемую переменную среды. Для переменной **Path** присвойте этому свойству значение `$true`; для остальных переменных используйте значение `$false`. Значение по умолчанию — `$false`. Если настраивается переменная **Path**, к существующему значению прикрепляется значение свойства **Value**. |
|целевого объекта| Указывает, откуда извлечь переменную: компьютер или процесс. Если указаны оба значения, возвращается только значение с компьютера. По умолчанию выбраны оба источника, так как это значение по умолчанию для остальной части ресурса. |
|Значение |Значение, которое нужно присвоить переменной среды. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли переменная. Присвойте этому свойству значение **Present**, чтобы создать переменную среды, если она отсутствует, или убедиться, что ее значение соответствует значению свойства **Value**, если переменная уже существует. Задайте значение **Absent**, чтобы удалить переменную, если она существует. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

В следующем примере проверяется, существует ли переменная TestEnvironmentVariable и имеет ли она значение _TestValue_. Если переменная не существует, она создается.

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```

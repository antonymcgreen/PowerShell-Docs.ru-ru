---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Environment в DSC
ms.openlocfilehash: 5670646b6e94019f436d85296deff4de8da920f6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560361"
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
|путь |Определяет настраиваемую переменную среды. Для переменной `$true`Path**присвойте этому свойству значение**; для остальных переменных используйте значение `$false`. Значение по умолчанию — `$false`. Если настраивается переменная **Path**, к существующему значению прикрепляется значение свойства **Value**. |
|Значение |Значение, которое нужно присвоить переменной среды. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
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

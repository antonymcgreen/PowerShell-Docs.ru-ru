---
ms.date: 07/17/2020
ms.topic: reference
title: Ресурс nxEnvironment в DSC для Linux
description: Ресурс nxEnvironment в DSC для Linux
ms.openlocfilehash: 86ed538732254967cb4a3bb55af4f6b179947e52
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644676"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a>Ресурс nxEnvironment в DSC для Linux

Ресурс **nxEnvironment** в DSC PowerShell предоставляет механизм управления системными переменными среды на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Path = <bool> }
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|Имя |Указывает имя переменной среды, для которой требуется обеспечить определенное состояние. |
|Значение |Значение, которое нужно присвоить переменной среды. |
|путь |Определяет настраиваемую переменную среды. Для переменной **Path** присвойте этому свойству значение `$true`; для остальных переменных используйте значение `$false`. Значение по умолчанию — `$false`. Если настраивается переменная **Path** , к существующему значению прикрепляется значение свойства **Value** . |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, нужно ли проверять существование переменной. Чтобы гарантировать, что переменная существует, укажите для этого свойства значение **Present** . Чтобы гарантировать, что переменная не существует, укажите для этого свойства значение **Absent** . Значение по умолчанию — **Present** . |

## <a name="additional-information"></a>Дополнительные сведения

- Если свойство **Path** не задано или имеет значение `$false`, управление переменными среды осуществляется в файле `/etc/environment`.
  Для доступа к управляемым переменным среды может потребоваться настроить файл `/etc/environment` в качестве источника для программ или сценариев.
- Если свойство **Path** имеет значение `$true`, управление переменными среды осуществляется в файле `/etc/profile.d/DSCenvironment.sh`. Если этот файл не существует, он будет создан. Если свойство **Ensure** имеет значение **Absent** , а свойство **Path**  — значение `$true`, существующая переменная среды будет удалена только из файла `/etc/profile.d/DSCenvironment.sh`; остальные файлы затронуты не будут.

## <a name="example"></a>Пример

В следующем примере показано, как использовать ресурс **nxEnvironment** , чтобы убедиться, что переменная **TestEnvironmentVariable** существует и имеет значение Test-Value. Если переменная **TestEnvironmentVariable** не существует, она будет создана.

```powershell
Import-DSCResource -Module nx

nxEnvironment EnvironmentExample
{
    Ensure = "Present"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```

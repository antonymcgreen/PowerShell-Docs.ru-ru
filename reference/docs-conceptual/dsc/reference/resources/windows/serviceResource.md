---
ms.date: 09/20/2019
ms.topic: reference
title: Ресурс Service в DSC
description: Ресурс Service в DSC
ms.openlocfilehash: 24121688bc46dcef70e3751d243d140fb7fcc7c9
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142630"
---
# <a name="dsc-service-resource"></a>Ресурс Service в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Синтаксис

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя службы. Обратите внимание! Иногда оно отличается от отображаемого имени. Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`. |
|BuiltInAccount |Указывает учетную запись, используемую службой для входа. Допустимые значения этого свойства: **LocalService** , **LocalSystem** и **NetworkService** . |
|Учетные данные |Указывает учетные данные для учетной записи, от имени которой будет запускаться служба. Это свойство нельзя использовать одновременно со свойством **BuiltinAccount** . |
|StartupType |Указывает тип запуска службы. Допустимые значения этого свойства: **Automatic** , **Disabled** и **Manual** . |
|Состояние |Указывает состояние, в котором должна находиться служба. Значения качества производительности: **Running** или **Stopped** . |
|Зависимости | Массив имен зависимостей, которые должна иметь служба. |
|Описание |Указывает описание целевой службы. |
|DisplayName |Указывает отображаемое имя целевой службы. |
|Путь |Указывает путь к двоичному файлу для новой службы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, имеется ли целевая служба в системе. Если целевая служба не должна существовать, укажите для этого свойства значение **Absent** . Если целевая служба должна существовать, укажите значение **Present** . Значение по умолчанию — **Present** . |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```

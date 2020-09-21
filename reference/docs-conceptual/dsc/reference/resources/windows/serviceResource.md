---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Service в DSC
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463590"
---
# <a name="dsc-service-resource"></a>Ресурс Service в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.

## <a name="syntax"></a>Синтаксис

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя службы. Обратите внимание! Иногда оно отличается от отображаемого имени. Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`. |
|BuiltInAccount |Указывает учетную запись, используемую службой для входа. Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**. |
|Учетные данные |Указывает учетные данные для учетной записи, от имени которой будет запускаться служба. Это свойство нельзя использовать одновременно со свойством **BuiltinAccount**. |
|StartupTimeout | Время ожидания выполнения службы в миллисекундах.|
|StartupType |Указывает тип запуска службы. Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**. |
|Состояние |Указывает состояние, в котором должна находиться служба. Значения качества производительности: **Running** или **Stopped**. |
|TerminateTimeout |Время ожидания остановки службы в миллисекундах.|
|Зависимости | Массив имен зависимостей, которые должна иметь служба. |
|Описание |Указывает описание целевой службы. |
|DesktopInteract | Указывает, должна ли служба взаимодействовать с окном на рабочем столе. Для служб, не работающих в качестве LocalSystem, должно быть задано значение false.|
|DisplayName |Указывает отображаемое имя целевой службы. |
|Путь |Указывает путь к двоичному файлу для новой службы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, имеется ли целевая служба в системе. Если целевая служба не должна существовать, укажите для этого свойства значение **Absent**. Если целевая служба должна существовать, укажите значение **Present**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

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

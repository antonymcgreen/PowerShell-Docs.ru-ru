---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Service в DSC
ms.openlocfilehash: 09571bd0eaa428e7d0bb7a533d6ad1c0c936e2cf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076901"
---
# <a name="dsc-service-resource"></a>Ресурс Service в DSC

> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0


Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.

## <a name="syntax"></a>Синтаксис

```
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Path = [string] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Name| Указывает имя службы. Обратите внимание! Иногда оно отличается от отображаемого имени. Список служб и их текущее состояние можно получить с помощью командлета Get-Service.|
| BuiltInAccount| Указывает учетную запись, используемую службой для входа. Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**.|
| Учетные данные| Указывает учетные данные для учетной записи, от имени которой будет запускаться служба. Это свойство нельзя использовать одновременно со свойством __BuiltinAccount__.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|
| StartupType| Указывает тип запуска службы. Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**.|
| State| Указывает состояние, в котором должна находиться служба.|
| Описание | Указывает описание целевой службы.|
| DisplayName | Указывает отображаемое имя целевой службы.|
| Ensure | Указывает, имеется ли целевая служба в системе. Если целевая служба не должна существовать, укажите для этого свойства значение **Absent**. Если целевая служба должна существовать, укажите значение **Present** (используется по умолчанию).|
| путь | Указывает путь к двоичному файлу для новой службы.|

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
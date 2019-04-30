---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC ServiceSet
ms.openlocfilehash: 5694c2abc5c0caf0098670b629af464b35125583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076843"
---
# <a name="dsc-serviceset-resource"></a>Ресурс DSC ServiceSet

> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс **ServiceSet** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле. Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Service](serviceResource.md) для каждой службы, указанной в свойстве `Name`.

Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких служб.

## <a name="syntax"></a>Синтаксис

```
Service [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Ensure = [string] { Absent | Present }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Name| Указывает имена служб. Обратите внимание на то, что иногда они отличаются от отображаемых имен. Список служб и их текущее состояние можно получить с помощью командлета [Get-Service](https://technet.microsoft.com/library/hh849804.aspx).|
| StartupType| Указывает тип запуска службы. Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**.|
| BuiltInAccount| Указывает учетную запись, используемую службами для входа. Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**.|
| State| Указывает состояние, в котором должны находиться службы: **Stopped** или **Running**.|
| Ensure| Указывает, имеются ли службы в системе. Если службы не должны существовать, присвойте этому свойству значение **Absent**. Если целевые службы должны существовать, укажите значение **Present** (используется по умолчанию).|
| Учетные данные| Указывает учетные данные для учетной записи, от имени которой будет запускаться ресурс службы. Это свойство нельзя использовать одновременно со свойством **BuiltinAccount**.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — *ResourceName*, а его тип — *ResourceType*, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|



## <a name="example"></a>Пример

Приведенная ниже конфигурация запускает службы "Windows Audio" и "Службы удаленных рабочих столов".

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```

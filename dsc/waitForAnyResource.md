---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForAny
ms.openlocfilehash: 39100f0fc52092c54bbecab55e3ef3dfabb4c70e
ms.sourcegitcommit: e76665315fd928bf85210778f1fea2be15264fea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50226055"
---
# <a name="dsc-waitforany-resource"></a>Ресурс DSC WaitForAny

> Область применения: Windows PowerShell 5.1 и более поздних версий.

Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](configurations.md) для определения зависимостей от конфигураций на других узлах.

Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName**.


## <a name="syntax"></a>Синтаксис

```
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| ResourceName| Имя ресурса, с которым настраивается отношение зависимости. Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".|
| NodeName| Целевые узлы ресурса, с которым настраивается отношение зависимости.|
| RetryIntervalSec| Количество секунд перед повторной попыткой. Минимальное значение — 1.|
| RetryCount| Максимальное число повторных попыток.|
| ThrottleLimit| Количество одновременно подключаемых компьютеров. Значение по умолчанию — New-CimSession.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|


## <a name="example"></a>Пример

Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](crossNodeDependencies.md).
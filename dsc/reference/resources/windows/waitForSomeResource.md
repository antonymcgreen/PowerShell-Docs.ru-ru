---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: 906375a8fcf9b87d4b7487e63e6fae3f05b86d0d
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047544"
---
# <a name="dsc-waitforsome-resource"></a>Ресурс DSC WaitForSome

> Область применения. Windows PowerShell 5.0 и более поздние версии

Ресурс настройки требуемого состояния **WaitForAny** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.

Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.


## <a name="syntax"></a>Синтаксис

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| NodeCount| Минимальное количество узлов, которые должны быть в требуемом состоянии для успешного выполнения этого ресурса.|
| NodeName| Целевые узлы ресурса, с которым настраивается отношение зависимости.|
| ResourceName| Имя ресурса, с которым настраивается отношение зависимости. Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".|
| RetryIntervalSec| Количество секунд перед повторной попыткой. Минимальное значение — 1.|
| RetryCount| Максимальное число повторных попыток.|
| ThrottleLimit| Количество одновременно подключаемых компьютеров. Значение по умолчанию — New-CimSession.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|
| PsDscRunAsCredential | См. статью [Запуск DSC с учетными данными пользователя](https://docs.microsoft.com/powershell/dsc/runasuser). |

## <a name="example"></a>Пример

Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).

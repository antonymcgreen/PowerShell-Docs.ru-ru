---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс DSC WaitForSome
description: Ресурс DSC WaitForSome
ms.openlocfilehash: bc9c3df2b476e7046ccfe6257acc1d1641e7594b
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143098"
---
# <a name="dsc-waitforsome-resource"></a>Ресурс DSC WaitForSome

> Область применения: Windows PowerShell 5.x

Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName** , находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount** ), заданных свойством **NodeName** .

> [!NOTE]
> Ресурс **WaitForSome** использует удаленное управление Windows, чтобы проверить состояние других узлов. Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity).

## <a name="syntax"></a>Синтаксис

```Syntax
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [ RetryCount = [UInt32] ]
    [ RetryIntervalSec = [UInt64] ]
    [ ThrottleLimit = [UInt32] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|NodeCount |Минимальное количество узлов, которые должны быть в требуемом состоянии для успешного выполнения этого ресурса. |
|NodeName |Целевые узлы ресурса, с которым настраивается отношение зависимости. |
|ResourceName |Имя ресурса, с которым настраивается отношение зависимости. Если этот ресурс относится к другой конфигурации, то его имя следует отформатировать как `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`. |
|RetryIntervalSec |Количество секунд перед повторной попыткой. Минимальное значение — 1. |
|RetryCount |Максимальное число повторных попыток. |
|ThrottleLimit |Количество одновременно подключаемых компьютеров. Значение по умолчанию — `New-CimSession`. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).

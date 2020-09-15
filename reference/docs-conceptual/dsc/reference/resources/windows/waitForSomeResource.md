---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: ea2618fbb77dd24a0c73fd9357e87862da514b66
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464389"
---
# <a name="dsc-waitforsome-resource"></a>Ресурс DSC WaitForSome

> Область применения: Windows PowerShell 5.x

Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.

Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.

> [!NOTE]
> Ресурс **WaitForSome** использует удаленное управление Windows, чтобы проверить состояние других узлов. Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).

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
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).

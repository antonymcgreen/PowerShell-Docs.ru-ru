---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForAny
ms.openlocfilehash: fa895c78f233a2e446552bb27d4491a90076e05a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463879"
---
# <a name="dsc-waitforany-resource"></a>Ресурс DSC WaitForAny

> Область применения: Windows PowerShell 5.1

Ресурс настройки требуемого состояния **WaitForAny** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.

Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName**.

> [!NOTE]
> Ресурс **WaitForAny** использует удаленное управление Windows, чтобы проверить состояние других узлов. Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).

## <a name="syntax"></a>Синтаксис

```Syntax
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|ResourceName |Имя ресурса, с которым настраивается отношение зависимости. Если этот ресурс относится к другой конфигурации, то его имя следует отформатировать как `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`. |
|NodeName |Целевые узлы ресурса, с которым настраивается отношение зависимости. |
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

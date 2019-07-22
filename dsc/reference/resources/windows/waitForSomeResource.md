---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: 2260f37002171154a6f2c3996b2af1bd9120039d
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726766"
---
# <a name="dsc-waitforsome-resource"></a>Ресурс DSC WaitForSome

> Область применения. Windows PowerShell 5.0 и более поздних версий

Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.

Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.

> [!NOTE]
> Ресурс **WaitForSome** использует удаленное управление Windows, чтобы проверить состояние других узлов.
> Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).

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

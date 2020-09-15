---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Log в DSC
ms.openlocfilehash: bc59bb2670561306a039d024fcff5e0746a659f2
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464032"
---
# <a name="dsc-log-resource"></a>Ресурс Log в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Log** в DSC Windows PowerShell предоставляет механизм записи сообщений в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.

## <a name="syntax"></a>Синтаксис

```Syntax
Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> По умолчанию включены только операционные журналы DSC. Чтобы журнал аналитики стал доступным или видимым, его необходимо включить. См. дополнительные сведения о [расположении журналов событий DSC](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs).

## <a name="properties"></a>Свойства

| Свойство |                                                   Description                                                    |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| Сообщение  | Указывает сообщение для записи в журнал событий Microsoft-Windows-Desired State Configuration/Analytic. |

## <a name="common-properties"></a>Общие свойства

|       Свойство       |                                                                                                                                                          Description                                                                                                                                                           |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DependsOn            | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
| PsDscRunAsCredential | Задает учетные данные для выполнения всего ресурса от другого имени.                                                                                                                                                                                                                                                                        |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

В следующем примере показано, как добавить сообщение в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.

> [!NOTE]
> Если этот ресурс настроен, при выполнении командлета [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/test-dscconfiguration?view=powershell-5.1) всегда возвращается значение **$false**.

```powershell
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost
    {
        Log LogExample
        {
            Message = 'This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log.'
        }
    }
}
```

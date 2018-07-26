---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Log в DSC
ms.openlocfilehash: fade94efd8133ae0172737e4bb1aed89fc0f97d9
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093482"
---
# <a name="dsc-log-resource"></a>Ресурс Log в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс __Log__ в DSC Windows PowerShell предоставляет механизм записи сообщений в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

> [!NOTE]
> По умолчанию включены только операционные журналы DSC. Чтобы журнал аналитики стал доступным или видимым, его необходимо включить. См. дополнительные сведения о [расположении журналов событий DSC](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs).

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Сообщение| Указывает сообщение для записи в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.|
| DependsOn | Указывает, что перед записью этого сообщения в журнал необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = '[ResourceType]ResourceName'`.|

## <a name="example"></a>Пример

В следующем примере показано, как добавить сообщение в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.

> [!NOTE]
> Если этот ресурс настроен, при выполнении командлета [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) всегда возвращается значение **$false**.

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
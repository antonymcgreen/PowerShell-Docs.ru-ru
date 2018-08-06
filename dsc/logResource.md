---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Log в DSC
ms.openlocfilehash: 50fd6cd31ba426108830fcf124a767318060a95d
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268438"
---
# <a name="dsc-log-resource"></a>Ресурс Log в DSC

_Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0_

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
> По умолчанию включены только операционные журналы DSC. Чтобы журнал аналитики стал доступным или видимым, его необходимо включить. См. дополнительные сведения о [расположении журналов событий DSC](troubleshooting.md#where-are-dsc-event-logs).

## <a name="properties"></a>Свойства

| Свойство | Описание |
| --- | --- |
| Сообщение| Указывает сообщение для записи в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.|
| DependsOn | Указывает, что перед записью этого сообщения в журнал необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = '[ResourceType]ResourceName'`.|

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
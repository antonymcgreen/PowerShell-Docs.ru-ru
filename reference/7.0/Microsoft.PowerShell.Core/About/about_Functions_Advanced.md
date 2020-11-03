---
description: Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: 36b354e813c60208960f4cfb826ef0db81435c77
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231001"
---
# <a name="about-functions-advanced"></a>О функциях Advanced

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Командлет — это одна команда, которая участвует в семантике конвейера PowerShell. Сюда входят двоичные командлеты, расширенные функции скриптов, CDXML и рабочие процессы.

Расширенные функции позволяют создавать командлеты, написанные как функция PowerShell. Расширенные функции упрощают создание командлетов без написания и компиляции двоичного командлета. Двоичные командлеты — это классы .NET, написанные на языке .NET, например C#.

Дополнительные функции используют `CmdletBinding` атрибут, чтобы обозначить их как функции, которые действуют как командлеты. `CmdletBinding`Атрибут аналогичен атрибуту командлета, который используется в скомпилированных классах командлетов для задания класса в качестве командлета. Дополнительные сведения об этом атрибуте см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

В следующем примере показана функция, которая принимает имя, а затем выводит приветствие с использованием заданного имени. Также обратите внимание, что эта функция определяет имя, которое включает пару глагол (Send) и существительное (приветствие), например пару глагол-существительное скомпилированного командлета. Однако функции не обязательно должны иметь имя существительное.

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

Параметры функции объявляются с помощью атрибута Parameter.
Этот атрибут можно использовать отдельно или в сочетании с атрибутом Alias или с несколькими другими атрибутами проверки параметров. Дополнительные сведения об объявлении параметров (включая динамические параметры, добавляемые во время выполнения) см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

Фактическая работа предыдущей функции выполняется в блоке Process, что эквивалентно методу Процессингрекорд, который используется скомпилированными командлетами для обработки данных, передаваемых в командлет. Этот блок вместе с блоками Begin и End описан в разделе [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) .

Дополнительные функции отличаются от скомпилированных командлетов следующими способами.

- Расширенная привязка параметра функции не вызывает исключение, если массив строк привязан к логическому параметру.
- Атрибут Validate и атрибут ValidatePattern не могут передавать именованные параметры.
- В транзакциях нельзя использовать дополнительные функции.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

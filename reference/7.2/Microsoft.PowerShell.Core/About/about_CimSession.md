---
description: Описывает объект **CimSession** и разницу между сеансами CIM и сеансами PowerShell.
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CimSession
ms.openlocfilehash: 556c3db21ea5e410b28f5546cdd8a433e0bc3e50
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604497"
---
# <a name="about-cimsession"></a>О CimSession

## <a name="short-description"></a>Краткое описание
Описывает объект **CimSession** и разницу между сеансами CIM и сеансами PowerShell.

## <a name="long-description"></a>Подробное описание

Сеанс модель CIM (CIM) — это клиентский объект, представляющий подключение к локальному или удаленному компьютеру. Вы можете использовать сеансы CIM в качестве альтернативы сеансам PowerShell (PSSession). Оба подхода имеют свои преимущества.

С помощью `New-CimSession` командлета можно создать сеанс CIM, содержащий сведения о соединении, такие как имя компьютера, протокол, используемый для соединения, идентификатор сеанса и идентификатор экземпляра.

После создания объекта **CimSession** , указывающего сведения, необходимые для установления соединения, PowerShell не устанавливает соединение немедленно. Когда командлет использует сеанс CIM, PowerShell подключается к указанному компьютеру, а после завершения выполнения командлета PowerShell завершает соединение.

Если вы создаете **PSSession** вместо сеанса CIM, то PowerShell проверяет параметры подключения, а затем устанавливает и поддерживает подключение. При использовании сеансов CIM PowerShell не открывает сетевое подключение, пока это не потребуется. Дополнительные сведения о сеансах PowerShell см. в разделе [about_PSSessions](about_PSSessions.md).

## <a name="when-to-use-a-cim-session"></a>Когда следует использовать сеанс CIM

Только командлеты, которые работают с поставщиком инструментарий управления Windows (WMI) (WMI) или CIM при WS-Man принимают сеансы CIM. Для других командлетов используйте **PSSession**.

При использовании сеанса CIM PowerShell запускает командлет на локальном клиенте. Он подключается к поставщику WMI с помощью сеанса CIM. На целевом компьютере не требуется PowerShell или даже любая версия операционной системы Windows.

В отличие от этого командлет запускается с помощью **сеанса PSSession** на целевом компьютере.
Для этого требуется PowerShell в целевой системе. Более того, командлет отправляет данные обратно на локальный компьютер. PowerShell управляет данными, отправленными по подключению, и сохраняет размер в пределах установленных служба удаленного управления Windows (WinRM). Сеансы CIM не накладывают ограничения WinRM.

## <a name="using-cdxml-cmdlets"></a>Использование командлетов CDXML

Командлеты XML (CDXML) определения командлетов на основе CIM могут быть написаны для использования любого поставщика WMI. Все поставщики WMI используют объекты **CimSession** . Дополнительные сведения о CDXML см. в разделе [Определение и термины cdxml](/previous-versions/windows/desktop/wmi_v2/cdxml-overview).

Командлеты CDXML имеют автоматический параметр **CimSession** , который может принимать массив объектов **CimSession** . По умолчанию PowerShell ограничивает число параллельных подключений CIM до 15. Это ограничение можно переопределить с помощью командлетов CDXML, которые реализуют **ThrottleLimit**. Сведения о **ThrottleLimit** см. в документации по отдельным командлетам.

## <a name="see-also"></a>СМ. ТАКЖЕ

[New-CimSession](xref:CimCmdlets.New-CimSession)

[about_PSSessions](about_PSSessions.md)


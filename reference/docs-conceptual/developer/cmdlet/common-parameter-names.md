---
ms.date: 09/13/2016
ms.topic: reference
title: Общие имена параметров
description: Общие имена параметров
ms.openlocfilehash: cf39dd3b04660076718336857d79d55c3784ccd1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668224"
---
# <a name="common-parameter-names"></a>Общие имена параметров

Параметры, описанные в этом разделе, называются *общими параметрами*. Они добавляются в командлеты средой выполнения Windows PowerShell и не могут быть объявлены с помощью командлета.

> [!NOTE]
> Эти параметры также добавляются в командлеты поставщика и в функции, снабженные `CmdletBinding` атрибутом.

## <a name="general-common-parameters"></a>Общие общие параметры

Следующие параметры добавляются во все командлеты и доступны при каждом запуске командлета. Эти параметры определяются классом [System. Management. Automation. internal. общиепараметры](/dotnet/api/System.Management.Automation.Internal.CommonParameters) .

### <a name="debug-alias-db"></a>Отладка (псевдоним: DB)

Тип данных: переключатель

Этот параметр указывает, могут ли сообщения отладки на уровне программиста отображаться в командной строке. Эти сообщения предназначены для устранения неполадок в работе командлета и создаются вызовами метода [System. Management. Automation. командлета. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) . Сообщения отладки не обязательно должны быть локализованы.

### <a name="erroraction-alias-ea"></a>ErrorAction (псевдоним: EA)

Тип данных: перечисление

Этот параметр указывает, какое действие должно выполняться при возникновении ошибки. Возможные значения для этого параметра определяются перечислением [System. Management. Automation. действие](/dotnet/api/System.Management.Automation.ActionPreference) .

### <a name="errorvariable-alias-ev"></a>ErrorVariable (псевдоним: EV)

Тип данных: строковый

Этот параметр задает переменную, в которой должны размещаться объекты при возникновении ошибки. Чтобы добавить к этой переменной, используйте +*имя_переменной* вместо очистки и задания переменной.

### <a name="outvariable-alias-ov"></a>Переменная (Alias: OV)

Тип данных: строковый

Этот параметр задает переменную, в которой должны размещаться все выходные объекты, созданные командлетом. Чтобы добавить к этой переменной, используйте +*имя_переменной* вместо очистки и задания переменной.

### <a name="outbuffer-alias-ob"></a>Буфер (псевдоним: OB)

Тип данных: Int32

Этот параметр определяет число объектов для хранения в выходном буфере до того, как все объекты передаются по конвейеру. По умолчанию объекты передаются сразу по конвейеру.

### <a name="verbose-alias-vb"></a>Подробный (псевдоним: VB)

Тип данных: переключатель

Этот параметр указывает, записывает ли командлет пояснительные сообщения, которые могут отображаться в командной строке. Эти сообщения предназначены для предоставления пользователю дополнительной справки и создаются вызовами метода [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .

### <a name="warningaction-alias-wa"></a>WarningAction (псевдоним: WA)

Тип данных: перечисление

Этот параметр указывает, какое действие должно выполняться, когда командлет Записывает предупреждающее сообщение. Возможные значения для этого параметра определяются перечислением [System. Management. Automation. действие](/dotnet/api/System.Management.Automation.ActionPreference) .

### <a name="warningvariable-alias-wv"></a>WarningVariable (псевдоним: WV)

Тип данных: строковый

Этот параметр указывает переменную, в которой можно сохранять предупреждающие сообщения. Чтобы добавить к этой переменной, используйте +*имя_переменной* вместо очистки и задания переменной.

## <a name="risk-mitigation-parameters"></a>Параметры Risk-Mitigation

Следующие параметры добавляются в командлеты, которые запрашивают подтверждение перед выполнением действия. Дополнительные сведения о запросах на подтверждение см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md). Эти параметры определяются классом [System. Management. Automation. internal. шаулдпроцесспараметерс](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters) .

### <a name="confirm-alias-cf"></a>Подтверждение (псевдоним: CF)

Тип данных: переключатель

Этот параметр указывает, отображается ли в командлете запрос, предлагающий пользователю, что он должен продолжить работу.

### <a name="whatif-alias-wi"></a>WhatIf (псевдоним: Wi-in)

Тип данных: переключатель

Этот параметр указывает, записывает ли командлет сообщение, описывающее последствия выполнения командлета, без фактического выполнения каких-либо действий.

## <a name="transaction-parameters"></a>Параметры транзакции

Следующий параметр добавляется в командлеты, которые поддерживают транзакции. Эти параметры определяются классом [System. Management. Automation. internal. трансактионпараметерс](/dotnet/api/System.Management.Automation.Internal.TransactionParameters) .

### <a name="usetransaction-alias-usetx"></a>UseTransaction (псевдоним: усеткс)

Тип данных: переключатель

Этот параметр указывает, будет ли командлет использовать текущую транзакцию для выполнения действия.

## <a name="see-also"></a>См. также:

[System. Management. Automation. internal. Общиепараметры](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[System. Management. Automation. internal. Шаулдпроцесспараметерс](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[System. Management. Automation. internal. Трансактионпараметерс](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

---
title: Имена общих параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0db9f54c-4014-4450-9e81-c9f5fe562a0e
caps.latest.revision: 12
ms.openlocfilehash: c65deeda6b2ef1b52de55035dc606259a7f2d232
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068437"
---
# <a name="common-parameter-names"></a>Общие имена параметров

Параметры, описанные в этом разделе, называются *общих параметров*. Они добавляются в командлетах средой выполнения Windows PowerShell и не может объявляться с помощью командлета.

> [!NOTE]
> Эти параметры также добавляются в командлеты поставщика, а также функций, обозначенных с помощью `CmdletBinding` атрибута.

## <a name="general-common-parameters"></a>Общие Общие параметры

Следующие параметры добавляются все командлеты и может осуществляться при запуске командлета. Эти параметры определяются [System.Management.Automation.Internal.Commonparameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters) класса.

### <a name="debug-alias-db"></a>Отладка (псевдоним: db)

Тип данных: Переключатель

Этот параметр указывает ли отладка на уровне программист сообщения, которые могут отображаться в командной строке. Эти сообщения предназначены для устранения неполадок операцию командлета и создаются путем вызова [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метод. Отладочные сообщения не обязательно должны быть локализованы.

### <a name="erroraction-alias-ea"></a>ErrorAction (псевдоним: ea)

Тип данных: Перечисление

Этот параметр указывает, какое действие следует выполнить при возникновении ошибки. Возможные значения для этого параметра определяются [System.Management.Automation.Actionpreference](/dotnet/api/System.Management.Automation.ActionPreference) перечисления.

### <a name="errorvariable-alias-ev"></a>ErrorVariable (псевдоним: ev)

Тип данных: Строка

Этот параметр задает переменную, в котором следует разместить объекты при возникновении ошибки. Для добавления в эту переменную, рекомендуется использовать +*varname* вместо того чтобы очистка и настройки переменной.

### <a name="outvariable-alias-ov"></a>OutVariable (псевдоним: ov)

Тип данных: Строка

Этот параметр задает переменную, в которую необходимо поместить все выходные объекты, сформированные с помощью командлета. Для добавления в эту переменную, рекомендуется использовать +*varname* вместо того чтобы очистка и настройки переменной.

### <a name="outbuffer-alias-ob"></a>OutBuffer (псевдоним: ob)

Тип данных: Int32

Этот параметр определяет количество объектов для хранения в выходной буфер, прежде чем все объекты передаются по конвейеру. По умолчанию объекты, немедленно передаются по конвейеру.

### <a name="verbose-alias-vb"></a>Verbose (псевдоним: vb)

Тип данных: Переключатель

Этот параметр указывает, является ли этот командлет записывает пояснительный сообщений, которые могут отображаться в командной строке. Эти сообщения предназначены для получения дополнительной справки для пользователя и создаются путем вызова [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метод.

### <a name="warningaction-alias-wa"></a>WarningAction (псевдоним: wa)

Тип данных: Перечисление

Этот параметр указывает, какое действие должно иметь место, когда этот командлет записывает предупреждающее сообщение. Возможные значения для этого параметра определяются [System.Management.Automation.Actionpreference](/dotnet/api/System.Management.Automation.ActionPreference) перечисления.

### <a name="warningvariable-alias-wv"></a>WarningVariable (псевдоним: wv)

Тип данных: Строка

Этот параметр задает переменную, в котором можно сохранить предупреждающие сообщения. Для добавления в эту переменную, рекомендуется использовать +*varname* вместо того чтобы очистка и настройки переменной.

## <a name="risk-mitigation-parameters"></a>Параметры уменьшения рисков

Следующие параметры добавляются в командлеты, которые запрашивает подтверждение перед выполнением их действия. Дополнительные сведения о запросах подтверждения, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md). Эти параметры определяются [System.Management.Automation.Internal.Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters) класса.

### <a name="confirm-alias-cf"></a>Подтвердите (псевдоним: cf)

Тип данных: Переключатель

Этот параметр указывает, отображаются ли командлет запрос, является ли пользователь в том, что они хотят продолжить.

### <a name="whatif-alias-wi"></a>WhatIf (псевдоним: рабочие элементы)

Тип данных: Переключатель

Этот параметр указывает, является ли этот командлет записывает сообщение, описывающее эффекты выполнения командлета, не выполняя никаких действий.

## <a name="transaction-parameters"></a>Параметры транзакций

Следующий параметр добавляется в командлеты, которые поддерживают транзакции. Эти параметры определяются [System.Management.Automation.Internal.Transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters) класса.

### <a name="usetransaction-alias-usetx"></a>UseTransaction (псевдоним: usetx)

Тип данных: Переключатель

Этот параметр указывает, использует ли командлет текущей транзакции для выполнения действия.

## <a name="see-also"></a>См. также

[System.Management.Automation.Internal.Commonparameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[System.Management.Automation.Internal.Shouldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[System.Management.Automation.Internal.Transactionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

---
title: Необходимые рекомендации по разработке | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41d2b308-a36a-496f-8542-666b6a21eedc
caps.latest.revision: 19
ms.openlocfilehash: e68e43a91f9139e8d3dc636b5740121515aab2e6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369523"
---
# <a name="required-development-guidelines"></a>Обязательные требования к разработке

При написании командлетов необходимо следовать приведенным ниже рекомендациям. Они разделены на рекомендации по проектированию командлетов и руководств по написанию кода командлета. Если не следовать этим рекомендациям, командлеты могут завершиться сбоем, и пользователи могут столкнуться с плохими возможностями при использовании командлетов.

## <a name="in-this-topic"></a>В этом разделе

### <a name="design-guidelines"></a>Руководство по проектированию

- [Использовать только утвержденные команды (RD01)](./required-development-guidelines.md#use-only-approved-verbs-rd01)

- [Имена командлетов: символы, которые не могут быть использованы (RD02)](./required-development-guidelines.md#cmdlet-names-characters-that-cannot-be-used-rd02)

- [Имена параметров, которые нельзя использовать (RD03)](./required-development-guidelines.md#parameters-names-that-cannot-be-used-rd03)

- [Запросы на подтверждение поддержки (RD04)](./required-development-guidelines.md#support-confirmation-requests-rd04)

- [Поддержка параметра Force для интерактивных сеансов (RD05)](./required-development-guidelines.md#support-force-parameter-for-interactive-sessions-rd05)

- [Объекты вывода документа (RD06)](./required-development-guidelines.md#document-output-objects-rd06)

### <a name="code-guidelines"></a>Рекомендации по коду

- [Наследование от классов командлета или PSCmdlet (RC01)](./required-development-guidelines.md#derive-from-the-cmdlet-or-pscmdlet-classes-rc01)

- [Укажите атрибут командлета (RC02)](./required-development-guidelines.md#specify-the-cmdlet-attribute-rc02)

- [Переопределение метода обработки ввода (RC03)](./required-development-guidelines.md#override-an-input-processing-method-rc03)

- [Указание атрибута OutputType (RC04)](./required-development-guidelines.md#specify-the-outputtype-attribute-rc04)

- [Не сохраняйте дескрипторы для выходных объектов (RC05)](./required-development-guidelines.md#do-not-retain-handles-to-output-objects-rc05)

- [Устойчивая работа с ошибками (RC06)](./required-development-guidelines.md#handle-errors-robustly-rc06)

- [Использование модуля Windows PowerShell для развертывания командлетов (RC07)](./required-development-guidelines.md#use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07)

## <a name="design-guidelines"></a>Руководство по проектированию

При проектировании командлетов необходимо следовать приведенным ниже рекомендациям, чтобы обеспечить согласованное взаимодействие с пользователем при использовании командлетов и других командлетов. Если вы нашли рекомендации по проектированию, применимые к вашей ситуации, ознакомьтесь с рекомендациями по написанию кода для аналогичных руководств.

### <a name="use-only-approved-verbs-rd01"></a>Использовать только утвержденные команды (RD01)

Команда, указанная в атрибуте командлета, должна поступать из распознанного набора команд, предоставляемых Windows PowerShell. Он не должен быть одним из запрещенных синонимов. Используйте константные строки, определенные следующими перечислениями, для указания команд командлета:

- [System. Management. Automation. Вербскоммон](/dotnet/api/System.Management.Automation.VerbsCommon)

- [System. Management. Automation. Вербскоммуникатионс](/dotnet/api/System.Management.Automation.VerbsCommunications)

- [System. Management. Automation. Вербсдата](/dotnet/api/System.Management.Automation.VerbsData)

- [System. Management. Automation. Вербсдиагностик](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

- [System. Management. Automation. Вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

- [System. Management. Automation. Вербссекурити](/dotnet/api/System.Management.Automation.VerbsSecurity)

- [System. Management. Automation. Вербсосер](/dotnet/api/System.Management.Automation.VerbsOther)

Дополнительные сведения о утвержденных именах команд см. в разделе [команды командлета](./approved-verbs-for-windows-powershell-commands.md).

Пользователям требуется набор обнаруживаемых и ожидаемых имен командлетов. Используйте соответствующую команду, чтобы пользователь мог быстро оценить то, что делает командлет, и легко обнаружить возможности системы. Например, следующая команда командной строки возвращает список всех команд в системе, имена которых начинаются на "Start": `get-command start-*`. Используйте существительные в командлетах, чтобы отличать командлеты от других командлетов. Существительное указывает ресурс, в котором будет выполнена операция. Сама операция представляется командой.

### <a name="cmdlet-names-characters-that-cannot-be-used-rd02"></a>Имена командлетов: символы, которые не могут быть использованы (RD02)

При именовании командлетов не используйте следующие специальные символы.

|Знак|Название|
|---------------|----------|
|#|знак числа|
|,|запятая|
|()|круглые скобки|
|{}|фигурные скобки|
|[]|квадратных|
|&|знаки|
|-|дефис **Примечание.** дефис можно использовать для отделения глагола от существительных, но не может использоваться внутри существительного или внутри команды.|
|/|знак косой черты|
|\\| обратная косая черта|
|$|знак доллара|
|^|caret|
|;|точка с запятой|
|.|ставит|
|«Службы|двойная кавычка|
|'|одиночные кавычки|
|<>|угловые скобки|
|&#124;|Вертикальная черта|
|?|вопросительный знак|
|@|знак «коммерческое эт»|
|`|Обратная шкала (ударение)|
|*|звездочка|
|%|знак процента|
|+|Знак "плюс"|
|=|знак равенства|
|~|символа|

### <a name="parameters-names-that-cannot-be-used-rd03"></a>Имена параметров, которые нельзя использовать (RD03)

Windows PowerShell предоставляет общий набор параметров для всех командлетов, а также дополнительные параметры, которые добавляются в конкретных ситуациях. При проектировании собственных командлетов нельзя использовать следующие имена: Confirm, Debug, ErrorAction, ErrorVariable, rebuffer, of Variable, WarningAction, WarningVariable, WhatIf, UseTransaction и verbose. Дополнительные сведения об этих параметрах см. в разделе [Общие имена параметров](./common-parameter-names.md).

### <a name="support-confirmation-requests-rd04"></a>Запросы на подтверждение поддержки (RD04)

Для командлетов, выполняющих операцию, которая изменяет систему, они должны вызвать метод [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , чтобы запросить подтверждение, а в особых случаях вызвать метод [System. Management. Automation. командлет. ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) . (Метод [System. Management. Automation. командлет. ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) следует вызывать только после вызова метода [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .)

Для выполнения этих вызовов командлет должен указать, что он поддерживает запросы на подтверждение, установив ключевое слово `SupportsShouldProcess` атрибута командлета. Дополнительные сведения о задании этого атрибута см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).

> [!NOTE]
> Если атрибут командлета класса командлета указывает, что командлет поддерживает вызовы метода [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , и командлет не может вызвать метод [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , пользователь может неожиданно изменить систему.

Используйте метод [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) для любых изменений в системе. Предпочтения пользователя и параметр `WhatIf` управляют методом [System. Management. Automation. командлет. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . В отличие от этого, вызов [System. Management. Automation. командлет. ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) выполняет дополнительную проверку потенциально опасных изменений. Этот метод не контролируется ни одним из предпочтений пользователя, ни параметром `WhatIf`. Если командлет вызывает метод [System. Management. Automation. командлет. ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , он должен иметь параметр `Force`, который обходит вызовы этих двух методов и продолжает работу. Это важно, так как позволяет использовать командлет в неинтерактивных скриптах и узлах.

Если командлеты поддерживают эти вызовы, пользователь может определить, следует ли выполнять действие фактически. Например, командлет [Stop-Process](/powershell/module/microsoft.powershell.management/stop-process) вызывает метод [System. Management. Automation. командлет. ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) перед остановкой набора критически важных процессов, включая процессы System, Winlogon и Spoolsv.

Дополнительные сведения о поддержке этих методов см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

### <a name="support-force-parameter-for-interactive-sessions-rd05"></a>Поддержка параметра Force для интерактивных сеансов (RD05)

Если командлет используется в интерактивном режиме, всегда следует использовать параметр Force для переопределения интерактивных действий, таких как запросы или считывание строк ввода. Это важно, так как позволяет использовать командлет в неинтерактивных скриптах и узлах. С помощью интерактивного узла можно реализовать следующие методы.

- [System. Management. Automation. host. Пшостусеринтерфаце. prompt *](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.Prompt)

- [System. Management. Automation. host. Пшостусеринтерфаце. Промптфорчоице](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForChoice)

- [System. Management. Automation. host. Ихостуисуппортсмултиплечоицеселектион. Промптфорчоице](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection.PromptForChoice)

- [System. Management. Automation. host. Пшостусеринтерфаце. PromptForCredential *](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForCredential)

- [System. Management. Automation. host. Пшостусеринтерфаце. ReadLine *](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLine)

- [System. Management. Automation. host. Пшостусеринтерфаце. Реадлинеассекурестринг *](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLineAsSecureString)

### <a name="document-output-objects-rd06"></a>Объекты вывода документа (RD06)

Windows PowerShell использует объекты, которые записываются в конвейер. Чтобы пользователи могли воспользоваться преимуществами объектов, возвращаемых каждым командлетом, необходимо задокументировать возвращаемые объекты, и необходимо задокументировать, для каких элементов возвращенных объектов используется.

## <a name="code-guidelines"></a>Рекомендации по коду

При написании кода командлета необходимо следовать приведенным ниже рекомендациям. Когда вы найдете рекомендации по коду, применимые к вашей ситуации, ознакомьтесь с рекомендациями по проектированию для аналогичных руководств.

### <a name="derive-from-the-cmdlet-or-pscmdlet-classes-rc01"></a>Наследование от классов командлета или PSCmdlet (RC01)

Командлет должен быть производным от базового класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) или [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) . Командлеты, производные от класса [System. Management. Automation. командлета](/dotnet/api/System.Management.Automation.Cmdlet) , не зависят от среды выполнения Windows PowerShell. Их можно вызывать непосредственно на любом языке платформы Microsoft .NET Framework. Командлеты, производные от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) , зависят от среды выполнения Windows PowerShell. Поэтому они выполняются в пределах пространства выполнения.

Все классы командлетов, которые реализуются, должны быть открытыми классами. Дополнительные сведения об этих классах командлетов см. в разделе [Общие сведения о командлетах](./cmdlet-overview.md).

### <a name="specify-the-cmdlet-attribute-rc02"></a>Укажите атрибут командлета (RC02)

Для распознавания командлетом Windows PowerShell его .NET Framework класс должен быть дополнен атрибутом командлета. Этот атрибут задает следующие функции командлета.

- Пара «глагол--существительное», определяющая командлет.

- Набор параметров по умолчанию, используемый при указании нескольких наборов параметров. Набор параметров по умолчанию используется в том случае, если в Windows PowerShell недостаточно сведений для определения используемого набора параметров.

- Указывает, поддерживает ли командлет вызовы метода [System. Management. Automation. командлета. ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Этот метод выводит сообщение с подтверждением пользователю перед тем, как командлет вносит изменения в систему. Дополнительные сведения о том, как выполняются запросы на подтверждение, см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

- Указывает уровень влияния (или серьезность) действия, связанного с сообщением подтверждения. В большинстве случаев следует использовать значение по умолчанию Medium. Дополнительные сведения о том, как уровень влияния влияет на запросы подтверждения, отображаемые пользователю, см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

Дополнительные сведения об объявлении атрибута командлета см. в разделе [объявление CmdletAttribute](./cmdlet-attribute-declaration.md).

### <a name="override-an-input-processing-method-rc03"></a>Переопределение метода обработки ввода (RC03)

Чтобы командлет принимал участие в среде Windows PowerShell, он должен переопределить по крайней мере один из следующих *методов обработки входных данных*.

[System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) . Этот метод вызывается один раз и используется для предоставления функций предварительной обработки.

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) этот метод вызывается несколько раз и используется для предоставления функциональных возможностей записи по записям.

[System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Этот метод вызывается один раз и используется для предоставления функций последующей обработки.

### <a name="specify-the-outputtype-attribute-rc04"></a>Указание атрибута OutputType (RC04)

Атрибут OutputType (представленный в Windows PowerShell 2,0) указывает тип .NET Framework, возвращаемый командлетом в конвейер. Указав тип выходных данных командлетов, вы сделаете объекты, возвращаемые командлетом, более доступными для других командлетов. Дополнительные сведения о декорировании класса командлета с помощью этого атрибута см. в разделе [объявление атрибута OutputType](./outputtype-attribute-declaration.md).

### <a name="do-not-retain-handles-to-output-objects-rc05"></a>Не сохраняйте дескрипторы для выходных объектов (RC05)

Командлет не должен хранить дескрипторы объектов, которые передаются в метод [System. Management. Automation. командлет. WriteObject *](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Эти объекты передаются следующему командлету в конвейере или используются сценарием. При хранении дескрипторов объектов две сущности будут владеть каждым объектом, что вызывает ошибки.

### <a name="handle-errors-robustly-rc06"></a>Устойчивая работа с ошибками (RC06)

Среда администрирования изначально обнаруживает и вносит важные изменения в систему, которую вы администрировать. Поэтому крайне важно, чтобы командлеты правильно обрабатывали ошибки. Дополнительные сведения о записи об ошибках см. в разделе [отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md).

- Если ошибка не позволяет командлету продолжить обработку каких-либо записей, это является завершающим ошибкой. Командлет должен вызвать метод [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) , который ссылается на объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) . Если в командлете не перехвачено исключение, то среда выполнения Windows PowerShell создает завершающую ошибку, которая содержит меньше информации.

- Для устранимой ошибки, которая не останавливает операцию над следующей записью, которая поступает из конвейера (например, запись, созданная другим процессом), командлет должен вызвать метод [System. Management. Automation. командлет. WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , который ссылается на объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) . Примером неустранимой ошибки является ошибка, которая возникает, если не удается завершить определенный процесс. Вызов метода [System. Management. Automation. командлет. WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) позволяет пользователю последовательно выполнять запрошенные действия и хранить сведения о конкретных действиях, которые не удалось выполнить. Командлет должен обрабатывать каждую запись как можно независимо.

- На объект [System. Management](/dotnet/api/System.Management.Automation.ErrorRecord) . Automation. ерроррекорд, на который ссылается метод [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) и [System. Management. Automation. командлет. WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , требуется исключение в ядре. При определении используемого исключения следуйте рекомендациям по проектированию .NET Framework. Если ошибка семантически аналогична существующему исключению, используйте это исключение или производные от этого исключения. В противном случае создайте новое исключение или иерархию исключений непосредственно из типа [System. Exception](/dotnet/api/System.Exception) .

Объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) также требует категорию ошибок, которая группирует ошибки для пользователя. Пользователь может просматривать ошибки на основе категории, присвоив переменной `$ErrorView` оболочки значение Категоривиев. Возможные категории определяются перечислением [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) .

- Если командлет создает новый поток, и если код, выполняемый в этом потоке, создает необработанное исключение, Windows PowerShell не будет перехватывать ошибку и завершит процесс.

- Если у объекта есть код в его деструкторе, который вызывает необработанное исключение, Windows PowerShell не будет перехватывать ошибку и завершит процесс. Это также происходит, если объект вызывает методы Dispose, вызывающие необработанное исключение.

### <a name="use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07"></a>Использование модуля Windows PowerShell для развертывания командлетов (RC07)

Создайте модуль Windows PowerShell для упаковки и развертывания командлетов. Поддержка модулей представлена в Windows PowerShell 2,0. Сборки, содержащие классы командлетов, можно использовать непосредственно в виде файлов двоичных модулей (это очень удобно при тестировании командлетов) или создать манифест модуля, который ссылается на сборки командлетов. (При использовании модулей можно также добавить существующие сборки оснастки). Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>См. также:

[Настоятельно рекомендуется руководство по разработке](./strongly-encouraged-development-guidelines.md)

[Рекомендации по разработке рекомендаций](./advisory-development-guidelines.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

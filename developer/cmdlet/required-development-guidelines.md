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
ms.openlocfilehash: a4b228be91bba27670b26fe21e765ae942afe968
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860720"
---
# <a name="required-development-guidelines"></a>Обязательные требования к разработке

При написании командлетов, должен следовать приведенным ниже рекомендациям. Они разделяются на рекомендации по разработке командлетов и рекомендации по написанию кода командлета. Если не следовать рекомендациям, командлетов может привести к сбою, а у пользователей могут быть слишком ограничивать возможности при использовании командлетов.

## <a name="in-this-topic"></a>В этом разделе

### <a name="design-guidelines"></a>Рекомендации по проектированию

- [Используйте только утвержденные глаголы (RD01)](./required-development-guidelines.md#use-only-approved-verbs-rd01)

- [Имена командлетов: Нельзя использовать символы (RD02)](./required-development-guidelines.md#cmdlet-names-characters-that-cannot-be-used-rd02)

- [Имена параметров, которые нельзя использовать (RD03)](./required-development-guidelines.md#parameters-names-that-cannot-be-used-rd03)

- [Запросы в службу поддержки подтверждения (RD04)](./required-development-guidelines.md#support-confirmation-requests-rd04)

- [Поддерживает параметр Force для интерактивных сеансов (RD05)](./required-development-guidelines.md#support-force-parameter-for-interactive-sessions-rd05)

- [Объекты документа вывода (RD06)](./required-development-guidelines.md#document-output-objects-rd06)

### <a name="code-guidelines"></a>Руководствам по кодам

- [Наследовать из командлета или классы PSCmdlet (RC01)](./required-development-guidelines.md#derive-from-the-cmdlet-or-pscmdlet-classes-rc01)

- [Укажите атрибут командлета (RC02)](./required-development-guidelines.md#specify-the-cmdlet-attribute-rc02)

- [Переопределите метод (RC03) обработки входных данных](./required-development-guidelines.md#override-an-input-processing-method-rc03)

- [Укажите атрибута OutputType (RC04)](./required-development-guidelines.md#specify-the-outputtype-attribute-rc04)

- [Не сохраняют дескрипторы для вывода объектов (RC05)](./required-development-guidelines.md#do-not-retain-handles-to-output-objects-rc05)

- [Надежно обрабатывать ошибки (RC06)](./required-development-guidelines.md#handle-errors-robustly-rc06)

- [Использовать модуль Windows PowerShell для развертывания командлеты (RC07)](./required-development-guidelines.md#use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07)

## <a name="design-guidelines"></a>Рекомендации по проектированию

При разработке командлетов, чтобы обеспечить согласованность пользовательского интерфейса между использованием командлетов и другими командлетами, должен следовать приведенным ниже рекомендациям. Когда вы найдете рекомендации разработки для этого применяется в вашей ситуации, убедитесь, что рассмотрим руководствам по кодам аналогичные инструкции.

### <a name="use-only-approved-verbs-rd01"></a>Используйте только утвержденные глаголы (RD01)

Команды, указанной в атрибуте командлета должны поступать из распознанных набор команд, предоставляемых Windows PowerShell. Он не должен быть одним из запрещенных синонимы. Используйте константных строк, которые определяются следующие перечисления для указания команды cmdlet.

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)

- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)

- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)

- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)

- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)

Дополнительные сведения об именах утвержденного глагола см. в разделе [глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Пользователи должны набор имен доступными и ожидаемый командлет. Таким образом, чтобы пользователь мог принять быструю оценку того, что делает командлет и легко находить возможности системы, используйте соответствующую команду. Например, следующую команду Получает список всех команд в системе, имена которых начинаются с «start»: `get-command start-*`. Используйте существительные в командлеты для различения командлеты другие командлеты. Существительное указывает на ресурс, на котором выполняется операция. Сама операция представляется команды.

### <a name="cmdlet-names-characters-that-cannot-be-used-rd02"></a>Имена командлетов: Нельзя использовать символы (RD02)

При вводе имени командлеты, не используйте следующие специальные символы.

|Символ|Name|
|---------------|----------|
|#|знак числа|
|,|Запятая|
|()|Круглые скобки|
|{}|фигурные скобки|
|[]|квадратные скобки|
|&|амперсанд|
|-|дефис **Примечание:**  Дефис может использоваться для разделения команды с существительным, но его нельзя использовать внутри существительное или команды.|
|/|косая черта|
|\|обратная косая черта|
|$|Знак доллара|
|^|Курсор|
|;|Точка с запятой|
|.|Двоеточие|
|"|двойная кавычка|
|'|одинарная кавычка|
|<>|угловые скобки|
|&#124;|Вертикальная черта|
|?|вопросительный знак|
|@|знак|
|"| резервного кавычки (апостроф)|
|*|Звездочка|
|%|Знак процента|
|+|Знак "плюс"|
|=|Знак равенства|
|~|tilda|

### <a name="parameters-names-that-cannot-be-used-rd03"></a>Имена параметров, которые нельзя использовать (RD03)

Windows PowerShell предоставляет общий набор параметров для всех командлетов, а также дополнительные параметры, которые добавляются в определенных ситуациях. При разработке собственных командлетов нельзя использовать следующие имена: Подтвердите, Debug, ErrorAction, ErrorVariable, OutBuffer OutVariable, WarningAction, WarningVariable, WhatIf, UseTransaction и многословными. Дополнительные сведения об этих параметрах см. в разделе [общие имена параметров](./common-parameter-names.md).

### <a name="support-confirmation-requests-rd04"></a>Запросы в службу поддержки подтверждения (RD04)

Для командлетов, выполните операцию, которая изменяет система, им следует вызвать [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод запросит подтверждение, а в особых случаях вызвать [ System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод. ( [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод должен вызываться только после [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывается метод.)

Для выполнения этих вызовов, командлет необходимо указать, что он поддерживает запросы подтверждения, присвоив `SupportsShouldProcess` ключевое слово атрибута командлет. Дополнительные сведения о настройке этого атрибута см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).

> [!NOTE]
> Если атрибут командлета командлет класса указывает, что командлет поддерживает вызовы [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод и командлет не может обеспечить вызов [ System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод, пользователь может изменять система неожиданно.

Используйте [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метода для каких-либо изменений системы. Пользовательские настройки и `Whatif` элемент управления параметром [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод. Напротив [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызов выполняет дополнительную проверку для потенциально опасных изменений. Этот метод не может контролировать все пользовательские настройки или `Whatif` параметра. Если в командлете вызывает [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод, он должен иметь `Force` параметр, который обходит вызовы к этим двум методам, после чего, с операцией. Это важно, так как она допускает командлета для использования в запуске неинтерактивных сценариев и узлов.

Если командлеты поддерживает эти вызовы, пользователь может определить, ли действие фактически должно быть выполнено. Например [Stop-Process](/powershell/module/microsoft.powershell.management/stop-process) вызывает командлет [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод до остановки набор критических процессов, включая систему, Winlogon, и Spoolsrv процессов.

Дополнительные сведения о поддержке этих методов см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

### <a name="support-force-parameter-for-interactive-sessions-rd05"></a>Поддерживает параметр Force для интерактивных сеансов (RD05)

Если командлет используется в интерактивном режиме, всегда укажите параметр Force, чтобы переопределить интерактивные действия, такие как запросы и чтение строк входных данных). Это важно, так как она допускает командлета для использования в запуске неинтерактивных сценариев и узлов. Следующие методы можно реализовать интерактивный для узла.

- [System.Management.Automation.Host.PSHostUserInterface.Prompt*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.Prompt)

- [System.Management.Automation.Host.Pshostuserinterface.PromptForChoice](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForChoice)

- [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection.PromptForChoice](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection.PromptForChoice)

- [System.Management.Automation.Host.Pshostuserinterface.PromptForCredential*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForCredential)

- [System.Management.Automation.Host.Pshostuserinterface.ReadLine*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLine)

- [System.Management.Automation.Host.Pshostuserinterface.ReadLineAsSecureString*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLineAsSecureString)

### <a name="document-output-objects-rd06"></a>Объекты документа вывода (RD06)

Windows PowerShell использует объекты, которые записываются в конвейер. В соответствующем порядке для пользователей, чтобы воспользоваться преимуществами объекты, возвращаемые для каждого командлета, возвращаемые объекты должны быть документированы и необходимо задокументировать, для чего используются членами этих возвращаемых объектов.

## <a name="code-guidelines"></a>Руководствам по кодам

При написании кода командлет, должен следовать приведенным ниже рекомендациям. Когда вы найдете рекомендации код для этого применяется в вашей ситуации, убедитесь, что рассмотрим рекомендации по проектированию аналогичные инструкции.

### <a name="derive-from-the-cmdlet-or-pscmdlet-classes-rc01"></a>Наследовать из командлета или классы PSCmdlet (RC01)

Командлет должен быть производным от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) или [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса. Командлеты, которые являются производными от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса не зависят от среды выполнения Windows PowerShell. Они могут вызываться непосредственно из любого языка Microsoft .NET Framework. Командлеты, которые являются производными от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класс зависят от среды выполнения Windows PowerShell. Таким образом они выполняются в пространство выполнения.

Все классы командлет, реализации должен быть открытых классов. Дополнительные сведения об этих классах командлета см. в разделе [Обзор командлетов](./cmdlet-overview.md).

### <a name="specify-the-cmdlet-attribute-rc02"></a>Укажите атрибут командлета (RC02)

Для командлета, распознаваемых Windows PowerShell его класс .NET Framework должны быть оснащены атрибутом командлет. Этот атрибут задает следующие функции командлета.

- Пара "глагол существительное", определяющий командлет.

- Набор параметров по умолчанию используется, если указано несколько наборов параметров. Набор параметров по умолчанию используется в том случае, когда Windows PowerShell не имеет достаточно информации для определения, какой набор параметров следует использовать.

- Указывает, поддерживает ли командлет вызовы [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод. Этот метод отображает сообщение с подтверждением для пользователя, прежде, чем командлет вносит изменение в систему. Дополнительные сведения о том, как выполняются запросы подтверждения, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

- Укажите уровень влияния (или серьезность) действие, связанное с сообщением подтверждения. В большинстве случаев следует использовать значение по умолчанию среды. Дополнительные сведения о влиянии уровень влияния на запросы подтверждения, которые отображаются для пользователя, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

Дополнительные сведения о том, как объявить атрибут командлета см. в разделе [объявление CmdletAttribute](./cmdlet-attribute-declaration.md).

### <a name="override-an-input-processing-method-rc03"></a>Переопределите метод (RC03) обработки входных данных

Командлет, чтобы участвовать в среде Windows PowerShell, его необходимо переопределить по крайней мере одно из следующих *методы обработки ввода*.

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) этот метод вызывается один раз, и он используется для предоставления функциональных возможностей предварительной обработки.

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) этот метод вызывается несколько раз, и он используется для предоставления функциональности записи по.

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) этот метод вызывается один раз, и он используется для предоставления функций постобработки.

### <a name="specify-the-outputtype-attribute-rc04"></a>Укажите атрибута OutputType (RC04)

Атрибут OutputType (впервые появилась в Windows PowerShell 2.0) тип .NET Framework, командлет возвращает в конвейер. Указав тип выходных данных командлетов сделать объекты, возвращенные командлета обнаружение других командлетов. Дополнительные сведения о Декорирование класса cmdlet этим атрибутом, см. в разделе [объявление атрибута OutputType](./outputtype-attribute-declaration.md).

### <a name="do-not-retain-handles-to-output-objects-rc05"></a>Не сохраняют дескрипторы для вывода объектов (RC05)

Командлет не должен сохранить все дескрипторы объектов, которые передаются [System.Management.Automation.Cmdlet.WriteObject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод. Эти объекты передаются следующему командлету в конвейере, или они используются с помощью сценария. Если вы сохраните дескрипторов к объектам, две сущности будет принадлежать каждый объект, который приводит к возникновению ошибок.

### <a name="handle-errors-robustly-rc06"></a>Надежно обрабатывать ошибки (RC06)

Администрирование среды по своей природе обнаруживает и вносит важные изменения в системе, где осуществляется Администрирование. Крайне важно правильно обрабатывать ошибки командлетов. Дополнительные сведения о записи об ошибках, см. в разделе [отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md).

- Ошибка препятствует командлета продолжит обрабатывать все большее число записей, при неустранимую ошибку. Необходимо вызвать командлет [System.Management.Automation.Cmdlet.ThrowTerminatingError*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) метод, который ссылается на [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта. Если исключение не перехвачено с помощью командлета, в самой среде выполнения Windows PowerShell создает неустранимую ошибку, которая содержит меньше информации.

- Неустранимая ошибка, которая не останавливает операцию при следующем необходимо вызвать метод записи, которая поступает из конвейера (например, запись создается другим процессом), командлет [System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод, который ссылается на [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта. Примером неустранимой ошибки является ошибка, которая возникает, если не удается остановить определенный процесс. Вызов [System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод позволяет пользователю постоянно выполняющие действий, запрошенных и сохранения сведений для определенного действия, завершившиеся сбоем. Командлет для независимой обработки каждой записи.

- [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта, на который ссылается [System.Management.Automation.Cmdlet.ThrowTerminatingError*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) и [ System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) методы требует исключение по своей сути. Выполните рекомендации по разработке .NET Framework, если определить исключение для использования. Если ошибка является семантически так же, как существующие исключения, используйте это исключение или являются производными от этого исключения. В противном случае — наследовать новое исключение, либо иерархия исключений непосредственно из [System.Exception](/dotnet/api/System.Exception) типа.

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта также требуется категории ошибок, группирующий ошибок для пользователя. Пользователь может просмотреть ошибки по категории, установив значение `$ErrorView` переменной оболочки для CategoryView. Возможные категории определяются [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) перечисления.

- Командлет создает новый поток, если код, выполняемый в этом потоке вызывает необработанное исключение, Windows PowerShell не перехватывает ошибку и завершает процесс.

- Если объект имеет код в деструкторе, приводит к возникновению необработанного исключения, Windows PowerShell не перехватывает ошибку и завершает процесс. Это также происходит, если объект вызывает метод Dispose, возникновения необработанного исключения.

### <a name="use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07"></a>Использовать модуль Windows PowerShell для развертывания командлеты (RC07)

Создание модуля Windows PowerShell для упаковки и развертывания командлетов. Поддержка модулей впервые появился в Windows PowerShell 2.0. Вы можете использовать сборок, содержащих классы командлет непосредственно как файлы двоичных модулей (это очень полезно при тестировании командлетов), или можно создать манифест модуля, ссылается на сборки командлет. (Можно также добавить существующие сборки оснастки при использовании модулей.) Дополнительные сведения о модулях см. в разделе [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>См. также

[Рекомендации по настоятельно рекомендуется и разработка](./strongly-encouraged-development-guidelines.md)

[Рекомендации по разработке рекомендаций](./advisory-development-guidelines.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

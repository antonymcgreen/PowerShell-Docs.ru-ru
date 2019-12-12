---
title: Обзор командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK]
- cmdlets [PowerShell SDK], described
ms.assetid: 0aa32589-4447-4ead-a5dd-a3be99113140
caps.latest.revision: 21
ms.openlocfilehash: 14200aed2fb94c37c8b8af29650f602945e7ac1c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365893"
---
# <a name="cmdlet-overview"></a>Общие сведения о командлетах

Командлет — это упрощенная команда, используемая в среде Windows PowerShell. Среда выполнения Windows PowerShell вызывает эти командлеты в контексте скриптов автоматизации, предоставленных в командной строке. Среда выполнения Windows PowerShell также вызывает их программно с помощью API-интерфейсов Windows PowerShell.

## <a name="cmdlets"></a>Командлеты

Командлеты выполняют действие и обычно возвращают объект Microsoft .NET Framework в следующую команду в конвейере. Для написания командлета необходимо реализовать класс командлета, производный от одного из двух специализированных базовых классов командлетов. Производный класс должен:

- Объявите атрибут, который идентифицирует производный класс в качестве командлета.

- Определите открытые свойства, снабженные атрибутами, которые определяют открытые свойства в качестве параметров командлета.

- Переопределите один или несколько методов обработки ввода для обработки записей.

Сборку, содержащую класс, можно загрузить напрямую с помощью командлета [Import-Module](/powershell/module/microsoft.powershell.core/import-module) . также можно создать ведущее приложение, которое загружает сборку с помощью API [System. Management. Automation. пространства](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) выполнения. Initialsessionstate. Оба метода предоставляют программный и доступ командной строки к функциональности командлета.

## <a name="cmdlet-terms"></a>Условия для командлетов

В документации по командлетам Windows PowerShell часто используются следующие термины:

### <a name="cmdlet-attribute"></a>Атрибут командлета

Атрибут .NET Framework, используемый для объявления класса командлета в качестве командлета.
Хотя PowerShell использует несколько других атрибутов, которые являются необязательными, атрибут командлета является обязательным.
Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута командлета](cmdlet-attribute-declaration.md).

### <a name="cmdlet-parameter"></a>Параметр командлета

Открытые свойства, определяющие параметры, доступные пользователю или приложению, запускающему командлет.
Командлеты могут иметь обязательные параметры, именованные, позиционированные и *переключатели* .
Параметры переключателя позволяют определить параметры, которые оцениваются, только если в вызове указаны параметры.
Дополнительные сведения о различных типах параметров см. в разделе [параметры командлета](cmdlet-parameters.md).

### <a name="parameter-set"></a>Набор параметров

Группа параметров, которые можно использовать в одной команде для выполнения определенного действия.
Командлет может иметь несколько наборов параметров, но каждый набор параметров должен иметь по крайней мере один уникальный параметр.
Хорошая разработка командлетов настоятельно предполагает, что уникальный параметр также является обязательным параметром.
Дополнительные сведения о наборах параметров см. в разделе [наборы параметров командлета](cmdlet-parameter-sets.md).

### <a name="dynamic-parameter"></a>Динамический параметр

Параметр, добавляемый в командлет во время выполнения.
Как правило, динамические параметры добавляются в командлет, если для другого параметра задано конкретное значение.
Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета](cmdlet-dynamic-parameters.md).

### <a name="input-processing-method"></a>Метод обработки входных данных

Метод, который командлет может использовать для обработки записей, получаемых в качестве входных данных.
Методы обработки входных данных включают метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) , метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , метод [System. Management. Automation.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) командлет. EndProcessing и метод [System. Management. Automation. командлет. StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) . При реализации командлета необходимо переопределить по крайней мере один из методов [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)и [System. Management. EndProcessing.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .
Как правило, метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) является переопределяемым методом, поскольку он вызывается для каждой записи, обрабатываемой командлетом.
Напротив, метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) вызываются один раз для выполнения предварительной или завершающей обработки записей.
Дополнительные сведения об этих методах см. в разделе [методы обработки входных данных](cmdlet-input-processing-methods.md).

### <a name="shouldprocess-feature"></a>Функция ShouldProcess

PowerShell позволяет создавать командлеты, предлагающие пользователю отправить отзыв, прежде чем командлет вносит изменения в систему.
Чтобы использовать эту функцию, командлет должен объявить, что он поддерживает функцию ShouldProcess при объявлении атрибута командлета, и командлет должен вызвать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из метода обработки входных данных.
Дополнительные сведения о поддержке функций ShouldProcess см. в разделе [запрос подтверждения](requesting-confirmation-from-cmdlets.md).

### <a name="transaction"></a>Transaction

Логическая группа команд, обрабатываемых как одна задача.
Задача автоматически завершается ошибкой, если любая команда в группе завершается ошибкой, и пользователь может принять или отклонить действия, выполненные внутри транзакции.
Чтобы принять участие в транзакции, командлет должен объявить, что он поддерживает транзакции при объявлении атрибута командлета.
Поддержка транзакций появилась в Windows PowerShell 2,0.
Дополнительные сведения о транзакциях см. [в разделе Поддержка транзакций](how-to-support-transactions.md).

## <a name="how-cmdlets-differ-from-commands"></a>Отличия командлетов от команд

Командлеты отличаются от команд в других средах командной оболочки следующими способами.

- Командлеты являются экземплярами .NET Framework классов; они не являются изолированными исполняемыми файлами.

- Командлеты можно создавать с помощью нескольких десятков строк кода.

- Командлеты обычно не выполняют собственный синтаксический анализ, представление ошибок или форматирование выходных данных. Синтаксический анализ, представление ошибок и форматирование вывода обрабатываются средой выполнения Windows PowerShell.

- Командлеты обрабатывают входные объекты из конвейера, а не из потоков текста, а командлеты обычно доставляют объекты в конвейер в качестве выходных данных.

- Командлеты ориентированы на записи, так как они обрабатывают один объект за раз.

## <a name="cmdlet-base-classes"></a>Базовые классы командлетов

Windows PowerShell поддерживает командлеты, которые являются производными от следующих двух базовых классов.

- Большинство командлетов основаны на .NET Framework классах, производных от базового класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) . Наследование от этого класса позволяет командлету использовать минимальный набор зависимостей в среде выполнения Windows PowerShell. Это имеет два преимущества. Первое преимущество заключается в том, что объекты командлетов меньше, и, скорее всего, изменения в среде выполнения Windows PowerShell подвергаются меньшему. Второе преимущество заключается в том, что при необходимости можно напрямую создать экземпляр объекта командлета, а затем вызвать его напрямую, а не вызывать его через среду выполнения Windows PowerShell.

- Более сложные командлеты основаны на .NET Framework классах, производных от базового класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) . Наследование от этого класса обеспечивает гораздо больший доступ к среде выполнения Windows PowerShell. Этот доступ позволяет командлету вызывать скрипты, получать доступ к поставщикам и получать доступ к текущему состоянию сеанса. (Для доступа к текущему состоянию сеанса вы получаете и устанавливаете переменные сеанса и настройки.) Однако наследование от этого класса увеличивает размер объекта командлета, и это означает, что командлет более тесно связан с текущей версией среды выполнения Windows PowerShell.

Как правило, если вам не нужен расширенный доступ к среде выполнения Windows PowerShell, необходимо создать производный от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) . Однако среда выполнения Windows PowerShell имеет широкие возможности ведения журнала для выполнения командлетов. Если модель аудита зависит от этого журнала, можно предотвратить выполнение командлета из другого командлета, производя от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .

## <a name="input-processing-methods"></a>Методы обработки входных данных

Класс [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) предоставляет следующие виртуальные методы, используемые для обработки записей. Все производные классы командлетов должны переопределять один или несколько первых трех методов:

- [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing): используется для предоставления необязательных одноразовых функций предварительной обработки для командлета.

- [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord): используется для предоставления функций обработки записей по записям для командлета. Метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) может вызываться любое количество раз, в зависимости от входных данных командлета.

- [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing): используется для предоставления необязательных одноразовых функций последующей обработки для командлета.

- [System. Management. Automation. командлет. StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing): используется для остановки обработки, когда пользователь останавливает командлет асинхронно (например, нажав клавиши CTRL + C).

Дополнительные сведения об этих методах см. в разделе [методы обработки входных данных командлета](./cmdlet-input-processing-methods.md).

## <a name="cmdlet-attributes"></a>Атрибуты командлета

Windows PowerShell определяет несколько .NET Framework атрибутов, которые используются для управления командлетами и для указания общих функциональных возможностей, предоставляемых Windows PowerShell, которые могут потребоваться для командлета. Например, атрибуты используются для обозначения класса в качестве командлета, для указания параметров командлета и для запроса проверки входных данных, чтобы разработчикам командлета не применяли эту функциональность в своем коде командлета. Дополнительные сведения об атрибутах см. в разделе [атрибуты Windows PowerShell](./cmdlet-attributes.md).

## <a name="cmdlet-names"></a>Имена командлетов

Windows PowerShell использует пару имен глагол-и-существительное для командлетов Name. Например, командлет `Get-Command`, включенный в Windows PowerShell, используется для получения всех командлетов, зарегистрированных в командной оболочке. Команда определяет действие, выполняемое командлетом, а существительное определяет ресурс, в котором командлет выполняет свое действие.

Эти имена указываются, когда класс .NET Framework объявляется как командлет. Дополнительные сведения об объявлении класса .NET Framework в качестве командлета см. в разделе [объявление атрибута командлета](./cmdlet-class-declaration.md).

## <a name="writing-cmdlet-code"></a>Написание кода командлета

В этом документе представлены два способа определения способа написания кода командлета. Если вы предпочитаете Просмотреть код без подробного объяснения, см. [примеры кода командлета](./examples-of-cmdlet-code.md). Если вы предпочитаете более подробное описание кода, см. статью учебник по [процедурам](./getproc-tutorial.md) [Стоппрок](./stopproc-tutorial.md)или руководства [селектстр](./selectstr-tutorial.md) .

Дополнительные сведения о рекомендациях по написанию командлетов см. в разделе [рекомендации по разработке командлетов](./cmdlet-development-guidelines.md).

## <a name="see-also"></a>См. также:

[Основные понятия о командлетах Windows PowerShell](./windows-powershell-cmdlet-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

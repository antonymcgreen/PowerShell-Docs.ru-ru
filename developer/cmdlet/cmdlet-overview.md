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
ms.openlocfilehash: f8a8c9300d1ac811c7fbbf7050dd24f78306db8f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056674"
---
# <a name="cmdlet-overview"></a>Общие сведения о командлетах

Командлет является упрощенная команда, которая используется в среде Windows PowerShell. Среда выполнения Windows PowerShell вызывает эти командлеты в контексте скриптов автоматизации, которые предоставляются в командной строке. Среда выполнения Windows PowerShell также вызывает их программно через API-интерфейсы Windows PowerShell.

## <a name="cmdlets"></a>Командлеты

Командлеты выполняют действия и обычно возвращают объект Microsoft .NET Framework в следующую команду в конвейере. Чтобы создать командлет, должен реализовать класса cmdlet, который является производным от одного из двух базовых классов специализированного командлета. Производный класс должен:

- Объявите атрибут, определяющий производного класса как командлет.

- Определение открытых свойств, обозначенных с помощью атрибутов, которые идентифицируют общих свойств как параметры командлета.

- Переопределите один или несколько входных данных, методы для обработки записей обработки.

Вы можете загрузить сборку, содержащую класс напрямую с помощью [Import-Module](/powershell/module/microsoft.powershell.core/import-module) командлета, или можно создать ведущее приложение, которое загружает сборку с помощью [ System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) API. Оба метода предоставляют командную строку и программный доступ к функциям этого командлета.

## <a name="cmdlet-terms"></a>Командлет условия

В документации по командлетам Windows PowerShell часто используются следующие термины:

- **Атрибут командлета**: Атрибут .NET Framework, который используется для объявления в классе кандлетов как командлет. Несмотря на то, что Windows PowerShell использует несколько атрибутов, которые не являются обязательными, командлет атрибут является обязательным. Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).

- **Параметр командлета**: Открытые свойства, которые определяют параметры, которые доступны пользователю или приложению, на котором выполняется командлет. Командлеты можно установить обязательные, именованный, позиционные, и *переключения* параметров. Параметры-переключатели позволяют определять параметры, которые вычисляются только в том случае, если параметры указываются в вызове. Дополнительные сведения о различных типах параметров, см. в разделе [параметры командлета](./cmdlet-parameters.md).

- **Набор параметров**: Группа параметров, которые можно использовать в одной команде для выполнения определенного действия. У командлета может быть несколько наборов параметров, но каждый набор параметров должен иметь по крайней мере один параметр, который является уникальным. Структуры хороший командлетов строго предполагает, что параметр unique командлета также быть обязательным параметром. Дополнительные сведения о наборах параметров см. в разделе [командлет задает параметр](./cmdlet-parameter-sets.md).

- **Динамический параметр**: Параметр, который добавляется в командлет во время выполнения. Как правило динамические параметры добавляются в командлет при другой установлено определенное значение. Дополнительные сведения о динамических параметров, см. в разделе [динамические параметры командлета](./cmdlet-dynamic-parameters.md).

- **Метод обработки ввода**: Метод, который командлет может использовать для обработки записей, получаемых в качестве входных данных. Методы обработки ввода включают в себя [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метода [ System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод и [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) метод. При реализации командлета, необходимо переопределить хотя бы один из [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)и [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) методы. Как правило [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод — метод, который вы переопределить, так как он вызывается для каждой записи, которая обрабатывает командлет. Напротив [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод и [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метода вызываются один раз для выполнения Предварительная обработка или последующей обработки записей. Дополнительные сведения об этих методах см. в разделе [методы обработки ввода](./cmdlet-input-processing-methods.md).

- **Функция ShouldProcess**: Windows PowerShell позволяет создавать командлеты, которые пользователю запрос на отзыв прежде, чем командлет вносит изменение в систему. Чтобы использовать эту функцию, командлет необходимо объявить, что он поддерживает возможность ShouldProcess, при объявлении атрибута командлет, и необходимо вызвать командлет [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [ System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы в метод обработки входных данных. Дополнительные сведения о том, как для поддержки функций ShouldProcess см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

- **Транзакции**: Логическая группа команд, которые обрабатываются как одну задачу. Задача будет автоматически выполнена Если команд в группе завершается ошибкой, и у пользователя есть возможность принять или отклонить действия, выполняемые в рамках транзакции. Для участия в транзакции, командлет необходимо объявить, что он поддерживает транзакции, при объявлении атрибута командлет. Поддержка транзакций появилась в Windows PowerShell 2.0. Дополнительные сведения о транзакциях см. в разделе [транзакции Windows PowerShell](http://msdn.microsoft.com/en-us/74d7bac7-bc53-49f1-a47a-272e8da84710).

## <a name="how-cmdlets-differ-from-commands"></a>Командлеты отличаются от команд

Командлеты отличаются от команд в других средах командной оболочки одним из следующих способов:

- Командлеты являются экземплярами классов .NET Framework; они не являются автономного исполняемые файлы.

- Командлеты могут создаваться из всего лишь десяток строк кода.

- Командлеты обычно не делайте свои собственные синтаксического анализа, ошибка презентации или форматирование выходных данных. Синтаксический анализ, ошибка представления и форматирование выходных данных, обрабатываются средой выполнения Windows PowerShell.

- Командлеты обработка входных объектов из конвейера, а не из потоки текста, а командлеты обычно доставлять объекты как выходные данные в конвейер.

- Командлеты являются ориентированные на запись, так как они обрабатывают один объект за раз.

## <a name="cmdlet-base-classes"></a>Командлет базовых классов

Windows PowerShell поддерживает командлеты, которые являются производными от двух базовых классов.

- Большинство командлетов основаны на классы платформы .NET Framework, которые являются производными от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) базового класса. Наследование от этого класса позволяет командлету, чтобы использовать минимальный набор зависимостей от среды выполнения Windows PowerShell. Это дает два преимущества. Первый преимущество заключается в меньшие по размеру объектов командлет, что вы обычно не подвергаться влиянию изменений в среду выполнения Windows PowerShell. Это второй удобно, если необходимо, можно непосредственно создать экземпляр объекта командлета и затем вызвать его напрямую, вместо вызова этого метода до среды выполнения Windows PowerShell.

- Более сложные командлеты основаны на классы платформы .NET Framework, которые являются производными от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса. Наследование от этого класса дает гораздо более высокий уровень доступа к среде выполнения Windows PowerShell. Такой доступ позволяет командлета для вызова сценариев, чтобы получить доступ к поставщикам, а также для доступа к текущим состоянием сеанса. (Чтобы получить доступ к текущим состоянием сеанса, вы get и set переменные сеанса и предпочтений.) Тем не менее производного от этого класса увеличивает размер объекта, командлет, и это означает, что командлет более тесно связан с текущей версии среды выполнения Windows PowerShell.

Вообще говоря, если вам требуется расширенный доступ к среде выполнения Windows PowerShell, необходимо наследовать из [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса. Тем не менее среда выполнения Windows PowerShell имеет возможности подробные журналы для выполнения командлетов. Если модель аудита зависит это ведение журнала, можно предотвратить выполнение командлета в другой командлет путем наследования от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.

## <a name="input-processing-methods"></a>Методы обработки ввода

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класс предоставляет следующие виртуальные методы, которые используются для обработки записей. Все командлет производные классы должны переопределить один или несколько из первых трех методов:

- [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing): Используется для предоставления дополнительные однократные функциональные возможности предварительной обработки командлета.

- [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord): Используется для предоставления функциональности записи по обработке для командлета. [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод может вызываться любое число раз или вообще не, в зависимости от входных данных командлета.

- [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing): Используется для предоставления дополнительные однократные функциональные возможности завершающей обработки командлета.

- [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing): Используется для остановки обработки при остановке командлета пользователем асинхронно (например, нажав сочетание клавиш CTRL + C).

Дополнительные сведения об этих методах см. в разделе [методы обработки входных данных командлета](./cmdlet-input-processing-methods.md).

## <a name="cmdlet-attributes"></a>Атрибуты командлета

Windows PowerShell определяет несколько атрибутов .NET Framework, которые используются для управления командлеты и укажите общую функциональность, предоставляемую Windows PowerShell и может потребоваться с помощью командлета. Например атрибуты используются для назначения класса как командлет, для указания параметров командлета и запрашивает проверку входных данных, таким образом, разработчикам командлетов не нужно реализовать эту функциональность в своем коде командлета. Дополнительные сведения об атрибутах см. в разделе [Windows PowerShell атрибуты](./cmdlet-attributes.md).

## <a name="cmdlet-names"></a>Имена командлетов

Windows PowerShell использует пару существительное-имени в командлетах имя. Например `Get-Command` командлетов, включенных в Windows PowerShell используется для получения всех командлетов, которые зарегистрированы в командной оболочке. Команда определяет действие, выполняемое командлетом, а существительное определяет ресурс, на котором командлет выполняет его действие.

Эти имена указаны в том случае, когда .NET Framework класс объявляется как командлет. Дополнительные сведения о том, как объявить класс .NET Framework как командлет, см. в разделе [объявление атрибута командлет](./cmdlet-class-declaration.md).

## <a name="writing-cmdlet-code"></a>Написание кода командлета

Этот документ содержит два способа обнаружения, как командлет код. Если вы хотите просмотреть код без долгие объяснения, см. в разделе [код примеры командлета](./examples-of-cmdlet-code.md). Если вы предпочитаете более подробного объяснения о коде, см. в разделе [руководстве GetProc](./getproc-tutorial.md), [руководстве StopProc](./stopproc-tutorial.md), или [SelectStr руководстве](./selectstr-tutorial.md) разделы.

Дополнительные сведения о назначении написание командлетов см. в разделе [рекомендации по разработке командлет](./cmdlet-development-guidelines.md).

## <a name="see-also"></a>См. также

[Основные понятия Windows PowerShell командлет](./windows-powershell-cmdlet-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

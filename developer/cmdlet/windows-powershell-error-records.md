---
title: Ошибка Windows PowerShell записывает | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error category [PowerShell SDK]
- error identifier [PowerShell SDK]
- error records [PowerShell SDK]
- error category string [PowerShell SDK]
ms.assetid: bdd66fea-eb63-4bb6-9cbe-9a799e5e0db5
caps.latest.revision: 9
ms.openlocfilehash: f6f5e50c55b477cbbeeaaf4f3ea665d5dc07758c
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059768"
---
# <a name="windows-powershell-error-records"></a>Записи об ошибках Windows PowerShell

Командлеты необходимо передать [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) , определяющий состояния ошибки для завершающего и устранимые ошибки.

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объект содержит следующие сведения:

- Исключение, которое описывает ошибку. Часто это исключение, которое командлет перехвачено и преобразуются в записи об ошибке. Каждая ошибка запись может содержать исключение.

Если командлет не удалось перехватить исключение, его необходимо создать новое исключение и выберите класс исключений, который лучше всего описывает условие ошибки. Тем не менее, не нужно создавать исключение, так как он может осуществляться через [System.Management.Automation.ErrorRecord.Exception](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) свойство [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)объекта.

- Идентификатор ошибки, который предоставляет целевые обозначение, который может использоваться для диагностики и скриптами Windows PowerShell для обработки условия возникновения данной ошибки с обработчиками определенных ошибок. Каждой записи об ошибке должно содержать идентификатор ошибок (см. код ошибки).

- Категория ошибки, который предоставляет общие обозначение, который может использоваться для диагностики. Каждая запись ошибки необходимо указать категорию (см. категорию ошибки).

- Сообщение об ошибке необязательно замены и рекомендуемые действия (см. сообщение об ошибке замены).

- Вызов необязательные сведения о командлете, вызвавшего ошибку. Эта информация определяется Windows PowerShell (см. сообщение о вызове).

- Целевой объект, который обрабатывался во время возникновения ошибки. Это может быть входной объект, или может быть другой объект, который выполнял обработку командлета. Например, для команды `remove-item -recurse c:\somedirectory`, ошибка может быть экземпляром объекта FileInfo для «c:\somedirectory\lockedfile». Информации о целевой объект является необязательным.

## <a name="error-identifier"></a>Идентификатор ошибки

При создании записи об ошибке, укажите идентификатор, обозначающий условия ошибки в командлет. Windows PowerShell объединяет целевой идентификатор с именем командлета для создания идентификатора полное ошибки. Идентификатор ошибки полное может осуществляться через [System.Management.Automation.ErrorRecord.FullyQualifiedErrorId](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId) свойство [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)объекта. Идентификатор ошибки сама по себе недоступен. Он доступен только в качестве идентификатора полное ошибки.

Для создания идентификаторов ошибка при создании записи об ошибках, следуйте приведенным ниже рекомендациям:

- Сделать идентификаторы ошибки для ошибки. Целевые идентификаторы ошибок для диагностики, а также для сценариев, которые обрабатывают условия возникновения данной ошибки с обработчиками определенных ошибок. Пользователь должен иметь возможность использовать идентификатор ошибки для идентификации ошибки и ее источник. Идентификаторы ошибки также включить отчеты для конкретных условий ошибки из-за существующих исключений, таким образом, чтобы новые исключения подклассов не требуются.

- Как правило назначает идентификаторы другую ошибку на разных путей кода. Преимущества конечных пользователей из определенных идентификаторов. Часто, каждый путь кода, который вызывает [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) имеет собственный идентификатор. Как правило определите новый идентификатор, при определении новой строки шаблона для сообщение об ошибке и наоборот. Не используйте сообщение об ошибке в качестве идентификатора.

- При публикации кода, с помощью идентификатора конкретной ошибки, вы устанавливаете, что семантика ошибок с помощью этого идентификатора продукта полный жизненный цикл поддержки. Не использовать ее в контексте, который является семантически отличной от исходного контекста. Если изменить семантики эту ошибку, создайте и затем использовать новый идентификатор.

- Идентификатор конкретной ошибки следует использовать только для исключений определенного типа CLR. Тип исключения типа целевого объекта при изменении, создать и затем использовать новый идентификатор.

- Выберите текст для вашего идентификатора ошибки, кратко соответствует ошибке, вы сообщаете. Используйте соглашения об именовании и регистр букв standard .NET Framework. Не используйте пробелы или знаки препинания. Не следует локализировать ошибке идентификаторы.

- Не создавать идентификаторы ошибка динамически невоспроизводимых способом. Например не включают сведения об ошибке, например идентификатор процесса. Ошибка идентификаторы полезны только в том случае, если они соответствуют идентификаторам ошибки видны другим пользователям, у которых возникают то же условие ошибки.

## <a name="error-category"></a>Категория ошибки

Когда вы создаете записи об ошибке, указать категорию ошибки с использованием одной из констант, определенных [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory) перечисления. Windows PowerShell использует категорию ошибки для отображения сведений об ошибке, когда пользователи `$ErrorView` переменной `"CategoryView"`.

Избегайте использования [System.Management.Automation.Errorcategory.Notspecified](/dotnet/api/System.Management.Automation.ErrorCategory.NotSpecified) константы. Если у вас есть все данные об ошибке или об операции, которая вызвала ошибку, выберите категорию, которая лучше всего описывает ошибку или операции, даже если категории не является идеальным дополнением.

Информация, отображаемая в Windows PowerShell, называется строка вид по категориям и построена на основе свойств [System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo) класса. (Этот класс осуществляется через ошибки [System.Management.Automation.ErrorRecord.CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) свойство.)

```
{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}
```

Ниже приводятся отображаемые сведения.

- Категория: Определяемые Windows PowerShell [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory) константы.

- TargetName: По умолчанию имя объекта командлет выполнял обработку при возникновении ошибки. Или, другой строкой, определяемой командлет.

- TargetType: По умолчанию, тип целевого объекта. Или, другой строкой, определяемой командлет.

- Действие: По умолчанию имя командлета, для которого создана запись об ошибке. Или же другую строку, определяемые командлет.

- Причина: По умолчанию, тип исключения. Или, другой строкой, определяемой командлет.

## <a name="replacement-error-message"></a>Сообщение об ошибке замены

При разработке запись об ошибке для командлета, сообщение об ошибке по умолчанию для ошибки поступают из текст сообщения по умолчанию в [System.Exception.Message](/dotnet/api/System.Exception.Message) свойство. Это свойство только для чтения, текст сообщения предназначено только для отладки (согласно рекомендациям .NET Framework). Мы рекомендуем создать сообщение об ошибке, которая заменяет или дополняет текст сообщения по умолчанию. Сделать сообщения более понятно для пользователей и более конкретные в командлет.

Предоставляемые в заменяющее сообщение [System.Management.Automation.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) объекта. Используйте один из следующих конструкторов этого объекта, так как они предоставляют сведения о дополнительных локализации, который может использоваться с Windows PowerShell.

- [ErrorDetails.ErrorDetails (командлет, строки, строки, объекта\[System.Management.Automation.ErrorDetails.%23Ctor%28System.Management.Automation.Cmdlet%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.ErrorDetails.%23ctor%28System.Management.Automation.Cmdlet%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29): Этот конструктор используется, если строки шаблона строку ресурса в той же сборке, в котором реализован командлет, или если вы хотите загрузить строку шаблона с помощью переопределения [System.Management.Automation.Cmdlet.GetResourceString ](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString) метод.

- [ErrorDetails.ErrorDetails (сборки, строки, строки, объекта\[System.Management.Automation.ErrorDetails.%23Ctor%28System.Reflection.Assembly%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.ErrorDetails.%23ctor%28System.Reflection.Assembly%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29): Этот конструктор используется, если строка шаблона в другой сборке и не загрузит его через переопределение [System.Management.Automation.Cmdlet.GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString).

Заменяющее сообщение должны соответствовать правилам разработки .NET Framework для записи сообщения об исключениях с небольшими различиями. Состояние правила, сообщения об исключениях, которые должны быть написаны для разработчиков. Для командлета пользователя должны быть написаны эти сообщения замены.

Сообщение об ошибке замены необходимо добавить перед [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) методы вызываются. Чтобы добавить сообщение замены, задайте [System.Management.Automation.ErrorRecord.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails) свойство записи об ошибке. Если это свойство имеет значение, Windows PowerShell отображает [System.Management.Automation.ErrorDetails.Message*](/dotnet/api/System.Management.Automation.ErrorDetails.Message) свойству, а не текст сообщения по умолчанию.

## <a name="recommended-action-information"></a>Рекомендуется использовать сведения о действии

[System.Management.Automation.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) объект также может предоставлять сведения о действиях рекомендуются, когда произошла ошибка.

## <a name="invocation-information"></a>Сведения о вызове

Если командлет использует [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) для сообщения запись об ошибке, Windows PowerShell автоматически добавляет сведения, описывающие команду, которая была вызвана ошибка. Эта информация предоставляется по [System.Management.Automation.Invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo) , содержащий имя командлета, для которого была вызвана командой, команда и сведения о конвейере или сценарии. Это свойство только для чтения.

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System.Management.Automation.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails)

[System.Management.Automation.Invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo)

[Отчетов об ошибках Windows PowerShell](./error-reporting-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

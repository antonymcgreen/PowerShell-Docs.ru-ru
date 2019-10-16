---
title: Записи об ошибках Windows PowerShell | Документация Майкрософт
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
ms.openlocfilehash: 5412d88b690a1f5f1ef387416e3bf9da3a32c95d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369113"
---
# <a name="windows-powershell-error-records"></a>Записи об ошибках Windows PowerShell

Командлеты должны передавать объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) , который определяет условие ошибки для завершающих и устранимых ошибок.

Объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) содержит следующие сведения:

- Исключение, описывающее ошибку. Часто это исключение, которое командлет перехватывает и преобразует в запись об ошибке. Каждая запись об ошибке должна содержать исключение.

Если командлет не перехватывает исключение, он должен создать новое исключение и выбрать класс исключения, который наилучшим образом описывает условие ошибки. Однако исключение не требуется, так как доступ к нему можно получить с помощью свойства [System. Management. Automation. ерроррекорд. Exception](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) объекта [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) .

- Идентификатор ошибки, предоставляющий целевой указатель, который может использоваться в целях диагностики и сценариях Windows PowerShell для обработки определенных условий ошибок с определенными обработчиками ошибок. Каждая запись об ошибке должна содержать идентификатор ошибки (см. Идентификатор ошибки).

- Категория ошибок, которая предоставляет общее обозначение, которое можно использовать в целях диагностики. Каждая запись об ошибке должна указывать категорию ошибок (см. раздел Категория ошибок).

- Необязательное сообщение об ошибке замены и рекомендуемое действие (см. сообщение об ошибке замены).

- Дополнительные сведения о вызове командлета, вызвавшего ошибку. Эти сведения указываются в Windows PowerShell (см. сообщение о вызове).

- Целевой объект, который был обработан при возникновении ошибки. Это может быть входной объект или другой объект, обрабатываемый командлетом. Например, для команды `remove-item -recurse c:\somedirectory` ошибка может быть экземпляром объекта FileInfo для "к:\сомедиректори\локкедфиле". Сведения о целевом объекте являются необязательными.

## <a name="error-identifier"></a>Идентификатор ошибки

При создании записи об ошибке укажите идентификатор, обозначающий условие ошибки в командлете. Windows PowerShell объединяет целевой идентификатор с именем командлета, чтобы создать полный идентификатор ошибки. Полный идентификатор ошибки можно получить с помощью свойства [System. Management. Automation. ерроррекорд. фулликуалифиедеррорид](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId) объекта [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) . Идентификатор ошибки недоступен для самого себя. Он доступен только в составе полного идентификатора ошибки.

При создании записей об ошибках следуйте приведенным ниже рекомендациям по созданию идентификаторов ошибок.

- Создание идентификаторов ошибок, относящихся к условию ошибки. Нацеливание идентификаторов ошибок для целей диагностики и скриптов, которые обрабатывали определенные условия ошибок с помощью конкретных обработчиков ошибок. Пользователь должен иметь возможность использовать идентификатор ошибки для идентификации ошибки и ее источника. Идентификаторы ошибок также позволяют создавать отчеты о конкретных условиях ошибок из существующих исключений, чтобы новые подклассы исключений не требовались.

- В общем случае назначьте разные идентификаторы ошибок разным путям кода. Преимущества конечных пользователей от конкретных идентификаторов. Часто каждый путь кода, вызывающий [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) , имеет свой собственный идентификатор. В качестве правила определите новый идентификатор при определении новой строки шаблона для сообщения об ошибке и наоборот. Не используйте сообщение об ошибке в качестве идентификатора.

- При публикации кода с использованием определенного идентификатора ошибки вы устанавливаете семантику ошибок с этим идентификатором для полного жизненного цикла поддержки продукта. Не используйте его в контексте, который семантически отличается от исходного контекста. При изменении семантики этой ошибки создайте и затем используйте новый идентификатор.

- Обычно конкретный идентификатор ошибки следует использовать только для исключений определенного типа CLR. Если тип исключения или тип целевого объекта изменяется, создайте и используйте новый идентификатор.

- Выберите текст для идентификатора ошибки, который кратко соответствует ошибке, о которой вы сообщаете. Используйте стандартные .NET Framework соглашения об именовании и капитализации. Не используйте пробелы или знаки препинания. Не следует локализовать идентификаторы ошибок.

- Не следует динамически создавать идентификаторы ошибок невоспроизводимым способом. Например, не следует включать сведения об ошибке, такие как идентификатор процесса. Идентификаторы ошибок полезны только в том случае, если они соответствуют идентификаторам ошибок, видимым другим пользователям, которые столкнулись с тем же условием ошибки.

## <a name="error-category"></a>Категория ошибки

При создании записи об ошибке укажите категорию ошибки с помощью одной из констант, определенных перечислением [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) . Windows PowerShell использует категорию ошибок для вывода сведений об ошибках, когда пользователь устанавливает переменную `$ErrorView` в `"CategoryView"`.

Старайтесь не использовать константу [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) **NotSpecified** . Если у вас есть какие-либо сведения об ошибке или об операции, вызвавшей ошибку, выберите категорию, которая лучше описывает ошибку или операцию, даже если категория не является идеальным соответствием.

Информация, отображаемая Windows PowerShell, называется строкой представления категории и строится на основе свойств класса [System. Management. Automation. ерроркатегоринфо](/dotnet/api/System.Management.Automation.ErrorCategoryInfo) . (Доступ к этому классу осуществляется через свойство Error [System. Management. Automation. ерроррекорд. CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) .)

```
{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}
```

В следующем списке описаны отображаемые сведения.

- Category: константа [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) , определяемая Windows PowerShell.

- TargetName: по умолчанию имя объекта, обрабатываемого командлетом при возникновении ошибки. Или другая строка, определяемая командлетом.

- TargetType: по умолчанию это тип целевого объекта. Или другая строка, определяемая командлетом.

- Действие: по умолчанию имя командлета, создавшего запись об ошибке. Или другая строка, определяемая командлетом.

- Причина: по умолчанию это тип исключения. Или другая строка, определяемая командлетом.

## <a name="replacement-error-message"></a>Сообщение об ошибке замены

При разработке записи об ошибке для командлета сообщение об ошибке по умолчанию поступает из текста сообщения по умолчанию в свойстве [System. Exception. Message](/dotnet/api/System.Exception.Message) . Это свойство только для чтения, текст сообщения которого предназначен только для целей отладки (в соответствии с рекомендациями .NET Framework). Рекомендуется создать сообщение об ошибке, которое заменит или дополнит текст сообщения по умолчанию. Сделайте сообщение более понятным для пользователя и более конкретным для командлета.

Заменяющее сообщение предоставляется объектом [System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) . Используйте один из следующих конструкторов этого объекта, так как они предоставляют дополнительные сведения о локализации, которые могут использоваться Windows PowerShell.

- [ErrorDetails (командлет, строка, строка, объект [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Management_Automation_Cmdlet_System_String_System_String_System_Object___). Используйте этот конструктор, если строка шаблона является строкой ресурса в той же сборке, в которой реализуется командлет, или если требуется загрузить строку шаблона через переопределение [ Метод System. Management. Automation. командлет. Жетресаурцестринг](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString) .

- [ErrorDetails (сборка, строка, строка, объект [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Reflection_Assembly_System_String_System_String_System_Object___): Используйте этот конструктор, если строка шаблона находится в другой сборке и вы не загрузили ее с помощью переопределения [System. Management. Automation. командлета. жетресаурцестринг](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString).

Сообщение о замене должно соответствовать .NET Framework правилам проектирования для написания сообщений об исключениях с небольшими различиями. Рекомендации о том, что сообщения об исключениях должны быть написаны для разработчиков. Эти замещающие сообщения должны быть написаны для пользователя командлета.

Сообщение об ошибке замены должно быть добавлено перед вызовом методов [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System. Management. Automation. командлета. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) . Чтобы добавить заменяющее сообщение, задайте свойство [System. Management. Automation. ерроррекорд. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails) записи об ошибке. Если это свойство задано, Windows PowerShell отображает свойство [System. Management. Automation. ErrorDetails. Message *](/dotnet/api/System.Management.Automation.ErrorDetails.Message) вместо текста сообщения по умолчанию.

## <a name="recommended-action-information"></a>Рекомендуемые сведения о действии

Объект [System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) также может предоставлять сведения о том, какие действия рекомендуются при возникновении ошибки.

## <a name="invocation-information"></a>Сведения о вызове

Если командлет использует [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) или [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) для передачи записи об ошибке, Windows PowerShell автоматически добавляет сведения, описывающие команда, которая была вызвана при возникновении ошибки. Эта информация предоставляется объектом [System. Management. Automation. инвокатионинфо](/dotnet/api/System.Management.Automation.InvocationInfo) , который содержит имя командлета, который был вызван командой, самой командой, а также сведения о конвейере или скрипте. Это свойство доступно только для чтения.

## <a name="see-also"></a>См. также:

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0)

[System. Management. Automation. Ерроркатегоринфо](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System. Management. Automation. Ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord)

[System. Management. Automation. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails)

[System. Management. Automation. Инвокатионинфо](/dotnet/api/System.Management.Automation.InvocationInfo)

[Отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

---
title: Рекомендации по разработке рекомендаций | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79c9bcbc-a2eb-4253-a4b8-65ba54ce8d01
caps.latest.revision: 9
ms.openlocfilehash: 871a74a084da3c7ec36767b7195461e0e7290cb9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068799"
---
# <a name="advisory-development-guidelines"></a>Советы по разработке

В этом разделе приводятся рекомендации, которые следует учитывать для предотвращения хороший опыт разработки и пользователя. Иногда они могут применяться, а иногда они не могут.

## <a name="design-guidelines"></a>Рекомендации по проектированию

- [Поддерживает параметр InputObject (AD01)](./advisory-development-guidelines.md#AD01)

- [Поддерживает параметр Force (AD02)](./advisory-development-guidelines.md#AD02)

- [Обработка учетных данных с помощью Windows PowerShell (AD03)](./advisory-development-guidelines.md#AD03)

- [Поддерживает параметры кодирования (AD04)](./advisory-development-guidelines.md#AD04)

- [Командлеты теста должен возвращать логическое значение (AD05)](./advisory-development-guidelines.md#AD05)

## <a name="code-guidelines"></a>Руководствам по кодам

- [Выполните командлет класс соглашения об именовании (AC01)](./advisory-development-guidelines.md#AC01)

- [Если отсутствуют входные данные конвейера переопределить метод BeginProcessing (AC02)](./advisory-development-guidelines.md#AC02)

- [Чтобы обрабатывать запросы остановки Переопределите метод StopProcessing (AC03)](./advisory-development-guidelines.md#AC03)

- [Реализовать интерфейс IDisposable (AC04)](./advisory-development-guidelines.md#AC04)

- [Типы параметров пригодным к сериализации (AC05)](./advisory-development-guidelines.md#AC05)

- [Используйте SecureString для конфиденциальных данных (AC06)](./advisory-development-guidelines.md#AC06)

## <a name="design-guidelines"></a>Рекомендации по проектированию

При разработке командлетов следует учитывать следующие рекомендации. Когда вы найдете рекомендации разработки для этого применяется в вашей ситуации, убедитесь, что рассмотрим руководствам по кодам аналогичные инструкции.

### <a name="support-an-inputobject-parameter-ad01"></a>Поддерживает параметр InputObject (AD01)

Поскольку Windows PowerShell работает непосредственно с объектами Microsoft .NET Framework, объект .NET Framework часто является доступным, что точно совпадает, тип пользователя необходимо выполнение определенной операции. `InputObject` — Это стандартное имя для параметра, который принимает такой объект в качестве входных данных. К примеру, образец **Stop-Proc** командлет в [руководстве StopProc](./stopproc-tutorial.md) определяет `InputObject` параметр типа процесс, который поддерживает входные данные из конвейера. Пользователь может получить набор объектов процессов, управлять ими, чтобы выбрать точный список объектов для остановки и затем передать их в **Stop-Proc** командлет напрямую.

### <a name="support-the-force-parameter-ad02"></a>Поддерживает параметр Force (AD02)

В некоторых случаях командлет необходимо защитить пользователя от выполнения запрошенной операции. Должен поддерживать такой командлет `Force` параметр, чтобы разрешить пользователю переопределить эту защиту, если у пользователя есть разрешения для выполнения операции.

Например [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) обычно командлет не удаляет файл, доступный только для чтения. Тем не менее, этот командлет поддерживает `Force` параметра, поэтому пользователь может Принудительное удаление файла только для чтения. Если у пользователя уже есть разрешения на изменение атрибут только для чтения, и пользователь удаляет файл, использование `Force` параметр упрощает операции. Тем не менее, если пользователь не имеет разрешения на удаление файла, `Force` параметр не оказывает влияния.

### <a name="handle-credentials-through-windows-powershell-ad03"></a>Обработка учетных данных с помощью Windows PowerShell (AD03)

Командлет необходимо определить `Credential` параметр для представления учетных данных. Этот параметр должен иметь тип [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) и должны быть определены с помощью атрибута объявления учетных данных. Эта поддержка автоматически запрашивает пользователя для имени пользователя, пароля или обоих, при полной учетных данных не предоставляется напрямую. Дополнительные сведения об атрибуте учетных данных см. в разделе [объявление атрибута учетных данных](./credential-attribute-declaration.md).

### <a name="support-encoding-parameters-ad04"></a>Поддерживает параметры кодирования (AD04)

Если командлет считывает или записывает текст в или из двоичной форме, например запись или чтение данных из файла в файловую систему, командлет должен содержать параметр Encoding, который указывает, как текст кодируется в двоичной форме.

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a>Командлеты теста должен возвращать логическое значение (AD05)

Командлеты, выполните тесты в соответствии с ресурсами вы получите [System.Boolean](/dotnet/api/System.Boolean) введите в конвейер, чтобы их можно использовать в условных выражениях.

## <a name="code-guidelines"></a>Руководствам по кодам

Следующие рекомендации можно рассматривать при написании кода командлета. Когда вы найдете рекомендации для этого применяется в вашей ситуации, убедитесь, что рассмотрим рекомендации по проектированию аналогичные инструкции.

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a>Выполните командлет класс соглашения об именовании (AC01)

Следующие стандартные правила именования командлеты делает обнаружение, и вы помочь пользователю понять, точно что делают командлеты. Такой подход особенно важен для других разработчиков, с помощью Windows PowerShell, так как командлеты, открытые типы.

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a>Определение командлета в правильное пространство имен

Обычно определить класс для командлета в пространстве имен .NET Framework, который добавляет «. Команды» в пространстве имен, представляющий продукт, в котором выполняется командлет. Например, определенные командлеты, которые входят в состав Windows PowerShell в `Microsoft.PowerShell.Commands` пространства имен.

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a>Назовите класс командлета должно соответствовать имени командлета

При вводе имени класса .NET Framework, который реализует командлет, имя класса "*\<глагол >**\<существительное >**\<команда >*«, где вы замените  *\<Глагол >* и  *\<существительное >* заполнители глагол и существительное, используемый для имени командлета. Например [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет реализован классом с именем `GetProcessCommand`.

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a>Если отсутствуют входные данные конвейера переопределить метод BeginProcessing (AC02)

Если командлет не принимает входные данные из конвейера, обработки, следует реализовать [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод. Использование этого метода позволяет Windows PowerShell для сохранения порядка между командлетами. Первый командлет в конвейере всегда возвращает ее объектов прежде, чем остальные командлеты в конвейере будет возможность запустить их обработки.

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a>Чтобы обрабатывать запросы остановки Переопределите метод StopProcessing (AC03)

Переопределить [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) метод таким образом, чтобы командлет может обрабатывать сигнал остановки. Некоторые командлеты занять много времени для завершения их работы, и они позволяют передавать между вызовами в среду выполнения Windows PowerShell, например когда командлет блокирует поток в вызовы RPC долго выполняющейся длительное время. Сюда входят командлеты, которые упрощают вызовы [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод, чтобы [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод и другие отзывы механизмы, которые может занять много времени для завершения. В этих случаях пользователю может потребоваться отправить сигнал об остановке этих командлетов.

### <a name="implement-the-idisposable-interface-ac04"></a>Реализовать интерфейс IDisposable (AC04)

Если в командлете содержит объекты, не удаляются (написанного в конвейер) [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод, командлет может потребоваться удаление дополнительных объектов. Например, если командлет открывает дескриптор файла, в его [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод и сохраняет открыть дескриптор для использования [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод, этот дескриптор должен быть закрыт по завершении обработки.

Среда выполнения Windows PowerShell не всегда вызывает [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод. Например [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод не может быть вызван, если командлет отменяется середине операции, или если завершающей в любой части командлета возникает ошибка. Таким образом, класс .NET Framework для командлета, требующий очистки объектов следует реализовать полный [System.IDisposable](/dotnet/api/System.IDisposable) интерфейс шаблону, в том числе метод завершения, таким образом, чтобы среда выполнения Windows PowerShell можно вызвать оба [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) и [System.IDisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose) методы в конце обработки.

### <a name="use-serialization-friendly-parameter-types-ac05"></a>Типы параметров пригодным к сериализации (AC05)

Для поддержки выполнения командлета на удаленных компьютерах, используйте типы, которые можно легко сериализовать на клиентском компьютере и затем восстановлен на компьютере сервера. Следующие типы, пригодным к сериализации.

Типы-примитивы:

- Byte, SByte, Decimal, Single, Double, Int16, Int32, Int64, Uint16, UInt32 и UInt64.

- Значение типа Boolean, Guid, Byte [], TimeSpan, даты и времени, Uri и версии.

- Char, строка, XmlDocument.

Встроенные типы rehydratable:

- PSPrimitiveDictionary

- Переключатель

- PSListModifier

- PSCredential

- IP-адрес, MailAddress

- CultureInfo

- X509Certificate2, X500DistinguishedName

- RegistrySecurity DirectorySecurity FileSecurity,

Другие типы:

- SecureString

- Контейнеры (списки и словари указанного выше типа)

### <a name="use-securestring-for-sensitive-data-ac06"></a>Используйте SecureString для конфиденциальных данных (AC06)

При обработке конфиденциальных данных, всегда используйте [System.Security.Securestring](/dotnet/api/System.Security.SecureString) тип данных. Это может включать входные данные конвейера для параметров, а также возврат конфиденциальные данные в конвейер.

## <a name="see-also"></a>См. также

[Рекомендации по разработке требуется](./required-development-guidelines.md)

[Рекомендации по разработке настоятельно рекомендуется](./strongly-encouraged-development-guidelines.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

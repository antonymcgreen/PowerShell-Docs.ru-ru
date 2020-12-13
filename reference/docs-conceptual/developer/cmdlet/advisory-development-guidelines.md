---
ms.date: 09/13/2016
ms.topic: reference
title: Советы по разработке
description: Советы по разработке
ms.openlocfilehash: 1ac18925bbc2506e6a03810d24f58c2f3113fd55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668326"
---
# <a name="advisory-development-guidelines"></a>Советы по разработке

В этом разделе описываются рекомендации, которые следует учитывать для обеспечения хорошей разработки и взаимодействия с пользователем. Иногда они могут применяться, и иногда они могут не быть.

## <a name="design-guidelines"></a>Рекомендации по разработке

При проектировании командлетов следует учитывать следующие рекомендации. Если вы нашли рекомендации по проектированию, применимые к вашей ситуации, ознакомьтесь с рекомендациями по написанию кода для аналогичных руководств.

### <a name="support-an-inputobject-parameter-ad01"></a>Поддержка параметра InputObject (AD01)

Поскольку Windows PowerShell работает непосредственно с объектами Microsoft .NET Framework, часто бывает доступен объект .NET Framework, точно соответствующий типу, который пользователь должен выполнить для выполнения определенной операции. `InputObject` стандартное имя параметра, принимающего такой объект в качестве входных данных. Например, командлет «Sample **-proc** » в руководстве по [стоппрок](./stopproc-tutorial.md) определяет `InputObject` параметр типа Process, который поддерживает входные данные из конвейера. Пользователь может получить набор объектов процесса, управлять ими, чтобы выбрать точные объекты для их отмены, а затем передать их непосредственно командлету Process **-proc** .

### <a name="support-the-force-parameter-ad02"></a>Поддержка параметра Force (AD02)

Иногда командлету необходимо защитить пользователя от выполнения запрошенной операции. Такой командлет должен поддерживать `Force` параметр, позволяющий пользователю переопределить эту защиту, если у пользователя есть разрешения на выполнение этой операции.

Например, командлет [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) обычно не удаляет файл, который доступен только для чтения. Однако этот командлет поддерживает `Force` параметр, чтобы пользователь мог принудительно удалить файл, предназначенный только для чтения. Если пользователь уже имеет разрешение на изменение атрибута только для чтения и пользователь удаляет файл, использование `Force` параметра упрощает операцию. Однако если пользователь не имеет разрешения на удаление файла, `Force` параметр не действует.

### <a name="handle-credentials-through-windows-powershell-ad03"></a>Работа с учетными данными с помощью Windows PowerShell (AD03)

Командлет должен определить `Credential` параметр для представления учетных данных. Этот параметр должен иметь тип [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) и должен быть определен с помощью объявления атрибута Credential. Эта поддержка автоматически запрашивает у пользователя имя пользователя, пароль или значение, если полные учетные данные не указаны напрямую. Дополнительные сведения об атрибуте Credential см. в разделе [объявление атрибута учетных данных](./credential-attribute-declaration.md).

### <a name="support-encoding-parameters-ad04"></a>Поддержка параметров кодировки (AD04)

Если командлет считывает или записывает текст в двоичную форму или из нее, например запись в файл или чтение из файла в файловой системе, то у командлета должен быть параметр кодирования, указывающий способ кодирования текста в двоичной форме.

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a>Командлеты тестирования должны возвращать логическое значение (AD05)

Командлеты, выполняющие тесты для своих ресурсов, должны возвращать тип [System. Boolean](/dotnet/api/System.Boolean) конвейеру, чтобы их можно было использовать в условных выражениях.

## <a name="code-guidelines"></a>Рекомендации по коду

При написании кода командлета следует учитывать следующие рекомендации. При обнаружении рекомендации, относящейся к вашей ситуации, обязательно ознакомьтесь с рекомендациями по проектированию для аналогичных руководств.

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a>Следование соглашениям об именовании классов командлетов (AC01)

Следуя стандартным соглашениям об именовании, можно сделать командлеты более обнаруживаемыми и помочь пользователю точно понять, что делают командлеты. Эта практика особенно важна для других разработчиков, использующих Windows PowerShell, так как командлеты являются общедоступными типами.

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a>Определите командлет в правильном пространстве имен.

Класс для командлета обычно определяется в .NET Framework пространстве имен, которое добавляет ". Commands в пространство имен, представляющее продукт, в котором выполняется командлет. Например, командлеты, которые входят в состав Windows PowerShell, определяются в `Microsoft.PowerShell.Commands` пространстве имен.

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a>Присвойте классу командлета имя, совпадающее с именем командлета.

При именовании класса .NET Framework, реализующего командлет, назовите класс " *\<Verb>**\<Noun>**\<Command>* ", где заменяются *\<Verb>* *\<Noun>* заполнители и с помощью глагола и существительного, используемого для имени командлета. Например, командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) реализуется классом с именем `GetProcessCommand` .

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a>Если входные данные конвейера не переопределяют метод BeginProcessing (AC02)

Если командлет не принимает входные данные из конвейера, обработка должна быть реализована в методе [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) . Использование этого метода позволяет Windows PowerShell поддерживать порядок между командлетами. Первый командлет в конвейере всегда возвращает свои объекты, прежде чем остальные командлеты в конвейере получат возможность начать обработку.

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a>Для обработки запросов на прерывание переопределяет метод StopProcessing (AC03)

Переопределите метод [System. Management. Automation. командлет. StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing) , чтобы командлет мог справиться с сигналом об ошибке. Некоторые командлеты занимают много времени для выполнения операции, и они позволяют длительное время между вызовами среды выполнения Windows PowerShell, например, когда командлет блокирует поток в долгосрочных вызовах RPC. К ним относятся командлеты, которые выполняют вызовы метода [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) в метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) и другие механизмы обратной связи, выполнение которых может занять много времени. В таких случаях пользователю может потребоваться отправить сигнал об ошибке в эти командлеты.

### <a name="implement-the-idisposable-interface-ac04"></a>Реализация интерфейса IDisposable (AC04)

Если командлет содержит объекты, которые не были удалены (записаны в конвейер) методом [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , для вашего командлета может потребоваться дополнительная реализация объекта. Например, если командлет открывает в методе [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) маркер файла и сохраняет открытый для использования методом [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , этот маркер должен быть закрыт в конце обработки.

Среда выполнения Windows PowerShell не всегда вызывает метод  [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Например, метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) может не вызываться при отмене самого посредине командлета или при возникновении завершающей ошибки в любой части командлета. Таким образом, класс .NET Framework для командлета, требующего очистки объектов, должен реализовать полный шаблон интерфейса  [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения Windows PowerShell могла вызывать методы [System. Management. Automation. командлета. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) и [System. IDisposable. Dispose *](/dotnet/api/System.IDisposable.Dispose) в конце обработки.

### <a name="use-serialization-friendly-parameter-types-ac05"></a>Использование типов параметров, удобных для сериализации (AC05)

Для поддержки выполнения командлета на удаленных компьютерах используйте типы, которые могут быть легко сериализованы на клиентском компьютере, а затем восстановлены на компьютере сервера. Следующие типы являются понятными для сериализации.

Типы-примитивы:

- Byte, SByte, Decimal, Single, Double, Int16, Int32, Int64, UInt16, UInt32 и UInt64.

- Boolean, GUID, Byte [], TimeSpan, DateTime, URI и версия.

- Char, String, XmlDocument.

Встроенные типы с восстановлением:

- пспримитиведиктионари

- Параметр-переключатель

- пслистмодифиер

- PSCredential

- IPAddress, MailAddress

- CultureInfo

- X509Certificate2, X500DistinguishedName

- Директорисекурити, FileSecurity, Регистрисекурити

Другие типы:

- SecureString

- Контейнеры (списки и словари указанного выше типа)

### <a name="use-securestring-for-sensitive-data-ac06"></a>Использование SecureString для конфиденциальных данных (AC06)

При обработке конфиденциальных данных всегда используется тип данных [System. Security. SecureString](/dotnet/api/System.Security.SecureString) . Это может включать входные данные конвейера в параметры, а также возвращение конфиденциальных данных в конвейер.

## <a name="see-also"></a>См. также:

[Обязательные требования к разработке](./required-development-guidelines.md)

[Настоятельные рекомендации по разработке](./strongly-encouraged-development-guidelines.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

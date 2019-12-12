---
title: Установка пакета SDK для Windows PowerShell
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: e7ca38377b3e6533eec1a70027f6de1a9fb3091b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "73444507"
---
# <a name="installing-the-windows-powershell-sdk"></a>Установка пакета SDK для Windows PowerShell

Область применения: Windows PowerShell 2,0, Windows PowerShell 3,0

В следующей статье описывается, как установить пакет PowerShell SDK на разные версии Windows.

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a>Установка пакета SDK для Windows PowerShell 3.0 в Windows 8 и Windows Server 2012

Windows PowerShell 3.0 устанавливается автоматически вместе с Windows 8 и Windows Server 2012. Вы также можете скачать и установить ссылочные сборки для Windows PowerShell 3.0 в составе Windows 8 SDK. Эти сборки позволяют написать командлеты, поставщики и ведущие программы для Windows PowerShell 3.0. При установке Windows SDK для Windows 8 сборки Windows PowerShell автоматически устанавливаются в папку базовой сборки, в `\Program Files
(x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`. Дополнительные сведения см. на сайте загрузки пакета SDK для Windows 8. Примеры кода Windows PowerShell также доступны в центре разработки в [примере пакета SDK для Windows powershell 3,0](https://code.msdn.microsoft.com/Windows-PowerShell-30-SDK-9a34641d).

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a>Установка пакета SDK для Windows PowerShell 3.0 в Windows 7 и Windows Server 2008 R2

Вместе с Windows 7 и Windows Server 2008 R2 автоматически устанавливается PowerShell 2.0. Вы также можете установить PowerShell 3.0 в этих системах. Вы также можете установить пакет SDK для Windows 8 в Windows 7 и Windows Server 2008 R2, как описано выше.

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a>Установка пакета SDK для Windows PowerShell 2.0 в Windows 7, Windows Vista, Windows XP, Windows Server 2003 и Windows Server 2008

Установка пакета SDK для Windows PowerShell 2.0 предоставляет эталонные сборки, необходимые для написания командлетов, поставщиков и ведущих приложений, а также пример кода C#, который можно использовать в качестве начальной точки при написании кода. Примеры кода можно загрузить из [https://www.microsoft.com/download/details.aspx?id=2560](https://www.microsoft.com/download/details.aspx?id=2560).

### <a name="reference-assemblies"></a>Эталонные сборки

Эталонные сборки по умолчанию устанавливаются в следующий каталог: `c:\Program Files\Reference
Assemblies\Microsoft\WindowsPowerShell\V1.0`.

> [!NOTE]
>
> Код, который компилируется с использованием сборок Windows PowerShell 2.0, нельзя загрузить в установках Windows PowerShell 1.0. Но код, который компилируется в сборках Windows PowerShell 1.0, можно загрузить в установках Windows PowerShell 2.0.


### <a name="samples"></a>примеры

Примеры кода по умолчанию устанавливаются в следующий каталог: `C:\Program Files\Microsoft
SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`. В следующих разделах приводится краткое описание каждого примера.

#### <a name="cmdlet-samples"></a>Примеры командлетов

- GetProcessSample01 — показывает, как написать простой командлет, который получает все процессы на локальном компьютере.
- GetProcessSample02 — показывает, как добавить параметры в командлет. Командлет принимает одно или несколько имен процессов и возвращает соответствующие процессы.
- GetProcessSample03 — показывает, как добавить параметры, которые принимают входные данные из конвейера.
- GetProcessSample04 — показывает, как справляться с устранимыми ошибками.
- GetProcessSample05 — показывает, как отобразить список указанных процессов.
- SelectObject — показывает, как написать фильтр для выбора только определенных объектов.
- Селектстринг — показывает, как искать файлы по указанным шаблонам.
- StopProcessSample01 — показывает, как реализовать параметр PassThru и как запросить отзывы пользователей с помощью вызовов методов ShouldProcess и ShouldContinue. Пользователи указывают параметр PassThru, если требуется принудительно вернуть объект в командлет.
- StopProcessSample02 — показывает, как можно прерывать конкретный процесс.
- StopProcessSample03 — показывает, как объявлять псевдонимы для параметров и как поддерживать подстановочные знаки.
- StopProcessSample04 — показывает, как объявлять наборы параметров, объект, который командлет принимает в качестве входных данных, и как указать используемый по умолчанию набор параметров.

#### <a name="remoting-samples"></a>Примеры удаленного взаимодействия

- RemoteRunspace01 — показывает, как создать удаленное пространство выполнения, которое используется для установления удаленного подключения.
- RemoteRunspacePool01 — показывает, как создать пул удаленных пространств выполнения и как одновременно выполнять несколько команд с помощью этого пула.
- Serialization01 — показывает, как просмотреть существующий класс .NET и убедиться, что сведения из выбранных общедоступных свойств этого класса сохраняются в процессе сериализации и десериализации.
- Serialization02 — показывает, как просмотреть существующий класс .NET и убедиться, что информация из экземпляра этого класса сохраняется в процессе сериализации или десериализации, когда информация недоступна в открытых свойствах класса.
- Serialization03 — показывает, как просмотреть существующий класс .NET и убедиться, что экземпляры этого класса и производных классов десериализованы (восстановлены) в динамические объекты .NET.

#### <a name="event-samples"></a>Примеры событий

- Event01 — показывает, как создать командлет для регистрации событий, производный от ObjectEventRegistrationBase.
- Event02 — показывает, как получать уведомления о событиях Windows PowerShell, созданных на удаленных компьютерах. Он использует событие PSEventReceived, доступное через класс пространства выполнения.

#### <a name="hosting-application-samples"></a>Примеры размещения приложений

- Runspace01 — показывает, как использовать класс PowerShell для синхронного выполнения командлета `Get-Process`.
Командлет `Get-Process` возвращает объекты обработки для каждого процесса, выполняемого на локальном компьютере.
- Runspace02 — показывает, как использовать класс PowerShell для синхронного запуска командлетов `Get-Process` и `Sort-Object`. Командлет `Get-Process` возвращает объекты обработки для каждого процесса, выполняемого на локальном компьютере, а `Sort-Object` сортирует объекты по их свойству ID. Результаты этих команд отображаются с помощью элемента управления DataGridView.
- Runspace03 — показывает, как использовать класс PowerShell для синхронного выполнения скрипта и как обрабатываются устранимые ошибки. Скрипт получает список имен процессов, а затем извлекает эти процессы. Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.
- Runspace04 — показывает, как использовать класс PowerShell для выполнения команд и как перехватывать ошибки, возникающие при выполнении команд. Выполняются две команды, и последняя получает недопустимый аргумент параметра. В результате объекты не возвращаются и создается неустранимая ошибка.
- Runspace05 — показывает, как добавить оснастку в объект InitialSessionState, чтобы командлет оснастки был доступен при открытии пространства выполнения. Оснастка предоставляет командлет Get-proc (определяемый образцом GetProcessSample01), который выполняется синхронно с помощью объекта PowerShell.
- Runspace06 — показывает, как добавить модуль в объект InitialSessionState, чтобы модуль загружался при открытии пространства выполнения. Модуль предоставляет командлет Get-proc (определяемый образцом GetProcessSample02), который выполняется синхронно с помощью объекта PowerShell.
- Runspace07 — показывает, как создать пространство выполнения, а затем использовать это пространство выполнения для синхронного выполнения двух командлетов с помощью объекта PowerShell.
- Runspace08 — показывает, как добавить команды и аргументы в конвейер объекта PowerShell и как выполнять команды синхронно.
- Runspace09 — показывает, как добавить скрипт в конвейер объекта PowerShell и как выполнить скрипт асинхронно. События используются для обработки выходных данных скрипта.
- Runspace10 — показывает, как создать начальное состояние сеанса по умолчанию, как добавить командлет в InitialSessionState, как создать пространство выполнения, использующее исходное состояние сеанса, и как выполнить команду с помощью объекта PowerShell.
- Runspace11 — показывает, как использовать класс Проксикомманд для создания команды-посредника, которая вызывает существующий командлет, но ограничит набор доступных параметров. Прокси-команда затем добавляется в начальное состояние сеанса, который используется для создания ограниченного пространства выполнения. Это означает, что пользователь может получить доступ к функциям командлета только с помощью прокси-команды.
- PowerShell01 — показывает, как создать ограниченное пространство выполнения с помощью объекта InitialSessionState.
- PowerShell02 — показывает, как использовать пул пространства выполнения для одновременного выполнения нескольких команд.

#### <a name="host-samples"></a>Примеры узлов

- Host01 — показывает, как реализовать ведущее приложение, использующее пользовательский узел. В этом примере создается пространство выполнения, которое использует пользовательский узел, а затем API PowerShell используется для выполнения сценария, вызывающего "Exit". Затем ведущее приложение анализирует выходные данные скрипта и выводит на экран результаты.
- Host02 — показывает, как написать ведущее приложение, которое использует среду выполнения Windows PowerShell вместе с реализацией пользовательского узла. Ведущее приложение устанавливает немецкий язык и региональные параметры, запускает командлет `Get-Process` и отображает результаты, как это можно увидеть с помощью пврш. exe, а затем выводит текущие данные и время на немецком языке.
- Host03 — показывает, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль.
- Host04 — показывает, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль. Это приложение также поддерживает отображение запросов, позволяющих пользователю выбрать несколько вариантов.
- Host05 — показывает, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль. Это ведущее приложение также поддерживает вызовы удаленных компьютеров с помощью командлетов `Enter-PsSession` и `Exit-PsSession`.
- Host06 — показывает, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль. Кроме того, в этом примере используются интерфейсы API создателя токенов для указания цвета текста, вводимого пользователем.

#### <a name="provider-samples"></a>Примеры поставщиков

- AccessDBProviderSample01 — показывает, как объявить класс поставщика, производный непосредственно от класса Кмдлетпровидер. Он приводится здесь только для полноты картины.

- AccessDBProviderSample02 — показывает, как перезаписать методы Невдриве и Ремоведриве для поддержки вызовов командлетов `New-PSDrive` и `Remove-PSDrive`. Класс поставщика в этом примере является производным от класса Дривекмдлетпровидер.

- AccessDBProviderSample03 — показывает, как перезаписать методы DataItem и Сетитем для поддержки вызовов командлетов `Get-Item` и `Set-Item`. Класс поставщика в этом примере является производным от класса Итемкмдлетпровидер.

- AccessDBProviderSample04 — показывает, как перезаписать методы контейнера для поддержки вызовов командлетов `Copy-Item`, `Get-ChildItem`, `New-Item`и `Remove-Item`. Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами. Контейнер — это группа дочерних элементов в составе общего родительского элемента. Класс поставщика в этом примере является производным от класса Итемкмдлетпровидер.

- AccessDBProviderSample05 — показывает, как перезаписать методы контейнера для поддержки вызовов командлетов `Move-Item` и `Join-Path`. Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры. Класс поставщика в этом примере является производным от класса NavigationCmdletProvider.

- AccessDBProviderSample06 — показывает, как перезаписывать методы содержимого для поддержки вызовов командлетов `Clear-Content`, `Get-Content`и `Set-Content`. Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных. Класс поставщика в этом примере является производным от класса NavigationCmdletProvider и реализует интерфейс Иконтенткмдлетпровидер.
---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Новые и обновленные командлеты
ms.openlocfilehash: ffd5db2d4fc9bf8f67ef5e352633ad3209f72c87
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147594"
---
# <a name="new-and-updated-cmdlets"></a>Новые и обновленные командлеты

В ответ на отзывы участников сообщества мы добавили новые и обновили имеющиеся командлеты.

## <a name="archive-cmdlets"></a>Командлеты Archive

Два новых командлета, `Compress-Archive` и `Expand-Archive`, позволяют сжимать и распаковывать ZIP-файлы.

Дополнительные сведения см. в разделе документации по модулю [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/).

## <a name="catalog-cmdlets"></a>Командлеты для работы с каталогами

В модуле Microsoft.PowerShell.Security добавлены два новых командлета.

- [New-FileCatalog](/powershell/module/microsoft.powershell.security/New-FileCatalog)
- [Test-FileCatalog](/powershell/module/microsoft.powershell.security/Test-FileCatalog)

Они создают и проверяют файлы каталога Windows.

## <a name="clipboard-cmdlets"></a>Командлеты Clipboard

Командлеты `Get-Clipboard` и `Set-Clipboard` упрощают передачу содержимого в сеанс Windows PowerShell и из него. Командлеты Clipboard поддерживают изображения, звуковые файлы, списки файлов и текст.

Дополнительная информация:

- [Get-Clipboard](/powershell/module/Microsoft.PowerShell.Management/Get-Clipboard)
- [Set-Clipboard](/powershell/module/Microsoft.PowerShell.Management/Set-Clipboard)

## <a name="cryptographic-message-syntax-cms-cmdlets"></a>Командлеты Cryptographic Message Syntax (CMS)

Командлеты Cryptographic Message Syntax поддерживают шифрование и расшифровку содержимого с помощью стандартного формата IETF для криптографической защиты сообщений, задокументированного в [RFC5652](https://tools.ietf.org/html/rfc5652.html).

Стандарт шифрования CMS реализует шифрование с открытым ключом, при котором ключи, используемые для шифрования содержимого (*открытый ключ*) и для его расшифровки (*закрытый ключ*), существуют отдельно.

Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям. Любое содержимое, зашифрованное с помощью открытого ключа, можно расшифровать только с помощью закрытого ключа. Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).

Дополнительная информация:

- [Get-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Get-CmsMessage)
- [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)
- [Unprotect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/unprotect-CmsMessage)

Для определения в качестве сертификатов шифрования данных в PowerShell сертификатам требуется уникальный идентификатор использования ключа (EKU), например "Подписывание кода" или "Зашифрованная почта". Чтобы просмотреть сертификаты шифрования документов в поставщике сертификатов, можно использовать динамический параметр **DocumentEncryptionCert** метода `Get-ChildItem`:

```powershell
Get-ChildItem Cert:\CurrentUser -DocumentEncryptionCert -Recurse
```

## <a name="extract-and-parse-structured-objects-from-string-content"></a>Извлечение и анализ структурированных объектов вне строки

### <a name="convertfrom-string"></a>ConvertFrom-String

Новый командлет `ConvertFrom-String` поддерживает два режима:

- базовый анализ с разделением;
- анализ с управлением автоматически создаваемым примером.

Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.

Параметр **UpdateTemplate** для сохранения результатов алгоритма обучения в комментарий внутри файла шаблона. Это делает затраты на процесс обучения (являющийся самым медленным этапом) единовременными. Выполнение `ConvertFrom-String` с шаблоном, содержащим закодированный обучающий алгоритм, теперь осуществляется практически мгновенно.

Дополнительные сведения см. в статье [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).

### <a name="convert-string"></a>Convert-String

`Convert-String` позволяет указать примеры того, как должен выглядеть текст в исходном и итоговом виде. Командлет автоматически форматирует текст.

Дополнительные сведения см. в статье [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).

## <a name="updates-to-fileinfo-object"></a>Изменения объекта FileInfo

Сведения о версии файла могут вводить пользователя в заблуждение, особенно в случаях, когда файл был исправлен. В выпуске WMF 5.0 добавлены новые свойства **FileVersionRaw** и **ProductVersionRaw** сценария для объектов **FileInfo**.
Ниже приведены свойства, отображаемые для powershell.exe (при условии, что $pid является идентификатором процесса PowerShell).

```powershell
Get-Process -Id $pid -FileVersionInfo | Format-List *version*
```

```Output
FileVersionRaw    : 10.0.17763.1
ProductVersionRaw : 10.0.17763.1
FileVersion       : 10.0.17763.1 (WinBuild.160101.0800)
ProductVersion    : 10.0.17763.1
```

## <a name="format-hex"></a>Format-Hex

`Format-Hex` позволяет просматривать текст или двоичные данные в шестнадцатеричном формате.

Дополнительные сведения см. в статье [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).

## <a name="get-childitem-has--depth-parameter"></a>Get-ChildItem получает параметр -Depth

Теперь `Get-ChildItem` имеет параметр **Depth**, используемый вместе с **Recurse** для ограничения рекурсии:

## <a name="modules-support-for-declaring-version-ranges-1-etc"></a>Поддержка модулей для объявления диапазонов версий (1.* и т. д.)

Теперь вы можете сочетать **MinimumVersion** и **MaximumVersion**, чтобы импортировать модуль из определенного диапазона. Параметры также поддерживают подстановочные знаки.

```powershell
Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*
```

```Output
VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```

## <a name="new-guid"></a>New-Guid

Во многих сценариях требуется уникальный идентификатор. Командлет `New-GUID` предоставляет простой способ создания идентификатора GUID.

```powershell
New-Guid
```

```Output
Guid
----
e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
```

## <a name="nonewline-parameter"></a>Параметр NoNewLine

Теперь для `Out-File`, `Add-Content` и `Set-Content` есть новый параметр **NoNewline**, который пропускает новую строку после выходных данных. Например:

```powershell
"This is " | Out-File -FilePath Example.txt -NoNewline
"a single " | Add-Content -Path Example.txt -NoNewline
"sentence." | Add-Content -Path Example.txt -NoNewline
Get-Content .\Example.txt
```

```Output
This is a single sentence.
```

Без параметра **NoNewline** каждый фрагмент будет находиться на отдельной строке:

```powershell
"This is " | Out-File -FilePath Example.txt
"a single " | Add-Content -Path Example.txt
"sentence." | Add-Content -Path Example.txt
Get-Content .\Example.txt
```

```Output
This is
a single
sentence.
```

## <a name="interact-with-symbolic-links-using-improved-item-cmdlets"></a>Взаимодействие с символьными ссылками с помощью улучшенных командлетов Item

Для поддержки символьных ссылок расширена функциональность командлета Item и нескольких связанных с ним командлетов.

### <a name="symbolic-link-files"></a>Файлы с символьными ссылками

В этом примере мы создадим файл символьной ссылки MySymLinkFile.txt в C:\Temp со ссылкой на файл $pshome\profile.ps1. Все три примера дают одинаковый результат.

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="symbolic-link-directories"></a>Каталоги с символьными ссылками

В этом примере мы создадим каталог символьной ссылки MySymLinkDir в папке C:\Temp, который позволяет перейти к папке $pshome. Все три примера дают одинаковый результат.

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkDir -Value $pshome
```

### <a name="hard-links"></a>жесткие ссылки;

Одинаковые комбинации **пути** и **имени** разрешены, как описано выше.

```powershell
New-Item -ItemType HardLink -Path C:\Temp -Name MyHardLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="directory-junctions"></a>Соединения каталогов

Одинаковые комбинации **пути** и **имени** разрешены, как описано выше.

```powershell
New-Item -ItemType Junction -Path C:\Temp\MyJunctionDir -Value $pshome
```

### <a name="get-childitem"></a>Get-ChildItem

`Get-ChildItem` теперь отображает "l" в свойстве **Mode**, указывающем на файл или каталог символьной ссылки.

```powershell
Get-ChildItem C:\Temp | sort LastWriteTime -Descending

Directory: C:\Temp

Mode       LastWriteTime Length Name
----       ------------- ------ ----
-a---- 6/13/2014 3:00 PM     16 File.txt
d----- 6/13/2014 3:00 PM        Directory
-a---l 6/13/2014 3:21 PM      0 MySymLinkFile.txt
d----l 6/13/2014 3:22 PM        MySymLinkDir
-a---l 6/13/2014 3:23 PM  23304 MyHardLinkFile.txt
d----l 6/13/2014 3:24 PM        MyJunctionDir
```

### <a name="remove-item"></a>Remove-Item

Удаление символьной ссылки подобно удалению любого другого типа элемента.

```powershell
Remove-Item C:\Temp\MySymLinkFile.txt
Remove-Item C:\Temp\MySymLinkDir
```

Используйте параметр **Force**, чтобы удалить файлы в целевом каталоге и символьную ссылку.

```powershell
Remove-Item C:\Temp\MySymLinkDir -Force
```

## <a name="new-temporaryfile"></a>New-TemporaryFile

Иногда в сценариях необходимо создать временный файл. Теперь это можно сделать с помощью командлета `New-TemporaryFile`:

```powershell
$tempFile = New-TemporaryFile
$tempFile.FullName
```

```Output
C:\Users\user1\AppData\Local\Temp\tmp375.tmp
```

## <a name="network-switch-management-with-powershell"></a>Управление сетевыми коммутаторами с помощью PowerShell

Командлеты сетевых коммутаторов, представленные в WMF 5.0, позволяют применять конфигурацию коммутатора, виртуальной локальной сети и портов базового сетевого коммутатора уровня 2 к сетевым коммутаторам, прошедшим сертификацию для Windows Server 2012 R2. Эти командлеты позволяют осуществлять следующее.

- Глобальная конфигурация коммутаторов, например следующее.
  - Задание имени узла
  - Задание баннера параметров
  - Сохранение конфигурации
  - Включение и отключение функции

- Конфигурация виртуальной локальной сети:
  - Создание или удаление виртуальной ЛС
  - Включение или отключение виртуальной ЛС
  - Перечисление виртуальной ЛС
  - Указание понятного имени для виртуальной ЛС

- Конфигурация портов уровня 2:
  - Перечисление портов
  - Включение или отключение портов
  - Задание свойств и режимов портов
  - Добавление или сопоставление виртуальной ЛС с режимом магистрали или доступа для порта

Дополнительные сведения см. в статье документации [NetworkSwitchManager](/powershell/module/networkswitchmanager/).

## <a name="generate-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a>Создание командлетов PowerShell на основе конечной точки OData с помощью ODataUtils

Модуль ODataUtils позволяет создавать командлеты PowerShell на базе конечных точек REST, которые поддерживают OData. Модуль Microsoft.PowerShell.ODataUtils включает следующие компоненты:

- Передача дополнительных сведений с серверной конечной точки на сторону клиента
- Поддержки разбивки на страницы на стороне клиента
- Фильтрация на стороне сервера с помощью параметра Select
- Поддержка заголовков веб-запросов

Командлеты прокси-сервера, созданные командлетом `Export-ODataEndPointProxy`, предоставляют дополнительные сведения из конечной точки OData на стороне сервера в потоке **Information**.

```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
```

В следующем примере мы получаем данные о самом популярном продукте и записываем выходные данные в переменную `$infoStream`.

Указав параметр **IncludeTotalResponseCount**, мы получаем общее число всех записей **Product**, доступных на сервере.

```powershell
Import-Module $generatedProxyModuleDir -Force
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
$additionalInfo['odata.count']
```

Записи с сервера можно получить в пакетах, используя поддержку разбивки на страницы на стороне клиента. Это удобно, когда требуется получить большой объем данных с сервера по сети.

```powershell
$skipCount = 0
$batchSize = 3
while($skipCount -le $additionalInfo['odata.count'])
{
  Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
  $skipCount += $batchSize
}
```

Созданные командлеты прокси-сервера поддерживают параметр **Select**, используемый в качестве фильтра, чтобы получить только свойства записей, необходимые клиенту. Это уменьшает объем передаваемых по сети данных, так как фильтрация выполняется на стороне сервера.

```powershell
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

Командлет `Export-ODataEndpointProxy` и созданные на его основе командлеты прокси-сервера теперь поддерживают параметр **Headers**. Заголовок может использоваться для передачи дополнительных сведений, ожидаемых конечной точкой OData.

В следующем примере в параметр **Headers** передается хэш-таблица, содержащая ключ подписки. Это типичный пример для служб, которые ожидают ключ подписки для проверки подлинности.

```powershell
Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```

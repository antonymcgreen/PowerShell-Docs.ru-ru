---
title: Основные сведения о модуле Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4e38235-9987-4347-afd2-0f7d1dc8f64a
caps.latest.revision: 19
ms.openlocfilehash: b42ba6b2bf42a74213eb78f2db22e16de7e90583
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360643"
---
# <a name="understanding-a-windows-powershell-module"></a>Общие сведения о модулях Windows PowerShell

*Модуль* — это набор связанных функциональных возможностей Windows PowerShell, сгруппированных в качестве удобного блока (обычно сохраненный в одном каталоге). Определяя набор связанных файлов скриптов, сборок и связанных ресурсов в качестве модуля, вы можете ссылаться, загружать, сохранять и совместно использовать код гораздо проще, чем в противном случае.

Основным назначением модуля является разрешение модульной (IE, повторного использования и абстракции) кода Windows PowerShell. Например, самый простой способ создать модуль — просто сохранить сценарий Windows PowerShell как PSM1-файл. Это позволяет управлять (IE, сделать общедоступными или частными) функции и переменные, содержащиеся в скрипте. Сохранение скрипта в виде файла. PSM1 также позволяет управлять областью определенных переменных. Наконец, можно также использовать командлеты [Install-Module](/powershell/module/PowershellGet/Install-Module) для Организации, установки и использования скриптов в качестве стандартных блоков для более крупных решений.

## <a name="module-components-and-types"></a>Компоненты и типы модулей

Модуль состоит из четырех основных компонентов:

1. Какой-либо файл кода — обычно сценарий PowerShell или управляемая сборка командлета.

2. Все остальное, что может потребоваться для файла кода, например дополнительные сборки, файлы справки или сценарии.

3. Файл манифеста, описывающий указанные выше файлы, а также хранит метаданные, такие как сведения об авторе и управлении версиями.

4. Каталог, содержащий все приведенное выше содержимое и расположенный там, где PowerShell может его найти.

   Обратите внимание, что ни один из этих компонентов, по сути, не требуется. Например, модуль может быть только сценарием, хранящимся в PSM1-файле. Также можно иметь модуль, который не является ни файлом манифеста, который используется главным образом для организационных целей. Можно также написать сценарий, который динамически создает модуль, и, таким образом, не требуется каталог для хранения каких-либо данных в. В следующих разделах описываются типы модулей, которые можно получить путем смешивания и сопоставления различных возможных частей модуля.

### <a name="script-modules"></a>Модули скриптов

Как следует из названия, *модуль скрипта* — это файл (. PSM1), который содержит любой допустимый код Windows PowerShell. Разработчики и администраторы скриптов могут использовать этот тип модуля для создания модулей, члены которых включают функции, переменные и многое другое. В сердце модуль скрипта — это просто сценарий Windows PowerShell с другим расширением, который позволяет администраторам использовать на нем функции импорта, экспорта и управления.

Кроме того, файл манифеста можно использовать для включения в модуль других ресурсов, таких как файлы данных, другие зависимые модули или скрипты среды выполнения. Файлы манифеста также полезны для отслеживания метаданных, таких как сведения о создании и управлении версиями.

Наконец, модуль скрипта, как и любой другой модуль, который не создается динамически, необходимо сохранить в папке, которую PowerShell может найти. Обычно это происходит в пути модуля PowerShell. но при необходимости можно явно описать, где установлен модуль. Дополнительные сведения см. [в разделе как написать модуль скрипта PowerShell](./how-to-write-a-powershell-script-module.md).

### <a name="binary-modules"></a>Двоичные модули

*Двоичный модуль* — это .NET Frameworkая сборка (. dll), которая содержит скомпилированный код C#, например. Разработчики командлетов могут использовать этот тип модуля для совместного использования командлетов, поставщиков и многого другого. (Существующие оснастки также могут использоваться в качестве двоичных модулей.) По сравнению с модулем скрипта двоичный модуль позволяет создавать более быстрые командлеты или использовать функции (например, многопоточность), которые не так просты в написании сценариев Windows PowerShell.

Как и в случае с модулями скриптов, можно включить файл манифеста для описания дополнительных ресурсов, используемых модулем, а также для отслеживания метаданных модуля. Аналогичным образом, вы, вероятно, должны установить двоичный модуль в папку где-то в пути модуля PowerShell. Дополнительные сведения см. в разделе как [написать двоичный модуль PowerShell](./how-to-write-a-powershell-binary-module.md).

### <a name="manifest-modules"></a>Модули манифеста

*Модуль манифеста* — это модуль, который использует файл манифеста для описания всех его компонентов, но не имеет какой-либо основной сборки или скрипта. (Формально модуль манифеста оставляет `ModuleToProcess` или `RootModule` пустой элемент манифеста.) Тем не менее можно по-прежнему использовать другие функции модуля, такие как возможность загружать зависимые сборки или автоматически запускать определенные предварительно обрабатываемые скрипты. Кроме того, модуль манифеста можно использовать как удобный способ упаковки ресурсов, которые будут использоваться другими модулями, например вложенные модули, сборки, типы или форматы. Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).

### <a name="dynamic-modules"></a>Динамические модули

*Динамический модуль* — это модуль, который не загружается из файла или не сохраняется в файле. Вместо этого они создаются динамически скриптом с помощью командлета [New-Module](/powershell/module/Microsoft.PowerShell.Core/New-Module) . Этот тип модуля позволяет скрипту создавать модуль по запросу, который не требуется загружать или сохранять в постоянное хранилище. По своей природе динамический модуль предназначен для кратковременного существования, поэтому к нему нельзя получить доступ с помощью командлета `Get-Module`. Аналогично, они обычно не требуют манифестов модулей и не требуют постоянных папок для хранения связанных сборок.

## <a name="module-manifests"></a>Манифесты модулей

*Манифест модуля* — это файл PSD1, содержащий хэш-таблицу. Ключи и значения в хэш-таблице выполняют следующие действия.

- Опишите содержимое и атрибуты модуля.

- Определите необходимые компоненты.

- Определите, как обрабатываются компоненты.

  Манифесты не являются необходимыми элементами модулей. Модули могут ссылаться на файлы скриптов (PS1), файлы модулей скриптов (PSM1), файлы манифеста (. PSD1), файлы форматирования и типы (. ps1xml), сборки командлетов и поставщиков (. dll), файлы ресурсов, файлы справки, файлы локализации, а также любые другие типы файлов или ресурсов, которые объединяется в состав модуля. Для международного сценария в папке Module также содержится набор файлов каталога сообщений. При добавлении файла манифеста в папку Module можно сослаться на несколько файлов как единое целое, обратившись к манифесту.

  Сам манифест описывает следующие категории данных:

- Метаданные о модуле, такие как номер версии модуля, автор и описание.

- Необходимые компоненты для импорта модуля, такие как версия Windows PowerShell, версия среды CLR и необходимые модули.

- Обработка директив, таких как скрипты, форматы и типы для обработки.

- Ограничения для элементов экспортируемого модуля, например псевдонимы, функции, переменные и командлеты для экспорта.

  Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).

## <a name="storing-and-installing-a-module"></a>Хранение и установка модуля

После создания скрипта, двоичного файла или модуля манифеста можно сохранить работу в расположении, к которому другие пользователи могут получить доступ. Например, модуль можно хранить в системной папке, в которой установлен Windows PowerShell, или храниться в папке пользователя.

В целом, вы можете определить, где следует установить модуль, используя один из путей, сохраненных в переменной `$ENV:PSModulePath`. Использование одного из этих путей означает, что PowerShell может автоматически находить и загружать модуль, когда пользователь вызывает его в своем коде. Если вы храните модуль в другом месте, можно явно разрешить PowerShell узнавать, передав расположение модуля в качестве параметра при вызове `Install-Module`.

Независимо от этого путь к папке называется *основой* модуля (ModuleBase), а имя скрипта, двоичного файла или модуля манифеста должно совпадать с именем папки модуля со следующими исключениями:

- Динамические модули, создаваемые командлетом `New-Module`, могут называться с помощью параметра `Name` командлета.

- Модули, импортированные из объектов сборки с помощью команды **`Import-Module`-Assembly** , именуются в соответствии со следующим синтаксисом: `"dynamic_code_module_" + assembly.GetName()`.

  Дополнительные сведения см. в статьях [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменение пути установки PSModulePath](./modifying-the-psmodulepath-installation-path.md).

## <a name="module-cmdlets-and-variables"></a>Командлеты и переменные модуля

Следующие командлеты и переменные предоставляются Windows PowerShell для создания модулей и управления ими.

Командлет [New-Module](/powershell/module/Microsoft.PowerShell.Core/New-Module) . Этот командлет создает новый динамический модуль, который существует только в памяти. Модуль создается из блока сценария, и его экспортированные члены, такие как функции и переменные, немедленно становятся доступными в сеансе и остаются доступными до закрытия сеанса.

Командлет [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) . Этот командлет создает новый файл манифеста модуля (. PSD1), заполняет его значения и сохраняет файл манифеста по указанному пути. Этот командлет также можно использовать для создания шаблона манифеста модуля, который можно заполнить вручную.

Командлет [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) . Этот командлет добавляет один или несколько модулей в текущий сеанс.

Командлет [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) . Этот командлет извлекает сведения о модулях, которые были или могут быть импортированы в текущий сеанс.

Командлет [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) . Этот командлет задает элементы модуля (например, командлеты, функции, переменные и псевдонимы), которые экспортируются из файла модуля скрипта (. PSM1) или из динамического модуля, созданного с помощью командлета `New-Module`.

Командлет [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) . Этот командлет удаляет модули из текущего сеанса.

Командлет [Test-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest) . Этот командлет проверяет, что манифест модуля точно описывает компоненты модуля, убедившись, что файлы, перечисленные в файле манифеста модуля (. PSD1), фактически существуют в указанных путях.

$PSScriptRoot эта переменная содержит каталог, из которого выполняется модуль скрипта. Он позволяет сценариям использовать путь к модулю для доступа к другим ресурсам.

$env:P Смодулепас эта переменная среды содержит список каталогов, в которых хранятся модули Windows PowerShell. Windows PowerShell использует значение этой переменной при автоматическом импорте модулей и обновлении разделов справки для модулей.

## <a name="see-also"></a>См. также:

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
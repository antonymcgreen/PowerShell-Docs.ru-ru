---
title: Импорт модуля PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 697791b3-2135-4a39-b9d7-8566ed67acf2
caps.latest.revision: 13
ms.openlocfilehash: bb5d036e5658c365a4fafa2cac05c0bba9f87019
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854060"
---
# <a name="importing-a-powershell-module"></a>Импорт модуля PowerShell

Один раз вашей установки модуля в системе, вероятно, стоит для импорта модуля. Импорт — процесс, который загружает модуль в активной памяти, таким образом, пользователь может открыть этот модуль в свой сеанс PowerShell. В PowerShell 2.0, можно импортировать модуль PowerShell вновь созданной вызовом [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлета. В PowerShell 3.0 PowerShell — возможность неявно импортировать модуль, при вызове пользователем одного из перечисленных функций и командлетов в модуле. Обратите внимание на то, что обе версии Предположим, вы устанавливаете вашего модуля в расположении, где PowerShell — возможность найти ее. Дополнительные сведения см. в разделе [Установка модуля PowerShell](./installing-a-powershell-module.md). Манифест модуля можно использовать для ограничения того, какие части вашего модуля экспортируются, и можно использовать параметры `Import-Module` вызов для ограничения того, какие части будут импортированы.

## <a name="importing-a-snap-in-powershell-10"></a>Импорт оснастки (PowerShell 1.0)

Модули не существует в PowerShell 1.0: вместо этого, необходимо зарегистрировать и использовать оснастки. Тем не менее не рекомендуется использовать эту технологию на этом этапе как обычно проще установить и импортировать модули. Дополнительные сведения см. в разделе [Создание оснастки Windows PowerShell](../cmdlet/how-to-create-a-windows-powershell-snap-in.md).

## <a name="importing-a-module-with-import-module-powershell-20"></a>Импорт модуля с Import-Module (PowerShell 2.0)

PowerShell 2.0 использует-с именем [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлета для импорта модулей. При выполнении этого командлета Windows PowerShell выполняет поиск указанного модуля в каталогах, указанных в `PSModulePath` переменной. При обнаружении указанного каталога, Windows PowerShell ищет файлы в следующем порядке: файлы манифеста модуля (psd1), скрипт файлы модуля (psm1), файлы двоичных модулей (DLL). Дополнительные сведения о добавлении каталоги для поиска, см. в разделе [изменении пути установки PSModulePath](./modifying-the-psmodulepath-installation-path.md). Ниже описывается, как импорт модуля:

```powershell
Import-Module myModule
```

При условии, что myModule выполнялось в `PSModulePath`, PowerShell загружает myModule в активной памяти. Если myModule не расположен на `PSModulePath` путь, по-прежнему явно сообщить PowerShell где ее найти:

```powershell
Import-Module -Name C:\myRandomDirectory\myModule -Verbose
```

Можно также использовать параметр verbose, чтобы определить, что выполняется экспорт из модуля, и что импортируется в активной памяти. Экспорты и импорты ограничения, которые представлены для пользователя: отличается тем, кто управляет видимостью. По сути экспорты управляются кода в модуле. Напротив, управляются imports `Import-Module` вызова. Дополнительные сведения см. в разделе **ограничение членов, будут импортироваться**ниже.

## <a name="implicitly-importing-a-module-powershell-30"></a>Неявно импорт модуля (PowerShell 3.0)

Начиная с Windows PowerShell 3.0 модули импортируются автоматически при любой командлет или функцию в модуле используется в команде. Эта функция работает для любого модуля в каталоге, включенного в значении параметра **PSModulePath** переменной среды. Если не сохранить ваш модуль на допустимый путь тем не менее, ее можно по-прежнему загружать их с помощью явного [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) описанному выше.

Следующие действия триггера, автоматический импорт модуля, а также называется «модуль автозагрузки.»

- С помощью командлета в команде. Например, при вводе `Get-ExecutionPolicy` импортирует модуль Microsoft.PowerShell.Security, содержащий `Get-ExecutionPolicy` командлета.

- С помощью [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) для получения команды.  Например, при вводе `Get-Command Get-JobTrigger` импортирует **PSScheduledJob** модуля, содержащего `Get-JobTrigger` командлета. Объект `Get-Command` команда, которая содержит подстановочные знаки считается обнаружения и не вызывает импорт модуля.

- С помощью [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) для получения справки по командлету. Например, при вводе `Get-Help Get-WinEvent` импортирует модуль Microsoft.PowerShell.Diagnostics, который содержит `Get-WinEvent` командлета.

Для поддержки автоматический импорт модулей, `Get-Command` командлет получает все командлеты и функции во всех установленных модулях, даже если модуль не импортируется в сеанс. Дополнительные сведения см. в разделе справки для [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) командлета.

## <a name="the-importing-process"></a>Процесс импорта

При импорте модуля, состояние нового сеанса создается для модуля и [System.Management.Automation.PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) объект создается в памяти. Состояние сеанса создается для каждого модуля, который импортируется (включая корневой модуль и все вложенные модули). Элементы, экспортируемые из корневого модуля, включая любые элементы, которые были экспортированы для основного модуля, все вложенные модули импортируются в состоянии сеанса вызывающего.

Метаданные элементов, которые экспортируются из модуля имеют свойство ModuleName. Это свойство заполняется с именем модуля, экспортировать их.

> [!WARNING]
> Если в имени члена экспортированного используется недопустимую команду или если в имени элемента используется запрещенные знаки, то отображается предупреждение при [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) выполнения командлета.

По умолчанию [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлет не возвращает никакие объекты в конвейер. Тем не менее, этот командлет поддерживает `PassThru` параметр, который может использоваться для возврата [System.Management.Automation.PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) объекта для каждого модуля, который импортируется. Для отправки выходных данных на узел, пользователи должны запускать [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) командлета.

## <a name="restricting--the-members-that-are-imported"></a>Ограничение импортируемые элементы

При импорте модуля с помощью [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлета, по умолчанию все экспортированного модуля, члены импортируются в сеанс, включая любые команды экспортировать в модуль с вложенного модуля. По умолчанию переменные и псевдонимы не экспортируются. Чтобы ограничить элементы, экспортируемые [манифеста модуля](./how-to-write-a-powershell-module-manifest.md). Чтобы ограничить элементы, которые будут импортированы, используйте следующие параметры `Import-Module` командлета.

- `Function`: Этот параметр ограничивает экспортируемые функции. (Если вы используете манифеста модуля, см. в разделе ключ FunctionsToExport.)

- `Cmdlet`: Этот параметр ограничивает командлеты, которые экспортируются (Если вы используете модуль манифеста, см. раздел CmdletsToExport.)

- `Variable`: Этот параметр ограничивает переменные, экспортируемые (Если вы используете модуль манифеста, см. раздел VariablesToExport.)

- `Alias`: Этот параметр ограничивает псевдонимы, экспортируемые (Если вы используете модуль манифеста, см. раздел AliasesToExport.)

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)

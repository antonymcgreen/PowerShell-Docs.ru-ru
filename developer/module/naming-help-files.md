---
title: Именование файлов справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: 06281a1260dbdc120867fce89e6d5c8dd0754b87
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856670"
---
# <a name="naming-help-files"></a>Указание имен для файлов справки

В этом разделе объясняется, как имя файла справки на основе XML, чтобы [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета можно найти его. Требования к имени зависят от типа команды.
В этом разделе объясняется, как имя файла справки на основе XML, чтобы [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета можно найти его. Требования к имени зависят от типа команды.

## <a name="cmdlet-help-files"></a>Файлы справки по командлетам

Файл справки для C# командлет должен иметь имя для сборки, в котором определен этот командлет. Используйте следующий формат имени файла:

```
<AssemblyName>.dll-help.xml
```

Формат имени сборки является обязательным, даже в том случае, если сборка является вложенного модуля.

Например [Get-WinEvent; PSITPro5_Diagnostic; ](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) командлет определен в сборке Microsoft.PowerShell.Diagnostics.dll. `Get-Help` Командлет ищет раздел справки для `Get-WinEvent` командлет только в файле Microsoft.PowerShell.Diagnostics.dll help.xml в каталоге модуля.
Например [Get-WinEvent; PSITPro5_Diagnostic; ](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) командлет определен в сборке Microsoft.PowerShell.Diagnostics.dll. `Get-Help` Командлет ищет раздел справки для `Get-WinEvent` командлет только в файле Microsoft.PowerShell.Diagnostics.dll help.xml в каталоге модуля.

## <a name="provider-help-files"></a>Файлы справки поставщика

Для сборки, в которой определен поставщик должен называться файл справки для поставщика Windows PowerShell. Используйте следующий формат имени файла:

```
<AssemblyName>.dll-help.xml
```

Формат имени сборки является обязательным, даже в том случае, если сборка является вложенного модуля.

Например поставщик Certificate определяется в сборке Microsoft.PowerShell.Security.dll. `Get-Help` Командлет ищет раздел справки по поставщику Certificate только в файле Microsoft.PowerShell.Security.dll help.xml в каталоге модуля.

## <a name="function-help-files"></a>Файлы справки для функции

Функции можно задокументировать с помощью [справки на основе комментариев](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) или в XML-файл справки. Когда функция описана в XML-файл, функция должна иметь `.ExternalHelp` комментарий ключевое слово, которое связывает функцию с XML-файле. В противном случае `Get-Help` командлету не удается найти файл справки.
Функции можно задокументировать с помощью [справки на основе комментариев](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) или в XML-файл справки. Когда функция описана в XML-файл, функция должна иметь `.ExternalHelp` комментарий ключевое слово, которое связывает функцию с XML-файле. В противном случае `Get-Help` командлету не удается найти файл справки.

Не существует технических требований к имени файла справки функции. Тем не менее мы рекомендуем для именования файла справки для модуля сценария, в котором определена функция. Например следующая функция определяется в файле MyModule.psm1.

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>Файлы справки для команд CIM

Файл справки для команд CIM должен иметь имя для файла CDXML, в котором определен команды CIM. Используйте следующий формат имени файла:

```
<FileName>.cdxml-help.xml
```

Команды CIM, определяются в CDXML-файлы, которые могут быть включены в модулях, как вложенные модули. При импорте команды CIM в сеанс как функции Windows PowerShell добавляет `.ExternalHelp` комментарий, ключевое слово в определении функции, который связывает функцию с помощью XML файл, который совпадает с именем файла CDXML, в котором определен команды CIM.

## <a name="script-workflow-help-files"></a>Файлы справки для рабочего процесса сценария

Рабочие процессы сценариев, включенных в модулях документируется в файлы справки на основе XML. Не существует технических требований к имени файла справки. Тем не менее мы рекомендуем для именования файла справки для модуля сценария, в котором определен рабочем процессе сценария. Например:

```
<ScriptModule>.psm1-help.xml
```

В отличие от других скриптовые команды рабочих процессах сценариев не требуют `.ExternalHelp` комментарий ключевое слово, чтобы связать их с файлом справки. Вместо этого Windows PowerShell выполняет подкаталоги каталога модуля файлы справки на основе XML для конкретного языка и региональных параметров пользовательского интерфейса и ищет справку для рабочего процесса сценария во всех файлах. `.ExternalHelp` Ключевое слово комментария, игнорируются.

Так как `.ExternalHelp` комментарий ключевого слова пропускается, `Get-Help` командлета можно найти справки для рабочих процессов для сценариев, только в том случае, если они включены в модулях.
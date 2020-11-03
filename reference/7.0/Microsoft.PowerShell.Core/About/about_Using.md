---
description: Позволяет указать, какие пространства имен используются в сеансе.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: bfd1208516193adf470a25dbdf3d58563847a26a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231866"
---
# <a name="about-using"></a>Об использовании

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Позволяет указать, какие пространства имен используются в сеансе.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

`using`Инструкция позволяет указать, какие пространства имен используются в сеансе. Добавление пространств имен упрощает использование классов и членов .NET и позволяет импортировать классы из модулей скриптов и сборок.

`using`Операторы должны располагаться перед любыми другими инструкциями в скрипте.

`using`Оператор не следует путать с `using:` модификатором области для переменных. Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).

## <a name="syntax"></a>Синтаксис

Чтобы указать пространства имен .NET, из которых следует разрешить типы:

```
using namespace <.NET-namespace>
```

Чтобы загрузить классы из модуля PowerShell, сделайте следующее:

```
using module <module-name>
```

Предварительная загрузка типов из сборки .NET:

```
using assembly <.NET-assembly-path>
```

Указание пространства имен упрощает ссылки на типы по их коротким именам.

При загрузке сборки выгружаются типы .NET из этой сборки в скрипт во время синтаксического анализа. Это позволяет создавать новые классы PowerShell, использующие типы из предварительно загруженной сборки.

Если вы не создаете новые классы PowerShell, используйте `Add-Type` вместо этого командлет. Дополнительные сведения см. в разделе [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).

## <a name="examples"></a>Примеры

### <a name="example-1---add-namespaces-for-typename-resolution"></a>Пример 1. Добавление пространств имен для разрешения имени TypeName

Следующий скрипт получает криптографический хэш для строки "Hello World".

Обратите внимание, что `using namespace System.Text` и `using namespace System.IO` упрощает ссылки на `[UnicodeEncoding]` в и и в `System.Text` `[Stream]` `[MemoryStream]` `System.IO` .

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a>Пример 2. Загрузка классов из модуля скрипта

В этом примере у нас есть модуль скрипта PowerShell с именем **кардгамес** , который определяет следующие классы:

- **Кардгамес. колода**
- **Кардгамес. Card**

`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем. Классы не импортируются. `using module`Команда импортирует модуль, а также загружает определения классов.

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a>Пример 3. Загрузка классов из сборки

В этом примере загружается сборка, чтобы ее классы можно было использовать для создания новых классов PowerShell. Следующий скрипт создает новый класс PowerShell, производный от класса **директориконтекст** .

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```

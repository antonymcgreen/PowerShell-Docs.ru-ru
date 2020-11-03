---
description: Описывает использование подстановочных знаков в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 4778de5022f35f354e7783cedc5019198d11604b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232645"
---
# <a name="about-wildcards"></a>О подстановочных знаках

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описывает использование подстановочных знаков в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Символы-шаблоны представляют один или несколько символов. Их можно использовать для создания шаблонов Word в командах. Например, чтобы получить все файлы в `C:\Techdocs` каталоге с `.ppt` расширением имени файла, введите:

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

В этом случае `*` подстановочный знак звездочки () представляет все символы, которые отображаются перед `.ppt` расширением имени файла.

PowerShell поддерживает следующие подстановочные знаки:

|Подстановочный знак|Описание               |Пример |Соответствует        |Нет совпадений|
|--------|--------------------------|--------|-------------|--------|
|\*      |Совпадение с нулем или несколькими символами | конкретного\*  | aA, AG, Apple | банан |
|?       |Совпадение с одним символом в этой позиции | ? n | Объект, в, на | обнаружил |
|\[ \]   |Совпадение с диапазоном символов | \[a-l \] УК | книга, Кука, взгляд | была |
|\[ \]   |Совпадение с конкретными символами | \[BC \] УК | книга, Кука | ключ |

В один шаблон Word можно включить несколько подстановочных знаков. Например, чтобы найти текстовые файлы с именами, начинающимися с букв **a** до **l** , введите:

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

Многие командлеты принимают подстановочные знаки в значениях параметров. Раздел справки для каждого командлета описывает, какие параметры принимают подстановочные знаки. Для параметров, которые принимают подстановочные знаки, их использование не учитывает регистр.

Подстановочные знаки можно использовать в командах и блоках скриптов, например для создания шаблона Word, представляющего значения свойств. Например, следующая команда получает службы, в которых значение свойства **serviceType** включает **Interactive**.

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

В следующем примере `If` инструкция включает условие, которое использует подстановочные знаки для поиска значений свойств. Если **Описание** точки восстановления включает **PowerShell** , команда добавляет значение свойства **CreationTime** для точки восстановления в файл журнала.

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Language_Keywords](about_Language_Keywords.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)


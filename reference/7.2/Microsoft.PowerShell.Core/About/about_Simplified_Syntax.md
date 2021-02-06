---
description: Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: dbd30d566414f784e7d5eca04af716c2bf1642b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604300"
---
# <a name="about_simplified_syntax"></a>about_Simplified_Syntax

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Упрощенный синтаксис, представленный в Windows PowerShell 3,0, позволяет создавать некоторые команды фильтров без использования блоков сценариев. Упрощенный синтаксис более похож на естественный язык и в основном полезен для коллекций объектов, которые передаются в команды, и `Where-Object` `ForEach-Object` их соответствующие псевдонимы `where` и `foreach` .

Можно использовать метод для членов коллекции (чаще всего это массив), не ссылаясь на автоматическую переменную `$_` внутри блока script.

Рассмотрим следующие два вызова:

### <a name="standard-syntax"></a>Стандартный синтаксис

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a>Упрощенный синтаксис

В упрощенном синтаксисе операторы сравнения, работающие с членами объектов в коллекции, обрабатываются как параметры. Можно вызвать метод для объектов в коллекции, не ссылаясь на автоматическую переменную `$_` внутри блока script.
Сравните следующие два вызова с теми, которые относятся к предыдущему примеру:

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

Хотя оба синтаксиса работают, упрощенный синтаксис возвращает результаты, не ссылаясь на автоматическую переменную `$_` внутри блока script.
Имя метода `GetKeyAlgorithm` рассматривается как параметр `ForEach-Object` .
Вторая команда возвращает те же результаты, но без ошибок, поскольку упрощенный синтаксис не пытается вернуть результаты для элементов, для которых указанный аргумент не был применен.

В этом примере `Process` свойство `Description` передается в качестве параметра имени члена в `ForEach-Object` команду. Результаты представляют собой описания активных процессов.

```powershell
Get-Process | foreach Description
```

В этом примере `DirectoryInfo` метод `GetFiles` передается в качестве параметра имени члена `ForEach-Object` команды.  
Метод вызывается с параметром шаблона поиска `.*` .  
Результаты представляют собой `FileInfo` записи для всех скрытых файлов в стиле UNIX в домашних каталогах пользователей. 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_Comparison_Operators](about_Comparison_Operators.md)
- [about_Foreach](about_Foreach.md)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)


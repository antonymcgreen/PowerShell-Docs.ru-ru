---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: 8773c69d638a1d04dc946cf448a44799341e663b
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390598"
---
# Set-StrictMode

## Краткий обзор
Устанавливает и применяет правила кодирования в выражениях, сценариях и блоках сценариев.

## SYNTAX

### Версия (по умолчанию)

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### Выключено

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## DESCRIPTION

`Set-StrictMode`Командлет настраивает в режиме ограниченного режима для текущей области и всех дочерних областей, включает и выключает ее. Если режим строгого режима включен, PowerShell создает завершающую ошибку, если содержимое выражения, скрипта или блока скрипта нарушает основные рекомендации по написанию кода.

Используйте параметр **Version** , чтобы определить, какие правила кодирования применяются.

`Set-PSDebug -Strict` включает в себя режим для глобальной области. `Set-StrictMode` влияет только на текущую область и ее дочерние области. Таким образом, его можно использовать в скрипте или функции для переопределения параметра, унаследованного от глобальной области.

Если `Set-StrictMode` параметр имеет значение OFF, PowerShell имеет следующие характеристики:

- Предполагается, что неинициализированные переменные имеют значение 0 (ноль) или `$Null` , в зависимости от типа.
- Возвращают ссылки на несуществующие свойства `$Null`
- Результаты неправильного синтаксиса функции зависят от условий возникновения ошибок
- Попытка получить значение с помощью недопустимого индекса в массиве возвращает `$Null`

## Примеры

### Пример 1. Включение режима "в режиме" для версии 1,0

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
InvalidOperation: The variable '$a' cannot be retrieved because it has not been set.
```

Если в режиме ограниченного режима задана версия 1,0, пытается ссылаться на переменные, которые не были инициализированы ошибкой.

### Пример 2. Включение режима "в режиме" для версии 2,0

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
InvalidOperation: The function or command was called as if it were a method. Parameters should be separated by spaces. For information about parameters, see the about_Parameters Help topic.
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$null -eq $string.Month
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$null -eq $string.Month
```

```Output
PropertyNotFoundException: The property 'Month' cannot be found on this object. Verify that the property exists.
```

Эта команда включает строгий режим и задает его версию 2.0. В результате PowerShell возвращает ошибку, если используется синтаксис метода, который использует круглые скобки и запятые для вызова функции или ссылки на неинициализированные переменные или несуществующие свойства.

Пример выходных данных приведен для строгого режима версии 2.0.

Если строгий режим версии 2.0 не используется, значение "(3,4)" интерпретируется как один объект массива, к которому ничего не добавляется. С помощью режима в режиме версии 2,0 он правильно интерпретируется как ошибочный синтаксис для отправки двух значений.

Без версии 2,0 ссылка на несуществующее свойство **Month** строки возвращает только `$Null` . С помощью версии 2,0 она правильно интерпретируется как ошибка ссылки.

### Пример 3. Включение режима "в режиме" для версии 3,0

Если задан режим " **выкл**.", то результатом недопустимости или выхода из индексов границ будет возвращено значение null.

```powershell
# Strict mode is off by default.
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
OperationStopped: Index was outside the bounds of the array.

InvalidArgument: Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
```

Если в режиме строгих версий задано значение версии 3 или выше, индексы недопустим или out вне границ приводят к ошибкам.

## PARAMETERS

### -Выкл.

Указывает, что этот командлет выключает режим "ограничено" для текущей области и всех дочерних областей.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Определяет условия, которые приводят к ошибке в строгом режиме. Этот параметр принимает любой допустимый номер версии PowerShell. Любое число выше 3 обрабатывается как **Последнее**.

Действующие значения для этого параметра:

- 1.0
  - Запрещает ссылки на неинициализированные переменные, за исключением неинициализированных переменных в строках.
- 2.0
  - Запрещает ссылки на неинициализированные переменные. Сюда входят неинициализированные переменные в строках.
  - Запрещает ссылки на несуществующие свойства объекта.
  - Запрещает вызовы функций, которые используют синтаксис для вызова методов.
- 3.0
  - Запрещает ссылки на неинициализированные переменные. Сюда входят неинициализированные переменные в строках.
  - Запрещает ссылки на несуществующие свойства объекта.
  - Запрещает вызовы функций, которые используют синтаксис для вызова методов.
  - Запрет вне границ или неразрешимые индексы массива.
- Последняя версия
  - Выбирается последняя доступная версия. Самая последняя версия — наиболее доступная. Используйте это значение, чтобы убедиться, что скрипты используют наиболее доступную версию, даже если новые версии добавлены в PowerShell.

> [!CAUTION]
> Использование последней **версии** в **Latest** скриптах. Значение **последней** может измениться в новых выпусках PowerShell. Таким образом, сценарий, написанный для более ранней версии PowerShell, который использует, `Set-StrictMode -Version Latest` имеет более ограниченные правила при запуске в более новой версии PowerShell.

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

`Set-StrictMode` действует только в области, в которой он задан, и в его дочерних областях. Дополнительные сведения об областях в PowerShell см. в разделе [about_Scopes](about/about_Scopes.md).

## Связанные ссылки

[Set-PSDebug](Set-PSDebug.md)

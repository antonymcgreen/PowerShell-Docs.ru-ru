---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a332ba5226f13b6af393c5ba52c4f3447e2799df
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225601"
---
# Set-PSDebug

## Краткий обзор
Включает и выключает функции отладки сценариев, задает уровень трассировки и переключает строгий режим.

## SYNTAX

### on

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### off

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## DESCRIPTION

`Set-PSDebug`Командлет включает и выключает функции отладки скриптов, устанавливает уровень трассировки и переключает в режим «в режиме». По умолчанию функции отладки PowerShell отключены.

Если параметр **трассировки** имеет значение `1` , каждая строка скрипта будет отслеживаться по мере выполнения. Если параметр имеет значение `2` , то также отслеживаются присваивания переменных, вызовы функций и вызовы скриптов. Если указан параметр **Step** , перед выполнением каждой строки скрипта выводится запрос.

## Примеры

### Пример 1. Задание уровня трассировки

В этом примере устанавливается уровень трассировки `2` , а затем выполняется сценарий, отображающий числа 1, 2 и
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### Пример 2. Включение пошагового выполнения

В этом примере включается пошаговая отладка, а затем выполняется сценарий, отображающий числа 1, 2 и 3.

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### Пример 3. Использование режима "в режиме"

В этом примере PowerShell помещается в режиме с максимальным доступом и пытается получить доступ к переменной, которой не назначено значение.

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### Пример 4. Отключение функций отладки

В этом примере отключаются все функции отладки, а затем выполняется сценарий, отображающий числа 1, 2 и 3.

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## PARAMETERS

### -Выкл.

Отключает все функции отладки сценариев.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Шаг

Включает пошаговое выполнение сценария. Перед выполнением каждой строки PowerShell предлагает прекратить, продолжить или ввести новый уровень интерпретатора для проверки состояния сценария.

При указании параметра **Step** автоматически устанавливается уровень трассировки `1` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### — Не ограничивать

Указывает, что переменным должно быть присвоено значение, прежде чем ссылаться на них в скрипте. Если ссылка на переменную указана перед присвоением значения, PowerShell возвращает ошибку исключения. Это равносильно `Set-StrictMode -Version 1`. Дополнительные сведения см. в разделе [Set-StrictMode](Set-StrictMode.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trace

Задает уровень трассировки для каждой строки в скрипте. Каждая строка отслеживается по мере выполнения.

Для этого параметра допустимы следующие значения:

- 0: отключить трассировку скрипта.
- 1: трассировка строк скрипта при их выполнении.
- 2: трассировка строк скрипта, назначения переменных, вызовы функций и скрипты.

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете конвейерировать входные данные для этого командлета.

## Выходные данные

### Нет

Этот командлет не возвращает никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Debuggers](./About/about_Debuggers.md)

[Debug-Process](../Microsoft.PowerShell.Management/Debug-Process.md)

[Set-PSBreakpoint](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[Set-StrictMode](Set-StrictMode.md)

[Write-Debug](../Microsoft.PowerShell.Utility/Write-Debug.md)

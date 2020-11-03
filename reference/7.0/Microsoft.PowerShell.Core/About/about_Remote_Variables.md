---
description: Объясняет использование локальных и удаленных переменных в удаленных командах.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: 2260e1a6ba4553cbdba0057972f491d17c61382d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232533"
---
# <a name="about-remote-variables"></a>Сведения об удаленных переменных

## <a name="short-description"></a>Краткое описание

Объясняет использование локальных и удаленных переменных в удаленных командах.

## <a name="long-description"></a>Подробное описание

Переменные можно использовать в командах, выполняемых на удаленных компьютерах. Присвойте значение переменной, а затем используйте переменную вместо значения.

По умолчанию переменные в удаленных командах считаются определенными в сеансе, который выполняет команду. Переменные, определенные в локальном сеансе, должны быть идентифицированы как локальные переменные в команде.

## <a name="using-remote-variables"></a>Использование удаленных переменных

В PowerShell предполагается, что переменные, используемые в удаленных командах, определены в сеансе, в котором выполняется команда.

В этом примере `$ps` переменная определена во временном сеансе, в котором `Get-WinEvent` выполняется команда.

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

При выполнении команды в постоянном сеансе **PSSession** в этом сеансе должна быть определена удаленная переменная.

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a>Использование локальных переменных

Локальные переменные можно использовать в удаленных командах, но переменная должна быть определена в локальном сеансе.

Начиная с PowerShell 3,0 можно использовать `Using` Модификатор области для определения локальной переменной в удаленной команде.

Синтаксис `Using` имеет следующий вид:

```
$Using:<VariableName>
```

В следующем примере `$ps` переменная создается в локальном сеансе, но используется в сеансе, в котором выполняется команда. `Using`Модификатор области определяет `$ps` как локальную переменную.

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

`Using`Модификатор области может использоваться в **PSSession**.

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

Ссылка на переменную, например, `$using:var` расширяется до значения переменной `$var` из контекста вызывающего объекта. Вы не получаете доступ к объекту переменной вызывающего объекта.
`Using`Модификатор области не может использоваться для изменения локальной переменной в **PSSession**. Например, следующий код не работает:

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

Дополнительные сведения о `Using` см. в разделе [about_Scopes](./about_Scopes.md)

### <a name="using-splatting"></a>Использование Сплаттинг

Сплаттинг PowerShell передает коллекцию имен и значений параметров в команду. Дополнительные сведения см. в разделе [about_Splatting](about_Splatting.md).

В этом примере переменная Сплаттинг `$Splat` является хэш-таблицей, настроенной на локальном компьютере. `Invoke-Command`Подключается к сеансу удаленного компьютера. Блок **ScriptBlock** использует `Using` Модификатор области с `@` символом at () для представления переменной сплаттед.

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a>Другие ситуации, в которых требуется модификатор области using

Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ. `Using`Модификатор области поддерживается в следующих контекстах:

- Удаленно выполненные команды, запущенные с `Invoke-Command` использованием параметров **ComputerName** , **HostName** , **сшконнектион** или **Session** (удаленный сеанс)
- Фоновые задания, запущенные с помощью `Start-Job` (вне процесса)
- Задания потоков, запущенные через `Start-ThreadJob` или `ForEach-Object -Parallel` (отдельный сеанс потока)

В зависимости от контекста значения внедренных переменных — это либо независимые копии данных в области вызывающего объекта, либо ссылки на него. В удаленных и необработанных сеансах они всегда являются независимыми копиями. В сеансах потока они передаются по ссылке.

## <a name="serialization-of-variable-values"></a>Сериализация значений переменных

Удаленные команды и фоновые задания выполняются вне процесса.
Необработанные сеансы используют сериализацию и десериализацию на основе XML, чтобы сделать значения переменных доступными через границы процесса. Процесс сериализации преобразует объекты в **PSObject** , который содержит исходные свойства объектов, но не его методы.

Для ограниченного набора типов десериализация восстанавливает объекты обратно в исходный тип. Восстановленный объект является копией исходного экземпляра объекта.
Он содержит свойства и методы типа. Для простых типов, таких как **System. Version** , копия является точной. Для сложных типов копия — неидеальны. Например, rehydratя объектов сертификатов не включает закрытый ключ.

Экземпляры всех остальных типов являются экземплярами **PSObject** . Свойство **PSTypeNames** содержит имя исходного типа с префиксом **десериализации** , например **Deserialized.SysTEM. Data. DataTable**

## <a name="using-local-variables-with-argumentlist-parameter"></a>Использование локальных переменных с параметром **ArgumentList**

Локальные переменные можно использовать в удаленной команде, определяя параметры для удаленной команды и используя параметр **ArgumentList** `Invoke-Command` командлета, чтобы указать локальную переменную в качестве значения параметра.

- Используйте `param` ключевое слово для определения параметров удаленной команды. Имена параметров — это заполнители, которые не обязательно должны совпадать с именем локальной переменной.

- Используйте параметры, определенные `param` ключевым словом в команде.

- Используйте параметр **ArgumentList** `Invoke-Command` командлета, чтобы указать локальную переменную в качестве значения параметра.

Например, следующие команды определяют `$ps` переменную в локальном сеансе и затем используют ее в удаленной команде. Команда использует `$log` в качестве значения имени параметра и локальной переменной `$ps` .

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a>См. также статью

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Splatting](about_Splatting.md)

[about_Variables](about_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Start-ThreadJob](xref:ThreadJob.Start-ThreadJob)

[ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)

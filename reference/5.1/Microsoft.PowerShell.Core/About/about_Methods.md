---
description: Описывает, как использовать методы для выполнения действий с объектами в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 7160b049cffffa35263fc75fd595997c98ca2e34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232001"
---
# <a name="about-methods"></a>О методах

## <a name="short-description"></a>Краткое описание
Описывает, как использовать методы для выполнения действий с объектами в PowerShell.

## <a name="long-description"></a>Подробное описание

PowerShell использует объекты для представления элементов в хранилищах данных или состояния компьютера. Например, объекты FileInfo представляют файлы на дисках файловой системы, а объекты Процессинфо представляют процессы на компьютере.

Объекты имеют свойства, которые хранят данные об объекте и методы, позволяющие изменить объект.

"Метод" — это набор инструкций, указывающих действие, которое можно выполнить над объектом. Например, `FileInfo` объект включает `CopyTo` метод, который копирует файл, который `FileInfo` представляет объект.

Чтобы получить методы любого объекта, используйте `Get-Member` командлет. Используйте свойство **MemberType** со значением "Method". Следующая команда получает методы объектов Process.

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

Чтобы выполнить или "вызвать" метод объекта, введите точку (.), имя метода и набор круглых скобок "()". Если у метода есть аргументы, заключите значения аргументов в круглые скобки. Круглые скобки требуются для каждого вызова метода, даже если отсутствуют аргументы. Если метод принимает несколько аргументов, они должны быть разделены запятыми.

Например, следующая команда вызывает метод Kill для процессов, чтобы завершить процесс «блокнота» на компьютере.

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

Этот пример можно сократить, объединив приведенные выше операторы.

```powershell
(Get-Process Notepad).Kill()
```

`Get-Process`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед вызовом метода Kill. `Kill`Затем метод вызывается для возвращенного `Process` объекта.

Еще один очень полезный метод — это `Replace` метод строк. `Replace`Метод заменяет текст в строке. В приведенном ниже примере точка (.) может быть помещена сразу после закрывающей кавычки строки.

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

Как показано в предыдущих примерах, можно вызвать метод для объекта, полученного с помощью команды, объекта в переменной или любого объекта, который приводит к объекту (например, строке в кавычках).

Начиная с PowerShell 4,0 поддерживается вызов методов с использованием имен динамических методов.

### <a name="learning-about-methods"></a>Изучение методов

Чтобы найти определения методов объекта, перейдите в раздел справки по типу объекта в MSDN и найдите страницу методов. Например, на следующей странице описываются методы обработки объектов [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods).

Чтобы определить аргументы метода, проверьте определение метода, похожее на схему синтаксиса командлета PowerShell.

Определение метода может иметь одну или несколько подписей методов, которые подобны наборам параметров командлетов PowerShell. Сигнатуры показывают все допустимые форматы команд для вызова метода.

Например, `CopyTo` метод `FileInfo` класса содержит следующие две сигнатуры метода:

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

Первая сигнатура метода принимает имя целевого файла (и путь). В следующем примере первый метод используется `CopyTo` для копирования `Final.txt` файла в `C:\Bin` каталог.

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> В отличие от режима _аргументов_ PowerShell, методы объекта выполняются в режиме _выражения_ , который является транзитным для платформы .NET Framework, на которой построена оболочка PowerShell. В _expression_ режиме выражения **бареворд** аргументы (строки без кавычек) не допускаются. Это различие можно увидеть при использовании пути в качестве параметра, а не пути в качестве аргумента. Дополнительные сведения о режимах анализа можно узнать в [about_Parsing](about_Parsing.md)

Вторая сигнатура метода принимает имя целевого файла и логическое значение, определяющее, следует ли перезаписывать файл назначения, если он уже существует.

В следующем примере второй метод используется `CopyTo` для копирования `Final.txt` файла в `C:\Bin` каталог и для перезаписи существующих файлов.

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a>Методы скалярных объектов и коллекций

Методы одного («скалярного») объекта определенного типа часто отличаются от методов коллекции объектов того же типа.

Например, каждый процесс имеет `Kill` метод, но коллекция процессов не имеет метода Kill.

Начиная с PowerShell 3,0, PowerShell пытается предотвратить ошибки скрипта, которые возникают из разных методов скалярных объектов и коллекций.

Если вы отправляете коллекцию, но запрашиваете метод, который существует только для отдельных ("скалярных") объектов, PowerShell вызывает метод для каждого объекта в коллекции.

Если метод существует для отдельных объектов и коллекции, вызывается только метод коллекции.

Эта функция также работает с свойствами скалярных объектов и коллекций. Дополнительные сведения см. в разделе [about_Properties](about_Properties.md).

### <a name="examples"></a>Примеры

В следующем примере выполняется метод **Kill** отдельных объектов Process в коллекции объектов.

Первая команда запускает три экземпляра процесса Блокнота. `Get-Process` Возвращает все три экземпляра процесса блокнота и сохраняет их в `$p` переменной.

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

Следующая команда выполняет метод **Kill** для всех трех процессов в `$p` переменной. Эта команда работает, даже если в коллекции процессов отсутствует `Kill` метод.

```powershell
$p.Kill()
Get-Process Notepad
```

`Get-Process`Команда подтверждает, что `Kill` метод сработал.

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

Этот пример функционально эквивалентен использованию `Foreach-Object` командлета для выполнения метода для каждого объекта в коллекции.

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a>Методы ForEach и WHERE

Начиная с PowerShell 4,0, поддерживается фильтрация коллекций с помощью синтаксиса методов. Это позволяет использовать два новых метода при работе с коллекциями `ForEach` и `Where` .

Дополнительные сведения об этих методах в см. в разделе [about_arrays](about_arrays.md).

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a>Вызов определенного метода при наличии нескольких перегрузок

При вызове методов .NET учитывайте следующий сценарий. Если метод принимает объект, но имеет перегрузку через интерфейс, принимающий более конкретный тип, то PowerShell выбирает метод, который принимает объект, пока он не будет явно приведен к этому интерфейсу.

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

В этом примере `object` был выбран менее определенный перегруженный метод **линейчатого** метода.

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

В этом примере мы приведен метод к интерфейсу **Ифу** , чтобы выбрать более конкретную перегрузку метода **Bar** .

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a>См. также:

[about_Objects](about_Objects.md)

[about_Properties](about_Properties.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

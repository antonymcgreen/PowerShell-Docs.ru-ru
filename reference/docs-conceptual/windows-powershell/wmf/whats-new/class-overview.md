---
ms.date: 07/29/2020
title: Новые возможности языка в PowerShell 5.0
ms.openlocfilehash: dada39c4121a810c7ce87a642f232934152104e5
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410178"
---
# <a name="new-language-features-in-powershell-50"></a>Новые возможности языка в PowerShell 5.0

В PowerShell 5.0 появилась возможность определения классов и других определяемых пользователем типов с использованием формального синтаксиса и семантики, как и в других объектно-ориентированных языках программирования. Целью этого шага является расширение вариантов использования PowerShell, доступных разработчикам и ИТ-специалистам, упрощение разработки артефактов PowerShell (например, ресурсов DSC) и ускорение освоения поверхностей управления.

В PowerShell 5.0 появились следующие новые элементы языка для PowerShell:

### <a name="class-keyword"></a>Ключевое слово Class

Ключевое слово `class` определяет новый класс. Это подлинный тип .NET Framework. Члены класса являются открытыми, но только в рамках области модуля. Вы не можете ссылаться на имя типа в виде строки (например, `New-Object` не работает), а также использовать литерал типа (например, `[MyClass]`) за пределами файла скрипта или модуля, где определен этот класс.

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Ключевое слово Enum и перечисления

Добавлена поддержка ключевого слова `enum`, где символ новой строки используется в качестве разделителя. Сейчас нельзя определить перечислитель относительно самого себя. Тем не менее перечисление можно инициализировать относительно другого перечисления, как показано в следующем примере. Кроме того, нельзя задать базовый тип (всегда `[int]`).

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Значение перечислителя должно быть константой времени анализа. Его нельзя задать как результат вызванной команды.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

Перечисления поддерживают арифметические операции, как показано в следующем примере:

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

Теперь `Import-DscResource` — это динамическое ключевое слово. PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут **DscResource**.

### <a name="implementingassembly"></a>ImplementingAssembly

В **ModuleInfo** добавлено новое поле **ImplementingAssembly**. Ему присваивается динамическая сборка, созданная для модуля сценариев, если скрипт определяет классы, или загруженная сборка для двоичных модулей. Оно не задано, когда **ModuleType** имеет значение **Manifest**.

Отражение поля **ImplementingAssembly** обнаруживает ресурсы в модуле. Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.

## <a name="further-reading"></a>Дополнительные сведения

- [about_Classes](/powershell/module/microsoft.powershell.core/about/about_classes)
- [about_Enum](/powershell/module/microsoft.powershell.core/about/about_enum)
- [about_Classes_and_DSC](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)

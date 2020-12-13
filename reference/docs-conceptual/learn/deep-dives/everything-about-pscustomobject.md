---
title: Все, что вы хотели знать о PSCustomObject
description: PSCustomObject — это простое средство для создания структурированных данных.
ms.date: 10/05/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ccbdcdae5ad38f555233dffbed7e8a6ec2b0726b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "91772326"
---
# <a name="everything-you-wanted-to-know-about-pscustomobject"></a>Все, что вы хотели знать о PSCustomObject

Объекты `PSCustomObject` — это отличное средство, которое стоит добавить в набор инструментов PowerShell. Начнем с основ, а затем постепенно перейдем к работе с более сложными функциями. `PSCustomObject` стоит использовать потому, что это простой способ создания структурированных данных. Взгляните на первый пример, и вы получите более наглядное представление о том, что я имею в виду.

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом. Читайте его блог — [PowerShellExplained.com][].

## <a name="creating-a-pscustomobject"></a>Создание PSCustomObject

Мне нравится использовать `[PSCustomObject]` в PowerShell. Создать пригодный к использованию объект просто, как никогда.
Вот почему я опущу все остальные способы создания объекта. Однако обратите внимание, что большинство из этих примеров для PowerShell версии 3.0 и более поздних.

```powershell
$myObject = [PSCustomObject]@{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
```

Этот метод хорошо мне подходит, поскольку я практически везде использую хэш-таблицы. Но иногда мне хочется, чтобы в PowerShell работа с хэш-таблицами была больше похожа на работу с объектами. Первое различие становится заметно, когда вы хотите использовать `Format-Table` или `Export-CSV` и понимаете, что хэш-таблица — это просто коллекция пар "ключ — значение".

При этом вы можете получать доступ к значениям и использовать их, как в случае с обычным объектом.

```powershell
$myObject.Name
```

### <a name="converting-a-hashtable"></a>Преобразование хэш-таблицы

Хотя мне не следует отступать от темы, возможно, не все знают о следующей возможности.

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

Я предпочитаю создавать объект с самого начала, но иногда сначала приходится работать с хэш-таблицей. Этот пример работает, поскольку конструктор принимает хэш-таблицу в качестве значения свойств объекта. Важно отметить, что хотя этот метод тоже работает, он не является точным эквивалентом. Самое большое отличие заключается в том, что порядок свойств не сохраняется.

### <a name="legacy-approach"></a>Устаревший подход

Возможно, вы видели, что некоторые разработчики используют `New-Object` для создания пользовательских объектов.

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}

$myObject = New-Object -TypeName PSObject -Property $myHashtable
```

Этот метод медленнее, но он может оказаться лучшим вариантом для ранних версий PowerShell.

### <a name="saving-to-a-file"></a>Сохранение в папке

Самый лучший способ сохранить хэш-таблицу в файл — использовать формат JSON. Вы можете импортировать ее обратно в `[PSCustomObject]`.

```powershell
$myObject | ConvertTo-Json -depth 1- | Set-Content -Path $Path
$myObject = Get-Content -Path $Path | ConvertFrom-Json
```

Я рассказываю о других способах сохранения объектов в файл в моей статье о [Множество способов чтения и записи в файлы][].

## <a name="working-with-properties"></a>Работа со свойствами

### <a name="adding-properties"></a>Добавление свойств

Вы по-прежнему можете добавлять новые свойства в объект `PSCustomObject` с помощью `Add-Member`.

```powershell
$myObject | Add-Member -MemberType NoteProperty -Name `ID` -Value 'KevinMarquette'

$myObject.ID
```

### <a name="remove-properties"></a>Удаление свойств

Вы также можете удалять свойства из объекта.

```powershell
$myObject.psobject.properties.remove('ID')
```

Доступ к метаданным базового объекта можно получить с помощью скрытого свойства `psobject`.

### <a name="enumerating-property-names"></a>Перечисление имен свойств

Иногда требуется список всех имен свойств объекта.

```powershell
$myObject | Get-Member -MemberType NoteProperty | Select -ExpandProperty Name
```

Его можно также получить из свойства `psobject`.

```powershell
$myobject.psobject.properties.name
```

### <a name="dynamically-accessing-properties"></a>Динамический доступ к свойствам

Я уже упоминал, что доступ к значениям свойств можно получить напрямую.

```powershell
$myObject.Name
```

В качестве имени свойства можно использовать строку, и это сработает.

```powershell
$myObject.'Name'
```

Можно пойти дальше и использовать в качестве имени свойства переменную.

```powershell
$property = 'Name'
$myObject.$property
```

Я знаю, что выглядит это странно, но это работает.

### <a name="convert-pscustomobject-into-a-hashtable"></a>Преобразование PSCustomObject в хэш-таблицу

В продолжение сделанного в последнем разделе можно динамически проанализировать свойства и создать из них хэш-таблицу.

```powershell
$hashtable = @{}
foreach( $property in $myobject.psobject.properties.name )
{
    $hashtable[$property] = $myObject.$property
}
```

### <a name="testing-for-properties"></a>Проверка свойств

Если необходимо узнать, существует ли свойство, можно просто проверить, есть ли у него значение.

```powershell
if( $null -ne $myObject.ID )
```

Но если это значение может быть равным `$null`, а вам все равно нужно проверить его наличие, можно проверить для него `psobject.properties`.

```powershell
if( $myobject.psobject.properties.match('ID').Count )
```

## <a name="adding-object-methods"></a>Добавление методов объектов

Если в объект необходимо добавить метод скрипта, это можно сделать с помощью `Add-Member` и `ScriptBlock`. При этом необходимо использовать автоматическую переменную `this`, ссылающуюся на текущий объект. Ниже приведен блок `scriptblock` для преобразования объекта в хэш-таблицу. (Это тот же код, что и в последнем примере.)

```powershell
$ScriptBlock = {
    $hashtable = @{}
    foreach( $property in $this.psobject.properties.name )
    {
        $hashtable[$property] = $this.$property
    }
    return $hashtable
}
```

Затем мы добавим его к нашему объекту в качестве свойства скрипта.

```powershell
$memberParam = @{
    MemberType = "ScriptMethod"
    InputObject = $myobject
    Name = "ToHashtable"
    Value = $scriptBlock
}
Add-Member @memberParam
```

Теперь мы можем вызвать нашу функцию следующим образом:

```powershell
$myObject.ToHashtable()
```

### <a name="objects-vs-value-types"></a>Объекты и типы значений

Объекты и типы значений обрабатывают назначения переменных по-разному. Если типы значений присваиваются друг другу, в новую переменную копируется только значение.

```powershell
$first = 1
$second = $first
$second = 2
```

В этом случае `$first` равно 1, а `$second` — 2.

Объектные переменные содержат ссылку на фактический объект. При назначении одного объекта новой переменной они по-прежнему ссылаются на один и тот же объект.

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third
$fourth.Key = 4
```

Поскольку `$third` и `$fourth` ссылаются на один и тот же экземпляр объекта, значение `$third.key` и `$fourth.Key` равно 4.

### <a name="psobjectcopy"></a>psobject.copy()

Если вам нужна копия объекта, его можно клонировать.

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third.psobject.copy()
$fourth.Key = 4
```

При клонировании создается неполная копия объекта. Теперь экземпляры разные, и в этом примере `$third.key` равно 3, а `$fourth.Key` — 4.

Я называю это неполной копией, так как при наличии вложенных объектов (когда свойства содержат другие объекты) копируются только значения верхнего уровня. Дочерние объекты будут ссылаться друг на друга.

### <a name="pstypename-for-custom-object-types"></a>PSTypeName для пользовательских типов объектов

Теперь, когда у нас есть объект, мы можем выполнить с ним еще несколько действий, которые могут быть не так очевидны. Прежде всего необходимо присвоить ему `PSTypeName`. Это, насколько я знаю, наиболее распространенный способ.

```powershell
$myObject.PSObject.TypeNames.Insert(0,"My.Object")
```

Недавно я обнаружил, что это можно сделать другим способом. Узнал я о нем здесь из [публикации /u/markekraus][]. Я изучил этот вопрос глубже и сделал несколько публикаций об идее [Адам Бертрам][] и [Майк Шепард][], где излагаю их мнение об этом подходе, который позволяет создавать встроенные определения.

```powershell
$myObject = [PSCustomObject]@{
    PSTypeName = 'My.Object'
    Name       = 'Kevin'
    Language   = 'PowerShell'
    State      = 'Texas'
}
```

Мне нравится то, как хорошо он соответствует языку. Теперь, когда у нас есть объект с правильным именем типа, мы можем сделать кое-что еще.

> [!NOTE]
> Можно также создавать пользовательские типы PowerShell с помощью классов PowerShell. Дополнительные сведения см. в [описании класса PowerShell](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes).

## <a name="using-defaultpropertyset-the-long-way"></a>Использование DefaultPropertySet (длинный способ)

PowerShell автоматически выбирает отображаемые свойства по умолчанию. У многих собственных команд имеется [файл форматирования ][] `.ps1xml`, который выполняет всю тяжелую работу. В [публикация Бо Прокса][] предложен еще один способ сделать это с пользовательским объектом, используя только PowerShell. Ему можно присвоить `MemberSet` для использования.

```powershell
$defaultDisplaySet = 'Name','Language'
$defaultDisplayPropertySet = New-Object System.Management.Automation.PSPropertySet('DefaultDisplayPropertySet',[string[]]$defaultDisplaySet)
$PSStandardMembers = [System.Management.Automation.PSMemberInfo[]]@($defaultDisplayPropertySet)
$MyObject | Add-Member MemberSet PSStandardMembers $PSStandardMembers
```

Теперь, когда объект оказался в оболочке, для него по умолчанию будут отображаться только эти свойства.

### <a name="update-typedata-with-defaultpropertyset"></a>Update-TypeData с DefaultPropertySet

Это удобный способ, но недавно при просмотре видео [PowerShell 2016 без подключения с Джеффри Сновером и Доном Джонсом][psunplugged] я узнал, что есть еще удобнее. Чтобы указать свойства по умолчанию, Джеффри использовал [Update-TypeData][].

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    DefaultDisplayPropertySet = 'Name','Language'
}
Update-TypeData @TypeData
```

Это так просто, что я бы даже запомнил этот способ, если бы у меня не было под рукой этой публикации для справки. Теперь я могу легко создавать объекты с большим количеством свойств, которые будут выглядеть все так же аккуратно и понятно при просмотре из оболочки. Если мне нужно получить доступ к другим свойствам или просмотреть их, они всегда под рукой.

```powershell
$myObject | Format-List *
```

### <a name="update-typedata-with-scriptproperty"></a>Update-TypeData со ScriptProperty

Из этого видео я также узнал, как создавать свойства скрипта для объектов. Стоит отметить, что этот подход работает и для имеющихся объектов.

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    MemberType = 'ScriptProperty'
    MemberName = 'UpperCaseName'
    Value = {$this.Name.toUpper()}
}
Update-TypeData @TypeData
```

Его можно применить как до создания объекта, так и после, и все равно все получится. Этим данный подход и отличается от использования `Add-Member` со свойством скрипта. При использовании `Add-Member` (этот способ я описал ранее) свойство существует только в данном конкретном экземпляре объекта. Это относится ко всем объектам с таким значением `TypeName`.

## <a name="function-parameters"></a>Параметры функции

Теперь эти пользовательские типы можно применять для параметров в функциях и скриптах. Одна функция может создать эти пользовательские объекты и передать их в другие функции.

```powershell
param( [PSTypeName('My.Object')]$Data )
```

В PowerShell требуется, чтобы объект принадлежал к указанному типу. Если при автоматической проверке обнаруживается несоответствие типов, выводится сообщение об ошибке проверки, чтобы вам не пришлось делать лишний шаг при тестировании. Это отличный пример того, как оптимально использовать преимущества PowerShell.

### <a name="function-outputtype"></a>Тип OutputType функции

Вы можете также определить `OutputType` для расширенных функций.

```powershell
function Get-MyObject
{
    [OutputType('My.Object')]
    [CmdletBinding()]
        param
        (
            ...
```

Значение атрибута **OutputType** предназначено только для документации. Он не является производным от кода функции и не сравнивается с ее фактическими выходными данными.

Основная причина использования выходного типа заключается в том, что метаданные, относящиеся к вашей функции, должны отражать ваши намерения. Это могут быть `Get-Command` и `Get-Help`, преимущества которых можно использовать в среде разработки. Дополнительные сведения см. в справке: [about_Functions_OutputTypeAttribute][].

При этом, если вы используете Pester для модульного тестирования функций, неплохо было бы убедиться, что выходные объекты соответствуют типу **OutputType**. Это позволит перехватить переменные, которые попадают в канал, в котором их быть не должно.

## <a name="closing-thoughts"></a>Выводы

Эта статья посвящена `[PSCustomObject]`, но многие из этих сведений относятся к объектам в целом.

Я уже встречал сведения об этих возможностях ранее, но никогда не видел, чтобы они были собраны в единый документ по `PSCustomObject`. Буквально на прошлой неделе я наткнулся на такую информацию и был удивлен, что никогда ранее ее не встречал. Я хотел объединить все эти идеи, чтобы вы могли увидеть более полную картину и знали о том, что такие возможности существуют, когда они вам понадобятся. Надеюсь, что вы чему-то научились и сможете применить эти знания на практике в своих сценариях.

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[публикация Бо Прокса]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[файл форматирования ]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[about_Functions_OutputTypeAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute
[Множество способов чтения и записи в файлы]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[публикации /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[Адам Бертрам]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Майк Шепард]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[psunplugged]: https://www.youtube.com/watch?v=Ab46gHXNm8Q
[Update-TypeData]: /powershell/module/microsoft.powershell.utility/update-typedata

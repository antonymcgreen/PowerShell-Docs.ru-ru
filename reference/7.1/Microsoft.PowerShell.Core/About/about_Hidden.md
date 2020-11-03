---
description: Описывает ключевое слово Hidden, которое скрывает члены класса от результатов по умолчанию Get-Member.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 7a8646f1b88da9b42ef26ccdf1d27eaa7042abd7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231110"
---
# <a name="about_hidden"></a>about_Hidden

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает ключевое слово Hidden, которое скрывает члены класса от результатов по умолчанию Get-Member.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

При использовании в скрипте ключевого слова Hidden члены класса скрываются по умолчанию. Ключевое слово Hidden может скрывать свойства, методы (включая конструкторы, события, свойства псевдонима и другие типы элементов, включая статические элементы, из результатов по умолчанию для командлета Get-Member, а также из результатов функций IntelliSense и табуляции. Чтобы отобразить элементы, скрытые с помощью ключевого слова Hidden, добавьте параметр-Force в Get-Member команду.

Скрытые члены не отображаются при нажатии клавиши TAB или IntelliSense, если завершение не происходит в классе, который определяет скрытый элемент.

Добавлен новый атрибут System. Management. Automation. Хидденаттрибуте, поэтому \# код C может иметь ту же семантику в PowerShell.

Ключевое слово Hidden полезно для создания свойств и методов внутри класса, которые не обязательно должны видеть другие пользователи класса или могут быть доступны для редактирования.

Ключевое слово Hidden не влияет на то, как можно просматривать или вносить изменения в члены класса. Как и все ключевые слова языка в PowerShell, скрытые элементы не учитывают регистр, а скрытые члены по-прежнему являются общедоступными.

Скрытый, а также пользовательские классы появились в PowerShell 5,0.

## <a name="example"></a>ПРИМЕР

В следующем примере показано, как использовать ключевое слово Hidden в определении класса. Метод класса Car, на диске имеется свойство, которое не нужно просматривать или изменять (оно просто суммирует число раз, когда диск вызывается классом Car, метрику, которая не важна для пользователей класса; рассмотрите, например, что при покупке автомобиля вы не спросите продавца о количестве дисков, занятых автомобильом.

Поскольку пользователям класса не нужно изменять это свойство, можно скрыть свойство от Get-Member и автоматических результатов выполнения с помощью ключевого слова Hidden.

Добавьте ключевое слово Hidden, введя его в той же строке оператора, что и свойство, и его тип данных. Хотя ключевое слово может находиться в любом порядке в этой строке, запуск инструкции с ключевым словом Hidden упрощает поиск всех скрытых элементов.

```powershell
class Car
{
   # Properties
   [String] $Color
   [String] $ModelYear
   [int] $Distance

   # Method
   [int] Drive ([int]$miles)
   {
      $this.Distance += $miles
      $this.rides++
      return $this.Distance
   }

   # Hidden property of the Drive method
    hidden [int] $rides = 0
}
```

Теперь создайте новый экземпляр класса Car и сохраните его в переменной \$ тесткар.

```powershell
$TestCar = [Car]::new()
```

После создания нового экземпляра необходимо передать содержимое переменной $TestCar в командлет Get-Member. Обратите внимание, что свойство переводится не между элементами, перечисленными в результатах команды Get-Member.

```output
PS C:\Windows\system32> $TestCar | Get-Member

   TypeName: Car

Name        MemberType Definition
----        ---------- ----------
Drive       Method     int Drive(int miles)
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
ToString    Method     string ToString()
Color       Property   string Color {get;set;}
Distance    Property   int Distance {get;set;}
ModelYear   Property   string ModelYear {get;set;}

```

Теперь попробуйте запустить Get-Member еще раз, но на этот раз добавьте параметр-Force.
Обратите внимание, что результаты содержат скрытые свойства перезначений, помимо других элементов, которые по умолчанию скрыты.

```output
PS C:\Windows\system32> $TestCar | Get-Member -Force

   TypeName: Car

Name          MemberType   Definition
----          ----------   ----------
pstypenames   CodeProperty System.Collections.ObjectModel.Collection`1
psadapted     MemberSet    psadapted {Color, ModelYear, Distance,
psbase        MemberSet    psbase {Color, ModelYear, Distance,...
psextended    MemberSet    psextended {}
psobject      MemberSet    psobject {BaseObject, Members,...
Drive         Method       int Drive(int miles)
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
get_Color     Method       string get_Color()
get_Distance  Method       int get_Distance()
get_ModelYear Method       string get_ModelYear()
get_rides     Method       int get_rides()
set_Color     Method       void set_Color(string )
set_Distance  Method       void set_Distance(int )
set_ModelYear Method       void set_ModelYear(string )
set_rides     Method       void set_rides(int )
ToString      Method       string ToString()
Color         Property     string Color {get;set;}
Distance      Property     int Distance {get;set;}
ModelYear     Property     string ModelYear {get;set;}
rides         Property     int rides {get;set;}

```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Classes](about_Classes.md)

[about_Language_Keywords](about_Language_Keywords.md)

[about_Wildcards](about_Wildcards.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)


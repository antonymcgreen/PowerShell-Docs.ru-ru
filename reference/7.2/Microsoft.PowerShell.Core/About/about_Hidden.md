---
description: Описывает ключевое слово Hidden, которое скрывает члены класса от результатов по умолчанию Get-Member.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 8340a955b7cfa540baccde0da233d6d9cf0c5552
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599990"
---
# <a name="about_hidden"></a><span data-ttu-id="0d6f8-103">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="0d6f8-103">about_Hidden</span></span>

## <a name="short-description"></a><span data-ttu-id="0d6f8-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0d6f8-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0d6f8-105">Описывает ключевое слово Hidden, которое скрывает члены класса от результатов по умолчанию Get-Member.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-105">Describes the Hidden keyword, which hides class members from default Get-Member results.</span></span>

## <a name="long-description"></a><span data-ttu-id="0d6f8-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0d6f8-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="0d6f8-107">При использовании в скрипте ключевого слова Hidden члены класса скрываются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-107">When you use the Hidden keyword in a script, you hide the members of a class by default.</span></span> <span data-ttu-id="0d6f8-108">Ключевое слово Hidden может скрывать свойства, методы (включая конструкторы, события, свойства псевдонима и другие типы элементов, включая статические элементы, из результатов по умолчанию для командлета Get-Member, а также из результатов функций IntelliSense и табуляции.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-108">The Hidden keyword can hide properties, methods (including constructors, events, alias properties, and other member types, including static members, from the default results of the Get-Member cmdlet, and from IntelliSense and tab completion results.</span></span> <span data-ttu-id="0d6f8-109">Чтобы отобразить элементы, скрытые с помощью ключевого слова Hidden, добавьте параметр-Force в Get-Member команду.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-109">To display members that you have hidden with the Hidden keyword, add the -Force parameter to a Get-Member command.</span></span>

<span data-ttu-id="0d6f8-110">Скрытые члены не отображаются при нажатии клавиши TAB или IntelliSense, если завершение не происходит в классе, который определяет скрытый элемент.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-110">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="0d6f8-111">Добавлен новый атрибут System. Management. Automation. Хидденаттрибуте, поэтому \# код C может иметь ту же семантику в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-111">A new attribute, System.Management.Automation.HiddenAttribute, has been added, so that C\# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="0d6f8-112">Ключевое слово Hidden полезно для создания свойств и методов внутри класса, которые не обязательно должны видеть другие пользователи класса или могут быть доступны для редактирования.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-112">The Hidden keyword is useful for creating properties and methods within a class that you do not necessarily want other users of the class to see, or readily be able to edit.</span></span>

<span data-ttu-id="0d6f8-113">Ключевое слово Hidden не влияет на то, как можно просматривать или вносить изменения в члены класса.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-113">The Hidden keyword has no effect on how you can view or make changes to members of a class.</span></span> <span data-ttu-id="0d6f8-114">Как и все ключевые слова языка в PowerShell, скрытые элементы не учитывают регистр, а скрытые члены по-прежнему являются общедоступными.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-114">Like all language keywords in PowerShell, Hidden is not case-sensitive, and hidden members are still public.</span></span>

<span data-ttu-id="0d6f8-115">Скрытый, а также пользовательские классы появились в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-115">Hidden, along with custom classes, was introduced in PowerShell 5.0.</span></span>

## <a name="example"></a><span data-ttu-id="0d6f8-116">ПРИМЕР</span><span class="sxs-lookup"><span data-stu-id="0d6f8-116">EXAMPLE</span></span>

<span data-ttu-id="0d6f8-117">В следующем примере показано, как использовать ключевое слово Hidden в определении класса.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-117">The following example shows how to use the Hidden keyword in a class definition.</span></span> <span data-ttu-id="0d6f8-118">Метод класса Car, на диске имеется свойство, которое не нужно просматривать или изменять (оно просто суммирует число раз, когда диск вызывается классом Car, метрику, которая не важна для пользователей класса; рассмотрите, например, что при покупке автомобиля вы не спросите продавца о количестве дисков, занятых автомобильом.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-118">The Car class method, Drive, has a property, rides, that does not need to be viewed or changed (it merely tallies the number of times that Drive is called on the Car class, a metric that is not important to users of the class; consider, for example, that when you are buying a car, you do not ask the seller on how many drives the car has been taken.</span></span>

<span data-ttu-id="0d6f8-119">Поскольку пользователям класса не нужно изменять это свойство, можно скрыть свойство от Get-Member и автоматических результатов выполнения с помощью ключевого слова Hidden.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-119">Because there is little need for users of the class to change this property, we can hide the property from Get-Member and automatic completion results by using the Hidden keyword.</span></span>

<span data-ttu-id="0d6f8-120">Добавьте ключевое слово Hidden, введя его в той же строке оператора, что и свойство, и его тип данных.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-120">Add the Hidden keyword by entering it on the same statement line as the property and its data type.</span></span> <span data-ttu-id="0d6f8-121">Хотя ключевое слово может находиться в любом порядке в этой строке, запуск инструкции с ключевым словом Hidden упрощает поиск всех скрытых элементов.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-121">Although the keyword can be in any order on this line, starting the statement with the Hidden keyword makes it easier for you later to identify all members that you have hidden.</span></span>

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

<span data-ttu-id="0d6f8-122">Теперь создайте новый экземпляр класса Car и сохраните его в переменной \$ тесткар.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-122">Now, create a new instance of the Car class, and save it in a variable, \$TestCar.</span></span>

```powershell
$TestCar = [Car]::new()
```

<span data-ttu-id="0d6f8-123">После создания нового экземпляра необходимо передать содержимое переменной $TestCar в командлет Get-Member.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-123">After you create the new instance, pipe the contents of the $TestCar variable to Get-Member.</span></span> <span data-ttu-id="0d6f8-124">Обратите внимание, что свойство переводится не между элементами, перечисленными в результатах команды Get-Member.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-124">Observe that the rides property is not among the members listed in the Get-Member command results.</span></span>

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

<span data-ttu-id="0d6f8-125">Теперь попробуйте запустить Get-Member еще раз, но на этот раз добавьте параметр-Force.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-125">Now, try running Get-Member again, but this time, add the -Force parameter.</span></span>
<span data-ttu-id="0d6f8-126">Обратите внимание, что результаты содержат скрытые свойства перезначений, помимо других элементов, которые по умолчанию скрыты.</span><span class="sxs-lookup"><span data-stu-id="0d6f8-126">Note that the results contain the hidden rides property, among other members that are hidden by default.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0d6f8-127">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="0d6f8-127">SEE ALSO</span></span>

[<span data-ttu-id="0d6f8-128">about_Classes</span><span class="sxs-lookup"><span data-stu-id="0d6f8-128">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="0d6f8-129">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="0d6f8-129">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="0d6f8-130">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="0d6f8-130">about_Wildcards</span></span>](about_Wildcards.md)

[<span data-ttu-id="0d6f8-131">Get-Member</span><span class="sxs-lookup"><span data-stu-id="0d6f8-131">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)


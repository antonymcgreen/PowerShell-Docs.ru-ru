---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: eccee5ad302395116430006ed4dc0395946696b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227477"
---
# <span data-ttu-id="b1278-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="b1278-103">Update-List</span></span>

## <span data-ttu-id="b1278-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b1278-104">SYNOPSIS</span></span>
<span data-ttu-id="b1278-105">Добавляет и удаляет элементы из значении свойства, содержащего коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="b1278-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="b1278-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1278-106">SYNTAX</span></span>

### <span data-ttu-id="b1278-107">Аддремовесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b1278-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="b1278-108">Переставьте</span><span class="sxs-lookup"><span data-stu-id="b1278-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="b1278-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1278-109">DESCRIPTION</span></span>

<span data-ttu-id="b1278-110">`Update-List`Командлет добавляет, удаляет или заменяет элементы в значении свойства объекта и возвращает обновленный объект.</span><span class="sxs-lookup"><span data-stu-id="b1278-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="b1278-111">Этот командлет предназначен для работы со свойствами, которые содержат коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="b1278-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="b1278-112">Параметры **Add** и **Remove** добавляют отдельные элементы в коллекцию и удаляют их из нее.</span><span class="sxs-lookup"><span data-stu-id="b1278-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="b1278-113">Параметр **Replace** заменяет всю коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b1278-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="b1278-114">Если не указать свойство в команде, `Update-List` возвращает объект, описывающий обновление, а не обновление объекта.</span><span class="sxs-lookup"><span data-stu-id="b1278-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="b1278-115">Объект обновления можно отправить в командлеты, изменяющие объекты, такие как `Set` командлеты.</span><span class="sxs-lookup"><span data-stu-id="b1278-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="b1278-116">Этот командлет работает только в том случае, если обновляемое свойство поддерживает интерфейс **IList** , `Update-List` использующий.</span><span class="sxs-lookup"><span data-stu-id="b1278-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="b1278-117">Кроме того, все `Set` командлеты, которые принимают обновление, должны поддерживать интерфейс **IList** .</span><span class="sxs-lookup"><span data-stu-id="b1278-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="b1278-118">Основные командлеты, устанавливаемые с помощью PowerShell, не поддерживают этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b1278-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="b1278-119">Чтобы определить, поддерживает ли командлет `Update-List` , см. раздел справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="b1278-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

## <span data-ttu-id="b1278-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="b1278-120">EXAMPLES</span></span>

### <span data-ttu-id="b1278-121">Пример 1. Добавление элементов к значению свойства</span><span class="sxs-lookup"><span data-stu-id="b1278-121">Example 1: Add items to a property value</span></span>

<span data-ttu-id="b1278-122">В этом примере мы создадим класс, представляющий колоду карточек, в которой карты хранятся в виде объекта коллекции **списков** .</span><span class="sxs-lookup"><span data-stu-id="b1278-122">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="b1278-123">Метод **невдекк ()** использует `Update-List` для добавления в коллекцию **карточек** полного колоды значений карточек.</span><span class="sxs-lookup"><span data-stu-id="b1278-123">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = [char]0x2663,[char]0x2666,[char]0x2665,[char]0x2660
        $_values = 'A',2,3,4,5,6,7,8,9,10,'J','Q','K'
        $_deck = foreach ($s in $_suits){ foreach ($v in $_values){ "$v$s"} }
        $this | Update-List -Property cards -Add $_deck | Out-Null
    }

    Show() {
        Write-Host
        Write-Host $this.name ": " $this.cards[0..12]
        if ($this.cards.count -gt 13) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[13..25]
        }
        if ($this.cards.count -gt 26) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[26..38]
        }
        if ($this.cards.count -gt 39) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[39..51]
        }
    }

    Shuffle() { $this.cards = Get-Random -InputObject $this.cards -Count 52 }

    Sort() { $this.cards.Sort() }
}
```

> [!NOTE]
> <span data-ttu-id="b1278-124">`Update-List`Командлет выводит обновленный объект в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b1278-124">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="b1278-125">Мы передаем выходные данные для `Out-Null` подавления нежелательного отображения.</span><span class="sxs-lookup"><span data-stu-id="b1278-125">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="b1278-126">Пример 2. Добавление и удаление элементов свойства коллекции</span><span class="sxs-lookup"><span data-stu-id="b1278-126">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="b1278-127">Продолжая код в примере 1, мы создадим экземпляры класса **карточек** для представления колоды карт и карточек, удерживаемых двумя игроками.</span><span class="sxs-lookup"><span data-stu-id="b1278-127">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="b1278-128">Мы используем `Update-List` командлет для добавления карточек в руки игроков и для удаления карточек из колоды.</span><span class="sxs-lookup"><span data-stu-id="b1278-128">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

```powershell
$player1 = [Cards]::new('Player 1')
$player2 = [Cards]::new('Player 2')

$deck = [Cards]::new('Deck')
$deck.NewDeck()
$deck.Shuffle()
$deck.Show()

# Deal two hands
$player1 | Update-List -Property cards -Add $deck.cards[0,2,4,6,8] | Out-Null
$player2 | Update-List -Property cards -Add $deck.cards[1,3,5,7,9] | Out-Null
$deck | Update-List -Property cards -Remove $player1.cards | Out-Null
$deck | Update-List -Property cards -Remove $player2.cards | Out-Null

$player1.Show()
$player2.Show()
$deck.Show()
```

```Output
Deck :  4♦ 7♥ J♦ 5♣ A♣ 8♦ J♣ Q♥ 6♦ 3♦ 9♦ 6♣ 2♣
        K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥ Q♠
        3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠ 2♥
        6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣ 8♥

Player 1 :  4♦ J♦ A♣ J♣ 6♦

Player 2 :  7♥ 5♣ 8♦ Q♥ 3♦

Deck :  9♦ 6♣ 2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣
        Q♣ A♥ Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠
        4♣ 2♠ 2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣
        A♦ K♣ 8♥
```

<span data-ttu-id="b1278-129">В выходных данных отображается состояние колоды до того, как карты были обнаружены игроками.</span><span class="sxs-lookup"><span data-stu-id="b1278-129">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="b1278-130">Вы видите, что каждый игрок получил пять карточек из колоды.</span><span class="sxs-lookup"><span data-stu-id="b1278-130">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="b1278-131">Окончательный результат показывает состояние колоды после того, как карточки выводятся игроками.</span><span class="sxs-lookup"><span data-stu-id="b1278-131">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="b1278-132">`Update-List` использовался для выбора карточек из колоды и добавления их в коллекцию игроков.</span><span class="sxs-lookup"><span data-stu-id="b1278-132">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="b1278-133">Затем карточки игроков были удалены из колоды с помощью `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b1278-133">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="b1278-134">Пример 3. Добавление и удаление элементов в одной команде</span><span class="sxs-lookup"><span data-stu-id="b1278-134">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="b1278-135">`Update-List` позволяет использовать параметры **добавления** и **удаления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b1278-135">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="b1278-136">В этом примере игрок 1 хочет отбросить `4♦` и `6♦` получить две новые карты.</span><span class="sxs-lookup"><span data-stu-id="b1278-136">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

```powershell
# Player 1 wants two new cards - remove 2 cards & add 2 cards
$player1 | Update-List -Property cards -Remove $player1.cards[0,4] -Add $deck.cards[0..1] | Out-Null
$player1.Show()

# remove dealt cards from deck
$deck | Update-List -Property cards -Remove $deck.cards[0..1] | Out-Null
$deck.Show()
```

```Output
Player 1 :  J♦ A♣ J♣ 9♦ 6♣

Deck :  2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥
        Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠
        2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣
        8♥
```

## <span data-ttu-id="b1278-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1278-137">PARAMETERS</span></span>

### <span data-ttu-id="b1278-138">-Add</span><span class="sxs-lookup"><span data-stu-id="b1278-138">-Add</span></span>

<span data-ttu-id="b1278-139">Задает значения свойств, которые необходимо добавить в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b1278-139">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="b1278-140">Введите значения свойств в том порядке, в котором они должны располагаться в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b1278-140">Enter the values in the order that they should appear in the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1278-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b1278-141">-InputObject</span></span>

<span data-ttu-id="b1278-142">Задает объекты для обновления.</span><span class="sxs-lookup"><span data-stu-id="b1278-142">Specifies the objects to be updated.</span></span> <span data-ttu-id="b1278-143">Можно также передать по конвейеру объект для обновления `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b1278-143">You can also pipe the object to be updated to `Update-List`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1278-144">-Property</span><span class="sxs-lookup"><span data-stu-id="b1278-144">-Property</span></span>

<span data-ttu-id="b1278-145">Указывает свойство, содержащее обновляемую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b1278-145">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="b1278-146">Если опустить этот параметр, `Update-List` возвращает объект, представляющий изменение, вместо изменения объекта.</span><span class="sxs-lookup"><span data-stu-id="b1278-146">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1278-147">-Remove</span><span class="sxs-lookup"><span data-stu-id="b1278-147">-Remove</span></span>

<span data-ttu-id="b1278-148">Задает значения свойств, которые необходимо удалить из коллекции.</span><span class="sxs-lookup"><span data-stu-id="b1278-148">Specifies the property values to be removed from the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1278-149">-Replace</span><span class="sxs-lookup"><span data-stu-id="b1278-149">-Replace</span></span>

<span data-ttu-id="b1278-150">Задает новую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b1278-150">Specifies a new collection.</span></span> <span data-ttu-id="b1278-151">Этот параметр заменяет все элементы в исходной коллекции новыми элементами, которые определяются этим параметром.</span><span class="sxs-lookup"><span data-stu-id="b1278-151">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ReplaceSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1278-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b1278-152">CommonParameters</span></span>

<span data-ttu-id="b1278-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1278-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1278-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1278-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1278-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b1278-155">INPUTS</span></span>

### <span data-ttu-id="b1278-156">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b1278-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b1278-157">Объекты, которые должны быть обновлены, можно передать в конвейер `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="b1278-157">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="b1278-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b1278-158">OUTPUTS</span></span>

### <span data-ttu-id="b1278-159">Objects или System. Management. Automation. Пслистмодифиер</span><span class="sxs-lookup"><span data-stu-id="b1278-159">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="b1278-160">`Update-List` Возвращает обновленный объект или возвращает объект, представляющий действие обновления.</span><span class="sxs-lookup"><span data-stu-id="b1278-160">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="b1278-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b1278-161">NOTES</span></span>

## <span data-ttu-id="b1278-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b1278-162">RELATED LINKS</span></span>

[<span data-ttu-id="b1278-163">Format-List</span><span class="sxs-lookup"><span data-stu-id="b1278-163">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b1278-164">Select-Object</span><span class="sxs-lookup"><span data-stu-id="b1278-164">Select-Object</span></span>](Select-Object.md)

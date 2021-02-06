---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: ae473541770948dee1ce927ddee45bd806d8ff29
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600179"
---
# Update-List

## Краткий обзор
Добавляет и удаляет элементы из значении свойства, содержащего коллекцию объектов.

## SYNTAX

### Аддремовесет (по умолчанию)

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### Переставьте

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## DESCRIPTION

`Update-List`Командлет добавляет, удаляет или заменяет элементы в значении свойства объекта и возвращает обновленный объект. Этот командлет предназначен для работы со свойствами, которые содержат коллекции объектов.

Параметры **Add** и **Remove** добавляют отдельные элементы в коллекцию и удаляют их из нее.
Параметр **Replace** заменяет всю коллекцию.

Если не указать свойство в команде, `Update-List` возвращает объект, описывающий обновление, а не обновление объекта. Объект обновления можно отправить в командлеты, изменяющие объекты, такие как `Set` командлеты.

Этот командлет работает только в том случае, если обновляемое свойство поддерживает интерфейс **IList** , `Update-List` использующий. Кроме того, все `Set` командлеты, которые принимают обновление, должны поддерживать интерфейс **IList** .

Основные командлеты, устанавливаемые с помощью PowerShell, не поддерживают этот интерфейс. Чтобы определить, поддерживает ли командлет `Update-List` , см. раздел справки по командлетам.

Этот командлет был повторно введен в PowerShell 7.

## Примеры

### Пример 1. Добавление элементов к значению свойства

В этом примере мы создадим класс, представляющий колоду карточек, в которой карты хранятся в виде объекта коллекции **списков** . Метод **невдекк ()** использует `Update-List` для добавления в коллекцию **карточек** полного колоды значений карточек.

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = "`u{2663}","`u{2666}","`u{2665}","`u{2660}"
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
> `Update-List`Командлет выводит обновленный объект в конвейер. Мы передаем выходные данные для `Out-Null` подавления нежелательного отображения.

### Пример 2. Добавление и удаление элементов свойства коллекции

Продолжая код в примере 1, мы создадим экземпляры класса **карточек** для представления колоды карт и карточек, удерживаемых двумя игроками. Мы используем `Update-List` командлет для добавления карточек в руки игроков и для удаления карточек из колоды.

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

В выходных данных отображается состояние колоды до того, как карты были обнаружены игроками. Вы видите, что каждый игрок получил пять карточек из колоды. Окончательный результат показывает состояние колоды после того, как карточки выводятся игроками. `Update-List` использовался для выбора карточек из колоды и добавления их в коллекцию игроков. Затем карточки игроков были удалены из колоды с помощью `Update-List` .

### Пример 3. Добавление и удаление элементов в одной команде

`Update-List` позволяет использовать параметры **добавления** и **удаления** в одной команде. В этом примере игрок 1 хочет отбросить `4♦` и `6♦` получить две новые карты.

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

## PARAMETERS

### -Add

Задает значения свойств, которые необходимо добавить в коллекцию. Введите значения свойств в том порядке, в котором они должны располагаться в коллекции.

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

### -InputObject

Задает объекты для обновления. Можно также передать по конвейеру объект для обновления `Update-List` .

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

### -Property

Указывает свойство, содержащее обновляемую коллекцию. Если опустить этот параметр, `Update-List` возвращает объект, представляющий изменение, вместо изменения объекта.

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

### -Remove

Задает значения свойств, которые необходимо удалить из коллекции.

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

### -Replace

Задает новую коллекцию. Этот параметр заменяет все элементы в исходной коллекции новыми элементами, которые определяются этим параметром.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объекты, которые должны быть обновлены, можно передать в конвейер `Update-List` .

## Выходные данные

### Objects или System. Management. Automation. Пслистмодифиер

`Update-List` Возвращает обновленный объект или возвращает объект, представляющий действие обновления.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Format-List](Format-List.md)

[Select-Object](Select-Object.md)


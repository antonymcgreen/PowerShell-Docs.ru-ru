---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Создание графического элемента управления "Выбор даты"
description: В этой статье описывается, как создать пользовательский элемент управления в стиле календаря с помощью функций создания форм .NET Framework в Windows PowerShell.
ms.openlocfilehash: b73c9ba78817af7c38c20642402752765a7a3674
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500510"
---
# <a name="creating-a-graphical-date-picker"></a>Создание графического элемента управления "Выбор даты"

Используйте Windows PowerShell 3.0 и более поздние версии для создания формы с графическим элементом управления "Календарь", в котором пользователи могут выбрать день месяца.

## <a name="create-a-graphical-date-picker-control"></a>Создание графического элемента "Выбор даты"

Скопируйте и вставьте следующий код в интегрированную среду сценариев Windows PowerShell, а затем сохраните файл как сценарий Windows PowerShell (PS1-файл).

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}

$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)

$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

Сценарий начинается с загрузки двух классов .NET Framework: **System.Drawing** и **System.Windows.Forms** . Затем вы запускаете новый экземпляр класса .NET Framework **Windows.Forms.Form** , предоставляющий пустую форму или окно, в котором можно начать добавлять элементы управления.

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

В этом примере четырем свойствам этого класса присваиваются значения с помощью свойства **Свойство** и хэш-таблицы.

1. **StartPosition.** Если это свойство не добавлено, Windows выберет расположение после открытия формы. Если для этого свойства задать значение **CenterScreen** , форма будет автоматически отображаться в центре экрана при загрузке.

2. **Size.** Это размер формы в пикселях.
   Предыдущий сценарий создает форму шириной 243 пикселя и высотой 230 пикселей.

3. **Text.** Это будет заголовком окна.

4. **Topmost.** Задав для этого свойства значение `$true`, вы сможете принудительно открыть окно поверх других диалоговых окон.

Далее создайте и добавьте элемент управления "Календарь" в форму.
В этом примере текущий день не выделен и не обведен.
Пользователи могут выбрать в календаре не больше одного дня за раз.

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

Далее создайте кнопку **OК** для формы. Укажите размер и поведение кнопки **ОК** . В этом примере кнопка расположена на 165 пикселей ниже верхней границы формы и на 38 пикселей правее левой границы. Высота кнопки — 23 пикселя, а длина — 75 пикселей. Сценарий использует предопределенные типы Windows Forms для определения поведения кнопок.

```powershell
$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

Аналогичным образом создайте кнопку **Отмена** .
Кнопка **Отмена** расположена на 165 пикселей ниже верхней границы и на 113 пикселей правее левой границы окна.

```powershell
$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

Добавьте следующую строку кода для отображения формы в Windows.

```powershell
$result = $form.ShowDialog()
```

Наконец, код внутри блока `if` указывает Windows, что следует делать с формой, когда пользователь выберет день в календаре и нажмет кнопку **ОК** или клавишу **ВВОД** . Windows PowerShell отображает выбранную дату для пользователей.

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a>См. также:

- [GitHub: Dave Wyatt's WinFormsExampleUpdates (WinFormsExampleUpdates от Дэйва Уайята)](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [Windows PowerShell Tip of the Week: Creating a Graphical Date Picker (Совет недели для Windows PowerShell: создание графического элемента управления "Выбор даты")](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))

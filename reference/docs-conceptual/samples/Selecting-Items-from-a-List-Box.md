---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Выбор элементов из списка
ms.openlocfilehash: 048bccd403e01e2290a8930a0faba30d4c7caa73
ms.sourcegitcommit: 0a3f9945d52e963e9cba2538ffb33e42156e1395
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "77706178"
---
# <a name="selecting-items-from-a-list-box"></a>Выбор элементов из списка

Используйте Windows PowerShell 3.0 и более поздние версии для создания диалогового окна, в котором пользователи могут выбирать элементы из списка.

## <a name="create-a-list-box-control-and-select-items-from-it"></a>Создание элемента управления "Список" и выбор элементов

Скопируйте и вставьте следующий код в интегрированную среду сценариев Windows PowerShell, а затем сохраните файл как сценарий Windows PowerShell (PS1-файл).

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80

[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')

$form.Controls.Add($listBox)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

Сначала с помощью скрипта загружаются два класса .NET Framework: **System.Drawing** и **System.Windows.Forms**. Затем вы запускаете новый экземпляр класса .NET Framework **System.Windows.Forms.Form**, предоставляющий пустую форму или окно, в которые можно добавить элементы управления.

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

После создания экземпляра класса "Форма" назначьте значения для трех свойств этого класса.

- **Text.** Это будет заголовком окна.

- **Size.** Это размер формы в пикселях. Предыдущий сценарий создает форму шириной 300 пикселей и высотой 200 пикселей.

- **StartingPosition.** Для этого дополнительного свойства задается значение **CenterScreen** в предыдущем сценарии.
  Если это свойство не добавлено, Windows выберет расположение после открытия формы. Если для **StartingPosition** задать значение **CenterScreen**, форма будет автоматически отображаться в центре экрана при загрузке.

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

Далее создайте кнопку **OК** для формы. Укажите размер и поведение кнопки **ОК**. В этом примере кнопка расположена на 120 пикселей ниже верхней границы формы и на 75 пикселей правее левой границы. Высота кнопки — 23 пикселя, а длина — 75 пикселей. Сценарий использует предопределенные типы Windows Forms для определения поведения кнопок.

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

Аналогичным образом создайте кнопку **Отмена**. Кнопка **Отмена** расположена на 120 пикселей ниже верхней границы и на 150 пикселей правее левой границы окна.

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

Далее введите текст метки в окне, который должны получить пользователи. В данном случае пользователям необходимо выбрать компьютер.

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

Добавьте элемент управления (в данном случае список), который позволит пользователям указать сведения, описанные в тексте метки. Помимо списка существует много других элементов управления, которые можно применить. Их описание см. в статье [Пространство имен System.Windows.Forms](/dotnet/api/system.windows.forms) на сайте MSDN.

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

В следующем разделе необходимо указать значения списка, которые должны отображаться пользователям.

> [!NOTE]
> Список, созданный этим сценарием, позволяет выбрать только один вариант. Чтобы создать список, допускающий множественный выбор, укажите для свойства **SelectionMode** значение, аналогичное следующему: `$listBox.SelectionMode = 'MultiExtended'`. Дополнительные сведения см. в статье [Списки с множественным выбором](Multiple-selection-List-Boxes.md).

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

Добавьте список в форму и настройте его так, чтобы он открывался в Windows поверх других диалоговых окон.

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

Добавьте следующую строку кода для отображения формы в Windows.

```powershell
$result = $form.ShowDialog()
```

Наконец, код внутри блока **If** указывает Windows, что следует делать с формой после того, как пользователь выберет параметр из списка и нажмет кнопку **ОК** или клавишу **ВВОД**.

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a>См. также:

- [GitHub: Dave Wyatt's WinFormsExampleUpdates (WinFormsExampleUpdates от Дэйва Уайята)](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [Windows PowerShell Tip of the Week:  Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10)) (Совет недели для Windows PowerShell: выбор элементов из списка)

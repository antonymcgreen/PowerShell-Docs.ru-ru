---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Создание графического элемента управления "Выбор даты"
ms.openlocfilehash: d05445963b41af61a61aa29a425e638d43fb5d9d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030252"
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="70e75-103">Создание графического элемента управления "Выбор даты"</span><span class="sxs-lookup"><span data-stu-id="70e75-103">Creating a Graphical Date Picker</span></span>

<span data-ttu-id="70e75-104">Используйте Windows PowerShell 3.0 и более поздние версии для создания формы с графическим элементом управления "Календарь", в котором пользователи могут выбрать день месяца.</span><span class="sxs-lookup"><span data-stu-id="70e75-104">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="70e75-105">Создание графического элемента "Выбор даты"</span><span class="sxs-lookup"><span data-stu-id="70e75-105">Create a graphical date-picker control</span></span>

<span data-ttu-id="70e75-106">Скопируйте и вставьте следующий код в интегрированную среду сценариев Windows PowerShell, а затем сохраните файл как сценарий Windows PowerShell (PS1-файл).</span><span class="sxs-lookup"><span data-stu-id="70e75-106">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

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

$OKButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

<span data-ttu-id="70e75-107">Сначала с помощью скрипта загружаются два класса .NET Framework: **System.Drawing** и **System.Windows.Forms**.</span><span class="sxs-lookup"><span data-stu-id="70e75-107">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span>
<span data-ttu-id="70e75-108">Затем вы запускаете новый экземпляр класса .NET Framework **Windows.Forms.Form**, предоставляющий пустую форму или окно, в которые можно добавить элементы управления.</span><span class="sxs-lookup"><span data-stu-id="70e75-108">You then start a new instance of the .NET Framework class **Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

<span data-ttu-id="70e75-109">В этом примере четырем свойствам этого класса присваиваются значения с помощью свойства **Свойство** и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="70e75-109">This example assigns values to four properties of this class by using the **Property** property and hashtable.</span></span>

1. <span data-ttu-id="70e75-110">**StartPosition.** Если это свойство не добавлено, Windows выберет расположение после открытия формы.</span><span class="sxs-lookup"><span data-stu-id="70e75-110">**StartPosition**: If you don’t add this property, Windows selects a location when the form is opened.</span></span>
   <span data-ttu-id="70e75-111">Если для этого свойства задать значение **CenterScreen**, форма будет автоматически отображаться в центре экрана при загрузке.</span><span class="sxs-lookup"><span data-stu-id="70e75-111">By setting this property to **CenterScreen**, you’re automatically displaying the form in the middle of the screen each time it loads.</span></span>

2. <span data-ttu-id="70e75-112">**Size.** Это размер формы в пикселях.</span><span class="sxs-lookup"><span data-stu-id="70e75-112">**Size**: This is the size of the form, in pixels.</span></span>
   <span data-ttu-id="70e75-113">Предыдущий сценарий создает форму шириной 243 пикселей и высотой 230 пикселей.</span><span class="sxs-lookup"><span data-stu-id="70e75-113">The preceding script creates a form that’s 243 pixels wide by 230 pixels tall.</span></span>

3. <span data-ttu-id="70e75-114">**Text.** Это будет заголовком окна.</span><span class="sxs-lookup"><span data-stu-id="70e75-114">**Text**: This becomes the title of the window.</span></span>

4. <span data-ttu-id="70e75-115">**Topmost.** Задав для этого свойства значение `$true`, вы сможете принудительно открыть окно поверх других диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="70e75-115">**Topmost**: By setting this property to `$true`, you can force the window to open atop other open windows and dialog boxes.</span></span>

<span data-ttu-id="70e75-116">Далее создайте и добавьте элемент управления "Календарь" в форму.</span><span class="sxs-lookup"><span data-stu-id="70e75-116">Next, create and then add a calendar control in your form.</span></span>
<span data-ttu-id="70e75-117">В этом примере текущий день не выделен и не обведен.</span><span class="sxs-lookup"><span data-stu-id="70e75-117">In this example, the current day is not highlighted or circled.</span></span>
<span data-ttu-id="70e75-118">Пользователи могут выбрать в календаре не больше одного дня за раз.</span><span class="sxs-lookup"><span data-stu-id="70e75-118">Users can select only one day on the calendar at one time.</span></span>

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

<span data-ttu-id="70e75-119">Далее создайте кнопку **OК** для формы.</span><span class="sxs-lookup"><span data-stu-id="70e75-119">Next, create an **OK** button for your form.</span></span>
<span data-ttu-id="70e75-120">Укажите размер и поведение кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="70e75-120">Specify the size and behavior of the **OK** button.</span></span>
<span data-ttu-id="70e75-121">В этом примере кнопка расположена на 165 пикселей ниже верхней границы формы и на 38 пикселей правее левой границы.</span><span class="sxs-lookup"><span data-stu-id="70e75-121">In this example, the button position is 165 pixels from the form’s top edge, and 38 pixels from the left edge.</span></span>
<span data-ttu-id="70e75-122">Высота кнопки — 23 пикселя, а длина — 75 пикселей.</span><span class="sxs-lookup"><span data-stu-id="70e75-122">The button height is 23 pixels, while the button length is 75 pixels.</span></span>
<span data-ttu-id="70e75-123">Сценарий использует предопределенные типы Windows Forms для определения поведения кнопок.</span><span class="sxs-lookup"><span data-stu-id="70e75-123">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="70e75-124">Аналогичным образом создайте кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="70e75-124">Similarly, you create a **Cancel** button.</span></span>
<span data-ttu-id="70e75-125">Кнопка **Отмена** расположена на 165 пикселей ниже верхней границы и на 113 пикселей правее левой границы окна.</span><span class="sxs-lookup"><span data-stu-id="70e75-125">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="70e75-126">Добавьте следующую строку кода для отображения формы в Windows.</span><span class="sxs-lookup"><span data-stu-id="70e75-126">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="70e75-127">Наконец, код внутри блока `if` указывает Windows, что следует делать с формой, когда пользователь выберет день в календаре и нажмет кнопку **ОК** или клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="70e75-127">Finally, the code inside the `if` block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span>
<span data-ttu-id="70e75-128">Windows PowerShell отображает выбранную дату для пользователей.</span><span class="sxs-lookup"><span data-stu-id="70e75-128">Windows PowerShell displays the selected date to users.</span></span>

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="70e75-129">См. также</span><span class="sxs-lookup"><span data-stu-id="70e75-129">See Also</span></span>

- [<span data-ttu-id="70e75-130">Блог Hey Scripting Guy:  Why don’t these PowerShell GUI examples work? (Почему эти примеры скриптов PowerShell GUI не работают)</span><span class="sxs-lookup"><span data-stu-id="70e75-130">Hey Scripting Guy:  Why don’t these PowerShell GUI examples work?</span></span>](https://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="70e75-131">GitHub: Dave Wyatt's WinFormsExampleUpdates (WinFormsExampleUpdates от Дэйва Уайята)</span><span class="sxs-lookup"><span data-stu-id="70e75-131">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="70e75-132">[Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker](https://technet.microsoft.com/library/ff730942.aspx) (Совет недели для Windows PowerShell: создание графического элемента управления "Выбор даты")</span><span class="sxs-lookup"><span data-stu-id="70e75-132">[Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker](https://technet.microsoft.com/library/ff730942.aspx)</span></span>

---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Выбор элементов из списка
ms.openlocfilehash: 55bc9409b0e330a2080781bfd4c586109896258f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030829"
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="09f6c-103">Выбор элементов из списка</span><span class="sxs-lookup"><span data-stu-id="09f6c-103">Selecting Items from a List Box</span></span>

<span data-ttu-id="09f6c-104">Используйте Windows PowerShell 3.0 и более поздние версии для создания диалогового окна, в котором пользователи могут выбирать элементы из списка.</span><span class="sxs-lookup"><span data-stu-id="09f6c-104">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="09f6c-105">Создание элемента управления "Список" и выбор элементов</span><span class="sxs-lookup"><span data-stu-id="09f6c-105">Create a list box control, and select items from it</span></span>

<span data-ttu-id="09f6c-106">Скопируйте и вставьте следующий код в интегрированную среду сценариев Windows PowerShell, а затем сохраните файл как сценарий Windows PowerShell (PS1-файл).</span><span class="sxs-lookup"><span data-stu-id="09f6c-106">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

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

<span data-ttu-id="09f6c-107">Сначала с помощью скрипта загружаются два класса .NET Framework: **System.Drawing** и **System.Windows.Forms**.</span><span class="sxs-lookup"><span data-stu-id="09f6c-107">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="09f6c-108">Затем вы запускаете новый экземпляр класса .NET Framework **System.Windows.Forms.Form**, предоставляющий пустую форму или окно, в которые можно добавить элементы управления.</span><span class="sxs-lookup"><span data-stu-id="09f6c-108">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="09f6c-109">После создания экземпляра класса "Форма" назначьте значения для трех свойств этого класса.</span><span class="sxs-lookup"><span data-stu-id="09f6c-109">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="09f6c-110">**Text.**</span><span class="sxs-lookup"><span data-stu-id="09f6c-110">**Text.**</span></span> <span data-ttu-id="09f6c-111">Это будет заголовком окна.</span><span class="sxs-lookup"><span data-stu-id="09f6c-111">This becomes the title of the window.</span></span>

- <span data-ttu-id="09f6c-112">**Size.**</span><span class="sxs-lookup"><span data-stu-id="09f6c-112">**Size.**</span></span> <span data-ttu-id="09f6c-113">Это размер формы в пикселях.</span><span class="sxs-lookup"><span data-stu-id="09f6c-113">This is the size of the form, in pixels.</span></span> <span data-ttu-id="09f6c-114">Предыдущий сценарий создает форму шириной 300 пикселей и высотой 200 пикселей.</span><span class="sxs-lookup"><span data-stu-id="09f6c-114">The preceding script creates a form that’s 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="09f6c-115">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="09f6c-115">**StartingPosition.**</span></span> <span data-ttu-id="09f6c-116">Для этого дополнительного свойства задается значение **CenterScreen** в предыдущем сценарии.</span><span class="sxs-lookup"><span data-stu-id="09f6c-116">This optional property is set to **CenterScreen** in the preceding script.</span></span> <span data-ttu-id="09f6c-117">Если это свойство не добавлено, Windows выберет расположение после открытия формы.</span><span class="sxs-lookup"><span data-stu-id="09f6c-117">If you don’t add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="09f6c-118">Если для **StartingPosition** задать значение **CenterScreen**, форма будет автоматически отображаться в центре экрана при загрузке.</span><span class="sxs-lookup"><span data-stu-id="09f6c-118">By setting the **StartingPosition** to **CenterScreen**, you’re automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="09f6c-119">Далее создайте кнопку **OК** для формы.</span><span class="sxs-lookup"><span data-stu-id="09f6c-119">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="09f6c-120">Укажите размер и поведение кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09f6c-120">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="09f6c-121">В этом примере кнопка расположена на 120 пикселей ниже верхней границы формы и на 75 пикселей правее левой границы.</span><span class="sxs-lookup"><span data-stu-id="09f6c-121">In this example, the button position is 120 pixels from the form’s top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="09f6c-122">Высота кнопки — 23 пикселя, а длина — 75 пикселей.</span><span class="sxs-lookup"><span data-stu-id="09f6c-122">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="09f6c-123">Сценарий использует предопределенные типы Windows Forms для определения поведения кнопок.</span><span class="sxs-lookup"><span data-stu-id="09f6c-123">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="09f6c-124">Аналогичным образом создайте кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="09f6c-124">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="09f6c-125">Кнопка **Отмена** расположена на 120 пикселей ниже верхней границы и на 150 пикселей правее левой границы окна.</span><span class="sxs-lookup"><span data-stu-id="09f6c-125">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="09f6c-126">Далее введите текст метки в окне, который должны получить пользователи.</span><span class="sxs-lookup"><span data-stu-id="09f6c-126">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="09f6c-127">В данном случае пользователям необходимо выбрать компьютер.</span><span class="sxs-lookup"><span data-stu-id="09f6c-127">In this case, you want users to select a computer.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

<span data-ttu-id="09f6c-128">Добавьте элемент управления (в данном случае список), который позволит пользователям указать сведения, описанные в тексте метки.</span><span class="sxs-lookup"><span data-stu-id="09f6c-128">Add the control (in this case, a list box) that lets users provide the information you’ve described in your label text.</span></span> <span data-ttu-id="09f6c-129">Помимо списка существует много других элементов управления, которые можно применить. Их описание см. в статье [Пространство имен System.Windows.Forms](https://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx) на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="09f6c-129">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](https://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx) on MSDN.</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

<span data-ttu-id="09f6c-130">В следующем разделе необходимо указать значения списка, которые должны отображаться пользователям.</span><span class="sxs-lookup"><span data-stu-id="09f6c-130">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="09f6c-131">Список, созданный этим сценарием, позволяет выбрать только один вариант.</span><span class="sxs-lookup"><span data-stu-id="09f6c-131">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="09f6c-132">Чтобы создать список, допускающий множественный выбор, укажите значение для свойства **SelectionMode**, аналогичное следующему: `$listBox.SelectionMode = 'MultiExtended'`.</span><span class="sxs-lookup"><span data-stu-id="09f6c-132">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following:  `$listBox.SelectionMode = 'MultiExtended'`.</span></span> <span data-ttu-id="09f6c-133">Дополнительные сведения см. в статье [Списки с множественным выбором](Multiple-selection-List-Boxes.md).</span><span class="sxs-lookup"><span data-stu-id="09f6c-133">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

<span data-ttu-id="09f6c-134">Добавьте список в форму и настройте его так, чтобы он открывался в Windows поверх других диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="09f6c-134">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it’s opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="09f6c-135">Добавьте следующую строку кода для отображения формы в Windows.</span><span class="sxs-lookup"><span data-stu-id="09f6c-135">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="09f6c-136">Наконец, код внутри блока **If** указывает Windows, что следует делать с формой после того, как пользователь выберет параметр из списка и нажмет кнопку **ОК** или клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="09f6c-136">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="09f6c-137">См. также</span><span class="sxs-lookup"><span data-stu-id="09f6c-137">See Also</span></span>

- [<span data-ttu-id="09f6c-138">Блог Hey Scripting Guy:  Why don’t these PowerShell GUI examples work? (Почему эти примеры скриптов PowerShell GUI не работают)</span><span class="sxs-lookup"><span data-stu-id="09f6c-138">Hey Scripting Guy:  Why don’t these PowerShell GUI examples work?</span></span>](https://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="09f6c-139">GitHub: Dave Wyatt's WinFormsExampleUpdates (WinFormsExampleUpdates от Дэйва Уайята)</span><span class="sxs-lookup"><span data-stu-id="09f6c-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="09f6c-140">[Windows PowerShell Tip of the Week:  Selecting Items from a List Box](https://technet.microsoft.com/library/ff730949.aspx) (Совет недели для Windows PowerShell: выбор элементов из списка)</span><span class="sxs-lookup"><span data-stu-id="09f6c-140">[Windows PowerShell Tip of the Week:  Selecting Items from a List Box](https://technet.microsoft.com/library/ff730949.aspx)</span></span>

---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Списки с множественным выбором
description: В этой статье описывается, как создать элемент управления "Список с множественным выбором" с помощью функций создания форм .NET Framework в Windows PowerShell.
ms.openlocfilehash: 2724188695f054d1115b385987cda8a578c102de
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391533"
---
# <a name="multiple-selection-list-boxes"></a><span data-ttu-id="6d0dd-104">Списки с множественным выбором</span><span class="sxs-lookup"><span data-stu-id="6d0dd-104">Multiple-selection List Boxes</span></span>

<span data-ttu-id="6d0dd-105">Используйте Windows PowerShell 3.0 и более поздние версии для создания списка с множественным выбором в настраиваемой форме Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-105">Use Windows PowerShell 3.0 and later releases to create a multiple-selection list box control in a custom Windows Form.</span></span>

## <a name="create-list-box-controls-that-allow-multiple-selections"></a><span data-ttu-id="6d0dd-106">Создание списков, допускающих множественный выбор</span><span class="sxs-lookup"><span data-stu-id="6d0dd-106">Create list box controls that allow multiple selections</span></span>

<span data-ttu-id="6d0dd-107">Скопируйте и вставьте следующий код в интегрированную среду сценариев Windows PowerShell, а затем сохраните файл как сценарий Windows PowerShell (PS1-файл).</span><span class="sxs-lookup"><span data-stu-id="6d0dd-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
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
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)

$listBox.SelectionMode = 'MultiExtended'

[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')

$listBox.Height = 70
$form.Controls.Add($listBox)
$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

<span data-ttu-id="6d0dd-108">Сценарий начинается с загрузки двух классов .NET Framework: **System.Drawing** и **System.Windows.Forms**.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="6d0dd-109">Затем вы запускаете новый экземпляр класса .NET Framework **System.Windows.Forms.Form**, предоставляющий пустую форму или окно, в которые можно добавить элементы управления.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="6d0dd-110">После создания экземпляра класса "Форма" назначьте значения для трех свойств этого класса.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="6d0dd-111">**Text.**</span><span class="sxs-lookup"><span data-stu-id="6d0dd-111">**Text.**</span></span> <span data-ttu-id="6d0dd-112">Это будет заголовком окна.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="6d0dd-113">**Size.**</span><span class="sxs-lookup"><span data-stu-id="6d0dd-113">**Size.**</span></span> <span data-ttu-id="6d0dd-114">Это размер формы в пикселях.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="6d0dd-115">Предыдущий сценарий создает форму шириной 300 пикселей и высотой 200 пикселей.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="6d0dd-116">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="6d0dd-116">**StartingPosition.**</span></span> <span data-ttu-id="6d0dd-117">Для этого дополнительного свойства задается значение **CenterScreen** в предыдущем сценарии.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="6d0dd-118">Если это свойство не добавлено, Windows выберет расположение после открытия формы.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="6d0dd-119">Если для **StartingPosition** задать значение **CenterScreen**, форма будет автоматически отображаться в центре экрана при загрузке.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="6d0dd-120">Далее создайте кнопку **OК** для формы.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="6d0dd-121">Укажите размер и поведение кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="6d0dd-122">В этом примере кнопка расположена на 120 пикселей ниже верхней границы формы и на 75 пикселей правее левой границы.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="6d0dd-123">Высота кнопки — 23 пикселя, а длина — 75 пикселей.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="6d0dd-124">Сценарий использует предопределенные типы Windows Forms для определения поведения кнопок.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Size(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="6d0dd-125">Аналогичным образом создайте кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="6d0dd-126">Кнопка **Отмена** расположена на 120 пикселей ниже верхней границы и на 150 пикселей правее левой границы окна.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="6d0dd-127">Далее введите текст метки в окне, который должны получить пользователи.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)
```

<span data-ttu-id="6d0dd-128">Добавьте элемент управления (в данном случае список), который позволит пользователям указать сведения, описанные в тексте метки.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-128">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="6d0dd-129">Помимо текстового поля существует много других элементов управления, которые можно применить. Их описание см. в статье [Пространство имен System.Windows.Forms](/dotnet/api/system.windows.forms).</span><span class="sxs-lookup"><span data-stu-id="6d0dd-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
```

<span data-ttu-id="6d0dd-130">Далее показано, как указать, что вы разрешаете пользователям выбрать несколько значений в списке.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-130">Here's how you specify that you want to allow users to select multiple values from the list.</span></span>

```powershell
$listBox.SelectionMode = 'MultiExtended'
```

<span data-ttu-id="6d0dd-131">В следующем разделе необходимо указать значения списка, которые должны отображаться пользователям.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-131">In the next section, you specify the values you want the list box to display to users.</span></span>

```powershell
[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')
```

<span data-ttu-id="6d0dd-132">Укажите максимальную высоту элемента управления "список".</span><span class="sxs-lookup"><span data-stu-id="6d0dd-132">Specify the maximum height of the list box control.</span></span>

```powershell
$listBox.Height = 70
```

<span data-ttu-id="6d0dd-133">Добавьте список в форму и настройте его так, чтобы он открывался в Windows поверх других диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-133">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="6d0dd-134">Добавьте следующую строку кода для отображения формы в Windows.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-134">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="6d0dd-135">Наконец, код внутри блока **If** указывает Windows, что следует делать с формой после того, как пользователь выберет параметр из списка и нажмет кнопку **ОК** или клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="6d0dd-135">Finally, the code inside the **If** block instructs Windows what to do with the form after users select one or more options from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="6d0dd-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d0dd-136">See Also</span></span>

- [<span data-ttu-id="6d0dd-137">Weekend Scripter: примеры исправления графического пользовательского интерфейса PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d0dd-137">Weekend Scripter: Fixing PowerShell GUI Examples</span></span>](https://devblogs.microsoft.com/scripting/weekend-scripter-fixing-powershell-gui-examples/)
- [<span data-ttu-id="6d0dd-138">GitHub: Dave Wyatt's WinFormsExampleUpdates (WinFormsExampleUpdates от Дэйва Уайята)</span><span class="sxs-lookup"><span data-stu-id="6d0dd-138">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="6d0dd-139">[Windows PowerShell Tip of the Week: Multi-Select List Boxes – And More!](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730950(v=technet.10)) (Совет недели по Windows PowerShell: списки с множественным выбором и многое другое)</span><span class="sxs-lookup"><span data-stu-id="6d0dd-139">[Windows PowerShell Tip of the Week: Multi-Select List Boxes - And More!](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730950(v=technet.10))</span></span>

---
ms.date: 06/05/2017
title: Объект ISEAddOnTool
description: Объект ISEAddonTool — это устанавливаемая надстройка, расширяющая функциональные возможности интегрированной среды сценариев Windows PowerShell.
ms.openlocfilehash: cc2d50881b7d0033e08de9af5d4cc9e1a9aa55db
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667136"
---
# <a name="the-iseaddontool-object"></a><span data-ttu-id="74b04-103">Объект ISEAddOnTool</span><span class="sxs-lookup"><span data-stu-id="74b04-103">The ISEAddOnTool Object</span></span>

<span data-ttu-id="74b04-104">Объект **ISEAddonTool**  — это устанавливаемая надстройка, расширяющая функциональные возможности интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74b04-104">An **ISEAddonTool** object represents an installed add-on tool that provides additional functionality to Windows PowerShell ISE.</span></span> <span data-ttu-id="74b04-105">В качестве примера можно привести средство **Commands** , которое отображается, если выбрать **Вид** , а затем **Show Command Add-on** (Показать настройку Command).</span><span class="sxs-lookup"><span data-stu-id="74b04-105">An example is the **Commands** tool that you can display by clicking **View** , then **Show Command Add-on**.</span></span> <span data-ttu-id="74b04-106">После этого средство становится доступным за счет манипуляций с различными доступными объектами **ISEAddOnTool**.</span><span class="sxs-lookup"><span data-stu-id="74b04-106">This tool is then accessible to you by manipulating the various available **ISEAddOnTool** objects.</span></span>

<span data-ttu-id="74b04-107">Каждую надстройку можно связать с вертикальной или горизонтальной панелью.</span><span class="sxs-lookup"><span data-stu-id="74b04-107">Each add-on tool can be associated with either the vertical pane or the horizontal pane.</span></span> <span data-ttu-id="74b04-108">Вертикальная область прикрепляется к правому краю интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74b04-108">The vertical pane is docked to the right edge of Windows PowerShell ISE.</span></span> <span data-ttu-id="74b04-109">Горизонтальная панель прикрепляется к нижнему краю.</span><span class="sxs-lookup"><span data-stu-id="74b04-109">The horizontal pane is docked to the bottom edge.</span></span>

<span data-ttu-id="74b04-110">Каждая вкладка PowerShell в интегрированной среде сценариев Windows PowerShell может содержать собственный набор установленных надстроек.</span><span class="sxs-lookup"><span data-stu-id="74b04-110">Each PowerShell tab in Windows PowerShell ISE can have its own set of add-on tools installed.</span></span> <span data-ttu-id="74b04-111">Доступ к коллекции средств, доступных для выбранной вкладки, или к свойствам одного из объектов **PowerShellTab** в объекте коллекции [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) рассматривается в статьях [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) и [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md).</span><span class="sxs-lookup"><span data-stu-id="74b04-111">See [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) and [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md) to access the collection of tools available to the currently selected tab or the same properties on any of the **PowerShellTab** objects in the [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) collection object.</span></span>

## <a name="methods"></a><span data-ttu-id="74b04-112">Методы</span><span class="sxs-lookup"><span data-stu-id="74b04-112">Methods</span></span>

<span data-ttu-id="74b04-113">Для объектов этого класса нет доступных методов интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74b04-113">There are no Windows PowerShell ISE-specific methods available for objects of this class.</span></span>

## <a name="properties"></a><span data-ttu-id="74b04-114">Свойства</span><span class="sxs-lookup"><span data-stu-id="74b04-114">Properties</span></span>

### <a name="control"></a><span data-ttu-id="74b04-115">Control</span><span class="sxs-lookup"><span data-stu-id="74b04-115">Control</span></span>

<span data-ttu-id="74b04-116">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="74b04-116">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="74b04-117">Свойство **Control** обеспечивает доступ для чтения ко множеству сведений надстройки Command.</span><span class="sxs-lookup"><span data-stu-id="74b04-117">The **Control** property provides read access to many of the details of the Commands add-on tool.</span></span>

```powershell
# View the properties of the Commands add-on tool.
# (assumes that it is visible in the vertical pane)
$psISE.CurrentVisibleVerticalTool.Control
```

```Output
HostObject                  : Microsoft.PowerShell.Host.ISE.ObjectModelRoot
Content                     :
HasContent                  :
ContentTemplate             :
ContentTemplateSelector     :
ContentStringFormat         :
BorderBrush                 :
BorderThickness             :
Background                  :
Foreground                  :
FontFamily                  :
FontSize                    :
FontStretch                 :
FontStyle                   :
FontWeight                  :
HorizontalContentAlignment  :
VerticalContentAlignment    :
TabIndex                    :
IsTabStop                   :
Padding                     :
Template                    : System.Windows.Controls.ControlTemplate
Style                       :
OverridesDefaultStyle       :
UseLayoutRounding           :
Triggers                    : {}
TemplatedParent             :
Resources                   : {System.Windows.Controls.TabItem}
DataContext                 :
BindingGroup                :
Language                    :
Name                        :
Tag                         :
InputScope                  :
ActualWidth                 : 370.75
ActualHeight                : 676.559097412109
LayoutTransform             :
Width                       :
MinWidth                    :
MaxWidth                    :
Height                      :
MinHeight                   :
MaxHeight                   :
FlowDirection               : LeftToRight
Margin                      :
HorizontalAlignment         :
VerticalAlignment           :
FocusVisualStyle            :
Cursor                      :
ForceCursor                 :
IsInitialized               : True
IsLoaded                    :
ToolTip                     :
ContextMenu                 :
Parent                      :
HasAnimatedProperties       :
InputBindings               :
CommandBindings             :
AllowDrop                   :
DesiredSize                 : 227.66,676.559097412109
IsMeasureValid              : True
IsArrangeValid              : True
RenderSize                  : 370.75,676.559097412109
RenderTransform             :
RenderTransformOrigin       :
IsMouseDirectlyOver         : False
IsMouseOver                 : False
IsStylusOver                : False
IsKeyboardFocusWithin       : False
IsMouseCaptured             :
IsMouseCaptureWithin        : False
IsStylusDirectlyOver        : False
IsStylusCaptured            :
IsStylusCaptureWithin       : False
IsKeyboardFocused           : False
IsInputMethodEnabled        :
Opacity                     :
OpacityMask                 :
BitmapEffect                :
Effect                      :
BitmapEffectInput           :
CacheMode                   :
Uid                         :
Visibility                  : Visible
ClipToBounds                : False
Clip                        :
SnapsToDevicePixels         : False
IsFocused                   :
IsEnabled                   :
IsHitTestVisible            :
IsVisible                   : True
Focusable                   :
PersistId                   : 1
IsManipulationEnabled       :
AreAnyTouchesOver           : False
AreAnyTouchesDirectlyOver   :
AreAnyTouchesCapturedWithin : False
AreAnyTouchesCaptured       :
TouchesCaptured             : {}
TouchesCapturedWithin       : {}
TouchesOver                 : {}
TouchesDirectlyOver         : {}
DependencyObjectType        : System.Windows.DependencyObjectType
IsSealed                    : False
Dispatcher                  : System.Windows.Threading.Dispatcher
```

### <a name="isvisible"></a><span data-ttu-id="74b04-118">IsVisible</span><span class="sxs-lookup"><span data-stu-id="74b04-118">IsVisible</span></span>

<span data-ttu-id="74b04-119">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="74b04-119">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="74b04-120">Логическое свойство, которое определяет видимость надстройки в соответствующей области.</span><span class="sxs-lookup"><span data-stu-id="74b04-120">The Boolean property that indicates whether the add-on tool is currently visible in its assigned pane.</span></span> <span data-ttu-id="74b04-121">Если она видна, свойству **IsVisible** можно присвоить значение `$false`, чтобы скрыть средство, или **IsVisible** `$true`, чтобы средство отображалось на вкладке PowerShell. Обратите внимание, что к скрытой надстройке нельзя получить доступ с помощью объекта **CurrentVisibleHorizontalTool** или **CurrentVisibleVerticalTool** , а значит, ее нельзя сделать видимой, используя данное свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="74b04-121">If it is visible, you can set the **IsVisible** property to `$false` to hide the tool, or set the **IsVisible** property to `$true` to make an add-on tool visible on its PowerShell tab. Note that after an add-on tool is hidden, it is no longer accessible through the **CurrentVisibleHorizontalTool** or **CurrentVisibleVerticalTool** objects, and therefore cannot be made visible by using this property on that object.</span></span>

```powershell
# Hide the current tool in the vertical tool pane
$psISE.CurrentVisibleVerticalTool.IsVisible = $false
# Show the first tool on the currently selected PowerShell tab
$psISE.CurrentPowerShellTab.VerticalAddOnTools[0].IsVisible = $true
```

### <a name="name"></a><span data-ttu-id="74b04-122">Имя</span><span class="sxs-lookup"><span data-stu-id="74b04-122">Name</span></span>

<span data-ttu-id="74b04-123">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="74b04-123">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="74b04-124">Свойство только для чтения, которое получает имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="74b04-124">The read-only property that gets the name of the add-on tool.</span></span>

```powershell
# Gets the name of the visible vertical pane add-on tool.
$psISE.CurrentVisibleVerticalTool.Name
```

```Output
Commands
```

## <a name="see-also"></a><span data-ttu-id="74b04-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="74b04-125">See Also</span></span>

- [<span data-ttu-id="74b04-126">Объект ISEAddOnToolCollection</span><span class="sxs-lookup"><span data-stu-id="74b04-126">The ISEAddOnToolCollection Object</span></span>](The-ISEAddOnToolCollection-Object.md)
- [<span data-ttu-id="74b04-127">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74b04-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="74b04-128">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="74b04-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

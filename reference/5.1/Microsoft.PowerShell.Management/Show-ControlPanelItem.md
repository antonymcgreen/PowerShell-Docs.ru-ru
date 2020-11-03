---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227866"
---
# <span data-ttu-id="a15f1-103">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a15f1-103">Show-ControlPanelItem</span></span>

## <span data-ttu-id="a15f1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a15f1-104">SYNOPSIS</span></span>
<span data-ttu-id="a15f1-105">Открывает элементы панели управления.</span><span class="sxs-lookup"><span data-stu-id="a15f1-105">Opens control panel items.</span></span>

## <span data-ttu-id="a15f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a15f1-106">SYNTAX</span></span>

### <span data-ttu-id="a15f1-107">Регуларнаме (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a15f1-107">RegularName (Default)</span></span>

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="a15f1-108">каноникалнаме</span><span class="sxs-lookup"><span data-stu-id="a15f1-108">CanonicalName</span></span>

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="a15f1-109">ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a15f1-109">ControlPanelItem</span></span>

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## <span data-ttu-id="a15f1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a15f1-110">DESCRIPTION</span></span>

<span data-ttu-id="a15f1-111">`Show-ControlPanelItem`Командлет открывает элементы панели управления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a15f1-111">The `Show-ControlPanelItem` cmdlet opens control panel items on the local computer.</span></span> <span data-ttu-id="a15f1-112">Его можно использовать для открытия элементов панели управления по имени, категории или описанию даже в системах без пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a15f1-112">You can use it to open control panel items by name, category, or description, even on systems that do not have a user interface.</span></span> <span data-ttu-id="a15f1-113">Элементы панели управления можно передать из `Get-ControlPanelItem` командлета в `Show-ControlPanelItem` .</span><span class="sxs-lookup"><span data-stu-id="a15f1-113">You can pipe control panel items from the `Get-ControlPanelItem` cmdlet to `Show-ControlPanelItem`.</span></span>

<span data-ttu-id="a15f1-114">`Show-ControlPanelItem` выполняет поиск только элементов панели управления, которые могут быть открыты в системе.</span><span class="sxs-lookup"><span data-stu-id="a15f1-114">`Show-ControlPanelItem` searches only control panel items that can be opened on the system.</span></span> <span data-ttu-id="a15f1-115">На компьютерах, на которых не установлена **Панель управления** или **проводник** , `Show-ControlPanelItem` выполняет поиск только элементов панели управления, которые могут открываться без этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="a15f1-115">On computers that do not have **Control Panel** or **File Explorer** , `Show-ControlPanelItem` searches only control panel items that can open without these components.</span></span>

<span data-ttu-id="a15f1-116">Этот командлет появился в Windows PowerShell 3,0 и работает в Windows 8, Windows Server 2012 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="a15f1-116">This cmdlet was introduced in Windows PowerShell 3.0 and works on Windows 8, Windows Server 2012, and higher versions.</span></span>

## <span data-ttu-id="a15f1-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="a15f1-117">EXAMPLES</span></span>

### <span data-ttu-id="a15f1-118">Пример 1. Отображение элемента панели управления</span><span class="sxs-lookup"><span data-stu-id="a15f1-118">Example 1: Show a control panel item</span></span>

<span data-ttu-id="a15f1-119">В этом примере запускается элемент панели управления **Автозапуск** .</span><span class="sxs-lookup"><span data-stu-id="a15f1-119">This example launches the **AutoPlay** control panel item.</span></span>

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### <span data-ttu-id="a15f1-120">Пример 2. Передача элемента панели управления по конвейеру в этот командлет</span><span class="sxs-lookup"><span data-stu-id="a15f1-120">Example 2: Pipe a control panel item to this cmdlet</span></span>

<span data-ttu-id="a15f1-121">В этом примере открывается элемент панели управления **брандмауэром защитника Windows** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a15f1-121">This example opens the **Windows Defender Firewall** control panel item on the local computer.</span></span>
<span data-ttu-id="a15f1-122">Имя элемента панели управления брандмауэра Windows изменилось по сравнению с версиями Windows.</span><span class="sxs-lookup"><span data-stu-id="a15f1-122">The name of the Windows Firewall control panel item has changed over the versions of Windows.</span></span> <span data-ttu-id="a15f1-123">В этом примере для поиска элемента панели управления используется шаблон с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="a15f1-123">This example uses a wildcard pattern to find the control panel item.</span></span>

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="a15f1-124">`Get-ControlPanelItem` Возвращает элемент панели управления, и `Show-ControlPanelItem` командлет открывает его.</span><span class="sxs-lookup"><span data-stu-id="a15f1-124">`Get-ControlPanelItem` gets the control panel item and the `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="a15f1-125">Пример 3. Использование имени файла для открытия элемента панели управления</span><span class="sxs-lookup"><span data-stu-id="a15f1-125">Example 3: Use a file name to open a control panel item</span></span>

<span data-ttu-id="a15f1-126">В этом примере элемент панели управления **программы и компоненты** открывается с использованием имени приложения.</span><span class="sxs-lookup"><span data-stu-id="a15f1-126">This example opens the **Programs and Features** control panel item by using its application name.</span></span>

```powershell
appwiz.cpl
```

<span data-ttu-id="a15f1-127">Этот метод является альтернативой использованию `Show-ControlPanelItem` команды.</span><span class="sxs-lookup"><span data-stu-id="a15f1-127">This method is an alternative to using a `Show-ControlPanelItem` command.</span></span>

> [!NOTE]
> <span data-ttu-id="a15f1-128">В PowerShell можно опустить расширение файла. cpl для файлов панели управления, так как оно включается в значение `$env:PathExt` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="a15f1-128">In PowerShell, you can omit the .cpl file extension for control panel files because it's included in the value of the `$env:PathExt` environment variable.</span></span>

## <span data-ttu-id="a15f1-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a15f1-129">PARAMETERS</span></span>

### <span data-ttu-id="a15f1-130">-Каноникалнаме</span><span class="sxs-lookup"><span data-stu-id="a15f1-130">-CanonicalName</span></span>

<span data-ttu-id="a15f1-131">Задает элементы панели управления с использованием указанных канонических имен или шаблонов имен.</span><span class="sxs-lookup"><span data-stu-id="a15f1-131">Specifies control panel items by using the specified canonical names or name patterns.</span></span> <span data-ttu-id="a15f1-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a15f1-132">Wildcard characters are permitted.</span></span> <span data-ttu-id="a15f1-133">При вводе нескольких имен этот командлет открывает элементы панели управления, соответствующие любому из имен, как если бы элементы списка имен были разделены оператором **или** .</span><span class="sxs-lookup"><span data-stu-id="a15f1-133">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a15f1-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a15f1-134">-InputObject</span></span>

<span data-ttu-id="a15f1-135">Указывает элементы панели управления, открываемые при отправке объектов элементов панели управления.</span><span class="sxs-lookup"><span data-stu-id="a15f1-135">Specifies control panel items to open by submitting control panel item objects.</span></span> <span data-ttu-id="a15f1-136">Введите переменную, содержащую объекты элементов панели управления, или введите команду или выражение, которое получает объекты элементов панели управления, такие как `Get-ControlPanelItem` .</span><span class="sxs-lookup"><span data-stu-id="a15f1-136">Enter a variable that contains control panel item objects, or type a command or expression that gets control panel item objects, such as `Get-ControlPanelItem`.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a15f1-137">-Name</span><span class="sxs-lookup"><span data-stu-id="a15f1-137">-Name</span></span>

<span data-ttu-id="a15f1-138">Указывает имена элементов панели управления.</span><span class="sxs-lookup"><span data-stu-id="a15f1-138">Specifies names of control panel items.</span></span> <span data-ttu-id="a15f1-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a15f1-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="a15f1-140">При вводе нескольких имен этот командлет открывает элементы панели управления, соответствующие любому из имен, как если бы элементы списка имен были разделены оператором **или** .</span><span class="sxs-lookup"><span data-stu-id="a15f1-140">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a15f1-141">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a15f1-141">CommonParameters</span></span>

<span data-ttu-id="a15f1-142">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a15f1-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a15f1-143">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a15f1-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a15f1-144">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a15f1-144">INPUTS</span></span>

### <span data-ttu-id="a15f1-145">System. String, Microsoft. PowerShell. Commands. ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a15f1-145">System.String, Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="a15f1-146">К этому командлету можно передать объект имени или элемента панели управления.</span><span class="sxs-lookup"><span data-stu-id="a15f1-146">You can pipe a name or control panel item object to this cmdlet.</span></span>

## <span data-ttu-id="a15f1-147">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a15f1-147">OUTPUTS</span></span>

### <span data-ttu-id="a15f1-148">Нет</span><span class="sxs-lookup"><span data-stu-id="a15f1-148">None</span></span>

<span data-ttu-id="a15f1-149">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a15f1-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="a15f1-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a15f1-150">NOTES</span></span>

## <span data-ttu-id="a15f1-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a15f1-151">RELATED LINKS</span></span>

[<span data-ttu-id="a15f1-152">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a15f1-152">Get-ControlPanelItem</span></span>](Get-ControlPanelItem.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228402"
---
# <span data-ttu-id="06cb4-103">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="06cb4-103">Get-ControlPanelItem</span></span>

## <span data-ttu-id="06cb4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06cb4-104">SYNOPSIS</span></span>
<span data-ttu-id="06cb4-105">Получает элементы панели управления.</span><span class="sxs-lookup"><span data-stu-id="06cb4-105">Gets control panel items.</span></span>

## <span data-ttu-id="06cb4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06cb4-106">SYNTAX</span></span>

### <span data-ttu-id="06cb4-107">Регуларнаме (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06cb4-107">RegularName (Default)</span></span>

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="06cb4-108">каноникалнаме</span><span class="sxs-lookup"><span data-stu-id="06cb4-108">CanonicalName</span></span>

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="06cb4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06cb4-109">DESCRIPTION</span></span>

<span data-ttu-id="06cb4-110">`Get-ControlPanelItem`Командлет возвращает элементы панели управления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06cb4-110">The `Get-ControlPanelItem` cmdlet gets control panel items on the local computer.</span></span> <span data-ttu-id="06cb4-111">С его помощью можно находить элементы панели управления по имени, категории или описанию даже в системах, в которых нет пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="06cb4-111">You can use it to find control panel items by name, category, or description, even on systems that do not have a user interface.</span></span>

<span data-ttu-id="06cb4-112">Этот командлет возвращает только элементы панели управления, которые могут быть открыты в системе.</span><span class="sxs-lookup"><span data-stu-id="06cb4-112">This cmdlet gets only the control panel items that can be opened on the system.</span></span> <span data-ttu-id="06cb4-113">На компьютерах, на которых нет панели управления или проводника, этот командлет получает только элементы панели управления, которые могут открываться без этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="06cb4-113">On computers that do not have Control Panel or File Explorer, this cmdlet gets only control panel items that can open without these components.</span></span>

<span data-ttu-id="06cb4-114">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="06cb4-114">This cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="06cb4-115">Он работает только в Windows 8 и Windows Server 2012 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="06cb4-115">It works only on Windows 8 and Windows Server 2012 and newer.</span></span>

## <span data-ttu-id="06cb4-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="06cb4-116">EXAMPLES</span></span>

### <span data-ttu-id="06cb4-117">Пример 1. получение всех элементов панели управления</span><span class="sxs-lookup"><span data-stu-id="06cb4-117">Example 1: Get all control panel items</span></span>

<span data-ttu-id="06cb4-118">Эта команда возвращает все элементы панели управления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06cb4-118">This command gets all control panel items on the local computer.</span></span>

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### <span data-ttu-id="06cb4-119">Пример 2. Получение элементов панели управления по имени</span><span class="sxs-lookup"><span data-stu-id="06cb4-119">Example 2: Get control panel items by name</span></span>

<span data-ttu-id="06cb4-120">Этот пример возвращает элементы панели управления, в именах которых есть программа или приложение.</span><span class="sxs-lookup"><span data-stu-id="06cb4-120">This example gets control panel items that have Program or App in their names.</span></span>

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### <span data-ttu-id="06cb4-121">Пример 3. Получение элементов панели управления по категориям</span><span class="sxs-lookup"><span data-stu-id="06cb4-121">Example 3: Get control panel items by category</span></span>

<span data-ttu-id="06cb4-122">Эта команда возвращает все элементы панели управления в категориях, в именах которых есть безопасность.</span><span class="sxs-lookup"><span data-stu-id="06cb4-122">This command gets all control panel items in categories that have Security in their names.</span></span>

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### <span data-ttu-id="06cb4-123">Пример 4. Открытие элемента панели управления</span><span class="sxs-lookup"><span data-stu-id="06cb4-123">Example 4: Open a control panel item</span></span>

<span data-ttu-id="06cb4-124">В этом примере открывается элемент панели управления Брандмауэр Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06cb4-124">This example opens the Windows Firewall control panel item on the local computer.</span></span>

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="06cb4-125">`Get-ControlPanelItem`Командлет возвращает элемент панели управления.</span><span class="sxs-lookup"><span data-stu-id="06cb4-125">The `Get-ControlPanelItem` cmdlet gets the control panel item.</span></span> <span data-ttu-id="06cb4-126">`Show-ControlPanelItem`Командлет откроет его.</span><span class="sxs-lookup"><span data-stu-id="06cb4-126">The `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="06cb4-127">Пример 5. Получение элементов панели управления на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="06cb4-127">Example 5: Get control panel items on a remote computer</span></span>

<span data-ttu-id="06cb4-128">В этом примере возвращается элемент панели управления шифрование диска BitLocker на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="06cb4-128">This example gets the BitLocker Drive Encryption control panel item on the Server01 remote computer.</span></span>
<span data-ttu-id="06cb4-129">`Invoke-Command`Командлет запускает `Get-ControlPanelItem` командлет удаленно.</span><span class="sxs-lookup"><span data-stu-id="06cb4-129">The `Invoke-Command` cmdlet runs the `Get-ControlPanelItem` cmdlet remotely.</span></span>

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### <span data-ttu-id="06cb4-130">Пример 6. Поиск в описаниях элементов панели управления</span><span class="sxs-lookup"><span data-stu-id="06cb4-130">Example 6: Search the descriptions of control panel items</span></span>

<span data-ttu-id="06cb4-131">В этом примере выполняется поиск в свойстве **Description** элементов панели управления, чтобы получить только те, которые содержат имя **устройства** .</span><span class="sxs-lookup"><span data-stu-id="06cb4-131">This example searches the **Description** property of the control panel items to get only those that contain the name **Device** .</span></span>

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

<span data-ttu-id="06cb4-132">`Get-ControlPanelItem`Командлет возвращает все элементы панели управления.</span><span class="sxs-lookup"><span data-stu-id="06cb4-132">The `Get-ControlPanelItem` cmdlet gets all control panel items.</span></span> <span data-ttu-id="06cb4-133">`Where-Object`Командлет фильтрует элементы по значению свойства **Description** .</span><span class="sxs-lookup"><span data-stu-id="06cb4-133">The `Where-Object` cmdlet filters the items by the value of the **Description** property.</span></span>

## <span data-ttu-id="06cb4-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06cb4-134">PARAMETERS</span></span>

### <span data-ttu-id="06cb4-135">-Каноникалнаме</span><span class="sxs-lookup"><span data-stu-id="06cb4-135">-CanonicalName</span></span>

<span data-ttu-id="06cb4-136">Указывает в виде массива строк элементы панели управления по каноническому имени или шаблонам имен, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="06cb4-136">Specifies, as a string array, the control panel items by their canonical names or name patterns that this cmdlet gets.</span></span> <span data-ttu-id="06cb4-137">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="06cb4-137">Wildcards are permitted.</span></span> <span data-ttu-id="06cb4-138">При вводе нескольких имен этот командлет получает элементы панели управления, соответствующие любому из имен, как будто элементы в списке имен были разделены оператором "или".</span><span class="sxs-lookup"><span data-stu-id="06cb4-138">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span>

<span data-ttu-id="06cb4-139">По умолчанию этот командлет получает все элементы панели управления в системе.</span><span class="sxs-lookup"><span data-stu-id="06cb4-139">By default, this cmdlet gets all control panel items in the system.</span></span>

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

### <span data-ttu-id="06cb4-140">-Category</span><span class="sxs-lookup"><span data-stu-id="06cb4-140">-Category</span></span>

<span data-ttu-id="06cb4-141">Указывает в виде массива строк категории элементов панели управления в указанных категориях, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="06cb4-141">Specifies, as a string array, the categories of the control panel items in the specified categories that this cmdlet gets.</span></span> <span data-ttu-id="06cb4-142">Введите имя категории или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="06cb4-142">Enter a category name or name pattern.</span></span> <span data-ttu-id="06cb4-143">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="06cb4-143">Wildcards are permitted.</span></span> <span data-ttu-id="06cb4-144">При вводе нескольких имен этот командлет получает элементы панели управления, соответствующие любому из имен, как будто элементы в списке имен были разделены оператором "или".</span><span class="sxs-lookup"><span data-stu-id="06cb4-144">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span> <span data-ttu-id="06cb4-145">По умолчанию этот командлет получает все элементы панели управления в системе.</span><span class="sxs-lookup"><span data-stu-id="06cb4-145">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="06cb4-146">-Name</span><span class="sxs-lookup"><span data-stu-id="06cb4-146">-Name</span></span>

<span data-ttu-id="06cb4-147">Указывает в виде массива строк имена или шаблоны имен или имен элементов панели управления, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="06cb4-147">Specifies, as a string array, the names or name patterns of the control panel that this cmdlet gets.</span></span>
<span data-ttu-id="06cb4-148">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="06cb4-148">Wildcards are permitted.</span></span> <span data-ttu-id="06cb4-149">В этот командлет можно также передать по конвейеру имя или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="06cb4-149">You can also pipe a name or name pattern to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="06cb4-150">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="06cb4-150">CommonParameters</span></span>

<span data-ttu-id="06cb4-151">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06cb4-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06cb4-152">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06cb4-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06cb4-153">Входные данные</span><span class="sxs-lookup"><span data-stu-id="06cb4-153">INPUTS</span></span>

### <span data-ttu-id="06cb4-154">System.String</span><span class="sxs-lookup"><span data-stu-id="06cb4-154">System.String</span></span>

<span data-ttu-id="06cb4-155">В этот командлет можно передать по конвейеру имя или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="06cb4-155">You can pipe a name or name pattern to this cmdlet.</span></span>

## <span data-ttu-id="06cb4-156">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="06cb4-156">OUTPUTS</span></span>

### <span data-ttu-id="06cb4-157">Microsoft. PowerShell. Commands. ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="06cb4-157">Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="06cb4-158">Этот командлет возвращает элементы панели управления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06cb4-158">This cmdlet gets control panel items on the local computer.</span></span>

## <span data-ttu-id="06cb4-159">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="06cb4-159">NOTES</span></span>

## <span data-ttu-id="06cb4-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="06cb4-160">RELATED LINKS</span></span>

[<span data-ttu-id="06cb4-161">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="06cb4-161">Show-ControlPanelItem</span></span>](Show-ControlPanelItem.md)

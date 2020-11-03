---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227054"
---
# <span data-ttu-id="a26e9-103">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a26e9-103">Remove-PSSnapin</span></span>

## <span data-ttu-id="a26e9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a26e9-104">SYNOPSIS</span></span>
<span data-ttu-id="a26e9-105">Удаляет оснастки Windows PowerShell из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-105">Removes Windows PowerShell snap-ins from the current session.</span></span>

## <span data-ttu-id="a26e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a26e9-106">SYNTAX</span></span>

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a26e9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a26e9-107">DESCRIPTION</span></span>
<span data-ttu-id="a26e9-108">Командлет **Remove-PSSnapin** удаляет оснастку Windows PowerShell из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-108">The **Remove-PSSnapin** cmdlet removes a Windows PowerShell snap-in from the current session.</span></span>
<span data-ttu-id="a26e9-109">Его можно использовать для удаления оснасток, добавленных в Windows PowerShell. Этот командлет нельзя использовать для удаления оснасток, установленных с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a26e9-109">You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.</span></span>

<span data-ttu-id="a26e9-110">После удаления оснастки из текущего сеанса оснастка по-прежнему загружается, но командлеты и поставщики в оснастке больше не будут доступны в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a26e9-110">After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.</span></span>

## <span data-ttu-id="a26e9-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="a26e9-111">EXAMPLES</span></span>

### <span data-ttu-id="a26e9-112">Пример 1. удаление оснастки</span><span class="sxs-lookup"><span data-stu-id="a26e9-112">Example 1: Remove a snap-in</span></span>

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

<span data-ttu-id="a26e9-113">Эта команда удаляет оснастку **Microsoft. Exchange** из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-113">This command removes the **Microsoft.Exchange** snap-in from the current session.</span></span>
<span data-ttu-id="a26e9-114">После выполнения команды командлеты и поставщики, поддерживаемые этой оснасткой, будут недоступны в данном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a26e9-114">When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.</span></span>

### <span data-ttu-id="a26e9-115">Пример 2. удаление оснасток с помощью имен в конвейере</span><span class="sxs-lookup"><span data-stu-id="a26e9-115">Example 2: Remove snap-ins by using names with the pipeline</span></span>

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

<span data-ttu-id="a26e9-116">Эта команда удаляет оснастки Windows PowerShell, имена которых начинаются с SMP, из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-116">This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.</span></span>

<span data-ttu-id="a26e9-117">Команда использует командлет **Get-PSSnapin** для получения объектов, представляющих оснастки. Оператор конвейера (|) отправляет результаты в командлет **Remove-PSSnapin** , который удаляет их из сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-117">The command uses the **Get-PSSnapin** cmdlet to get objects that represent the snap-ins. The pipeline operator (|) sends the results to the **Remove-PSSnapin** cmdlet, which removes them from the session.</span></span>
<span data-ttu-id="a26e9-118">При этом поддерживаемые оснасткой поставщики и командлеты становятся недоступными в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="a26e9-118">The providers and cmdlets that this snap-in supports are no longer available in the session.</span></span>

<span data-ttu-id="a26e9-119">При передаче объектов в командлет **Remove-PSSnapin** имена объектов связываются с параметром *Name* , который принимает объекты из конвейера, у которых есть свойство **Name** .</span><span class="sxs-lookup"><span data-stu-id="a26e9-119">When you pipe objects to **Remove-PSSnapin** , the names of the objects are associated with the *Name* parameter, which accepts objects from the pipeline that have a **Name** property.</span></span>

### <span data-ttu-id="a26e9-120">Пример 3. удаление оснасток с помощью имен</span><span class="sxs-lookup"><span data-stu-id="a26e9-120">Example 3: Remove snap-ins by using names</span></span>

```
PS C:\> Remove-PSSnapin -Name *event*
```

<span data-ttu-id="a26e9-121">Эта команда удаляет все оснастки Windows PowerShell с именами, которые содержат событие.</span><span class="sxs-lookup"><span data-stu-id="a26e9-121">This command removes all Windows PowerShell snap-ins that have names that include event.</span></span>

## <span data-ttu-id="a26e9-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a26e9-122">PARAMETERS</span></span>

### <span data-ttu-id="a26e9-123">-Name</span><span class="sxs-lookup"><span data-stu-id="a26e9-123">-Name</span></span>
<span data-ttu-id="a26e9-124">Задает имена оснасток Windows PowerShell для удаления из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-124">Specifies the names of Windows PowerShell snap-ins to remove from the current session.</span></span>
<span data-ttu-id="a26e9-125">Допускается использование подстановочных знаков (\*).</span><span class="sxs-lookup"><span data-stu-id="a26e9-125">Wildcard characters (\*) are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a26e9-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a26e9-126">-PassThru</span></span>
<span data-ttu-id="a26e9-127">Возвращает объект, представляющий оснастку.</span><span class="sxs-lookup"><span data-stu-id="a26e9-127">Returns an object that represents the snap-in.</span></span>
<span data-ttu-id="a26e9-128">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a26e9-128">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a26e9-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a26e9-129">-Confirm</span></span>
<span data-ttu-id="a26e9-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a26e9-130">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a26e9-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a26e9-131">-WhatIf</span></span>
<span data-ttu-id="a26e9-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a26e9-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a26e9-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a26e9-133">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a26e9-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a26e9-134">CommonParameters</span></span>
<span data-ttu-id="a26e9-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a26e9-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a26e9-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a26e9-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a26e9-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a26e9-137">INPUTS</span></span>

### <span data-ttu-id="a26e9-138">System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="a26e9-138">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a26e9-139">Объект оснастки можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a26e9-139">You can pipe a snap-in object to this cmdlet.</span></span>

## <span data-ttu-id="a26e9-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a26e9-140">OUTPUTS</span></span>

### <span data-ttu-id="a26e9-141">Нет, System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="a26e9-141">None, System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a26e9-142">Этот командлет создает объект **System. Management. Automation. PSSnapInInfo** , представляющий оснастку, если указан параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="a26e9-142">This cmdlet generates a **System.Management.Automation.PSSnapInInfo** object that represents the snap-in, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="a26e9-143">По умолчанию **Remove-PSSnapin** не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a26e9-143">By default, **Remove-PSSnapin** does not generate any output.</span></span>

## <span data-ttu-id="a26e9-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a26e9-144">NOTES</span></span>

* <span data-ttu-id="a26e9-145">Командлет **Remove-PSSnapin** не проверяет версию Windows PowerShell перед удалением оснастки из сеанса.</span><span class="sxs-lookup"><span data-stu-id="a26e9-145">**Remove-PSSnapin** does not check the version of Windows PowerShell before removing a snap-in from the session.</span></span> <span data-ttu-id="a26e9-146">Если удалить оснастку не удается, отображается предупреждение и команда не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a26e9-146">If a snap-in cannot be removed, a warning appears and the command fails.</span></span>
* <span data-ttu-id="a26e9-147">**Remove-PSSnapin** влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="a26e9-147">**Remove-PSSnapin** affects only the current session.</span></span> <span data-ttu-id="a26e9-148">Если команда Add-PSSnapin добавлена в профиль Windows PowerShell, то для удаления оснастки из будущих сеансов эту команду следует удалить.</span><span class="sxs-lookup"><span data-stu-id="a26e9-148">If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.</span></span> <span data-ttu-id="a26e9-149">Для получения инструкций введите `Get-Help about_Profiles` .</span><span class="sxs-lookup"><span data-stu-id="a26e9-149">For instructions, type `Get-Help about_Profiles`.</span></span>

## <span data-ttu-id="a26e9-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a26e9-150">RELATED LINKS</span></span>

[<span data-ttu-id="a26e9-151">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a26e9-151">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="a26e9-152">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a26e9-152">Get-PSSnapin</span></span>](Get-PSSnapin.md)

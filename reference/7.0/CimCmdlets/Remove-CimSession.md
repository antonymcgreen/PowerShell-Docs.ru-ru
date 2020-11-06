---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: 729b0d1c860d29190ab4b87b818dd7b89018bfd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225690"
---
# <span data-ttu-id="2fc0a-103">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="2fc0a-103">Remove-CimSession</span></span>

## <span data-ttu-id="2fc0a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2fc0a-104">SYNOPSIS</span></span>
<span data-ttu-id="2fc0a-105">Удаляет один или несколько сеансов CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-105">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="2fc0a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2fc0a-106">SYNTAX</span></span>

### <span data-ttu-id="2fc0a-107">Цимсессионсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2fc0a-107">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2fc0a-108">компутернамесет</span><span class="sxs-lookup"><span data-stu-id="2fc0a-108">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2fc0a-109">SessionId</span><span class="sxs-lookup"><span data-stu-id="2fc0a-109">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2fc0a-110">инстанцеидсет</span><span class="sxs-lookup"><span data-stu-id="2fc0a-110">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2fc0a-111">Имя</span><span class="sxs-lookup"><span data-stu-id="2fc0a-111">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2fc0a-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fc0a-112">DESCRIPTION</span></span>

<span data-ttu-id="2fc0a-113">`Remove-CimSession`Командлет удаляет один или несколько объектов сеанса CIM из локального сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-113">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="2fc0a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="2fc0a-114">EXAMPLES</span></span>

### <span data-ttu-id="2fc0a-115">Пример 1. Удаление всех сеансов CIM</span><span class="sxs-lookup"><span data-stu-id="2fc0a-115">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="2fc0a-116">Этот пример извлекает все доступные сеансы CIM на локальном компьютере с помощью командлета [Get-CimSession](Get-CimSession.md) , а затем удаляет их с помощью `Remove-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="2fc0a-116">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="2fc0a-117">Пример 2. удаление конкретного сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="2fc0a-117">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="2fc0a-118">В этом примере удаляется сеанс CIM, имеющий значение **ID** , равное 5.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-118">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="2fc0a-119">Пример 3. Отображение списка сеансов CIM для удаления с помощью параметра WhatIf</span><span class="sxs-lookup"><span data-stu-id="2fc0a-119">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="2fc0a-120">В этом примере используется общий параметр **WhatIf** для указания на то, что удаление не должно выполняться, но при этом выводятся только те данные, которые были бы выполнены.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-120">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="2fc0a-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2fc0a-121">PARAMETERS</span></span>

### <span data-ttu-id="2fc0a-122">-CimSession</span><span class="sxs-lookup"><span data-stu-id="2fc0a-122">-CimSession</span></span>

<span data-ttu-id="2fc0a-123">Указывает объекты сеанса для закрытия сеансов CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-123">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="2fc0a-124">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) командлеты или.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-124">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="2fc0a-125">Дополнительные сведения см. в разделе [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="2fc0a-125">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2fc0a-126">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2fc0a-126">-ComputerName</span></span>

<span data-ttu-id="2fc0a-127">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-127">Specifies an array of names of computers.</span></span> <span data-ttu-id="2fc0a-128">Удаляет сеансы, подключающиеся к указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-128">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="2fc0a-129">Можно указать полное доменное имя или NetBIOS-имя.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2fc0a-130">-Id</span><span class="sxs-lookup"><span data-stu-id="2fc0a-130">-Id</span></span>

<span data-ttu-id="2fc0a-131">Указывает идентификатор удаляемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-131">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="2fc0a-132">Укажите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range ( `..` ), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-132">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="2fc0a-133">**Идентификатор** — это целое число, которое однозначно определяет сеанс CIM в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-133">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="2fc0a-134">Дополнительные сведения об операторе Range см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="2fc0a-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2fc0a-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="2fc0a-135">-InstanceId</span></span>

<span data-ttu-id="2fc0a-136">Указывает идентификатор экземпляра удаляемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-136">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="2fc0a-137">**InstanceId** — это глобальный уникальный идентификатор (GUID), который однозначно определяет сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-137">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="2fc0a-138">Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="2fc0a-139">**InstanceId** хранится в свойстве **InstanceId** объекта, представляющего сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2fc0a-140">-Name</span><span class="sxs-lookup"><span data-stu-id="2fc0a-140">-Name</span></span>

<span data-ttu-id="2fc0a-141">Указывает понятное имя удаляемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-141">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="2fc0a-142">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-142">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2fc0a-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2fc0a-143">-Confirm</span></span>

<span data-ttu-id="2fc0a-144">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2fc0a-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2fc0a-145">-WhatIf</span></span>

<span data-ttu-id="2fc0a-146">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-146">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2fc0a-147">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2fc0a-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2fc0a-148">CommonParameters</span></span>

<span data-ttu-id="2fc0a-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2fc0a-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2fc0a-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2fc0a-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2fc0a-151">INPUTS</span></span>

### <span data-ttu-id="2fc0a-152">Нет</span><span class="sxs-lookup"><span data-stu-id="2fc0a-152">None</span></span>

<span data-ttu-id="2fc0a-153">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-153">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="2fc0a-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2fc0a-154">OUTPUTS</span></span>

### <span data-ttu-id="2fc0a-155">System.Object</span><span class="sxs-lookup"><span data-stu-id="2fc0a-155">System.Object</span></span>

<span data-ttu-id="2fc0a-156">Этот командлет возвращает объект, содержащий сведения о сеансе CIM.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-156">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="2fc0a-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2fc0a-157">NOTES</span></span>

## <span data-ttu-id="2fc0a-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2fc0a-158">RELATED LINKS</span></span>

[<span data-ttu-id="2fc0a-159">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="2fc0a-159">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="2fc0a-160">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="2fc0a-160">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="2fc0a-161">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="2fc0a-161">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
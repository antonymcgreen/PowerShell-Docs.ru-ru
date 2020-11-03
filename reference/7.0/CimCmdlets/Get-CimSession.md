---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: dbbbb352d1b3af8a0f05d2805fb42b7bb3ed27d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226034"
---
# <span data-ttu-id="0f2a9-103">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="0f2a9-103">Get-CimSession</span></span>

## <span data-ttu-id="0f2a9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0f2a9-104">SYNOPSIS</span></span>
<span data-ttu-id="0f2a9-105">Возвращает объекты сеанса CIM из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-105">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="0f2a9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f2a9-106">SYNTAX</span></span>

### <span data-ttu-id="0f2a9-107">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0f2a9-107">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0f2a9-108">SessionId</span><span class="sxs-lookup"><span data-stu-id="0f2a9-108">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="0f2a9-109">инстанцеидсет</span><span class="sxs-lookup"><span data-stu-id="0f2a9-109">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="0f2a9-110">Имя</span><span class="sxs-lookup"><span data-stu-id="0f2a9-110">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="0f2a9-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f2a9-111">DESCRIPTION</span></span>

<span data-ttu-id="0f2a9-112">По умолчанию командлет получает все сеансы CIM, созданные в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-112">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="0f2a9-113">`Get-CimSession`Для получения сеансов, предназначенных для конкретных компьютеров, можно использовать параметры, или можно указать сеансы по их именам или другим идентификаторам.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-113">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="0f2a9-114">`Get-CimSession` не получает сеансы CIM, созданные в других сеансах PowerShell или созданные на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-114">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="0f2a9-115">Дополнительные сведения о сеансах CIM см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="0f2a9-115">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="0f2a9-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f2a9-116">EXAMPLES</span></span>

### <span data-ttu-id="0f2a9-117">Пример 1. получение сеансов CIM из текущего сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f2a9-117">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="0f2a9-118">Этот пример создает сеансы CIM с помощью [New-CimSession](New-CimSession.md), а затем получает сеансы CIM с помощью `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="0f2a9-118">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="0f2a9-119">Пример 2. получение сеансов CIM для определенного компьютера</span><span class="sxs-lookup"><span data-stu-id="0f2a9-119">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="0f2a9-120">В этом примере возвращаются сеансы CIM, подключенные к компьютеру с именем **Server02**.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-120">This example gets the CIM sessions that are connected to the computer named **Server02**.</span></span>

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="0f2a9-121">Пример 3. Получение списка сеансов CIM и последующее форматирование списка</span><span class="sxs-lookup"><span data-stu-id="0f2a9-121">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="0f2a9-122">Этот пример получает все сеансы CIM в текущем сеансе PowerShell и отображает таблицу, содержащую только свойства **ComputerName** и **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="0f2a9-122">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="0f2a9-123">Пример 4. получение всех сеансов CIM с конкретными именами</span><span class="sxs-lookup"><span data-stu-id="0f2a9-123">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="0f2a9-124">В этом примере получаются все сеансы CIM, имена которых начинаются с **серв**.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-124">This example gets all CIM sessions that have names that begin with **serv**.</span></span>

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="0f2a9-125">Пример 5. получение конкретного сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="0f2a9-125">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="0f2a9-126">В этом примере возвращается сеанс CIM с **идентификатором** 2.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-126">This example gets the CIM session that has an **Id** of 2.</span></span>

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## <span data-ttu-id="0f2a9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f2a9-127">PARAMETERS</span></span>

### <span data-ttu-id="0f2a9-128">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0f2a9-128">-ComputerName</span></span>

<span data-ttu-id="0f2a9-129">Указывает имя компьютера, к которому подключены сеансы CIM.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-129">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="0f2a9-130">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0f2a9-131">-Id</span><span class="sxs-lookup"><span data-stu-id="0f2a9-131">-Id</span></span>

<span data-ttu-id="0f2a9-132">Указывает идентификатор получаемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-132">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="0f2a9-133">Для нескольких идентификаторов используйте запятые для разделения идентификаторов или используйте оператор Range ( `..` ), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-133">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="0f2a9-134">**Идентификатор** — это целое число, которое однозначно определяет сеанс CIM в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-134">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="0f2a9-135">Дополнительные сведения об операторе Range см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0f2a9-135">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="0f2a9-136">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0f2a9-136">-InstanceId</span></span>

<span data-ttu-id="0f2a9-137">Указывает идентификаторы экземпляров получаемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-137">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="0f2a9-138">**InstanceId** — это глобальный уникальный идентификатор (GUID), который однозначно определяет сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-138">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="0f2a9-139">Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-139">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="0f2a9-140">**InstanceId** хранится в свойстве **InstanceId** объекта, представляющего сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-140">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="0f2a9-141">-Name</span><span class="sxs-lookup"><span data-stu-id="0f2a9-141">-Name</span></span>

<span data-ttu-id="0f2a9-142">Возвращает один или несколько сеансов CIM, которые содержат указанные понятные имена.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-142">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="0f2a9-143">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-143">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0f2a9-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0f2a9-144">CommonParameters</span></span>
<span data-ttu-id="0f2a9-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f2a9-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f2a9-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f2a9-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f2a9-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0f2a9-147">INPUTS</span></span>

### <span data-ttu-id="0f2a9-148">Нет</span><span class="sxs-lookup"><span data-stu-id="0f2a9-148">None</span></span>

## <span data-ttu-id="0f2a9-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0f2a9-149">OUTPUTS</span></span>

### <span data-ttu-id="0f2a9-150">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="0f2a9-150">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="0f2a9-151">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0f2a9-151">NOTES</span></span>

## <span data-ttu-id="0f2a9-152">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0f2a9-152">RELATED LINKS</span></span>

[<span data-ttu-id="0f2a9-153">Format-Table</span><span class="sxs-lookup"><span data-stu-id="0f2a9-153">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="0f2a9-154">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="0f2a9-154">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="0f2a9-155">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="0f2a9-155">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="0f2a9-156">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="0f2a9-156">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

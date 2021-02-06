---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: 0e531b3cc072b7cc1efe0ef06fb741326bf3a72b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599796"
---
# <span data-ttu-id="5e71d-102">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="5e71d-102">Get-CimSession</span></span>

## <span data-ttu-id="5e71d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5e71d-103">SYNOPSIS</span></span>
<span data-ttu-id="5e71d-104">Возвращает объекты сеанса CIM из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5e71d-104">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="5e71d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5e71d-105">SYNTAX</span></span>

### <span data-ttu-id="5e71d-106">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5e71d-106">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5e71d-107">SessionId</span><span class="sxs-lookup"><span data-stu-id="5e71d-107">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="5e71d-108">инстанцеидсет</span><span class="sxs-lookup"><span data-stu-id="5e71d-108">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="5e71d-109">Имя</span><span class="sxs-lookup"><span data-stu-id="5e71d-109">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="5e71d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5e71d-110">DESCRIPTION</span></span>

<span data-ttu-id="5e71d-111">По умолчанию командлет получает все сеансы CIM, созданные в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e71d-111">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="5e71d-112">`Get-CimSession`Для получения сеансов, предназначенных для конкретных компьютеров, можно использовать параметры, или можно указать сеансы по их именам или другим идентификаторам.</span><span class="sxs-lookup"><span data-stu-id="5e71d-112">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="5e71d-113">`Get-CimSession` не получает сеансы CIM, созданные в других сеансах PowerShell или созданные на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5e71d-113">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="5e71d-114">Дополнительные сведения о сеансах CIM см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="5e71d-114">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="5e71d-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="5e71d-115">EXAMPLES</span></span>

### <span data-ttu-id="5e71d-116">Пример 1. получение сеансов CIM из текущего сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e71d-116">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="5e71d-117">Этот пример создает сеансы CIM с помощью [New-CimSession](New-CimSession.md), а затем получает сеансы CIM с помощью `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="5e71d-117">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

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

### <span data-ttu-id="5e71d-118">Пример 2. получение сеансов CIM для определенного компьютера</span><span class="sxs-lookup"><span data-stu-id="5e71d-118">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="5e71d-119">В этом примере возвращаются сеансы CIM, подключенные к компьютеру с именем **Server02**.</span><span class="sxs-lookup"><span data-stu-id="5e71d-119">This example gets the CIM sessions that are connected to the computer named **Server02**.</span></span>

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

### <span data-ttu-id="5e71d-120">Пример 3. Получение списка сеансов CIM и последующее форматирование списка</span><span class="sxs-lookup"><span data-stu-id="5e71d-120">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="5e71d-121">Этот пример получает все сеансы CIM в текущем сеансе PowerShell и отображает таблицу, содержащую только свойства **ComputerName** и **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="5e71d-121">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="5e71d-122">Пример 4. получение всех сеансов CIM с конкретными именами</span><span class="sxs-lookup"><span data-stu-id="5e71d-122">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="5e71d-123">В этом примере получаются все сеансы CIM, имена которых начинаются с **серв**.</span><span class="sxs-lookup"><span data-stu-id="5e71d-123">This example gets all CIM sessions that have names that begin with **serv**.</span></span>

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

### <span data-ttu-id="5e71d-124">Пример 5. получение конкретного сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="5e71d-124">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="5e71d-125">В этом примере возвращается сеанс CIM с **идентификатором** 2.</span><span class="sxs-lookup"><span data-stu-id="5e71d-125">This example gets the CIM session that has an **Id** of 2.</span></span>

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

## <span data-ttu-id="5e71d-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5e71d-126">PARAMETERS</span></span>

### <span data-ttu-id="5e71d-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5e71d-127">-ComputerName</span></span>

<span data-ttu-id="5e71d-128">Указывает имя компьютера, к которому подключены сеансы CIM.</span><span class="sxs-lookup"><span data-stu-id="5e71d-128">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="5e71d-129">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5e71d-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5e71d-130">-Id</span><span class="sxs-lookup"><span data-stu-id="5e71d-130">-Id</span></span>

<span data-ttu-id="5e71d-131">Указывает идентификатор получаемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="5e71d-131">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="5e71d-132">Для нескольких идентификаторов используйте запятые для разделения идентификаторов или используйте оператор Range ( `..` ), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="5e71d-132">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="5e71d-133">**Идентификатор** — это целое число, которое однозначно определяет сеанс CIM в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e71d-133">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="5e71d-134">Дополнительные сведения об операторе Range см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="5e71d-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="5e71d-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5e71d-135">-InstanceId</span></span>

<span data-ttu-id="5e71d-136">Указывает идентификаторы экземпляров получаемого сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="5e71d-136">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="5e71d-137">**InstanceId** — это глобальный уникальный идентификатор (GUID), который однозначно определяет сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="5e71d-137">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="5e71d-138">Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="5e71d-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="5e71d-139">**InstanceId** хранится в свойстве **InstanceId** объекта, представляющего сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="5e71d-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="5e71d-140">-Name</span><span class="sxs-lookup"><span data-stu-id="5e71d-140">-Name</span></span>

<span data-ttu-id="5e71d-141">Возвращает один или несколько сеансов CIM, которые содержат указанные понятные имена.</span><span class="sxs-lookup"><span data-stu-id="5e71d-141">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="5e71d-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5e71d-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5e71d-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5e71d-143">CommonParameters</span></span>
<span data-ttu-id="5e71d-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5e71d-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e71d-145">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5e71d-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e71d-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5e71d-146">INPUTS</span></span>

### <span data-ttu-id="5e71d-147">None</span><span class="sxs-lookup"><span data-stu-id="5e71d-147">None</span></span>

## <span data-ttu-id="5e71d-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5e71d-148">OUTPUTS</span></span>

### <span data-ttu-id="5e71d-149">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="5e71d-149">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="5e71d-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5e71d-150">NOTES</span></span>

## <span data-ttu-id="5e71d-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5e71d-151">RELATED LINKS</span></span>

[<span data-ttu-id="5e71d-152">Format-Table</span><span class="sxs-lookup"><span data-stu-id="5e71d-152">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="5e71d-153">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="5e71d-153">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="5e71d-154">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="5e71d-154">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="5e71d-155">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="5e71d-155">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)


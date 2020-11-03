---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226610"
---
# <span data-ttu-id="e40ea-103">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e40ea-103">Get-LocalGroupMember</span></span>

## <span data-ttu-id="e40ea-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e40ea-104">SYNOPSIS</span></span>
<span data-ttu-id="e40ea-105">Возвращает элементы из локальной группы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-105">Gets members from a local group.</span></span>

## <span data-ttu-id="e40ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e40ea-106">SYNTAX</span></span>

### <span data-ttu-id="e40ea-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e40ea-107">Default (Default)</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### <span data-ttu-id="e40ea-108">Group</span><span class="sxs-lookup"><span data-stu-id="e40ea-108">Group</span></span>

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### <span data-ttu-id="e40ea-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e40ea-109">SecurityIdentifier</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## <span data-ttu-id="e40ea-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e40ea-110">DESCRIPTION</span></span>
<span data-ttu-id="e40ea-111">Командлет **Get-локалграупмембер** получает элементы из локальной группы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-111">The **Get-LocalGroupMember** cmdlet gets members from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="e40ea-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="e40ea-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="e40ea-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e40ea-113">EXAMPLES</span></span>

### <span data-ttu-id="e40ea-114">Пример 1. получение всех членов группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="e40ea-114">Example 1: Get all members of the Administrators group</span></span>

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

<span data-ttu-id="e40ea-115">Эта команда возвращает всех членов локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="e40ea-115">This command gets all the members of the local Administrators group.</span></span>

## <span data-ttu-id="e40ea-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e40ea-116">PARAMETERS</span></span>

### <span data-ttu-id="e40ea-117">-Group</span><span class="sxs-lookup"><span data-stu-id="e40ea-117">-Group</span></span>
<span data-ttu-id="e40ea-118">Указывает группу безопасности, из которой этот командлет получает элементы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-118">Specifies the security group from which this cmdlet gets members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e40ea-119">-Member</span><span class="sxs-lookup"><span data-stu-id="e40ea-119">-Member</span></span>
<span data-ttu-id="e40ea-120">Указывает пользователя или группу, которую этот командлет получает из группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="e40ea-120">Specifies a user or group that this cmdlet gets from a security group.</span></span>
<span data-ttu-id="e40ea-121">Можно указать пользователей или группы по имени или ИДЕНТИФИКАТОРу безопасности (SID).</span><span class="sxs-lookup"><span data-stu-id="e40ea-121">You can specify users or groups by name or security ID (SID).</span></span>
<span data-ttu-id="e40ea-122">Укажите строки SID в S-R-I-S-S.</span><span class="sxs-lookup"><span data-stu-id="e40ea-122">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="e40ea-123">.</span><span class="sxs-lookup"><span data-stu-id="e40ea-123">.</span></span> <span data-ttu-id="e40ea-124">.</span><span class="sxs-lookup"><span data-stu-id="e40ea-124">.</span></span>
<span data-ttu-id="e40ea-125">ЧЧ:ММ:СС...</span><span class="sxs-lookup"><span data-stu-id="e40ea-125">format.</span></span>
<span data-ttu-id="e40ea-126">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e40ea-126">You can use wildcard characters.</span></span>
<span data-ttu-id="e40ea-127">Если этот параметр не указан, командлет получает все члены группы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-127">If you do not specify this parameter, the cmdlet gets all members of the group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e40ea-128">-Name</span><span class="sxs-lookup"><span data-stu-id="e40ea-128">-Name</span></span>
<span data-ttu-id="e40ea-129">Указывает имя группы безопасности, из которой этот командлет получает элементы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-129">Specifies the name of the security group from which this cmdlet gets members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e40ea-130">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="e40ea-130">-SID</span></span>
<span data-ttu-id="e40ea-131">Указывает идентификатор безопасности группы безопасности, из которой этот командлет получает элементы.</span><span class="sxs-lookup"><span data-stu-id="e40ea-131">Specifies the security ID of the security group from which this cmdlet gets members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e40ea-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e40ea-132">CommonParameters</span></span>
<span data-ttu-id="e40ea-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e40ea-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e40ea-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e40ea-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e40ea-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e40ea-135">INPUTS</span></span>

### <span data-ttu-id="e40ea-136">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e40ea-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="e40ea-137">К этому командлету можно передать по конвейеру локальную группу, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="e40ea-137">You can pipe a local group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="e40ea-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e40ea-138">OUTPUTS</span></span>

### <span data-ttu-id="e40ea-139">Microsoft. Секуритяккаунтсманажер. ЛокалпринЦипал</span><span class="sxs-lookup"><span data-stu-id="e40ea-139">Microsoft.SecurityAccountsManager.LocalPrincipal</span></span>
<span data-ttu-id="e40ea-140">Этот командлет возвращает локальных участников.</span><span class="sxs-lookup"><span data-stu-id="e40ea-140">This cmdlet returns local principals.</span></span>

## <span data-ttu-id="e40ea-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e40ea-141">NOTES</span></span>

* <span data-ttu-id="e40ea-142">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="e40ea-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="e40ea-143">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="e40ea-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="e40ea-144">Локальная</span><span class="sxs-lookup"><span data-stu-id="e40ea-144">Local</span></span>
- <span data-ttu-id="e40ea-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e40ea-145">Active Directory</span></span>
- <span data-ttu-id="e40ea-146">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e40ea-146">Azure Active Directory group</span></span>
- <span data-ttu-id="e40ea-147">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e40ea-147">Microsoft Account</span></span>

<span data-ttu-id="e40ea-148">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="e40ea-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="e40ea-149">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="e40ea-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="e40ea-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e40ea-150">RELATED LINKS</span></span>

[<span data-ttu-id="e40ea-151">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e40ea-151">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="e40ea-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e40ea-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="e40ea-153">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e40ea-153">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)

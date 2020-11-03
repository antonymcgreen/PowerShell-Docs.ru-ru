---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226617"
---
# <span data-ttu-id="b6005-103">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-103">Get-LocalGroup</span></span>

## <span data-ttu-id="b6005-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b6005-104">SYNOPSIS</span></span>
<span data-ttu-id="b6005-105">Возвращает локальные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6005-105">Gets the local security groups.</span></span>

## <span data-ttu-id="b6005-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6005-106">SYNTAX</span></span>

### <span data-ttu-id="b6005-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b6005-107">Default (Default)</span></span>

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b6005-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b6005-108">SecurityIdentifier</span></span>

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="b6005-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6005-109">DESCRIPTION</span></span>
<span data-ttu-id="b6005-110">Командлет **Get-LocalGroup** получает локальные группы безопасности в диспетчере учетных записей безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6005-110">The **Get-LocalGroup** cmdlet gets local security groups in Security Account Manager.</span></span>
<span data-ttu-id="b6005-111">Этот командлет получает встроенные группы по умолчанию и локальные группы безопасности, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="b6005-111">This cmdlet gets default built-in groups and local security groups that you create.</span></span>

> [!NOTE]
> <span data-ttu-id="b6005-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="b6005-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="b6005-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b6005-113">EXAMPLES</span></span>

### <span data-ttu-id="b6005-114">Пример 1. Получение группы администраторов</span><span class="sxs-lookup"><span data-stu-id="b6005-114">Example 1: Get the Administrators group</span></span>

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

<span data-ttu-id="b6005-115">Эта команда возвращает локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="b6005-115">This command gets the local Administrators group.</span></span>
<span data-ttu-id="b6005-116">Команда отображает свойства группы в консоли.</span><span class="sxs-lookup"><span data-stu-id="b6005-116">The command displays properties of the group in the console.</span></span>

## <span data-ttu-id="b6005-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6005-117">PARAMETERS</span></span>

### <span data-ttu-id="b6005-118">-Name</span><span class="sxs-lookup"><span data-stu-id="b6005-118">-Name</span></span>
<span data-ttu-id="b6005-119">Указывает массив имен групп безопасности, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b6005-119">Specifies an array of names of security groups that this cmdlet gets.</span></span>
<span data-ttu-id="b6005-120">Можно использовать подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="b6005-120">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b6005-121">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="b6005-121">-SID</span></span>
<span data-ttu-id="b6005-122">Указывает массив идентификаторов безопасности (SID) групп безопасности, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b6005-122">Specifies an array of security IDs (SIDs) of security groups that this cmdlet gets.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b6005-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b6005-123">CommonParameters</span></span>
<span data-ttu-id="b6005-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b6005-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6005-125">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b6005-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6005-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b6005-126">INPUTS</span></span>

### <span data-ttu-id="b6005-127">System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b6005-127">System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="b6005-128">В этот командлет можно передать строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6005-128">You can pipe a string or a SID to this cmdlet.</span></span>

## <span data-ttu-id="b6005-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b6005-129">OUTPUTS</span></span>

### <span data-ttu-id="b6005-130">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-130">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="b6005-131">Этот командлет возвращает локальную группу.</span><span class="sxs-lookup"><span data-stu-id="b6005-131">This cmdlet returns a local group.</span></span>

## <span data-ttu-id="b6005-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b6005-132">NOTES</span></span>

* <span data-ttu-id="b6005-133">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="b6005-133">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="b6005-134">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="b6005-134">The possible sources are as follows:</span></span>

- <span data-ttu-id="b6005-135">Локальная</span><span class="sxs-lookup"><span data-stu-id="b6005-135">Local</span></span>
- <span data-ttu-id="b6005-136">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6005-136">Active Directory</span></span>
- <span data-ttu-id="b6005-137">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6005-137">Azure Active Directory group</span></span>
- <span data-ttu-id="b6005-138">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b6005-138">Microsoft Account</span></span>

<span data-ttu-id="b6005-139">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="b6005-139">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="b6005-140">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="b6005-140">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="b6005-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b6005-141">RELATED LINKS</span></span>

[<span data-ttu-id="b6005-142">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-142">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="b6005-143">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-143">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="b6005-144">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-144">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="b6005-145">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="b6005-145">Set-LocalGroup</span></span>](Set-LocalGroup.md)

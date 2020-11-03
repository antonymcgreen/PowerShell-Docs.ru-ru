---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalGroup
ms.openlocfilehash: de66ad724d3cfee2d296d3b431618768a9cd38da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228009"
---
# <span data-ttu-id="fd478-103">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-103">New-LocalGroup</span></span>

## <span data-ttu-id="fd478-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fd478-104">SYNOPSIS</span></span>
<span data-ttu-id="fd478-105">Создает локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd478-105">Creates a local security group.</span></span>

## <span data-ttu-id="fd478-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd478-106">SYNTAX</span></span>

```
New-LocalGroup [-Description <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd478-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd478-107">DESCRIPTION</span></span>
<span data-ttu-id="fd478-108">Командлет **New-LocalGroup** создает локальную группу безопасности в диспетчере учетных записей безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd478-108">The **New-LocalGroup** cmdlet creates a local security group in the Security Account Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="fd478-109">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="fd478-109">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="fd478-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="fd478-110">EXAMPLES</span></span>

### <span data-ttu-id="fd478-111">Пример 1. Создание группы безопасности</span><span class="sxs-lookup"><span data-stu-id="fd478-111">Example 1: Create a security group</span></span>

```
PS C:\> New-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="fd478-112">Эта команда создает группу с именем SecurityGroup04.</span><span class="sxs-lookup"><span data-stu-id="fd478-112">This command creates a group named SecurityGroup04.</span></span>

## <span data-ttu-id="fd478-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd478-113">PARAMETERS</span></span>

### <span data-ttu-id="fd478-114">-Description</span><span class="sxs-lookup"><span data-stu-id="fd478-114">-Description</span></span>
<span data-ttu-id="fd478-115">Задает комментарий для группы.</span><span class="sxs-lookup"><span data-stu-id="fd478-115">Specifies a comment for the group.</span></span>
<span data-ttu-id="fd478-116">Максимальная длина — 48 символов.</span><span class="sxs-lookup"><span data-stu-id="fd478-116">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd478-117">-Name</span><span class="sxs-lookup"><span data-stu-id="fd478-117">-Name</span></span>
<span data-ttu-id="fd478-118">Задает имя группы.</span><span class="sxs-lookup"><span data-stu-id="fd478-118">Specifies a name for the group.</span></span>
<span data-ttu-id="fd478-119">Максимальная длина составляет 256 символов.</span><span class="sxs-lookup"><span data-stu-id="fd478-119">The maximum length is 256 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd478-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd478-120">-Confirm</span></span>
<span data-ttu-id="fd478-121">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="fd478-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd478-122">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd478-122">-WhatIf</span></span>
<span data-ttu-id="fd478-123">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="fd478-123">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fd478-124">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fd478-124">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd478-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fd478-125">CommonParameters</span></span>
<span data-ttu-id="fd478-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd478-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd478-127">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd478-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd478-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fd478-128">INPUTS</span></span>

### <span data-ttu-id="fd478-129">System.String</span><span class="sxs-lookup"><span data-stu-id="fd478-129">System.String</span></span>
<span data-ttu-id="fd478-130">Вы можете передать строку в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fd478-130">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="fd478-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fd478-131">OUTPUTS</span></span>

### <span data-ttu-id="fd478-132">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-132">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="fd478-133">Этот командлет возвращает группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd478-133">This cmdlet returns a security group.</span></span>

## <span data-ttu-id="fd478-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fd478-134">NOTES</span></span>

* <span data-ttu-id="fd478-135">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="fd478-135">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="fd478-136">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="fd478-136">The possible sources are as follows:</span></span>

- <span data-ttu-id="fd478-137">Локальная</span><span class="sxs-lookup"><span data-stu-id="fd478-137">Local</span></span>
- <span data-ttu-id="fd478-138">Active Directory</span><span class="sxs-lookup"><span data-stu-id="fd478-138">Active Directory</span></span>
- <span data-ttu-id="fd478-139">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fd478-139">Azure Active Directory group</span></span>
- <span data-ttu-id="fd478-140">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd478-140">Microsoft Account</span></span>

<span data-ttu-id="fd478-141">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="fd478-141">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="fd478-142">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="fd478-142">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="fd478-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fd478-143">RELATED LINKS</span></span>

[<span data-ttu-id="fd478-144">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-144">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="fd478-145">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-145">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="fd478-146">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-146">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="fd478-147">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="fd478-147">Set-LocalGroup</span></span>](Set-LocalGroup.md)

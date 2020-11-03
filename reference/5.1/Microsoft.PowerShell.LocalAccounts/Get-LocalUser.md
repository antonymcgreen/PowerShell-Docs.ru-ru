---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226609"
---
# <span data-ttu-id="448f6-103">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-103">Get-LocalUser</span></span>

## <span data-ttu-id="448f6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="448f6-104">SYNOPSIS</span></span>
<span data-ttu-id="448f6-105">Возвращает учетные записи локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="448f6-105">Gets local user accounts.</span></span>

## <span data-ttu-id="448f6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="448f6-106">SYNTAX</span></span>

### <span data-ttu-id="448f6-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="448f6-107">Default (Default)</span></span>

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="448f6-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="448f6-108">SecurityIdentifier</span></span>

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="448f6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="448f6-109">DESCRIPTION</span></span>

<span data-ttu-id="448f6-110">`Get-LocalUser`Командлет получает локальные учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="448f6-110">The `Get-LocalUser` cmdlet gets local user accounts.</span></span> <span data-ttu-id="448f6-111">Этот командлет получает встроенные учетные записи пользователей по умолчанию, созданные локальные учетные записи пользователей и локальные учетные записи, подключенные к учетным записям Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="448f6-111">This cmdlet gets default built-in user accounts, local user accounts that you created, and local accounts that you connected to Microsoft accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="448f6-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="448f6-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="448f6-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="448f6-113">EXAMPLES</span></span>

### <span data-ttu-id="448f6-114">Пример 1. Получение учетной записи с помощью ее имени</span><span class="sxs-lookup"><span data-stu-id="448f6-114">Example 1: Get an account by using its name</span></span>

<span data-ttu-id="448f6-115">В этом примере получается учетная запись пользователя с именем AdminContoso02.</span><span class="sxs-lookup"><span data-stu-id="448f6-115">This example gets a user account named AdminContoso02.</span></span>

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### <span data-ttu-id="448f6-116">Пример 2. Получение учетной записи, подключенной к учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="448f6-116">Example 2: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="448f6-117">В этом примере возвращается учетная запись пользователя, подключенная к учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="448f6-117">This example gets a user account that is connected to a Microsoft account.</span></span> <span data-ttu-id="448f6-118">В этом примере используется значение заполнителя для имени пользователя учетной записи в Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="448f6-118">This example uses a placeholder value for the username of an account at Outlook.com.</span></span>

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### <span data-ttu-id="448f6-119">Пример 3. Получение учетной записи, подключенной к учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="448f6-119">Example 3: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="448f6-120">В этом примере возвращается локальная учетная запись пользователя с указанным идентификатором SID.</span><span class="sxs-lookup"><span data-stu-id="448f6-120">This example gets a local user account that has the specified SID.</span></span>

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## <span data-ttu-id="448f6-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="448f6-121">PARAMETERS</span></span>

### <span data-ttu-id="448f6-122">-Name</span><span class="sxs-lookup"><span data-stu-id="448f6-122">-Name</span></span>

<span data-ttu-id="448f6-123">Указывает массив имен учетных записей пользователей, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="448f6-123">Specifies an array of names of user accounts that this cmdlet gets.</span></span> <span data-ttu-id="448f6-124">Можно использовать подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="448f6-124">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="448f6-125">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="448f6-125">-SID</span></span>

<span data-ttu-id="448f6-126">Указывает массив идентификаторов безопасности (SID) учетных записей пользователей, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="448f6-126">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet gets.</span></span>

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

### <span data-ttu-id="448f6-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="448f6-127">CommonParameters</span></span>

<span data-ttu-id="448f6-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="448f6-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="448f6-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="448f6-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="448f6-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="448f6-130">INPUTS</span></span>

### <span data-ttu-id="448f6-131">System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="448f6-131">System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="448f6-132">В этот командлет можно передать строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="448f6-132">You can pipe a string or SID to this cmdlet.</span></span>

## <span data-ttu-id="448f6-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="448f6-133">OUTPUTS</span></span>

### <span data-ttu-id="448f6-134">System. Management. Automation. Секуритяккаунтсманажер. LocalUser []</span><span class="sxs-lookup"><span data-stu-id="448f6-134">System.Management.Automation.SecurityAccountsManager.LocalUser[]</span></span>

<span data-ttu-id="448f6-135">Этот командлет возвращает локальные учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="448f6-135">This cmdlet returns local user accounts.</span></span>

## <span data-ttu-id="448f6-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="448f6-136">NOTES</span></span>

<span data-ttu-id="448f6-137">Свойство **принЦипалсаурце** объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** описывает источник объекта.</span><span class="sxs-lookup"><span data-stu-id="448f6-137">The **PrincipalSource** property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects describes the source of the object.</span></span> <span data-ttu-id="448f6-138">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="448f6-138">The possible sources are as follows:</span></span>

- <span data-ttu-id="448f6-139">Локальная</span><span class="sxs-lookup"><span data-stu-id="448f6-139">Local</span></span>
- <span data-ttu-id="448f6-140">Active Directory</span><span class="sxs-lookup"><span data-stu-id="448f6-140">Active Directory</span></span>
- <span data-ttu-id="448f6-141">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="448f6-141">Azure Active Directory group</span></span>
- <span data-ttu-id="448f6-142">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="448f6-142">Microsoft Account</span></span>

<span data-ttu-id="448f6-143">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="448f6-143">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="448f6-144">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="448f6-144">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="448f6-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="448f6-145">RELATED LINKS</span></span>

[<span data-ttu-id="448f6-146">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-146">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="448f6-147">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-147">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="448f6-148">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-148">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="448f6-149">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-149">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="448f6-150">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-150">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="448f6-151">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="448f6-151">Set-LocalUser</span></span>](Set-LocalUser.md)

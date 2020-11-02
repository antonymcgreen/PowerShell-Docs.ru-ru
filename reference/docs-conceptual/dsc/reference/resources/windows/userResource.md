---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс User в DSC
description: Ресурс User в DSC
ms.openlocfilehash: b14f8d434ef3e1eb220fe7b0b18a011014c9ae6c
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142606"
---
# <a name="dsc-user-resource"></a><span data-ttu-id="1b694-103">Ресурс User в DSC</span><span class="sxs-lookup"><span data-stu-id="1b694-103">DSC User Resource</span></span>

> <span data-ttu-id="1b694-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1b694-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="1b694-105">Ресурс **User** в DSC Windows PowerShell предоставляет механизм управления локальными учетными записями на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="1b694-105">The **User** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="1b694-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b694-106">Syntax</span></span>

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1b694-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1b694-107">Properties</span></span>

|<span data-ttu-id="1b694-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="1b694-108">Property</span></span> |<span data-ttu-id="1b694-109">Description</span><span class="sxs-lookup"><span data-stu-id="1b694-109">Description</span></span> |
|---|---|
|<span data-ttu-id="1b694-110">UserName</span><span class="sxs-lookup"><span data-stu-id="1b694-110">UserName</span></span> |<span data-ttu-id="1b694-111">Указывает имя учетной записи, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="1b694-111">Indicates the account name for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="1b694-112">Description</span><span class="sxs-lookup"><span data-stu-id="1b694-112">Description</span></span> |<span data-ttu-id="1b694-113">Указывает описание учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b694-113">Indicates the description you want to use for the user account.</span></span> |
|<span data-ttu-id="1b694-114">Выключено</span><span class="sxs-lookup"><span data-stu-id="1b694-114">Disabled</span></span> |<span data-ttu-id="1b694-115">Указывает, включена ли учетная запись.</span><span class="sxs-lookup"><span data-stu-id="1b694-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="1b694-116">Присвойте этому свойству значение `$true`, чтобы отключить учетную запись, и `$false`, чтобы включить ее.</span><span class="sxs-lookup"><span data-stu-id="1b694-116">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="1b694-117">FullName</span><span class="sxs-lookup"><span data-stu-id="1b694-117">FullName</span></span> |<span data-ttu-id="1b694-118">Представляет строку с полным именем для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b694-118">Represents a string with the full name you want to use for the user account.</span></span> |
|<span data-ttu-id="1b694-119">Пароль</span><span class="sxs-lookup"><span data-stu-id="1b694-119">Password</span></span> |<span data-ttu-id="1b694-120">Указывает пароль для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1b694-120">Indicates the password you want to use for this account.</span></span> |
|<span data-ttu-id="1b694-121">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="1b694-121">PasswordChangeNotAllowed</span></span> |<span data-ttu-id="1b694-122">Указывает, может ли пользователь изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="1b694-122">Indicates if the user can change the password.</span></span> <span data-ttu-id="1b694-123">Присвойте этому свойству значение `$true`, чтобы пользователь не мог изменить пароль, и `$false`, чтобы мог.</span><span class="sxs-lookup"><span data-stu-id="1b694-123">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="1b694-124">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="1b694-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="1b694-125">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="1b694-125">PasswordChangeRequired</span></span> |<span data-ttu-id="1b694-126">Указывает, требуется ли смена пароля при следующем входе пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="1b694-126">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="1b694-127">Присвойте этому свойству значение `$true`, если пользователь должен изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="1b694-127">Set this property to `$true` if the user must change the password.</span></span> <span data-ttu-id="1b694-128">Значение по умолчанию — `$true`.</span><span class="sxs-lookup"><span data-stu-id="1b694-128">The default value is `$true`.</span></span> |
|<span data-ttu-id="1b694-129">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="1b694-129">PasswordNeverExpires</span></span> |<span data-ttu-id="1b694-130">Указывает, может ли истечь срок действия пароля.</span><span class="sxs-lookup"><span data-stu-id="1b694-130">Indicates if the password will expire.</span></span> <span data-ttu-id="1b694-131">Присвойте этому свойству значение `$true`, чтобы срок действия пароля никогда не истекал.</span><span class="sxs-lookup"><span data-stu-id="1b694-131">To ensure that the password for this account will never expire, set this property to `$true`.</span></span> <span data-ttu-id="1b694-132">Задайте значение `$false`, чтобы ограничить срок действия пароля.</span><span class="sxs-lookup"><span data-stu-id="1b694-132">Set it to `$false` if the password will expire.</span></span> <span data-ttu-id="1b694-133">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="1b694-133">The default value is `$false`.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1b694-134">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="1b694-134">Common properties</span></span>

|<span data-ttu-id="1b694-135">Свойство</span><span class="sxs-lookup"><span data-stu-id="1b694-135">Property</span></span> |<span data-ttu-id="1b694-136">Description</span><span class="sxs-lookup"><span data-stu-id="1b694-136">Description</span></span> |
|---|---|
|<span data-ttu-id="1b694-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1b694-137">DependsOn</span></span> |<span data-ttu-id="1b694-138">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="1b694-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1b694-139">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1b694-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1b694-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="1b694-140">Ensure</span></span> |<span data-ttu-id="1b694-141">Указывает, существует ли учетная запись.</span><span class="sxs-lookup"><span data-stu-id="1b694-141">Indicates if the account exists.</span></span> <span data-ttu-id="1b694-142">Присвойте этому свойству значение **Present** , чтобы гарантировать, что учетная запись существует, и **Absent** в противном случае.</span><span class="sxs-lookup"><span data-stu-id="1b694-142">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> <span data-ttu-id="1b694-143">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="1b694-143">The default value is **Present** .</span></span> |
|<span data-ttu-id="1b694-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1b694-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="1b694-145">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="1b694-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1b694-146">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1b694-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1b694-147">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="1b694-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="1b694-148">Пример</span><span class="sxs-lookup"><span data-stu-id="1b694-148">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```

---
external help file: Microsoft.PowerShell.Utility-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 5c8e963486c0d4f5f3e7d643cb65c752720f37d1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600007"
---
# <span data-ttu-id="856e1-102">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="856e1-102">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="856e1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="856e1-103">SYNOPSIS</span></span>
<span data-ttu-id="856e1-104">Преобразует строку SDDL в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="856e1-104">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="856e1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="856e1-105">SYNTAX</span></span>

### <span data-ttu-id="856e1-106">Все</span><span class="sxs-lookup"><span data-stu-id="856e1-106">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="856e1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="856e1-107">DESCRIPTION</span></span>

<span data-ttu-id="856e1-108">`ConvertFrom-SddlString`Командлет преобразует строку языка определения дескрипторов безопасности в пользовательский объект **PSCustomObject** со следующими свойствами: owner, Group, дискретионарякл, системакл и равдескриптор.</span><span class="sxs-lookup"><span data-stu-id="856e1-108">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="856e1-109">Свойства Owner, Group, Дискретионарякл и Системакл содержат доступное для чтения текстовое представление прав доступа, указанных в строке SDDL.</span><span class="sxs-lookup"><span data-stu-id="856e1-109">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="856e1-110">Этот командлет появился в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="856e1-110">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="856e1-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="856e1-111">EXAMPLES</span></span>

### <span data-ttu-id="856e1-112">Пример 1. Преобразование SDDL прав доступа файловой системы в PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="856e1-112">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="856e1-113">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для папки C:\Windows и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="856e1-113">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="856e1-114">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="856e1-114">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="856e1-115">Пример 2. Преобразование SDDL для прав доступа к реестру в PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="856e1-115">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="856e1-116">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="856e1-116">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="856e1-117">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="856e1-117">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="856e1-118">Он использует `-Type` параметр, чтобы указать, что строка SDDL представляет дескриптор безопасности реестра.</span><span class="sxs-lookup"><span data-stu-id="856e1-118">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="856e1-119">Пример 3. Преобразование SDDL для прав доступа к реестру в PSCustomObject с помощью ConvertFrom-SddlString с параметром и без него `-Type`</span><span class="sxs-lookup"><span data-stu-id="856e1-119">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="856e1-120">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="856e1-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="856e1-121">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="856e1-121">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="856e1-122">Он не использует `-Type` параметр, поэтому отображаются права доступа для файловой системы.</span><span class="sxs-lookup"><span data-stu-id="856e1-122">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="856e1-123">Третья команда использует `ConvertFrom-SddlString` командлет с `-Type` параметром, поэтому возвращенные права доступа предназначены для реестра.</span><span class="sxs-lookup"><span data-stu-id="856e1-123">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="856e1-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="856e1-124">PARAMETERS</span></span>

### <span data-ttu-id="856e1-125">— SDDL</span><span class="sxs-lookup"><span data-stu-id="856e1-125">-Sddl</span></span>

<span data-ttu-id="856e1-126">Указывает строку, представляющую дескриптор безопасности в синтаксисе SDDL.</span><span class="sxs-lookup"><span data-stu-id="856e1-126">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="856e1-127">-Type</span><span class="sxs-lookup"><span data-stu-id="856e1-127">-Type</span></span>

<span data-ttu-id="856e1-128">Указывает тип прав, которые представляет строка SDDL.</span><span class="sxs-lookup"><span data-stu-id="856e1-128">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="856e1-129">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="856e1-129">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="856e1-130">филесистемригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-130">FileSystemRights</span></span>
- <span data-ttu-id="856e1-131">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="856e1-131">RegistryRights</span></span>
- <span data-ttu-id="856e1-132">активедиректориригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-132">ActiveDirectoryRights</span></span>
- <span data-ttu-id="856e1-133">мутексригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-133">MutexRights</span></span>
- <span data-ttu-id="856e1-134">семафореригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-134">SemaphoreRights</span></span>
- <span data-ttu-id="856e1-135">криптокэйригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-135">CryptoKeyRights</span></span>
- <span data-ttu-id="856e1-136">евентваисандлеригхтс</span><span class="sxs-lookup"><span data-stu-id="856e1-136">EventWaitHandleRights</span></span>

<span data-ttu-id="856e1-137">По умолчанию командлет использует права файловой системы.</span><span class="sxs-lookup"><span data-stu-id="856e1-137">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="856e1-138">Криптокэйригхтс и Активедиректориригхтс не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="856e1-138">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="856e1-139">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="856e1-139">CommonParameters</span></span>

<span data-ttu-id="856e1-140">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="856e1-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="856e1-141">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="856e1-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="856e1-142">Входные данные</span><span class="sxs-lookup"><span data-stu-id="856e1-142">INPUTS</span></span>

### <span data-ttu-id="856e1-143">System.String</span><span class="sxs-lookup"><span data-stu-id="856e1-143">System.String</span></span>

<span data-ttu-id="856e1-144">Строку SDDL можно передать в `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="856e1-144">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="856e1-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="856e1-145">OUTPUTS</span></span>

## <span data-ttu-id="856e1-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="856e1-146">NOTES</span></span>

<span data-ttu-id="856e1-147">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="856e1-147">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="856e1-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="856e1-148">RELATED LINKS</span></span>

[<span data-ttu-id="856e1-149">Язык определения дескрипторов безопасности</span><span class="sxs-lookup"><span data-stu-id="856e1-149">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)

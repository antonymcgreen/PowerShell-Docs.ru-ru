---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 128a86312f424eaf9dcfb6cdc97ebd3e148c7886
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "93230569"
---
# <span data-ttu-id="3a54d-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="3a54d-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="3a54d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3a54d-104">SYNOPSIS</span></span>

<span data-ttu-id="3a54d-105">Преобразует строку SDDL в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="3a54d-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="3a54d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a54d-106">SYNTAX</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <Object>] [<CommonParameters>]
```

## <span data-ttu-id="3a54d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a54d-107">DESCRIPTION</span></span>

<span data-ttu-id="3a54d-108">`ConvertFrom-SddlString`Командлет преобразует строку языка определения дескрипторов безопасности в пользовательский объект **PSCustomObject** со следующими свойствами: owner, Group, дискретионарякл, системакл и равдескриптор.</span><span class="sxs-lookup"><span data-stu-id="3a54d-108">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="3a54d-109">Свойства Owner, Group, Дискретионарякл и Системакл содержат доступное для чтения текстовое представление прав доступа, указанных в строке SDDL.</span><span class="sxs-lookup"><span data-stu-id="3a54d-109">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="3a54d-110">Этот командлет появился в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="3a54d-110">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="3a54d-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3a54d-111">EXAMPLES</span></span>

### <span data-ttu-id="3a54d-112">Пример 1. Преобразование SDDL прав доступа файловой системы в PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="3a54d-112">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="3a54d-113">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для папки C:\Windows и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="3a54d-113">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="3a54d-114">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a54d-114">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="3a54d-115">Пример 2. Преобразование SDDL для прав доступа к реестру в PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="3a54d-115">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="3a54d-116">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="3a54d-116">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="3a54d-117">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a54d-117">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="3a54d-118">Он использует `-Type` параметр, чтобы указать, что строка SDDL представляет дескриптор безопасности реестра.</span><span class="sxs-lookup"><span data-stu-id="3a54d-118">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="3a54d-119">Пример 3. Преобразование SDDL для прав доступа к реестру в PSCustomObject с помощью ConvertFrom-SddlString с параметром и без него `-Type`</span><span class="sxs-lookup"><span data-stu-id="3a54d-119">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="3a54d-120">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="3a54d-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="3a54d-121">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a54d-121">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="3a54d-122">Он не использует `-Type` параметр, поэтому отображаются права доступа для файловой системы.</span><span class="sxs-lookup"><span data-stu-id="3a54d-122">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="3a54d-123">Третья команда использует `ConvertFrom-SddlString` командлет с `-Type` параметром, поэтому возвращенные права доступа предназначены для реестра.</span><span class="sxs-lookup"><span data-stu-id="3a54d-123">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

### <span data-ttu-id="3a54d-124">Пример 4. Преобразование SDDL Active Directory прав доступа в PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="3a54d-124">Example 4: Convert Active Directory access rights SDDL to a PSCustomObject</span></span>

```powershell
$user = [ADSI]"LDAP://CN=username,CN=Users,DC=domain,DC=com"
ConvertFrom-SddlString $user.psbase.ObjectSecurity.Sddl -Type ActiveDirectoryRights
```

<span data-ttu-id="3a54d-125">Первая команда использует интерфейсы служб Active Directory (ADSI) для получения объекта пользователя и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="3a54d-125">The first command uses Active Directory Service Interfaces (ADSI) to get the user object and saves it in the variable.</span></span>

<span data-ttu-id="3a54d-126">Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a54d-126">The second command uses the `ConvertFrom-SddlString` cmdlet to get text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="3a54d-127">Он использует `-Type` параметр, чтобы указать, что строка SDDL представляет Active Directory дескрипторе безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a54d-127">It uses the `-Type` parameter to specify that SDDL string represents an Active Directory security descriptor.</span></span>

## <span data-ttu-id="3a54d-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a54d-128">PARAMETERS</span></span>

### <span data-ttu-id="3a54d-129">— SDDL</span><span class="sxs-lookup"><span data-stu-id="3a54d-129">-Sddl</span></span>

<span data-ttu-id="3a54d-130">Указывает строку, представляющую дескриптор безопасности в синтаксисе SDDL.</span><span class="sxs-lookup"><span data-stu-id="3a54d-130">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

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

### <span data-ttu-id="3a54d-131">-Type</span><span class="sxs-lookup"><span data-stu-id="3a54d-131">-Type</span></span>

<span data-ttu-id="3a54d-132">Указывает тип прав, которые представляет строка SDDL.</span><span class="sxs-lookup"><span data-stu-id="3a54d-132">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="3a54d-133">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3a54d-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3a54d-134">филесистемригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-134">FileSystemRights</span></span>
- <span data-ttu-id="3a54d-135">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="3a54d-135">RegistryRights</span></span>
- <span data-ttu-id="3a54d-136">активедиректориригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-136">ActiveDirectoryRights</span></span>
- <span data-ttu-id="3a54d-137">мутексригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-137">MutexRights</span></span>
- <span data-ttu-id="3a54d-138">семафореригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-138">SemaphoreRights</span></span>
- <span data-ttu-id="3a54d-139">криптокэйригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-139">CryptoKeyRights</span></span>
- <span data-ttu-id="3a54d-140">евентваисандлеригхтс</span><span class="sxs-lookup"><span data-stu-id="3a54d-140">EventWaitHandleRights</span></span>

<span data-ttu-id="3a54d-141">По умолчанию командлет использует права файловой системы.</span><span class="sxs-lookup"><span data-stu-id="3a54d-141">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="3a54d-142">Криптокэйригхтс и Активедиректориригхтс не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="3a54d-142">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3a54d-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3a54d-143">CommonParameters</span></span>
<span data-ttu-id="3a54d-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a54d-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a54d-145">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a54d-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a54d-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3a54d-146">INPUTS</span></span>

### <span data-ttu-id="3a54d-147">System.String</span><span class="sxs-lookup"><span data-stu-id="3a54d-147">System.String</span></span>

<span data-ttu-id="3a54d-148">Строку SDDL можно передать в `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="3a54d-148">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="3a54d-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3a54d-149">OUTPUTS</span></span>

## <span data-ttu-id="3a54d-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3a54d-150">NOTES</span></span>

## <span data-ttu-id="3a54d-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3a54d-151">RELATED LINKS</span></span>

[<span data-ttu-id="3a54d-152">Язык определения дескрипторов безопасности</span><span class="sxs-lookup"><span data-stu-id="3a54d-152">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 0481526aead285e3d5fb494218d1573e03216f2e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604656"
---
# <span data-ttu-id="e5102-102">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-102">Resolve-Path</span></span>

## <span data-ttu-id="e5102-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e5102-103">SYNOPSIS</span></span>
<span data-ttu-id="e5102-104">Разрешает подстановочные знаки в пути и отображает содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="e5102-104">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="e5102-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5102-105">SYNTAX</span></span>

### <span data-ttu-id="e5102-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e5102-106">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="e5102-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e5102-107">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="e5102-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5102-108">DESCRIPTION</span></span>

<span data-ttu-id="e5102-109">`Resolve-Path`Командлет отображает элементы и контейнеры, которые соответствуют шаблону подстановочного знака в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="e5102-109">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="e5102-110">Соответствие может включать файлы, папки, разделы реестра или любой другой объект, доступный поставщику PSDrive.</span><span class="sxs-lookup"><span data-stu-id="e5102-110">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="e5102-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="e5102-111">EXAMPLES</span></span>

### <span data-ttu-id="e5102-112">Пример 1. разрешение пути к домашней папке</span><span class="sxs-lookup"><span data-stu-id="e5102-112">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="e5102-113">Символ тильды (~) является сокращенной записью для домашней папки текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5102-113">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="e5102-114">В этом примере показано `Resolve-Path` возвращение полного значения пути.</span><span class="sxs-lookup"><span data-stu-id="e5102-114">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="e5102-115">Пример 2. разрешение пути к папке Windows</span><span class="sxs-lookup"><span data-stu-id="e5102-115">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="e5102-116">При запуске из корня диска C: Эта команда возвращает путь к папке Windows на диске C:.</span><span class="sxs-lookup"><span data-stu-id="e5102-116">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="e5102-117">Пример 3. получение всех путей в папке Windows</span><span class="sxs-lookup"><span data-stu-id="e5102-117">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="e5102-118">Эта команда возвращает все папки в папке C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="e5102-118">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="e5102-119">Команда использует оператор конвейера (|) для отправки строки пути в `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="e5102-119">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="e5102-120">Пример 4. разрешение пути UNC</span><span class="sxs-lookup"><span data-stu-id="e5102-120">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="e5102-121">Эта команда разрешает UNC-путь и возвращает ресурсы совместного использования этого пути.</span><span class="sxs-lookup"><span data-stu-id="e5102-121">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="e5102-122">Пример 5. получение относительных путей</span><span class="sxs-lookup"><span data-stu-id="e5102-122">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="e5102-123">Эта команда возвращает относительные пути для каталогов в корне диска C:.</span><span class="sxs-lookup"><span data-stu-id="e5102-123">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="e5102-124">Пример 6. разрешение пути, содержащего скобки</span><span class="sxs-lookup"><span data-stu-id="e5102-124">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="e5102-125">В этом примере используется параметр **LiteralPath** для разрешения пути к \[ \] вложенной папке test XML.</span><span class="sxs-lookup"><span data-stu-id="e5102-125">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="e5102-126">Использование **LiteralPath** приводит к тому, что квадратные скобки интерпретируются как обычные символы, а не как регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="e5102-126">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="e5102-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5102-127">PARAMETERS</span></span>

### <span data-ttu-id="e5102-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="e5102-128">-Credential</span></span>

<span data-ttu-id="e5102-129">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="e5102-129">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="e5102-130">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="e5102-130">The default is the current user.</span></span>

<span data-ttu-id="e5102-131">Введите имя пользователя, например User01 или Domain01\User01, или передайте объект **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="e5102-131">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="e5102-132">Объект **PSCredential** можно создать с помощью `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="e5102-132">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e5102-133">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="e5102-133">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="e5102-134">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5102-134">This parameter is not supported by any providers installed with PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e5102-135">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e5102-135">-LiteralPath</span></span>

<span data-ttu-id="e5102-136">Указывает преобразуемый путь, который требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="e5102-136">Specifies the path to be resolved.</span></span>
<span data-ttu-id="e5102-137">Значение параметра **LiteralPath** используется в точности как типизированное.</span><span class="sxs-lookup"><span data-stu-id="e5102-137">The value of the **LiteralPath** parameter is used exactly as typed.</span></span>
<span data-ttu-id="e5102-138">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e5102-138">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="e5102-139">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e5102-139">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="e5102-140">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="e5102-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e5102-141">-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-141">-Path</span></span>

<span data-ttu-id="e5102-142">Указывает путь PowerShell для разрешения.</span><span class="sxs-lookup"><span data-stu-id="e5102-142">Specifies the PowerShell path to resolve.</span></span>
<span data-ttu-id="e5102-143">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e5102-143">This parameter is required.</span></span>
<span data-ttu-id="e5102-144">Можно также передать строку пути в `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="e5102-144">You can also pipe a path string to `Resolve-Path`.</span></span>
<span data-ttu-id="e5102-145">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e5102-145">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e5102-146">Относительное</span><span class="sxs-lookup"><span data-stu-id="e5102-146">-Relative</span></span>

<span data-ttu-id="e5102-147">Указывает, что этот командлет возвращает относительный путь.</span><span class="sxs-lookup"><span data-stu-id="e5102-147">Indicates that this cmdlet returns a relative path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5102-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e5102-148">CommonParameters</span></span>

<span data-ttu-id="e5102-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5102-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5102-150">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e5102-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e5102-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e5102-151">INPUTS</span></span>

### <span data-ttu-id="e5102-152">System.String</span><span class="sxs-lookup"><span data-stu-id="e5102-152">System.String</span></span>

<span data-ttu-id="e5102-153">Строку, содержащую путь к этому командлету, можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e5102-153">You can pipe a string that contains a path to this cmdlet</span></span>

## <span data-ttu-id="e5102-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e5102-154">OUTPUTS</span></span>

### <span data-ttu-id="e5102-155">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="e5102-155">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="e5102-156">Возвращает объект **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="e5102-156">Returns a **PathInfo** object.</span></span> <span data-ttu-id="e5102-157">Возвращает строковое значение для разрешенного пути, если указан **относительный** параметр.</span><span class="sxs-lookup"><span data-stu-id="e5102-157">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="e5102-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e5102-158">NOTES</span></span>

<span data-ttu-id="e5102-159">`*-Path`Командлеты работают с файловой системой, реестром и поставщиками сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e5102-159">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="e5102-160">`Resolve-Path` предназначен для работы с любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="e5102-160">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="e5102-161">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="e5102-161">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="e5102-162">Дополнительные сведения см. в разделе [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="e5102-162">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="e5102-163">`Resolve-Path` разрешает только существующие пути.</span><span class="sxs-lookup"><span data-stu-id="e5102-163">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="e5102-164">Его нельзя использовать для разрешения несуществующего расположения.</span><span class="sxs-lookup"><span data-stu-id="e5102-164">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="e5102-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e5102-165">RELATED LINKS</span></span>

[<span data-ttu-id="e5102-166">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-166">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="e5102-167">Join-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-167">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="e5102-168">Split-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-168">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="e5102-169">Test-Path</span><span class="sxs-lookup"><span data-stu-id="e5102-169">Test-Path</span></span>](Test-Path.md)


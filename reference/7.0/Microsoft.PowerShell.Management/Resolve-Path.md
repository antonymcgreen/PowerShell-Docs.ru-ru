---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 6e52bec2a26d0776887bcc8814459d3a8baca042
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226093"
---
# <span data-ttu-id="3ac6f-103">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-103">Resolve-Path</span></span>

## <span data-ttu-id="3ac6f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3ac6f-104">SYNOPSIS</span></span>
<span data-ttu-id="3ac6f-105">Разрешает подстановочные знаки в пути и отображает содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-105">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="3ac6f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ac6f-106">SYNTAX</span></span>

### <span data-ttu-id="3ac6f-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3ac6f-107">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="3ac6f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3ac6f-108">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="3ac6f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ac6f-109">DESCRIPTION</span></span>

<span data-ttu-id="3ac6f-110">`Resolve-Path`Командлет отображает элементы и контейнеры, которые соответствуют шаблону подстановочного знака в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-110">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="3ac6f-111">Соответствие может включать файлы, папки, разделы реестра или любой другой объект, доступный поставщику PSDrive.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-111">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="3ac6f-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ac6f-112">EXAMPLES</span></span>

### <span data-ttu-id="3ac6f-113">Пример 1. разрешение пути к домашней папке</span><span class="sxs-lookup"><span data-stu-id="3ac6f-113">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="3ac6f-114">Символ тильды (~) является сокращенной записью для домашней папки текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-114">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="3ac6f-115">В этом примере показано `Resolve-Path` возвращение полного значения пути.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-115">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="3ac6f-116">Пример 2. разрешение пути к папке Windows</span><span class="sxs-lookup"><span data-stu-id="3ac6f-116">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="3ac6f-117">При запуске из корня диска C: Эта команда возвращает путь к папке Windows на диске C:.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-117">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="3ac6f-118">Пример 3. получение всех путей в папке Windows</span><span class="sxs-lookup"><span data-stu-id="3ac6f-118">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="3ac6f-119">Эта команда возвращает все папки в папке C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-119">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="3ac6f-120">Команда использует оператор конвейера (|) для отправки строки пути в `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="3ac6f-120">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="3ac6f-121">Пример 4. разрешение пути UNC</span><span class="sxs-lookup"><span data-stu-id="3ac6f-121">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="3ac6f-122">Эта команда разрешает UNC-путь и возвращает ресурсы совместного использования этого пути.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-122">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="3ac6f-123">Пример 5. получение относительных путей</span><span class="sxs-lookup"><span data-stu-id="3ac6f-123">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="3ac6f-124">Эта команда возвращает относительные пути для каталогов в корне диска C:.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-124">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="3ac6f-125">Пример 6. разрешение пути, содержащего скобки</span><span class="sxs-lookup"><span data-stu-id="3ac6f-125">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="3ac6f-126">В этом примере используется параметр **LiteralPath** для разрешения пути к \[ \] вложенной папке test XML.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-126">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="3ac6f-127">Использование **LiteralPath** приводит к тому, что квадратные скобки интерпретируются как обычные символы, а не как регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-127">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="3ac6f-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ac6f-128">PARAMETERS</span></span>

### <span data-ttu-id="3ac6f-129">-Credential</span><span class="sxs-lookup"><span data-stu-id="3ac6f-129">-Credential</span></span>

<span data-ttu-id="3ac6f-130">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-130">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="3ac6f-131">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-131">The default is the current user.</span></span>

<span data-ttu-id="3ac6f-132">Введите имя пользователя, например User01 или Domain01\User01, или передайте объект **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="3ac6f-132">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="3ac6f-133">Объект **PSCredential** можно создать с помощью `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-133">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3ac6f-134">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-134">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="3ac6f-135">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-135">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="3ac6f-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3ac6f-136">-LiteralPath</span></span>

<span data-ttu-id="3ac6f-137">Указывает преобразуемый путь, который требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-137">Specifies the path to be resolved.</span></span> <span data-ttu-id="3ac6f-138">Значение параметра **LiteralPath** используется в точности как типизированное.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-138">The value of the **LiteralPath** parameter is used exactly as typed.</span></span> <span data-ttu-id="3ac6f-139">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-139">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="3ac6f-140">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3ac6f-141">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3ac6f-142">-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-142">-Path</span></span>

<span data-ttu-id="3ac6f-143">Указывает путь PowerShell для разрешения.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-143">Specifies the PowerShell path to resolve.</span></span> <span data-ttu-id="3ac6f-144">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-144">This parameter is required.</span></span> <span data-ttu-id="3ac6f-145">Можно также передать строку пути в `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="3ac6f-145">You can also pipe a path string to `Resolve-Path`.</span></span> <span data-ttu-id="3ac6f-146">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-146">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3ac6f-147">Относительное</span><span class="sxs-lookup"><span data-stu-id="3ac6f-147">-Relative</span></span>

<span data-ttu-id="3ac6f-148">Указывает, что этот командлет возвращает относительный путь.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-148">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="3ac6f-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3ac6f-149">CommonParameters</span></span>

<span data-ttu-id="3ac6f-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ac6f-151">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3ac6f-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3ac6f-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3ac6f-152">INPUTS</span></span>

### <span data-ttu-id="3ac6f-153">System.String</span><span class="sxs-lookup"><span data-stu-id="3ac6f-153">System.String</span></span>

<span data-ttu-id="3ac6f-154">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-154">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="3ac6f-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3ac6f-155">OUTPUTS</span></span>

### <span data-ttu-id="3ac6f-156">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="3ac6f-156">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="3ac6f-157">Возвращает объект **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="3ac6f-157">Returns a **PathInfo** object.</span></span> <span data-ttu-id="3ac6f-158">Возвращает строковое значение для разрешенного пути, если указан **относительный** параметр.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-158">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="3ac6f-159">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3ac6f-159">NOTES</span></span>

<span data-ttu-id="3ac6f-160">`*-Path`Командлеты работают с файловой системой, реестром и поставщиками сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-160">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="3ac6f-161">`Resolve-Path` предназначен для работы с любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-161">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="3ac6f-162">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-162">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3ac6f-163">Дополнительные сведения см. в разделе [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="3ac6f-163">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="3ac6f-164">`Resolve-Path` разрешает только существующие пути.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-164">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="3ac6f-165">Его нельзя использовать для разрешения несуществующего расположения.</span><span class="sxs-lookup"><span data-stu-id="3ac6f-165">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="3ac6f-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3ac6f-166">RELATED LINKS</span></span>

[<span data-ttu-id="3ac6f-167">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-167">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="3ac6f-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-168">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="3ac6f-169">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-169">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="3ac6f-170">Test-Path</span><span class="sxs-lookup"><span data-stu-id="3ac6f-170">Test-Path</span></span>](Test-Path.md)

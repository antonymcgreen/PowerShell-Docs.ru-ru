---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: 5d92acbe080b0d232047f1184c9a369b8837845c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227865"
---
# <span data-ttu-id="79af3-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-103">Split-Path</span></span>

## <span data-ttu-id="79af3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="79af3-104">SYNOPSIS</span></span>
<span data-ttu-id="79af3-105">Возвращает указанную часть пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="79af3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="79af3-106">SYNTAX</span></span>

### <span data-ttu-id="79af3-107">Родительский элемент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="79af3-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="79af3-108">нокуалифиерсет</span><span class="sxs-lookup"><span data-stu-id="79af3-108">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="79af3-109">Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="79af3-109">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="79af3-110">куалифиерсет</span><span class="sxs-lookup"><span data-stu-id="79af3-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-Qualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="79af3-111">Absolute</span><span class="sxs-lookup"><span data-stu-id="79af3-111">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="79af3-112">литералпассет</span><span class="sxs-lookup"><span data-stu-id="79af3-112">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="79af3-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="79af3-113">DESCRIPTION</span></span>

<span data-ttu-id="79af3-114">Командлет **Split-Path** возвращает только указанную часть пути, например родительскую папку, подпапку или имя файла.</span><span class="sxs-lookup"><span data-stu-id="79af3-114">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="79af3-115">Он также может получать элементы, на которые ссылается Split Path, и определять, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="79af3-115">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="79af3-116">Этот командлет можно использовать для получения или отправки только выбранной части пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-116">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="79af3-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="79af3-117">EXAMPLES</span></span>

### <span data-ttu-id="79af3-118">Пример 1. получение квалификатора пути</span><span class="sxs-lookup"><span data-stu-id="79af3-118">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="79af3-119">Эта команда возвращает только квалификатор пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-119">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="79af3-120">Квалификатор — это диск.</span><span class="sxs-lookup"><span data-stu-id="79af3-120">The qualifier is the drive.</span></span>

### <span data-ttu-id="79af3-121">Пример 2. Отображение имен файлов</span><span class="sxs-lookup"><span data-stu-id="79af3-121">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="79af3-122">Эта команда отображает файлы, на которые ссылается разделенный путь.</span><span class="sxs-lookup"><span data-stu-id="79af3-122">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="79af3-123">Поскольку этот путь разбивается на последний элемент, также известный как лист, команда отображает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="79af3-123">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="79af3-124">Параметр *Resolve* указывает **разделяемый путь** для отображения элементов, на которые ссылается путь разбиения, вместо отображения пути разбиения.</span><span class="sxs-lookup"><span data-stu-id="79af3-124">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="79af3-125">Как и все команды **с разделением пути** , эта команда возвращает строки.</span><span class="sxs-lookup"><span data-stu-id="79af3-125">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="79af3-126">Он не возвращает объекты **FileInfo** , представляющие файлы.</span><span class="sxs-lookup"><span data-stu-id="79af3-126">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="79af3-127">Пример 3. получение родительского контейнера</span><span class="sxs-lookup"><span data-stu-id="79af3-127">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="79af3-128">Эта команда возвращает только родительские контейнеры пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-128">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="79af3-129">Так как в нем не содержатся параметры для указания разбиения, **разделяемый путь** использует разворачивающееся расположение по умолчанию, которое является *родительским* .</span><span class="sxs-lookup"><span data-stu-id="79af3-129">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="79af3-130">Пример 4. определяет, является ли путь абсолютным</span><span class="sxs-lookup"><span data-stu-id="79af3-130">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="79af3-131">Эта команда определяет, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="79af3-131">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="79af3-132">В этом случае, поскольку путь задается относительно текущей папки, которая представляется точкой (.), она возвращает $False.</span><span class="sxs-lookup"><span data-stu-id="79af3-132">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="79af3-133">Пример 5. изменение расположения по указанному пути</span><span class="sxs-lookup"><span data-stu-id="79af3-133">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="79af3-134">Эта команда изменяет расположение на папку, содержащую профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79af3-134">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="79af3-135">Команда в круглых скобках использует **разделяемый путь** для возврата только родителя пути, хранящегося во встроенной $Profile переменной.</span><span class="sxs-lookup"><span data-stu-id="79af3-135">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="79af3-136">*Родительский* параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79af3-136">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="79af3-137">Поэтому его можно опустить из команды.</span><span class="sxs-lookup"><span data-stu-id="79af3-137">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="79af3-138">Круглые скобки указывают PowerShell для выполнения команды в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="79af3-138">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="79af3-139">Это удобный способ перехода в папку, имеющую длинное имя пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-139">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="79af3-140">Пример 6. разбиение пути с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="79af3-140">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="79af3-141">Эта команда использует конвейерный оператор (|) для отправки пути к **разделяемому пути** .</span><span class="sxs-lookup"><span data-stu-id="79af3-141">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="79af3-142">Заключенный в кавычки путь означает, что это единичный маркер.</span><span class="sxs-lookup"><span data-stu-id="79af3-142">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="79af3-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="79af3-143">PARAMETERS</span></span>

### <span data-ttu-id="79af3-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="79af3-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="79af3-145">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79af3-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="79af3-146">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="79af3-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="79af3-147">-Absolute</span><span class="sxs-lookup"><span data-stu-id="79af3-147">-IsAbsolute</span></span>

<span data-ttu-id="79af3-148">Указывает, что этот командлет возвращает $True, если путь является абсолютным, и $False, если он является относительным.</span><span class="sxs-lookup"><span data-stu-id="79af3-148">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="79af3-149">Абсолютный путь имеет длину больше нуля и не использует точку (.) для указания текущего пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-149">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-150">-Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="79af3-150">-Leaf</span></span>

<span data-ttu-id="79af3-151">Указывает, что этот командлет возвращает только последний элемент или контейнер в пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-151">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="79af3-152">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только Pass1. log.</span><span class="sxs-lookup"><span data-stu-id="79af3-152">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="79af3-153">-LiteralPath</span></span>

<span data-ttu-id="79af3-154">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="79af3-154">Specifies the paths to be split.</span></span>
<span data-ttu-id="79af3-155">В отличие от параметра *Path* , значение параметра *LiteralPath* используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="79af3-155">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="79af3-156">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="79af3-156">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="79af3-157">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="79af3-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="79af3-158">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="79af3-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-159">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="79af3-159">-NoQualifier</span></span>

<span data-ttu-id="79af3-160">Указывает, что этот командлет возвращает путь без квалификатора.</span><span class="sxs-lookup"><span data-stu-id="79af3-160">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="79af3-161">Для файловой системы или поставщиков реестра квалификатор —  диска в пути поставщика, например C: или HKCU:.</span><span class="sxs-lookup"><span data-stu-id="79af3-161">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="79af3-162">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только \Test\Logs\Pass1.log.</span><span class="sxs-lookup"><span data-stu-id="79af3-162">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-163">— Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="79af3-163">-Parent</span></span>

<span data-ttu-id="79af3-164">Указывает, что этот командлет возвращает только родительские контейнеры элемента или контейнера, заданного путем.</span><span class="sxs-lookup"><span data-stu-id="79af3-164">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="79af3-165">Например, в пути `C:\Test\Logs\Pass1.log` возвращается к:\тест\логс.</span><span class="sxs-lookup"><span data-stu-id="79af3-165">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="79af3-166">*Родительский* параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79af3-166">The *Parent* parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-167">-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-167">-Path</span></span>

<span data-ttu-id="79af3-168">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="79af3-168">Specifies the paths to be split.</span></span>
<span data-ttu-id="79af3-169">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="79af3-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="79af3-170">Если путь содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="79af3-170">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="79af3-171">Можно также передать по конвейеру путь к этому командлету.</span><span class="sxs-lookup"><span data-stu-id="79af3-171">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, NoQualifierSet, LeafSet, QualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="79af3-172">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="79af3-172">-Qualifier</span></span>

<span data-ttu-id="79af3-173">Указывает, что этот командлет возвращает только квалификатор указанного пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-173">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="79af3-174">Для файловой системы или поставщиков реестра квалификатор —  диска в пути поставщика, например C: или HKCU:.</span><span class="sxs-lookup"><span data-stu-id="79af3-174">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-175">-Разрешить</span><span class="sxs-lookup"><span data-stu-id="79af3-175">-Resolve</span></span>

<span data-ttu-id="79af3-176">Указывает, что этот командлет отображает элементы, на которые ссылается результирующий разделяемый путь, вместо отображения элементов пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-176">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="79af3-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="79af3-177">-UseTransaction</span></span>

<span data-ttu-id="79af3-178">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="79af3-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="79af3-179">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="79af3-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="79af3-180">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="79af3-180">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79af3-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="79af3-181">CommonParameters</span></span>

<span data-ttu-id="79af3-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="79af3-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="79af3-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="79af3-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="79af3-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="79af3-184">INPUTS</span></span>

### <span data-ttu-id="79af3-185">System.String</span><span class="sxs-lookup"><span data-stu-id="79af3-185">System.String</span></span>

<span data-ttu-id="79af3-186">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="79af3-186">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="79af3-187">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="79af3-187">OUTPUTS</span></span>

### <span data-ttu-id="79af3-188">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="79af3-188">System.String, System.Boolean</span></span>

<span data-ttu-id="79af3-189">**Разделяемый путь** возвращает текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="79af3-189">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="79af3-190">При указании параметра *Resolve* **Split-Path** возвращает строку, описывающую расположение элементов. Он не возвращает объекты, представляющие элементы, например, объект **FileInfo** или **RegistryKey** .</span><span class="sxs-lookup"><span data-stu-id="79af3-190">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="79af3-191">При указании параметра *Absolute* командлет **Split-Path** возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="79af3-191">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="79af3-192">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="79af3-192">NOTES</span></span>

* <span data-ttu-id="79af3-193">Параметры раздельного расположения ( *квалификатор* , *родительский элемент* , *конечный* объект и *квалификатор* ) являются эксклюзивными.</span><span class="sxs-lookup"><span data-stu-id="79af3-193">The split location parameters ( *Qualifier* , *Parent* , *Leaf* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="79af3-194">Можно использовать только один из них в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="79af3-194">You can use only one in each command.</span></span>

  <span data-ttu-id="79af3-195">Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79af3-195">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="79af3-196">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="79af3-196">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="79af3-197">Используйте их в том виде, в котором будут использоваться **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="79af3-197">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="79af3-198">Командлеты **path** можно использовать вместе с несколькими поставщиками.</span><span class="sxs-lookup"><span data-stu-id="79af3-198">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="79af3-199">К ним относятся файловая система, реестр и поставщики сертификатов.</span><span class="sxs-lookup"><span data-stu-id="79af3-199">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="79af3-200">**Разделяемый путь** предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="79af3-200">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="79af3-201">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="79af3-201">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="79af3-202">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="79af3-202">For more information, see about_Providers.</span></span>

## <span data-ttu-id="79af3-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="79af3-203">RELATED LINKS</span></span>

[<span data-ttu-id="79af3-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-204">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="79af3-205">Join-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-205">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="79af3-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-206">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="79af3-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="79af3-207">Test-Path</span></span>](Test-Path.md)

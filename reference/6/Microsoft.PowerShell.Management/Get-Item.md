---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 8483fd374ee973256633e3711322561fc14b8ae2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228833"
---
# <span data-ttu-id="a0e88-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-103">Get-Item</span></span>

## <span data-ttu-id="a0e88-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a0e88-104">SYNOPSIS</span></span>
<span data-ttu-id="a0e88-105">Получает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="a0e88-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="a0e88-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0e88-106">SYNTAX</span></span>

### <span data-ttu-id="a0e88-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a0e88-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a0e88-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a0e88-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a0e88-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0e88-109">DESCRIPTION</span></span>

<span data-ttu-id="a0e88-110">`Get-Item`Командлет возвращает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="a0e88-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="a0e88-111">Он не получает содержимое элемента в расположении, если только вы не используете подстановочный знак ( `*` ) для запроса всего содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="a0e88-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="a0e88-112">Этот командлет используется поставщиками PowerShell для перемещения по различным типам хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="a0e88-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="a0e88-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="a0e88-113">EXAMPLES</span></span>

### <span data-ttu-id="a0e88-114">Пример 1. Получение текущего каталога</span><span class="sxs-lookup"><span data-stu-id="a0e88-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="a0e88-115">В этом примере возвращается текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="a0e88-115">This example gets the current directory.</span></span> <span data-ttu-id="a0e88-116">Точка (".") представляет элемент в текущем расположении (а не его содержимом).</span><span class="sxs-lookup"><span data-stu-id="a0e88-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="a0e88-117">Пример 2. получение всех элементов в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="a0e88-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="a0e88-118">Этот пример возвращает все элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a0e88-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="a0e88-119">Символ-шаблон ( `*` ) представляет все содержимое текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="a0e88-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### <span data-ttu-id="a0e88-120">Пример 3. Получение текущего каталога диска</span><span class="sxs-lookup"><span data-stu-id="a0e88-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="a0e88-121">В этом примере возвращается текущий каталог `C:` диска.</span><span class="sxs-lookup"><span data-stu-id="a0e88-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="a0e88-122">Извлекаемый объект представляет только каталог, но не его содержимое.</span><span class="sxs-lookup"><span data-stu-id="a0e88-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="a0e88-123">Пример 4. Получение элементов на указанном диске</span><span class="sxs-lookup"><span data-stu-id="a0e88-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="a0e88-124">В этом примере выполняется получение элементов на `C:` диске.</span><span class="sxs-lookup"><span data-stu-id="a0e88-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="a0e88-125">Подстановочный знак ( `*` ) представляет все элементы в контейнере, а не только контейнер.</span><span class="sxs-lookup"><span data-stu-id="a0e88-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="a0e88-126">В PowerShell используйте одну звездочку ( `*` ) для получения содержимого вместо традиционной `*.*` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="a0e88-127">Формат интерпретируется буквально, поэтому `*.*` не извлекаются каталоги или имена файлов без точки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="a0e88-128">Пример 5. получение свойства в указанном каталоге</span><span class="sxs-lookup"><span data-stu-id="a0e88-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="a0e88-129">В этом примере возвращается свойство **lastAccessTime** `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="a0e88-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="a0e88-130">**LastAccessTime** — это только одно свойство каталогов файловой системы.</span><span class="sxs-lookup"><span data-stu-id="a0e88-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="a0e88-131">Чтобы просмотреть все свойства каталога, введите `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="a0e88-132">Пример 6. Отображение содержимого раздела реестра</span><span class="sxs-lookup"><span data-stu-id="a0e88-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="a0e88-133">В этом примере показано содержимое раздела реестра **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="a0e88-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="a0e88-134">Этот командлет можно использовать вместе с поставщиком реестра PowerShell для получения разделов и подразделов реестра, но `Get-ItemProperty` для получения значений и данных реестра необходимо использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="a0e88-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="a0e88-135">Пример 7. Получение элементов в каталоге с исключением</span><span class="sxs-lookup"><span data-stu-id="a0e88-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="a0e88-136">Этот пример получает элементы в каталоге Windows с именами, которые содержат точку ( `.` ), но не начинаются с `w*` . Этот пример работает только в том случае, если путь содержит подстановочный знак ( `*` ) для указания содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="a0e88-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="a0e88-137">Пример 8. Получение сведений о hardlink</span><span class="sxs-lookup"><span data-stu-id="a0e88-137">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="a0e88-138">В PowerShell 6,2 для получения сведений о hardlink было добавлено альтернативное представление.</span><span class="sxs-lookup"><span data-stu-id="a0e88-138">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="a0e88-139">Чтобы получить сведения о hardlink, передайте выходные данные в `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="a0e88-139">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

## <span data-ttu-id="a0e88-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0e88-140">PARAMETERS</span></span>

### <span data-ttu-id="a0e88-141">-Stream</span><span class="sxs-lookup"><span data-stu-id="a0e88-141">-Stream</span></span>

<span data-ttu-id="a0e88-142">Возвращает указанный альтернативный файловый поток NTFS из файла.</span><span class="sxs-lookup"><span data-stu-id="a0e88-142">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="a0e88-143">Введите имя потока.</span><span class="sxs-lookup"><span data-stu-id="a0e88-143">Enter the stream name.</span></span> <span data-ttu-id="a0e88-144">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-144">Wildcards are supported.</span></span> <span data-ttu-id="a0e88-145">Чтобы получить все потоки, используйте звездочку ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="a0e88-145">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="a0e88-146">Этот параметр не является допустимым для папок.</span><span class="sxs-lookup"><span data-stu-id="a0e88-146">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="a0e88-147">**Stream** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="a0e88-147">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="a0e88-148">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="a0e88-148">This parameter works only in file system drives.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a0e88-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="a0e88-149">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a0e88-150">Этот параметр не поддерживается поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0e88-150">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a0e88-151">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="a0e88-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a0e88-152">-Exclude</span><span class="sxs-lookup"><span data-stu-id="a0e88-152">-Exclude</span></span>

<span data-ttu-id="a0e88-153">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="a0e88-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a0e88-154">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a0e88-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a0e88-155">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a0e88-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="a0e88-157">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="a0e88-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a0e88-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="a0e88-158">-Filter</span></span>

<span data-ttu-id="a0e88-159">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="a0e88-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a0e88-160">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры.</span><span class="sxs-lookup"><span data-stu-id="a0e88-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="a0e88-161">Фильтры более эффективны, чем другие параметры.</span><span class="sxs-lookup"><span data-stu-id="a0e88-161">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="a0e88-162">Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="a0e88-162">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="a0e88-163">Строка фильтра передается в API .NET для перечисления файлов.</span><span class="sxs-lookup"><span data-stu-id="a0e88-163">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="a0e88-164">API поддерживает только `*` `?` подстановочные знаки и.</span><span class="sxs-lookup"><span data-stu-id="a0e88-164">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a0e88-165">-Force</span><span class="sxs-lookup"><span data-stu-id="a0e88-165">-Force</span></span>

<span data-ttu-id="a0e88-166">Указывает, что этот командлет получает элементы, доступ к которым в противном случае невозможен, например скрытые элементы.</span><span class="sxs-lookup"><span data-stu-id="a0e88-166">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="a0e88-167">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="a0e88-167">Implementation varies from provider to provider.</span></span> <span data-ttu-id="a0e88-168">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a0e88-168">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="a0e88-169">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a0e88-169">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0e88-170">-Include</span><span class="sxs-lookup"><span data-stu-id="a0e88-170">-Include</span></span>

<span data-ttu-id="a0e88-171">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="a0e88-171">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a0e88-172">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="a0e88-172">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a0e88-173">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-173">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a0e88-174">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-174">Wildcard characters are permitted.</span></span> <span data-ttu-id="a0e88-175">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="a0e88-175">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a0e88-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a0e88-176">-LiteralPath</span></span>

<span data-ttu-id="a0e88-177">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="a0e88-177">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a0e88-178">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="a0e88-178">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="a0e88-179">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-179">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a0e88-180">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a0e88-181">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="a0e88-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a0e88-182">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a0e88-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a0e88-183">-Path</span><span class="sxs-lookup"><span data-stu-id="a0e88-183">-Path</span></span>

<span data-ttu-id="a0e88-184">Определяет путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="a0e88-184">Specifies the path to an item.</span></span> <span data-ttu-id="a0e88-185">Этот командлет возвращает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="a0e88-185">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="a0e88-186">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a0e88-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="a0e88-187">Этот параметр является обязательным, но **путь к** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a0e88-187">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="a0e88-188">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="a0e88-188">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="a0e88-189">Используйте подстановочный знак ( `*` ), чтобы указать все элементы в текущем расположении.</span><span class="sxs-lookup"><span data-stu-id="a0e88-189">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="a0e88-190">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a0e88-190">CommonParameters</span></span>

<span data-ttu-id="a0e88-191">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-191">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a0e88-192">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a0e88-192">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a0e88-193">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a0e88-193">INPUTS</span></span>

### <span data-ttu-id="a0e88-194">System.String</span><span class="sxs-lookup"><span data-stu-id="a0e88-194">System.String</span></span>

<span data-ttu-id="a0e88-195">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="a0e88-195">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a0e88-196">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a0e88-196">OUTPUTS</span></span>

### <span data-ttu-id="a0e88-197">System.Object</span><span class="sxs-lookup"><span data-stu-id="a0e88-197">System.Object</span></span>

<span data-ttu-id="a0e88-198">Этот командлет возвращает объекты, которые он получает.</span><span class="sxs-lookup"><span data-stu-id="a0e88-198">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="a0e88-199">Тип определяется типом объектов в пути.</span><span class="sxs-lookup"><span data-stu-id="a0e88-199">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="a0e88-200">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a0e88-200">NOTES</span></span>

<span data-ttu-id="a0e88-201">Этот командлет не имеет **рекурсивного** параметра, так как он получает только элемент, а не его содержимое.</span><span class="sxs-lookup"><span data-stu-id="a0e88-201">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="a0e88-202">Для рекурсивного получения содержимого элемента используйте `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="a0e88-202">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="a0e88-203">Для перемещения по реестру используйте этот командлет для получения разделов реестра и `Get-ItemProperty` для получения значений и данных реестра.</span><span class="sxs-lookup"><span data-stu-id="a0e88-203">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="a0e88-204">Параметры реестра являются свойствами раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="a0e88-204">The registry values are considered to be properties of the registry key.</span></span>
  
<span data-ttu-id="a0e88-205">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a0e88-205">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a0e88-206">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="a0e88-206">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="a0e88-207">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a0e88-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a0e88-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a0e88-208">RELATED LINKS</span></span>

[<span data-ttu-id="a0e88-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="a0e88-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="a0e88-211">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-211">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="a0e88-212">Move-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-212">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="a0e88-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="a0e88-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="a0e88-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="a0e88-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="a0e88-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="a0e88-217">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a0e88-217">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="a0e88-218">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a0e88-218">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="a0e88-219">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a0e88-219">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="a0e88-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a0e88-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

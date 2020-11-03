---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 1498c7eb254e0d21b108c4016d8b737d5b33298d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228377"
---
# <span data-ttu-id="f5056-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-103">Get-Item</span></span>

## <span data-ttu-id="f5056-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f5056-104">SYNOPSIS</span></span>
<span data-ttu-id="f5056-105">Получает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="f5056-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="f5056-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5056-106">SYNTAX</span></span>

### <span data-ttu-id="f5056-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f5056-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f5056-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f5056-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f5056-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5056-109">DESCRIPTION</span></span>

<span data-ttu-id="f5056-110">`Get-Item`Командлет возвращает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="f5056-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="f5056-111">Он не получает содержимое элемента в расположении, если только вы не используете подстановочный знак ( `*` ) для запроса всего содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="f5056-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="f5056-112">Этот командлет используется поставщиками PowerShell для перемещения по различным типам хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="f5056-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="f5056-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="f5056-113">EXAMPLES</span></span>

### <span data-ttu-id="f5056-114">Пример 1. Получение текущего каталога</span><span class="sxs-lookup"><span data-stu-id="f5056-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="f5056-115">В этом примере возвращается текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="f5056-115">This example gets the current directory.</span></span> <span data-ttu-id="f5056-116">Точка (".") представляет элемент в текущем расположении (а не его содержимом).</span><span class="sxs-lookup"><span data-stu-id="f5056-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="f5056-117">Пример 2. получение всех элементов в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="f5056-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="f5056-118">Этот пример возвращает все элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5056-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="f5056-119">Символ-шаблон ( `*` ) представляет все содержимое текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="f5056-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="f5056-120">Пример 3. Получение текущего каталога диска</span><span class="sxs-lookup"><span data-stu-id="f5056-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="f5056-121">В этом примере возвращается текущий каталог `C:` диска.</span><span class="sxs-lookup"><span data-stu-id="f5056-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="f5056-122">Извлекаемый объект представляет только каталог, но не его содержимое.</span><span class="sxs-lookup"><span data-stu-id="f5056-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="f5056-123">Пример 4. Получение элементов на указанном диске</span><span class="sxs-lookup"><span data-stu-id="f5056-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="f5056-124">В этом примере выполняется получение элементов на `C:` диске.</span><span class="sxs-lookup"><span data-stu-id="f5056-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="f5056-125">Подстановочный знак ( `*` ) представляет все элементы в контейнере, а не только контейнер.</span><span class="sxs-lookup"><span data-stu-id="f5056-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="f5056-126">В PowerShell используйте одну звездочку ( `*` ) для получения содержимого вместо традиционной `*.*` .</span><span class="sxs-lookup"><span data-stu-id="f5056-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="f5056-127">Формат интерпретируется буквально, поэтому `*.*` не извлекаются каталоги или имена файлов без точки.</span><span class="sxs-lookup"><span data-stu-id="f5056-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="f5056-128">Пример 5. получение свойства в указанном каталоге</span><span class="sxs-lookup"><span data-stu-id="f5056-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="f5056-129">В этом примере возвращается свойство **lastAccessTime** `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="f5056-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="f5056-130">**LastAccessTime** — это только одно свойство каталогов файловой системы.</span><span class="sxs-lookup"><span data-stu-id="f5056-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="f5056-131">Чтобы просмотреть все свойства каталога, введите `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f5056-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="f5056-132">Пример 6. Отображение содержимого раздела реестра</span><span class="sxs-lookup"><span data-stu-id="f5056-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="f5056-133">В этом примере показано содержимое раздела реестра **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="f5056-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="f5056-134">Этот командлет можно использовать вместе с поставщиком реестра PowerShell для получения разделов и подразделов реестра, но `Get-ItemProperty` для получения значений и данных реестра необходимо использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="f5056-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="f5056-135">Пример 7. Получение элементов в каталоге с исключением</span><span class="sxs-lookup"><span data-stu-id="f5056-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="f5056-136">Этот пример получает элементы в каталоге Windows с именами, которые содержат точку ( `.` ), но не начинаются с `w*` . Этот пример работает только в том случае, если путь содержит подстановочный знак ( `*` ) для указания содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="f5056-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

## <span data-ttu-id="f5056-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5056-137">PARAMETERS</span></span>

### <span data-ttu-id="f5056-138">-Stream</span><span class="sxs-lookup"><span data-stu-id="f5056-138">-Stream</span></span>

<span data-ttu-id="f5056-139">Возвращает указанный альтернативный файловый поток NTFS из файла.</span><span class="sxs-lookup"><span data-stu-id="f5056-139">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="f5056-140">Введите имя потока.</span><span class="sxs-lookup"><span data-stu-id="f5056-140">Enter the stream name.</span></span> <span data-ttu-id="f5056-141">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f5056-141">Wildcards are supported.</span></span> <span data-ttu-id="f5056-142">Чтобы получить все потоки, используйте звездочку ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="f5056-142">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="f5056-143">Этот параметр не является допустимым для папок.</span><span class="sxs-lookup"><span data-stu-id="f5056-143">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="f5056-144">**Stream** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="f5056-144">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="f5056-145">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="f5056-145">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="f5056-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="f5056-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="f5056-147">Этот параметр не поддерживается поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5056-147">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="f5056-148">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="f5056-149">-Exclude</span><span class="sxs-lookup"><span data-stu-id="f5056-149">-Exclude</span></span>

<span data-ttu-id="f5056-150">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="f5056-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="f5056-151">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="f5056-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f5056-152">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="f5056-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f5056-153">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f5056-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="f5056-154">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="f5056-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="f5056-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="f5056-155">-Filter</span></span>

<span data-ttu-id="f5056-156">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="f5056-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="f5056-157">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры.</span><span class="sxs-lookup"><span data-stu-id="f5056-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="f5056-158">Фильтры более эффективны, чем другие параметры.</span><span class="sxs-lookup"><span data-stu-id="f5056-158">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="f5056-159">Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="f5056-159">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="f5056-160">Строка фильтра передается в API .NET для перечисления файлов.</span><span class="sxs-lookup"><span data-stu-id="f5056-160">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="f5056-161">API поддерживает только `*` `?` подстановочные знаки и.</span><span class="sxs-lookup"><span data-stu-id="f5056-161">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="f5056-162">-Force</span><span class="sxs-lookup"><span data-stu-id="f5056-162">-Force</span></span>

<span data-ttu-id="f5056-163">Указывает, что этот командлет получает элементы, доступ к которым в противном случае невозможен, например скрытые элементы.</span><span class="sxs-lookup"><span data-stu-id="f5056-163">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="f5056-164">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="f5056-164">Implementation varies from provider to provider.</span></span> <span data-ttu-id="f5056-165">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="f5056-166">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5056-166">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="f5056-167">-Include</span><span class="sxs-lookup"><span data-stu-id="f5056-167">-Include</span></span>

<span data-ttu-id="f5056-168">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="f5056-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="f5056-169">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="f5056-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f5056-170">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="f5056-170">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="f5056-171">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f5056-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="f5056-172">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="f5056-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="f5056-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f5056-173">-LiteralPath</span></span>

<span data-ttu-id="f5056-174">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="f5056-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="f5056-175">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="f5056-175">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="f5056-176">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f5056-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f5056-177">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f5056-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f5056-178">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f5056-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="f5056-179">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f5056-180">-Path</span><span class="sxs-lookup"><span data-stu-id="f5056-180">-Path</span></span>

<span data-ttu-id="f5056-181">Определяет путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="f5056-181">Specifies the path to an item.</span></span> <span data-ttu-id="f5056-182">Этот командлет возвращает элемент в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="f5056-182">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="f5056-183">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f5056-183">Wildcard characters are permitted.</span></span> <span data-ttu-id="f5056-184">Этот параметр является обязательным, но **путь к** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f5056-184">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="f5056-185">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="f5056-185">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="f5056-186">Используйте подстановочный знак ( `*` ), чтобы указать все элементы в текущем расположении.</span><span class="sxs-lookup"><span data-stu-id="f5056-186">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="f5056-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="f5056-187">-UseTransaction</span></span>

<span data-ttu-id="f5056-188">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="f5056-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="f5056-189">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="f5056-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="f5056-190">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-190">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="f5056-191">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f5056-191">CommonParameters</span></span>

<span data-ttu-id="f5056-192">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="f5056-192">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f5056-193">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-193">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f5056-194">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f5056-194">INPUTS</span></span>

### <span data-ttu-id="f5056-195">System.String</span><span class="sxs-lookup"><span data-stu-id="f5056-195">System.String</span></span>

<span data-ttu-id="f5056-196">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="f5056-196">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="f5056-197">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f5056-197">OUTPUTS</span></span>

### <span data-ttu-id="f5056-198">System.Object</span><span class="sxs-lookup"><span data-stu-id="f5056-198">System.Object</span></span>

<span data-ttu-id="f5056-199">Этот командлет возвращает объекты, которые он получает.</span><span class="sxs-lookup"><span data-stu-id="f5056-199">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="f5056-200">Тип определяется типом объектов в пути.</span><span class="sxs-lookup"><span data-stu-id="f5056-200">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="f5056-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f5056-201">NOTES</span></span>

<span data-ttu-id="f5056-202">Этот командлет не имеет **рекурсивного** параметра, так как он получает только элемент, а не его содержимое.</span><span class="sxs-lookup"><span data-stu-id="f5056-202">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="f5056-203">Для рекурсивного получения содержимого элемента используйте `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="f5056-203">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="f5056-204">Для перемещения по реестру используйте этот командлет для получения разделов реестра и `Get-ItemProperty` для получения значений и данных реестра.</span><span class="sxs-lookup"><span data-stu-id="f5056-204">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="f5056-205">Параметры реестра являются свойствами раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="f5056-205">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="f5056-206">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="f5056-206">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f5056-207">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="f5056-207">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="f5056-208">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f5056-208">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f5056-209">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f5056-209">RELATED LINKS</span></span>

[<span data-ttu-id="f5056-210">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-210">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="f5056-211">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-211">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="f5056-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="f5056-213">Move-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-213">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="f5056-214">New-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-214">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="f5056-215">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-215">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="f5056-216">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-216">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="f5056-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="f5056-217">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="f5056-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="f5056-218">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="f5056-219">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f5056-219">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="f5056-220">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f5056-220">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="f5056-221">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f5056-221">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 5b12e91ab5562dcce9fa4441ecd27f575f6e07a7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225505"
---
# <span data-ttu-id="641bc-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="641bc-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="641bc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="641bc-104">SYNOPSIS</span></span>
<span data-ttu-id="641bc-105">Возвращает значение для одного или нескольких свойств указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="641bc-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="641bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="641bc-106">SYNTAX</span></span>

### <span data-ttu-id="641bc-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="641bc-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="641bc-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="641bc-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="641bc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="641bc-109">DESCRIPTION</span></span>

<span data-ttu-id="641bc-110">`Get-ItemPropertyValue`Возвращает текущее значение свойства, которое указывается при использовании параметра *Name* , расположенного в пути, указанном с помощью параметров *path* или *LiteralPath* .</span><span class="sxs-lookup"><span data-stu-id="641bc-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="641bc-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="641bc-111">EXAMPLES</span></span>

### <span data-ttu-id="641bc-112">Пример 1. получение значения свойства ProductID</span><span class="sxs-lookup"><span data-stu-id="641bc-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="641bc-113">Эта команда возвращает значение свойства **ProductID** объекта "\софтваре\микрософт\виндовс нт\куррентверсион" в поставщике реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="641bc-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="641bc-114">Пример 2. получение времени последней записи файла или папки</span><span class="sxs-lookup"><span data-stu-id="641bc-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="641bc-115">Эта команда получает значение свойства **LastWriteTime** или время последнего изменения файла или папки из папки "к:\усерс\тест\документс\модулетоассембли", работающей в поставщике FileSystem.</span><span class="sxs-lookup"><span data-stu-id="641bc-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="641bc-116">Пример 3. получение нескольких значений свойств файла или папки</span><span class="sxs-lookup"><span data-stu-id="641bc-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="641bc-117">Эта команда возвращает значения свойств **LastWriteTime** , **CreationTime** и **root** папки.</span><span class="sxs-lookup"><span data-stu-id="641bc-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span> <span data-ttu-id="641bc-118">Значения свойств возвращаются в порядке, в котором указаны имена свойств.</span><span class="sxs-lookup"><span data-stu-id="641bc-118">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="641bc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="641bc-119">PARAMETERS</span></span>

### <span data-ttu-id="641bc-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="641bc-120">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="641bc-121">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="641bc-121">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="641bc-122">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="641bc-122">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="641bc-123">-Exclude</span><span class="sxs-lookup"><span data-stu-id="641bc-123">-Exclude</span></span>

<span data-ttu-id="641bc-124">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="641bc-124">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="641bc-125">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="641bc-125">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="641bc-126">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="641bc-126">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="641bc-127">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="641bc-127">Wildcard characters are permitted.</span></span> <span data-ttu-id="641bc-128">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="641bc-128">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="641bc-129">-Filter</span><span class="sxs-lookup"><span data-stu-id="641bc-129">-Filter</span></span>

<span data-ttu-id="641bc-130">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="641bc-130">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="641bc-131">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="641bc-131">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="641bc-132">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="641bc-132">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="641bc-133">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="641bc-133">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="641bc-134">-Include</span><span class="sxs-lookup"><span data-stu-id="641bc-134">-Include</span></span>

<span data-ttu-id="641bc-135">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="641bc-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="641bc-136">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="641bc-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="641bc-137">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="641bc-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="641bc-138">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="641bc-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="641bc-139">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="641bc-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="641bc-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="641bc-140">-LiteralPath</span></span>

<span data-ttu-id="641bc-141">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="641bc-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="641bc-142">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="641bc-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="641bc-143">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="641bc-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="641bc-144">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="641bc-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="641bc-145">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="641bc-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="641bc-146">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="641bc-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="641bc-147">-Name</span><span class="sxs-lookup"><span data-stu-id="641bc-147">-Name</span></span>

<span data-ttu-id="641bc-148">Указывает имена свойств, которые нужно извлечь.</span><span class="sxs-lookup"><span data-stu-id="641bc-148">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="641bc-149">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="641bc-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="641bc-150">-Path</span><span class="sxs-lookup"><span data-stu-id="641bc-150">-Path</span></span>

<span data-ttu-id="641bc-151">Указывает путь к элементам.</span><span class="sxs-lookup"><span data-stu-id="641bc-151">Specifies the path to the item or items.</span></span>
<span data-ttu-id="641bc-152">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="641bc-152">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="641bc-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="641bc-153">CommonParameters</span></span>

<span data-ttu-id="641bc-154">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="641bc-154">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="641bc-155">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="641bc-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="641bc-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="641bc-156">INPUTS</span></span>

### <span data-ttu-id="641bc-157">System.String</span><span class="sxs-lookup"><span data-stu-id="641bc-157">System.String</span></span>

<span data-ttu-id="641bc-158">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="641bc-158">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="641bc-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="641bc-159">OUTPUTS</span></span>

### <span data-ttu-id="641bc-160">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="641bc-160">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="641bc-161">Этот командлет возвращает объект для каждого значения свойства элемента, которое он получает.</span><span class="sxs-lookup"><span data-stu-id="641bc-161">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="641bc-162">Тип объекта зависит от полученного значения свойства.</span><span class="sxs-lookup"><span data-stu-id="641bc-162">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="641bc-163">Например, на диске файловой системы командлет может вернуть файл или папку.</span><span class="sxs-lookup"><span data-stu-id="641bc-163">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="641bc-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="641bc-164">NOTES</span></span>

<span data-ttu-id="641bc-165">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="641bc-165">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="641bc-166">Чтобы получить список поставщиков, доступных в вашем сеансе, выполните `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="641bc-166">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="641bc-167">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="641bc-167">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="641bc-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="641bc-168">RELATED LINKS</span></span>

[<span data-ttu-id="641bc-169">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-169">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="641bc-170">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-170">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="641bc-171">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-171">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="641bc-172">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="641bc-172">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="641bc-173">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-173">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="641bc-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-174">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="641bc-175">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-175">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="641bc-176">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-176">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="641bc-177">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="641bc-177">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="641bc-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="641bc-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 2dbbbfeac3810f79b976b6a68ab3089e91707fb3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228373"
---
# <span data-ttu-id="6d95a-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="6d95a-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="6d95a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6d95a-104">SYNOPSIS</span></span>
<span data-ttu-id="6d95a-105">Возвращает значение для одного или нескольких свойств указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="6d95a-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="6d95a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6d95a-106">SYNTAX</span></span>

### <span data-ttu-id="6d95a-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6d95a-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="6d95a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6d95a-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="6d95a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6d95a-109">DESCRIPTION</span></span>

<span data-ttu-id="6d95a-110">`Get-ItemPropertyValue`Возвращает текущее значение свойства, которое указывается при использовании параметра *Name* , расположенного в пути, указанном с помощью параметров *path* или *LiteralPath* .</span><span class="sxs-lookup"><span data-stu-id="6d95a-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="6d95a-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="6d95a-111">EXAMPLES</span></span>

### <span data-ttu-id="6d95a-112">Пример 1. получение значения свойства ProductID</span><span class="sxs-lookup"><span data-stu-id="6d95a-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="6d95a-113">Эта команда возвращает значение свойства **ProductID** объекта "\софтваре\микрософт\виндовс нт\куррентверсион" в поставщике реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="6d95a-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="6d95a-114">Пример 2. получение времени последней записи файла или папки</span><span class="sxs-lookup"><span data-stu-id="6d95a-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="6d95a-115">Эта команда получает значение свойства **LastWriteTime** или время последнего изменения файла или папки из папки "к:\усерс\тест\документс\модулетоассембли", работающей в поставщике FileSystem.</span><span class="sxs-lookup"><span data-stu-id="6d95a-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="6d95a-116">Пример 3. получение нескольких значений свойств файла или папки</span><span class="sxs-lookup"><span data-stu-id="6d95a-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="6d95a-117">Эта команда возвращает значения свойств **LastWriteTime** , **CreationTime** и **root** папки.</span><span class="sxs-lookup"><span data-stu-id="6d95a-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span>
<span data-ttu-id="6d95a-118">Значения свойств возвращаются в порядке, в котором указаны имена свойств.</span><span class="sxs-lookup"><span data-stu-id="6d95a-118">The property values are returned in the order in which you specified the property names.</span></span>

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

## <span data-ttu-id="6d95a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6d95a-119">PARAMETERS</span></span>

### <span data-ttu-id="6d95a-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="6d95a-120">-Credential</span></span>

<span data-ttu-id="6d95a-121">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="6d95a-121">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="6d95a-122">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6d95a-122">The default is the current user.</span></span>

<span data-ttu-id="6d95a-123">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="6d95a-123">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="6d95a-124">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="6d95a-124">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="6d95a-125">Этот параметр не поддерживается поставщиками, которые устанавливаются вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d95a-125">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="6d95a-126">-Exclude</span><span class="sxs-lookup"><span data-stu-id="6d95a-126">-Exclude</span></span>

<span data-ttu-id="6d95a-127">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="6d95a-127">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="6d95a-128">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="6d95a-128">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="6d95a-129">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="6d95a-129">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="6d95a-130">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6d95a-130">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="6d95a-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="6d95a-131">-Filter</span></span>

<span data-ttu-id="6d95a-132">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="6d95a-132">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="6d95a-133">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="6d95a-133">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="6d95a-134">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="6d95a-134">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="6d95a-135">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="6d95a-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="6d95a-136">-Include</span><span class="sxs-lookup"><span data-stu-id="6d95a-136">-Include</span></span>

<span data-ttu-id="6d95a-137">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="6d95a-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="6d95a-138">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="6d95a-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="6d95a-139">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="6d95a-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="6d95a-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6d95a-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="6d95a-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6d95a-141">-LiteralPath</span></span>

<span data-ttu-id="6d95a-142">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="6d95a-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="6d95a-143">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="6d95a-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="6d95a-144">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="6d95a-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="6d95a-145">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="6d95a-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="6d95a-146">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="6d95a-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="6d95a-147">-Name</span><span class="sxs-lookup"><span data-stu-id="6d95a-147">-Name</span></span>

<span data-ttu-id="6d95a-148">Указывает имена свойств, которые нужно извлечь.</span><span class="sxs-lookup"><span data-stu-id="6d95a-148">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6d95a-149">-Path</span><span class="sxs-lookup"><span data-stu-id="6d95a-149">-Path</span></span>

<span data-ttu-id="6d95a-150">Указывает путь к элементам.</span><span class="sxs-lookup"><span data-stu-id="6d95a-150">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6d95a-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="6d95a-151">-UseTransaction</span></span>

<span data-ttu-id="6d95a-152">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="6d95a-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="6d95a-153">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="6d95a-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="6d95a-154">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="6d95a-154">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="6d95a-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6d95a-155">CommonParameters</span></span>

<span data-ttu-id="6d95a-156">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="6d95a-156">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="6d95a-157">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6d95a-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6d95a-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6d95a-158">INPUTS</span></span>

### <span data-ttu-id="6d95a-159">System.String</span><span class="sxs-lookup"><span data-stu-id="6d95a-159">System.String</span></span>

<span data-ttu-id="6d95a-160">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="6d95a-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="6d95a-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6d95a-161">OUTPUTS</span></span>

### <span data-ttu-id="6d95a-162">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="6d95a-162">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="6d95a-163">Этот командлет возвращает объект для каждого значения свойства элемента, которое он получает.</span><span class="sxs-lookup"><span data-stu-id="6d95a-163">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="6d95a-164">Тип объекта зависит от полученного значения свойства.</span><span class="sxs-lookup"><span data-stu-id="6d95a-164">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="6d95a-165">Например, на диске файловой системы командлет может вернуть файл или папку.</span><span class="sxs-lookup"><span data-stu-id="6d95a-165">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="6d95a-166">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6d95a-166">NOTES</span></span>

<span data-ttu-id="6d95a-167">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="6d95a-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="6d95a-168">Чтобы получить список поставщиков, доступных в вашем сеансе, выполните `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="6d95a-168">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="6d95a-169">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="6d95a-169">For more information, see about_Providers.</span></span>

## <span data-ttu-id="6d95a-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6d95a-170">RELATED LINKS</span></span>

[<span data-ttu-id="6d95a-171">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-171">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="6d95a-172">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-172">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="6d95a-173">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-173">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="6d95a-174">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-174">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="6d95a-175">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-175">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="6d95a-176">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-176">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="6d95a-177">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-177">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="6d95a-178">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6d95a-178">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="6d95a-179">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="6d95a-179">Get-PSProvider</span></span>](Get-PSProvider.md)

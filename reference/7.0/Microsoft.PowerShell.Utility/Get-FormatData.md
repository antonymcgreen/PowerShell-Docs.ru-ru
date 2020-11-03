---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData;
ms.openlocfilehash: 22cdfce0ca9e591dfc97a6ac7ef2c1e0f0ed37ab
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226061"
---
# <span data-ttu-id="36fcb-103">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="36fcb-103">Get-FormatData</span></span>

## <span data-ttu-id="36fcb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="36fcb-104">SYNOPSIS</span></span>
<span data-ttu-id="36fcb-105">Получает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="36fcb-105">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="36fcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36fcb-106">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="36fcb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36fcb-107">DESCRIPTION</span></span>

<span data-ttu-id="36fcb-108">`Get-FormatData`Командлет возвращает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="36fcb-108">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="36fcb-109">Данные форматирования в сеансе включают данные форматирования из `Format.ps1xml` файлов форматирования, такие как в `$PSHOME` каталоге, форматирование данных для модулей, импортированных в сеанс, и форматирование данных для команд, импортируемых в сеанс с помощью `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="36fcb-109">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="36fcb-110">С помощью этого командлета можно изучать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="36fcb-110">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="36fcb-111">Затем можно использовать `Export-FormatData` командлет для сериализации объектов, преобразования их в формат XML и сохранения в `Format.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="36fcb-111">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="36fcb-112">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="36fcb-112">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="36fcb-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="36fcb-113">EXAMPLES</span></span>

### <span data-ttu-id="36fcb-114">Пример 1. получение всех данных форматирования</span><span class="sxs-lookup"><span data-stu-id="36fcb-114">Example 1: Get all formatting data</span></span>

<span data-ttu-id="36fcb-115">В этом примере выполняется получение всех данных форматирования в сеансе.</span><span class="sxs-lookup"><span data-stu-id="36fcb-115">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1
```

> [!IMPORTANT]
> <span data-ttu-id="36fcb-116">Чтобы убедиться в том, что возвращаются полные сведения о форматировании типов, следует всегда включать параметр **PowerShellVersion** со значением `5.1` при использовании локального вызова `Get-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="36fcb-116">To ensure that the complete type formatting information is returned, you should always include the **PowerShellVersion** parameter with the value `5.1` when using a local invocation of `Get-FormatData`.</span></span> <span data-ttu-id="36fcb-117">Если параметр и значение опущены, вы не сможете получить все правильные сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="36fcb-117">If the parameter and value are omitted, you may not get all the correct type information.</span></span>

### <span data-ttu-id="36fcb-118">Пример 2. получение данных форматирования по имени типа</span><span class="sxs-lookup"><span data-stu-id="36fcb-118">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="36fcb-119">Этот пример возвращает элементы данных форматирования, имена которых начинаются с `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="36fcb-119">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
```

### <span data-ttu-id="36fcb-120">Пример 3. Проверка объекта данных форматирования</span><span class="sxs-lookup"><span data-stu-id="36fcb-120">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="36fcb-121">В этом примере показано, как получить объект данных форматирования и изучить его свойства.</span><span class="sxs-lookup"><span data-stu-id="36fcb-121">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### <span data-ttu-id="36fcb-122">Пример 4. получение данных форматирования и их экспорт</span><span class="sxs-lookup"><span data-stu-id="36fcb-122">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="36fcb-123">В этом примере показано, как использовать `Get-FormatData` и `Export-FormatData` для экспорта данных форматирования, добавленных модулем.</span><span class="sxs-lookup"><span data-stu-id="36fcb-123">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData -PowerShellVersion 5.1
Import-Module bitstransfer
$B = Get-FormatData -PowerShellVersion 5.1
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

<span data-ttu-id="36fcb-124">Первые четыре команды используют `Get-FormatData` `Import-Module` `Compare-Object` командлеты, и для задания типа формата, который модуль **BitsTransfer** добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="36fcb-124">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="36fcb-125">Пятая команда использует `Get-FormatData` командлет для получения типа формата, добавляемого модулем **BitsTransfer** .</span><span class="sxs-lookup"><span data-stu-id="36fcb-125">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="36fcb-126">Он использует оператор конвейера ( `|` ) для отправки в командлет объекта типа формата `Export-FormatData` , который преобразует его обратно в XML и сохраняет в указанном `format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="36fcb-126">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="36fcb-127">Последняя команда показывает выдержку из `format.ps1xml` содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="36fcb-127">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="36fcb-128">Пример 5. получение данных форматирования на основе указанной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="36fcb-128">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="36fcb-129">В этом примере показано, как использовать `Get-FormatData` для получения данных форматирования для указанных **имени TypeName** и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36fcb-129">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="36fcb-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36fcb-130">PARAMETERS</span></span>

### <span data-ttu-id="36fcb-131">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="36fcb-131">-PowerShellVersion</span></span>

<span data-ttu-id="36fcb-132">Укажите версию PowerShell, которую этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="36fcb-132">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="36fcb-133">Введите значение из двух цифр, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="36fcb-133">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="36fcb-134">Этот параметр был добавлен в PowerShell 5,1 для улучшения совместимости при удаленном использовании компьютеров с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36fcb-134">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36fcb-135">-TypeName</span><span class="sxs-lookup"><span data-stu-id="36fcb-135">-TypeName</span></span>

<span data-ttu-id="36fcb-136">Указывает имена типов, которые этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="36fcb-136">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="36fcb-137">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="36fcb-137">Enter the type names.</span></span>
<span data-ttu-id="36fcb-138">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="36fcb-138">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="36fcb-139">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="36fcb-139">CommonParameters</span></span>

<span data-ttu-id="36fcb-140">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36fcb-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36fcb-141">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36fcb-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36fcb-142">Входные данные</span><span class="sxs-lookup"><span data-stu-id="36fcb-142">INPUTS</span></span>

### <span data-ttu-id="36fcb-143">Нет</span><span class="sxs-lookup"><span data-stu-id="36fcb-143">None</span></span>

<span data-ttu-id="36fcb-144">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="36fcb-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="36fcb-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="36fcb-145">OUTPUTS</span></span>

### <span data-ttu-id="36fcb-146">System. Management. Automation. Екстендедтипедефинитион</span><span class="sxs-lookup"><span data-stu-id="36fcb-146">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="36fcb-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="36fcb-147">NOTES</span></span>

## <span data-ttu-id="36fcb-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="36fcb-148">RELATED LINKS</span></span>

[<span data-ttu-id="36fcb-149">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="36fcb-149">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="36fcb-150">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="36fcb-150">Update-FormatData</span></span>](Update-FormatData.md)

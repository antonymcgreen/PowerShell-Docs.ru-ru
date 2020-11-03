---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData;
ms.openlocfilehash: 0024bb83b983d0b13e2fbfafb24505849acf15f6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227205"
---
# <span data-ttu-id="acc2b-103">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="acc2b-103">Get-FormatData</span></span>

## <span data-ttu-id="acc2b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="acc2b-104">SYNOPSIS</span></span>
<span data-ttu-id="acc2b-105">Получает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="acc2b-105">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="acc2b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="acc2b-106">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="acc2b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="acc2b-107">DESCRIPTION</span></span>

<span data-ttu-id="acc2b-108">`Get-FormatData`Командлет возвращает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="acc2b-108">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="acc2b-109">Данные форматирования в сеансе включают данные форматирования из `Format.ps1xml` файлов форматирования, такие как в `$PSHOME` каталоге, форматирование данных для модулей, импортированных в сеанс, и форматирование данных для команд, импортируемых в сеанс с помощью `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="acc2b-109">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="acc2b-110">С помощью этого командлета можно изучать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="acc2b-110">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="acc2b-111">Затем можно использовать `Export-FormatData` командлет для сериализации объектов, преобразования их в формат XML и сохранения в `Format.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="acc2b-111">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="acc2b-112">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="acc2b-112">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="acc2b-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="acc2b-113">EXAMPLES</span></span>

### <span data-ttu-id="acc2b-114">Пример 1. получение всех данных форматирования</span><span class="sxs-lookup"><span data-stu-id="acc2b-114">Example 1: Get all formatting data</span></span>

<span data-ttu-id="acc2b-115">В этом примере выполняется получение всех данных форматирования в сеансе.</span><span class="sxs-lookup"><span data-stu-id="acc2b-115">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData
```

### <span data-ttu-id="acc2b-116">Пример 2. получение данных форматирования по имени типа</span><span class="sxs-lookup"><span data-stu-id="acc2b-116">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="acc2b-117">Этот пример возвращает элементы данных форматирования, имена которых начинаются с `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="acc2b-117">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
```

### <span data-ttu-id="acc2b-118">Пример 3. Проверка объекта данных форматирования</span><span class="sxs-lookup"><span data-stu-id="acc2b-118">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="acc2b-119">В этом примере показано, как получить объект данных форматирования и изучить его свойства.</span><span class="sxs-lookup"><span data-stu-id="acc2b-119">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
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

### <span data-ttu-id="acc2b-120">Пример 4. получение данных форматирования и их экспорт</span><span class="sxs-lookup"><span data-stu-id="acc2b-120">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="acc2b-121">В этом примере показано, как использовать `Get-FormatData` и `Export-FormatData` для экспорта данных форматирования, добавленных модулем.</span><span class="sxs-lookup"><span data-stu-id="acc2b-121">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData
Import-Module bitstransfer
$B = Get-FormatData
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

<span data-ttu-id="acc2b-122">Первые четыре команды используют `Get-FormatData` `Import-Module` `Compare-Object` командлеты, и для задания типа формата, который модуль **BitsTransfer** добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="acc2b-122">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="acc2b-123">Пятая команда использует `Get-FormatData` командлет для получения типа формата, добавляемого модулем **BitsTransfer** .</span><span class="sxs-lookup"><span data-stu-id="acc2b-123">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="acc2b-124">Он использует оператор конвейера ( `|` ) для отправки в командлет объекта типа формата `Export-FormatData` , который преобразует его обратно в XML и сохраняет в указанном `format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="acc2b-124">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="acc2b-125">Последняя команда показывает выдержку из `format.ps1xml` содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="acc2b-125">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="acc2b-126">Пример 5. получение данных форматирования на основе указанной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="acc2b-126">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="acc2b-127">В этом примере показано, как использовать `Get-FormatData` для получения данных форматирования для указанных **имени TypeName** и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acc2b-127">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="acc2b-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="acc2b-128">PARAMETERS</span></span>

### <span data-ttu-id="acc2b-129">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="acc2b-129">-PowerShellVersion</span></span>

<span data-ttu-id="acc2b-130">Укажите версию PowerShell, которую этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="acc2b-130">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="acc2b-131">Введите значение из двух цифр, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="acc2b-131">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="acc2b-132">Этот параметр был добавлен в PowerShell 5,1 для улучшения совместимости при удаленном использовании компьютеров с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acc2b-132">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

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

### <span data-ttu-id="acc2b-133">-TypeName</span><span class="sxs-lookup"><span data-stu-id="acc2b-133">-TypeName</span></span>

<span data-ttu-id="acc2b-134">Указывает имена типов, которые этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="acc2b-134">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="acc2b-135">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="acc2b-135">Enter the type names.</span></span>
<span data-ttu-id="acc2b-136">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="acc2b-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="acc2b-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="acc2b-137">CommonParameters</span></span>

<span data-ttu-id="acc2b-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="acc2b-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="acc2b-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="acc2b-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="acc2b-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="acc2b-140">INPUTS</span></span>

### <span data-ttu-id="acc2b-141">Нет</span><span class="sxs-lookup"><span data-stu-id="acc2b-141">None</span></span>

<span data-ttu-id="acc2b-142">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="acc2b-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="acc2b-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="acc2b-143">OUTPUTS</span></span>

### <span data-ttu-id="acc2b-144">System. Management. Automation. Екстендедтипедефинитион</span><span class="sxs-lookup"><span data-stu-id="acc2b-144">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="acc2b-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="acc2b-145">NOTES</span></span>

## <span data-ttu-id="acc2b-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="acc2b-146">RELATED LINKS</span></span>

[<span data-ttu-id="acc2b-147">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="acc2b-147">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="acc2b-148">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="acc2b-148">Update-FormatData</span></span>](Update-FormatData.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData;
ms.openlocfilehash: 28eab1709de12ec5d391009aacccfd4e973a8b9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601087"
---
# <span data-ttu-id="44d6e-102">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="44d6e-102">Get-FormatData</span></span>

## <span data-ttu-id="44d6e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="44d6e-103">SYNOPSIS</span></span>
<span data-ttu-id="44d6e-104">Получает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="44d6e-104">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="44d6e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44d6e-105">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="44d6e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44d6e-106">DESCRIPTION</span></span>

<span data-ttu-id="44d6e-107">`Get-FormatData`Командлет возвращает данные форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="44d6e-107">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="44d6e-108">Данные форматирования в сеансе включают данные форматирования из `Format.ps1xml` файлов форматирования, такие как в `$PSHOME` каталоге, форматирование данных для модулей, импортированных в сеанс, и форматирование данных для команд, импортируемых в сеанс с помощью `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="44d6e-108">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="44d6e-109">С помощью этого командлета можно изучать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="44d6e-109">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="44d6e-110">Затем можно использовать `Export-FormatData` командлет для сериализации объектов, преобразования их в формат XML и сохранения в `Format.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="44d6e-110">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="44d6e-111">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="44d6e-111">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="44d6e-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="44d6e-112">EXAMPLES</span></span>

### <span data-ttu-id="44d6e-113">Пример 1. получение всех данных форматирования</span><span class="sxs-lookup"><span data-stu-id="44d6e-113">Example 1: Get all formatting data</span></span>

<span data-ttu-id="44d6e-114">В этом примере выполняется получение всех данных форматирования в сеансе.</span><span class="sxs-lookup"><span data-stu-id="44d6e-114">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData
```

### <span data-ttu-id="44d6e-115">Пример 2. получение данных форматирования по имени типа</span><span class="sxs-lookup"><span data-stu-id="44d6e-115">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="44d6e-116">Этот пример возвращает элементы данных форматирования, имена которых начинаются с `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="44d6e-116">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
```

### <span data-ttu-id="44d6e-117">Пример 3. Проверка объекта данных форматирования</span><span class="sxs-lookup"><span data-stu-id="44d6e-117">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="44d6e-118">В этом примере показано, как получить объект данных форматирования и изучить его свойства.</span><span class="sxs-lookup"><span data-stu-id="44d6e-118">This example shows how to get a formatting data object and examine its properties.</span></span>

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

### <span data-ttu-id="44d6e-119">Пример 4. получение данных форматирования и их экспорт</span><span class="sxs-lookup"><span data-stu-id="44d6e-119">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="44d6e-120">В этом примере показано, как использовать `Get-FormatData` и `Export-FormatData` для экспорта данных форматирования, добавленных модулем.</span><span class="sxs-lookup"><span data-stu-id="44d6e-120">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

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

<span data-ttu-id="44d6e-121">Первые четыре команды используют `Get-FormatData` `Import-Module` `Compare-Object` командлеты, и для задания типа формата, который модуль **BitsTransfer** добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="44d6e-121">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="44d6e-122">Пятая команда использует `Get-FormatData` командлет для получения типа формата, добавляемого модулем **BitsTransfer** .</span><span class="sxs-lookup"><span data-stu-id="44d6e-122">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="44d6e-123">Он использует оператор конвейера ( `|` ) для отправки в командлет объекта типа формата `Export-FormatData` , который преобразует его обратно в XML и сохраняет в указанном `format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="44d6e-123">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="44d6e-124">Последняя команда показывает выдержку из `format.ps1xml` содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="44d6e-124">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="44d6e-125">Пример 5. получение данных форматирования на основе указанной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="44d6e-125">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="44d6e-126">В этом примере показано, как использовать `Get-FormatData` для получения данных форматирования для указанных **имени TypeName** и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44d6e-126">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="44d6e-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44d6e-127">PARAMETERS</span></span>

### <span data-ttu-id="44d6e-128">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="44d6e-128">-PowerShellVersion</span></span>

<span data-ttu-id="44d6e-129">Укажите версию PowerShell, которую этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="44d6e-129">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="44d6e-130">Введите значение из двух цифр, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="44d6e-130">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="44d6e-131">Этот параметр был добавлен в PowerShell 5,1 для улучшения совместимости при удаленном использовании компьютеров с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44d6e-131">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

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

### <span data-ttu-id="44d6e-132">-TypeName</span><span class="sxs-lookup"><span data-stu-id="44d6e-132">-TypeName</span></span>

<span data-ttu-id="44d6e-133">Указывает имена типов, которые этот командлет получает для данных форматирования.</span><span class="sxs-lookup"><span data-stu-id="44d6e-133">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="44d6e-134">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="44d6e-134">Enter the type names.</span></span>
<span data-ttu-id="44d6e-135">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="44d6e-135">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="44d6e-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="44d6e-136">CommonParameters</span></span>

<span data-ttu-id="44d6e-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44d6e-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44d6e-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44d6e-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44d6e-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="44d6e-139">INPUTS</span></span>

### <span data-ttu-id="44d6e-140">None</span><span class="sxs-lookup"><span data-stu-id="44d6e-140">None</span></span>

<span data-ttu-id="44d6e-141">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="44d6e-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="44d6e-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="44d6e-142">OUTPUTS</span></span>

### <span data-ttu-id="44d6e-143">System. Management. Automation. Екстендедтипедефинитион</span><span class="sxs-lookup"><span data-stu-id="44d6e-143">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="44d6e-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="44d6e-144">NOTES</span></span>

## <span data-ttu-id="44d6e-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="44d6e-145">RELATED LINKS</span></span>

[<span data-ttu-id="44d6e-146">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="44d6e-146">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="44d6e-147">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="44d6e-147">Update-FormatData</span></span>](Update-FormatData.md)

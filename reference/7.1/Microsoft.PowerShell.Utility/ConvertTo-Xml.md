---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: 2e7ebe3a528095873dc7ba5ba0deba2905f531ee
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228593"
---
# <span data-ttu-id="3aed0-103">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="3aed0-103">ConvertTo-Xml</span></span>

## <span data-ttu-id="3aed0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3aed0-104">SYNOPSIS</span></span>
<span data-ttu-id="3aed0-105">Создает XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="3aed0-105">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="3aed0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3aed0-106">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="3aed0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3aed0-107">DESCRIPTION</span></span>

<span data-ttu-id="3aed0-108">`ConvertTo-Xml`Командлет создает [основанное на XML](/dotnet/api/system.xml.xmldocument) представление одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="3aed0-108">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="3aed0-109">Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="3aed0-109">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="3aed0-110">При передаче нескольких объектов `ConvertTo-Xml` или использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Xml` возвращает отдельный XML-документ в памяти, включающий представления всех объектов.</span><span class="sxs-lookup"><span data-stu-id="3aed0-110">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="3aed0-111">Этот командлет аналогичен [Export-Clixml](./Export-Clixml.md) , за исключением того, что `Export-Clixml` сохраняет результирующий XML-файл в [Common Language Infrastructureном XML-файле (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) , который может быть повторно импортирован как объекты с помощью командлета [Import-Clixml](./Import-Clixml.md).</span><span class="sxs-lookup"><span data-stu-id="3aed0-111">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="3aed0-112">`ConvertTo-Xml` Возвращает представление XML-документа в памяти, поэтому вы можете продолжить его обработку в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aed0-112">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="3aed0-113">`ConvertTo-Xml` не имеет параметра для преобразования объектов в XML CLI.</span><span class="sxs-lookup"><span data-stu-id="3aed0-113">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="3aed0-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3aed0-114">EXAMPLES</span></span>

### <span data-ttu-id="3aed0-115">Пример 1. Преобразование даты в XML</span><span class="sxs-lookup"><span data-stu-id="3aed0-115">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="3aed0-116">Эта команда преобразует текущую дату (объект **DateTime** ) в XML.</span><span class="sxs-lookup"><span data-stu-id="3aed0-116">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="3aed0-117">Пример 2. Преобразование процессов в XML</span><span class="sxs-lookup"><span data-stu-id="3aed0-117">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="3aed0-118">Эта команда преобразует объекты процессов, представляющие все процессы на компьютере, в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="3aed0-118">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="3aed0-119">Объекты расширяются до трех уровней.</span><span class="sxs-lookup"><span data-stu-id="3aed0-119">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="3aed0-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3aed0-120">PARAMETERS</span></span>

### <span data-ttu-id="3aed0-121">— Как</span><span class="sxs-lookup"><span data-stu-id="3aed0-121">-As</span></span>

<span data-ttu-id="3aed0-122">Определяет формат вывода.</span><span class="sxs-lookup"><span data-stu-id="3aed0-122">Determines the output format.</span></span>
<span data-ttu-id="3aed0-123">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3aed0-123">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3aed0-124">Строка.</span><span class="sxs-lookup"><span data-stu-id="3aed0-124">String.</span></span>
<span data-ttu-id="3aed0-125">возвращает отдельную строку;</span><span class="sxs-lookup"><span data-stu-id="3aed0-125">Returns a single string.</span></span>
- <span data-ttu-id="3aed0-126">Поток.</span><span class="sxs-lookup"><span data-stu-id="3aed0-126">Stream.</span></span>
<span data-ttu-id="3aed0-127">возвращает массив строк;</span><span class="sxs-lookup"><span data-stu-id="3aed0-127">Returns an array of strings.</span></span>
- <span data-ttu-id="3aed0-128">Документ.</span><span class="sxs-lookup"><span data-stu-id="3aed0-128">Document.</span></span>
<span data-ttu-id="3aed0-129">Возвращает объект **XmlDocument** .</span><span class="sxs-lookup"><span data-stu-id="3aed0-129">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="3aed0-130">Значение по умолчанию — Document.</span><span class="sxs-lookup"><span data-stu-id="3aed0-130">The default value is Document.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3aed0-131">-Depth</span><span class="sxs-lookup"><span data-stu-id="3aed0-131">-Depth</span></span>

<span data-ttu-id="3aed0-132">Указывает, сколько уровней вложенных объектов включается в XML-представление.</span><span class="sxs-lookup"><span data-stu-id="3aed0-132">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="3aed0-133">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="3aed0-133">The default value is 1.</span></span>

<span data-ttu-id="3aed0-134">Например, если свойства объекта также содержат объекты, то для сохранения XML-представления свойств этих вложенных объектов необходимо указать глубину, равную 2.</span><span class="sxs-lookup"><span data-stu-id="3aed0-134">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="3aed0-135">Значение по умолчанию можно переопределить для типа объекта в файлах Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="3aed0-135">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="3aed0-136">Дополнительные сведения см. в разделе about_Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="3aed0-136">For more information, see about_Types.ps1xml.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3aed0-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3aed0-137">-InputObject</span></span>

<span data-ttu-id="3aed0-138">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="3aed0-138">Specifies the object to be converted.</span></span> <span data-ttu-id="3aed0-139">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="3aed0-139">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="3aed0-140">Также можно передать объекты в **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="3aed0-140">You can also pipe objects to **ConvertTo-XML** .</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3aed0-141">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="3aed0-141">-NoTypeInformation</span></span>

<span data-ttu-id="3aed0-142">Исключает атрибут Type из узлов объектов.</span><span class="sxs-lookup"><span data-stu-id="3aed0-142">Omits the Type attribute from the object nodes.</span></span>

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

### <span data-ttu-id="3aed0-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3aed0-143">CommonParameters</span></span>

<span data-ttu-id="3aed0-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3aed0-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3aed0-145">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3aed0-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3aed0-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3aed0-146">INPUTS</span></span>

### <span data-ttu-id="3aed0-147">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="3aed0-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3aed0-148">Любой объект можно передать по конвейеру в **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="3aed0-148">You can pipe any object to **ConvertTo-XML** .</span></span>

## <span data-ttu-id="3aed0-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3aed0-149">OUTPUTS</span></span>

### <span data-ttu-id="3aed0-150">System. String или System.Xml.Xmlдокумент</span><span class="sxs-lookup"><span data-stu-id="3aed0-150">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="3aed0-151">Значение параметра *as* определяет тип объекта, возвращаемого **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="3aed0-151">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="3aed0-152">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3aed0-152">NOTES</span></span>

## <span data-ttu-id="3aed0-153">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3aed0-153">RELATED LINKS</span></span>

[<span data-ttu-id="3aed0-154">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="3aed0-154">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="3aed0-155">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="3aed0-155">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="3aed0-156">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="3aed0-156">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="3aed0-157">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="3aed0-157">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="3aed0-158">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="3aed0-158">Import-Clixml</span></span>](Import-Clixml.md)

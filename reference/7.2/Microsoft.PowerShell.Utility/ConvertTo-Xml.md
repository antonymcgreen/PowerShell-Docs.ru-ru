---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: e461c07360b3d9eaf7d9a3c8875d34cd1fc841e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605290"
---
# <span data-ttu-id="2070d-102">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="2070d-102">ConvertTo-Xml</span></span>

## <span data-ttu-id="2070d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2070d-103">SYNOPSIS</span></span>
<span data-ttu-id="2070d-104">Создает XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="2070d-104">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="2070d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2070d-105">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="2070d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2070d-106">DESCRIPTION</span></span>

<span data-ttu-id="2070d-107">`ConvertTo-Xml`Командлет создает [основанное на XML](/dotnet/api/system.xml.xmldocument) представление одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2070d-107">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="2070d-108">Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="2070d-108">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="2070d-109">При передаче нескольких объектов `ConvertTo-Xml` или использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Xml` возвращает отдельный XML-документ в памяти, включающий представления всех объектов.</span><span class="sxs-lookup"><span data-stu-id="2070d-109">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="2070d-110">Этот командлет аналогичен [Export-Clixml](./Export-Clixml.md) , за исключением того, что `Export-Clixml` сохраняет результирующий XML-файл в [Common Language Infrastructureном XML-файле (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) , который может быть повторно импортирован как объекты с помощью командлета [Import-Clixml](./Import-Clixml.md).</span><span class="sxs-lookup"><span data-stu-id="2070d-110">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="2070d-111">`ConvertTo-Xml` Возвращает представление XML-документа в памяти, поэтому вы можете продолжить его обработку в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2070d-111">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="2070d-112">`ConvertTo-Xml` не имеет параметра для преобразования объектов в XML CLI.</span><span class="sxs-lookup"><span data-stu-id="2070d-112">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="2070d-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="2070d-113">EXAMPLES</span></span>

### <span data-ttu-id="2070d-114">Пример 1. Преобразование даты в XML</span><span class="sxs-lookup"><span data-stu-id="2070d-114">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="2070d-115">Эта команда преобразует текущую дату (объект **DateTime** ) в XML.</span><span class="sxs-lookup"><span data-stu-id="2070d-115">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="2070d-116">Пример 2. Преобразование процессов в XML</span><span class="sxs-lookup"><span data-stu-id="2070d-116">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="2070d-117">Эта команда преобразует объекты процессов, представляющие все процессы на компьютере, в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="2070d-117">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="2070d-118">Объекты расширяются до трех уровней.</span><span class="sxs-lookup"><span data-stu-id="2070d-118">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="2070d-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2070d-119">PARAMETERS</span></span>

### <span data-ttu-id="2070d-120">— Как</span><span class="sxs-lookup"><span data-stu-id="2070d-120">-As</span></span>

<span data-ttu-id="2070d-121">Определяет формат вывода.</span><span class="sxs-lookup"><span data-stu-id="2070d-121">Determines the output format.</span></span>
<span data-ttu-id="2070d-122">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2070d-122">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2070d-123">Строка.</span><span class="sxs-lookup"><span data-stu-id="2070d-123">String.</span></span>
<span data-ttu-id="2070d-124">возвращает отдельную строку;</span><span class="sxs-lookup"><span data-stu-id="2070d-124">Returns a single string.</span></span>
- <span data-ttu-id="2070d-125">Поток.</span><span class="sxs-lookup"><span data-stu-id="2070d-125">Stream.</span></span>
<span data-ttu-id="2070d-126">возвращает массив строк;</span><span class="sxs-lookup"><span data-stu-id="2070d-126">Returns an array of strings.</span></span>
- <span data-ttu-id="2070d-127">Документ.</span><span class="sxs-lookup"><span data-stu-id="2070d-127">Document.</span></span>
<span data-ttu-id="2070d-128">Возвращает объект **XmlDocument** .</span><span class="sxs-lookup"><span data-stu-id="2070d-128">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="2070d-129">Значение по умолчанию — Document.</span><span class="sxs-lookup"><span data-stu-id="2070d-129">The default value is Document.</span></span>

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

### <span data-ttu-id="2070d-130">-Depth</span><span class="sxs-lookup"><span data-stu-id="2070d-130">-Depth</span></span>

<span data-ttu-id="2070d-131">Указывает, сколько уровней вложенных объектов включается в XML-представление.</span><span class="sxs-lookup"><span data-stu-id="2070d-131">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="2070d-132">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="2070d-132">The default value is 1.</span></span>

<span data-ttu-id="2070d-133">Например, если свойства объекта также содержат объекты, то для сохранения XML-представления свойств этих вложенных объектов необходимо указать глубину, равную 2.</span><span class="sxs-lookup"><span data-stu-id="2070d-133">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="2070d-134">Значение по умолчанию можно переопределить для типа объекта в файлах Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="2070d-134">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="2070d-135">Дополнительные сведения см. в разделе about_Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="2070d-135">For more information, see about_Types.ps1xml.</span></span>

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

### <span data-ttu-id="2070d-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2070d-136">-InputObject</span></span>

<span data-ttu-id="2070d-137">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="2070d-137">Specifies the object to be converted.</span></span> <span data-ttu-id="2070d-138">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="2070d-138">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="2070d-139">Также можно передать объекты в **ConvertTo-XML**.</span><span class="sxs-lookup"><span data-stu-id="2070d-139">You can also pipe objects to **ConvertTo-XML**.</span></span>

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

### <span data-ttu-id="2070d-140">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="2070d-140">-NoTypeInformation</span></span>

<span data-ttu-id="2070d-141">Исключает атрибут Type из узлов объектов.</span><span class="sxs-lookup"><span data-stu-id="2070d-141">Omits the Type attribute from the object nodes.</span></span>

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

### <span data-ttu-id="2070d-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2070d-142">CommonParameters</span></span>

<span data-ttu-id="2070d-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2070d-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2070d-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2070d-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2070d-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2070d-145">INPUTS</span></span>

### <span data-ttu-id="2070d-146">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="2070d-146">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2070d-147">Любой объект можно передать по конвейеру в **ConvertTo-XML**.</span><span class="sxs-lookup"><span data-stu-id="2070d-147">You can pipe any object to **ConvertTo-XML**.</span></span>

## <span data-ttu-id="2070d-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2070d-148">OUTPUTS</span></span>

### <span data-ttu-id="2070d-149">System. String или System.Xml.Xmlдокумент</span><span class="sxs-lookup"><span data-stu-id="2070d-149">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="2070d-150">Значение параметра *as* определяет тип объекта, возвращаемого **ConvertTo-XML** .</span><span class="sxs-lookup"><span data-stu-id="2070d-150">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="2070d-151">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2070d-151">NOTES</span></span>

## <span data-ttu-id="2070d-152">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2070d-152">RELATED LINKS</span></span>

[<span data-ttu-id="2070d-153">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="2070d-153">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="2070d-154">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="2070d-154">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="2070d-155">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="2070d-155">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="2070d-156">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="2070d-156">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="2070d-157">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="2070d-157">Import-Clixml</span></span>](Import-Clixml.md)


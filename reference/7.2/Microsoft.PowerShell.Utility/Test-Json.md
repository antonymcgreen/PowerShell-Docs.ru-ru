---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: a29eab449e567f78d1e54a6716ca91d87aa08405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605538"
---
# <span data-ttu-id="40162-102">Test-Json</span><span class="sxs-lookup"><span data-stu-id="40162-102">Test-Json</span></span>

## <span data-ttu-id="40162-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="40162-103">SYNOPSIS</span></span>
<span data-ttu-id="40162-104">Проверяет, является ли строка допустимым документом JSON</span><span class="sxs-lookup"><span data-stu-id="40162-104">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="40162-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40162-105">SYNTAX</span></span>

### <span data-ttu-id="40162-106">__AllParameterSets (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="40162-106">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="40162-107">счемастринг</span><span class="sxs-lookup"><span data-stu-id="40162-107">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="40162-108">счемафиле</span><span class="sxs-lookup"><span data-stu-id="40162-108">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="40162-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40162-109">DESCRIPTION</span></span>

<span data-ttu-id="40162-110">`Test-Json`Командлет проверяет, является ли строка допустимым документом нотация объектов JavaScript (JSON), и при необходимости может проверить, что документ JSON связан с указанной схемой.</span><span class="sxs-lookup"><span data-stu-id="40162-110">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="40162-111">Проверенная строка может использоваться с `ConvertFrom-Json` командлетом для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell или отправляется другой программе или веб-службе, обращающейся к входным данным JSON.</span><span class="sxs-lookup"><span data-stu-id="40162-111">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="40162-112">Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="40162-112">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="40162-113">Этот командлет появился в PowerShell 6,1</span><span class="sxs-lookup"><span data-stu-id="40162-113">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="40162-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="40162-114">EXAMPLES</span></span>

### <span data-ttu-id="40162-115">Пример 1. Проверка, является ли объект допустимым JSON</span><span class="sxs-lookup"><span data-stu-id="40162-115">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="40162-116">В этом примере проверяется, является ли входная строка допустимым документом JSON.</span><span class="sxs-lookup"><span data-stu-id="40162-116">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="40162-117">Пример 2. Проверка объекта по предоставленной схеме</span><span class="sxs-lookup"><span data-stu-id="40162-117">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="40162-118">Этот пример принимает строку, содержащую схему JSON, и сравнивает ее со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="40162-118">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

<span data-ttu-id="40162-119">В этом примере мы получаем ошибку, так как схема ожидает целое число, но входные данные JSON **, которые мы** проверяли, используют строковое значение.</span><span class="sxs-lookup"><span data-stu-id="40162-119">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="40162-120">Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="40162-120">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="40162-121">Пример 3. Проверка объекта на соответствие схеме из файла</span><span class="sxs-lookup"><span data-stu-id="40162-121">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="40162-122">Схема JSON может ссылаться на определения с помощью `$ref` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="40162-122">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="40162-123">`$ref`Может разрешаться в URI, ссылающийся на другой файл.</span><span class="sxs-lookup"><span data-stu-id="40162-123">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="40162-124">`SchemaFile`Параметр принимает литеральный путь к файлу схемы JSON и позволяет проверять файлы JSON по таким схемам.</span><span class="sxs-lookup"><span data-stu-id="40162-124">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="40162-125">В этом примере у нас есть `schema.json` файл, на который ссылается `definitions.json` .</span><span class="sxs-lookup"><span data-stu-id="40162-125">In this example we have `schema.json` file which references `definitions.json`.</span></span>

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

<span data-ttu-id="40162-126">Дополнительные сведения см. [в разделе Структурирование сложной схемы](https://json-schema.org/understanding-json-schema/structuring.html).</span><span class="sxs-lookup"><span data-stu-id="40162-126">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="40162-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40162-127">PARAMETERS</span></span>

### <span data-ttu-id="40162-128">-JSON</span><span class="sxs-lookup"><span data-stu-id="40162-128">-Json</span></span>

<span data-ttu-id="40162-129">Указывает строку JSON для проверки на допустимость.</span><span class="sxs-lookup"><span data-stu-id="40162-129">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="40162-130">Введите переменную, содержащую строку, либо введите команду или выражение для получения строки.</span><span class="sxs-lookup"><span data-stu-id="40162-130">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="40162-131">Можно также передать строку в `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="40162-131">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="40162-132">Параметр **JSON** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="40162-132">The **Json** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="40162-133">-Schema</span><span class="sxs-lookup"><span data-stu-id="40162-133">-Schema</span></span>

<span data-ttu-id="40162-134">Указывает схему для проверки входных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="40162-134">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="40162-135">При передаче `Test-Json` проверяет, что входные данные JSON соответствует спецификации, указанной параметром **Schema** , и возвращают, `$True` только если входные данные соответствует указанной схеме.</span><span class="sxs-lookup"><span data-stu-id="40162-135">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="40162-136">Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="40162-136">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40162-137">-Счемафиле</span><span class="sxs-lookup"><span data-stu-id="40162-137">-SchemaFile</span></span>

<span data-ttu-id="40162-138">Указывает файл схемы, используемый для проверки входных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="40162-138">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="40162-139">При использовании функция возвращает значение, `Test-Json` `$True` только если входные данные JSON соответствует схеме, определенной в файле, указанном параметром **счемафиле** .</span><span class="sxs-lookup"><span data-stu-id="40162-139">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="40162-140">Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="40162-140">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40162-141">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="40162-141">CommonParameters</span></span>

<span data-ttu-id="40162-142">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40162-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40162-143">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40162-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40162-144">Входные данные</span><span class="sxs-lookup"><span data-stu-id="40162-144">INPUTS</span></span>

### <span data-ttu-id="40162-145">System.String</span><span class="sxs-lookup"><span data-stu-id="40162-145">System.String</span></span>

<span data-ttu-id="40162-146">Строку JSON можно передать в `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="40162-146">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="40162-147">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="40162-147">OUTPUTS</span></span>

### <span data-ttu-id="40162-148">Логическое</span><span class="sxs-lookup"><span data-stu-id="40162-148">Boolean</span></span>

## <span data-ttu-id="40162-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="40162-149">NOTES</span></span>

<span data-ttu-id="40162-150">`Test-Json`Командлет реализуется с помощью [класса нжсонсчема](https://github.com/RSuter/NJsonSchema).</span><span class="sxs-lookup"><span data-stu-id="40162-150">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="40162-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="40162-151">RELATED LINKS</span></span>

<span data-ttu-id="40162-152">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="40162-152">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="40162-153">Дополнительные сведения о схеме JSON</span><span class="sxs-lookup"><span data-stu-id="40162-153">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="40162-154">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="40162-154">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="40162-155">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="40162-155">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="40162-156">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="40162-156">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

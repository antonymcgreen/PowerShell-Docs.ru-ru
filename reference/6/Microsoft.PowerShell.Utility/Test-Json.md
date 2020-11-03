---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228766"
---
# <span data-ttu-id="855b3-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="855b3-103">Test-Json</span></span>

## <span data-ttu-id="855b3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="855b3-104">SYNOPSIS</span></span>
<span data-ttu-id="855b3-105">Проверяет, является ли строка допустимым документом JSON</span><span class="sxs-lookup"><span data-stu-id="855b3-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="855b3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="855b3-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="855b3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="855b3-107">DESCRIPTION</span></span>

<span data-ttu-id="855b3-108">`Test-Json`Командлет проверяет, является ли строка допустимым документом нотация объектов JavaScript (JSON), и при необходимости может проверить, что документ JSON связан с указанной схемой.</span><span class="sxs-lookup"><span data-stu-id="855b3-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="855b3-109">Проверенная строка может использоваться с `ConvertFrom-Json` командлетом для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell или отправляется другой программе или веб-службе, обращающейся к входным данным JSON.</span><span class="sxs-lookup"><span data-stu-id="855b3-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="855b3-110">Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="855b3-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="855b3-111">Этот командлет появился в PowerShell 6,1</span><span class="sxs-lookup"><span data-stu-id="855b3-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="855b3-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="855b3-112">EXAMPLES</span></span>

### <span data-ttu-id="855b3-113">Пример 1. Проверка, является ли объект допустимым JSON</span><span class="sxs-lookup"><span data-stu-id="855b3-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="855b3-114">В этом примере проверяется, является ли входная строка допустимым документом JSON.</span><span class="sxs-lookup"><span data-stu-id="855b3-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="855b3-115">Пример 2. Проверка объекта по предоставленной схеме</span><span class="sxs-lookup"><span data-stu-id="855b3-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="855b3-116">Этот пример принимает строку, содержащую схему JSON, и сравнивает ее со входной строкой.</span><span class="sxs-lookup"><span data-stu-id="855b3-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="855b3-117">В этом примере мы получаем ошибку, так как схема ожидает целое число, но входные данные JSON **, которые мы** проверяли, используют строковое значение.</span><span class="sxs-lookup"><span data-stu-id="855b3-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="855b3-118">Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="855b3-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="855b3-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="855b3-119">PARAMETERS</span></span>

### <span data-ttu-id="855b3-120">-JSON</span><span class="sxs-lookup"><span data-stu-id="855b3-120">-Json</span></span>

<span data-ttu-id="855b3-121">Указывает строку JSON для проверки на допустимость.</span><span class="sxs-lookup"><span data-stu-id="855b3-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="855b3-122">Введите переменную, содержащую строку, либо введите команду или выражение для получения строки.</span><span class="sxs-lookup"><span data-stu-id="855b3-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="855b3-123">Можно также передать строку в `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="855b3-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="855b3-124">Параметр **JSON** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="855b3-124">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="855b3-125">-Schema</span><span class="sxs-lookup"><span data-stu-id="855b3-125">-Schema</span></span>

<span data-ttu-id="855b3-126">Указывает схему для проверки входных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="855b3-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="855b3-127">При передаче `Test-Json` проверяет, что входные данные JSON соответствует спецификации, указанной параметром **Schema** , и возвращают, `$True` только если входные данные соответствует указанной схеме.</span><span class="sxs-lookup"><span data-stu-id="855b3-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="855b3-128">Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="855b3-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855b3-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="855b3-129">CommonParameters</span></span>

<span data-ttu-id="855b3-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="855b3-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="855b3-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="855b3-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="855b3-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="855b3-132">INPUTS</span></span>

### <span data-ttu-id="855b3-133">System.String</span><span class="sxs-lookup"><span data-stu-id="855b3-133">System.String</span></span>

<span data-ttu-id="855b3-134">Строку JSON можно передать в `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="855b3-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="855b3-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="855b3-135">OUTPUTS</span></span>

### <span data-ttu-id="855b3-136">Логическое значение</span><span class="sxs-lookup"><span data-stu-id="855b3-136">Boolean</span></span>

## <span data-ttu-id="855b3-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="855b3-137">NOTES</span></span>

<span data-ttu-id="855b3-138">`Test-Json`Командлет реализуется с помощью [класса нжсонсчема](https://github.com/RSuter/NJsonSchema).</span><span class="sxs-lookup"><span data-stu-id="855b3-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="855b3-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="855b3-139">RELATED LINKS</span></span>

<span data-ttu-id="855b3-140">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="855b3-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="855b3-141">Дополнительные сведения о схеме JSON</span><span class="sxs-lookup"><span data-stu-id="855b3-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="855b3-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="855b3-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="855b3-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="855b3-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="855b3-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="855b3-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

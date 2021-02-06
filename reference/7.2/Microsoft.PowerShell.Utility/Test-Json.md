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
# Test-Json

## Краткий обзор
Проверяет, является ли строка допустимым документом JSON

## SYNTAX

### __AllParameterSets (по умолчанию)
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### счемастринг
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### счемафиле
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## DESCRIPTION

`Test-Json`Командлет проверяет, является ли строка допустимым документом нотация объектов JavaScript (JSON), и при необходимости может проверить, что документ JSON связан с указанной схемой.

Проверенная строка может использоваться с `ConvertFrom-Json` командлетом для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell или отправляется другой программе или веб-службе, обращающейся к входным данным JSON.

Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.

Этот командлет появился в PowerShell 6,1

## Примеры

### Пример 1. Проверка, является ли объект допустимым JSON

В этом примере проверяется, является ли входная строка допустимым документом JSON.

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### Пример 2. Проверка объекта по предоставленной схеме

Этот пример принимает строку, содержащую схему JSON, и сравнивает ее со входной строкой.

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

В этом примере мы получаем ошибку, так как схема ожидает целое число, но входные данные JSON **, которые мы** проверяли, используют строковое значение.

Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).

### Пример 3. Проверка объекта на соответствие схеме из файла

Схема JSON может ссылаться на определения с помощью `$ref` ключевого слова. `$ref`Может разрешаться в URI, ссылающийся на другой файл. `SchemaFile`Параметр принимает литеральный путь к файлу схемы JSON и позволяет проверять файлы JSON по таким схемам.

В этом примере у нас есть `schema.json` файл, на который ссылается `definitions.json` .

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

Дополнительные сведения см. [в разделе Структурирование сложной схемы](https://json-schema.org/understanding-json-schema/structuring.html).

## PARAMETERS

### -JSON

Указывает строку JSON для проверки на допустимость. Введите переменную, содержащую строку, либо введите команду или выражение для получения строки. Можно также передать строку в `Test-Json` .

Параметр **JSON** является обязательным.

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

### -Schema

Указывает схему для проверки входных данных JSON. При передаче `Test-Json` проверяет, что входные данные JSON соответствует спецификации, указанной параметром **Schema** , и возвращают, `$True` только если входные данные соответствует указанной схеме.

Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).

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

### -Счемафиле

Указывает файл схемы, используемый для проверки входных данных JSON. При использовании функция возвращает значение, `Test-Json` `$True` только если входные данные JSON соответствует схеме, определенной в файле, указанном параметром **счемафиле** .

Дополнительные сведения см. в разделе [схема JSON](https://json-schema.org/).

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку JSON можно передать в `Test-Json` .

## Выходные данные

### Логическое

## ПРИМЕЧАНИЯ

`Test-Json`Командлет реализуется с помощью [класса нжсонсчема](https://github.com/RSuter/NJsonSchema).

## Связанные ссылки

[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[Дополнительные сведения о схеме JSON](https://json-schema.org/)

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)

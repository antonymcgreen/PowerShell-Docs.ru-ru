---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: 0f95f66bdd13fd57f71823f2d44a28a1323d0d15
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601882"
---
# ConvertTo-SecureString

## Краткий обзор
Преобразует обычный текст или зашифрованные строки в защищенные строки.

## SYNTAX

### Secure (по умолчанию)

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### PlainText

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### Открыть

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-SecureString`Командлет преобразует зашифрованные стандартные строки в защищенные строки. Кроме того, он конвертирует простой текст в защищенные строки. Он используется с `ConvertFrom-SecureString` и `Read-Host` . Безопасная строка, созданная командлетом, может использоваться с командлетами или функциями, для которых требуется параметр типа **SecureString**. Безопасную строку можно преобразовать обратно в зашифрованную стандартную строку с помощью `ConvertFrom-SecureString` командлета. Это позволит сохранить ее в файле для последующего использования.

Если преобразуемая Стандартная строка была зашифрована с `ConvertFrom-SecureString` помощью указанного ключа, то этот ключ должен быть указан в качестве значения параметра **Key** или **SecureKey** `ConvertTo-SecureString` командлета.

> [!NOTE]
> Обратите внимание, что на [DotNet](/dotnet/api/system.security.securestring#remarks)содержимое SecureString не шифруется в системах, отличных от Windows.

## Примеры

### Пример 1. Преобразование защищенной строки в зашифрованную строку

В этом примере показано, как создать защищенную строку из введенных пользователем данных и преобразовать ее в зашифрованную стандартную строку, а затем обратно в защищенную строку.

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

Первая команда использует параметр **AsSecureString** `Read-Host` командлета для создания защищенной строки. После ввода команды все вводимые символы преобразуются в защищенную строку и затем сохраняются в `$Secure` переменной.

Вторая команда отображает содержимое `$Secure` переменной. Так как `$Secure` переменная содержит защищенную строку, PowerShell отображает только тип **System. Security. SecureString** .

Третья команда использует `ConvertFrom-SecureString` командлет для преобразования защищенной строки в `$Secure` переменную в зашифрованную стандартную строку. Результат сохраняется в `$Encrypted` переменной.

Четвертая команда отображает зашифрованную строку в значении `$Encrypted` переменной.

Пятая команда использует `ConvertTo-SecureString` командлет для преобразования зашифрованной стандартной строки в `$Encrypted` переменную обратно в безопасную строку. Результат сохраняется в `$Secure2` переменной.
Шестая команда выводит значение `$Secure2` переменной. Тип SecureString показывает, что команда выполнена успешно.

### Пример 2. Создание защищенной строки из зашифрованной строки в файле

В этом примере показано, как создать защищенную строку из стандартной зашифрованной строки, сохраненной в файл.

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

Первая команда использует параметр **AsSecureString** `Read-Host` командлета для создания защищенной строки. После ввода команды все вводимые символы преобразуются в защищенную строку и затем сохраняются в `$Secure` переменной.

Вторая команда использует `ConvertFrom-SecureString` командлет для преобразования защищенной строки в `$Secure` переменную в зашифрованную стандартную строку с помощью указанного ключа. Содержимое сохраняется в `$Encrypted` переменной.

Третья команда использует оператор конвейера ( `|` ) для отправки значения `$Encrypted` переменной в `Set-Content` командлет, который сохраняет значение в файле Encrypted.txt.

Четвертая команда использует `Get-Content` командлет для получения зашифрованной стандартной строки в файле Encrypted.txt. Команда использует оператор конвейера для отправки зашифрованной строки в `ConvertTo-SecureString` командлет, который преобразует его в защищенную строку с помощью указанного ключа.
Результаты сохраняются в `$Secure2` переменной.

### Пример 3. Преобразование обычной текстовой строки в защищенную строку

Эта команда преобразует обычную текстовую строку `P@ssW0rD!` в защищенную строку и сохраняет результат в `$Secure_String_Pwd` переменной. Чтобы использовать параметр **AsPlainText** , необходимо также включить параметр **Force** в команду.

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> Не следует использовать обычные текстовые строки в скрипте или из командной строки. Обычный текст может отображаться в журналах событий и журналах команд.

## PARAMETERS

### -AsPlainText

Указывает обычную текстовую строку для преобразования в защищенную. Командлеты защищенной строки помогают защищать секретные тексты. Текст шифруется в целях конфиденциальности и после использования удаляется из памяти компьютера. Если этот параметр используется для ввода обычного текста, система не сможет его защитить. Чтобы использовать этот параметр, необходимо также указать параметр **Force** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Подтверждает, что вы понимаете последствия использования параметра **AsPlainText** и все равно хотите использовать его.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key

Указывает ключ шифрования, используемый для преобразования исходной защищенной строки в зашифрованную стандартную строку. Допустимые значения длины ключа: 16, 24 и 32 байт.

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureKey

Указывает ключ шифрования, используемый для преобразования исходной защищенной строки в зашифрованную стандартную строку. Ключ должен быть предоставлен в формате защищенной строки. Защищенная строка будет преобразована в массив байтов, который будет использоваться в качестве ключа. Допустимая длина защищенных ключей — 8, 12 и 16 кодовых точек.

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -String

Задает строку для преобразования в защищенную строку.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Стандартную зашифрованную строку можно передать в `ConvertTo-SecureString` .

## Выходные данные

### System.Security.SecureString

`ConvertTo-SecureString` Возвращает объект **SecureString** .

## ПРИМЕЧАНИЯ

Некоторые символы, например значки настроения, соответствуют нескольким кодовым точкам в строке, в которой они содержатся. Старайтесь не использовать эти символы, так как они могут вызвать проблемы и нечеткое понимание при использовании пароля.

## Связанные ссылки

[ConvertFrom-SecureString](ConvertFrom-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)

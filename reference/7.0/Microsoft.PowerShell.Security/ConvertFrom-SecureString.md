---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 07/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 4bbdab62168a7306bb02d0ac47b5513d23920814
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "93230173"
---
# ConvertFrom-SecureString

## Краткий обзор
Преобразует защищенную строку в зашифрованную стандартную строку.

## SYNTAX

### Secure (по умолчанию)

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### AsPlainText

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-AsPlainText] [<CommonParameters>]
```

### Открыть

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **ConvertFrom-SecureString** Преобразует защищенную строку ( **System. Security. SecureString** ) в зашифрованную стандартную строку ( **System. String** ). В отличие от безопасной строки, зашифрованную стандартную строку можно сохранить в файл и использовать позднее. Зашифрованную стандартную строку можно преобразовать обратно в формат безопасной строки с помощью `ConvertTo-SecureString` командлета.

Если ключ шифрования указан с помощью параметров **Key** или **SecureKey** , используется алгоритм шифрования AES. Указанный ключ должен иметь размер, равный 128, 192 или 256 бит, потому что именно такие размеры поддерживаются алгоритмом шифрования AES. Если ключ не указан, то используется API защиты данных Windows (DPAPI) для шифрования представления стандартной строки.

> [!NOTE]
> Обратите внимание, что на [DotNet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks)содержимое SecureString не шифруется в системах, отличных от Windows.

## Примеры

### Пример 1. Создание защищенной строки

```powershell
$SecureString = Read-Host -AsSecureString
```

Эта команда создает безопасную строку из символов, введенных через командную строку. После ввода команды введите строку, которую нужно сохранить как безопасную. `*`Для представления каждого введенного символа отображается звездочка ().

### Пример 2. Преобразование защищенной строки в зашифрованную стандартную строку

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

Эта команда преобразует защищенную строку в `$SecureString` переменной в зашифрованную стандартную строку. Полученная зашифрованная стандартная строка хранится в `$StandardString` переменной.

### Пример 3. Преобразование защищенной строки в зашифрованную стандартную строку с помощью 192-разрядного ключа

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

Эти команды используют алгоритм AES (AES) для преобразования защищенной строки, хранящейся в `$SecureString` переменной, в зашифрованную стандартную строку с 192-битным ключом. Полученная зашифрованная стандартная строка хранится в `$StandardString` переменной.

Первая команда сохраняет ключ в `$Key` переменной. Ключ представляет собой массив из 24 десятичных цифр, каждый из которых должен быть меньше 256 для размещения в пределах одного байта без знака.

Так как каждое десятичное число представляет собой один байт (8 бит), ключ содержит 24 цифры для всего 192 бит (8 x 24). Это действительный размер ключа для алгоритма AES.

Вторая команда использует ключ в `$Key` переменной для преобразования защищенной строки в зашифрованную стандартную строку.

### Пример 4. Преобразование защищенной строки непосредственно в строку с открытым текстом

```powershell
$secureString = ConvertTo-SecureString -String 'Example' -AsPlainText
$secureString # 'System.Security.SecureString'
ConvertFrom-SecureString -SecureString $secureString -AsPlainText # 'Example'
```

## PARAMETERS

### -AsPlainText

Если этот параметр задан, то в `ConvertFrom-SecureString` качестве выходных данных преобразует защищенные строки в расшифрованную строку в виде открытого текста.

Этот настоящий момент был добавлен в PowerShell 7,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsPlainText
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key

Указывает ключ шифрования в виде массива байтов.

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

Указывает ключ шифрования в виде безопасной строки. Значение безопасной строки преобразуется в массив байтов перед использованием в качестве ключа.

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

### -SecureString

Указывает безопасную строку, в которую нужно преобразовать зашифрованную стандартную строку.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .
См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Security.SecureString

Объект **SecureString** можно передать в ConvertFrom-SecureString.

## Выходные данные

### System.String

ConvertFrom-SecureString возвращает объект стандартной строки.

## ПРИМЕЧАНИЯ

- Чтобы создать защищенную строку из символов, вводимых в командной строке, используйте параметр **AsSecureString** `Read-Host` командлета.
- При использовании параметров **Key** или **SecureKey** для указания ключа длина ключа должна быть правильной. Например, ключ 128 бит можно указать в виде массива байтов, сокоторый из 16 десятичных цифр.
  Аналогичным образом, 192-разрядные и 256-битовые ключи соответствуют массивам байтов из 24 и 32 десятичных цифр соответственно.
- Некоторые символы, например значки настроения, соответствуют нескольким кодовым точкам в строке, в которой они содержатся. Старайтесь не использовать эти символы, так как они могут вызвать проблемы и нечеткое понимание при использовании пароля.

## Связанные ссылки

[ConvertTo-SecureString](ConvertTo-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)

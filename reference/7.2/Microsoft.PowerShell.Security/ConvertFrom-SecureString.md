---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 07/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 9dcc79755854cc7b9f1928cfbc5d602632eca3cc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602858"
---
# <span data-ttu-id="d0ed1-102">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="d0ed1-102">ConvertFrom-SecureString</span></span>

## <span data-ttu-id="d0ed1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d0ed1-103">SYNOPSIS</span></span>
<span data-ttu-id="d0ed1-104">Преобразует защищенную строку в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-104">Converts a secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="d0ed1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0ed1-105">SYNTAX</span></span>

### <span data-ttu-id="d0ed1-106">Secure (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d0ed1-106">Secure (Default)</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="d0ed1-107">AsPlainText</span><span class="sxs-lookup"><span data-stu-id="d0ed1-107">AsPlainText</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-AsPlainText] [<CommonParameters>]
```

### <span data-ttu-id="d0ed1-108">Открыть</span><span class="sxs-lookup"><span data-stu-id="d0ed1-108">Open</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="d0ed1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0ed1-109">DESCRIPTION</span></span>

<span data-ttu-id="d0ed1-110">Командлет **ConvertFrom-SecureString** Преобразует защищенную строку (**System. Security. SecureString**) в зашифрованную стандартную строку (**System. String**).</span><span class="sxs-lookup"><span data-stu-id="d0ed1-110">The **ConvertFrom-SecureString** cmdlet converts a secure string (**System.Security.SecureString**) into an encrypted standard string (**System.String**).</span></span> <span data-ttu-id="d0ed1-111">В отличие от безопасной строки, зашифрованную стандартную строку можно сохранить в файл и использовать позднее.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-111">Unlike a secure string, an encrypted standard string can be saved in a file for later use.</span></span> <span data-ttu-id="d0ed1-112">Зашифрованную стандартную строку можно преобразовать обратно в формат безопасной строки с помощью `ConvertTo-SecureString` командлета.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-112">The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.</span></span>

<span data-ttu-id="d0ed1-113">Если ключ шифрования указан с помощью параметров **Key** или **SecureKey**, используется алгоритм шифрования AES.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-113">If an encryption key is specified by using the **Key** or **SecureKey** parameters, the Advanced Encryption Standard (AES) encryption algorithm is used.</span></span> <span data-ttu-id="d0ed1-114">Указанный ключ должен иметь размер, равный 128, 192 или 256 бит, потому что именно такие размеры поддерживаются алгоритмом шифрования AES.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-114">The specified key must have a length of 128, 192, or 256 bits because those are the key lengths supported by the AES encryption algorithm.</span></span> <span data-ttu-id="d0ed1-115">Если ключ не указан, то используется API защиты данных Windows (DPAPI) для шифрования представления стандартной строки.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-115">If no key is specified, the Windows Data Protection API (DPAPI) is used to encrypt the standard string representation.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ed1-116">Обратите внимание, что на [DotNet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks)содержимое SecureString не шифруется в системах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-116">Note that per [DotNet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks), the contents of a SecureString are not encrypted on non-Windows systems.</span></span>

## <span data-ttu-id="d0ed1-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="d0ed1-117">EXAMPLES</span></span>

### <span data-ttu-id="d0ed1-118">Пример 1. Создание защищенной строки</span><span class="sxs-lookup"><span data-stu-id="d0ed1-118">Example 1: Create a secure string</span></span>

```powershell
$SecureString = Read-Host -AsSecureString
```

<span data-ttu-id="d0ed1-119">Эта команда создает безопасную строку из символов, введенных через командную строку.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-119">This command creates a secure string from characters that you type at the command prompt.</span></span> <span data-ttu-id="d0ed1-120">После ввода команды введите строку, которую нужно сохранить как безопасную.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-120">After entering the command, type the string you want to store as a secure string.</span></span> <span data-ttu-id="d0ed1-121">`*`Для представления каждого введенного символа отображается звездочка ().</span><span class="sxs-lookup"><span data-stu-id="d0ed1-121">An asterisk (`*`) is displayed to represent each character that you type.</span></span>

### <span data-ttu-id="d0ed1-122">Пример 2. Преобразование защищенной строки в зашифрованную стандартную строку</span><span class="sxs-lookup"><span data-stu-id="d0ed1-122">Example 2: Convert a secure string to an encrypted standard string</span></span>

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

<span data-ttu-id="d0ed1-123">Эта команда преобразует защищенную строку в `$SecureString` переменной в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-123">This command converts the secure string in the `$SecureString` variable to an encrypted standard string.</span></span> <span data-ttu-id="d0ed1-124">Полученная зашифрованная стандартная строка хранится в `$StandardString` переменной.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-124">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

### <span data-ttu-id="d0ed1-125">Пример 3. Преобразование защищенной строки в зашифрованную стандартную строку с помощью 192-разрядного ключа</span><span class="sxs-lookup"><span data-stu-id="d0ed1-125">Example 3: Convert a secure string to an encrypted standard string with a 192-bit key</span></span>

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

<span data-ttu-id="d0ed1-126">Эти команды используют алгоритм AES (AES) для преобразования защищенной строки, хранящейся в `$SecureString` переменной, в зашифрованную стандартную строку с 192-битным ключом.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-126">These commands use the Advanced Encryption Standard (AES) algorithm to convert the secure string stored in the `$SecureString` variable to an encrypted standard string with a 192-bit key.</span></span> <span data-ttu-id="d0ed1-127">Полученная зашифрованная стандартная строка хранится в `$StandardString` переменной.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-127">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

<span data-ttu-id="d0ed1-128">Первая команда сохраняет ключ в `$Key` переменной.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-128">The first command stores a key in the `$Key` variable.</span></span> <span data-ttu-id="d0ed1-129">Ключ представляет собой массив из 24 десятичных цифр, каждый из которых должен быть меньше 256 для размещения в пределах одного байта без знака.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-129">The key is an array of 24 decimal numerals, each of which must be less than 256 to fit within a single unsigned byte.</span></span>

<span data-ttu-id="d0ed1-130">Так как каждое десятичное число представляет собой один байт (8 бит), ключ содержит 24 цифры для всего 192 бит (8 x 24).</span><span class="sxs-lookup"><span data-stu-id="d0ed1-130">Because each decimal numeral represents a single byte (8 bits), the key has 24 digits for a total of 192 bits (8 x 24).</span></span> <span data-ttu-id="d0ed1-131">Это действительный размер ключа для алгоритма AES.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-131">This is a valid key length for the AES algorithm.</span></span>

<span data-ttu-id="d0ed1-132">Вторая команда использует ключ в `$Key` переменной для преобразования защищенной строки в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-132">The second command uses the key in the `$Key` variable to convert the secure string to an encrypted standard string.</span></span>

### <span data-ttu-id="d0ed1-133">Пример 4. Преобразование защищенной строки непосредственно в строку с открытым текстом</span><span class="sxs-lookup"><span data-stu-id="d0ed1-133">Example 4: Convert a secure string directly to a plaintext string</span></span>

```powershell
$secureString = ConvertTo-SecureString -String 'Example' -AsPlainText
$secureString # 'System.Security.SecureString'
ConvertFrom-SecureString -SecureString $secureString -AsPlainText # 'Example'
```

## <span data-ttu-id="d0ed1-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0ed1-134">PARAMETERS</span></span>

### <span data-ttu-id="d0ed1-135">-AsPlainText</span><span class="sxs-lookup"><span data-stu-id="d0ed1-135">-AsPlainText</span></span>

<span data-ttu-id="d0ed1-136">Если этот параметр задан, то в `ConvertFrom-SecureString` качестве выходных данных преобразует защищенные строки в расшифрованную строку в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-136">When set, `ConvertFrom-SecureString` will convert secure strings to the decrypted plaintext string as output.</span></span>

<span data-ttu-id="d0ed1-137">Этот настоящий момент был добавлен в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-137">This paramater was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="d0ed1-138">-Key</span><span class="sxs-lookup"><span data-stu-id="d0ed1-138">-Key</span></span>

<span data-ttu-id="d0ed1-139">Указывает ключ шифрования в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-139">Specifies the encryption key as a byte array.</span></span>

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

### <span data-ttu-id="d0ed1-140">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="d0ed1-140">-SecureKey</span></span>

<span data-ttu-id="d0ed1-141">Указывает ключ шифрования в виде безопасной строки.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-141">Specifies the encryption key as a secure string.</span></span> <span data-ttu-id="d0ed1-142">Значение безопасной строки преобразуется в массив байтов перед использованием в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-142">The secure string value is converted to a byte array before being used as the key.</span></span>

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

### <span data-ttu-id="d0ed1-143">-SecureString</span><span class="sxs-lookup"><span data-stu-id="d0ed1-143">-SecureString</span></span>

<span data-ttu-id="d0ed1-144">Указывает безопасную строку, в которую нужно преобразовать зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-144">Specifies the secure string to convert to an encrypted standard string.</span></span>

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

### <span data-ttu-id="d0ed1-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d0ed1-145">CommonParameters</span></span>

<span data-ttu-id="d0ed1-146">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d0ed1-146">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`,`-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="d0ed1-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d0ed1-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0ed1-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d0ed1-148">INPUTS</span></span>

### <span data-ttu-id="d0ed1-149">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="d0ed1-149">System.Security.SecureString</span></span>

<span data-ttu-id="d0ed1-150">Объект **SecureString** можно передать в ConvertFrom-SecureString.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-150">You can pipe a **SecureString** object to ConvertFrom-SecureString.</span></span>

## <span data-ttu-id="d0ed1-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d0ed1-151">OUTPUTS</span></span>

### <span data-ttu-id="d0ed1-152">System.String</span><span class="sxs-lookup"><span data-stu-id="d0ed1-152">System.String</span></span>

<span data-ttu-id="d0ed1-153">ConvertFrom-SecureString возвращает объект стандартной строки.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-153">ConvertFrom-SecureString returns a standard string object.</span></span>

## <span data-ttu-id="d0ed1-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d0ed1-154">NOTES</span></span>

- <span data-ttu-id="d0ed1-155">Чтобы создать защищенную строку из символов, вводимых в командной строке, используйте параметр **AsSecureString** `Read-Host` командлета.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-155">To create a secure string from characters that are typed at the command prompt, use the **AsSecureString** parameter of the `Read-Host` cmdlet.</span></span>
- <span data-ttu-id="d0ed1-156">При использовании параметров **Key** или **SecureKey** для указания ключа длина ключа должна быть правильной.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-156">When you use the **Key** or **SecureKey** parameters to specify a key, the key length must be correct.</span></span> <span data-ttu-id="d0ed1-157">Например, ключ 128 бит можно указать в виде массива байтов, сокоторый из 16 десятичных цифр.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-157">For example, a key of 128 bits can be specified as a byte array of 16 decimal numerals.</span></span>
  <span data-ttu-id="d0ed1-158">Аналогичным образом, 192-разрядные и 256-битовые ключи соответствуют массивам байтов из 24 и 32 десятичных цифр соответственно.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-158">Similarly, 192-bit and 256-bit keys correspond to byte arrays of 24 and 32 decimal numerals, respectively.</span></span>
- <span data-ttu-id="d0ed1-159">Некоторые символы, например значки настроения, соответствуют нескольким кодовым точкам в строке, в которой они содержатся.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-159">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="d0ed1-160">Старайтесь не использовать эти символы, так как они могут вызвать проблемы и нечеткое понимание при использовании пароля.</span><span class="sxs-lookup"><span data-stu-id="d0ed1-160">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="d0ed1-161">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d0ed1-161">RELATED LINKS</span></span>

[<span data-ttu-id="d0ed1-162">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="d0ed1-162">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)

[<span data-ttu-id="d0ed1-163">Read-Host</span><span class="sxs-lookup"><span data-stu-id="d0ed1-163">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

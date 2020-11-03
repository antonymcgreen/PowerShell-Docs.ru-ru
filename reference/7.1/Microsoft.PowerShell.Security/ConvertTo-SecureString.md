---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: e3ee17ed9c309a02bf2032c039adacf12ccff04f
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "93233226"
---
# <span data-ttu-id="9e2fc-103">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="9e2fc-103">ConvertTo-SecureString</span></span>

## <span data-ttu-id="9e2fc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9e2fc-104">SYNOPSIS</span></span>
<span data-ttu-id="9e2fc-105">Преобразует обычный текст или зашифрованные строки в защищенные строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-105">Converts plain text or encrypted strings to secure strings.</span></span>

## <span data-ttu-id="9e2fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e2fc-106">SYNTAX</span></span>

### <span data-ttu-id="9e2fc-107">Secure (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9e2fc-107">Secure (Default)</span></span>

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="9e2fc-108">PlainText</span><span class="sxs-lookup"><span data-stu-id="9e2fc-108">PlainText</span></span>

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="9e2fc-109">Открыть</span><span class="sxs-lookup"><span data-stu-id="9e2fc-109">Open</span></span>

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="9e2fc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e2fc-110">DESCRIPTION</span></span>

<span data-ttu-id="9e2fc-111">`ConvertTo-SecureString`Командлет преобразует зашифрованные стандартные строки в защищенные строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-111">The `ConvertTo-SecureString` cmdlet converts encrypted standard strings into secure strings.</span></span> <span data-ttu-id="9e2fc-112">Кроме того, он конвертирует простой текст в защищенные строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-112">It can also convert plain text to secure strings.</span></span> <span data-ttu-id="9e2fc-113">Он используется с `ConvertFrom-SecureString` и `Read-Host` .</span><span class="sxs-lookup"><span data-stu-id="9e2fc-113">It is used with `ConvertFrom-SecureString` and `Read-Host`.</span></span> <span data-ttu-id="9e2fc-114">Безопасная строка, созданная командлетом, может использоваться с командлетами или функциями, для которых требуется параметр типа **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-114">The secure string created by the cmdlet can be used with cmdlets or functions that require a parameter of type **SecureString**.</span></span> <span data-ttu-id="9e2fc-115">Безопасную строку можно преобразовать обратно в зашифрованную стандартную строку с помощью `ConvertFrom-SecureString` командлета.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-115">The secure string can be converted back to an encrypted, standard string using the `ConvertFrom-SecureString` cmdlet.</span></span> <span data-ttu-id="9e2fc-116">Это позволит сохранить ее в файле для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-116">This enables it to be stored in a file for later use.</span></span>

<span data-ttu-id="9e2fc-117">Если преобразуемая Стандартная строка была зашифрована с `ConvertFrom-SecureString` помощью указанного ключа, то этот ключ должен быть указан в качестве значения параметра **Key** или **SecureKey** `ConvertTo-SecureString` командлета.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-117">If the standard string being converted was encrypted with `ConvertFrom-SecureString` using a specified key, that same key must be provided as the value of the **Key** or **SecureKey** parameter of the `ConvertTo-SecureString` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9e2fc-118">Обратите внимание, что на [DotNet](/dotnet/api/system.security.securestring#remarks)содержимое SecureString не шифруется в системах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-118">Note that per [DotNet](/dotnet/api/system.security.securestring#remarks), the contents of a SecureString are not encrypted on non-Windows systems.</span></span>

## <span data-ttu-id="9e2fc-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="9e2fc-119">EXAMPLES</span></span>

### <span data-ttu-id="9e2fc-120">Пример 1. Преобразование защищенной строки в зашифрованную строку</span><span class="sxs-lookup"><span data-stu-id="9e2fc-120">Example 1: Convert a secure string to an encrypted string</span></span>

<span data-ttu-id="9e2fc-121">В этом примере показано, как создать защищенную строку из введенных пользователем данных и преобразовать ее в зашифрованную стандартную строку, а затем обратно в защищенную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-121">This example shows how to create a secure string from user input, convert the secure string to an encrypted standard string, and then convert the encrypted standard string back to a secure string.</span></span>

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

<span data-ttu-id="9e2fc-122">Первая команда использует параметр **AsSecureString** `Read-Host` командлета для создания защищенной строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-122">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="9e2fc-123">После ввода команды все вводимые символы преобразуются в защищенную строку и затем сохраняются в `$Secure` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-123">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="9e2fc-124">Вторая команда отображает содержимое `$Secure` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-124">The second command displays the contents of the `$Secure` variable.</span></span> <span data-ttu-id="9e2fc-125">Так как `$Secure` переменная содержит защищенную строку, PowerShell отображает только тип **System. Security. SecureString** .</span><span class="sxs-lookup"><span data-stu-id="9e2fc-125">Because the `$Secure` variable contains a secure string, PowerShell displays only the **System.Security.SecureString** type.</span></span>

<span data-ttu-id="9e2fc-126">Третья команда использует `ConvertFrom-SecureString` командлет для преобразования защищенной строки в `$Secure` переменную в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-126">The third command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string.</span></span> <span data-ttu-id="9e2fc-127">Результат сохраняется в `$Encrypted` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-127">It saves the result in the `$Encrypted` variable.</span></span>

<span data-ttu-id="9e2fc-128">Четвертая команда отображает зашифрованную строку в значении `$Encrypted` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-128">The fourth command displays the encrypted string in the value of the `$Encrypted` variable.</span></span>

<span data-ttu-id="9e2fc-129">Пятая команда использует `ConvertTo-SecureString` командлет для преобразования зашифрованной стандартной строки в `$Encrypted` переменную обратно в безопасную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-129">The fifth command uses the `ConvertTo-SecureString` cmdlet to convert the encrypted standard string in the `$Encrypted` variable back into a secure string.</span></span> <span data-ttu-id="9e2fc-130">Результат сохраняется в `$Secure2` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-130">It saves the result in the `$Secure2` variable.</span></span>
<span data-ttu-id="9e2fc-131">Шестая команда выводит значение `$Secure2` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-131">The sixth command displays the value of the `$Secure2` variable.</span></span> <span data-ttu-id="9e2fc-132">Тип SecureString показывает, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-132">The SecureString type indicates that the command was successful.</span></span>

### <span data-ttu-id="9e2fc-133">Пример 2. Создание защищенной строки из зашифрованной строки в файле</span><span class="sxs-lookup"><span data-stu-id="9e2fc-133">Example 2: Create a secure string from an encrypted string in a file</span></span>

<span data-ttu-id="9e2fc-134">В этом примере показано, как создать защищенную строку из стандартной зашифрованной строки, сохраненной в файл.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-134">This example shows how to create a secure string from an encrypted standard string that is saved in a file.</span></span>

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

<span data-ttu-id="9e2fc-135">Первая команда использует параметр **AsSecureString** `Read-Host` командлета для создания защищенной строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-135">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="9e2fc-136">После ввода команды все вводимые символы преобразуются в защищенную строку и затем сохраняются в `$Secure` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-136">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="9e2fc-137">Вторая команда использует `ConvertFrom-SecureString` командлет для преобразования защищенной строки в `$Secure` переменную в зашифрованную стандартную строку с помощью указанного ключа.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-137">The second command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string by using the specified key.</span></span> <span data-ttu-id="9e2fc-138">Содержимое сохраняется в `$Encrypted` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-138">The contents are saved in the `$Encrypted` variable.</span></span>

<span data-ttu-id="9e2fc-139">Третья команда использует оператор конвейера ( `|` ) для отправки значения `$Encrypted` переменной в `Set-Content` командлет, который сохраняет значение в файле Encrypted.txt.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-139">The third command uses a pipeline operator (`|`) to send the value of the `$Encrypted` variable to the `Set-Content` cmdlet, which saves the value in the Encrypted.txt file.</span></span>

<span data-ttu-id="9e2fc-140">Четвертая команда использует `Get-Content` командлет для получения зашифрованной стандартной строки в файле Encrypted.txt.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-140">The fourth command uses the `Get-Content` cmdlet to get the encrypted standard string in the Encrypted.txt file.</span></span> <span data-ttu-id="9e2fc-141">Команда использует оператор конвейера для отправки зашифрованной строки в `ConvertTo-SecureString` командлет, который преобразует его в защищенную строку с помощью указанного ключа.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-141">The command uses a pipeline operator to send the encrypted string to the `ConvertTo-SecureString` cmdlet, which converts it to a secure string by using the specified key.</span></span>
<span data-ttu-id="9e2fc-142">Результаты сохраняются в `$Secure2` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-142">The results are saved in the `$Secure2` variable.</span></span>

### <span data-ttu-id="9e2fc-143">Пример 3. Преобразование обычной текстовой строки в защищенную строку</span><span class="sxs-lookup"><span data-stu-id="9e2fc-143">Example 3: Convert a plain text string to a secure string</span></span>

<span data-ttu-id="9e2fc-144">Эта команда преобразует обычную текстовую строку `P@ssW0rD!` в защищенную строку и сохраняет результат в `$Secure_String_Pwd` переменной.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-144">This command converts the plain text string `P@ssW0rD!` into a secure string and stores the result in the `$Secure_String_Pwd` variable.</span></span> <span data-ttu-id="9e2fc-145">Чтобы использовать параметр **AsPlainText** , необходимо также включить параметр **Force** в команду.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-145">To use the **AsPlainText** parameter, the **Force** parameter must also be included in the command.</span></span>

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> <span data-ttu-id="9e2fc-146">Не следует использовать обычные текстовые строки в скрипте или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-146">You should avoid using plain text strings in script or from the command line.</span></span> <span data-ttu-id="9e2fc-147">Обычный текст может отображаться в журналах событий и журналах команд.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-147">The plain text can show up in event logs and command history logs.</span></span>

## <span data-ttu-id="9e2fc-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e2fc-148">PARAMETERS</span></span>

### <span data-ttu-id="9e2fc-149">-AsPlainText</span><span class="sxs-lookup"><span data-stu-id="9e2fc-149">-AsPlainText</span></span>

<span data-ttu-id="9e2fc-150">Указывает обычную текстовую строку для преобразования в защищенную.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-150">Specifies a plain text string to convert to a secure string.</span></span> <span data-ttu-id="9e2fc-151">Командлеты защищенной строки помогают защищать секретные тексты.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-151">The secure string cmdlets help protect confidential text.</span></span> <span data-ttu-id="9e2fc-152">Текст шифруется в целях конфиденциальности и после использования удаляется из памяти компьютера.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-152">The text is encrypted for privacy and is deleted from computer memory after it is used.</span></span> <span data-ttu-id="9e2fc-153">Если этот параметр используется для ввода обычного текста, система не сможет его защитить.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-153">If you use this parameter to provide plain text as input, the system cannot protect that input in this manner.</span></span> <span data-ttu-id="9e2fc-154">Чтобы использовать этот параметр, необходимо также указать параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="9e2fc-154">To use this parameter, you must also specify the **Force** parameter.</span></span>

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

### <span data-ttu-id="9e2fc-155">-Force</span><span class="sxs-lookup"><span data-stu-id="9e2fc-155">-Force</span></span>

<span data-ttu-id="9e2fc-156">Подтверждает, что вы понимаете последствия использования параметра **AsPlainText** и все равно хотите использовать его.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-156">Confirms that you understand the implications of using the **AsPlainText** parameter and still want to use it.</span></span>

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

### <span data-ttu-id="9e2fc-157">-Key</span><span class="sxs-lookup"><span data-stu-id="9e2fc-157">-Key</span></span>

<span data-ttu-id="9e2fc-158">Указывает ключ шифрования, используемый для преобразования исходной защищенной строки в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-158">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="9e2fc-159">Допустимые значения длины ключа: 16, 24 и 32 байт.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-159">Valid key lengths are 16, 24 and 32 bytes.</span></span>

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

### <span data-ttu-id="9e2fc-160">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="9e2fc-160">-SecureKey</span></span>

<span data-ttu-id="9e2fc-161">Указывает ключ шифрования, используемый для преобразования исходной защищенной строки в зашифрованную стандартную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-161">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="9e2fc-162">Ключ должен быть предоставлен в формате защищенной строки.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-162">The key must be provided in the format of a secure string.</span></span> <span data-ttu-id="9e2fc-163">Защищенная строка будет преобразована в массив байтов, который будет использоваться в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-163">The secure string will be converted to a byte array to be used as the key.</span></span> <span data-ttu-id="9e2fc-164">Допустимая длина защищенных ключей — 8, 12 и 16 кодовых точек.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-164">Valid secure key lengths are 8, 12 and 16 code points.</span></span>

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

### <span data-ttu-id="9e2fc-165">-String</span><span class="sxs-lookup"><span data-stu-id="9e2fc-165">-String</span></span>

<span data-ttu-id="9e2fc-166">Задает строку для преобразования в защищенную строку.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-166">Specifies the string to convert to a secure string.</span></span>

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

### <span data-ttu-id="9e2fc-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9e2fc-167">CommonParameters</span></span>

<span data-ttu-id="9e2fc-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e2fc-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e2fc-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e2fc-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9e2fc-170">INPUTS</span></span>

### <span data-ttu-id="9e2fc-171">System.String</span><span class="sxs-lookup"><span data-stu-id="9e2fc-171">System.String</span></span>

<span data-ttu-id="9e2fc-172">Стандартную зашифрованную строку можно передать в `ConvertTo-SecureString` .</span><span class="sxs-lookup"><span data-stu-id="9e2fc-172">You can pipe a standard encrypted string to `ConvertTo-SecureString`.</span></span>

## <span data-ttu-id="9e2fc-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9e2fc-173">OUTPUTS</span></span>

### <span data-ttu-id="9e2fc-174">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="9e2fc-174">System.Security.SecureString</span></span>

<span data-ttu-id="9e2fc-175">`ConvertTo-SecureString` Возвращает объект **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="9e2fc-175">`ConvertTo-SecureString` returns a **SecureString** object.</span></span>

## <span data-ttu-id="9e2fc-176">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9e2fc-176">NOTES</span></span>

<span data-ttu-id="9e2fc-177">Некоторые символы, например значки настроения, соответствуют нескольким кодовым точкам в строке, в которой они содержатся.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-177">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="9e2fc-178">Старайтесь не использовать эти символы, так как они могут вызвать проблемы и нечеткое понимание при использовании пароля.</span><span class="sxs-lookup"><span data-stu-id="9e2fc-178">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="9e2fc-179">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9e2fc-179">RELATED LINKS</span></span>

[<span data-ttu-id="9e2fc-180">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="9e2fc-180">ConvertFrom-SecureString</span></span>](ConvertFrom-SecureString.md)

[<span data-ttu-id="9e2fc-181">Read-Host</span><span class="sxs-lookup"><span data-stu-id="9e2fc-181">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

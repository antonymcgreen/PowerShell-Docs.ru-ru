---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 2efe75730ef7d35618dc0d1fbf7a8d6f8a5db5ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603951"
---
# <span data-ttu-id="93433-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="93433-102">Read-Host</span></span>

## <span data-ttu-id="93433-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="93433-103">SYNOPSIS</span></span>
<span data-ttu-id="93433-104">Считывает строку ввода из консоли.</span><span class="sxs-lookup"><span data-stu-id="93433-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="93433-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93433-105">SYNTAX</span></span>

### <span data-ttu-id="93433-106">AsString (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="93433-106">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="93433-107">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="93433-107">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="93433-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="93433-108">DESCRIPTION</span></span>

<span data-ttu-id="93433-109">`Read-Host`Командлет считывает строку входных данных из консоли.</span><span class="sxs-lookup"><span data-stu-id="93433-109">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="93433-110">Его можно использовать для запроса ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="93433-110">You can use it to prompt a user for input.</span></span> <span data-ttu-id="93433-111">Так как входные данные можно сохранить в виде защищенной строки, этот командлет можно использовать, чтобы запросить у пользователя защищенные данные, такие как пароли, а также общие данные.</span><span class="sxs-lookup"><span data-stu-id="93433-111">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="93433-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="93433-112">EXAMPLES</span></span>

### <span data-ttu-id="93433-113">Пример 1. Сохранение входных данных консоли в переменную</span><span class="sxs-lookup"><span data-stu-id="93433-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="93433-114">В этом примере отображается строка "введите свой возраст:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="93433-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="93433-115">Если введено значение и нажата клавиша ВВОД, значение сохраняется в `$Age` переменной.</span><span class="sxs-lookup"><span data-stu-id="93433-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="93433-116">Пример 2. Сохранение входных данных консоли в виде защищенной строки</span><span class="sxs-lookup"><span data-stu-id="93433-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="93433-117">В этом примере отображается строка "введите пароль:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="93433-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="93433-118">При вводе значения в `*` консоли вместо входных данных появятся звездочки ().</span><span class="sxs-lookup"><span data-stu-id="93433-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="93433-119">При нажатии клавиши Ввод значение сохраняется как объект **SecureString** в `$pwd_secure_string` переменной.</span><span class="sxs-lookup"><span data-stu-id="93433-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="93433-120">Пример 3. входные данные маски и в виде строки с открытым текстом</span><span class="sxs-lookup"><span data-stu-id="93433-120">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="93433-121">В этом примере отображается строка "введите пароль:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="93433-121">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="93433-122">При вводе значения в `*` консоли вместо входных данных появятся звездочки ().</span><span class="sxs-lookup"><span data-stu-id="93433-122">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="93433-123">При нажатии клавиши Ввод значение сохраняется как объект **строкового** текста в `$pwd_string` переменной.</span><span class="sxs-lookup"><span data-stu-id="93433-123">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="93433-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93433-124">PARAMETERS</span></span>

### <span data-ttu-id="93433-125">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="93433-125">-AsSecureString</span></span>

<span data-ttu-id="93433-126">Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="93433-126">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="93433-127">При использовании этого параметра выходные данные `Read-Host` командлета являются объектом **SecureString** (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="93433-127">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsSecureString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93433-128">-Маскинпут</span><span class="sxs-lookup"><span data-stu-id="93433-128">-MaskInput</span></span>

<span data-ttu-id="93433-129">Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="93433-129">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="93433-130">При использовании этого параметра выходные данные `Read-Host` командлета являются **строковым** объектом.</span><span class="sxs-lookup"><span data-stu-id="93433-130">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="93433-131">Это позволяет безопасно запрашивать пароль, который возвращается в виде обычного текста, а не **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="93433-131">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93433-132">-Prompt</span><span class="sxs-lookup"><span data-stu-id="93433-132">-Prompt</span></span>

<span data-ttu-id="93433-133">Задает текст запроса.</span><span class="sxs-lookup"><span data-stu-id="93433-133">Specifies the text of the prompt.</span></span>
<span data-ttu-id="93433-134">Введите строку.</span><span class="sxs-lookup"><span data-stu-id="93433-134">Type a string.</span></span>
<span data-ttu-id="93433-135">Если строка содержит пробелы, заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="93433-135">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="93433-136">PowerShell добавляет двоеточие ( `:` ) в введенный текст.</span><span class="sxs-lookup"><span data-stu-id="93433-136">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93433-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="93433-137">CommonParameters</span></span>

<span data-ttu-id="93433-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="93433-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93433-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="93433-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93433-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="93433-140">INPUTS</span></span>

### <span data-ttu-id="93433-141">None</span><span class="sxs-lookup"><span data-stu-id="93433-141">None</span></span>

<span data-ttu-id="93433-142">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="93433-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="93433-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="93433-143">OUTPUTS</span></span>

### <span data-ttu-id="93433-144">System. String или System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="93433-144">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="93433-145">Если используется параметр **AsSecureString** , `Read-Host` возвращает **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="93433-145">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="93433-146">В противном случае возвращается строка.</span><span class="sxs-lookup"><span data-stu-id="93433-146">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="93433-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="93433-147">NOTES</span></span>

## <span data-ttu-id="93433-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="93433-148">RELATED LINKS</span></span>

[<span data-ttu-id="93433-149">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="93433-149">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="93433-150">Get-Host</span><span class="sxs-lookup"><span data-stu-id="93433-150">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="93433-151">Write-Host</span><span class="sxs-lookup"><span data-stu-id="93433-151">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="93433-152">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="93433-152">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)

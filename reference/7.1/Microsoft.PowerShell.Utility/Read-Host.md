---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: b76fc092046a29dcad52f755794fd55dd84ac675
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "93229626"
---
# <span data-ttu-id="aed78-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="aed78-103">Read-Host</span></span>

## <span data-ttu-id="aed78-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aed78-104">SYNOPSIS</span></span>
<span data-ttu-id="aed78-105">Считывает строку ввода из консоли.</span><span class="sxs-lookup"><span data-stu-id="aed78-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="aed78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aed78-106">SYNTAX</span></span>

### <span data-ttu-id="aed78-107">AsString (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="aed78-107">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="aed78-108">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="aed78-108">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="aed78-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aed78-109">DESCRIPTION</span></span>

<span data-ttu-id="aed78-110">`Read-Host`Командлет считывает строку входных данных из консоли.</span><span class="sxs-lookup"><span data-stu-id="aed78-110">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="aed78-111">Его можно использовать для запроса ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="aed78-111">You can use it to prompt a user for input.</span></span> <span data-ttu-id="aed78-112">Так как входные данные можно сохранить в виде защищенной строки, этот командлет можно использовать, чтобы запросить у пользователя защищенные данные, такие как пароли, а также общие данные.</span><span class="sxs-lookup"><span data-stu-id="aed78-112">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="aed78-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="aed78-113">EXAMPLES</span></span>

### <span data-ttu-id="aed78-114">Пример 1. Сохранение входных данных консоли в переменную</span><span class="sxs-lookup"><span data-stu-id="aed78-114">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="aed78-115">В этом примере отображается строка "введите свой возраст:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="aed78-115">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="aed78-116">Если введено значение и нажата клавиша ВВОД, значение сохраняется в `$Age` переменной.</span><span class="sxs-lookup"><span data-stu-id="aed78-116">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="aed78-117">Пример 2. Сохранение входных данных консоли в виде защищенной строки</span><span class="sxs-lookup"><span data-stu-id="aed78-117">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="aed78-118">В этом примере отображается строка "введите пароль:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="aed78-118">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="aed78-119">При вводе значения в `*` консоли вместо входных данных появятся звездочки ().</span><span class="sxs-lookup"><span data-stu-id="aed78-119">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="aed78-120">При нажатии клавиши Ввод значение сохраняется как объект **SecureString** в `$pwd_secure_string` переменной.</span><span class="sxs-lookup"><span data-stu-id="aed78-120">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="aed78-121">Пример 3. входные данные маски и в виде строки с открытым текстом</span><span class="sxs-lookup"><span data-stu-id="aed78-121">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="aed78-122">В этом примере отображается строка "введите пароль:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="aed78-122">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="aed78-123">При вводе значения в `*` консоли вместо входных данных появятся звездочки ().</span><span class="sxs-lookup"><span data-stu-id="aed78-123">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="aed78-124">При нажатии клавиши Ввод значение сохраняется как объект **строкового** текста в `$pwd_string` переменной.</span><span class="sxs-lookup"><span data-stu-id="aed78-124">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="aed78-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aed78-125">PARAMETERS</span></span>

### <span data-ttu-id="aed78-126">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="aed78-126">-AsSecureString</span></span>

<span data-ttu-id="aed78-127">Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="aed78-127">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="aed78-128">При использовании этого параметра выходные данные `Read-Host` командлета являются объектом **SecureString** ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="aed78-128">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="aed78-129">-Маскинпут</span><span class="sxs-lookup"><span data-stu-id="aed78-129">-MaskInput</span></span>

<span data-ttu-id="aed78-130">Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="aed78-130">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="aed78-131">При использовании этого параметра выходные данные `Read-Host` командлета являются **строковым** объектом.</span><span class="sxs-lookup"><span data-stu-id="aed78-131">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="aed78-132">Это позволяет безопасно запрашивать пароль, который возвращается в виде обычного текста, а не **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="aed78-132">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString** .</span></span>

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

### <span data-ttu-id="aed78-133">-Prompt</span><span class="sxs-lookup"><span data-stu-id="aed78-133">-Prompt</span></span>

<span data-ttu-id="aed78-134">Задает текст запроса.</span><span class="sxs-lookup"><span data-stu-id="aed78-134">Specifies the text of the prompt.</span></span>
<span data-ttu-id="aed78-135">Введите строку.</span><span class="sxs-lookup"><span data-stu-id="aed78-135">Type a string.</span></span>
<span data-ttu-id="aed78-136">Если строка содержит пробелы, заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="aed78-136">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="aed78-137">PowerShell добавляет двоеточие ( `:` ) в введенный текст.</span><span class="sxs-lookup"><span data-stu-id="aed78-137">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="aed78-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aed78-138">CommonParameters</span></span>

<span data-ttu-id="aed78-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aed78-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aed78-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aed78-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aed78-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aed78-141">INPUTS</span></span>

### <span data-ttu-id="aed78-142">Нет</span><span class="sxs-lookup"><span data-stu-id="aed78-142">None</span></span>

<span data-ttu-id="aed78-143">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="aed78-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="aed78-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aed78-144">OUTPUTS</span></span>

### <span data-ttu-id="aed78-145">System. String или System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="aed78-145">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="aed78-146">Если используется параметр **AsSecureString** , `Read-Host` возвращает **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="aed78-146">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString** .</span></span> <span data-ttu-id="aed78-147">В противном случае возвращается строка.</span><span class="sxs-lookup"><span data-stu-id="aed78-147">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="aed78-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aed78-148">NOTES</span></span>

## <span data-ttu-id="aed78-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aed78-149">RELATED LINKS</span></span>

[<span data-ttu-id="aed78-150">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="aed78-150">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="aed78-151">Get-Host</span><span class="sxs-lookup"><span data-stu-id="aed78-151">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="aed78-152">Write-Host</span><span class="sxs-lookup"><span data-stu-id="aed78-152">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="aed78-153">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="aed78-153">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)

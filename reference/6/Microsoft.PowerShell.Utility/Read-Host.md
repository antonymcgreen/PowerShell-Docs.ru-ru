---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 8e0c1057a4117eb60cdc8ec494470dacaca78699
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "93229630"
---
# <span data-ttu-id="8b7d8-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="8b7d8-103">Read-Host</span></span>

## <span data-ttu-id="8b7d8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8b7d8-104">SYNOPSIS</span></span>
<span data-ttu-id="8b7d8-105">Считывает строку ввода из консоли.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="8b7d8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b7d8-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="8b7d8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8b7d8-107">DESCRIPTION</span></span>

<span data-ttu-id="8b7d8-108">`Read-Host`Командлет считывает строку входных данных из консоли.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="8b7d8-109">Его можно использовать для запроса ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="8b7d8-110">Так как входные данные можно сохранить в виде защищенной строки, этот командлет можно использовать, чтобы запросить у пользователя защищенные данные, такие как пароли, а также общие данные.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="8b7d8-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8b7d8-111">EXAMPLES</span></span>

### <span data-ttu-id="8b7d8-112">Пример 1. Сохранение входных данных консоли в переменную</span><span class="sxs-lookup"><span data-stu-id="8b7d8-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="8b7d8-113">В этом примере отображается строка "введите свой возраст:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="8b7d8-114">Если введено значение и нажата клавиша ВВОД, значение сохраняется в `$Age` переменной.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="8b7d8-115">Пример 2. Сохранение входных данных консоли в виде защищенной строки</span><span class="sxs-lookup"><span data-stu-id="8b7d8-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="8b7d8-116">В этом примере отображается строка "введите пароль:" в качестве подсказки.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="8b7d8-117">При вводе значения в `*` консоли вместо входных данных появятся звездочки ().</span><span class="sxs-lookup"><span data-stu-id="8b7d8-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="8b7d8-118">При нажатии клавиши Ввод значение сохраняется как объект **SecureString** в `$pwd_secure_string` переменной.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="8b7d8-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b7d8-119">PARAMETERS</span></span>

### <span data-ttu-id="8b7d8-120">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="8b7d8-120">-AsSecureString</span></span>

<span data-ttu-id="8b7d8-121">Указывает, что командлет отображает звездочки ( `*` ) вместо символов, которые пользователь вводит в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="8b7d8-122">При использовании этого параметра выходные данные `Read-Host` командлета являются объектом **SecureString** ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="8b7d8-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="8b7d8-123">-Prompt</span><span class="sxs-lookup"><span data-stu-id="8b7d8-123">-Prompt</span></span>

<span data-ttu-id="8b7d8-124">Задает текст запроса.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="8b7d8-125">Введите строку.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-125">Type a string.</span></span>
<span data-ttu-id="8b7d8-126">Если строка содержит пробелы, заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="8b7d8-127">PowerShell добавляет двоеточие ( `:` ) в введенный текст.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="8b7d8-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8b7d8-128">CommonParameters</span></span>

<span data-ttu-id="8b7d8-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b7d8-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8b7d8-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b7d8-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8b7d8-131">INPUTS</span></span>

### <span data-ttu-id="8b7d8-132">Нет</span><span class="sxs-lookup"><span data-stu-id="8b7d8-132">None</span></span>

<span data-ttu-id="8b7d8-133">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8b7d8-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8b7d8-134">OUTPUTS</span></span>

### <span data-ttu-id="8b7d8-135">System. String или System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="8b7d8-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="8b7d8-136">Если используется параметр **AsSecureString** , `Read-Host` возвращает **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="8b7d8-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString** .</span></span> <span data-ttu-id="8b7d8-137">В противном случае возвращается строка.</span><span class="sxs-lookup"><span data-stu-id="8b7d8-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="8b7d8-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8b7d8-138">NOTES</span></span>

## <span data-ttu-id="8b7d8-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8b7d8-139">RELATED LINKS</span></span>

[<span data-ttu-id="8b7d8-140">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="8b7d8-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="8b7d8-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="8b7d8-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="8b7d8-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="8b7d8-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="8b7d8-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="8b7d8-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)

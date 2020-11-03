---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227809"
---
# <span data-ttu-id="21b92-103">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="21b92-103">Get-OperationValidation</span></span>

## <span data-ttu-id="21b92-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="21b92-104">SYNOPSIS</span></span>
<span data-ttu-id="21b92-105">Возвращает тесты инфраструктуры проверки операций.</span><span class="sxs-lookup"><span data-stu-id="21b92-105">Gets Operation Validation Framework tests.</span></span>

## <span data-ttu-id="21b92-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21b92-106">SYNTAX</span></span>

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="21b92-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21b92-107">DESCRIPTION</span></span>
<span data-ttu-id="21b92-108">Командлет **Get-оператионвалидатион** возвращает платформу проверки операций для установленных модулей.</span><span class="sxs-lookup"><span data-stu-id="21b92-108">The **Get-OperationValidation** cmdlet gets Operation Validation Framework tests for installed modules.</span></span>

<span data-ttu-id="21b92-109">Модули, содержащие папку Diagnostics, проверяются на наличие Pester тестов в простой или полной вложенной папке или в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="21b92-109">Modules that include a Diagnostics folder are inspected for Pester tests in the Simple or Comprehensive subfolder, or both.</span></span>

## <span data-ttu-id="21b92-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="21b92-110">EXAMPLES</span></span>

### <span data-ttu-id="21b92-111">Пример 1. Проверка операций Get</span><span class="sxs-lookup"><span data-stu-id="21b92-111">Example 1: Get Operation Validation tests</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

<span data-ttu-id="21b92-112">Эта команда получает проверочные тесты из модуля с именем подставлял в папке К:\темп\модулес.</span><span class="sxs-lookup"><span data-stu-id="21b92-112">This command gets validation tests from the module named AddNumbers in the C:\temp\modules folder.</span></span>

## <span data-ttu-id="21b92-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21b92-113">PARAMETERS</span></span>

### <span data-ttu-id="21b92-114">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="21b92-114">-ModuleName</span></span>
<span data-ttu-id="21b92-115">Указывает массив имен модулей.</span><span class="sxs-lookup"><span data-stu-id="21b92-115">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b92-116">-TestType</span><span class="sxs-lookup"><span data-stu-id="21b92-116">-TestType</span></span>
<span data-ttu-id="21b92-117">Указывает массив типов тестов.</span><span class="sxs-lookup"><span data-stu-id="21b92-117">Specifies an array of test types.</span></span>
<span data-ttu-id="21b92-118">Допустимые значения: Simple, всесторонний или Both.</span><span class="sxs-lookup"><span data-stu-id="21b92-118">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="21b92-119">Значение по умолчанию — Simple, всеобъемлющее.</span><span class="sxs-lookup"><span data-stu-id="21b92-119">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b92-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="21b92-120">CommonParameters</span></span>
<span data-ttu-id="21b92-121">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21b92-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21b92-122">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="21b92-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21b92-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="21b92-123">INPUTS</span></span>

### <span data-ttu-id="21b92-124">Нет</span><span class="sxs-lookup"><span data-stu-id="21b92-124">None</span></span>
<span data-ttu-id="21b92-125">В этот командлет нельзя передавать входные данные.</span><span class="sxs-lookup"><span data-stu-id="21b92-125">You cannot pipe any input to this cmdlet.</span></span>

## <span data-ttu-id="21b92-126">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="21b92-126">OUTPUTS</span></span>

### <span data-ttu-id="21b92-127">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="21b92-127">PSCustomObject</span></span>
<span data-ttu-id="21b92-128">**PSCustomObject** описывает проверку.</span><span class="sxs-lookup"><span data-stu-id="21b92-128">The **PSCustomObject** describes the validation.</span></span>

## <span data-ttu-id="21b92-129">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="21b92-129">NOTES</span></span>

## <span data-ttu-id="21b92-130">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="21b92-130">RELATED LINKS</span></span>

[<span data-ttu-id="21b92-131">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="21b92-131">Invoke-OperationValidation</span></span>](Invoke-OperationValidation.md)

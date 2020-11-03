---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/invoke-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-OperationValidation
ms.openlocfilehash: 6c9d4001392de48032a0fe1ba3667db90ea614fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227806"
---
# <span data-ttu-id="9b139-103">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="9b139-103">Invoke-OperationValidation</span></span>

## <span data-ttu-id="9b139-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9b139-104">SYNOPSIS</span></span>

<span data-ttu-id="9b139-105">Вызывает тесты инфраструктуры проверки операций.</span><span class="sxs-lookup"><span data-stu-id="9b139-105">Invokes Operation Validation Framework tests.</span></span>

## <span data-ttu-id="9b139-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b139-106">SYNTAX</span></span>

### <span data-ttu-id="9b139-107">Филеандтест (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9b139-107">FileAndTest (Default)</span></span>

```
Invoke-OperationValidation [-TestInfo <PSObject[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="9b139-108">Путь</span><span class="sxs-lookup"><span data-stu-id="9b139-108">Path</span></span>

```
Invoke-OperationValidation [-testFilePath <String[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="9b139-109">усежетоператионтест</span><span class="sxs-lookup"><span data-stu-id="9b139-109">UseGetOperationTest</span></span>

```
Invoke-OperationValidation [-ModuleName <String[]>] [-TestType <String[]>] [-IncludePesterOutput] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9b139-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b139-110">DESCRIPTION</span></span>

<span data-ttu-id="9b139-111">Командлет **Invoke-оператионвалидатион** вызывает тесты инфраструктуры проверки операций для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="9b139-111">The **Invoke-OperationValidation** cmdlet invokes Operation Validation Framework tests for a specified module.</span></span>

## <span data-ttu-id="9b139-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="9b139-112">EXAMPLES</span></span>

### <span data-ttu-id="9b139-113">Пример 1. вызов проверки операции</span><span class="sxs-lookup"><span data-stu-id="9b139-113">Example 1: Invoke an Operation Validation test</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "OperationValidation" | Invoke-OperationValidation -IncludePesterOutput
Describing Simple Test Suite
 [+] first Operational test 20ms
 [+] second Operational test 19ms
 [+] third Operational test 9ms
Tests completed in 48ms
Passed: 3 Failed: 0 Skipped: 0 Pending: 0
Describing Scenario targeted tests
   Context The RemoteAccess service
    [+] The service is running 37ms
   Context The Firewall Rules
    [+] A rule for TCP port 3389 is enabled 1.19s
    [+] A rule for UDP port 3389 is enabled 11ms
Tests completed in 1.24s
Passed: 3 Failed: 0 Skipped: 0 Pending: 0




   Module: OperationValidation




Result  Name
------- --------
Passed  Simple Test Suite::first Operational test
Passed  Simple Test Suite::second Operational test
Passed  Simple Test Suite::third Operational test
Passed  Scenario targeted tests:The RemoteAccess service:The service is running
Passed  Scenario targeted tests:The Firewall Rules:A rule for TCP port 3389 is enabled
Passed  Scenario targeted tests:The Firewall Rules:A rule for UDP port 3389 is enabled
```

<span data-ttu-id="9b139-114">Эта команда получает модуль с именем Оператионвалидатион и использует оператор конвейера для передачи его в командлет **Invoke-оператионвалидатион** , который выполняет тест.</span><span class="sxs-lookup"><span data-stu-id="9b139-114">This command gets the module named OperationValidation, and uses the pipeline operator to pass it to the **Invoke-OperationValidation** cmdlet, which runs the test.</span></span>

## <span data-ttu-id="9b139-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b139-115">PARAMETERS</span></span>

### <span data-ttu-id="9b139-116">-Инклудепестераутпут</span><span class="sxs-lookup"><span data-stu-id="9b139-116">-IncludePesterOutput</span></span>

<span data-ttu-id="9b139-117">Включает выходные данные теста Pester.</span><span class="sxs-lookup"><span data-stu-id="9b139-117">Includes Pester test output.</span></span>
<span data-ttu-id="9b139-118">Значение по умолчанию — $False.</span><span class="sxs-lookup"><span data-stu-id="9b139-118">The default is $False.</span></span>

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

### <span data-ttu-id="9b139-119">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="9b139-119">-ModuleName</span></span>

<span data-ttu-id="9b139-120">Указывает массив имен модулей.</span><span class="sxs-lookup"><span data-stu-id="9b139-120">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-121">-Тестфилепас</span><span class="sxs-lookup"><span data-stu-id="9b139-121">-testFilePath</span></span>

<span data-ttu-id="9b139-122">Задает путь к тестовому файлу инфраструктуры проверки операций.</span><span class="sxs-lookup"><span data-stu-id="9b139-122">Specifies the path of an Operation Validation Framework test file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-123">-TestInfo</span><span class="sxs-lookup"><span data-stu-id="9b139-123">-TestInfo</span></span>

<span data-ttu-id="9b139-124">Задает пользовательский объект, указывающий путь к файлу и имя теста для запуска.</span><span class="sxs-lookup"><span data-stu-id="9b139-124">Specifies a custom object that specifies the path to the file and the name of the test to run.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: FileAndTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-125">-TestType</span><span class="sxs-lookup"><span data-stu-id="9b139-125">-TestType</span></span>

<span data-ttu-id="9b139-126">Указывает массив типов тестов.</span><span class="sxs-lookup"><span data-stu-id="9b139-126">Specifies an array of test types.</span></span>
<span data-ttu-id="9b139-127">Допустимые значения: Simple, всесторонний или Both.</span><span class="sxs-lookup"><span data-stu-id="9b139-127">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="9b139-128">Значение по умолчанию — Simple, всеобъемлющее.</span><span class="sxs-lookup"><span data-stu-id="9b139-128">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9b139-129">-Confirm</span></span>

<span data-ttu-id="9b139-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9b139-130">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9b139-131">-WhatIf</span></span>

<span data-ttu-id="9b139-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9b139-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9b139-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9b139-133">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9b139-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9b139-134">CommonParameters</span></span>
<span data-ttu-id="9b139-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9b139-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b139-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9b139-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b139-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9b139-137">INPUTS</span></span>

### <span data-ttu-id="9b139-138">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9b139-138">PSCustomObject</span></span>

<span data-ttu-id="9b139-139">Выходные данные **Get-оператионвалидатион** можно передать этому командлету.</span><span class="sxs-lookup"><span data-stu-id="9b139-139">You can pipe the output of **Get-OperationValidation** to this cmdlet.</span></span>

## <span data-ttu-id="9b139-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9b139-140">OUTPUTS</span></span>

### <span data-ttu-id="9b139-141">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9b139-141">PSCustomObject</span></span>

<span data-ttu-id="9b139-142">**PSCustomObject** описывает, была ли проверка успешной.</span><span class="sxs-lookup"><span data-stu-id="9b139-142">The **PSCustomObject** describes whether the validation was successful.</span></span>

## <span data-ttu-id="9b139-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9b139-143">NOTES</span></span>

## <span data-ttu-id="9b139-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9b139-144">RELATED LINKS</span></span>

[<span data-ttu-id="9b139-145">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="9b139-145">Get-OperationValidation</span></span>](Get-OperationValidation.md)

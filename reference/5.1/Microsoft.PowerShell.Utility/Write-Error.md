---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: 51698fa0ac5b12a76dec10717d01ef1ec188221c
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232817"
---
# <span data-ttu-id="778fd-103">Write-Error</span><span class="sxs-lookup"><span data-stu-id="778fd-103">Write-Error</span></span>

## <span data-ttu-id="778fd-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="778fd-104">SYNOPSIS</span></span>
<span data-ttu-id="778fd-105">Записывает объект в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="778fd-105">Writes an object to the error stream.</span></span>

## <span data-ttu-id="778fd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="778fd-106">SYNTAX</span></span>

### <span data-ttu-id="778fd-107">Except (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="778fd-107">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="778fd-108">висексцептион</span><span class="sxs-lookup"><span data-stu-id="778fd-108">WithException</span></span>

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="778fd-109">ерроррекорд</span><span class="sxs-lookup"><span data-stu-id="778fd-109">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="778fd-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="778fd-110">DESCRIPTION</span></span>

<span data-ttu-id="778fd-111">`Write-Error`Командлет объявляет неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="778fd-111">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="778fd-112">По умолчанию ошибки отправляются в основную программу для отображения вместе с выводом.</span><span class="sxs-lookup"><span data-stu-id="778fd-112">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="778fd-113">Устранимую можно записать путем отправки строки сообщения об ошибке, объекта **ErrorRecord** или объекта **Exception**.</span><span class="sxs-lookup"><span data-stu-id="778fd-113">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="778fd-114">Используйте другие параметры `Write-Error` для заполнения записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="778fd-114">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="778fd-115">Устранимые ошибки записываются в поток, но не прерывают обработку команд.</span><span class="sxs-lookup"><span data-stu-id="778fd-115">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="778fd-116">Если один из элементов в коллекции элементов ввода объявляет устранимую ошибку, команда продолжает обработку других элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="778fd-116">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="778fd-117">Чтобы объявить завершающую ошибку, используйте `Throw` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="778fd-117">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="778fd-118">Дополнительные сведения см. в разделе [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span><span class="sxs-lookup"><span data-stu-id="778fd-118">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="778fd-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="778fd-119">EXAMPLES</span></span>

### <span data-ttu-id="778fd-120">Пример 1. запись ошибки для объекта RegistryKey</span><span class="sxs-lookup"><span data-stu-id="778fd-120">Example 1: Write an error for RegistryKey object</span></span>

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

<span data-ttu-id="778fd-121">Эта команда объявляет неустранимую ошибку `Get-ChildItem` , когда командлет возвращает `Microsoft.Win32.RegistryKey` объект, например объекты на `HKLM:` `HKCU:` дисках или поставщика реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="778fd-121">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="778fd-122">Пример 2. запись сообщения об ошибке в консоль</span><span class="sxs-lookup"><span data-stu-id="778fd-122">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="778fd-123">Эта команда объявляет устранимую ошибку и записывает ошибку «Отказано в доступе».</span><span class="sxs-lookup"><span data-stu-id="778fd-123">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="778fd-124">Для задания сообщения в команде используется параметр **Message** , однако, имя параметра **Message** опущено, поскольку указывать его не обязательно.</span><span class="sxs-lookup"><span data-stu-id="778fd-124">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="778fd-125">Пример 3. запись ошибки в консоль и указание категории</span><span class="sxs-lookup"><span data-stu-id="778fd-125">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="778fd-126">Эта команда объявляет устранимую ошибку и указывает ее категорию.</span><span class="sxs-lookup"><span data-stu-id="778fd-126">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="778fd-127">Пример 4. запись ошибки с помощью объекта исключения</span><span class="sxs-lookup"><span data-stu-id="778fd-127">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="778fd-128">Эта команда объявляет устранимую ошибку с помощью объекта **Exception**.</span><span class="sxs-lookup"><span data-stu-id="778fd-128">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="778fd-129">Первая команда создает объект **System.Exception** , используя хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="778fd-129">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="778fd-130">Объект исключения сохраняется в `$E` переменной.</span><span class="sxs-lookup"><span data-stu-id="778fd-130">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="778fd-131">Хэш-таблицу можно использовать для создания любого объекта с конструктором типа, имеющим значение null.</span><span class="sxs-lookup"><span data-stu-id="778fd-131">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="778fd-132">Вторая команда использует `Write-Error` командлет для объявления незавершающей ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-132">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="778fd-133">Значение параметра **исключения** является объектом **исключения** в `$E` переменной.</span><span class="sxs-lookup"><span data-stu-id="778fd-133">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="778fd-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="778fd-134">PARAMETERS</span></span>

### <span data-ttu-id="778fd-135">-Category</span><span class="sxs-lookup"><span data-stu-id="778fd-135">-Category</span></span>

<span data-ttu-id="778fd-136">Задает категорию ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-136">Specifies the category of the error.</span></span> <span data-ttu-id="778fd-137">Значение по умолчанию — **NotSpecified**.</span><span class="sxs-lookup"><span data-stu-id="778fd-137">The default value is **NotSpecified**.</span></span> <span data-ttu-id="778fd-138">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="778fd-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="778fd-139">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="778fd-139">NotSpecified</span></span>
- <span data-ttu-id="778fd-140">опенеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-140">OpenError</span></span>
- <span data-ttu-id="778fd-141">клосиррор</span><span class="sxs-lookup"><span data-stu-id="778fd-141">CloseError</span></span>
- <span data-ttu-id="778fd-142">девицееррор</span><span class="sxs-lookup"><span data-stu-id="778fd-142">DeviceError</span></span>
- <span data-ttu-id="778fd-143">деадлоккдетектед</span><span class="sxs-lookup"><span data-stu-id="778fd-143">DeadlockDetected</span></span>
- <span data-ttu-id="778fd-144">InvalidArgument</span><span class="sxs-lookup"><span data-stu-id="778fd-144">InvalidArgument</span></span>
- <span data-ttu-id="778fd-145">InvalidData</span><span class="sxs-lookup"><span data-stu-id="778fd-145">InvalidData</span></span>
- <span data-ttu-id="778fd-146">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="778fd-146">InvalidOperation</span></span>
- <span data-ttu-id="778fd-147">инвалидресулт</span><span class="sxs-lookup"><span data-stu-id="778fd-147">InvalidResult</span></span>
- <span data-ttu-id="778fd-148">инвалидтипе</span><span class="sxs-lookup"><span data-stu-id="778fd-148">InvalidType</span></span>
- <span data-ttu-id="778fd-149">метадатаеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-149">MetadataError</span></span>
- <span data-ttu-id="778fd-150">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="778fd-150">NotImplemented</span></span>
- <span data-ttu-id="778fd-151">нотинсталлед</span><span class="sxs-lookup"><span data-stu-id="778fd-151">NotInstalled</span></span>
- <span data-ttu-id="778fd-152">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="778fd-152">ObjectNotFound</span></span>
- <span data-ttu-id="778fd-153">оператионстоппед</span><span class="sxs-lookup"><span data-stu-id="778fd-153">OperationStopped</span></span>
- <span data-ttu-id="778fd-154">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="778fd-154">OperationTimeout</span></span>
- <span data-ttu-id="778fd-155">SyntaxError</span><span class="sxs-lookup"><span data-stu-id="778fd-155">SyntaxError</span></span>
- <span data-ttu-id="778fd-156">парсереррор</span><span class="sxs-lookup"><span data-stu-id="778fd-156">ParserError</span></span>
- <span data-ttu-id="778fd-157">пермиссиондениед</span><span class="sxs-lookup"><span data-stu-id="778fd-157">PermissionDenied</span></span>
- <span data-ttu-id="778fd-158">ресаурцебуси</span><span class="sxs-lookup"><span data-stu-id="778fd-158">ResourceBusy</span></span>
- <span data-ttu-id="778fd-159">ресаурцеексистс</span><span class="sxs-lookup"><span data-stu-id="778fd-159">ResourceExists</span></span>
- <span data-ttu-id="778fd-160">ресаурцеунаваилабле</span><span class="sxs-lookup"><span data-stu-id="778fd-160">ResourceUnavailable</span></span>
- <span data-ttu-id="778fd-161">реадеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-161">ReadError</span></span>
- <span data-ttu-id="778fd-162">WriteError</span><span class="sxs-lookup"><span data-stu-id="778fd-162">WriteError</span></span>
- <span data-ttu-id="778fd-163">фромстдерр</span><span class="sxs-lookup"><span data-stu-id="778fd-163">FromStdErr</span></span>
- <span data-ttu-id="778fd-164">секуритеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-164">SecurityError</span></span>
- <span data-ttu-id="778fd-165">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="778fd-165">ProtocolError</span></span>
- <span data-ttu-id="778fd-166">коннектионеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-166">ConnectionError</span></span>
- <span data-ttu-id="778fd-167">аусентикатионеррор</span><span class="sxs-lookup"><span data-stu-id="778fd-167">AuthenticationError</span></span>
- <span data-ttu-id="778fd-168">лимитсексцеедед</span><span class="sxs-lookup"><span data-stu-id="778fd-168">LimitsExceeded</span></span>
- <span data-ttu-id="778fd-169">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="778fd-169">QuotaExceeded</span></span>
- <span data-ttu-id="778fd-170">нотенаблед</span><span class="sxs-lookup"><span data-stu-id="778fd-170">NotEnabled</span></span>

<span data-ttu-id="778fd-171">Дополнительные сведения о категориях ошибок см. в разделе [ErrorCategory enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span><span class="sxs-lookup"><span data-stu-id="778fd-171">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-172">-Категоряктивити</span><span class="sxs-lookup"><span data-stu-id="778fd-172">-CategoryActivity</span></span>

<span data-ttu-id="778fd-173">Указывает действие, вызвавшее ошибку.</span><span class="sxs-lookup"><span data-stu-id="778fd-173">Specifies the action that caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-174">-Категориреасон</span><span class="sxs-lookup"><span data-stu-id="778fd-174">-CategoryReason</span></span>

<span data-ttu-id="778fd-175">Указывает, как или почему действие привело к ошибке.</span><span class="sxs-lookup"><span data-stu-id="778fd-175">Specifies how or why the activity caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-176">-Категоритаржетнаме</span><span class="sxs-lookup"><span data-stu-id="778fd-176">-CategoryTargetName</span></span>

<span data-ttu-id="778fd-177">Задает имя объекта, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-177">Specifies the name of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-178">-Категоритаржеттипе</span><span class="sxs-lookup"><span data-stu-id="778fd-178">-CategoryTargetType</span></span>

<span data-ttu-id="778fd-179">Задает тип объекта, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-179">Specifies the type of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-180">-Код ошибки</span><span class="sxs-lookup"><span data-stu-id="778fd-180">-ErrorId</span></span>

<span data-ttu-id="778fd-181">Задает строку идентификатора для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-181">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="778fd-182">Эта строка должны быть уникальной для конкретной ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-182">The string should be unique to the error.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-183">-Ерроррекорд</span><span class="sxs-lookup"><span data-stu-id="778fd-183">-ErrorRecord</span></span>

<span data-ttu-id="778fd-184">Задает объект записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="778fd-184">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="778fd-185">Для описания ошибки используются свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="778fd-185">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="778fd-186">Чтобы создать объект записи об ошибке, используйте `New-Object` командлет или получите объект записи об ошибке из массива в `$Error` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="778fd-186">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-187">-Exception</span><span class="sxs-lookup"><span data-stu-id="778fd-187">-Exception</span></span>

<span data-ttu-id="778fd-188">Задает объект исключения, представляющего ошибку.</span><span class="sxs-lookup"><span data-stu-id="778fd-188">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="778fd-189">Для описания ошибки используются свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="778fd-189">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="778fd-190">Чтобы создать объект исключения, используйте хэш-таблицу или `New-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="778fd-190">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-191">-Message</span><span class="sxs-lookup"><span data-stu-id="778fd-191">-Message</span></span>

<span data-ttu-id="778fd-192">Задает текст сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="778fd-192">Specifies the message text of the error.</span></span> <span data-ttu-id="778fd-193">Если текст содержит пробелы или специальные символы, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="778fd-193">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="778fd-194">Можно также передать строку сообщения в `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="778fd-194">You can also pipe a message string to `Write-Error`.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-195">-Рекоммендедактион</span><span class="sxs-lookup"><span data-stu-id="778fd-195">-RecommendedAction</span></span>

<span data-ttu-id="778fd-196">Указывает действие, которое должен предпринять пользователь для разрешения или предотвращения ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-196">Specifies the action that the user should take to resolve or prevent the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-197">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="778fd-197">-TargetObject</span></span>

<span data-ttu-id="778fd-198">Задает объект, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="778fd-198">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="778fd-199">Введите объект, переменную, содержащую объект, или команду, которая получает объект.</span><span class="sxs-lookup"><span data-stu-id="778fd-199">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="778fd-200">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="778fd-200">CommonParameters</span></span>

<span data-ttu-id="778fd-201">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="778fd-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="778fd-202">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="778fd-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="778fd-203">Входные данные</span><span class="sxs-lookup"><span data-stu-id="778fd-203">INPUTS</span></span>

### <span data-ttu-id="778fd-204">System.String</span><span class="sxs-lookup"><span data-stu-id="778fd-204">System.String</span></span>

<span data-ttu-id="778fd-205">Строку, содержащую сообщение об ошибке, можно передать в `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="778fd-205">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="778fd-206">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="778fd-206">OUTPUTS</span></span>

### <span data-ttu-id="778fd-207">Объект ошибки</span><span class="sxs-lookup"><span data-stu-id="778fd-207">Error object</span></span>

<span data-ttu-id="778fd-208">`Write-Error` выполняет запись только в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="778fd-208">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="778fd-209">Он не возвращает никакие объекты.</span><span class="sxs-lookup"><span data-stu-id="778fd-209">It does not return any objects.</span></span>

## <span data-ttu-id="778fd-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="778fd-210">NOTES</span></span>

<span data-ttu-id="778fd-211">`Write-Error` не изменяет значение `$?` автоматически изменяемой переменной, поэтому не сообщает о неустранимой ошибке.</span><span class="sxs-lookup"><span data-stu-id="778fd-211">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="778fd-212">Чтобы сообщить о завершающей ошибке, используйте метод [$PSCmdlet. writeError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) .</span><span class="sxs-lookup"><span data-stu-id="778fd-212">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="778fd-213">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="778fd-213">RELATED LINKS</span></span>

[<span data-ttu-id="778fd-214">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="778fd-214">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="778fd-215">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="778fd-215">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="778fd-216">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="778fd-216">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="778fd-217">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="778fd-217">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="778fd-218">Write-Host</span><span class="sxs-lookup"><span data-stu-id="778fd-218">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="778fd-219">Write-Output</span><span class="sxs-lookup"><span data-stu-id="778fd-219">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="778fd-220">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="778fd-220">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="778fd-221">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="778fd-221">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="778fd-222">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="778fd-222">Write-Warning</span></span>](Write-Warning.md)

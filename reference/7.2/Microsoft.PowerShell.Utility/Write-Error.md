---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: d0ee66e1002e4f1d58f63e198bcb7f03b1c8d3a8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599389"
---
# <span data-ttu-id="1818a-102">Write-Error</span><span class="sxs-lookup"><span data-stu-id="1818a-102">Write-Error</span></span>

## <span data-ttu-id="1818a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1818a-103">SYNOPSIS</span></span>
<span data-ttu-id="1818a-104">Записывает объект в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="1818a-104">Writes an object to the error stream.</span></span>

## <span data-ttu-id="1818a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1818a-105">SYNTAX</span></span>

### <span data-ttu-id="1818a-106">Except (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1818a-106">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="1818a-107">висексцептион</span><span class="sxs-lookup"><span data-stu-id="1818a-107">WithException</span></span>

```
Write-Error -Exception <Exception> [[-Message] <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="1818a-108">ерроррекорд</span><span class="sxs-lookup"><span data-stu-id="1818a-108">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="1818a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1818a-109">DESCRIPTION</span></span>

<span data-ttu-id="1818a-110">`Write-Error`Командлет объявляет неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="1818a-110">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="1818a-111">По умолчанию ошибки отправляются в основную программу для отображения вместе с выводом.</span><span class="sxs-lookup"><span data-stu-id="1818a-111">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="1818a-112">Устранимую можно записать путем отправки строки сообщения об ошибке, объекта **ErrorRecord** или объекта **Exception**.</span><span class="sxs-lookup"><span data-stu-id="1818a-112">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="1818a-113">Используйте другие параметры `Write-Error` для заполнения записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1818a-113">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="1818a-114">Устранимые ошибки записываются в поток, но не прерывают обработку команд.</span><span class="sxs-lookup"><span data-stu-id="1818a-114">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="1818a-115">Если один из элементов в коллекции элементов ввода объявляет устранимую ошибку, команда продолжает обработку других элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="1818a-115">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="1818a-116">Чтобы объявить завершающую ошибку, используйте `Throw` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1818a-116">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="1818a-117">Дополнительные сведения см. в разделе [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span><span class="sxs-lookup"><span data-stu-id="1818a-117">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="1818a-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="1818a-118">EXAMPLES</span></span>

### <span data-ttu-id="1818a-119">Пример 1. запись ошибки для объекта RegistryKey</span><span class="sxs-lookup"><span data-stu-id="1818a-119">Example 1: Write an error for RegistryKey object</span></span>

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

<span data-ttu-id="1818a-120">Эта команда объявляет неустранимую ошибку `Get-ChildItem` , когда командлет возвращает `Microsoft.Win32.RegistryKey` объект, например объекты на `HKLM:` `HKCU:` дисках или поставщика реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1818a-120">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="1818a-121">Пример 2. запись сообщения об ошибке в консоль</span><span class="sxs-lookup"><span data-stu-id="1818a-121">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="1818a-122">Эта команда объявляет устранимую ошибку и записывает ошибку «Отказано в доступе».</span><span class="sxs-lookup"><span data-stu-id="1818a-122">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="1818a-123">Для задания сообщения в команде используется параметр **Message**, однако, имя параметра **Message** опущено, поскольку указывать его не обязательно.</span><span class="sxs-lookup"><span data-stu-id="1818a-123">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="1818a-124">Пример 3. запись ошибки в консоль и указание категории</span><span class="sxs-lookup"><span data-stu-id="1818a-124">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="1818a-125">Эта команда объявляет устранимую ошибку и указывает ее категорию.</span><span class="sxs-lookup"><span data-stu-id="1818a-125">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="1818a-126">Пример 4. запись ошибки с помощью объекта исключения</span><span class="sxs-lookup"><span data-stu-id="1818a-126">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="1818a-127">Эта команда объявляет устранимую ошибку с помощью объекта **Exception**.</span><span class="sxs-lookup"><span data-stu-id="1818a-127">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="1818a-128">Первая команда создает объект **System.Exception**, используя хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="1818a-128">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="1818a-129">Объект исключения сохраняется в `$E` переменной.</span><span class="sxs-lookup"><span data-stu-id="1818a-129">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="1818a-130">Хэш-таблицу можно использовать для создания любого объекта с конструктором типа, имеющим значение null.</span><span class="sxs-lookup"><span data-stu-id="1818a-130">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="1818a-131">Вторая команда использует `Write-Error` командлет для объявления незавершающей ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-131">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="1818a-132">Значение параметра **исключения** является объектом **исключения** в `$E` переменной.</span><span class="sxs-lookup"><span data-stu-id="1818a-132">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="1818a-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1818a-133">PARAMETERS</span></span>

### <span data-ttu-id="1818a-134">-Category</span><span class="sxs-lookup"><span data-stu-id="1818a-134">-Category</span></span>

<span data-ttu-id="1818a-135">Задает категорию ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-135">Specifies the category of the error.</span></span> <span data-ttu-id="1818a-136">Значение по умолчанию — **NotSpecified**.</span><span class="sxs-lookup"><span data-stu-id="1818a-136">The default value is **NotSpecified**.</span></span> <span data-ttu-id="1818a-137">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="1818a-137">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1818a-138">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="1818a-138">NotSpecified</span></span>
- <span data-ttu-id="1818a-139">опенеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-139">OpenError</span></span>
- <span data-ttu-id="1818a-140">клосиррор</span><span class="sxs-lookup"><span data-stu-id="1818a-140">CloseError</span></span>
- <span data-ttu-id="1818a-141">девицееррор</span><span class="sxs-lookup"><span data-stu-id="1818a-141">DeviceError</span></span>
- <span data-ttu-id="1818a-142">деадлоккдетектед</span><span class="sxs-lookup"><span data-stu-id="1818a-142">DeadlockDetected</span></span>
- <span data-ttu-id="1818a-143">InvalidArgument</span><span class="sxs-lookup"><span data-stu-id="1818a-143">InvalidArgument</span></span>
- <span data-ttu-id="1818a-144">InvalidData</span><span class="sxs-lookup"><span data-stu-id="1818a-144">InvalidData</span></span>
- <span data-ttu-id="1818a-145">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="1818a-145">InvalidOperation</span></span>
- <span data-ttu-id="1818a-146">инвалидресулт</span><span class="sxs-lookup"><span data-stu-id="1818a-146">InvalidResult</span></span>
- <span data-ttu-id="1818a-147">инвалидтипе</span><span class="sxs-lookup"><span data-stu-id="1818a-147">InvalidType</span></span>
- <span data-ttu-id="1818a-148">метадатаеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-148">MetadataError</span></span>
- <span data-ttu-id="1818a-149">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="1818a-149">NotImplemented</span></span>
- <span data-ttu-id="1818a-150">нотинсталлед</span><span class="sxs-lookup"><span data-stu-id="1818a-150">NotInstalled</span></span>
- <span data-ttu-id="1818a-151">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="1818a-151">ObjectNotFound</span></span>
- <span data-ttu-id="1818a-152">оператионстоппед</span><span class="sxs-lookup"><span data-stu-id="1818a-152">OperationStopped</span></span>
- <span data-ttu-id="1818a-153">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="1818a-153">OperationTimeout</span></span>
- <span data-ttu-id="1818a-154">SyntaxError</span><span class="sxs-lookup"><span data-stu-id="1818a-154">SyntaxError</span></span>
- <span data-ttu-id="1818a-155">парсереррор</span><span class="sxs-lookup"><span data-stu-id="1818a-155">ParserError</span></span>
- <span data-ttu-id="1818a-156">пермиссиондениед</span><span class="sxs-lookup"><span data-stu-id="1818a-156">PermissionDenied</span></span>
- <span data-ttu-id="1818a-157">ресаурцебуси</span><span class="sxs-lookup"><span data-stu-id="1818a-157">ResourceBusy</span></span>
- <span data-ttu-id="1818a-158">ресаурцеексистс</span><span class="sxs-lookup"><span data-stu-id="1818a-158">ResourceExists</span></span>
- <span data-ttu-id="1818a-159">ресаурцеунаваилабле</span><span class="sxs-lookup"><span data-stu-id="1818a-159">ResourceUnavailable</span></span>
- <span data-ttu-id="1818a-160">реадеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-160">ReadError</span></span>
- <span data-ttu-id="1818a-161">WriteError</span><span class="sxs-lookup"><span data-stu-id="1818a-161">WriteError</span></span>
- <span data-ttu-id="1818a-162">фромстдерр</span><span class="sxs-lookup"><span data-stu-id="1818a-162">FromStdErr</span></span>
- <span data-ttu-id="1818a-163">секуритеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-163">SecurityError</span></span>
- <span data-ttu-id="1818a-164">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="1818a-164">ProtocolError</span></span>
- <span data-ttu-id="1818a-165">коннектионеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-165">ConnectionError</span></span>
- <span data-ttu-id="1818a-166">аусентикатионеррор</span><span class="sxs-lookup"><span data-stu-id="1818a-166">AuthenticationError</span></span>
- <span data-ttu-id="1818a-167">лимитсексцеедед</span><span class="sxs-lookup"><span data-stu-id="1818a-167">LimitsExceeded</span></span>
- <span data-ttu-id="1818a-168">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="1818a-168">QuotaExceeded</span></span>
- <span data-ttu-id="1818a-169">нотенаблед</span><span class="sxs-lookup"><span data-stu-id="1818a-169">NotEnabled</span></span>

<span data-ttu-id="1818a-170">Дополнительные сведения о категориях ошибок см. в разделе [ErrorCategory enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span><span class="sxs-lookup"><span data-stu-id="1818a-170">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

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

### <span data-ttu-id="1818a-171">-Категоряктивити</span><span class="sxs-lookup"><span data-stu-id="1818a-171">-CategoryActivity</span></span>

<span data-ttu-id="1818a-172">Указывает действие, вызвавшее ошибку.</span><span class="sxs-lookup"><span data-stu-id="1818a-172">Specifies the action that caused the error.</span></span>

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

### <span data-ttu-id="1818a-173">-Категориреасон</span><span class="sxs-lookup"><span data-stu-id="1818a-173">-CategoryReason</span></span>

<span data-ttu-id="1818a-174">Указывает, как или почему действие привело к ошибке.</span><span class="sxs-lookup"><span data-stu-id="1818a-174">Specifies how or why the activity caused the error.</span></span>

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

### <span data-ttu-id="1818a-175">-Категоритаржетнаме</span><span class="sxs-lookup"><span data-stu-id="1818a-175">-CategoryTargetName</span></span>

<span data-ttu-id="1818a-176">Задает имя объекта, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-176">Specifies the name of the object that was being processed when the error occurred.</span></span>

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

### <span data-ttu-id="1818a-177">-Категоритаржеттипе</span><span class="sxs-lookup"><span data-stu-id="1818a-177">-CategoryTargetType</span></span>

<span data-ttu-id="1818a-178">Задает тип объекта, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-178">Specifies the type of the object that was being processed when the error occurred.</span></span>

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

### <span data-ttu-id="1818a-179">-Код ошибки</span><span class="sxs-lookup"><span data-stu-id="1818a-179">-ErrorId</span></span>

<span data-ttu-id="1818a-180">Задает строку идентификатора для идентификации ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-180">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="1818a-181">Эта строка должны быть уникальной для конкретной ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-181">The string should be unique to the error.</span></span>

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

### <span data-ttu-id="1818a-182">-Ерроррекорд</span><span class="sxs-lookup"><span data-stu-id="1818a-182">-ErrorRecord</span></span>

<span data-ttu-id="1818a-183">Задает объект записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1818a-183">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="1818a-184">Для описания ошибки используются свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="1818a-184">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="1818a-185">Чтобы создать объект записи об ошибке, используйте `New-Object` командлет или получите объект записи об ошибке из массива в `$Error` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="1818a-185">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

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

### <span data-ttu-id="1818a-186">-Exception</span><span class="sxs-lookup"><span data-stu-id="1818a-186">-Exception</span></span>

<span data-ttu-id="1818a-187">Задает объект исключения, представляющего ошибку.</span><span class="sxs-lookup"><span data-stu-id="1818a-187">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="1818a-188">Для описания ошибки используются свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="1818a-188">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="1818a-189">Чтобы создать объект исключения, используйте хэш-таблицу или `New-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="1818a-189">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

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

### <span data-ttu-id="1818a-190">-Message</span><span class="sxs-lookup"><span data-stu-id="1818a-190">-Message</span></span>

<span data-ttu-id="1818a-191">Задает текст сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1818a-191">Specifies the message text of the error.</span></span> <span data-ttu-id="1818a-192">Если текст содержит пробелы или специальные символы, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="1818a-192">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="1818a-193">Можно также передать строку сообщения в `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="1818a-193">You can also pipe a message string to `Write-Error`.</span></span>

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

### <span data-ttu-id="1818a-194">-Рекоммендедактион</span><span class="sxs-lookup"><span data-stu-id="1818a-194">-RecommendedAction</span></span>

<span data-ttu-id="1818a-195">Указывает действие, которое должен предпринять пользователь для разрешения или предотвращения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-195">Specifies the action that the user should take to resolve or prevent the error.</span></span>

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

### <span data-ttu-id="1818a-196">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="1818a-196">-TargetObject</span></span>

<span data-ttu-id="1818a-197">Задает объект, который обрабатывался во время возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1818a-197">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="1818a-198">Введите объект, переменную, содержащую объект, или команду, которая получает объект.</span><span class="sxs-lookup"><span data-stu-id="1818a-198">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

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

### <span data-ttu-id="1818a-199">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1818a-199">CommonParameters</span></span>

<span data-ttu-id="1818a-200">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1818a-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1818a-201">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1818a-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1818a-202">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1818a-202">INPUTS</span></span>

### <span data-ttu-id="1818a-203">System.String</span><span class="sxs-lookup"><span data-stu-id="1818a-203">System.String</span></span>

<span data-ttu-id="1818a-204">Строку, содержащую сообщение об ошибке, можно передать в `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="1818a-204">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="1818a-205">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1818a-205">OUTPUTS</span></span>

### <span data-ttu-id="1818a-206">Объект ошибки</span><span class="sxs-lookup"><span data-stu-id="1818a-206">Error object</span></span>

<span data-ttu-id="1818a-207">`Write-Error` выполняет запись только в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="1818a-207">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="1818a-208">Он не возвращает никакие объекты.</span><span class="sxs-lookup"><span data-stu-id="1818a-208">It does not return any objects.</span></span>

## <span data-ttu-id="1818a-209">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1818a-209">NOTES</span></span>

<span data-ttu-id="1818a-210">`Write-Error` не изменяет значение `$?` автоматически изменяемой переменной, поэтому не сообщает о неустранимой ошибке.</span><span class="sxs-lookup"><span data-stu-id="1818a-210">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="1818a-211">Чтобы сообщить о завершающей ошибке, используйте метод [$PSCmdlet. writeError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) .</span><span class="sxs-lookup"><span data-stu-id="1818a-211">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="1818a-212">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1818a-212">RELATED LINKS</span></span>

[<span data-ttu-id="1818a-213">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1818a-213">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="1818a-214">О потоках вывода</span><span class="sxs-lookup"><span data-stu-id="1818a-214">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="1818a-215">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="1818a-215">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="1818a-216">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="1818a-216">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="1818a-217">Write-Host</span><span class="sxs-lookup"><span data-stu-id="1818a-217">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="1818a-218">Write-Output</span><span class="sxs-lookup"><span data-stu-id="1818a-218">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="1818a-219">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="1818a-219">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="1818a-220">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="1818a-220">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="1818a-221">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="1818a-221">Write-Warning</span></span>](Write-Warning.md)

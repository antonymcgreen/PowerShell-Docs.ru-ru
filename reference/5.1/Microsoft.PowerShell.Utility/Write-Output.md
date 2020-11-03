---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: ccc72ac961adbcba542a7b8be55ad49df68a5ef6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232813"
---
# <span data-ttu-id="36559-103">Write-Output</span><span class="sxs-lookup"><span data-stu-id="36559-103">Write-Output</span></span>

## <span data-ttu-id="36559-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="36559-104">SYNOPSIS</span></span>
<span data-ttu-id="36559-105">Отправляет указанные объекты в следующую команду по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="36559-105">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="36559-106">Если команда является последней в конвейере, объекты отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="36559-106">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="36559-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36559-107">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="36559-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36559-108">DESCRIPTION</span></span>

<span data-ttu-id="36559-109">`Write-Output`Командлет отправляет указанный объект по конвейеру в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="36559-109">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="36559-110">Если команда является последней в конвейере, объект отображается в консоли.</span><span class="sxs-lookup"><span data-stu-id="36559-110">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="36559-111">`Write-Output` отправляет объекты в основной конвейер, также известный как "поток вывода" или "конвейер успешного выполнения".</span><span class="sxs-lookup"><span data-stu-id="36559-111">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="36559-112">Чтобы отправить объекты ошибок в конвейер ошибок, используйте командлет Write-Error.</span><span class="sxs-lookup"><span data-stu-id="36559-112">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="36559-113">Этот командлет обычно используется в сценариях для отображения строк и других объектов в консоли.</span><span class="sxs-lookup"><span data-stu-id="36559-113">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="36559-114">Один из встроенных псевдонимов для `Write-Output` — `echo` и аналогичен другим оболочкам, использующим `echo` , поведением по умолчанию является Отображение выходных данных в конце конвейера.</span><span class="sxs-lookup"><span data-stu-id="36559-114">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="36559-115">В PowerShell, как правило, нет необходимости использовать командлет в экземплярах, где выходные данные отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36559-115">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="36559-116">Например, выражение `Get-Process | Write-Output` будет эквивалентно `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="36559-116">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="36559-117">Или, `echo "Home directory: $HOME"` может быть записано, `"Home directory: $HOME"` .</span><span class="sxs-lookup"><span data-stu-id="36559-117">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="36559-118">По умолчанию `Write-Output` перечисляет по коллекциям, предоставленным командлету.</span><span class="sxs-lookup"><span data-stu-id="36559-118">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="36559-119">Однако `Write-Output` также можно использовать для передачи коллекций вниз по конвейеру в виде одного объекта с параметром **GetEnumerator** .</span><span class="sxs-lookup"><span data-stu-id="36559-119">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="36559-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="36559-120">EXAMPLES</span></span>

### <span data-ttu-id="36559-121">Пример 1. Получение объектов и запись их на консоль</span><span class="sxs-lookup"><span data-stu-id="36559-121">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="36559-122">Первая команда получает процессы, запущенные на компьютере, и сохраняет их в `$P` переменной.</span><span class="sxs-lookup"><span data-stu-id="36559-122">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="36559-123">Вторая и третья команды отображают объекты процесса в `$P` консоли.</span><span class="sxs-lookup"><span data-stu-id="36559-123">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="36559-124">Пример 2. Передача выходных данных другому командлету</span><span class="sxs-lookup"><span data-stu-id="36559-124">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="36559-125">Эта команда передает строку "тестовый вывод" в `Get-Member` командлет, который отображает члены класса **System. String** , предказывая, что строка передается в конвейере.</span><span class="sxs-lookup"><span data-stu-id="36559-125">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="36559-126">Пример 3. Отключение перечисления в выходных данных</span><span class="sxs-lookup"><span data-stu-id="36559-126">Example 3: Suppress enumeration in output</span></span>

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

<span data-ttu-id="36559-127">Эта команда добавляет параметр **GetEnumerator** , чтобы обрабатывать коллекцию или массив как один объект через конвейер.</span><span class="sxs-lookup"><span data-stu-id="36559-127">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="36559-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36559-128">PARAMETERS</span></span>

### <span data-ttu-id="36559-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="36559-129">-InputObject</span></span>

<span data-ttu-id="36559-130">Задает объекты для отправки в конвейер.</span><span class="sxs-lookup"><span data-stu-id="36559-130">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="36559-131">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="36559-131">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36559-132">-Не перечислять</span><span class="sxs-lookup"><span data-stu-id="36559-132">-NoEnumerate</span></span>

<span data-ttu-id="36559-133">По умолчанию `Write-Output` командлет всегда перечисляет выходные данные.</span><span class="sxs-lookup"><span data-stu-id="36559-133">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="36559-134">Параметр **GetEnumerator** подавляет поведение по умолчанию и предотвращает `Write-Output` перечисление выходных данных.</span><span class="sxs-lookup"><span data-stu-id="36559-134">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="36559-135">Параметр **GetEnumerator** не действует, если команда заключена в круглые скобки, так как скобки принудительно перечисление.</span><span class="sxs-lookup"><span data-stu-id="36559-135">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="36559-136">Например, `(Write-Output 1,2,3)` все равно перечисляет массив.</span><span class="sxs-lookup"><span data-stu-id="36559-136">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36559-137">Проблема с этим параметром в Windows PowerShell исправлена в PowerShell 6,2 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="36559-137">There is an issue with this switch in Windows PowerShell that is fixed in PowerShell 6.2 and above.</span></span> <span data-ttu-id="36559-138">При использовании аргумента **GetEnumerator** и явном использовании параметра **InputObject** команда все равно перечислена.</span><span class="sxs-lookup"><span data-stu-id="36559-138">When using **NoEnumerate** and explicitly using the **InputObject** parameter, the command still enumerates.</span></span> <span data-ttu-id="36559-139">Чтобы обойти это, передайте аргументы **InputObject** в расположение.</span><span class="sxs-lookup"><span data-stu-id="36559-139">To work around this, pass the **InputObject** argument(s) positionally.</span></span>

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

### <span data-ttu-id="36559-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="36559-140">CommonParameters</span></span>

<span data-ttu-id="36559-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36559-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36559-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36559-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36559-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="36559-143">INPUTS</span></span>

### <span data-ttu-id="36559-144">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="36559-144">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="36559-145">Вы можете передать объекты в `Write-Output` .</span><span class="sxs-lookup"><span data-stu-id="36559-145">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="36559-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="36559-146">OUTPUTS</span></span>

### <span data-ttu-id="36559-147">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="36559-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="36559-148">`Write-Output` Возвращает объекты, которые передаются в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="36559-148">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="36559-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="36559-149">NOTES</span></span>

## <span data-ttu-id="36559-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="36559-150">RELATED LINKS</span></span>

[<span data-ttu-id="36559-151">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="36559-151">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="36559-152">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="36559-152">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="36559-153">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="36559-153">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="36559-154">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="36559-154">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="36559-155">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="36559-155">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="36559-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="36559-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="36559-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="36559-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="36559-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="36559-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="36559-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="36559-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="36559-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="36559-160">Write-Warning</span></span>](Write-Warning.md)

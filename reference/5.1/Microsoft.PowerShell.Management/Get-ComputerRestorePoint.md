---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228405"
---
# <span data-ttu-id="c84f3-103">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="c84f3-103">Get-ComputerRestorePoint</span></span>

## <span data-ttu-id="c84f3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c84f3-104">SYNOPSIS</span></span>
<span data-ttu-id="c84f3-105">Получает точки восстановления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c84f3-105">Gets the restore points on the local computer.</span></span>

## <span data-ttu-id="c84f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c84f3-106">SYNTAX</span></span>

### <span data-ttu-id="c84f3-107">Идентификатор (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c84f3-107">ID (Default)</span></span>

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="c84f3-108">LastStatus</span><span class="sxs-lookup"><span data-stu-id="c84f3-108">LastStatus</span></span>

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## <span data-ttu-id="c84f3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c84f3-109">DESCRIPTION</span></span>

<span data-ttu-id="c84f3-110">`Get-ComputerRestorePoint`Командлет получает точки восстановления системы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c84f3-110">The `Get-ComputerRestorePoint` cmdlet gets the local computer's system restore points.</span></span> <span data-ttu-id="c84f3-111">Кроме того, он может отобразить состояние последней попытки восстановления компьютера.</span><span class="sxs-lookup"><span data-stu-id="c84f3-111">And, it can display the status of the most recent attempt to restore the computer.</span></span>

<span data-ttu-id="c84f3-112">`Get-ComputerRestorePoint`Для выбора точки восстановления можно использовать сведения из.</span><span class="sxs-lookup"><span data-stu-id="c84f3-112">You can use the information from `Get-ComputerRestorePoint` to select a restore point.</span></span> <span data-ttu-id="c84f3-113">Например, используйте порядковый номер для указания точки восстановления для `Restore-Computer` командлета.</span><span class="sxs-lookup"><span data-stu-id="c84f3-113">For example, use a sequence number to identify a restore point for the `Restore-Computer` cmdlet.</span></span>

<span data-ttu-id="c84f3-114">Точки восстановления системы и `Get-ComputerRestorePoint` командлеты поддерживаются только в клиентских операционных системах, таких как Windows 10, Windows 7, Windows Vista и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="c84f3-114">System restore points and the `Get-ComputerRestorePoint` cmdlet are supported only on client operating systems such as Windows 10, Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="c84f3-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="c84f3-115">EXAMPLES</span></span>

### <span data-ttu-id="c84f3-116">Пример 1. получение всех точек восстановления системы</span><span class="sxs-lookup"><span data-stu-id="c84f3-116">Example 1: Get all system restore points</span></span>

<span data-ttu-id="c84f3-117">В этом примере `Get-ComputerRestorePoint` получает все точки восстановления системы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c84f3-117">In this example, `Get-ComputerRestorePoint` gets all the local computer's system restore points.</span></span>

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### <span data-ttu-id="c84f3-118">Пример 2. получение конкретных порядковых номеров</span><span class="sxs-lookup"><span data-stu-id="c84f3-118">Example 2: Get specific sequence numbers</span></span>

<span data-ttu-id="c84f3-119">Этот пример получает точки восстановления системы для конкретных порядковых номеров.</span><span class="sxs-lookup"><span data-stu-id="c84f3-119">This example gets system restore points for specific sequence numbers.</span></span>

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

<span data-ttu-id="c84f3-120">`Get-ComputerRestorePoint` использует параметр **ресторепоинт** , чтобы указать разделенный запятыми массив порядковых номеров.</span><span class="sxs-lookup"><span data-stu-id="c84f3-120">`Get-ComputerRestorePoint` uses the **RestorePoint** parameter to specify a comma-separated array of sequence numbers.</span></span>

### <span data-ttu-id="c84f3-121">Пример 3. Отображение состояния восстановления системы</span><span class="sxs-lookup"><span data-stu-id="c84f3-121">Example 3: Display the status of a system restore</span></span>

<span data-ttu-id="c84f3-122">В этом примере отображается состояние последнего восстановления системы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c84f3-122">This example displays the status of the most recent system restore on the local computer.</span></span>

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

<span data-ttu-id="c84f3-123">`Get-ComputerRestorePoint` использует параметр **LastStatus** для вывода результатов последнего восстановления системы.</span><span class="sxs-lookup"><span data-stu-id="c84f3-123">`Get-ComputerRestorePoint` uses the **LastStatus** parameter to display the result of the most recent system restore.</span></span>

### <span data-ttu-id="c84f3-124">Пример 4. Использование выражения для преобразования CreationTime</span><span class="sxs-lookup"><span data-stu-id="c84f3-124">Example 4: Use an expression to convert the CreationTime</span></span>

<span data-ttu-id="c84f3-125">`Get-ComputerRestorePoint` выводит **CreationTime** в виде строки даты и времени инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="c84f3-125">`Get-ComputerRestorePoint` outputs the **CreationTime** as a Windows Management Instrumentation (WMI) date and time string.</span></span>

<span data-ttu-id="c84f3-126">В этом примере переменная хранит выражение, преобразующее строку **CreationTime** в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-126">In this example, a variable stores an expression that converts the **CreationTime** string to a **DateTime** object.</span></span> <span data-ttu-id="c84f3-127">Чтобы просмотреть строки **CreationTime** перед их преобразованием, используйте команду `((Get-ComputerRestorePoint).CreationTime)` .</span><span class="sxs-lookup"><span data-stu-id="c84f3-127">To view **CreationTime** strings before they're converted, use a command such as `((Get-ComputerRestorePoint).CreationTime)`.</span></span> <span data-ttu-id="c84f3-128">Дополнительные сведения о строке даты и времени WMI см. в разделе [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span><span class="sxs-lookup"><span data-stu-id="c84f3-128">For more information about the WMI date and time string, see [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span></span>

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

<span data-ttu-id="c84f3-129">`$date`Переменная хранит хэш-таблицу с выражением, использующим метод **ConvertToDateTime** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-129">The `$date` variable stores a hash table with the expression that uses the **ConvertToDateTime** method.</span></span> <span data-ttu-id="c84f3-130">Выражение преобразует значение свойства **CreationTime** из строки WMI в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-130">The expression converts the **CreationTime** property's value from a WMI string to a **DateTime** object.</span></span>

<span data-ttu-id="c84f3-131">`Get-ComputerRestorePoint` отправляет объекты точки восстановления системы по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c84f3-131">`Get-ComputerRestorePoint` sends the system restore point objects down the pipeline.</span></span> <span data-ttu-id="c84f3-132">`Select-Object` использует параметр **Property** для указания отображаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="c84f3-132">`Select-Object` uses the **Property** parameter to specify the properties to display.</span></span> <span data-ttu-id="c84f3-133">Для каждого объекта в конвейере выражение в `$date` преобразует **CreationTime** и выводит результат в свойстве **Date** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-133">For each object in the pipeline, the expression in `$date` converts the **CreationTime** and outputs the result in the **Date** property.</span></span>

### <span data-ttu-id="c84f3-134">Пример 5. использование свойства для получения порядкового номера</span><span class="sxs-lookup"><span data-stu-id="c84f3-134">Example 5: Use a property to get a sequence number</span></span>

<span data-ttu-id="c84f3-135">Этот пример получает порядковый номер с помощью свойства **SequenceNumber** и индекса массива.</span><span class="sxs-lookup"><span data-stu-id="c84f3-135">This example gets a sequence number by using the **SequenceNumber** property and an array index.</span></span> <span data-ttu-id="c84f3-136">Выходные данные содержат только порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="c84f3-136">The output only contains the sequence number.</span></span>

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

<span data-ttu-id="c84f3-137">`Get-ComputerRestorePoint` использует свойство **SequenceNumber** с индексом массива.</span><span class="sxs-lookup"><span data-stu-id="c84f3-137">`Get-ComputerRestorePoint` uses the **SequenceNumber** property with an array index.</span></span> <span data-ttu-id="c84f3-138">Индекс массива `-1` возвращает последний порядковый номер в массиве.</span><span class="sxs-lookup"><span data-stu-id="c84f3-138">The array index of `-1` gets the most recent sequence number in the array.</span></span>

## <span data-ttu-id="c84f3-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c84f3-139">PARAMETERS</span></span>

### <span data-ttu-id="c84f3-140">-LastStatus</span><span class="sxs-lookup"><span data-stu-id="c84f3-140">-LastStatus</span></span>

<span data-ttu-id="c84f3-141">Указывает, что `Get-ComputerRestorePoint` получает состояние последней операции восстановления системы.</span><span class="sxs-lookup"><span data-stu-id="c84f3-141">Indicates that `Get-ComputerRestorePoint` gets the status of the most recent system restore operation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c84f3-142">-Ресторепоинт</span><span class="sxs-lookup"><span data-stu-id="c84f3-142">-RestorePoint</span></span>

<span data-ttu-id="c84f3-143">Указывает порядковые номера точек восстановления системы.</span><span class="sxs-lookup"><span data-stu-id="c84f3-143">Specifies the sequence numbers of the system restore points.</span></span> <span data-ttu-id="c84f3-144">Можно указать либо один порядковый номер, либо разделенный запятыми массив порядковых номеров.</span><span class="sxs-lookup"><span data-stu-id="c84f3-144">You can specify either a single sequence number or a comma-separated array of sequence numbers.</span></span>

<span data-ttu-id="c84f3-145">Если параметр **ресторепоинт** не указан, `Get-ComputerRestorePoint` возвращает все точки восстановления системы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c84f3-145">If the **RestorePoint** parameter isn't specified, `Get-ComputerRestorePoint` returns all the local computer's system restore points.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c84f3-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c84f3-146">CommonParameters</span></span>

<span data-ttu-id="c84f3-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c84f3-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c84f3-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c84f3-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c84f3-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c84f3-149">INPUTS</span></span>

### <span data-ttu-id="c84f3-150">Нет</span><span class="sxs-lookup"><span data-stu-id="c84f3-150">None</span></span>

<span data-ttu-id="c84f3-151">Вы не можете отправить объекты по конвейеру в `Get-ComputerRestorePoint` .</span><span class="sxs-lookup"><span data-stu-id="c84f3-151">You can't send objects down the pipeline to `Get-ComputerRestorePoint`.</span></span>

## <span data-ttu-id="c84f3-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c84f3-152">OUTPUTS</span></span>

### <span data-ttu-id="c84f3-153">System. Management. ManagementObject # Рут\дефаулт\системресторе или строка</span><span class="sxs-lookup"><span data-stu-id="c84f3-153">System.Management.ManagementObject#root\default\SystemRestore or String</span></span>

<span data-ttu-id="c84f3-154">`Get-ComputerRestorePoint` Возвращает объект **SystemRestore** , являющийся экземпляром класса инструментарий управления Windows (WMI) (WMI) **SystemRestore** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-154">`Get-ComputerRestorePoint` returns a **SystemRestore** object, which is an instance of the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

<span data-ttu-id="c84f3-155">При использовании параметра **LastStatus** `Get-ComputerRestorePoint` возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="c84f3-155">When you use the **LastStatus** parameter, `Get-ComputerRestorePoint` returns a string.</span></span>

## <span data-ttu-id="c84f3-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c84f3-156">NOTES</span></span>

<span data-ttu-id="c84f3-157">Чтобы выполнить `Get-ComputerRestorePoint` команду в Windows Vista и более поздних версиях Windows, откройте PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="c84f3-157">To run a `Get-ComputerRestorePoint` command on Windows Vista and later versions of Windows, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="c84f3-158">`Get-ComputerRestorePoint` использует класс **SYSTEMRESTORE** инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="c84f3-158">`Get-ComputerRestorePoint` uses the WMI **SystemRestore** class.</span></span>

## <span data-ttu-id="c84f3-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c84f3-159">RELATED LINKS</span></span>

[<span data-ttu-id="c84f3-160">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c84f3-160">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="c84f3-161">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="c84f3-161">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="c84f3-162">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="c84f3-162">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="c84f3-163">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="c84f3-163">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="c84f3-164">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="c84f3-164">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="c84f3-165">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="c84f3-165">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="c84f3-166">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="c84f3-166">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="c84f3-167">SystemRestore</span><span class="sxs-lookup"><span data-stu-id="c84f3-167">SystemRestore</span></span>](/windows/win32/sr/systemrestore)

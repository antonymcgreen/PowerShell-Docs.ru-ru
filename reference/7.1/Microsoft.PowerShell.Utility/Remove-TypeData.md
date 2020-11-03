---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 926239c0bbdb17f53b7d869c0bb08c8ab125f1a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228033"
---
# <span data-ttu-id="6036b-103">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="6036b-103">Remove-TypeData</span></span>

## <span data-ttu-id="6036b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6036b-104">Synopsis</span></span>
<span data-ttu-id="6036b-105">Удаляет расширенные типы из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-105">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="6036b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6036b-106">Syntax</span></span>

### <span data-ttu-id="6036b-107">Ремоветипедатасет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6036b-107">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6036b-108">ремоветипесет</span><span class="sxs-lookup"><span data-stu-id="6036b-108">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6036b-109">ремовефилесет</span><span class="sxs-lookup"><span data-stu-id="6036b-109">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6036b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6036b-110">DESCRIPTION</span></span>

<span data-ttu-id="6036b-111">`Remove-TypeData`Командлет удаляет данные расширенного типа из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-111">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="6036b-112">Действие этого командлета распространяется только на текущий сеанс и на сеансы, созданные в его рамках.</span><span class="sxs-lookup"><span data-stu-id="6036b-112">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="6036b-113">Вы можете добавить свойства и методы в объекты в PowerShell, определив их в `Update-TypeData` командах и `Types.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="6036b-113">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="6036b-114">`Remove-TypeData` удаляет эти расширенные свойства и методы из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-114">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="6036b-115">`Remove-TypeData` не удаляет `Types.ps1xml` файлы и не удаляет какие либо расширенные определения типов из `Types.ps1xml` файлов.</span><span class="sxs-lookup"><span data-stu-id="6036b-115">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="6036b-116">Дополнительные сведения о `Types.ps1xml` файлах см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="6036b-116">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="6036b-117">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6036b-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="6036b-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="6036b-118">Examples</span></span>

### <span data-ttu-id="6036b-119">Пример 1. Удаление данных типа для указанного типа</span><span class="sxs-lookup"><span data-stu-id="6036b-119">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="6036b-120">В этом примере удаляются все **данные типа из** сеанса, включая данные типа, добавленные `Types.ps1xml` в файл, и данные динамического типа, которые были добавлены в сеанс с помощью `Update-TypeData` командлета.</span><span class="sxs-lookup"><span data-stu-id="6036b-120">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="6036b-121">Пример 2. Удаление расширенного типа данных из сеанса</span><span class="sxs-lookup"><span data-stu-id="6036b-121">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="6036b-122">В этом примере показан результат удаления расширенных данных типа из сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-122">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="6036b-123">Первый `Get-TypeData` получает данные расширенного типа для типа **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6036b-123">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="6036b-124">Выходные данные показывают, что для всех объектов **System. DateTime** в PowerShell было добавлено свойство **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6036b-124">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="6036b-125">`Get-Date`Командлет возвращает объект **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6036b-125">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="6036b-126">Команда использует точечную нотацию для получения значения свойства **DateTime** объекта **System. DateTime** , `Get-Date` возвращающего значение.</span><span class="sxs-lookup"><span data-stu-id="6036b-126">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

<span data-ttu-id="6036b-127">Следующий `Get-TypeData` командлет для получения всех данных расширенного типа для типа **System. DateTime** и каналов, которые должны быть `Remove-TypeData` удалены в командлете для удаления данных расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="6036b-127">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="6036b-128">Последний `Get-Date` командлет показывает результат удаления расширенных данных типа для типа **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6036b-128">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="6036b-129">Так как свойство **System. DateTime** больше не существует, команда для получения его значения возвращает значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="6036b-129">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="6036b-130">Пример 3. Удаление расширенных типов для модулей</span><span class="sxs-lookup"><span data-stu-id="6036b-130">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="6036b-131">В этом примере удаляются все данные расширенного типа для объектов модуля.</span><span class="sxs-lookup"><span data-stu-id="6036b-131">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="6036b-132">При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для всех объектов этого типа.</span><span class="sxs-lookup"><span data-stu-id="6036b-132">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="6036b-133">Пример 4. Удаление расширенных типов из указанных модулей</span><span class="sxs-lookup"><span data-stu-id="6036b-133">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="6036b-134">В этом примере используется параметр **path** `Remove-TypeData` командлета для удаления расширенных типов, определенных в `Types.ps1xml` файлах, добавленных модулями **PSScheduledJob** и **PSWorkflow** .</span><span class="sxs-lookup"><span data-stu-id="6036b-134">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="6036b-135">Эта команда не влияет на данные динамического типа, добавленные с помощью `Update-TypeData` командлета.</span><span class="sxs-lookup"><span data-stu-id="6036b-135">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="6036b-136">Эта команда завершается успешно, только если модули импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="6036b-136">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="6036b-137">Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="6036b-137">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="6036b-138">Пример 5. Удаление расширенных типов из удаленного сеанса</span><span class="sxs-lookup"><span data-stu-id="6036b-138">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="6036b-139">Этот пример удаляет расширенные типы из удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-139">This example removes extended types from a remote session.</span></span> <span data-ttu-id="6036b-140">Команда использует `Invoke-Command` командлет для удаления данных расширенного типа для всех типов CIM в сеансах в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="6036b-140">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="6036b-141">Параметры</span><span class="sxs-lookup"><span data-stu-id="6036b-141">Parameters</span></span>

### <span data-ttu-id="6036b-142">-Path</span><span class="sxs-lookup"><span data-stu-id="6036b-142">-Path</span></span>

<span data-ttu-id="6036b-143">Указывает массив файлов, которые этот командлет удаляет из данных расширенного типа сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-143">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="6036b-144">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="6036b-144">This parameter is required.</span></span>

<span data-ttu-id="6036b-145">Введите пути и имена файлов одного или нескольких `Types.ps1xml` файлов.</span><span class="sxs-lookup"><span data-stu-id="6036b-145">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="6036b-146">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6036b-146">Wildcards are not supported.</span></span> <span data-ttu-id="6036b-147">Если путь не указан, расположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="6036b-147">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6036b-148">-TypeData</span><span class="sxs-lookup"><span data-stu-id="6036b-148">-TypeData</span></span>

<span data-ttu-id="6036b-149">Указывает данные типа, которые этот командлет удаляет из сеанса.</span><span class="sxs-lookup"><span data-stu-id="6036b-149">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="6036b-150">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="6036b-150">This parameter is required.</span></span> <span data-ttu-id="6036b-151">Введите переменную, содержащую объекты **TypeData** ( **System. Management. Automation. пространства выполнения. TypeData** ) или команду, которая получает объекты **TypeData** , такие как `Get-TypeData` команда.</span><span class="sxs-lookup"><span data-stu-id="6036b-151">Enter a variable that contains **TypeData** objects ( **System.Management.Automation.Runspaces.TypeData** ) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="6036b-152">Вы также можете передать объекты **TypeData** в `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="6036b-152">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6036b-153">-TypeName</span><span class="sxs-lookup"><span data-stu-id="6036b-153">-TypeName</span></span>

<span data-ttu-id="6036b-154">Указывает типы, для которых этот командлет удаляет все данные расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="6036b-154">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="6036b-155">Для типов в пространстве имен System вводятся краткие имена.</span><span class="sxs-lookup"><span data-stu-id="6036b-155">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="6036b-156">В остальных случаях требуется полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="6036b-156">Otherwise, the full type name is required.</span></span> <span data-ttu-id="6036b-157">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6036b-157">Wildcards are not supported.</span></span>

<span data-ttu-id="6036b-158">Можно передать имена типов в `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="6036b-158">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="6036b-159">При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="6036b-159">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6036b-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6036b-160">-Confirm</span></span>

<span data-ttu-id="6036b-161">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6036b-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6036b-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6036b-162">-WhatIf</span></span>

<span data-ttu-id="6036b-163">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6036b-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6036b-164">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6036b-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6036b-165">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6036b-165">CommonParameters</span></span>

<span data-ttu-id="6036b-166">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6036b-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6036b-167">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6036b-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6036b-168">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6036b-168">Inputs</span></span>

### <span data-ttu-id="6036b-169">System. Management. Automation. пространства выполнения. TypeData</span><span class="sxs-lookup"><span data-stu-id="6036b-169">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="6036b-170">Объект **TypeData** , например, `Get-TypeData` возвращаемый командлетом, можно передать в `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="6036b-170">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="6036b-171">System.String</span><span class="sxs-lookup"><span data-stu-id="6036b-171">System.String</span></span>

<span data-ttu-id="6036b-172">Имена типов можно передать в `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="6036b-172">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="6036b-173">При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="6036b-173">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="6036b-174">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6036b-174">Outputs</span></span>

### <span data-ttu-id="6036b-175">Нет</span><span class="sxs-lookup"><span data-stu-id="6036b-175">None</span></span>

<span data-ttu-id="6036b-176">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6036b-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6036b-177">Примечания</span><span class="sxs-lookup"><span data-stu-id="6036b-177">Notes</span></span>

<span data-ttu-id="6036b-178">`Remove-TypeData` может удалять только данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6036b-178">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="6036b-179">Он не может удалять данные расширенных типов, которые находятся на компьютере, но не добавлены в текущий сеанс, например расширенные типы, определенные в модулях, которые не импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="6036b-179">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="6036b-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6036b-180">Related links</span></span>

[<span data-ttu-id="6036b-181">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="6036b-181">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="6036b-182">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="6036b-182">Update-TypeData</span></span>](Update-TypeData.md)


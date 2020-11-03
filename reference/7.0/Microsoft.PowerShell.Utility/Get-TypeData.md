---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 83e520f5d48aed89bdd1a461958331185eb46b9a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225934"
---
# <span data-ttu-id="22ec1-103">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="22ec1-103">Get-TypeData</span></span>

## <span data-ttu-id="22ec1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="22ec1-104">Synopsis</span></span>
<span data-ttu-id="22ec1-105">Получает данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-105">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="22ec1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22ec1-106">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="22ec1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="22ec1-107">Description</span></span>

<span data-ttu-id="22ec1-108">`Get-TypeData`Командлет получает данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-108">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="22ec1-109">Сюда относятся данные типа, которые были добавлены в сеанс по `Types.ps1xml` файлам и динамическим типам данных, добавленным с помощью параметра `Update-TypeData` командлета.</span><span class="sxs-lookup"><span data-stu-id="22ec1-109">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="22ec1-110">Можно использовать данные расширенного типа, которые `Get-TypeData` возвращают, чтобы проверить данные типа в сеансе и отправить их `Update-TypeData` `Remove-TypeData` командлетам и.</span><span class="sxs-lookup"><span data-stu-id="22ec1-110">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="22ec1-111">Расширенные данные типа добавляют свойства и методы в объекты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ec1-111">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="22ec1-112">Вы можете использовать добавленные свойства и методы таким же образом, как свойства и методы, определенные в типе объекта.</span><span class="sxs-lookup"><span data-stu-id="22ec1-112">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="22ec1-113">Однако при написании сценариев имейте в виду, что добавленные свойства и методы могут отсутствовать в каждом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ec1-113">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="22ec1-114">Дополнительные сведения о `Types.ps1xml` файлах см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="22ec1-114">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="22ec1-115">Дополнительные сведения о динамических данных типа, `Update-TypeData` добавляемых командлетом, см `Update-TypeData` . в разделе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-115">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="22ec1-116">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="22ec1-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="22ec1-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="22ec1-117">Examples</span></span>

### <span data-ttu-id="22ec1-118">Пример 1. получение всех данных расширенного типа</span><span class="sxs-lookup"><span data-stu-id="22ec1-118">Example 1: Get all extended type data</span></span>

<span data-ttu-id="22ec1-119">Этот пример получает все данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-119">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="22ec1-120">Пример 2. получение типов по имени</span><span class="sxs-lookup"><span data-stu-id="22ec1-120">Example 2: Get types by name</span></span>

<span data-ttu-id="22ec1-121">Этот пример возвращает все типы в текущем сеансе, имена которых содержат события.</span><span class="sxs-lookup"><span data-stu-id="22ec1-121">This example gets all types in the current session that have names that contain Eventing.</span></span>

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### <span data-ttu-id="22ec1-122">Пример 3. получение блока скрипта, который создает значение свойства</span><span class="sxs-lookup"><span data-stu-id="22ec1-122">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="22ec1-123">В этом примере получается блок скрипта, который создает значение свойства **EventID** объектов **EventLogEntry** .</span><span class="sxs-lookup"><span data-stu-id="22ec1-123">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="22ec1-124">Пример 4. получение блока сценария, определяющего свойство для указанного объекта</span><span class="sxs-lookup"><span data-stu-id="22ec1-124">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="22ec1-125">Этот пример получает блок скрипта, который определяет свойство **DateTime** объектов **System. DateTime** в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ec1-125">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

<span data-ttu-id="22ec1-126">Команда использует `Get-TypeData` командлет для получения данных расширенного типа для типа **System.** данных.</span><span class="sxs-lookup"><span data-stu-id="22ec1-126">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="22ec1-127">Команда получает свойство **Members** объекта **TypeData**.</span><span class="sxs-lookup"><span data-stu-id="22ec1-127">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="22ec1-128">Свойство **Members** содержит хэш-таблицу свойств и методов, определенных расширенными данными типа.</span><span class="sxs-lookup"><span data-stu-id="22ec1-128">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="22ec1-129">Каждый ключ в хэш-таблице Members — это имя свойства или метода, а каждое значение — это определение значения свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="22ec1-129">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="22ec1-130">Команда получает ключ **DateTime** в **элементах** и значение свойства **жетскриптблокк** .</span><span class="sxs-lookup"><span data-stu-id="22ec1-130">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="22ec1-131">В выходных данных показан блок скрипта, который создает значение свойства **DateTime** каждого объекта **System. DateTime** в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22ec1-131">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="22ec1-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="22ec1-132">Parameters</span></span>

### <span data-ttu-id="22ec1-133">-TypeName</span><span class="sxs-lookup"><span data-stu-id="22ec1-133">-TypeName</span></span>

<span data-ttu-id="22ec1-134">Указывает данные типа как массив только для типов с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="22ec1-134">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="22ec1-135">По умолчанию `Get-TypeData` получает все типы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-135">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="22ec1-136">Введите имена типов или шаблоны имен.</span><span class="sxs-lookup"><span data-stu-id="22ec1-136">Enter type names or a name patterns.</span></span> <span data-ttu-id="22ec1-137">Полные имена или шаблоны имен с подстановочными знаками обязательны, даже для типов в пространстве имен System.</span><span class="sxs-lookup"><span data-stu-id="22ec1-137">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="22ec1-138">Поддерживаются подстановочные знаки, и имя параметра **TypeName** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="22ec1-138">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="22ec1-139">Также можно передавать имена типов в `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="22ec1-139">You can also pipe type names to `Get-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="22ec1-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="22ec1-140">CommonParameters</span></span>

<span data-ttu-id="22ec1-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22ec1-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22ec1-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="22ec1-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22ec1-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="22ec1-143">Inputs</span></span>

### <span data-ttu-id="22ec1-144">System.String</span><span class="sxs-lookup"><span data-stu-id="22ec1-144">System.String</span></span>

<span data-ttu-id="22ec1-145">Можно передать имена типов в `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="22ec1-145">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="22ec1-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="22ec1-146">Outputs</span></span>

### <span data-ttu-id="22ec1-147">System. Management. Automation. пространства выполнения. TypeData</span><span class="sxs-lookup"><span data-stu-id="22ec1-147">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="22ec1-148">Примечания</span><span class="sxs-lookup"><span data-stu-id="22ec1-148">Notes</span></span>

<span data-ttu-id="22ec1-149">`Get-TypeData` Возвращает только данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="22ec1-149">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="22ec1-150">Командлет не получает расширенный тип данных, который находится на компьютере, но не был добавлен к текущему сеансу, например расширенные типы, определенные в модулях, но не импортированные в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="22ec1-150">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="22ec1-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="22ec1-151">Related links</span></span>

[<span data-ttu-id="22ec1-152">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="22ec1-152">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="22ec1-153">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="22ec1-153">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="22ec1-154">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="22ec1-154">Update-TypeData</span></span>](Update-TypeData.md)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: dbe084b553587ba09a2ce4b76b0c662915c59808
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347352"
---
# <span data-ttu-id="eca05-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-103">Remove-Service</span></span>

## <span data-ttu-id="eca05-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eca05-104">SYNOPSIS</span></span>
<span data-ttu-id="eca05-105">Удаляет службу Windows.</span><span class="sxs-lookup"><span data-stu-id="eca05-105">Removes a Windows service.</span></span>

## <span data-ttu-id="eca05-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eca05-106">SYNTAX</span></span>

### <span data-ttu-id="eca05-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="eca05-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="eca05-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="eca05-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="eca05-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eca05-109">DESCRIPTION</span></span>

<span data-ttu-id="eca05-110">`Remove-Service`Командлет удаляет службу Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="eca05-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="eca05-111">`Remove-Service`Командлет был представлен в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="eca05-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="eca05-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="eca05-112">EXAMPLES</span></span>

### <span data-ttu-id="eca05-113">Пример 1. Удаление службы</span><span class="sxs-lookup"><span data-stu-id="eca05-113">Example 1: Remove a service</span></span>

<span data-ttu-id="eca05-114">Это приведет к удалению службы с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="eca05-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="eca05-115">Пример 2. Удаление службы с помощью отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="eca05-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="eca05-116">В этом примере удаляется служба с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="eca05-116">This example removes a service named TestService.</span></span> <span data-ttu-id="eca05-117">Команда использует `Get-Service` для получения объекта, представляющего службу TestService, с помощью отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="eca05-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="eca05-118">Оператор конвейера ( `|` ) передает объект в `Remove-Service` , который удаляет службу.</span><span class="sxs-lookup"><span data-stu-id="eca05-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="eca05-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eca05-119">PARAMETERS</span></span>

### <span data-ttu-id="eca05-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="eca05-120">-InputObject</span></span>

<span data-ttu-id="eca05-121">Указывает объекты **ServiceController** , представляющие удаляемые службы.</span><span class="sxs-lookup"><span data-stu-id="eca05-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="eca05-122">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="eca05-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="eca05-123">-Name</span><span class="sxs-lookup"><span data-stu-id="eca05-123">-Name</span></span>

<span data-ttu-id="eca05-124">Указывает имена служб для удаления.</span><span class="sxs-lookup"><span data-stu-id="eca05-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="eca05-125">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="eca05-125">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="eca05-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eca05-126">-Confirm</span></span>

<span data-ttu-id="eca05-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="eca05-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="eca05-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eca05-128">-WhatIf</span></span>

<span data-ttu-id="eca05-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="eca05-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="eca05-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="eca05-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="eca05-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="eca05-131">CommonParameters</span></span>

<span data-ttu-id="eca05-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eca05-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eca05-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eca05-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eca05-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="eca05-134">INPUTS</span></span>

### <span data-ttu-id="eca05-135">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="eca05-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="eca05-136">В этот командлет можно передать объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="eca05-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="eca05-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="eca05-137">OUTPUTS</span></span>

### <span data-ttu-id="eca05-138">Нет</span><span class="sxs-lookup"><span data-stu-id="eca05-138">None</span></span>

<span data-ttu-id="eca05-139">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="eca05-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="eca05-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="eca05-140">NOTES</span></span>

<span data-ttu-id="eca05-141">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="eca05-141">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="eca05-142">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="eca05-142">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="eca05-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="eca05-143">RELATED LINKS</span></span>

[<span data-ttu-id="eca05-144">Get-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-144">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="eca05-145">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-145">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="eca05-146">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-146">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="eca05-147">Set-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-147">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="eca05-148">Start-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-148">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="eca05-149">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-149">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="eca05-150">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="eca05-150">Suspend-Service</span></span>](Suspend-Service.md)

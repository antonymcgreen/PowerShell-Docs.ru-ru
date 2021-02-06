---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: 645efc2d271a3b95801c8d0d264ee33ed788f15f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600009"
---
# <span data-ttu-id="1676d-102">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-102">Remove-Service</span></span>

## <span data-ttu-id="1676d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1676d-103">SYNOPSIS</span></span>
<span data-ttu-id="1676d-104">Удаляет службу Windows.</span><span class="sxs-lookup"><span data-stu-id="1676d-104">Removes a Windows service.</span></span>

## <span data-ttu-id="1676d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1676d-105">SYNTAX</span></span>

### <span data-ttu-id="1676d-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1676d-106">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1676d-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="1676d-107">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1676d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1676d-108">DESCRIPTION</span></span>

<span data-ttu-id="1676d-109">`Remove-Service`Командлет удаляет службу Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="1676d-109">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="1676d-110">`Remove-Service`Командлет был представлен в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1676d-110">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="1676d-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="1676d-111">EXAMPLES</span></span>

### <span data-ttu-id="1676d-112">Пример 1. Удаление службы</span><span class="sxs-lookup"><span data-stu-id="1676d-112">Example 1: Remove a service</span></span>

<span data-ttu-id="1676d-113">Это приведет к удалению службы с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="1676d-113">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="1676d-114">Пример 2. Удаление службы с помощью отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="1676d-114">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="1676d-115">В этом примере удаляется служба с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="1676d-115">This example removes a service named TestService.</span></span> <span data-ttu-id="1676d-116">Команда использует `Get-Service` для получения объекта, представляющего службу TestService, с помощью отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="1676d-116">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="1676d-117">Оператор конвейера ( `|` ) передает объект в `Remove-Service` , который удаляет службу.</span><span class="sxs-lookup"><span data-stu-id="1676d-117">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="1676d-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1676d-118">PARAMETERS</span></span>

### <span data-ttu-id="1676d-119">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1676d-119">-InputObject</span></span>

<span data-ttu-id="1676d-120">Указывает объекты **ServiceController** , представляющие удаляемые службы.</span><span class="sxs-lookup"><span data-stu-id="1676d-120">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="1676d-121">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="1676d-121">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="1676d-122">-Name</span><span class="sxs-lookup"><span data-stu-id="1676d-122">-Name</span></span>

<span data-ttu-id="1676d-123">Указывает имена служб для удаления.</span><span class="sxs-lookup"><span data-stu-id="1676d-123">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="1676d-124">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1676d-124">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="1676d-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1676d-125">-Confirm</span></span>

<span data-ttu-id="1676d-126">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1676d-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1676d-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1676d-127">-WhatIf</span></span>

<span data-ttu-id="1676d-128">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1676d-128">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1676d-129">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1676d-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1676d-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1676d-130">CommonParameters</span></span>

<span data-ttu-id="1676d-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1676d-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1676d-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1676d-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1676d-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1676d-133">INPUTS</span></span>

### <span data-ttu-id="1676d-134">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="1676d-134">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="1676d-135">В этот командлет можно передать объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="1676d-135">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="1676d-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1676d-136">OUTPUTS</span></span>

### <span data-ttu-id="1676d-137">None</span><span class="sxs-lookup"><span data-stu-id="1676d-137">None</span></span>

<span data-ttu-id="1676d-138">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1676d-138">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="1676d-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1676d-139">NOTES</span></span>

<span data-ttu-id="1676d-140">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="1676d-140">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="1676d-141">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="1676d-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="1676d-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1676d-142">RELATED LINKS</span></span>

[<span data-ttu-id="1676d-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="1676d-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="1676d-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="1676d-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="1676d-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="1676d-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="1676d-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="1676d-149">Suspend-Service</span></span>](Suspend-Service.md)

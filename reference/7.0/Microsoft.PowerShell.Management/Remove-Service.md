---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: 13ef4d483ad91b38c175f850da9cd4d1da771935
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225541"
---
# <span data-ttu-id="c2853-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-103">Remove-Service</span></span>

## <span data-ttu-id="c2853-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c2853-104">SYNOPSIS</span></span>
<span data-ttu-id="c2853-105">Удаляет службу Windows.</span><span class="sxs-lookup"><span data-stu-id="c2853-105">Removes a Windows service.</span></span>

## <span data-ttu-id="c2853-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c2853-106">SYNTAX</span></span>

### <span data-ttu-id="c2853-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c2853-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c2853-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="c2853-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c2853-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c2853-109">DESCRIPTION</span></span>

<span data-ttu-id="c2853-110">`Remove-Service`Командлет удаляет службу Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="c2853-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="c2853-111">`Remove-Service`Командлет был представлен в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="c2853-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="c2853-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="c2853-112">EXAMPLES</span></span>

### <span data-ttu-id="c2853-113">Пример 1. Удаление службы</span><span class="sxs-lookup"><span data-stu-id="c2853-113">Example 1: Remove a service</span></span>

<span data-ttu-id="c2853-114">Это приведет к удалению службы с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="c2853-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="c2853-115">Пример 2. Удаление службы с помощью отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="c2853-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="c2853-116">В этом примере удаляется служба с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="c2853-116">This example removes a service named TestService.</span></span> <span data-ttu-id="c2853-117">Команда использует `Get-Service` для получения объекта, представляющего службу TestService, с помощью отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="c2853-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="c2853-118">Оператор конвейера ( `|` ) передает объект в `Remove-Service` , который удаляет службу.</span><span class="sxs-lookup"><span data-stu-id="c2853-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="c2853-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c2853-119">PARAMETERS</span></span>

### <span data-ttu-id="c2853-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c2853-120">-InputObject</span></span>

<span data-ttu-id="c2853-121">Указывает объекты **ServiceController** , представляющие удаляемые службы.</span><span class="sxs-lookup"><span data-stu-id="c2853-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="c2853-122">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="c2853-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="c2853-123">-Name</span><span class="sxs-lookup"><span data-stu-id="c2853-123">-Name</span></span>

<span data-ttu-id="c2853-124">Указывает имена служб для удаления.</span><span class="sxs-lookup"><span data-stu-id="c2853-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="c2853-125">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c2853-125">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c2853-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c2853-126">-Confirm</span></span>

<span data-ttu-id="c2853-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c2853-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c2853-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c2853-128">-WhatIf</span></span>

<span data-ttu-id="c2853-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c2853-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c2853-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c2853-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c2853-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c2853-131">CommonParameters</span></span>

<span data-ttu-id="c2853-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c2853-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c2853-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c2853-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c2853-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c2853-134">INPUTS</span></span>

### <span data-ttu-id="c2853-135">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="c2853-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="c2853-136">В этот командлет можно передать объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="c2853-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="c2853-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c2853-137">OUTPUTS</span></span>

### <span data-ttu-id="c2853-138">Нет</span><span class="sxs-lookup"><span data-stu-id="c2853-138">None</span></span>

<span data-ttu-id="c2853-139">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c2853-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="c2853-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c2853-140">NOTES</span></span>

<span data-ttu-id="c2853-141">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="c2853-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="c2853-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c2853-142">RELATED LINKS</span></span>

[<span data-ttu-id="c2853-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="c2853-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="c2853-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="c2853-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="c2853-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="c2853-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="c2853-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="c2853-149">Suspend-Service</span></span>](Suspend-Service.md)

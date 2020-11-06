---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: 4407784b6e7e2897610991dbd449997143471134
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228046"
---
# <span data-ttu-id="1acd5-102">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1acd5-102">Disable-ExperimentalFeature</span></span>

## <span data-ttu-id="1acd5-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1acd5-103">SYNOPSIS</span></span>
<span data-ttu-id="1acd5-104">Отключите экспериментальную функцию при запуске нового экземпляра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd5-104">Disable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="1acd5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1acd5-105">SYNTAX</span></span>

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1acd5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1acd5-106">DESCRIPTION</span></span>

<span data-ttu-id="1acd5-107">`Disable-ExperimentalFeature`Командлет отключает экспериментальные функции, удаляя именованные экспериментальные функции из `powershell.config.json` файла параметров, считанного при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd5-107">The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named experimental features from the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="1acd5-108">Этот командлет появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="1acd5-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="1acd5-109">Любые изменения в экспериментальном состоянии вступают в силу только при перезапуске PowerShell</span><span class="sxs-lookup"><span data-stu-id="1acd5-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="1acd5-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="1acd5-110">EXAMPLES</span></span>

### <span data-ttu-id="1acd5-111">Пример 1. Отключение экспериментальной функции</span><span class="sxs-lookup"><span data-stu-id="1acd5-111">Example 1: Disable an experimental feature</span></span>

<span data-ttu-id="1acd5-112">В этом примере, если эта экспериментальная функция была включена ранее, `powershell.config.json` файл будет обновлен, чтобы пользователь не включил эту функцию после перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd5-112">In this example, if this experimental feature was previously enabled, then the `powershell.config.json` file is updated for the user to not enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="1acd5-113">При успешном выполнении в конвейер ничего не выводится, и отображается только предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="1acd5-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="1acd5-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1acd5-114">PARAMETERS</span></span>

### <span data-ttu-id="1acd5-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1acd5-115">-Confirm</span></span>

<span data-ttu-id="1acd5-116">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1acd5-116">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1acd5-117">-Name</span><span class="sxs-lookup"><span data-stu-id="1acd5-117">-Name</span></span>

<span data-ttu-id="1acd5-118">Имя или имена экспериментальных функций для отключения.</span><span class="sxs-lookup"><span data-stu-id="1acd5-118">The name or names of the experimental features to disable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1acd5-119">-Scope</span><span class="sxs-lookup"><span data-stu-id="1acd5-119">-Scope</span></span>

<span data-ttu-id="1acd5-120">Определяет, какие `powershell.config.json` обновления влияют на все пользователи или только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1acd5-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1acd5-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1acd5-121">-WhatIf</span></span>

<span data-ttu-id="1acd5-122">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1acd5-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1acd5-123">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1acd5-123">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1acd5-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1acd5-124">CommonParameters</span></span>

<span data-ttu-id="1acd5-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1acd5-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1acd5-126">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1acd5-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1acd5-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1acd5-127">INPUTS</span></span>

### <span data-ttu-id="1acd5-128">експерименталфеатуре</span><span class="sxs-lookup"><span data-stu-id="1acd5-128">ExperimentalFeature</span></span>

<span data-ttu-id="1acd5-129">Для отключения необходимо передать экземпляры Експерименталфеатуре из `Get-ExperimentalFeature` командлета.</span><span class="sxs-lookup"><span data-stu-id="1acd5-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to disable.</span></span>

## <span data-ttu-id="1acd5-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1acd5-130">OUTPUTS</span></span>

### <span data-ttu-id="1acd5-131">Нет</span><span class="sxs-lookup"><span data-stu-id="1acd5-131">None</span></span>

<span data-ttu-id="1acd5-132">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1acd5-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="1acd5-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1acd5-133">NOTES</span></span>

<span data-ttu-id="1acd5-134">Изменения в состоянии экспериментальной функции вступают в силу только при перезапуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd5-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="1acd5-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1acd5-135">RELATED LINKS</span></span>

[<span data-ttu-id="1acd5-136">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1acd5-136">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)

[<span data-ttu-id="1acd5-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1acd5-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)
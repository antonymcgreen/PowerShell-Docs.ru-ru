---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-experimentalfeature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ExperimentalFeature
ms.openlocfilehash: 79884c73bc6e010eb218f1b722d26e0aaa05ef53
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226157"
---
# <span data-ttu-id="1ec98-102">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1ec98-102">Enable-ExperimentalFeature</span></span>

## <span data-ttu-id="1ec98-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1ec98-103">SYNOPSIS</span></span>
<span data-ttu-id="1ec98-104">Включите экспериментальную функцию при запуске нового экземпляра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ec98-104">Enable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="1ec98-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ec98-105">SYNTAX</span></span>

```
Enable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1ec98-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ec98-106">DESCRIPTION</span></span>

<span data-ttu-id="1ec98-107">`Enable-ExperimentalFeature`Командлет включает экспериментальные функции, добавляя именованные экспериментальные функции в `powershell.config.json` файл параметров, который считывается при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ec98-107">The `Enable-ExperimentalFeature` cmdlet enables experimental features by adding the named experimental features to the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="1ec98-108">Этот командлет появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="1ec98-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec98-109">Любые изменения в экспериментальном состоянии вступают в силу только при перезапуске PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ec98-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="1ec98-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ec98-110">EXAMPLES</span></span>

### <span data-ttu-id="1ec98-111">Пример 1. Включение экспериментальной функции</span><span class="sxs-lookup"><span data-stu-id="1ec98-111">Example 1: Enable an experimental feature</span></span>

<span data-ttu-id="1ec98-112">В этом примере, если эта экспериментальная функция была ранее отключена, `powershell.config.json` файл будет обновлен, чтобы включить эту функцию после перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ec98-112">In this example, if this experimental feature was previously disabled, then the `powershell.config.json` file is updated for the user to enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="1ec98-113">При успешном выполнении в конвейер ничего не выводится, и отображается только предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="1ec98-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
Enable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="1ec98-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ec98-114">PARAMETERS</span></span>

### <span data-ttu-id="1ec98-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1ec98-115">-Confirm</span></span>

<span data-ttu-id="1ec98-116">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1ec98-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1ec98-117">-Name</span><span class="sxs-lookup"><span data-stu-id="1ec98-117">-Name</span></span>

<span data-ttu-id="1ec98-118">Имя или имена экспериментальных функций, которые нужно включить.</span><span class="sxs-lookup"><span data-stu-id="1ec98-118">The name or names of the experimental features to enable.</span></span>

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

### <span data-ttu-id="1ec98-119">-Scope</span><span class="sxs-lookup"><span data-stu-id="1ec98-119">-Scope</span></span>

<span data-ttu-id="1ec98-120">Определяет, какие `powershell.config.json` обновления влияют на все пользователи или только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ec98-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

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

### <span data-ttu-id="1ec98-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1ec98-121">-WhatIf</span></span>

<span data-ttu-id="1ec98-122">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1ec98-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1ec98-123">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1ec98-123">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1ec98-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1ec98-124">CommonParameters</span></span>

<span data-ttu-id="1ec98-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ec98-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ec98-126">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ec98-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ec98-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1ec98-127">INPUTS</span></span>

### <span data-ttu-id="1ec98-128">експерименталфеатуре</span><span class="sxs-lookup"><span data-stu-id="1ec98-128">ExperimentalFeature</span></span>

<span data-ttu-id="1ec98-129">Передаем экземпляры Експерименталфеатуре из `Get-ExperimentalFeature` командлета, чтобы включить.</span><span class="sxs-lookup"><span data-stu-id="1ec98-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to enable.</span></span>

## <span data-ttu-id="1ec98-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1ec98-130">OUTPUTS</span></span>

### <span data-ttu-id="1ec98-131">Нет</span><span class="sxs-lookup"><span data-stu-id="1ec98-131">None</span></span>

<span data-ttu-id="1ec98-132">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1ec98-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="1ec98-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1ec98-133">NOTES</span></span>

<span data-ttu-id="1ec98-134">Изменения в состоянии экспериментальной функции вступают в силу только при перезапуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ec98-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="1ec98-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1ec98-135">RELATED LINKS</span></span>

[<span data-ttu-id="1ec98-136">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1ec98-136">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="1ec98-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="1ec98-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

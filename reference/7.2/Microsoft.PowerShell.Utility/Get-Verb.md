---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 6aba1c87a5d711cbfe84f9f6f6d1051acbcd524a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605299"
---
# <span data-ttu-id="0bc49-102">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="0bc49-102">Get-Verb</span></span>

## <span data-ttu-id="0bc49-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0bc49-103">SYNOPSIS</span></span>
<span data-ttu-id="0bc49-104">Получает утвержденные команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bc49-104">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="0bc49-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bc49-105">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0bc49-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bc49-106">DESCRIPTION</span></span>

<span data-ttu-id="0bc49-107">`Get-Verb`Функция возвращает команды, которые утверждены для использования в командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bc49-107">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="0bc49-108">Рекомендуется, чтобы имена командлетов и функций PowerShell были в `Verb-Noun` формате и включали утвержденную команду.</span><span class="sxs-lookup"><span data-stu-id="0bc49-108">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="0bc49-109">Такой подход делает имена команд более единообразными, прогнозируемыми и простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="0bc49-109">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="0bc49-110">Команды, использующие неутвержденные команды, по-прежнему выполняются в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bc49-110">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="0bc49-111">Однако при импорте модуля, который содержит команду с неодобренным глаголом, в имени `Import-Module` команды отображается предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="0bc49-111">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="0bc49-112">Возвращаемый список команд `Get-Verb` может быть неполным.</span><span class="sxs-lookup"><span data-stu-id="0bc49-112">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="0bc49-113">Обновленный список утвержденных команд PowerShell с описаниями см. в разделе [утвержденные команды](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0bc49-113">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="0bc49-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="0bc49-114">Examples</span></span>

### <span data-ttu-id="0bc49-115">Пример 1. Получение списка всех команд</span><span class="sxs-lookup"><span data-stu-id="0bc49-115">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="0bc49-116">Пример 2. Получение списка утвержденных команд, начинающихся с "UN"</span><span class="sxs-lookup"><span data-stu-id="0bc49-116">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="0bc49-117">Пример 3. получение всех утвержденных команд в группе безопасности</span><span class="sxs-lookup"><span data-stu-id="0bc49-117">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="0bc49-118">Пример 4. Поиск всех команд в модуле с неутвержденными командами</span><span class="sxs-lookup"><span data-stu-id="0bc49-118">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="0bc49-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bc49-119">PARAMETERS</span></span>

### <span data-ttu-id="0bc49-120">-Verb</span><span class="sxs-lookup"><span data-stu-id="0bc49-120">-Verb</span></span>

<span data-ttu-id="0bc49-121">Возвращает только указанные глаголы.</span><span class="sxs-lookup"><span data-stu-id="0bc49-121">Gets only the specified verbs.</span></span> <span data-ttu-id="0bc49-122">Введите имя глагола или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="0bc49-122">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="0bc49-123">Знаки подстановки разрешены.</span><span class="sxs-lookup"><span data-stu-id="0bc49-123">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0bc49-124">-Group</span><span class="sxs-lookup"><span data-stu-id="0bc49-124">-Group</span></span>

<span data-ttu-id="0bc49-125">Возвращает только указанные группы.</span><span class="sxs-lookup"><span data-stu-id="0bc49-125">Gets only the specified groups.</span></span> <span data-ttu-id="0bc49-126">Введите имя группы.</span><span class="sxs-lookup"><span data-stu-id="0bc49-126">Enter the name of a group.</span></span> <span data-ttu-id="0bc49-127">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="0bc49-127">Wildcards are not allowed.</span></span>

<span data-ttu-id="0bc49-128">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0bc49-128">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0bc49-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0bc49-129">CommonParameters</span></span>

<span data-ttu-id="0bc49-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bc49-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bc49-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bc49-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bc49-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0bc49-132">INPUTS</span></span>

### <span data-ttu-id="0bc49-133">None</span><span class="sxs-lookup"><span data-stu-id="0bc49-133">None</span></span>

## <span data-ttu-id="0bc49-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0bc49-134">OUTPUTS</span></span>

### <span data-ttu-id="0bc49-135">System. Management. Automation. Вербинфо</span><span class="sxs-lookup"><span data-stu-id="0bc49-135">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="0bc49-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0bc49-136">NOTES</span></span>

<span data-ttu-id="0bc49-137">Команды PowerShell назначаются группе в соответствии с их наиболее распространенным использованием.</span><span class="sxs-lookup"><span data-stu-id="0bc49-137">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="0bc49-138">Группы предназначены для поиска и сравнения глаголов, а не для ограничения их использования.</span><span class="sxs-lookup"><span data-stu-id="0bc49-138">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="0bc49-139">Утвержденный глагол можно использовать в команде любого типа.</span><span class="sxs-lookup"><span data-stu-id="0bc49-139">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="0bc49-140">Каждая команда PowerShell назначается одной из следующих групп.</span><span class="sxs-lookup"><span data-stu-id="0bc49-140">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="0bc49-141">Общие: Определите общие действия, которые могут применяться практически к любому командлету, например Add.</span><span class="sxs-lookup"><span data-stu-id="0bc49-141">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="0bc49-142">Обмен данными: определение действий, которые применяются к обмену данными, например Connect.</span><span class="sxs-lookup"><span data-stu-id="0bc49-142">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="0bc49-143">Данные: определяют действия, которые применяются к обработке данных, например резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="0bc49-143">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="0bc49-144">Диагностика. определяет действия, которые применяются к диагностике, например Отладка.</span><span class="sxs-lookup"><span data-stu-id="0bc49-144">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="0bc49-145">Жизненный цикл. Определите действия, которые применяются к жизненному циклу командлета, например Complete.</span><span class="sxs-lookup"><span data-stu-id="0bc49-145">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="0bc49-146">Безопасность: Определите действия, которые применяются к безопасности, например отозвать.</span><span class="sxs-lookup"><span data-stu-id="0bc49-146">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="0bc49-147">Другое: определение других типов действий.</span><span class="sxs-lookup"><span data-stu-id="0bc49-147">Other: Define other types of actions.</span></span>

<span data-ttu-id="0bc49-148">Некоторые командлеты, устанавливаемые с помощью PowerShell, такие как `Tee-Object` и `Where-Object` , используют неутвержденные команды.</span><span class="sxs-lookup"><span data-stu-id="0bc49-148">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="0bc49-149">Эти командлеты являются историческими исключениями, а их глаголы классифицируются как **зарезервированные**.</span><span class="sxs-lookup"><span data-stu-id="0bc49-149">These cmdlets are historic exceptions and their verbs are classified as **reserved**.</span></span>

## <span data-ttu-id="0bc49-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0bc49-150">RELATED LINKS</span></span>

[<span data-ttu-id="0bc49-151">Import-Module</span><span class="sxs-lookup"><span data-stu-id="0bc49-151">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)


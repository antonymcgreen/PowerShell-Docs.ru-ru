---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 516ecf2b5d6e3bce2a0cda7c36c143d2ba75933a
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "93230418"
---
# <span data-ttu-id="4b4f8-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="4b4f8-103">Get-Verb</span></span>

## <span data-ttu-id="4b4f8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b4f8-104">SYNOPSIS</span></span>
<span data-ttu-id="4b4f8-105">Получает утвержденные команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="4b4f8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b4f8-106">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="4b4f8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b4f8-107">DESCRIPTION</span></span>

<span data-ttu-id="4b4f8-108">`Get-Verb`Функция возвращает команды, которые утверждены для использования в командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="4b4f8-109">Рекомендуется, чтобы имена командлетов и функций PowerShell были в `Verb-Noun` формате и включали утвержденную команду.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-109">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="4b4f8-110">Такой подход делает имена команд более единообразными, прогнозируемыми и простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="4b4f8-111">Команды, использующие неутвержденные команды, по-прежнему выполняются в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-111">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="4b4f8-112">Однако при импорте модуля, который содержит команду с неодобренным глаголом, в имени `Import-Module` команды отображается предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="4b4f8-113">Возвращаемый список команд `Get-Verb` может быть неполным.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="4b4f8-114">Обновленный список утвержденных команд PowerShell с описаниями см. в разделе [утвержденные команды](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="4b4f8-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b4f8-115">Examples</span></span>

### <span data-ttu-id="4b4f8-116">Пример 1. Получение списка всех команд</span><span class="sxs-lookup"><span data-stu-id="4b4f8-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="4b4f8-117">Пример 2. Получение списка утвержденных команд, начинающихся с "UN"</span><span class="sxs-lookup"><span data-stu-id="4b4f8-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

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

### <span data-ttu-id="4b4f8-118">Пример 3. получение всех утвержденных команд в группе безопасности</span><span class="sxs-lookup"><span data-stu-id="4b4f8-118">Example 3 - Get all approved verbs in the Security group</span></span>

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

### <span data-ttu-id="4b4f8-119">Пример 4. Поиск всех команд в модуле с неутвержденными командами</span><span class="sxs-lookup"><span data-stu-id="4b4f8-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="4b4f8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b4f8-120">PARAMETERS</span></span>

### <span data-ttu-id="4b4f8-121">-Verb</span><span class="sxs-lookup"><span data-stu-id="4b4f8-121">-Verb</span></span>

<span data-ttu-id="4b4f8-122">Возвращает только указанные глаголы.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-122">Gets only the specified verbs.</span></span> <span data-ttu-id="4b4f8-123">Введите имя глагола или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-123">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="4b4f8-124">Знаки подстановки разрешены.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-124">Wildcards are allowed.</span></span>

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

### <span data-ttu-id="4b4f8-125">-Group</span><span class="sxs-lookup"><span data-stu-id="4b4f8-125">-Group</span></span>

<span data-ttu-id="4b4f8-126">Возвращает только указанные группы.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-126">Gets only the specified groups.</span></span> <span data-ttu-id="4b4f8-127">Введите имя группы.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-127">Enter the name of a group.</span></span> <span data-ttu-id="4b4f8-128">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-128">Wildcards are not allowed.</span></span>

<span data-ttu-id="4b4f8-129">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-129">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="4b4f8-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b4f8-130">CommonParameters</span></span>

<span data-ttu-id="4b4f8-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b4f8-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b4f8-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b4f8-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b4f8-133">INPUTS</span></span>

### <span data-ttu-id="4b4f8-134">Нет</span><span class="sxs-lookup"><span data-stu-id="4b4f8-134">None</span></span>

## <span data-ttu-id="4b4f8-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b4f8-135">OUTPUTS</span></span>

### <span data-ttu-id="4b4f8-136">System. Management. Automation. Вербинфо</span><span class="sxs-lookup"><span data-stu-id="4b4f8-136">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="4b4f8-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b4f8-137">NOTES</span></span>

<span data-ttu-id="4b4f8-138">Команды PowerShell назначаются группе в соответствии с их наиболее распространенным использованием.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-138">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="4b4f8-139">Группы предназначены для поиска и сравнения глаголов, а не для ограничения их использования.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-139">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="4b4f8-140">Утвержденный глагол можно использовать в команде любого типа.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-140">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="4b4f8-141">Каждая команда PowerShell назначается одной из следующих групп.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-141">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="4b4f8-142">Общие: Определите общие действия, которые могут применяться практически к любому командлету, например Add.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-142">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="4b4f8-143">Обмен данными: определение действий, которые применяются к обмену данными, например Connect.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-143">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="4b4f8-144">Данные: определяют действия, которые применяются к обработке данных, например резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-144">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="4b4f8-145">Диагностика. определяет действия, которые применяются к диагностике, например Отладка.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-145">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="4b4f8-146">Жизненный цикл. Определите действия, которые применяются к жизненному циклу командлета, например Complete.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-146">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="4b4f8-147">Безопасность: Определите действия, которые применяются к безопасности, например отозвать.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-147">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="4b4f8-148">Другое: определение других типов действий.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-148">Other: Define other types of actions.</span></span>

<span data-ttu-id="4b4f8-149">Некоторые командлеты, устанавливаемые с помощью PowerShell, такие как `Tee-Object` и `Where-Object` , используют неутвержденные команды.</span><span class="sxs-lookup"><span data-stu-id="4b4f8-149">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="4b4f8-150">Эти командлеты являются историческими исключениями, а их глаголы классифицируются как **зарезервированные** .</span><span class="sxs-lookup"><span data-stu-id="4b4f8-150">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="4b4f8-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b4f8-151">RELATED LINKS</span></span>

[<span data-ttu-id="4b4f8-152">Import-Module</span><span class="sxs-lookup"><span data-stu-id="4b4f8-152">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)

---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "93230413"
---
# <span data-ttu-id="b0370-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="b0370-103">Get-Verb</span></span>

## <span data-ttu-id="b0370-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b0370-104">SYNOPSIS</span></span>
<span data-ttu-id="b0370-105">Получает утвержденные команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0370-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="b0370-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0370-106">SYNTAX</span></span>

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="b0370-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0370-107">DESCRIPTION</span></span>

<span data-ttu-id="b0370-108">`Get-Verb`Функция возвращает команды, которые утверждены для использования в командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0370-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="b0370-109">PowerShell рекомендует имена командлетов и функций в формате Verb-Noun и включают утвержденную команду.</span><span class="sxs-lookup"><span data-stu-id="b0370-109">PowerShell recommends cmdlet and function names have the Verb-Noun format and include an approved verb.</span></span> <span data-ttu-id="b0370-110">Такой подход делает имена команд более единообразными, прогнозируемыми и простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="b0370-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="b0370-111">Команды, использующие неутвержденные команды, выполняются в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0370-111">Commands that use unapproved verbs run in PowerShell.</span></span> <span data-ttu-id="b0370-112">Однако при импорте модуля, который содержит команду с неодобренным глаголом, в имени `Import-Module` команды отображается предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="b0370-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="b0370-113">Возвращаемый список команд `Get-Verb` может быть неполным.</span><span class="sxs-lookup"><span data-stu-id="b0370-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="b0370-114">Обновленный список утвержденных команд PowerShell с описаниями см. в разделе [утвержденные команды](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0370-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="b0370-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="b0370-115">EXAMPLES</span></span>

### <span data-ttu-id="b0370-116">Пример 1. Получение списка всех команд</span><span class="sxs-lookup"><span data-stu-id="b0370-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="b0370-117">Пример 2. Получение списка утвержденных команд, начинающихся с "UN"</span><span class="sxs-lookup"><span data-stu-id="b0370-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### <span data-ttu-id="b0370-118">Пример 3. получение всех утвержденных команд в группе безопасности</span><span class="sxs-lookup"><span data-stu-id="b0370-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### <span data-ttu-id="b0370-119">Пример 4. Поиск всех команд в модуле с неутвержденными командами</span><span class="sxs-lookup"><span data-stu-id="b0370-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="b0370-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0370-120">PARAMETERS</span></span>

### <span data-ttu-id="b0370-121">-verb</span><span class="sxs-lookup"><span data-stu-id="b0370-121">-verb</span></span>

<span data-ttu-id="b0370-122">Возвращает только указанные глаголы.</span><span class="sxs-lookup"><span data-stu-id="b0370-122">Gets only the specified verbs.</span></span>
<span data-ttu-id="b0370-123">Введите имя глагола или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="b0370-123">Enter the name of a verb or a name pattern.</span></span>
<span data-ttu-id="b0370-124">Знаки подстановки разрешены.</span><span class="sxs-lookup"><span data-stu-id="b0370-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## <span data-ttu-id="b0370-125">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b0370-125">INPUTS</span></span>

### <span data-ttu-id="b0370-126">Нет</span><span class="sxs-lookup"><span data-stu-id="b0370-126">None</span></span>

## <span data-ttu-id="b0370-127">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b0370-127">OUTPUTS</span></span>

### <span data-ttu-id="b0370-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="b0370-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span></span>

## <span data-ttu-id="b0370-129">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b0370-129">NOTES</span></span>

<span data-ttu-id="b0370-130">`Get-Verb` Возвращает измененную версию объекта Microsoft. PowerShell. Commands. MemberDefinition.</span><span class="sxs-lookup"><span data-stu-id="b0370-130">`Get-Verb` returns a modified version of a Microsoft.PowerShell.Commands.MemberDefinition object.</span></span>
<span data-ttu-id="b0370-131">Объект не имеет стандартных свойств объекта MemberDefinition.</span><span class="sxs-lookup"><span data-stu-id="b0370-131">The object does not have the standard properties of a MemberDefinition object.</span></span> <span data-ttu-id="b0370-132">У него есть свойства Verb и Group.</span><span class="sxs-lookup"><span data-stu-id="b0370-132">Instead it has Verb and Group properties.</span></span> <span data-ttu-id="b0370-133">Свойство Verb содержит строку с наименованием глагола.</span><span class="sxs-lookup"><span data-stu-id="b0370-133">The Verb property contains a string with the verb name.</span></span> <span data-ttu-id="b0370-134">Свойство Group содержит строку с группой глаголов.</span><span class="sxs-lookup"><span data-stu-id="b0370-134">The Group property contains a string with the verb group.</span></span>

<span data-ttu-id="b0370-135">Команды PowerShell назначаются группе в соответствии с их наиболее распространенным использованием.</span><span class="sxs-lookup"><span data-stu-id="b0370-135">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="b0370-136">Группы предназначены для поиска и сравнения глаголов, а не для ограничения их использования.</span><span class="sxs-lookup"><span data-stu-id="b0370-136">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="b0370-137">Утвержденный глагол можно использовать в команде любого типа.</span><span class="sxs-lookup"><span data-stu-id="b0370-137">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="b0370-138">Каждая команда PowerShell назначается одной из следующих групп.</span><span class="sxs-lookup"><span data-stu-id="b0370-138">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="b0370-139">Общие: Определите общие действия, которые могут применяться практически к любому командлету, например Add.</span><span class="sxs-lookup"><span data-stu-id="b0370-139">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="b0370-140">Обмен данными: определение действий, которые применяются к обмену данными, например Connect.</span><span class="sxs-lookup"><span data-stu-id="b0370-140">Communications:  Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="b0370-141">Данные: определяют действия, которые применяются к обработке данных, например резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="b0370-141">Data:  Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="b0370-142">Диагностика. определяет действия, которые применяются к диагностике, например Отладка.</span><span class="sxs-lookup"><span data-stu-id="b0370-142">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="b0370-143">Жизненный цикл. Определите действия, которые применяются к жизненному циклу командлета, например Complete.</span><span class="sxs-lookup"><span data-stu-id="b0370-143">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="b0370-144">Безопасность: Определите действия, которые применяются к безопасности, например отозвать.</span><span class="sxs-lookup"><span data-stu-id="b0370-144">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="b0370-145">Другое: определение других типов действий.</span><span class="sxs-lookup"><span data-stu-id="b0370-145">Other: Define other types of actions.</span></span>

<span data-ttu-id="b0370-146">Некоторые командлеты, устанавливаемые с помощью PowerShell, такие как `Tee-Object` и `Where-Object` , используют неутвержденные команды.</span><span class="sxs-lookup"><span data-stu-id="b0370-146">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="b0370-147">Эти командлеты являются историческими исключениями, а их глаголы классифицируются как **зарезервированные** .</span><span class="sxs-lookup"><span data-stu-id="b0370-147">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="b0370-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b0370-148">RELATED LINKS</span></span>

[<span data-ttu-id="b0370-149">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b0370-149">Import-Module</span></span>](import-module.md)

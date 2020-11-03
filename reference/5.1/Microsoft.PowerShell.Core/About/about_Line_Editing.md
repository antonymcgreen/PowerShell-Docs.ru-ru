---
description: Описание процесса изменения команд в командной строке PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: 5bf1505a7dd8c6ea29422eae9307c97ddd4765cb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232009"
---
# <a name="about-line-editing"></a><span data-ttu-id="7df7e-104">О редактировании строк</span><span class="sxs-lookup"><span data-stu-id="7df7e-104">About Line Editing</span></span>

## <a name="short-description"></a><span data-ttu-id="7df7e-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7df7e-105">Short description</span></span>

<span data-ttu-id="7df7e-106">Описание процесса изменения команд в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df7e-106">Describes how to edit commands at the PowerShell command prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="7df7e-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="7df7e-107">Long description</span></span>

<span data-ttu-id="7df7e-108">Консоль PowerShell имеет несколько полезных сочетаний клавиш, с помощью которых можно изменять команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df7e-108">The PowerShell console has some useful keyboard shortcuts to help you edit commands at the PowerShell command prompt.</span></span>

### <a name="add-a-line"></a><span data-ttu-id="7df7e-109">Добавление линии</span><span class="sxs-lookup"><span data-stu-id="7df7e-109">Add a line</span></span>

<span data-ttu-id="7df7e-110">Чтобы добавить линию, нажмите клавишу <kbd>SHIFT</kbd> + <kbd>Ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-110">To add a line, press <kbd>Shift</kbd>+<kbd>Enter</kbd>.</span></span>

<span data-ttu-id="7df7e-111">Можно добавить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="7df7e-111">You can add multiple lines.</span></span> <span data-ttu-id="7df7e-112">Каждая дополнительная строка начинается с `>>` строки продолжения.</span><span class="sxs-lookup"><span data-stu-id="7df7e-112">Each additional line begins with `>>`, the continuation prompt.</span></span> <span data-ttu-id="7df7e-113">Нажмите клавишу <kbd>Ввод</kbd> , чтобы выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="7df7e-113">Press <kbd>Enter</kbd> to execute the command.</span></span>

### <a name="move-left-and-right"></a><span data-ttu-id="7df7e-114">Переместить влево и вправо</span><span class="sxs-lookup"><span data-stu-id="7df7e-114">Move left and right</span></span>

<span data-ttu-id="7df7e-115">Чтобы переместить курсор на один символ влево, нажмите клавишу <kbd>стрелка влево</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-115">To move the cursor one character to the left, press the <kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="7df7e-116">Чтобы переместить курсор на одно слово влево, нажмите клавиши <kbd>CTRL</kbd> + <kbd>стрелка влево</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-116">To move the cursor one word to the left, press <kbd>Ctrl</kbd>+<kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="7df7e-117">Чтобы переместить курсор на один символ вправо, нажмите <kbd>стрелку вправо</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-117">To move the cursor one character to the right, press the <kbd>Right arrow</kbd>.</span></span>

<span data-ttu-id="7df7e-118">Чтобы переместить курсор на одно слово вправо, нажмите клавишу <kbd>CTRL</kbd> + <kbd>стрелка вправо</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-118">To move the cursor one word to the right, press <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.</span></span>

### <a name="move-to-a-lines-beginning-or-end"></a><span data-ttu-id="7df7e-119">Перейти к началу или концу строки</span><span class="sxs-lookup"><span data-stu-id="7df7e-119">Move to a line's beginning or end</span></span>

<span data-ttu-id="7df7e-120">Чтобы перейти к началу строки, нажмите клавишу <kbd>Home</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-120">To move to the beginning of a line, press <kbd>Home</kbd>.</span></span>

<span data-ttu-id="7df7e-121">Чтобы перейти к концу строки, нажмите клавишу <kbd>End</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-121">To move to the end of a line, press <kbd>End</kbd>.</span></span>

<span data-ttu-id="7df7e-122">Если строки были добавлены, дважды нажмите клавишу <kbd>Home</kbd> или <kbd>End</kbd> , чтобы перейти к началу или концу строк.</span><span class="sxs-lookup"><span data-stu-id="7df7e-122">If lines were added, press <kbd>Home</kbd> or <kbd>End</kbd> twice to move to the beginning or end of the lines.</span></span>

### <a name="delete-characters"></a><span data-ttu-id="7df7e-123">Удалить символы</span><span class="sxs-lookup"><span data-stu-id="7df7e-123">Delete characters</span></span>

<span data-ttu-id="7df7e-124">Чтобы удалить символ, расположенный за положением курсора, нажмите клавишу <kbd>Backspace</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-124">To delete the character behind the cursor's position, press <kbd>Backspace</kbd>.</span></span>

<span data-ttu-id="7df7e-125">Чтобы удалить символ в позиции курсора, нажмите клавишу <kbd>Delete</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-125">To delete the character at the cursor's position, press <kbd>Delete</kbd>.</span></span>

### <a name="delete-characters-from-a-line"></a><span data-ttu-id="7df7e-126">Удалить символы из строки</span><span class="sxs-lookup"><span data-stu-id="7df7e-126">Delete characters from a line</span></span>

<span data-ttu-id="7df7e-127">Чтобы удалить все символы с позиции курсора до конца строки, нажмите клавишу <kbd>CTRL</kbd> + <kbd>End</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-127">To delete all the characters from the cursor's position to the end of a line, press <kbd>Ctrl</kbd>+<kbd>End</kbd>.</span></span>

<span data-ttu-id="7df7e-128">Чтобы удалить все символы из позиции курсора в начало строки, нажмите <kbd>CTRL</kbd> + <kbd>Home</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-128">To delete all the characters from the cursor's position to the beginning of a line, press <kbd>Ctrl</kbd>+<kbd>Home</kbd>.</span></span>

<span data-ttu-id="7df7e-129">Если были добавлены строки, то символы удаляются из текущей строки и добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="7df7e-129">If lines were added, characters are deleted from the current line and the lines that were added.</span></span>

### <a name="insert-and-overstrike-mode"></a><span data-ttu-id="7df7e-130">Режим вставки и замены</span><span class="sxs-lookup"><span data-stu-id="7df7e-130">Insert and overstrike mode</span></span>

<span data-ttu-id="7df7e-131">Чтобы изменить режим перезаписи, нажмите клавишу <kbd>INSERT</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7df7e-131">To change to overwrite mode, press <kbd>Insert</kbd>.</span></span> <span data-ttu-id="7df7e-132">Чтобы вернуться в режим вставки, еще раз нажмите клавишу <kbd>INSERT</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7df7e-132">To return to insert mode, press <kbd>Insert</kbd> again.</span></span>

### <a name="tab-completion"></a><span data-ttu-id="7df7e-133">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="7df7e-133">Tab completion</span></span>

<span data-ttu-id="7df7e-134">Чтобы завершить имя командлета, параметр или путь, нажмите клавишу <kbd>Tab</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7df7e-134">To complete a cmdlet name, a parameter, or a path, press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="7df7e-135">Чтобы прокрутить список значений, снова нажмите клавишу <kbd>Tab</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7df7e-135">To scroll through a list of values, press the <kbd>Tab</kbd> key again.</span></span>

## <a name="see-also"></a><span data-ttu-id="7df7e-136">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7df7e-136">See also</span></span>

[<span data-ttu-id="7df7e-137">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="7df7e-137">about_Command_Syntax</span></span>](about_Command_Syntax.md)

[<span data-ttu-id="7df7e-138">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="7df7e-138">about_Path_Syntax</span></span>](about_Path_Syntax.md)

[<span data-ttu-id="7df7e-139">about_PSReadline</span><span class="sxs-lookup"><span data-stu-id="7df7e-139">about_PSReadline</span></span>](../../PSReadline/About/about_PSReadline.md)

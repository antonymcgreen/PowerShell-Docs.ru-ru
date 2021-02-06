---
description: Описание процесса изменения команд в командной строке PowerShell.
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: 2b9a320b92bc0a61efc9f9ed75078b17cdd9cbc9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601082"
---
# <a name="about-line-editing"></a><span data-ttu-id="7f4eb-103">О редактировании строк</span><span class="sxs-lookup"><span data-stu-id="7f4eb-103">About Line Editing</span></span>

## <a name="short-description"></a><span data-ttu-id="7f4eb-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7f4eb-104">Short description</span></span>

<span data-ttu-id="7f4eb-105">Описание процесса изменения команд в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-105">Describes how to edit commands at the PowerShell command prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="7f4eb-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="7f4eb-106">Long description</span></span>

<span data-ttu-id="7f4eb-107">Консоль PowerShell имеет несколько полезных сочетаний клавиш, с помощью которых можно изменять команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-107">The PowerShell console has some useful keyboard shortcuts to help you edit commands at the PowerShell command prompt.</span></span>

### <a name="add-a-line"></a><span data-ttu-id="7f4eb-108">Добавление линии</span><span class="sxs-lookup"><span data-stu-id="7f4eb-108">Add a line</span></span>

<span data-ttu-id="7f4eb-109">Чтобы добавить линию, нажмите клавишу <kbd>SHIFT</kbd> + <kbd>Ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-109">To add a line, press <kbd>Shift</kbd>+<kbd>Enter</kbd>.</span></span>

<span data-ttu-id="7f4eb-110">Можно добавить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-110">You can add multiple lines.</span></span> <span data-ttu-id="7f4eb-111">Каждая дополнительная строка начинается с `>>` строки продолжения.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-111">Each additional line begins with `>>`, the continuation prompt.</span></span> <span data-ttu-id="7f4eb-112">Нажмите клавишу <kbd>Ввод</kbd> , чтобы выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-112">Press <kbd>Enter</kbd> to execute the command.</span></span>

### <a name="move-left-and-right"></a><span data-ttu-id="7f4eb-113">Переместить влево и вправо</span><span class="sxs-lookup"><span data-stu-id="7f4eb-113">Move left and right</span></span>

<span data-ttu-id="7f4eb-114">Чтобы переместить курсор на один символ влево, нажмите клавишу <kbd>стрелка влево</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-114">To move the cursor one character to the left, press the <kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="7f4eb-115">Чтобы переместить курсор на одно слово влево, нажмите клавиши <kbd>CTRL</kbd> + <kbd>стрелка влево</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-115">To move the cursor one word to the left, press <kbd>Ctrl</kbd>+<kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="7f4eb-116">Чтобы переместить курсор на один символ вправо, нажмите <kbd>стрелку вправо</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-116">To move the cursor one character to the right, press the <kbd>Right arrow</kbd>.</span></span>

<span data-ttu-id="7f4eb-117">Чтобы переместить курсор на одно слово вправо, нажмите клавишу <kbd>CTRL</kbd> + <kbd>стрелка вправо</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-117">To move the cursor one word to the right, press <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.</span></span>

### <a name="move-to-a-lines-beginning-or-end"></a><span data-ttu-id="7f4eb-118">Перейти к началу или концу строки</span><span class="sxs-lookup"><span data-stu-id="7f4eb-118">Move to a line's beginning or end</span></span>

<span data-ttu-id="7f4eb-119">Чтобы перейти к началу строки, нажмите клавишу <kbd>Home</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-119">To move to the beginning of a line, press <kbd>Home</kbd>.</span></span>

<span data-ttu-id="7f4eb-120">Чтобы перейти к концу строки, нажмите клавишу <kbd>End</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-120">To move to the end of a line, press <kbd>End</kbd>.</span></span>

<span data-ttu-id="7f4eb-121">Если строки были добавлены, дважды нажмите клавишу <kbd>Home</kbd> или <kbd>End</kbd> , чтобы перейти к началу или концу строк.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-121">If lines were added, press <kbd>Home</kbd> or <kbd>End</kbd> twice to move to the beginning or end of the lines.</span></span>

### <a name="delete-characters"></a><span data-ttu-id="7f4eb-122">Удалить символы</span><span class="sxs-lookup"><span data-stu-id="7f4eb-122">Delete characters</span></span>

<span data-ttu-id="7f4eb-123">Чтобы удалить символ, расположенный за положением курсора, нажмите клавишу <kbd>Backspace</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-123">To delete the character behind the cursor's position, press <kbd>Backspace</kbd>.</span></span>

<span data-ttu-id="7f4eb-124">Чтобы удалить символ в позиции курсора, нажмите клавишу <kbd>Delete</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-124">To delete the character at the cursor's position, press <kbd>Delete</kbd>.</span></span>

### <a name="delete-characters-from-a-line"></a><span data-ttu-id="7f4eb-125">Удалить символы из строки</span><span class="sxs-lookup"><span data-stu-id="7f4eb-125">Delete characters from a line</span></span>

<span data-ttu-id="7f4eb-126">Чтобы удалить все символы с позиции курсора до конца строки, нажмите клавишу <kbd>CTRL</kbd> + <kbd>End</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-126">To delete all the characters from the cursor's position to the end of a line, press <kbd>Ctrl</kbd>+<kbd>End</kbd>.</span></span>

<span data-ttu-id="7f4eb-127">Чтобы удалить все символы из позиции курсора в начало строки, нажмите <kbd>CTRL</kbd> + <kbd>Home</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-127">To delete all the characters from the cursor's position to the beginning of a line, press <kbd>Ctrl</kbd>+<kbd>Home</kbd>.</span></span>

<span data-ttu-id="7f4eb-128">Если были добавлены строки, то символы удаляются из текущей строки и добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-128">If lines were added, characters are deleted from the current line and the lines that were added.</span></span>

### <a name="insert-and-overstrike-mode"></a><span data-ttu-id="7f4eb-129">Режим вставки и замены</span><span class="sxs-lookup"><span data-stu-id="7f4eb-129">Insert and overstrike mode</span></span>

<span data-ttu-id="7f4eb-130">Чтобы изменить режим перезаписи, нажмите клавишу <kbd>INSERT</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f4eb-130">To change to overwrite mode, press <kbd>Insert</kbd>.</span></span> <span data-ttu-id="7f4eb-131">Чтобы вернуться в режим вставки, еще раз нажмите клавишу <kbd>INSERT</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7f4eb-131">To return to insert mode, press <kbd>Insert</kbd> again.</span></span>

### <a name="tab-completion"></a><span data-ttu-id="7f4eb-132">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="7f4eb-132">Tab completion</span></span>

<span data-ttu-id="7f4eb-133">Чтобы завершить имя командлета, параметр или путь, нажмите клавишу <kbd>Tab</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7f4eb-133">To complete a cmdlet name, a parameter, or a path, press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="7f4eb-134">Чтобы прокрутить список значений, снова нажмите клавишу <kbd>Tab</kbd> .</span><span class="sxs-lookup"><span data-stu-id="7f4eb-134">To scroll through a list of values, press the <kbd>Tab</kbd> key again.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f4eb-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7f4eb-135">See also</span></span>

[<span data-ttu-id="7f4eb-136">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="7f4eb-136">about_Command_Syntax</span></span>](about_Command_Syntax.md)

[<span data-ttu-id="7f4eb-137">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="7f4eb-137">about_Path_Syntax</span></span>](about_Path_Syntax.md)

[<span data-ttu-id="7f4eb-138">about_PSReadline</span><span class="sxs-lookup"><span data-stu-id="7f4eb-138">about_PSReadline</span></span>](../../PSReadline/About/about_PSReadline.md)


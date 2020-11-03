---
description: Описание процесса изменения команд в командной строке PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: d4b525e4c3f461b799c3bef157e04e0763a0b9c6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231766"
---
# <a name="about-line-editing"></a>О редактировании строк

## <a name="short-description"></a>Краткое описание

Описание процесса изменения команд в командной строке PowerShell.

## <a name="long-description"></a>Подробное описание

Консоль PowerShell имеет несколько полезных сочетаний клавиш, с помощью которых можно изменять команды в командной строке PowerShell.

### <a name="add-a-line"></a>Добавление линии

Чтобы добавить линию, нажмите клавишу <kbd>SHIFT</kbd> + <kbd>Ввод</kbd>.

Можно добавить несколько строк. Каждая дополнительная строка начинается с `>>` строки продолжения. Нажмите клавишу <kbd>Ввод</kbd> , чтобы выполнить команду.

### <a name="move-left-and-right"></a>Переместить влево и вправо

Чтобы переместить курсор на один символ влево, нажмите клавишу <kbd>стрелка влево</kbd>.

Чтобы переместить курсор на одно слово влево, нажмите клавиши <kbd>CTRL</kbd> + <kbd>стрелка влево</kbd>.

Чтобы переместить курсор на один символ вправо, нажмите <kbd>стрелку вправо</kbd>.

Чтобы переместить курсор на одно слово вправо, нажмите клавишу <kbd>CTRL</kbd> + <kbd>стрелка вправо</kbd>.

### <a name="move-to-a-lines-beginning-or-end"></a>Перейти к началу или концу строки

Чтобы перейти к началу строки, нажмите клавишу <kbd>Home</kbd>.

Чтобы перейти к концу строки, нажмите клавишу <kbd>End</kbd>.

Если строки были добавлены, дважды нажмите клавишу <kbd>Home</kbd> или <kbd>End</kbd> , чтобы перейти к началу или концу строк.

### <a name="delete-characters"></a>Удалить символы

Чтобы удалить символ, расположенный за положением курсора, нажмите клавишу <kbd>Backspace</kbd>.

Чтобы удалить символ в позиции курсора, нажмите клавишу <kbd>Delete</kbd>.

### <a name="delete-characters-from-a-line"></a>Удалить символы из строки

Чтобы удалить все символы с позиции курсора до конца строки, нажмите клавишу <kbd>CTRL</kbd> + <kbd>End</kbd>.

Чтобы удалить все символы из позиции курсора в начало строки, нажмите <kbd>CTRL</kbd> + <kbd>Home</kbd>.

Если были добавлены строки, то символы удаляются из текущей строки и добавленных строк.

### <a name="insert-and-overstrike-mode"></a>Режим вставки и замены

Чтобы изменить режим перезаписи, нажмите клавишу <kbd>INSERT</kbd>. Чтобы вернуться в режим вставки, еще раз нажмите клавишу <kbd>INSERT</kbd> .

### <a name="tab-completion"></a>Заполнение нажатием клавиши TAB

Чтобы завершить имя командлета, параметр или путь, нажмите клавишу <kbd>Tab</kbd> . Чтобы прокрутить список значений, снова нажмите клавишу <kbd>Tab</kbd> .

## <a name="see-also"></a>См. также статью

[about_Command_Syntax](about_Command_Syntax.md)

[about_Path_Syntax](about_Path_Syntax.md)

[about_PSReadline](../../PSReadline/About/about_PSReadline.md)

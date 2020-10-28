---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Приложение 2. Создание настраиваемого ярлыка PowerShell
description: Следующая процедура описывает создание ярлыка для Windows PowerShell, в котором уже заданы нужные параметры.
ms.openlocfilehash: abdab517dec1357050bf431b6f2e35311ad49976
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500731"
---
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a><span data-ttu-id="b323b-104">Приложение 2. Создание настраиваемого ярлыка PowerShell</span><span class="sxs-lookup"><span data-stu-id="b323b-104">Appendix 2 - Creating a Custom PowerShell Shortcut</span></span>

<span data-ttu-id="b323b-105">Следующая процедура описывает создание ярлыка для Windows PowerShell, в котором уже заданы нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="b323b-105">The following procedure describes how to create a shortcut to Windows PowerShell that has several convenient options customized.</span></span>

1. <span data-ttu-id="b323b-106">Создайте ярлык, указывающий на Powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="b323b-106">Create a shortcut that points to Powershell.exe.</span></span>

1. <span data-ttu-id="b323b-107">Щелкните его правой кнопкой мыши и выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="b323b-107">Right-click the shortcut, and then click **Properties** .</span></span>

1. <span data-ttu-id="b323b-108">Откройте вкладку **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="b323b-108">Click the **Options** tab.</span></span>

1. <span data-ttu-id="b323b-109">В разделе **Правка** установите флажок **Для выделения** .</span><span class="sxs-lookup"><span data-stu-id="b323b-109">In the **Edit Options** section, select the **QuickEdit** check box.</span></span>

    <span data-ttu-id="b323b-110">Этот параметр позволяет выбрать текст в окне консоли Windows PowerShell, перетащив курсор при нажатой левой кнопке мыши, а также скопировать текст в буфер обмена, нажав клавишу ВВОД или правую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="b323b-110">This setting lets you select text in the Windows PowerShell console window by dragging the left  mouse button, and it lets you copy text to the clipboard by pressing ENTER or by right-clicking  the mouse.</span></span>

1. <span data-ttu-id="b323b-111">В разделе **Правка** установите флажок **Быстрая вставка** .</span><span class="sxs-lookup"><span data-stu-id="b323b-111">In the **Edit Options** section, select the **Insert Mode** check box.</span></span> <span data-ttu-id="b323b-112">Этот параметр позволяет автоматически вставить текст из буфера обмена с помощью щелчка правой кнопкой мыши в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="b323b-112">This setting lets you right-click in the console window to automatically paste text from the clipboard.</span></span>

1. <span data-ttu-id="b323b-113">В поле **Размер буфера** раздела **Запоминание команд** введите или выберите число от 1 до 999.</span><span class="sxs-lookup"><span data-stu-id="b323b-113">In the **Command History** section, type or select a number between 1 and 999 in the **Buffer Size** box.</span></span> <span data-ttu-id="b323b-114">Это задает число введенных команд, которые сохраняются в буфере консоли.</span><span class="sxs-lookup"><span data-stu-id="b323b-114">This sets the number of typed commands that will be kept in the console buffer.</span></span>

1. <span data-ttu-id="b323b-115">В разделе **Запоминание команд** установите флажок **Отбрасывать повторения** , чтобы исключить повторяющиеся команды из буфера консоли.</span><span class="sxs-lookup"><span data-stu-id="b323b-115">In the **Command History** section, select the **Discard Old Duplicates** check box to eliminate repeated commands from the console buffer.</span></span>

1. <span data-ttu-id="b323b-116">Откройте вкладку **Расположение** .</span><span class="sxs-lookup"><span data-stu-id="b323b-116">Click the **Layout** tab.</span></span>

1. <span data-ttu-id="b323b-117">В поле **Высота** раздела **Screen Buffer** (Буфер экрана) введите число от 1 до 9999.</span><span class="sxs-lookup"><span data-stu-id="b323b-117">In the **Screen Buffer** section, type a number between 1 and 9999 in the **Height** box.</span></span> <span data-ttu-id="b323b-118">Высота обозначает число строк выходных данных, помещаемых в буфер.</span><span class="sxs-lookup"><span data-stu-id="b323b-118">The height represents the number of lines of output that are buffered.</span></span> <span data-ttu-id="b323b-119">Это максимальное число строк, сохраняемых для просмотра при прокрутке в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="b323b-119">This is the maximum number of lines retained for viewing when you scroll through the console window.</span></span> <span data-ttu-id="b323b-120">Если это число меньше высоты, отображаемой в разделе **Размер окна** , высота окна автоматически уменьшается до того же значения.</span><span class="sxs-lookup"><span data-stu-id="b323b-120">If this number is lower than the height shown in the **Window size** section, the window size height will automatically be reduced to the same value.</span></span>

1. <span data-ttu-id="b323b-121">В разделе **Размер окна** введите число от 1 до 9999 для ширины.</span><span class="sxs-lookup"><span data-stu-id="b323b-121">In the **Window Size** section, type a number between 1 and 9999 for the width.</span></span> <span data-ttu-id="b323b-122">Оно представляет число символов, отображаемых в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="b323b-122">This represents the number of characters that are displayed across the console window.</span></span> <span data-ttu-id="b323b-123">По умолчанию ширина равна 80, и именно на нее рассчитано форматирование выходных данных Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b323b-123">The default width is 80, and Windows PowerShell's output formatting is designed for this width.</span></span>

1. <span data-ttu-id="b323b-124">Если вы хотите, чтобы при открытии консоль располагалась в определенной точке на рабочем столе, снимите флажок **Автоматический выбор** в разделе **Положение окна** , а затем измените значения в полях **Слева** и **Сверху** раздела **Положение окна** .</span><span class="sxs-lookup"><span data-stu-id="b323b-124">If you want to place the console at a particular point on the desktop when it is opened, clear  the **Let system position window** check box in the **Window position** section, and then change  the values in the **Left** and **Top** boxes in the **Window position** section.</span></span>

1. <span data-ttu-id="b323b-125">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="b323b-125">Click **OK** .</span></span>

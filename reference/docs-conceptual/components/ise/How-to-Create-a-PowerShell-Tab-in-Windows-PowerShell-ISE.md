---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Создание вкладки PowerShell в интегрированной среде сценариев Windows PowerShell
ms.assetid: c10c18c7-9ece-4fd0-83dc-a19c53d4fd83
ms.openlocfilehash: 080fe89bf1443f51460589b445431913fa20b4b8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057746"
---
# <a name="how-to-create-a-powershell-tab-in-windows-powershell-ise"></a><span data-ttu-id="44f33-103">Создание вкладки PowerShell в интегрированной среде сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-103">How to Create a PowerShell Tab in Windows PowerShell ISE</span></span>

<span data-ttu-id="44f33-104">Вкладки в интегрированной среде сценариев (ISE) Windows PowerShell позволяют одновременно создавать и использовать несколько сред выполнения внутри одного приложения.</span><span class="sxs-lookup"><span data-stu-id="44f33-104">Tabs in the Windows PowerShell Integrated Scripting Environment (ISE) allow you to simultaneously create and use several execution environments within the same application.</span></span>
<span data-ttu-id="44f33-105">Каждая вкладка PowerShell соответствует отдельной среде выполнения или отдельному сеансу.</span><span class="sxs-lookup"><span data-stu-id="44f33-105">Each PowerShell tab corresponds to a separate execution environment or session.</span></span>

> [!NOTE]
> <span data-ttu-id="44f33-106">Переменные, функции и псевдонимы, созданные на одной вкладке, на другую не переносятся.</span><span class="sxs-lookup"><span data-stu-id="44f33-106">Variables, functions, and aliases that you create in one tab do not carry over to another.</span></span> <span data-ttu-id="44f33-107">Это разные сеансы Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f33-107">They are different Windows PowerShell sessions.</span></span>

<span data-ttu-id="44f33-108">Выполните следующие действия, чтобы открыть или закрыть вкладку в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f33-108">Use the following steps to open or close a tab in Windows PowerShell.</span></span>
<span data-ttu-id="44f33-109">Чтобы переименовать вкладку, задайте свойство [DisplayName](object-model/The-PowerShellTab-Object.md#displayname) для объекта сценария на вкладке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f33-109">To rename a tab, set the [DisplayName](object-model/The-PowerShellTab-Object.md#displayname) property on the Windows PowerShell Tab scripting object.</span></span>

## <a name="to-create-and-use-a-new-powershell-tab"></a><span data-ttu-id="44f33-110">Создание и использование вкладки PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-110">To create and use a new PowerShell Tab</span></span>

<span data-ttu-id="44f33-111">В меню **Файл** щелкните элемент **Создать вкладку PowerShell**. Новая вкладка PowerShell всегда открывается в виде активного окна.</span><span class="sxs-lookup"><span data-stu-id="44f33-111">On the **File** menu, click **New PowerShell Tab**. The new PowerShell tab always opens as the active window.</span></span>
<span data-ttu-id="44f33-112">Вкладки PowerShell нумеруются последовательно в порядке их открытия.</span><span class="sxs-lookup"><span data-stu-id="44f33-112">PowerShell tabs are incrementally numbered in the order that they are opened.</span></span>
<span data-ttu-id="44f33-113">Каждая вкладка связана с собственным окном консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44f33-113">Each tab is associated with its own Windows PowerShell console window.</span></span>
<span data-ttu-id="44f33-114">Одновременно можно открыть до 32 вкладок PowerShell со своим сеансом (в интегрированной среде сценариев Windows PowerShell 2.0 это ограничение равно 8).</span><span class="sxs-lookup"><span data-stu-id="44f33-114">You can have up to 32 PowerShell tabs with their own session open at a time (this is limited to 8 on Windows PowerShell ISE 2.0.)</span></span>

<span data-ttu-id="44f33-115">Обратите внимание, что нажатие значка **Создать** или **Открыть** не приводит к созданию вкладки с отдельным сеансом.</span><span class="sxs-lookup"><span data-stu-id="44f33-115">Note that clicking the **New** or **Open** icons on the toolbar does not create a new tab with a separate session.</span></span>
<span data-ttu-id="44f33-116">Эти кнопки открывают новый или существующий файл сценария на активной вкладке с сеансом.</span><span class="sxs-lookup"><span data-stu-id="44f33-116">Instead, those buttons open a new or existing script file on the currently active tab with a session.</span></span>
<span data-ttu-id="44f33-117">Для каждой вкладки и сеанса можно открыть несколько файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="44f33-117">You can have multiple script files open with each tab and session.</span></span>
<span data-ttu-id="44f33-118">Вкладки сценариев для сеанса отображаются под вкладками сеанса, только когда соответствующий сеанс активен.</span><span class="sxs-lookup"><span data-stu-id="44f33-118">The script tabs for a session only appear below the session tabs when the associated session is active.</span></span>

<span data-ttu-id="44f33-119">Чтобы сделать вкладку PowerShell активной, щелкните ее. Чтобы выбрать одну из всех открытых вкладок PowerShell, щелкните ее в меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="44f33-119">To make a PowerShell tab active, click the tab. To select from all PowerShell tabs that are open, on the **View** menu, click the PowerShell tab you want to use.</span></span>

## <a name="to-create-and-use-a-new-remote-powershell-tab"></a><span data-ttu-id="44f33-120">Создание и использование вкладки удаленного использования PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-120">To create and use a new Remote PowerShell tab</span></span>

<span data-ttu-id="44f33-121">В меню **Файл** щелкните **Создание вкладки удаленного использования PowerShell** для создания сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f33-121">On the **File** menu, click **New Remote PowerShell Tab** to establish a session on a remote computer.</span></span>
<span data-ttu-id="44f33-122">Отображается диалоговое окно, предлагающее ввести сведения для установки удаленного подключения.</span><span class="sxs-lookup"><span data-stu-id="44f33-122">A dialog box appears and prompts you to enter details required to establish the remote connection.</span></span>
<span data-ttu-id="44f33-123">Удаленная вкладка PowerShell работает так же, как и локальная, только команды и сценарии выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="44f33-123">The remote tab functions just like a local PowerShell tab, but the commands and scripts are run on the remote computer.</span></span>

## <a name="to-close-a-powershell-tab"></a><span data-ttu-id="44f33-124">Закрытие вкладки PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-124">To close a PowerShell Tab</span></span>

<span data-ttu-id="44f33-125">Чтобы закрыть вкладку, можно использовать любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="44f33-125">To close a tab, you can use any of the following techniques:</span></span>

- <span data-ttu-id="44f33-126">Щелкните вкладку, которую требуется закрыть.</span><span class="sxs-lookup"><span data-stu-id="44f33-126">Click the tab that you want to close.</span></span>

- <span data-ttu-id="44f33-127">В меню **Файл** щелкните **Закрыть вкладку PowerShell** или нажмите кнопку "Закрыть" (**X**) на активной вкладке для ее закрытия.</span><span class="sxs-lookup"><span data-stu-id="44f33-127">On the **File** menu, click **Close PowerShell Tab**, or click  the Close button  (**X**) on an active tab to close the tab.</span></span>

<span data-ttu-id="44f33-128">Если на закрываемой вкладке PowerShell имеются несохраненные файлы, вам будет предложено сохранить их или отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="44f33-128">If you have unsaved files open in the PowerShell tab that you are closing, you are prompted to save or discard them.</span></span>
<span data-ttu-id="44f33-129">Дополнительные сведения о сохранении сценария см. в статье [Сохранение скрипта](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md#how-to-save-a-script).</span><span class="sxs-lookup"><span data-stu-id="44f33-129">For more information about how to save a script, see [How to Save a Script](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md#how-to-save-a-script).</span></span>

## <a name="see-also"></a><span data-ttu-id="44f33-130">См. также</span><span class="sxs-lookup"><span data-stu-id="44f33-130">See Also</span></span>

- [<span data-ttu-id="44f33-131">Введение в интегрированную среду сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-131">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
- [<span data-ttu-id="44f33-132">Использование области консоли в интегрированной среде сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f33-132">How to Use the Console Pane in the Windows PowerShell ISE</span></span>](How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)
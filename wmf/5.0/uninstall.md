---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 64a29aa87507e65a182837df538c5e695c420cb3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="f72f3-102">Инструкции по удалению</span><span class="sxs-lookup"><span data-stu-id="f72f3-102">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="f72f3-103">Использование командной строки</span><span class="sxs-lookup"><span data-stu-id="f72f3-103">Using Command Prompt</span></span>
1.  <span data-ttu-id="f72f3-104">Откройте окно **Командная строка**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-104">Open **Command Prompt.**</span></span>
2.  <span data-ttu-id="f72f3-105">Запустите [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) (Автономное средство запуска Центра обновления Windows), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="f72f3-105">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="f72f3-106">В Windows Server 2012 R2 и Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="f72f3-106">On Windows Server 2012 R2 and Windows 8.1:</span></span>
```powershell
wusa /uninstall /kb:3134758
```
<span data-ttu-id="f72f3-107">В Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="f72f3-107">On Windows Server 2012:</span></span>
```powershell
wusa /uninstall /kb:3134759
```
<span data-ttu-id="f72f3-108">В Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1):</span><span class="sxs-lookup"><span data-stu-id="f72f3-108">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>
```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="f72f3-109">Использование панели управления</span><span class="sxs-lookup"><span data-stu-id="f72f3-109">Using Control Panel</span></span>
1.  <span data-ttu-id="f72f3-110">Откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-110">Open **Control Panel.**</span></span>
2.  <span data-ttu-id="f72f3-111">Откройте **Программы** и выберите **Удаление программы**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-111">Open **Programs**, then open **Uninstall a program.**</span></span>
3.  <span data-ttu-id="f72f3-112">Щелкните **Просмотр установленных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-112">Click **View installed updates.**</span></span>
4.  <span data-ttu-id="f72f3-113">Выберите **Windows Management Framework 5.0** в списке установленных обновлений.</span><span class="sxs-lookup"><span data-stu-id="f72f3-113">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="f72f3-114">Это соответствует *KB3134758*, *KB3134759* или *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="f72f3-114">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="f72f3-115">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-115">Click **Uninstall.**</span></span>

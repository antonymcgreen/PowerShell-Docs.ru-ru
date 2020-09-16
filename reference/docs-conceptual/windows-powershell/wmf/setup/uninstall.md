---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Удаление WMF 5.0
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236311"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="947c4-103">Инструкции по удалению</span><span class="sxs-lookup"><span data-stu-id="947c4-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="947c4-104">Использование командной строки</span><span class="sxs-lookup"><span data-stu-id="947c4-104">Using Command Prompt</span></span>

1. <span data-ttu-id="947c4-105">Откройте **командную строку**.</span><span class="sxs-lookup"><span data-stu-id="947c4-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="947c4-106">Запустите [Автономное средство запуска Центра обновления Windows](https://support.microsoft.com/kb/934307), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="947c4-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="947c4-107">В Windows Server 2012 R2 и Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="947c4-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="947c4-108">В Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="947c4-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="947c4-109">В Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1):</span><span class="sxs-lookup"><span data-stu-id="947c4-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="947c4-110">Использование панели управления</span><span class="sxs-lookup"><span data-stu-id="947c4-110">Using Control Panel</span></span>

1. <span data-ttu-id="947c4-111">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="947c4-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="947c4-112">Откройте раздел **Программы** и выберите **Удаление программы**.</span><span class="sxs-lookup"><span data-stu-id="947c4-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="947c4-113">Щелкните **Просмотр установленных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="947c4-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="947c4-114">Выберите **Windows Management Framework 5.0** в списке установленных обновлений.</span><span class="sxs-lookup"><span data-stu-id="947c4-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="947c4-115">Это соответствует *KB3134758*, *KB3134759* или *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="947c4-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="947c4-116">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="947c4-116">Click **Uninstall.**</span></span>

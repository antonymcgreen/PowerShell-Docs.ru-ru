---
ms.date: 06/12/2017
title: Удаление WMF 5.0
description: В этой статье описывается, как удалить WMF из старых версий Windows.
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660804"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="d93d8-103">Инструкции по удалению</span><span class="sxs-lookup"><span data-stu-id="d93d8-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="d93d8-104">Использование командной строки</span><span class="sxs-lookup"><span data-stu-id="d93d8-104">Using Command Prompt</span></span>

1. <span data-ttu-id="d93d8-105">Откройте **командную строку**.</span><span class="sxs-lookup"><span data-stu-id="d93d8-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="d93d8-106">Запустите [Автономное средство запуска Центра обновления Windows](https://support.microsoft.com/kb/934307), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d93d8-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="d93d8-107">В Windows Server 2012 R2 и Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="d93d8-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="d93d8-108">В Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="d93d8-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="d93d8-109">В Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1):</span><span class="sxs-lookup"><span data-stu-id="d93d8-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="d93d8-110">Использование панели управления</span><span class="sxs-lookup"><span data-stu-id="d93d8-110">Using Control Panel</span></span>

1. <span data-ttu-id="d93d8-111">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="d93d8-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="d93d8-112">Откройте раздел **Программы** и выберите **Удаление программы**.</span><span class="sxs-lookup"><span data-stu-id="d93d8-112">Open **Programs** , then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="d93d8-113">Щелкните **Просмотр установленных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="d93d8-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="d93d8-114">Выберите **Windows Management Framework 5.0** в списке установленных обновлений.</span><span class="sxs-lookup"><span data-stu-id="d93d8-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="d93d8-115">Это соответствует *KB3134758* , *KB3134759* или *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="d93d8-115">This corresponds to *KB3134758* , *KB3134759* , or *KB3134760*.</span></span> <span data-ttu-id="d93d8-116">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d93d8-116">Click **Uninstall.**</span></span>

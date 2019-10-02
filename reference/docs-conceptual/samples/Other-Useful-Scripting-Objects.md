---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Другие полезные объекты для сценариев
ms.openlocfilehash: 4f236246714b0608658bbd535851489912430336
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325145"
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="fe0eb-103">Другие полезные объекты для сценариев</span><span class="sxs-lookup"><span data-stu-id="fe0eb-103">Other Useful Scripting Objects</span></span>

<span data-ttu-id="fe0eb-104">Следующие объекты предоставляют дополнительные возможности создания сценариев в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-104">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="fe0eb-105">Они не являются частью иерархии **$psISE**.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-105">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="fe0eb-106">Полезные объекты для сценариев</span><span class="sxs-lookup"><span data-stu-id="fe0eb-106">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="fe0eb-107">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="fe0eb-107">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="fe0eb-108">Существуют некоторые ограничения, применяемые к взаимодействию интегрированной среды сценариев Windows PowerShell с консольными приложениями.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-108">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="fe0eb-109">Команда или сценарий автоматизации, требующие участия пользователя, могут не работать так, как при запуске из консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-109">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="fe0eb-110">Может потребоваться заблокировать запуск этих команд или сценариев в области команд интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-110">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="fe0eb-111">Объект **$PsUnsupportedConsoleApplications** хранит список таких команд.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-111">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="fe0eb-112">При попытке выполнить команды, указанные в этом списке, вы получите сообщение о том, что они не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-112">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="fe0eb-113">Следующий сценарий добавляет запись в этот список.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-113">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="fe0eb-114">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="fe0eb-114">$psLocalHelp</span></span>

<span data-ttu-id="fe0eb-115">Это объект словаря, который поддерживает сопоставление с учетом контекста разделов справки и связанных ссылок в локальном скомпилированном файле справки HTML.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-115">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="fe0eb-116">Он используется для поиска локальной справки для определенного раздела.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-116">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="fe0eb-117">Разделы в этом списке можно добавлять и удалять.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-117">You can add or delete topics from this list.</span></span> <span data-ttu-id="fe0eb-118">В следующем примере кода показаны некоторые примеры пар "ключ —значение", которые содержатся в объекте `$psLocalHelp`.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-118">The following code example shows some example key-value pairs that are contained in `$psLocalHelp`.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

```output
Key   : Add-Computer
Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm

Key   : Add-Content
Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm
```

<span data-ttu-id="fe0eb-119">Следующий сценарий добавляет запись в этот список.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-119">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="fe0eb-120">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="fe0eb-120">$psOnlineHelp</span></span>

<span data-ttu-id="fe0eb-121">Это объект словаря, который поддерживает сопоставление с учетом контекста заголовков разделов справки и связанных внешних URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-121">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="fe0eb-122">Он используется для поиска справки для определенного раздела в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-122">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="fe0eb-123">Разделы в этом списке можно добавлять и удалять.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-123">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

```output
Key   : Add-Computer
Value : https://go.microsoft.com/fwlink/p/?LinkID=135194

Key   : Add-Content
Value : https://go.microsoft.com/fwlink/p/?LinkID=113278
```

<span data-ttu-id="fe0eb-124">Следующий сценарий добавляет запись в этот список.</span><span class="sxs-lookup"><span data-stu-id="fe0eb-124">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "https://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="fe0eb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fe0eb-125">See Also</span></span>

[<span data-ttu-id="fe0eb-126">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe0eb-126">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)

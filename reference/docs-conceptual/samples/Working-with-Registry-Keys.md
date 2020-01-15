---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Работа с разделами реестра
ms.openlocfilehash: 3feaf6d26db51a507434a6cec1f1095c9013efc8
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736851"
---
# <a name="working-with-registry-keys"></a><span data-ttu-id="b28b0-103">Работа с разделами реестра</span><span class="sxs-lookup"><span data-stu-id="b28b0-103">Working with Registry Keys</span></span>

<span data-ttu-id="b28b0-104">Так как разделы реестра представляют собой элементы на дисках PowerShell, работа с ними очень похожа на работу с файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="b28b0-104">Because registry keys are items on PowerShell drives, working with them is very similar to working with files and folders.</span></span> <span data-ttu-id="b28b0-105">Одно важное различие заключается в том, что каждый элемент реестрового диска PowerShell представляет собой контейнер, как и папка на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="b28b0-105">One critical difference is that every item on a registry-based PowerShell drive is a container, just like a folder on a file system drive.</span></span> <span data-ttu-id="b28b0-106">Однако записи реестра и связанные с ними значения являются свойствами элементов, а не отдельными элементами.</span><span class="sxs-lookup"><span data-stu-id="b28b0-106">However, registry entries and their associated values are properties of the items, not distinct items.</span></span>

## <a name="listing-all-subkeys-of-a-registry-key"></a><span data-ttu-id="b28b0-107">Получение всех подразделов раздела реестра</span><span class="sxs-lookup"><span data-stu-id="b28b0-107">Listing All Subkeys of a Registry Key</span></span>

<span data-ttu-id="b28b0-108">Показать все элементы, непосредственно содержащиеся в разделе реестра, можно с помощью командлета `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-108">You can show all items directly within a registry key by using `Get-ChildItem`.</span></span> <span data-ttu-id="b28b0-109">Для отображения скрытых и системных элементов добавьте необязательный параметр **Force**.</span><span class="sxs-lookup"><span data-stu-id="b28b0-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="b28b0-110">Например, эта команда отображает элементы, непосредственно расположенные на диске `HKCU:` PowerShell, который соответствует кусту реестра `HKEY_CURRENT_USER`:</span><span class="sxs-lookup"><span data-stu-id="b28b0-110">For example, this command displays the items directly within PowerShell drive `HKCU:`, which corresponds to the `HKEY_CURRENT_USER` registry hive:</span></span>

```powershell
Get-ChildItem -Path HKCU:\ | Select-Object Name
```

```Output
   Hive: Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER

Name
----
HKEY_CURRENT_USER\AppEvents
HKEY_CURRENT_USER\Console
HKEY_CURRENT_USER\Control Panel
HKEY_CURRENT_USER\DirectShow
HKEY_CURRENT_USER\dummy
HKEY_CURRENT_USER\Environment
HKEY_CURRENT_USER\EUDC
HKEY_CURRENT_USER\Keyboard Layout
HKEY_CURRENT_USER\MediaFoundation
HKEY_CURRENT_USER\Microsoft
HKEY_CURRENT_USER\Network
HKEY_CURRENT_USER\Printers
HKEY_CURRENT_USER\Software
HKEY_CURRENT_USER\System
HKEY_CURRENT_USER\Uninstall
HKEY_CURRENT_USER\WXP
HKEY_CURRENT_USER\Volatile Environment
```

<span data-ttu-id="b28b0-111">Это разделы верхнего уровня, отображаемые внутри `HKEY_CURRENT_USER` в редакторе реестра (Regedit.exe).</span><span class="sxs-lookup"><span data-stu-id="b28b0-111">These are the top-level keys visible under `HKEY_CURRENT_USER` in the Registry Editor (Regedit.exe).</span></span>

<span data-ttu-id="b28b0-112">Указать этот путь в реестре можно также, задав имя поставщика реестра с последующей строкой `::`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-112">You can also specify this registry path by specifying the registry provider's name, followed by `::`.</span></span> <span data-ttu-id="b28b0-113">Полное имя поставщика реестра имеет вид `Microsoft.PowerShell.Core\Registry`, но может быть сокращено до `Registry`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-113">The registry provider's full name is `Microsoft.PowerShell.Core\Registry`, but this can be shortened to just `Registry`.</span></span> <span data-ttu-id="b28b0-114">Любая из следующих команд выводит содержимое элементов, непосредственно расположенных внутри `HKCU:`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-114">Any of the following commands will list the contents directly under `HKCU:`.</span></span>

```powershell
Get-ChildItem -Path Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Registry::HKCU
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKCU
Get-ChildItem HKCU:
```

<span data-ttu-id="b28b0-115">Эти команды выводят только элементы, содержащиеся на диске непосредственно, так же как и команда `DIR` оболочки **Cmd.exe** или команда `ls` оболочки UNIX.</span><span class="sxs-lookup"><span data-stu-id="b28b0-115">These commands list only the directly contained items, much like using `DIR` in **Cmd.exe** or `ls` in a UNIX shell.</span></span> <span data-ttu-id="b28b0-116">Для показа вложенных элементов необходимо указать параметр **Recurse**.</span><span class="sxs-lookup"><span data-stu-id="b28b0-116">To show contained items, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="b28b0-117">Для вывода всех разделов реестра в `HKCU:` используется приведенная ниже команда.</span><span class="sxs-lookup"><span data-stu-id="b28b0-117">To list all registry keys in `HKCU:`, use the following command.</span></span>

```powershell
Get-ChildItem -Path HKCU:\ -Recurse
```

<span data-ttu-id="b28b0-118">Командлет `Get-ChildItem` позволяет выполнять сложные операции фильтрации с помощью параметров **Path**, **Filter**, **Include** и **Exclude**, но обычно осуществляется лишь фильтрация по имени.</span><span class="sxs-lookup"><span data-stu-id="b28b0-118">`Get-ChildItem` can perform complex filtering capabilities through its **Path**, **Filter**, **Include**, and **Exclude** parameters, but those parameters are typically based only on name.</span></span> <span data-ttu-id="b28b0-119">Сложную фильтрацию на основе других свойств элементов можно выполнить с помощью командлета `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-119">You can perform complex filtering based on other properties of items by using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="b28b0-120">Следующая команда находит все разделы в `HKCU:\Software`, у которых не более одного подраздела и ровно четыре значения:</span><span class="sxs-lookup"><span data-stu-id="b28b0-120">The following command finds all keys within `HKCU:\Software` that have no more than one subkey and also have exactly four values:</span></span>

```powershell
Get-ChildItem -Path HKCU:\Software -Recurse |
  Where-Object {($_.SubKeyCount -le 1) -and ($_.ValueCount -eq 4) }
```

## <a name="copying-keys"></a><span data-ttu-id="b28b0-121">Копирование разделов</span><span class="sxs-lookup"><span data-stu-id="b28b0-121">Copying Keys</span></span>

<span data-ttu-id="b28b0-122">Копирование выполняется с помощью командлета `Copy-Item`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-122">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="b28b0-123">Следующая команда копирует подраздел `CurrentVersion` из `HKLM:\SOFTWARE\Microsoft\Windows\` и все его свойства в `HKCU:\`.</span><span class="sxs-lookup"><span data-stu-id="b28b0-123">The following example copies the `CurrentVersion` subkey of `HKLM:\SOFTWARE\Microsoft\Windows\` and all of its properties to `HKCU:\`.</span></span>

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU:
```

<span data-ttu-id="b28b0-124">Если изучить этот новый раздел в редакторе реестра или с помощью командлета `Get-ChildItem`, вы увидите, что в новом расположении отсутствуют копии подразделов, содержавшихся в исходном разделе.</span><span class="sxs-lookup"><span data-stu-id="b28b0-124">If you examine this new key in the registry editor or by using `Get-ChildItem`, you notice that you do not have copies of the contained subkeys in the new location.</span></span> <span data-ttu-id="b28b0-125">Чтобы скопировать все содержимое контейнера, необходимо указать параметр **Recurse**.</span><span class="sxs-lookup"><span data-stu-id="b28b0-125">In order to copy all of the contents of a container, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="b28b0-126">Копирование в предыдущем примере можно сделать рекурсивным, если использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b28b0-126">To make the preceding copy command recursive, you would use this command:</span></span>

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU: -Recurse
```

<span data-ttu-id="b28b0-127">Для копирования файловой системы можно использовать и другие доступные средства.</span><span class="sxs-lookup"><span data-stu-id="b28b0-127">You can still use other tools you already have available to perform filesystem copies.</span></span> <span data-ttu-id="b28b0-128">В оболочке Windows PowerShell можно использовать любые средства для редактирования реестра (в том числе **reg.exe**, **regini.exe** и **regedit.exe**), а также COM-объекты, поддерживающие редактирование реестра (такие как **WScript.Shell** и WMI-класс **StdRegProv**).</span><span class="sxs-lookup"><span data-stu-id="b28b0-128">Any registry editing tools—including **reg.exe**, **regini.exe**, **regedit.exe**, and COM objects that support registry editing, such as **WScript.Shell** and WMI's **StdRegProv** class can be used from within Windows PowerShell.</span></span>

## <a name="creating-keys"></a><span data-ttu-id="b28b0-129">Создание разделов</span><span class="sxs-lookup"><span data-stu-id="b28b0-129">Creating Keys</span></span>

<span data-ttu-id="b28b0-130">Создание новых разделов в реестре проще, чем создание нового элемента в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="b28b0-130">Creating new keys in the registry is simpler than creating a new item in a file system.</span></span> <span data-ttu-id="b28b0-131">Поскольку все разделы реестра являются контейнерами, нет необходимости указывать тип элемента. Достаточно указать явный путь, например:</span><span class="sxs-lookup"><span data-stu-id="b28b0-131">Because all registry keys are containers, you do not need to specify the item type; you simply supply an explicit path, such as:</span></span>

```powershell
New-Item -Path HKCU:\Software_DeleteMe
```

<span data-ttu-id="b28b0-132">Для указания раздела можно также использовать путь на основе имени поставщика:</span><span class="sxs-lookup"><span data-stu-id="b28b0-132">You can also use a provider-based path to specify a key:</span></span>

```powershell
New-Item -Path Registry::HKCU\Software_DeleteMe
```

## <a name="deleting-keys"></a><span data-ttu-id="b28b0-133">Удаление разделов</span><span class="sxs-lookup"><span data-stu-id="b28b0-133">Deleting Keys</span></span>

<span data-ttu-id="b28b0-134">Удаление элементов в принципе осуществляется одинаково для всех поставщиков.</span><span class="sxs-lookup"><span data-stu-id="b28b0-134">Deleting items is essentially the same for all providers.</span></span> <span data-ttu-id="b28b0-135">Следующие команды удаляют элементы, не выводя никаких сообщений:</span><span class="sxs-lookup"><span data-stu-id="b28b0-135">The following commands will silently remove items:</span></span>

```powershell
Remove-Item -Path HKCU:\Software_DeleteMe
Remove-Item -Path 'HKCU:\key with spaces in the name'
```

## <a name="removing-all-keys-under-a-specific-key"></a><span data-ttu-id="b28b0-136">Удаление всех разделов внутри определенного раздела</span><span class="sxs-lookup"><span data-stu-id="b28b0-136">Removing All Keys Under a Specific Key</span></span>

<span data-ttu-id="b28b0-137">Удалить вложенные элементы можно с помощью командлета `Remove-Item`, однако он потребует подтверждения удаления, если элемент сам что-нибудь содержит.</span><span class="sxs-lookup"><span data-stu-id="b28b0-137">You can remove contained items by using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="b28b0-138">Например, при попытке удаления созданного нами подраздела `HKCU:\CurrentVersion` будет отображено следующее:</span><span class="sxs-lookup"><span data-stu-id="b28b0-138">For example, if we attempt to delete the `HKCU:\CurrentVersion` subkey we created, we see this:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion
```

```Output
Confirm
The item at HKCU:\CurrentVersion\AdminDebug has children and the -recurse
parameter was not specified. If you continue, all children will be removed with
the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="b28b0-139">Для удаления вложенных элементов без подтверждения следует указать параметр **Recurse**:</span><span class="sxs-lookup"><span data-stu-id="b28b0-139">To delete contained items without prompting, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion -Recurse
```

<span data-ttu-id="b28b0-140">Если нужно удалить все элементы в `HKCU:\CurrentVersion`, но не сам раздел `HKCU:\CurrentVersion`, вместо этого введите следующее:</span><span class="sxs-lookup"><span data-stu-id="b28b0-140">If you wanted to remove all items within `HKCU:\CurrentVersion` but not `HKCU:\CurrentVersion` itself, you could instead use:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion\* -Recurse
```

---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Расширение по клавише TAB
description: Описывается, как использовать функцию расширения по клавише TAB в PowerShell.
ms.openlocfilehash: 658cdf5ddf78bbd6dd431c2170cd5ff643e6bf95
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661347"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="497cf-104">Расширение по клавише TAB</span><span class="sxs-lookup"><span data-stu-id="497cf-104">Using Tab Expansion</span></span>

<span data-ttu-id="497cf-105">Оболочки командной строки часто позволяют автоматически завершать длинные имена файлов или команд, что ускоряет ввод и позволяет использовать подсказки.</span><span class="sxs-lookup"><span data-stu-id="497cf-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="497cf-106">PowerShell позволяет автоматически завершать имена файлов и командлетов, нажимая клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="497cf-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="497cf-107">Завершением по клавише TAB управляет внутренняя функция TabExpansion или TabExpansion2.</span><span class="sxs-lookup"><span data-stu-id="497cf-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="497cf-108">Так как ее можно изменить или переопределить, приведенные инструкции распространяются на стандартную конфигурацию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="497cf-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="497cf-109">Для автоматического завершения имени файла или пути из доступных вариантов введите часть имени и нажмите клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="497cf-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="497cf-110">PowerShell автоматически расширяет имя до первого совпадения.</span><span class="sxs-lookup"><span data-stu-id="497cf-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="497cf-111">Нажимая клавишу <kbd>TAB</kbd>, можно перебрать все варианты.</span><span class="sxs-lookup"><span data-stu-id="497cf-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="497cf-112">Расширение имен командлетов по клавише TAB происходит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="497cf-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="497cf-113">Чтобы использовать расширение по клавише TAB для имени командлета, введите всю первую часть имени (глагол) и дефис после нее.</span><span class="sxs-lookup"><span data-stu-id="497cf-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="497cf-114">Можно указать дополнительную часть имени для поиска частичного совпадения.</span><span class="sxs-lookup"><span data-stu-id="497cf-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="497cf-115">Например, если ввести `get-co` и нажать клавишу <kbd>TAB</kbd>, PowerShell автоматически расширит это до командлета `Get-Command` (обратите внимание, что это также приводит регистр букв к стандартной форме).</span><span class="sxs-lookup"><span data-stu-id="497cf-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="497cf-116">Если нажать клавишу <kbd>TAB</kbd> еще раз, PowerShell заменит результат на `Get-Content`, единственное другое подходящее имя командлета.</span><span class="sxs-lookup"><span data-stu-id="497cf-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="497cf-117">Начиная с PowerShell 7.0, с помощью клавиши <kbd>TAB</kbd> также можно развернуть сокращенные командлеты и функции.</span><span class="sxs-lookup"><span data-stu-id="497cf-117">As of PowerShell 7.0, <kbd>Tab</kbd> will also expand abbreviated cmdlets and functions.</span></span> <span data-ttu-id="497cf-118">Например, `i-psdf<tab>` возвращает `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="497cf-118">For example, `i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>

<span data-ttu-id="497cf-119">Расширение по клавише TAB можно использовать несколько раз в одной строке.</span><span class="sxs-lookup"><span data-stu-id="497cf-119">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="497cf-120">Например, вы можете использовать завершение по клавише TAB для имени командлета `Get-Content`:</span><span class="sxs-lookup"><span data-stu-id="497cf-120">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="497cf-121">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="497cf-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="497cf-122">После этого можно указать часть пути к файлу журнала активной установки и снова воспользоваться описанной функцией:</span><span class="sxs-lookup"><span data-stu-id="497cf-122">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="497cf-123">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="497cf-123">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="497cf-124">Единственным ограничением этого процесса является то, что символы табуляции принимаются за попытки завершения слова.</span><span class="sxs-lookup"><span data-stu-id="497cf-124">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="497cf-125">При копировании и вставке примеров команд в консоль PowerShell убедитесь, что пример не содержит символы табуляции. В противном случае результаты будут непредсказуемыми и почти наверняка будут отличаться от требуемых.</span><span class="sxs-lookup"><span data-stu-id="497cf-125">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>

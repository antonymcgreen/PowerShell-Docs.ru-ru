---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Расширение по клавише TAB
ms.openlocfilehash: d96cbf848f464aff29a7bed9b70d0b6a000aa808
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "67031009"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="38aa4-103">Расширение по клавише TAB</span><span class="sxs-lookup"><span data-stu-id="38aa4-103">Using Tab Expansion</span></span>

<span data-ttu-id="38aa4-104">Оболочки командной строки часто позволяют автоматически завершать длинные имена файлов или команд, что ускоряет ввод и позволяет использовать подсказки.</span><span class="sxs-lookup"><span data-stu-id="38aa4-104">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="38aa4-105">PowerShell позволяет автоматически завершать имена файлов и командлетов, нажимая клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="38aa4-105">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="38aa4-106">Завершением по клавише TAB управляет внутренняя функция TabExpansion или TabExpansion2.</span><span class="sxs-lookup"><span data-stu-id="38aa4-106">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="38aa4-107">Так как ее можно изменить или переопределить, приведенные инструкции распространяются на стандартную конфигурацию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38aa4-107">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="38aa4-108">Для автоматического завершения имени файла или пути из доступных вариантов введите часть имени и нажмите клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="38aa4-108">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="38aa4-109">PowerShell автоматически расширяет имя до первого совпадения.</span><span class="sxs-lookup"><span data-stu-id="38aa4-109">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="38aa4-110">Нажимая клавишу <kbd>TAB</kbd>, можно перебрать все варианты.</span><span class="sxs-lookup"><span data-stu-id="38aa4-110">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="38aa4-111">Расширение имен командлетов по клавише TAB происходит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="38aa4-111">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="38aa4-112">Чтобы использовать расширение по клавише TAB для имени командлета, введите всю первую часть имени (глагол) и дефис после нее.</span><span class="sxs-lookup"><span data-stu-id="38aa4-112">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="38aa4-113">Можно указать дополнительную часть имени для поиска частичного совпадения.</span><span class="sxs-lookup"><span data-stu-id="38aa4-113">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="38aa4-114">Например, если ввести `get-co` и нажать клавишу <kbd>TAB</kbd>, PowerShell автоматически расширит это до командлета `Get-Command` (обратите внимание, что это также приводит регистр букв к стандартной форме).</span><span class="sxs-lookup"><span data-stu-id="38aa4-114">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="38aa4-115">Если нажать клавишу <kbd>TAB</kbd> еще раз, PowerShell заменит результат на `Get-Content`, единственное другое подходящее имя командлета.</span><span class="sxs-lookup"><span data-stu-id="38aa4-115">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="38aa4-116">Расширение по клавише TAB можно использовать несколько раз в одной строке.</span><span class="sxs-lookup"><span data-stu-id="38aa4-116">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="38aa4-117">Например, вы можете использовать завершение по клавише TAB для имени командлета `Get-Content`:</span><span class="sxs-lookup"><span data-stu-id="38aa4-117">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="38aa4-118">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="38aa4-118">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="38aa4-119">После этого можно указать часть пути к файлу журнала активной установки и снова воспользоваться описанной функцией:</span><span class="sxs-lookup"><span data-stu-id="38aa4-119">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="38aa4-120">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="38aa4-120">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="38aa4-121">Единственным ограничением этого процесса является то, что символы табуляции принимаются за попытки завершения слова.</span><span class="sxs-lookup"><span data-stu-id="38aa4-121">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="38aa4-122">При копировании и вставке примеров команд в консоль PowerShell убедитесь, что пример не содержит символы табуляции. В противном случае результаты будут непредсказуемыми и почти наверняка будут отличаться от требуемых.</span><span class="sxs-lookup"><span data-stu-id="38aa4-122">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>

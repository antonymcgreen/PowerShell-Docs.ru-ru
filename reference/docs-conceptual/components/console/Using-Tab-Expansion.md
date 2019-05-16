---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Расширение по клавише TAB
ms.assetid: c8730471-bf6a-43b8-ab1d-f9ef5a74f04e
ms.openlocfilehash: 437c1e3c04352f2c5c3aba4c67b542821975f739
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229426"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="66c92-103">Расширение по клавише TAB</span><span class="sxs-lookup"><span data-stu-id="66c92-103">Using Tab Expansion</span></span>

<span data-ttu-id="66c92-104">Оболочки командной строки часто позволяют автоматически завершать длинные имена файлов или команд, что ускоряет ввод и позволяет использовать подсказки.</span><span class="sxs-lookup"><span data-stu-id="66c92-104">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="66c92-105">PowerShell позволяет автоматически завершать имена файлов и командлетов, нажимая клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="66c92-105">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="66c92-106">Завершением по клавише TAB управляет внутренняя функция TabExpansion или TabExpansion2.</span><span class="sxs-lookup"><span data-stu-id="66c92-106">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="66c92-107">Так как ее можно изменить или переопределить, приведенные инструкции распространяются на стандартную конфигурацию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66c92-107">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="66c92-108">Для автоматического завершения имени файла или пути из доступных вариантов введите часть имени и нажмите клавишу <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="66c92-108">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="66c92-109">PowerShell автоматически расширяет имя до первого совпадения.</span><span class="sxs-lookup"><span data-stu-id="66c92-109">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="66c92-110">Нажимая клавишу <kbd>TAB</kbd>, можно перебрать все варианты.</span><span class="sxs-lookup"><span data-stu-id="66c92-110">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="66c92-111">Расширение имен командлетов по клавише TAB происходит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="66c92-111">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="66c92-112">Чтобы использовать расширение по клавише TAB для имени командлета, введите всю первую часть имени (глагол) и дефис после нее.</span><span class="sxs-lookup"><span data-stu-id="66c92-112">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="66c92-113">Можно указать дополнительную часть имени для поиска частичного совпадения.</span><span class="sxs-lookup"><span data-stu-id="66c92-113">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="66c92-114">Например, если ввести `get-co` и нажать клавишу <kbd>TAB</kbd>, PowerShell автоматически расширит это до командлета `Get-Command` (обратите внимание, что это также приводит регистр букв к стандартной форме).</span><span class="sxs-lookup"><span data-stu-id="66c92-114">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="66c92-115">Если нажать клавишу <kbd>TAB</kbd> еще раз, PowerShell заменит результат на `Get-Content`, единственное другое подходящее имя командлета.</span><span class="sxs-lookup"><span data-stu-id="66c92-115">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="66c92-116">Расширение по клавише TAB можно использовать несколько раз в одной строке.</span><span class="sxs-lookup"><span data-stu-id="66c92-116">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="66c92-117">Например, вы можете использовать завершение по клавише TAB для имени командлета `Get-Content`:</span><span class="sxs-lookup"><span data-stu-id="66c92-117">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="66c92-118">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="66c92-118">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="66c92-119">После этого можно указать часть пути к файлу журнала активной установки и снова воспользоваться описанной функцией:</span><span class="sxs-lookup"><span data-stu-id="66c92-119">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="66c92-120">При нажатии клавиши <kbd>TAB</kbd> команда расширяет до следующей:</span><span class="sxs-lookup"><span data-stu-id="66c92-120">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="66c92-121">Единственным ограничением этого процесса является то, что символы табуляции принимаются за попытки завершения слова.</span><span class="sxs-lookup"><span data-stu-id="66c92-121">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="66c92-122">При копировании и вставке примеров команд в консоль PowerShell убедитесь, что пример не содержит символы табуляции. В противном случае результаты будут непредсказуемыми и почти наверняка будут отличаться от требуемых.</span><span class="sxs-lookup"><span data-stu-id="66c92-122">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
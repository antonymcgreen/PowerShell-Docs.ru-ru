---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 7730912707bb14e90a9926b387fb3a859d7ca26d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="convert-string"></a><span data-ttu-id="6f6be-102">Convert-String</span><span class="sxs-lookup"><span data-stu-id="6f6be-102">Convert-String</span></span>
<span data-ttu-id="6f6be-103">**Convert-String** предоставляет функциональность "магическая замена".</span><span class="sxs-lookup"><span data-stu-id="6f6be-103">**Convert-String** exposes "replace by magic" functionality.</span></span> <span data-ttu-id="6f6be-104">Укажите примеры того, как должен выглядеть текст в исходном и итоговом виде, чтобы **Convert-String** автоматически отформатировал текста.</span><span class="sxs-lookup"><span data-stu-id="6f6be-104">Provide before and after examples of how you want text to look, and **Convert-String** formats your text automatically.</span></span> <span data-ttu-id="6f6be-105">Продемонстрируем это — возьмем имя и фамилию человека и заменим их последовательностью из фамилии, точки, первой буквы имени и точки.</span><span class="sxs-lookup"><span data-stu-id="6f6be-105">Here's a demo - taking somebody's first and last name, and replacing it with their last name, a comma, the first initial of their last name, and a dot.</span></span> <span data-ttu-id="6f6be-106">Попробуйте сделать это с помощью регулярного выражения и посмотрите, сколько времени для этого потребуется.</span><span class="sxs-lookup"><span data-stu-id="6f6be-106">Try it with a regex, and see how long it takes you.</span></span>

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```

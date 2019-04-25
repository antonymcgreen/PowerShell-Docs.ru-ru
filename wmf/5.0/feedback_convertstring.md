---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 27541d903748738675917941dc6b60bc9acdc3f4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057797"
---
# <a name="convert-string"></a><span data-ttu-id="fb4cc-102">Convert-String</span><span class="sxs-lookup"><span data-stu-id="fb4cc-102">Convert-String</span></span>
<span data-ttu-id="fb4cc-103">**Convert-String** предоставляет функциональность "магическая замена".</span><span class="sxs-lookup"><span data-stu-id="fb4cc-103">**Convert-String** exposes "replace by magic" functionality.</span></span> <span data-ttu-id="fb4cc-104">Укажите примеры того, как должен выглядеть текст в исходном и итоговом виде, чтобы **Convert-String** автоматически отформатировал текста.</span><span class="sxs-lookup"><span data-stu-id="fb4cc-104">Provide before and after examples of how you want text to look, and **Convert-String** formats your text automatically.</span></span> <span data-ttu-id="fb4cc-105">Продемонстрируем это — возьмем имя и фамилию человека и заменим их последовательностью из фамилии, точки, первой буквы имени и точки.</span><span class="sxs-lookup"><span data-stu-id="fb4cc-105">Here's a demo - taking somebody's first and last name, and replacing it with their last name, a comma, the first initial of their last name, and a dot.</span></span> <span data-ttu-id="fb4cc-106">Попробуйте сделать это с помощью регулярного выражения и посмотрите, сколько времени для этого потребуется.</span><span class="sxs-lookup"><span data-stu-id="fb4cc-106">Try it with a regex, and see how long it takes you.</span></span>

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```

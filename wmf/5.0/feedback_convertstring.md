---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 7730912707bb14e90a9926b387fb3a859d7ca26d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="convert-string"></a>Convert-String
**Convert-String** предоставляет функциональность "магическая замена". Укажите примеры того, как должен выглядеть текст в исходном и итоговом виде, чтобы **Convert-String** автоматически отформатировал текста. Продемонстрируем это — возьмем имя и фамилию человека и заменим их последовательностью из фамилии, точки, первой буквы имени и точки. Попробуйте сделать это с помощью регулярного выражения и посмотрите, сколько времени для этого потребуется.

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```

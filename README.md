---
ms.openlocfilehash: 034d75a84e39cb0cf88a272ca58b5ccc229c5d9b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "74540461"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Правила поведения при работе с открытым кодом, принятые в проектах корпорации Майкрософт

В рамках этого проекта действуют [правила поведения в отношении продуктов с открытым исходным кодом Майкрософт](https://opensource.microsoft.com/codeofconduct/). Дополнительные сведения:[вопросы и ответы по правилам поведения](https://opensource.microsoft.com/codeofconduct/faq/). С любыми другими вопросами или комментариями обращайтесь по адресу[opencode@microsoft.com](mailto:opencode@microsoft.com).

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>Состояние сборки

| Активная ветвь | Промежуточная ветвь |
|:------------|:---------------|
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge]

## <a name="powershell-documentation"></a>Документация по PowerShell

Добро пожаловать в репозиторий PowerShell-Docs, в котором находится официальная документация по PowerShell.

## <a name="repository-structure"></a>Структура репозитория

Каждая из перечисленных ниже папок верхнего уровня содержит набор документации, которая опубликована на сайте [документации Майкрософт](https://docs.microsoft.com/powershell).

- [/reference/](https://docs.microsoft.com/powershell/scripting/) — для тематических статей по PowerShell и справочной документации по модулям для версий 5.1, 6.0 и 7.0. Это содержимое также служит источником справочных сведений, выводимых с помощью командлета `Get-Help`.
  - [docs-conceptual/](https://docs.microsoft.com/powershell) — папка, которая содержит тематическую документацию и следующие наборы документов:
    - [/developer/](https://docs.microsoft.com/powershell/scripting/developer/) — папка для документации по пакету SDK PowerShell (перенесена из MSDN).
    - [/dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) — папка для функции Desired State Configuration.
    - [/gallery/](https://docs.microsoft.com/powershell/scripting/gallery) — для [коллекции PowerShell](https://www.powershellgallery.com/).
    - [/jea/](https://docs.microsoft.com/powershell/scripting/jea/) — для функции Just Enough Administration (JEA).
    - [wmf/](https://docs.microsoft.com/powershell/scripting/wmf/overview) — содержит заметки о платформе Windows Management Framework (пакет, используемый для распространения новых версий PowerShell в предыдущих версиях Windows).

## <a name="contributing"></a>Участие

Мы активно объединяем публикации в этом репозитории с помощью [запроса на включение внесенных изменений](https://help.github.com/articles/using-pull-requests/) в *промежуточной* ветви.
Примечание. Для того, чтобы сообщество свободно использовало ваши публикации, перед отправкой запроса на включение внесенных изменений необходимо [подписать соглашение Contribution License Agreement](https://cla.microsoft.com/).

Дополнительные сведения о публикации можно прочесть в [руководстве по публикациям](https://docs.microsoft.com/contribute/powershell/powershell-contribute). Руководство по публикациям содержит подробные сведения об участии в составлении документации и рекомендуемых инструментах, а также требования к стилю и форматированию. Используйте шаблоны "Проблема" и "Запрос на включение внесенных изменений", чтобы обеспечить согласованность документации по разным версиям.

## <a name="licenses"></a>Лицензии

Существует два файла лицензии для этого проекта. Лицензия MIT применяется к коду, содержащемуся в этом репозитории. Лицензия Creative Commons применяется к документации.
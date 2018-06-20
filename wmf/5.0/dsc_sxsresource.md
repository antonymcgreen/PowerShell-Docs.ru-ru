---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 0543afbc72148b1ba713e59655126c069b16ef33
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218439"
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a>Поддержка параллельного управления версиями модулей для ресурсов DSC

Модули, содержащие ресурсы DSC, могут быть установлены параллельно, а конфигурации DSC могут использовать конкретную версию ресурса, установленного в системе.

Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](https://msdn.microsoft.com/powershell/dsc/sxsresource).

## <a name="known-issues"></a>Известные проблемы

Ниже перечислены известные с параллельной установкой в этом выпуске:

-   Использование двух различных версий ресурса DSC в одной конфигурации не поддерживается.

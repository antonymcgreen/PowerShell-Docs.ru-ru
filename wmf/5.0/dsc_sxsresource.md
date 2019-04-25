---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 5b31fe833fb0f9d0f3f2733e777e4608a697d583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057933"
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a>Поддержка параллельного управления версиями модулей для ресурсов DSC

Модули, содержащие ресурсы DSC, могут быть установлены параллельно, а конфигурации DSC могут использовать конкретную версию ресурса, установленного в системе.

Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](https://msdn.microsoft.com/powershell/dsc/sxsresource).

## <a name="known-issues"></a>Известные проблемы

Ниже перечислены известные с параллельной установкой в этом выпуске:

-   Использование двух различных версий ресурса DSC в одной конфигурации не поддерживается.

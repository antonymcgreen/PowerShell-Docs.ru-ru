---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 42f323590609319388e9a0a2c7c305dfa80c2d49
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221856"
---
# <a name="class-based-dsc-resources"></a>Ресурсы DSC, основанные на классах

## <a name="defining-dsc-resources-with-classes"></a>Определение ресурсов DSC с помощью классов

Основываясь на полученных отзывах, мы упростили создание и использование ресурсов DSC на основе классов.
Ресурс DSC на основе класса и поставщик ресурсов DSC командлета имеют следующие отличия.

* MOF-файл для схемы не требуется.
* Вложенная папка **DSCResource** в папке модуля не требуется.
* Файл модуля PowerShell может содержать несколько классов ресурсов DSC.

Дополнительные сведения см. в разделе [Написание пользовательских ресурсов DSC с использованием классов PowerShell](https://msdn.microsoft.com/powershell/dsc/authoringresource).

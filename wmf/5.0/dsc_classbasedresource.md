---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: a1e90a0b96f74decb55343292b97befaf1a85f8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058120"
---
# <a name="class-based-dsc-resources"></a>Ресурсы DSC, основанные на классах

## <a name="defining-dsc-resources-with-classes"></a>Определение ресурсов DSC с помощью классов

Основываясь на полученных отзывах, мы упростили создание и использование ресурсов DSC на основе классов.
Ресурс DSC на основе класса и поставщик ресурсов DSC командлета имеют следующие отличия.

* MOF-файл для схемы не требуется.
* Вложенная папка **DSCResource** в папке модуля не требуется.
* Файл модуля PowerShell может содержать несколько классов ресурсов DSC.

Дополнительные сведения см. в разделе [Написание пользовательских ресурсов DSC с использованием классов PowerShell](https://msdn.microsoft.com/powershell/dsc/authoringresource).

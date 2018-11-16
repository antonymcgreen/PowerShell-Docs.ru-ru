---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Удаление пакетов
ms.openlocfilehash: ca5e68fcad52e4c7561d2c2b3858228652f22e0b
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003936"
---
# <a name="deleting-packages"></a>Удаление пакетов

Коллекция PowerShell не поддерживает полное удаление пакетов, так как это помешает работе пользователей, которым они необходимы для работы.

Вместо этого пакет можно исключить из коллекции PowerShell. Для этого используется страница управления пакетами на веб-сайте.
Исключенный пакет больше не будет отображаться в результатах поиска и списках пакетов в коллекции PowerShell и при использовании команд PowerShellGet.
При этом он будет доступен для загрузки при указании точной версии, что обеспечит сохранение работоспособности автоматических скриптов.

Если возникнет исключительная ситуация и нужно будет удалить какой-либо пакет, это можно сделать вручную рабочей группой, ответственной за коллекцию PowerShell.
Например, уважительной причиной для удаления элемента может стать нарушение авторских прав или если он включает потенциально вредоносное содержимое.
Нужно отправить запрос поддержки через [коллекцию PowerShell](http://www.PowerShellGallery.com) в этом случае.
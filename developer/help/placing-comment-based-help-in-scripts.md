---
title: Размещение справки на основе комментариев в сценарии | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083235"
---
# <a name="placing-comment-based-help-in-scripts"></a>Размещение справки на основе комментариев в сценариях

В этом разделе объясняется, где разместить справки на основе комментариев по сценарию, чтобы `Get-Help` командлет связывает раздел справки, основанной на комментариях, с помощью сценариев, а не все функции, которые могут быть в скрипте.

## <a name="where-to-place-comment-based-help-for-a-script"></a>Размещение основанной на комментариях справку для скрипта

- В начале файла скрипта. Скрипт справки может стоять в скрипт только комментарии и пустые строки.

- В конце файла скрипта.

  При объявлении функции, первый элемент в тексте сценария (после Справка) должен существовать по крайней мере две пустые строки между концом скрипт справки и в объявлении функции. В противном случае справки интерпретируется как справку для функции, не справку для скрипта.

## <a name="examples-of-help-placement-in-a-script"></a>Примеры размещения справки в скрипте

 Ниже приведены примеры каждого из вариантов размещения, основанной на комментариях справку для скрипта.

### <a name="help-at-the-beginning-of-a-script"></a>Помочь в начале сценария

 В следующем примере показано основе комментариев в начале сценария.

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>Помочь в конце сценария

 В следующем примере показано, основанной на комментариях в конце скрипта.

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```
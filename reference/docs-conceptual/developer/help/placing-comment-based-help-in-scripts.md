---
title: Размещение справки на основе комментариев в скриптах | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361183"
---
# <a name="placing-comment-based-help-in-scripts"></a>Размещение справки на основе комментариев в сценариях

В этом разделе объясняется, куда разместить справку на основе комментариев для скрипта, чтобы командлет `Get-Help` сопоставленный с комментариями раздел справки с скриптами, а не с функциями, которые могут быть в скрипте.

## <a name="where-to-place-comment-based-help-for-a-script"></a>Размещение справки на основе комментариев для сценария

- В начале файла скрипта. Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.

- В конце файла скрипта.

  Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки. В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.

## <a name="examples-of-help-placement-in-a-script"></a>Примеры размещения справки в сценарии

 В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.

### <a name="help-at-the-beginning-of-a-script"></a>Справка в начале сценария

 В следующем примере показано, как на основе комментариев в начале скрипта.

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>Справка в конце скрипта

 В следующем примере показано, как на основе комментариев в конце скрипта.

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```
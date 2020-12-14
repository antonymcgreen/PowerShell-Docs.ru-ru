---
ms.date: 09/12/2016
ms.topic: reference
title: Размещение справки на основе комментариев в сценариях
description: Размещение справки на основе комментариев в сценариях
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645435"
---
# <a name="placing-comment-based-help-in-scripts"></a>Размещение справки на основе комментариев в сценариях

В этом разделе объясняется, куда поместить справку на основе комментариев для сценария, чтобы `Get-Help` командлет привязывает раздел справки на основе комментариев с скриптами, а не с функциями, которые могут быть в скрипте.

## <a name="where-to-place-comment-based-help-for-a-script"></a>Размещение Comment-Based справки по сценарию

- В начале файла скрипта.

  Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.

- В конце файла скрипта.

  Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки. В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.

## <a name="examples-of-help-placement-in-a-script"></a>Примеры размещения справки в сценарии

В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.

### <a name="help-at-the-beginning-of-a-script"></a>Справка в начале сценария

В следующем примере показано, как на основе комментариев в начале скрипта.

```powershell
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

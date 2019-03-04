---
title: Учебник GetProc | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4663905f-560a-4e39-9b03-6db2c315c322
caps.latest.revision: 6
ms.openlocfilehash: bbd07a0d0abd30742b7e02482adedae3af43aca4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862460"
---
# <a name="getproc-tutorial"></a>Руководство по GetProc

Этот раздел содержит руководство для создания командлет Get-Proc, — очень похоже на [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет, предоставляемые Windows PowerShell. Этот учебник содержит фрагменты кода, которые иллюстрируют, как реализованы командлеты и объяснение кода.

## <a name="topics-in-this-tutorial"></a>Разделы в данном руководстве

Подразделы в этом руководстве предназначены для прочтения последовательно, каждый раздел, основываясь на тех, которые обсуждались в предыдущем разделе.

[Создание командлета без параметров](./creating-a-cmdlet-without-parameters.md) в этом разделе описывается, как создать командлет, который извлекает данные из локального компьютера без использования параметров, а затем записывает данные в конвейер.

[Добавление параметров командной строки процесса Input](./adding-parameters-that-process-command-line-input.md) в этом разделе описывается добавление параметра в командлет Get-Proc, так что этот командлет может обработать входные данные, на основе явных объектов передается командлету. Реализацию, описанную здесь извлекает процессов на основе их имени и затем записывает данные в конвейер.

[Добавление параметров, входные данные конвейера процесс](./adding-parameters-that-process-pipeline-input.md) в этом разделе описывается добавление параметра в командлет Get-Proc, так что этот командлет может обработать объекты, передаваемый через конвейер. Командлет реализации описано здесь извлекает процессов на основе объектов, переданных в командлет и затем записывает данные в конвейер.

[Добавление отчетов об ошибках устранимые Your командлету](./adding-non-terminating-error-reporting-to-your-cmdlet.md) в этом разделе описывается добавление устранимые ошибки reporting в командлет. Реализация обнаруживает устранимые ошибки, которые возникают при обработке входных данных и записывает в поток ошибок записи об ошибке.

## <a name="see-also"></a>См. также

[Создание командлета без параметров](./creating-a-cmdlet-without-parameters.md)

[Добавление параметров, которые обрабатывают данные в командной строке](./adding-parameters-that-process-command-line-input.md)

[Добавление параметров конвейера обработки входных данных](./adding-parameters-that-process-pipeline-input.md)

[Добавление устранимые ошибки Reporting командлета](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

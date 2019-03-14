---
title: Учебник StopProc | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a142aeb6-9c11-44a0-b34f-1f9470fa347b
caps.latest.revision: 5
ms.openlocfilehash: 27c8e2c7525aba38e69e50b2b7fd3b18b8e54989
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794405"
---
# <a name="stopproc-tutorial"></a>Руководство по StopProc

В этом разделе содержится руководство по созданию командлет Stop-Proc, который очень похожа на [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) командлет, предоставляемые Windows PowerShell. Этот учебник содержит фрагменты кода, которые иллюстрируют, как реализованы командлеты и объяснение кода.

## <a name="topics-in-this-tutorial"></a>Разделы в данном руководстве

Подразделы в этом руководстве предназначены для прочтения последовательно, каждый раздел, основываясь на тех, которые обсуждались в предыдущем разделе.

[Создание командлета, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md) в этом разделе описывается, как создать командлет, поддерживающий изменения системы, такие как остановка процесса, выполняющегося на компьютере.

[Добавление пользовательских сообщений Your командлету](./adding-user-messages-to-your-cmdlet.md) в этом разделе описывается добавление возможность записи пользовательских сообщений, сообщений отладки, предупреждающие сообщения и сведения о ходе выполнения командлета.

[Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) в этом разделе описывается, как создать командлет, который поддерживает псевдонимы параметра "," Справка "и" Развертывание знаков подстановки.

[Добавление параметра в командлетах](./adding-parameter-sets-to-a-cmdlet.md) в этом разделе описывается добавление наборов параметров в командлет. Наборы параметров позволяют командлет для работы, на какие параметры задаются пользователем по-разному основе.

## <a name="see-also"></a>См. также

[Создание командлета, который изменяет системы](./creating-a-cmdlet-that-modifies-the-system.md)

[Добавление пользовательских сообщений в командлет](./adding-user-messages-to-your-cmdlet.md)

[Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[Добавление параметра наборов в командлетах](./adding-parameter-sets-to-a-cmdlet.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: c007bb11324e10ffd100797dccd9e6ab0d09a73e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067983"
---
# <a name="how-to-import-cmdlets-using-modules"></a>Импорт командлетов с помощью модулей

В этом разделе описывается, как импортировать командлеты в сеанс Windows PowerShell с помощью двоичного модуля.

> [!NOTE]
> Модули можно входят командлеты, поставщики, функции, переменные, псевдонимы и многое другое. Оснастки может содержать только командлеты и поставщики.

## <a name="how-to-load-cmdlets-using-a-module"></a>Как загрузить командлеты с помощью модуля

1. Создайте папку модуля с тем же именем в качестве файла сборки, в котором реализованы командлеты. В этой процедуре вы создадите в папке модуля `system32` папки.

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

2. Убедитесь, что `PSModulePath` переменная среды включает путь к папке нового модуля. По умолчанию папке системы уже добавлен `PSModulePath` переменной среды.

3. Скопируйте командлет сборки в папке модуля.

4. Выполните следующую команду, чтобы добавить командлеты к сеансу:

   `import-module [Module_Name]`

   Эту процедуру можно использовать для тестирования командлетов. Он добавляет все командлеты в сборке в сеанс. Дополнительные сведения о модулях различных типов модулей, различные способы загрузки модулей и как ограничить элементы модуля, которые экспортируются, см. в разделе [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[Установка модулей](../module/installing-a-powershell-module.md)
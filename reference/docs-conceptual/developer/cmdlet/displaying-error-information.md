---
ms.date: 09/13/2016
ms.topic: reference
title: Отображение сведений об ошибке
description: Отображение сведений об ошибке
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653060"
---
# <a name="displaying-error-information"></a>Отображение сведений об ошибке

В этом разделе обсуждаются способы, с помощью которых пользователи могут отображать сведения об ошибках.

При возникновении ошибки в командлете по умолчанию отображается представление сведений об ошибке, похожее на следующие выходные данные ошибки.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

Однако пользователи могут просматривать ошибки по категориям, присвоив `$ErrorView` переменной значение `"CategoryView"` . В представлении "Категория" отображаются конкретные сведения из записи об ошибке, а не описание ошибки в произвольном тексте. Это представление может быть полезно, если имеется длинный список ошибок для проверки. В представлении «Категория» предыдущее сообщение об ошибке отображается следующим образом.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

## <a name="see-also"></a>См. также:

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

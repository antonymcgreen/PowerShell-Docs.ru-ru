---
title: Отображение сведений об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369973"
---
# <a name="displaying-error-information"></a>Отображение сведений об ошибке

В этом разделе обсуждаются способы, с помощью которых пользователи могут отображать сведения об ошибках.

При возникновении ошибки в командлете по умолчанию отображается представление сведений об ошибке, похожее на следующие выходные данные ошибки.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

Однако пользователи могут просматривать ошибки по категориям, присвоив переменной `$ErrorView` значение `"CategoryView"`. В представлении "Категория" отображаются конкретные сведения из записи об ошибке, а не описание ошибки в произвольном тексте. Это представление может быть полезно, если имеется длинный список ошибок для проверки. В представлении «Категория» предыдущее сообщение об ошибке отображается следующим образом.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

## <a name="see-also"></a>См. также:

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

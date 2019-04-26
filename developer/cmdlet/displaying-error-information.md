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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068289"
---
# <a name="displaying-error-information"></a>Отображение сведений об ошибке

В этом разделе обсуждаются способы, в котором пользователи могут отобразить сведения об ошибке.

Когда командлета возникает ошибка, представление сведений об ошибке по умолчанию имеют следующие выходные данные ошибок.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

Тем не менее, пользователи могут просматривать ошибки по категориям, задав `$ErrorView` переменной `"CategoryView"`. Вид по категориям отображает специализированную информацию из запись об ошибке, а не произвольное текстовое описание ошибки. Это представление может быть полезно при наличии длинный список ошибок для сканирования. В представлении по категориям ранее сообщения об ошибке отображается следующим образом.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

## <a name="see-also"></a>См. также

[Записи об ошибках PowerShell Windows](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

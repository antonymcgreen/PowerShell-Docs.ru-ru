---
title: Отображение сведений об ошибках | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774581"
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

## <a name="see-also"></a>См. также

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

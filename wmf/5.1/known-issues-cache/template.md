---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
title: пример шаблона с описанием известной проблемы или ограничения
ms.openlocfilehash: 8c1004e16f78913174af2e519e451f6fd9f30ff7
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794503"
---
 >Примечание. Предоставьте предложенное описательное название и краткое описание.

## <a name="example-erroneous-executionpolicy-errors"></a>Пример: ложные ошибки ExecutionPolicy
В Windows 7 использование модулей PowerShell и ресурсов DSC может привести к возникновению ошибок, связанных с ExecutionPolicy.

### <a name="resolution"></a>Разрешение

Чтобы устранить проблему, задайте для **ExecutionPolicy** значение **RemoteSigned**, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):

```powershell
Set-ExecutionPolicy RemoteSigned
```

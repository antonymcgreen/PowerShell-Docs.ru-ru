---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
title: пример шаблона с описанием известной проблемы или ограничения
ms.openlocfilehash: 453d4e40b906ebcab7314f04e138ded271338846
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
>Примечание. Предоставьте предложенное описательное название и краткое описание.

## <a name="example-erroneous-executionpolicy-errors"></a>Пример. Ложные ошибки ExecutionPolicy ##
В Windows 7 использование модулей PowerShell и ресурсов DSC может привести к возникновению ошибок, связанных с ExecutionPolicy.

### <a name="resolution"></a>Разрешение

Чтобы устранить проблему, задайте для **ExecutionPolicy** значение **RemoteSigned**, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):

```powershell
Set-ExecutionPolicy RemoteSigned
```

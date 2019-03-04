---
title: Создание пространства выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857910"
---
# <a name="creating-runspaces"></a>Создание пространств выполнения

Пространства выполнения является операционной среды для команды, которые вызываются ведущим приложением. Эта среда включает в себя команды и данных, которые в настоящее время отсутствуют и каких-либо ограничений языка, которые в настоящее время применяются.

 Размещение приложений можно использовать пространству выполнения по умолчанию, предоставляемый Windows PowerShell, которая включает в себя все доступные основные команды, или создания пользовательских пространства выполнения, которая включает только подмножество доступных команд. Можно создать настраиваемые пространство выполнения, создав [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта и его назначение вашего пространства выполнения.

## <a name="runspace-tasks"></a>Пространства выполнения задачи

1. [Создание InitialSessionState](./creating-an-initialsessionstate.md)

2. [Создание ограниченное пространство выполнения](./creating-a-constrained-runspace.md)

3. [Создание несколькими средами](./creating-multiple-runspaces.md)

## <a name="see-also"></a>См. также

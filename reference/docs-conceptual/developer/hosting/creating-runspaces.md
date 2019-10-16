---
title: Создание пространств выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367583"
---
# <a name="creating-runspaces"></a>Создание пространств выполнения

Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением. Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.

 Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд. Чтобы создать настраиваемое пространство выполнения, создайте объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.

## <a name="runspace-tasks"></a>Задачи пространства выполнения

1. [Создание InitialSessionState](./creating-an-initialsessionstate.md)

2. [Создание ограниченного пространства выполнения](./creating-a-constrained-runspace.md)

3. [Создание нескольких пространств выполнения](./creating-multiple-runspaces.md)

## <a name="see-also"></a>См. также:

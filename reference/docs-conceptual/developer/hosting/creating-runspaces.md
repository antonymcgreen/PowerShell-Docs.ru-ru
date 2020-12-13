---
ms.date: 09/13/2016
ms.topic: reference
title: Создание пространств выполнения
description: Создание пространств выполнения
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649340"
---
# <a name="creating-runspaces"></a>Создание пространств выполнения

Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением. Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.

 Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд. Чтобы создать настраиваемое пространство выполнения, создайте объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.

## <a name="runspace-tasks"></a>Задачи пространства выполнения

1. [Создание InitialSessionState](./creating-an-initialsessionstate.md)

2. [Создание ограниченного пространства выполнения](./creating-a-constrained-runspace.md)

3. [Создание нескольких пространств выполнения](./creating-multiple-runspaces.md)

## <a name="see-also"></a>См. также

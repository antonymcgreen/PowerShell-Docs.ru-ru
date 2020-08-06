---
title: Создание пространств выполнения | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0c27e2bf54e16a3bdc93c4b91629893bb1cc1e3e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779579"
---
# <a name="creating-runspaces"></a>Создание пространств выполнения

Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением. Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.

 Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд. Чтобы создать настраиваемое пространство выполнения, создайте объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.

## <a name="runspace-tasks"></a>Задачи пространства выполнения

1. [Создание InitialSessionState](./creating-an-initialsessionstate.md)

2. [Создание ограниченного пространства выполнения](./creating-a-constrained-runspace.md)

3. [Создание нескольких пространств выполнения](./creating-multiple-runspaces.md)

## <a name="see-also"></a>См. также

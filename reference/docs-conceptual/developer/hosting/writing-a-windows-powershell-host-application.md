---
title: Создание ведущего приложения Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: fe0393634a1e5bb1a3d4a98ccf245e199beb0f16
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75869917"
---
# <a name="writing-a-windows-powershell-host-application"></a>Написание ведущего приложения Windows PowerShell

Windows PowerShell можно разместить в приложении. Ведущее приложение может определить пространство выполнения, в котором выполняются команды, открывать сеансы на локальном или удаленном компьютере и вызывать команды синхронно или асинхронно в зависимости от потребностей приложения.

В следующих разделах объясняется, как создать приложение, в котором размещается Windows PowerShell.

## <a name="in-this-section"></a>Содержание

[Краткое руководство по узлу Windows PowerShell](./windows-powershell-host-quickstart.md) Содержит инструкции и примеры кода, позволяющие приступить к созданию ведущих приложений.

[Создание пространств](./creating-runspaces.md) выполнения Набор разделов, в которых объясняется, как создавать пространства выполнения для команды Windows PowerShell в ведущем приложении.

[Добавление и вызов команд](./adding-and-invoking-commands.md) Объясняется, как создать и запустить конвейер команд в ведущем приложении.

[Создание удаленных пространств](./creating-remote-runspaces.md) выполнения Объясняет, как подключить пространство выполнения к удаленному компьютеру.

[Создание настраиваемого пользовательского интерфейса](./creating-a-custom-user-interface.md) Содержит общие сведения о пользовательских интерфейсах и ссылки на примеры.

[Примеры ведущих приложений](./host-application-samples.md) Этот раздел содержит примеры полных ведущих приложений.

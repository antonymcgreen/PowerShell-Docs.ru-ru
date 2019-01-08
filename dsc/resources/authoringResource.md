---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell
ms.openlocfilehash: 882b6efed4564d2354183d7472b301e1e1758335
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402275"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a>Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell

> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

Настройка требуемого состояния (DSC) Windows PowerShell включает встроенные ресурсы для настройки среды. Этот раздел содержит сведения о разработке ресурсов и ссылок на разделы с описанием особенностей и примерами.

## <a name="dsc-resource-components"></a>Компоненты ресурсов DSC

Ресурс DSC — это модуль Windows PowerShell. Модуль содержит схему (определение настраиваемых свойств) и реализацию (код, выполняющий заданную конфигурацией работу) для ресурса. Схема ресурсов DSC может быть определена в MOF-файле, а реализация выполняется модулем сценариев. С добавлением поддержки классов PowerShell в версии 5 появилась возможность определять схему и реализацию в классе. Более подробные инструкции по созданию ресурсов DSC см. в следующих статьях:

* [Написание пользовательских ресурсов DSC с использованием MOF](authoringResourceMOF.md)
* [Реализация ресурса DSC на языке C#](authoringResourceMofCS.md)
* [Написание пользовательских ресурсов DSC с использованием классов PowerShell](authoringResourceClass.md)
* [Составные ресурсы: использование конфигурации DSC как ресурса](authoringResourceComposite.md)
* [Использование конструктора ресурсов](../authoringResourceMofDesigner.md)

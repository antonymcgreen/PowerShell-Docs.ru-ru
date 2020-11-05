---
ms.date: 07/08/2020
keywords: dsc,powershell,конфигурация,установка
title: Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell
description: В этой статье приведены общие сведения о разработке ресурсов, а также ссылки на статьи с подробной информацией и примерами.
ms.openlocfilehash: ff9a0c8ae10583155217fbeccc62e6e1c94f9a11
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656412"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a>Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Настройка требуемого состояния (DSC) Windows PowerShell включает встроенные ресурсы для настройки среды. В этой статье приведены общие сведения о разработке ресурсов, а также ссылки на статьи с подробной информацией и примерами.

## <a name="dsc-resource-components"></a>Компоненты ресурсов DSC

Ресурс DSC — это модуль Windows PowerShell. Модуль содержит схему (определение настраиваемых свойств) и реализацию (код, выполняющий заданную конфигурацией работу) для ресурса. Схема ресурсов DSC может быть определена в MOF-файле, а реализация выполняется модулем сценариев. С добавлением поддержки классов PowerShell в версии 5 появилась возможность определять схему и реализацию в классе. Более подробные инструкции по созданию ресурсов DSC см. в следующих статьях:

- [Написание пользовательских ресурсов DSC с использованием MOF](authoringResourceMOF.md)
- [Реализация ресурса DSC на языке C#](authoringResourceMofCS.md)
- [Написание пользовательских ресурсов DSC с использованием классов PowerShell](authoringResourceClass.md)
- [Составные ресурсы: использование DSC как ресурса](authoringResourceComposite.md)
- [Использование конструктора ресурсов](authoringResourceMofDesigner.md)

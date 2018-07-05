---
ms.date: 06/12/2018
keywords: wmf,powershell,установка
title: Windows Management Framework (WMF)
ms.openlocfilehash: 17011f88c364cb56a0c87f092873ccd99db450bc
ms.sourcegitcommit: 68093cc12a7a22c53d11ce7d33c18622921a0dd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36943614"
---
# <a name="windows-management-framework"></a>Windows Management Framework

Windows Management Framework (WMF) — это согласованный интерфейс управления для Windows. WMF обеспечивает удобный способ управления несколькими версиями клиента Windows и Windows Server. Пакеты установщика WMF содержат обновления для функций управления и доступны для более старых версий Windows.

При установке WMF добавляются или обновляются следующие компоненты:

- Windows PowerShell
- Windows PowerShell Desired State Configuration (DSC)
- Интегрированная среда сценариев Windows PowerShell (ISE)
- Удаленное управление Windows (WinRM)
- Инструментарий управления Windows (WMI)
- Веб-службы Windows PowerShell (расширение IIS OData для управления)
- Инвентаризация программного обеспечения (SIL)
- Поставщик CIM диспетчера сервера

## <a name="wmf-release-notes"></a>Заметки о выпуске WMF

Сведения о различных улучшениях в PowerShell и других компонентах определенной версии WMF см. по следующим ссылкам на заметки о выпусках:

- [WMF 5.1](5.1/release-notes.md)
- [WMF 5.0](5.0/releasenotes.md)
- [WMF 4.0](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [WMF 3.0](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a>Доступность WMF в различных операционных системах Windows

|Версия операционной системы  |[WMF 5.1][] |[WMF 5.0][] |[WMF 4.0][] |[WMF 3.0][]  |[WMF 2.0][] |
|--------------------------|------------|------------|------------|-------------|------------|
|Windows Server 2016       |Входит в комплект поставки|            |            |             |            |
|Windows 10                |Входит в комплект поставки|Входит в комплект поставки|            |             |            |
|Windows Server 2012 R2    |Да         |Да         |Входит в комплект поставки|             |            |
|Windows 8.1               |Да         |Да         |Входит в комплект поставки|             |            |
|Windows Server 2012       |Да         |Да         |Да         |Входит в комплект поставки |            |
|Windows 8                 |            |            |            |Входит в комплект поставки |            |
|Windows Server 2008 R2 с пакетом обновления 1 (SP1)|Да         |Да         |Да         |Да          |Входит в комплект поставки|
|Windows 7 с пакетом обновления 1 (SP1)             |Да         |Да         |Да         |Да          |Входит в комплект поставки|
|Windows Server 2008 с пакетом обновления 2 (SP2)   |            |            |            |Да          |Да         |
|Windows Vista             |            |            |            |             |Да         |
|Windows Server 2003       |            |            |            |             |Да         |
|Windows XP                |            |            |            |Да          |            |

**Входит в комплект поставки**: функции указанной версии WMF были включены в указанную версию клиента Windows или Windows Server.

[WMF 5.1]: https://aka.ms/wmf51download
[WMF 5.0]: https://aka.ms/wmf5download
[WMF 4.0]: https://aka.ms/wmf4download
[WMF 3.0]: https://aka.ms/wmf3download
[WMF 2.0]: https://aka.ms/wmf2download

---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Усовершенствования отладки сценариев PowerShell
ms.openlocfilehash: f1771a451ba671da2371fcfc95374e6131573ddc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147814"
---
# <a name="improvements-in-powershell-script-debugging"></a>Усовершенствования отладки сценариев PowerShell

PowerShell 5.0 включает несколько улучшений для более эффективной отладки.

## <a name="break-all"></a>Команда "Прервать все"

Консоль PowerShell и интегрированная среда сценариев PowerShell теперь позволяют переходить в режим отладчика при выполнении скриптов. Это работает как в локальных, так и в удаленных сеансах.

В окне консоли нажмите клавиши <kbd>Ctrl</kbd>+<kbd>Break</kbd>.

В интегрированной среде сценариев нажмите клавиши <kbd>Ctrl</kbd>+<kbd>B</kbd> или воспользуйтесь командой меню **Отладка -> Прервать все**.

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a>Удаленная отладка и удаленное редактирование файлов в интегрированной среде сценариев PowerShell

Теперь среда PowerShell позволяет открывать и редактировать файлы в удаленном сеансе с помощью команды PSEdit.
Например, во время удаленного сеанса можно открыть файл для редактирования из командной строки, как показано ниже:

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

Кроме того, вы можете вносить изменения и сохранять их в удаленном файле, который автоматически открывается в интегрированной среде сценариев PowerShell при попадании в точку останова. Теперь можно выполнить отладку файла сценария, выполняемого на удаленном компьютере, отредактировать файл, чтобы исправить ошибку, а затем снова запустить обновленный сценарий.

## <a name="advanced-script-debugging"></a>Расширенная отладка сценариев

Стали доступны новые расширенные функции отладки, которые позволяют подключиться к любому процессу локального компьютера, загруженному в PowerShell, и осуществить отладку произвольных пространств выполнения в нем.

### <a name="runspace-debugging"></a>Отладка пространств выполнения

Были добавлены новые командлеты, позволяющие вывести список текущих пространств выполнения в процессе, а также подключить консоль PowerShell или отладчик интегрированной среды сценариев к такому пространству для отладки сценариев:

- Get-Runspace
- Debug-Runspace
- Enable-RunspaceDebug
- Disable-RunspaceDebug
- Get-RunspaceDebug

### <a name="attach-to-process-hosting-powershell"></a>Подключение к процессу, в котором размещается PowerShell

Теперь вы можете подключиться к любому процессу компьютера с загруженным PowerShell. Чтобы сделать это, войдите в интерактивный сеанс с процессом узла. Дополнительные сведения см. в разделе:

- [Enter-PSHostProcess](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [Exit-PSHostProcess](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)

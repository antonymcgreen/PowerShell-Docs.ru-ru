---
ms.date: 08/11/2020
keywords: dsc,powershell,конфигурация,установка
title: Прямой вызов методов ресурсов DSC
description: Командлет Invoke-DscResource можно использовать для вызова функций или методов ресурса DSC. Этот командлет могут использовать сторонние разработчики, которым требуется использовать ресурсы DSC. Кроме того, он удобен для разработки ресурсов.
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650991"
---
# <a name="calling-dsc-resource-methods-directly"></a>Прямой вызов методов ресурсов DSC

> Область применения: Windows PowerShell 5.0

Командлет [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) можно использовать для прямого вызова функций или методов ресурса DSC (функций `Get-TargetResource`, `Set-TargetResource` и `Test-TargetResource` ресурса на основе MOF-файла или методов **Get** , **Set** и **Test** ресурса на основе класса). Этот командлет могут использовать сторонние разработчики, которым требуется использовать ресурсы DSC, кроме того, он удобен для разработки ресурсов.

> [!NOTE]
> В PowerShell 7.0 и более поздних версий `Invoke-DscResource` больше не поддерживает вызов ресурсов DSC WMI. Сюда входят ресурсы **файл** и **журнал** в **PSDesiredStateConfiguration**.

Командлет обычно используется в сочетании со свойством метаконфигурации `refreshMode = 'Disabled'`, однако он доступен независимо от значения **refreshMode**.

При вызове командлета `Invoke-DscResource` указать, какой метод или функцию необходимо вызвать, можно с помощью параметра **Method**. Свойства ресурса указываются путем передачи хэш-таблицы в качестве значения параметра **Property**.

Ниже приведены примеры прямого вызова методов ресурсов:

## <a name="ensure-a-file-is-present"></a>Проверка наличия файла

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a>Тестирование наличия файла

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a>Получение содержимого файла

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> Прямой вызов методов составного ресурса не поддерживается. Вместо этого вызывайте методы базовых ресурсов, входящих в составной ресурс.

## <a name="see-also"></a>См. также:

- [Написание пользовательских ресурсов DSC с использованием MOF](../resources/authoringResourceMOF.md)
- [Написание пользовательских ресурсов DSC с использованием классов PowerShell](../resources/authoringResourceClass.md)
- [Отладка ресурсов DSC](../troubleshooting/debugResource.md)

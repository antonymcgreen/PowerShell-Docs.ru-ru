---
ms.date: 07/17/2020
ms.topic: reference
title: Метод ResourceSet
description: Метод ResourceSet
ms.openlocfilehash: 2554ff5805d7ed9518bd283565dc879a0fdfdfd0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650688"
---
# <a name="resourceset-method"></a>Метод ResourceSet

Напрямую вызывает метод **Set** ресурса DSC.

## <a name="syntax"></a>Синтаксис

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a>Параметры

**ResourceType** \[in\] Имя вызываемого ресурса.

**ModuleName** \[in\] Имя модуля, содержащего вызываемый ресурс.

**resourceProperty** \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно. Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.

**RebootRequired** \[out\] В выходных данных это свойство имеет значение **true** , если целевой узел необходимо перезагрузить.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

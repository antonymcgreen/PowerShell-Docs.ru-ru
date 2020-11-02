---
ms.date: 07/17/2020
ms.topic: reference
title: Метод StopConfiguration
description: Метод StopConfiguration
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644622"
---
# <a name="stopconfiguration-method"></a>Метод StopConfiguration

Останавливает выполняемое изменение конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>Параметры

**force** \[in\] **true** Принудительная остановка конфигурации.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

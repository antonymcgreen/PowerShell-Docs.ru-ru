---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendMetaConfigurationApply
description: Метод SendMetaConfigurationApply
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648966"
---
# <a name="sendmetaconfigurationapply-method"></a>Метод SendMetaConfigurationApply

Задает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a>Параметры

**ConfigurationData** \[in\] Данные среды для конфигурации.

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

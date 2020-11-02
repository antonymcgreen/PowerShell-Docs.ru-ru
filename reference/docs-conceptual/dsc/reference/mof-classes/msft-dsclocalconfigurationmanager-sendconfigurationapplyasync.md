---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendConfigurationApplyAsync
description: Метод SendConfigurationApplyAsync
ms.openlocfilehash: 92c9d03a7653e72b1ff04084caea4a8b5aadb0e5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644789"
---
# <a name="sendconfigurationapplyasync-method"></a>Метод SendConfigurationApplyAsync

Асинхронно отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a>Параметры

**ConfigurationData** \[in\] Данные среды для конфигурации.

**force** \[in\] **true** Принудительная остановка конфигурации.

**jobId** \[in\] Идентификатор задания, для которого отправляется конфигурация.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

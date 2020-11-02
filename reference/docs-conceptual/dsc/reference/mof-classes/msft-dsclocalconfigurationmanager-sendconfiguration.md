---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendConfiguration
description: Метод SendConfiguration
ms.openlocfilehash: 3939a76ab6672b49559847b0ef1408f1c7be6d0c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650561"
---
# <a name="sendconfiguration-method"></a>Метод SendConfiguration

Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.

## <a name="syntax"></a>Синтаксис

```mof
uint32 SendConfiguration(
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

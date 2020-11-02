---
ms.date: 07/17/2020
ms.topic: reference
title: Метод TestConfiguration
description: Метод TestConfiguration
ms.openlocfilehash: ed26fcad2286ca753fb4b1845b8c6ad0741d491b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648930"
---
# <a name="testconfiguration-method"></a>Метод TestConfiguration

Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.

## <a name="syntax"></a>Синтаксис

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a>Параметры

**configurationData** \[in\]. Данные среды для конфигурации.

**InDesiredState** \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.

**ResourcesInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState** , определяющий ресурсы, которые находятся в нужном состоянии.

**ResourcesNotInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState** , определяющий ресурсы, которые не находятся в нужном состоянии.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

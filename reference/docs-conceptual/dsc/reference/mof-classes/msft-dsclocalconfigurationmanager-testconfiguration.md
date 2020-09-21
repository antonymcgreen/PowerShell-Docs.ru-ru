---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод TestConfiguration
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464304"
---
# <a name="testconfiguration-method"></a>Метод TestConfiguration

Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.

## <a name="syntax"></a>Синтаксис

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a>Параметры

**configurationData** \[in\]. Данные среды для конфигурации.

**InDesiredState** \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.

**ResourcesInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState**, определяющий ресурсы, которые находятся в нужном состоянии.

**ResourcesNotInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState**, определяющий ресурсы, которые не находятся в нужном состоянии.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

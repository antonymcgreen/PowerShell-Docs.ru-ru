---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfiguration
ms.openlocfilehash: 989aeef4cd9aa5d55741b48c8565c657c4b6512c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463828"
---
# <a name="getconfiguration-method"></a>Метод GetConfiguration

Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a>Параметры

**configurationData** \[in\] Указывает передаваемые данные конфигурации.

**configurations** \[out\] Выходные данные содержат встроенный экземпляр конфигураций.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

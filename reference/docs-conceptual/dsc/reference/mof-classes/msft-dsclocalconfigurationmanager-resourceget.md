---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceGet
ms.openlocfilehash: aa7671989db6f4a98d879fd449d09503eddbeda3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463964"
---
# <a name="resourceget-method"></a>Метод ResourceGet

Напрямую вызывает метод **Get** ресурса DSC.

## <a name="syntax"></a>Синтаксис

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a>Параметры

**ResourceType** \[in\] Имя вызываемого ресурса.

**ModuleName** \[in\] Имя модуля, содержащего вызываемый ресурс.

**resourceProperty** \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно. Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.

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

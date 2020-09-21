---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceTest
ms.openlocfilehash: 7ef65227342091cb2a5063aaf95a2780d217f85a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463811"
---
# <a name="resourcetest-method"></a>Метод ResourceTest

Напрямую вызывает метод **Test** ресурса DSC.

## <a name="syntax"></a>Синтаксис

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a>Параметры

**ResourceType** \[in\] Имя вызываемого ресурса.

**ModuleName** \[in\] Имя модуля, содержащего вызываемый ресурс.

***resourceProperty** \[in\]. Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно. Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.

*InDesiredState** \[out\]. В выходных данных это свойство имеет значение **true**, если целевой узел находится в нужном состоянии.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

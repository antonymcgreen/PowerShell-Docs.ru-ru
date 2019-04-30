---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: ae31ac30c152c96707b764ddaf00c924806afcfc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078659"
---
# <a name="getconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод GetConfiguration класса MSFT_DSCLocalConfigurationManager

Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a>Параметры

*configurationData* \[in\] Указывает передаваемые данные конфигурации.

*configurations* \[out\] Выходные данные содержат встроенный экземпляр конфигураций.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
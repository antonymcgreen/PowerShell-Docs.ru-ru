---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 3529bc56ecba19ed0fbbf070a4e86d0692824d39
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078390"
---
# <a name="sendconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager

Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.

## <a name="syntax"></a>Синтаксис

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a>Параметры

*ConfigurationData* \[in\] Данные среды для конфигурации.

*force* \[in\] **true** для принудительной остановки конфигурации.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
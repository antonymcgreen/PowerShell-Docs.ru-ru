---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод TestConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: d746832b01310f43a7aae33dd0fa70c0928bb3e0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078084"
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод TestConfiguration класса MSFT_DSCLocalConfigurationManager

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

*configurationData* \[in\] Данные среды для конфигурации.

*InDesiredState* \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.

*ResourcesInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState**, указывающий ресурсы, которые находятся в нужном состоянии.

*ResourcesNotInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState**, указывающий ресурсы, которые не находятся в нужном состоянии.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
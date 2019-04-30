---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceTest класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e7645b0c6b93b96cb01f72c1c92d468f7642ea13
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078560"
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод ResourceTest класса MSFT_DSCLocalConfigurationManager

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

*ResourceType* \[in\] Имя вызываемого ресурса.

*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.

*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно. Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.

*InDesiredState* \[out\] В выходных данных это свойство имеет значение **true**, если целевой узел находится в нужном состоянии.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
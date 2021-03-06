---
title: Get işlevi (yönetilmeyen API Başvurusu)
description: Get işlevi, belirtilen özellik değerini alır.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb7475623961fe2ee5fc821c5f237f0a2acfae1a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507668"
---
# <a name="get-function"></a>Get işlevi
Varsa belirtilen özelliğin değerini alır.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`  
[in] Bu parametre kullanılmaz.

`ptr`  
[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.

`wszName`  
[in] Özelliğin adı.

`lFlags` [in] Ayrılmış. Bu parametre 0 olmalıdır.

`pVal` [out] İşlev başarıyla döndürürse, değerini içeren `wszName` özelliği. `pval` Bağımsız değişkeni doğru tür ve niteleyici değeri atanır.

`pvtType` [out] İşlev başarıyla döndürürse, içeren bir [CIM türü sabiti](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) özellik türü gösterir. Değeri de olabilir `null`. 

`plFlavor` [out] İşlev başarıyla döndürürse, özellik kaynağı hakkındaki bilgileri alır. Değeri olabilir `null`, veya tanımlanan WBEM_FLAVOR_TYPE sabitlerden biri *WbemCli.h* üst bilgi dosyası: 

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Standart sistem özelliği özelliğidir. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Bir sınıf için: özellik üst sınıftan devralınır. </br> Bir örneği için: özellik üst sınıftan devralındı sırada örneği tarafından değiştirilmedi.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Bir sınıf için: özelliği türetilmiş bir sınıfa aittir. </br> Bir örneği için: özelliğin bir örneği tarafından; değiştirilir diğer bir deyişle, bir değer sağlanmamış veya niteleyicisi eklenemez veya değiştirilemez. |

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Bir veya daha fazla parametre geçerli değil. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Belirtilen özellik bulunamadı. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | İşlemi tamamlamak yeterli bellek yok. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) yöntemi.

`Get` İşlev Ayrıca Sistem özellikleri döndürür.

`pVal` Bağımsız değişkeni doğru tür ve değer niteleyicisi ve COM atandığı [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) işlevi

## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)

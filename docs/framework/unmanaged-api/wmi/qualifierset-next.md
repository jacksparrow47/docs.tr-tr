---
title: QualifierSet_Next işlevi (yönetilmeyen API Başvurusu)
description: Bir listedeki sonraki niteleyicisi QualifierSet_Next işlevi alır.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 938044a4e932139eb8a4d0a5d2f998cbc6f193cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507699"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next işlevi
Bir çağrı ile başlatılan bir listedeki sonraki niteleyicisi alır [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) işlevi.   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`   
[in] Bu parametre kullanılmaz.

`ptr`   
[in] Bir işaretçi bir [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) örneği.

`lFlags`   
[in] Ayrılmış. Bu parametre 0 olmalıdır.

`pstrName`   
[out] Niteleyicisi adı. Varsa `null`, bu parametre yoksayıldı; Aksi takdirde `pstrName` geçerli bir işaret etmelidir değil `BSTR` veya bir bellek sızıntısı olur. Null, işlev her zaman yeni bir ayırır, `BSTR` döndüğünde, `WBEM_S_NO_ERROR`.

`pVal`   
[out] Başarılı olduğunda, Niteleyici değeri. İşlev başarısız olursa `VARIANT` işaret ettiği `pVal` değiştirilmez. Bu parametre `null`, parametre yoksayılır.

`plFlavor`   
[out] Niteleyici özelliği alan uzun bir işaretçi. Flavor bilgi istenildiği gibi değilse, bu parametre olabilir `null`. 

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Bir parametre geçerli değil. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Çağıranın çağrılmayan [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Yeni bir numaralandırma başlatmak yeterli bellek yok. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Hiçbir daha fazla niteleyici numaralandırmada bırakılır. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) yöntemi.

Çağırmanızı `QualifierSet_Next` işlevi dönüş işlevi kadar tüm niteleyicileri art arda Numaralandırılacak `WBEM_S_NO_MORE_DATA`. Numaralandırma erken sonlandırmak için çağrı [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) işlevi.

Numaralandırma sırasında döndürülen niteleyici sırası tanımlanmamıştır.

## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)

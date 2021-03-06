---
title: GetPropertyOrigin işlevi (Unmnaged API Başvurusu)
description: GetPropertyOrigin işlevi, bir özellik içinde bildirildiği sınıf belirler.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86c512f25c40f201d818b6789c6410bfb095b878
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488124"
---
# <a name="getpropertyorigin-function"></a>GetPropertyOrigin işlevi
Bir özellik içinde bildirildiği sınıf belirler.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`  
[in] Bu parametre kullanılmaz.

`ptr`  
[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.

`wszMethodName`  
[in] Özelliğin adı, sahibi olan sınıfı istenen nesne için. 

`pstrClassName`  
[out] Özellik sahibi sınıfının adını alır.

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Belirtilen özellik bulunamadı. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Bir parametre geçerli değil. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | İşlemi tamamlamak yeterli bellek yok. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) yöntemi.

Bir sınıf özelliklerini bir veya daha fazla temel sınıftan devralabilir olduğundan, geliştiriciler genellikle belirli bir yöntemin tanımlandığı özellik belirlemek istersiniz.

`pstrClassName` Parametre gerekir işaret geçerli bir `BSTR` çünkü bu işlevi çağrılmadan önce bir `out` parametre; bu işaretçisi işlev döndürdükten sonra serbest.

## <a name="requirements"></a>Gereksinimler  
**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)

---
title: ICorDebugRegisterSet::GetThreadContext Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 632d3912bae28da22e701078bb47d2d8dbfd3644
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423409"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext Metodu
Geçerli iş parçacığının bağlamını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `contextSize`  
 [in] Bayt olarak boyutu, `context` dizi.  
  
 `context`  
 [içinde out] Win32 oluşturan bir bayt dizisi `CONTEXT` geçerli platform için yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklayıcı Win32 yerine bu işlev çağırmalıdır `GetThreadContext` işlev çünkü iş parçacığı burada onun içeriği geçici olarak değiştirildi "ele geçirilen" bir durumda olabilir. Döndürülen veriler bir Win32 olduğu `CONTEXT` geçerli platform için yapısı.  
  
 Yaprak olmayan çerçeveler için istemcileri kullanarak hangi kayıtları geçerli denetlemelisiniz [Icordebugregisterset::getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorDebugRegisterSet Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
